---
title: Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8aa92296da81f984f260deace887c15f13443b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726021"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a><span data-ttu-id="09054-102">Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="09054-102">Define a Logical Backup Device for a Disk File (SQL Server)</span></span>
  <span data-ttu-id="09054-103">In diesem Thema wird beschrieben, wie Sie ein logisches Sicherungsmedium für eine Datenträgerdatei in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]definieren.</span><span class="sxs-lookup"><span data-stu-id="09054-103">This topic describes how to define a logical backup device for a disk file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="09054-104">Ein logisches Medium ist ein benutzerdefinierter Name, der auf ein bestimmtes, physisches Sicherungsmedium (Datenträgerdatei oder Bandlaufwerk) verweist.</span><span class="sxs-lookup"><span data-stu-id="09054-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="09054-105">Die Initialisierung des physischen Mediums erfolgt später, wenn eine Sicherung auf das Sicherungsmedium geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="09054-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
 <span data-ttu-id="09054-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="09054-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09054-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="09054-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09054-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="09054-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="09054-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="09054-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="09054-110">Security</span><span class="sxs-lookup"><span data-stu-id="09054-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="09054-111">**So definieren Sie ein logisches Sicherungsmedium für eine Datenträgerdatei mit**</span><span class="sxs-lookup"><span data-stu-id="09054-111">**To define a logical backup device for a disk file, using:**</span></span>  
  
     [<span data-ttu-id="09054-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09054-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="09054-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09054-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09054-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="09054-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="09054-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="09054-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="09054-116">Der Name des logischen Mediums muss innerhalb der logischen Sicherungsmedien auf der Serverinstanz eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="09054-116">The logical device name must be unique among all the logical backup devices on the server instance.</span></span> <span data-ttu-id="09054-117">Sie können sich die vorhandenen logischen Mediennamen anzeigen lassen, indem Sie eine Abfrage für die [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) -Katalogsicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="09054-117">To view the existing logical device names, query the [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) catalog view.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="09054-118">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="09054-118">Recommendations</span></span>  
  
-   <span data-ttu-id="09054-119">Als Sicherungsdatenträger sollte ein anderer Datenträger als für die Datenbankdaten und Protokolldatenträger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="09054-119">We recommend that a backup disk be a different disk than the database data and log disks.</span></span> <span data-ttu-id="09054-120">Nur so kann sichergestellt werden, dass Sie auch dann auf die Sicherungen zugreifen können, wenn die Daten- oder Protokolldatenträger ausfallen.</span><span class="sxs-lookup"><span data-stu-id="09054-120">This is necessary to make sure that you can access the backups if the data or log disk fails.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09054-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="09054-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09054-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="09054-122">Permissions</span></span>  
 <span data-ttu-id="09054-123">Erfordert die Mitgliedschaft in der festen Serverrolle **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="09054-123">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="09054-124">Erfordert die Berechtigung zum Schreiben auf den Datenträger.</span><span class="sxs-lookup"><span data-stu-id="09054-124">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09054-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09054-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a><span data-ttu-id="09054-126">So definieren Sie ein logisches Sicherungsmedium für eine Datenträgerdatei</span><span class="sxs-lookup"><span data-stu-id="09054-126">To define a logical backup device for a disk file</span></span>  
  
1.  <span data-ttu-id="09054-127">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="09054-127">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="09054-128">Erweitern Sie **Serverobjekte**, und klicken Sie dann mit der rechten Maustaste auf **Sicherungsmedien**.</span><span class="sxs-lookup"><span data-stu-id="09054-128">Expand **Server Objects**, and right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="09054-129">Klicken Sie auf **Neues Sicherungsmedium**.</span><span class="sxs-lookup"><span data-stu-id="09054-129">Click **New Backup Device**.</span></span> <span data-ttu-id="09054-130">Das Dialogfeld **Sicherungsmedium** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="09054-130">The **Backup Device** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="09054-131">Geben Sie einen Mediennamen ein.</span><span class="sxs-lookup"><span data-stu-id="09054-131">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="09054-132">Klicken Sie zur Angabe des Ziels auf **Datei** , und geben Sie den vollständigen Dateipfad an.</span><span class="sxs-lookup"><span data-stu-id="09054-132">For the destination, click **File** and specify the full path of the file.</span></span>  
  
6.  <span data-ttu-id="09054-133">Klicken Sie auf **OK**, um das neue Medium zu definieren.</span><span class="sxs-lookup"><span data-stu-id="09054-133">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="09054-134">Damit eine Sicherung auf dieses neue Medium erstellt werden kann, fügen Sie es dem Feld **Sichern auf:** im Dialogfeld **Datenbank sichern** (Seite **Allgemein**) hinzu.</span><span class="sxs-lookup"><span data-stu-id="09054-134">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="09054-135">Weitere Informationen finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="09054-135">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="09054-136">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09054-136">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a><span data-ttu-id="09054-137">So definieren Sie eine logische Sicherung für eine Datenträgerdatei</span><span class="sxs-lookup"><span data-stu-id="09054-137">To define a logical backup for a disk file</span></span>  
  
1.  <span data-ttu-id="09054-138">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="09054-138">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="09054-139">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="09054-139">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="09054-140">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="09054-140">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="09054-141">In diesem Beispiel wird gezeigt, wie Sie [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) verwenden müssen, um ein logisches Sicherungsmedium für eine Datenträgerdatei zu definieren.</span><span class="sxs-lookup"><span data-stu-id="09054-141">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a disk file.</span></span> <span data-ttu-id="09054-142">Im folgenden Beispiel wird das Datenträgersicherungsmedium `mydiskdump`mit dem physischen Namen `c:\dump\dump1.bak`hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="09054-142">The example adds the disk backup device named `mydiskdump`, with the physical name `c:\dump\dump1.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="09054-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09054-143">See Also</span></span>  
 <span data-ttu-id="09054-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09054-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="09054-145">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09054-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="09054-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09054-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="09054-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09054-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="09054-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09054-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="09054-149">[Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09054-149">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="09054-150">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="09054-150">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
