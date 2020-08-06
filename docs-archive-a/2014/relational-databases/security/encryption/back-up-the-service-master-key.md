---
title: Sichern des Diensthauptschlüssels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], exporting
ms.assetid: f60b917c-6408-48be-b911-f93b05796904
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: b79212040df67c22ae7e34cd380a1a1f1bd10773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725401"
---
# <a name="back-up-the-service-master-key"></a><span data-ttu-id="927c3-102">Sichern des Diensthauptschlüssels</span><span class="sxs-lookup"><span data-stu-id="927c3-102">Back Up the Service Master Key</span></span>
  <span data-ttu-id="927c3-103">In diesem Thema wird beschrieben, wie der Diensthauptschlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="927c3-103">This topic describes how to back-up the Service Master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="927c3-104">Der Diensthauptschlüssel ist der Stamm der Verschlüsselungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="927c3-104">The service master key is the root of the encryption hierarchy.</span></span> <span data-ttu-id="927c3-105">Er sollte gesichert und an einem sicheren Ort außerhalb der Geschäftsräume aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="927c3-105">It should be backed up and stored in a secure, off-site location.</span></span> <span data-ttu-id="927c3-106">Das Erstellen dieser Sicherung sollte eine der ersten administrativen Aktionen sein, die auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="927c3-106">Creating this backup should be one of the first administrative actions performed on the server.</span></span>  
  
 <span data-ttu-id="927c3-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="927c3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="927c3-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="927c3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="927c3-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="927c3-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="927c3-110">Security</span><span class="sxs-lookup"><span data-stu-id="927c3-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="927c3-111">So sichern Sie den Diensthauptschlüssel</span><span class="sxs-lookup"><span data-stu-id="927c3-111">To back-up the Service Master key</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="927c3-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="927c3-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="927c3-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="927c3-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="927c3-114">Der Hauptschlüssel muss geöffnet und entschlüsselt sein, bevor er gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="927c3-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="927c3-115">Wenn er mit dem Diensthauptschlüssel verschlüsselt wird, muss der Hauptschlüssel nicht explizit geöffnet werden. Wenn der Hauptschlüssel jedoch nur mit einem Kennwort verschlüsselt wird, muss er explizit geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="927c3-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened; however, if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="927c3-116">Es wird empfohlen, dass Sie sofort nach der Erstellung eine Sicherung des Hauptschlüssels anlegen und diese an einem sicheren Ort außerhalb Ihrer Geschäftsräume aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="927c3-116">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="927c3-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="927c3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="927c3-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="927c3-118">Permissions</span></span>  
 <span data-ttu-id="927c3-119">Erfordert die CONTROL-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="927c3-119">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="Procedure"></a> <span data-ttu-id="927c3-120">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="927c3-120">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-service-master-key"></a><span data-ttu-id="927c3-121">So sichern Sie den Diensthauptschlüssel</span><span class="sxs-lookup"><span data-stu-id="927c3-121">To back-up the Service Master key</span></span>  
  
1.  <span data-ttu-id="927c3-122">Stellen Sie in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]eine Verbindung mit der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz her, die den zu sichernden Diensthauptschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="927c3-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the service master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="927c3-123">Wählen Sie das Kennwort, das zum Verschlüsseln des Diensthauptschlüssels auf dem Sicherungsmedium verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="927c3-123">Choose a password that will be used to encrypt the service master key on the backup medium.</span></span> <span data-ttu-id="927c3-124">Dieses Kennwort unterliegt Komplexitätsüberprüfungen.</span><span class="sxs-lookup"><span data-stu-id="927c3-124">This password is subject to complexity checks.</span></span> <span data-ttu-id="927c3-125">Weitere Informationen finden Sie unter [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="927c3-125">For more information, see [Password Policy](../password-policy.md).</span></span>  
  
3.  <span data-ttu-id="927c3-126">Verwenden Sie ein Wechselsicherungsmedium, auf dem eine Kopie des gesicherten Schlüssels gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="927c3-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="927c3-127">Ermitteln Sie ein NTFS-Verzeichnis, in dem die Sicherung des Schlüssels erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="927c3-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="927c3-128">In diesem Verzeichnis erstellen Sie die im nächsten Schritt beschriebene Datei.</span><span class="sxs-lookup"><span data-stu-id="927c3-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="927c3-129">Das Verzeichnis sollte durch stark einschränkende Zugriffssteuerungslisten (Access Control Lists, ACLs) geschützt sein.</span><span class="sxs-lookup"><span data-stu-id="927c3-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="927c3-130">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="927c3-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="927c3-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="927c3-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="927c3-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="927c3-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key.  
    -- Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;  
    GO  
    BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_ key'   
        ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="927c3-133">Der Dateipfad zum Schlüssel und das Kennwort (sofern es vorhanden ist) des Schlüssels unterscheiden sich von den obigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="927c3-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="927c3-134">Stellen Sie sicher, dass beide für den Server und die Schlüsseleinrichtung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="927c3-134">Make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="927c3-135">Kopieren Sie die Datei auf das Sicherungsmedium, und überprüfen Sie die Kopie.</span><span class="sxs-lookup"><span data-stu-id="927c3-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="927c3-136">Verwahren Sie die Sicherung an einem sicheren Ort außerhalb der Geschäftsräume.</span><span class="sxs-lookup"><span data-stu-id="927c3-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="927c3-137">Weitere Informationen finden Sie unter [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) und [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="927c3-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
