---
title: Sichern eines Datenbank-Hauptschlüssels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], exporting
ms.assetid: 7ad9a0a0-6e4f-4f7b-8801-8c1b9d49c4d8
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 9a66d28fea8289719d3efb2351409e0f14379ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725406"
---
# <a name="back-up-a-database-master-key"></a><span data-ttu-id="0a9cd-102">Sichern eines Datenbank-Hauptschlüssels</span><span class="sxs-lookup"><span data-stu-id="0a9cd-102">Back Up a Database Master Key</span></span>
  <span data-ttu-id="0a9cd-103">In diesem Thema wird beschrieben, wie der Datenbank-Hauptschlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-103">This topic describes how to back up a database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0a9cd-104">Der Datenbank-Hauptschlüssel wird zur Verschlüsselung anderer Schlüssel und Zertifikate in einer Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-104">The database master key is used to encrypt other keys and certificates inside a database.</span></span> <span data-ttu-id="0a9cd-105">Wenn dieser Schlüssel beschädigt oder gelöscht wird, können die anderen Schlüssel möglicherweise von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nicht entschlüsselt werden, und die damit verschlüsselten Daten gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-105">If it is deleted or corrupted, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may be unable to decrypt those keys, and the data encrypted using them will be effectively lost.</span></span> <span data-ttu-id="0a9cd-106">Aus diesem Grund sollten Sie den Datenbank-Hauptschlüssel sichern und diese Sicherung an einem sicheren Ort außerhalb Ihrer Geschäftsräume aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-106">For this reason, you should back up the database master key and store the backup in a secure off-site location.</span></span>  
  
 <span data-ttu-id="0a9cd-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="0a9cd-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a9cd-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="0a9cd-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a9cd-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0a9cd-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0a9cd-110">Security</span><span class="sxs-lookup"><span data-stu-id="0a9cd-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="0a9cd-111">So sichern Sie den Datenbank-Hauptschlüssel mithilfe von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a9cd-111">To back up a database master key using Transact-SQL</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a9cd-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0a9cd-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0a9cd-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0a9cd-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0a9cd-114">Der Hauptschlüssel muss geöffnet und entschlüsselt sein, bevor er gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="0a9cd-115">Wenn er mit dem Diensthauptschlüssel verschlüsselt ist, muss der Hauptschlüssel nicht explizit geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened.</span></span> <span data-ttu-id="0a9cd-116">Falls der Hauptschlüssel jedoch nur mit einem Kennwort verschlüsselt ist, muss er explizit geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-116">But if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="0a9cd-117">Es wird empfohlen, dass Sie sofort nach der Erstellung eine Sicherung des Hauptschlüssels anlegen und diese an einem sicheren Ort außerhalb Ihrer Geschäftsräume aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-117">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a9cd-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0a9cd-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a9cd-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0a9cd-119">Permissions</span></span>  
 <span data-ttu-id="0a9cd-120">Erfordert die CONTROL-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-120">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="Procedure"></a><span data-ttu-id="0a9cd-121">Verwenden von SQL Server Management Studio mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a9cd-121">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-database-master-key"></a><span data-ttu-id="0a9cd-122">So sichern Sie den Datenbank-Hauptschlüssel</span><span class="sxs-lookup"><span data-stu-id="0a9cd-122">To back-up the database master key</span></span>  
  
1.  <span data-ttu-id="0a9cd-123">Stellen Sie in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]eine Verbindung mit der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz her, die den zu sichernden Datenbank-Hauptschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the database master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="0a9cd-124">Geben Sie ein Kennwort an, mit dem der Datenbank-Hauptschlüssel auf dem Sicherungsmedium verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-124">Choose a password that will be used to encrypt the database master key on the backup medium.</span></span> <span data-ttu-id="0a9cd-125">Dieses Kennwort unterliegt Komplexitätsüberprüfungen.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-125">This password is subject to complexity checks.</span></span>  
  
3.  <span data-ttu-id="0a9cd-126">Verwenden Sie ein Wechselsicherungsmedium, auf dem eine Kopie des gesicherten Schlüssels gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="0a9cd-127">Ermitteln Sie ein NTFS-Verzeichnis, in dem die Sicherung des Schlüssels erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="0a9cd-128">In diesem Verzeichnis erstellen Sie die im nächsten Schritt beschriebene Datei.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="0a9cd-129">Das Verzeichnis sollte durch stark einschränkende Zugriffssteuerungslisten (Access Control Lists, ACLs) geschützt sein.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="0a9cd-130">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="0a9cd-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="0a9cd-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key. Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;   
    GO  
    OPEN MASTER KEY DECRYPTION BY PASSWORD = 'sfj5300osdVdgwdfkli7';   
  
    BACKUP MASTER KEY TO FILE = 'c:\temp\exportedmasterkey'   
        ENCRYPTION BY PASSWORD = 'sd092735kjn$&adsg';   
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a9cd-133">Der Dateipfad zum Schlüssel und das Kennwort (sofern es vorhanden ist) des Schlüssels unterscheiden sich von den obigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="0a9cd-134">Stellen Sie sicher, dass beide für den Server und die Schlüsseleinrichtung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-134">Please make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="0a9cd-135">Kopieren Sie die Datei auf das Sicherungsmedium, und überprüfen Sie die Kopie.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="0a9cd-136">Verwahren Sie die Sicherung an einem sicheren Ort außerhalb der Geschäftsräume.</span><span class="sxs-lookup"><span data-stu-id="0a9cd-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="0a9cd-137">Weitere Informationen finden Sie unter [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) und [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0a9cd-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
