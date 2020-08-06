---
title: Löschen eines Sicherungsmediums (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], deleting devices
- backup devices [SQL Server], deleting
- deleting backup devices
- removing backup devices
- backing up databases [SQL Server], backup devices
ms.assetid: 7be62480-ed6a-4262-a071-1feba73b1c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8734e587a8ecde315fb17120511455a59e38901
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617137"
---
# <a name="delete-a-backup-device-sql-server"></a><span data-ttu-id="2e94a-102">Löschen eines Sicherungsmediums (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2e94a-102">Delete a Backup Device (SQL Server)</span></span>
  <span data-ttu-id="2e94a-103">In diesem Thema wird beschrieben, wie Sie ein Sicherungsmedium in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen können.</span><span class="sxs-lookup"><span data-stu-id="2e94a-103">This topic describes how to delete a backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2e94a-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="2e94a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2e94a-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="2e94a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2e94a-106">Security</span><span class="sxs-lookup"><span data-stu-id="2e94a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2e94a-107">**So löschen Sie ein Sicherungsmedium mit**</span><span class="sxs-lookup"><span data-stu-id="2e94a-107">**To delete a backup device, using:**</span></span>  
  
     [<span data-ttu-id="2e94a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e94a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2e94a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e94a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2e94a-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2e94a-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2e94a-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2e94a-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2e94a-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2e94a-112">Permissions</span></span>  
 <span data-ttu-id="2e94a-113">Erfordert die Mitgliedschaft in der festen Serverrolle **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="2e94a-113">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2e94a-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e94a-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="2e94a-115">So löschen Sie ein Sicherungsmedium</span><span class="sxs-lookup"><span data-stu-id="2e94a-115">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="2e94a-116">Stellen Sie eine Verbindung mit der entsprechenden Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und klicken Sie danach im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2e94a-116">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2e94a-117">Erweitern Sie **Serverobjekte**und anschließend **Sicherungsmedien**.</span><span class="sxs-lookup"><span data-stu-id="2e94a-117">Expand **Server Objects**, and then expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="2e94a-118">Klicken Sie mit der rechten Maustaste auf das gewünschte Medium, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="2e94a-118">Right-click the device you want, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="2e94a-119">Überprüfen Sie im Dialogfeld **Objekt löschen** , ob in der Spalte **Objektname** der richtige Medienname angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2e94a-119">In the **Delete Object** dialog box, verify that the correct device name appears in the **Object Name** column.</span></span>  
  
5.  <span data-ttu-id="2e94a-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e94a-120">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2e94a-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e94a-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="2e94a-122">So löschen Sie ein Sicherungsmedium</span><span class="sxs-lookup"><span data-stu-id="2e94a-122">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="2e94a-123">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="2e94a-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e94a-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="2e94a-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e94a-125">Kopieren Sie das folgende Beispiel, und fügen Sie es in das Abfragefenster ein.</span><span class="sxs-lookup"><span data-stu-id="2e94a-125">Copy and paste the following example into the query.</span></span> <span data-ttu-id="2e94a-126">In diesem Beispiel wird gezeigt, wie [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) verwendet werden muss, um ein Sicherungsmedium zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2e94a-126">This example shows how to use [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) to delete a backup device.</span></span> <span data-ttu-id="2e94a-127">Führen Sie das erste Beispiel aus, um das `mybackupdisk` -Sicherungsmedium und den physischen Namen `c:\backup\backup1.bak`zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e94a-127">Execute the first example to create the `mybackupdisk` backup device and the physical name `c:\backup\backup1.bak`.</span></span> <span data-ttu-id="2e94a-128">Führen Sie `sp_dropdevice` aus, um das Sicherungsmedium `mybackupdisk` zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2e94a-128">Execute `sp_dropdevice` to delete the `mybackupdisk` backup device.</span></span> <span data-ttu-id="2e94a-129">Der physische Namen wird vom `delfile` -Parameter gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2e94a-129">The `delfile` parameter deletes the physical name.</span></span>  
  
```sql  
--Define a backup device and physical name.   
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mybackupdisk', 'c:\backup\backup1.bak' ;  
GO  
--Delete the backup device and the physical name.  
USE AdventureWorks2012 ;  
GO  
EXEC sp_dropdevice ' mybackupdisk ', 'delfile' ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e94a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e94a-130">See Also</span></span>  
 <span data-ttu-id="2e94a-131">[Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2e94a-131">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="2e94a-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2e94a-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="2e94a-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2e94a-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="2e94a-134">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2e94a-134">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="2e94a-135">sp_addumpdevice &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2e94a-135">sp_addumpdevice &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)  
  
  
