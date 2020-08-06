---
title: Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- tape backup devices, creating
ms.assetid: 66f36e1d-0287-4fac-8a51-71f9f0d7ad5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8728df2cc0b5907e51da84ed9e77d897a1718d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726014"
---
# <a name="define-a-logical-backup-device-for-a-tape-drive-sql-server"></a><span data-ttu-id="52dec-102">Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="52dec-102">Define a Logical Backup Device for a Tape Drive (SQL Server)</span></span>
  <span data-ttu-id="52dec-103">In diesem Thema wird beschrieben, wie Sie ein logisches Sicherungsmedium für ein Bandlaufwerk in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]definieren.</span><span class="sxs-lookup"><span data-stu-id="52dec-103">This topic describes how to define a logical backup device for a tape drive in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="52dec-104">Ein logisches Medium ist ein benutzerdefinierter Name, der auf ein bestimmtes, physisches Sicherungsmedium (Datenträgerdatei oder Bandlaufwerk) verweist.</span><span class="sxs-lookup"><span data-stu-id="52dec-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="52dec-105">Die Initialisierung des physischen Mediums erfolgt später, wenn eine Sicherung auf das Sicherungsmedium geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="52dec-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52dec-106">Die Unterstützung für Bandsicherungsgeräte wird in zukünftigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]entfernt.</span><span class="sxs-lookup"><span data-stu-id="52dec-106">Support for tape backup devices will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="52dec-107">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="52dec-107">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="52dec-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="52dec-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="52dec-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="52dec-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="52dec-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="52dec-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="52dec-111">Security</span><span class="sxs-lookup"><span data-stu-id="52dec-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="52dec-112">**So definieren Sie ein logisches Sicherungsmedium für ein Bandlaufwerk mit**</span><span class="sxs-lookup"><span data-stu-id="52dec-112">**To define a logical backup device for a tape drive, using:**</span></span>  
  
     [<span data-ttu-id="52dec-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="52dec-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="52dec-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52dec-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="52dec-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="52dec-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="52dec-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="52dec-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="52dec-117">Das Bandlaufwerk bzw. die -laufwerke müssen vom Betriebssystem Microsoft Windows unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="52dec-117">The tape drive or drives must be supported by the Microsoft Windows operating system.</span></span>  
  
-   <span data-ttu-id="52dec-118">Das Bandmedium muss physisch mit dem Computer verbunden sein, auf dem eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52dec-118">The tape device must be connected physically to the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="52dec-119">Das Sichern auf Remotebandmedien wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52dec-119">Backing up to remote tape devices is not supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="52dec-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="52dec-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="52dec-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="52dec-121">Permissions</span></span>  
 <span data-ttu-id="52dec-122">Erfordert die Mitgliedschaft in der festen Serverrolle **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="52dec-122">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="52dec-123">Erfordert die Berechtigung zum Schreiben auf den Datenträger.</span><span class="sxs-lookup"><span data-stu-id="52dec-123">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="52dec-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="52dec-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="52dec-125">So definieren Sie ein logisches Sicherungsmedium für ein Bandlaufwerk</span><span class="sxs-lookup"><span data-stu-id="52dec-125">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="52dec-126">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="52dec-126">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="52dec-127">Erweitern Sie **Serverobjekte**, und klicken Sie dann mit der rechten Maustaste auf **Sicherungsmedien**.</span><span class="sxs-lookup"><span data-stu-id="52dec-127">Expand **Server Objects**, and then right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="52dec-128">Klicken Sie auf **Neues Sicherungsmedium**, um das Dialogfeld **Sicherungsmedium** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52dec-128">Click **New Backup Device**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="52dec-129">Geben Sie einen Mediennamen ein.</span><span class="sxs-lookup"><span data-stu-id="52dec-129">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="52dec-130">Klicken Sie für das Ziel auf **Band** , und wählen Sie ein Bandlaufwerk aus, das noch keinem anderen Sicherungsmedium zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="52dec-130">For the destination, click **Tape** and select a tape drive that is not already associated with another backup device.</span></span> <span data-ttu-id="52dec-131">Falls keine Bandlaufwerke verfügbar sind, ist die Option **Band** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="52dec-131">If no such tape drives are available, the **Tape** option is inactive.</span></span>  
  
6.  <span data-ttu-id="52dec-132">Klicken Sie auf **OK**, um das neue Medium zu definieren.</span><span class="sxs-lookup"><span data-stu-id="52dec-132">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="52dec-133">Damit eine Sicherung auf dieses neue Medium erstellt werden kann, fügen Sie es dem Feld **Sichern auf:** im Dialogfeld **Datenbank sichern** (Seite **Allgemein**) hinzu.</span><span class="sxs-lookup"><span data-stu-id="52dec-133">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="52dec-134">Weitere Informationen finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52dec-134">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="52dec-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52dec-135">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="52dec-136">So definieren Sie ein logisches Sicherungsmedium für ein Bandlaufwerk</span><span class="sxs-lookup"><span data-stu-id="52dec-136">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="52dec-137">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="52dec-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="52dec-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="52dec-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="52dec-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="52dec-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="52dec-140">In diesem Beispiel wird gezeigt, wie Sie [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) verwenden müssen, um ein logisches Sicherungsmedium für ein Band zu definieren.</span><span class="sxs-lookup"><span data-stu-id="52dec-140">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a tape.</span></span> <span data-ttu-id="52dec-141">Im folgenden Beispiel wird das Bandsicherungsmedium `tapedump1`mit dem physischen Namen `\\.\tape0`hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52dec-141">The example adds the tape backup device named `tapedump1`, with the physical name `\\.\tape0`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'tape', 'tapedump1', '\\.\tape0' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="52dec-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52dec-142">See Also</span></span>  
 <span data-ttu-id="52dec-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52dec-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="52dec-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52dec-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="52dec-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52dec-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="52dec-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52dec-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="52dec-147">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52dec-147">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="52dec-148">[Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52dec-148">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="52dec-149">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="52dec-149">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
