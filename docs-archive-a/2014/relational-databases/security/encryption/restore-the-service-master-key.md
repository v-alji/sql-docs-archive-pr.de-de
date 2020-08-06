---
title: Wiederherstellen des Diensthauptschlüssels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 2ad99fc9baa518d50678ddd6e6db1ec554658823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726846"
---
# <a name="restore-the-service-master-key"></a><span data-ttu-id="e1c5b-102">Wiederherstellen des Diensthauptschlüssels</span><span class="sxs-lookup"><span data-stu-id="e1c5b-102">Restore the Service Master Key</span></span>
  <span data-ttu-id="e1c5b-103">In diesem Thema wird beschrieben, wie der Diensthauptschlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-103">This topic describes how to restore the service master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e1c5b-104">Es ist unwahrscheinlich, dass die Notwendigkeit zum Wiederherstellen des Diensthauptschlüssels eintreten wird.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-104">It is unlikely that you will ever need to restore the service master key.</span></span> <span data-ttu-id="e1c5b-105">Sollte dies doch erforderlich sein, muss dies mit äußerster Sorgfalt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-105">If you do, you should proceed with extreme caution.</span></span> <span data-ttu-id="e1c5b-106">Weitere Informationen finden Sie unter [Back Up the Service Master Key](service-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="e1c5b-106">For more information, see [Back Up the Service Master Key](service-master-key.md).</span></span>  
  
 <span data-ttu-id="e1c5b-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e1c5b-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e1c5b-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e1c5b-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e1c5b-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e1c5b-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e1c5b-110">Security</span><span class="sxs-lookup"><span data-stu-id="e1c5b-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="e1c5b-111">So stellen Sie den Diensthauptschlüssel mithilfe von Transact-SQL wieder her</span><span class="sxs-lookup"><span data-stu-id="e1c5b-111">To restore the service master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e1c5b-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e1c5b-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e1c5b-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e1c5b-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e1c5b-114">Bei der Wiederherstellung des Diensthauptschlüssels werden alle Schlüssel und geheimen Bereiche von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] entschlüsselt, die mit dem aktuellen Diensthauptschlüssel verschlüsselt wurden. Diese Schlüssel werden dann mit dem aus der Sicherungsdatei geladenen Diensthauptschlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-114">When the service master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys and secrets that have been encrypted with the current service master key, and then encrypts them with the service master key loaded from the backup file.</span></span>  
  
-   <span data-ttu-id="e1c5b-115">Falls einer dieser Entschlüsselungsvorgänge nicht erfolgreich ausgeführt werden kann, tritt bei der Wiederherstellung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-115">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="e1c5b-116">Sie können die FORCE-Option verwenden, um Fehler zu ignorieren, dies kann jedoch zum Verlust von Daten führen, die nicht entschlüsselt werden können.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-116">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="e1c5b-117">Das Neugenerieren der Verschlüsselungshierarchie ist ein ressourcenintensiver Vorgang.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-117">Regenerating the encryption hierarchy is a resource-intensive operation.</span></span> <span data-ttu-id="e1c5b-118">Die Ausführung dieses Vorgangs sollte außerhalb der Hauptzeiten geplant werden.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-118">You should schedule this during a period of low demand.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e1c5b-119">Der Diensthauptschlüssel ist der Stamm der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-119">The service master key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="e1c5b-120">Mit dem Diensthauptschlüssel werden alle Schlüssel in der Struktur direkt oder indirekt geschützt.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-120">The service master key directly or indirectly secures all other keys in the tree.</span></span> <span data-ttu-id="e1c5b-121">Wenn ein abhängiger Schlüssel während der erzwungenen Wiederherstellung nicht entschlüsselt werden kann, gehen die durch diesen Schlüssel geschützten Daten verloren.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-121">If a dependent key cannot be decrypted during a forced restore, data that is secured by that key will be lost.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1c5b-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e1c5b-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e1c5b-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e1c5b-123">Permissions</span></span>  
 <span data-ttu-id="e1c5b-124">Erfordert die CONTROL SERVER-Berechtigung auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-124">Requires CONTROL SERVER permission on the server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e1c5b-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1c5b-125">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-the-service-master-key"></a><span data-ttu-id="e1c5b-126">So stellen Sie den Diensthauptschlüssel wieder her</span><span class="sxs-lookup"><span data-stu-id="e1c5b-126">To restore the service master key</span></span>  
  
1.  <span data-ttu-id="e1c5b-127">Rufen Sie entweder von einem physischen Sicherungsmedium oder einem Verzeichnis im lokalen Dateisystem eine Kopie des gesicherten Diensthauptschlüssels ab.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-127">Retrieve a copy of the backed-up service master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="e1c5b-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="e1c5b-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-129">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="e1c5b-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="e1c5b-131">Der Dateipfad zum Schlüssel und das Kennwort (sofern es vorhanden ist) des Schlüssels unterscheiden sich von den obigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-131">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="e1c5b-132">Stellen Sie sicher, dass beide für den Server und die Schlüsseleinrichtung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-132">Please make sure that both are specific to your server and key set-up.</span></span>  
  
  
