---
title: Wiederherstellen eines Datenbank-Hauptschlüssels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 614ba8bdc494ae7e7e5b3ed7b62390721ef642a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726845"
---
# <a name="restore-a-database-master-key"></a><span data-ttu-id="7c9cc-102">Wiederherstellen eines Datenbank-Hauptschlüssels</span><span class="sxs-lookup"><span data-stu-id="7c9cc-102">Restore a Database Master Key</span></span>
  <span data-ttu-id="7c9cc-103">In diesem Thema wird beschrieben, wie der Datenbank-Hauptschlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-103">This topic describes how to restore the database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7c9cc-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7c9cc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7c9cc-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7c9cc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7c9cc-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7c9cc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7c9cc-107">Security</span><span class="sxs-lookup"><span data-stu-id="7c9cc-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="7c9cc-108">So stellen Sie den Datenbank-Hauptschlüssel mithilfe von Transact-SQL wieder her</span><span class="sxs-lookup"><span data-stu-id="7c9cc-108">To restore the database master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7c9cc-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7c9cc-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7c9cc-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7c9cc-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7c9cc-111">Bei der Wiederherstellung des Hauptschlüssels werden alle Schlüssel von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] entschlüsselt, die mit dem aktuell aktiven Hauptschlüssel verschlüsselt sind. Diese Schlüssel werden dann mit dem wiederhergestellten Hauptschlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-111">When the master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys that are encrypted with the currently active master key, and then encrypts these keys with the restored master key.</span></span> <span data-ttu-id="7c9cc-112">Die Ausführung dieses ressourcenintensiven Vorgangs sollte außerhalb der Hauptzeiten geplant werden.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-112">This resource-intensive operation should be scheduled during a period of low demand.</span></span> <span data-ttu-id="7c9cc-113">Falls der aktuelle Datenbank-Hauptschlüssel nicht geöffnet ist oder nicht geöffnet werden kann oder falls einer der Schlüssel, die mit ihm verschlüsselt sind, nicht entschlüsselt werden kann, kann der Wiederherstellungsvorgang nicht erfolgreich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-113">If the current database master key is not open or cannot be opened, or if any of the keys that are encrypted by it cannot be decrypted, the restore operation fails.</span></span>  
  
-   <span data-ttu-id="7c9cc-114">Falls einer dieser Entschlüsselungsvorgänge nicht erfolgreich ausgeführt werden kann, tritt bei der Wiederherstellung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-114">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="7c9cc-115">Sie können die FORCE-Option verwenden, um Fehler zu ignorieren, dies kann jedoch zum Verlust von Daten führen, die nicht entschlüsselt werden können.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-115">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="7c9cc-116">Wurde der Hauptschlüssel mit dem Diensthauptschlüssel verschlüsselt, wird auch der wiederhergestellte Hauptschlüssel mit dem Diensthauptschlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-116">If the master key was encrypted by the service master key, the restored master key will also be encrypted by the service master key.</span></span>  
  
-   <span data-ttu-id="7c9cc-117">Falls in der aktuellen Datenbank kein Hauptschlüssel vorhanden ist, wird von RESTORE MASTER KEY ein Hauptschlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-117">If there is no master key in the current database, RESTORE MASTER KEY creates a master key.</span></span> <span data-ttu-id="7c9cc-118">Der neue Hauptschlüssel wird nicht automatisch mit dem Diensthauptschlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-118">The new master key will not be automatically encrypted with the service master key.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7c9cc-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7c9cc-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7c9cc-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7c9cc-120">Permissions</span></span>  
 <span data-ttu-id="7c9cc-121">Erfordert die CONTROL-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-121">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="SSMSProcedure"></a><span data-ttu-id="7c9cc-122">Verwenden von SQL Server Management Studio mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c9cc-122">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-restore-the-database-master-key"></a><span data-ttu-id="7c9cc-123">So stellen Sie den Datenbank-Hauptschlüssel wieder her</span><span class="sxs-lookup"><span data-stu-id="7c9cc-123">To restore the database master key</span></span>  
  
1.  <span data-ttu-id="7c9cc-124">Rufen Sie entweder von einem physischen Sicherungsmedium oder einem Verzeichnis im lokalen Dateisystem eine Kopie des gesicherten Datenbank-Hauptschlüssels ab.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-124">Retrieve a copy of the backed-up database master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="7c9cc-125">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="7c9cc-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-126">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="7c9cc-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c9cc-128">Der Dateipfad zum Schlüssel und das Kennwort (sofern es vorhanden ist) des Schlüssels unterscheiden sich von den obigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-128">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="7c9cc-129">Stellen Sie sicher, dass beide für den Server und die Schlüsseleinrichtung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-129">Please make sure that both are specific to your server and key set-up.</span></span>  
  
 <span data-ttu-id="7c9cc-130">Weitere Informationen finden Sie unter [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7c9cc-130">For more information, see [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span></span>  
  
  
