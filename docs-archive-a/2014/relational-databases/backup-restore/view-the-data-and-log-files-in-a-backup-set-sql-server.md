---
title: Anzeigen der Daten und Protokolldateien in einem Sicherungssatz (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7dbcb14a658b49aba6f5f2ebe3425a2ab5759efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718301"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a><span data-ttu-id="c6a70-102">Anzeigen der Daten und Protokolldateien in einem Sicherungssatz (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c6a70-102">View the Data and Log Files in a Backup Set (SQL Server)</span></span>
  <span data-ttu-id="c6a70-103">In diesem Thema wird beschrieben, wie Sie Daten und Protokolldateien in einem Sicherungssatz in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c6a70-103">This topic describes how to view the data and log files in a backup set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c6a70-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c6a70-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6a70-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c6a70-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6a70-106">Security</span><span class="sxs-lookup"><span data-stu-id="c6a70-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6a70-107">**So zeigen Sie die Daten und Protokolldateien in einem Sicherungssatz an mit**</span><span class="sxs-lookup"><span data-stu-id="c6a70-107">**To view the data and log files in a backup set, using:**</span></span>  
  
     [<span data-ttu-id="c6a70-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6a70-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6a70-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6a70-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6a70-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c6a70-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6a70-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c6a70-111">Security</span></span>  
 <span data-ttu-id="c6a70-112">Weitere Informationen zur Sicherheit finden Sie unter [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6a70-112">For information about security, see [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6a70-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c6a70-113">Permissions</span></span>  
 <span data-ttu-id="c6a70-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und höheren Versionen benötigen Sie die CREATE DATABASE-Berechtigung, um Informationen zu Sicherungssätzen oder Sicherungsmedien abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c6a70-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="c6a70-115">Weitere Informationen finden Sie unter [GRANT (Datenbankberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6a70-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6a70-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6a70-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="c6a70-117">So zeigen Sie die Daten und Protokolldateien in einem Sicherungssatz an</span><span class="sxs-lookup"><span data-stu-id="c6a70-117">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="c6a70-118">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c6a70-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c6a70-119">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="c6a70-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="c6a70-120">Klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie dann auf **Eigenschaften**. Das Dialogfeld **Datenbankeigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c6a70-120">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="c6a70-121">Klicken Sie im Fensterbereich **Seite auswählen** auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="c6a70-121">In the **Select a Page** pane, click **Files**.</span></span>  
  
5.  <span data-ttu-id="c6a70-122">Suchen Sie im Bereich **Datenbankdateien** nach einer Liste der Daten- und Protokolldateien und deren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c6a70-122">Look in the **Database files** grid for a list of the data and log files and their properties.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6a70-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6a70-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="c6a70-124">So zeigen Sie die Daten und Protokolldateien in einem Sicherungssatz an</span><span class="sxs-lookup"><span data-stu-id="c6a70-124">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="c6a70-125">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="c6a70-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6a70-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6a70-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6a70-127">Verwenden Sie die [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c6a70-127">Use the [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) statement.</span></span> <span data-ttu-id="c6a70-128">In diesem Beispiel werden Informationen zum sekundären Sicherungsmedium (`FILE=2`) auf dem `AdventureWorksBackups` -Sicherungsmedium zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="c6a70-128">This example returns information about the second backup set (`FILE=2`) on the `AdventureWorksBackups` backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6a70-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6a70-129">See Also</span></span>  
 <span data-ttu-id="c6a70-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6a70-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="c6a70-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6a70-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="c6a70-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6a70-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="c6a70-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6a70-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="c6a70-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6a70-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 [<span data-ttu-id="c6a70-135">Sicherungsmedien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c6a70-135">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
