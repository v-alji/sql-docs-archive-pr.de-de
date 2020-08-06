---
title: Anzeigen der Inhalte eines Sicherungsbands oder einer Sicherungsdatei (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- displaying backup content
- viewing backup content
- tape backup devices, viewing contents
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
ms.assetid: cd6674a2-ca55-4b5a-a971-878ba001821e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 044519b64d41fbbdfc9302ce24369ab282727f67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718304"
---
# <a name="view-the-contents-of-a-backup-tape-or-file-sql-server"></a><span data-ttu-id="ad0b4-102">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ad0b4-102">View the Contents of a Backup Tape or File (SQL Server)</span></span>
  <span data-ttu-id="ad0b4-103">In diesem Thema wird beschrieben, wie Sie den Inhalt eines Sicherungsbands oder einer -datei in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-103">This topic describes how to view the content of a backup tape or file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad0b4-104">Die Unterstützung für Bandsicherungsmedien wird in zukünftigen Versionen von SQL Server entfernt.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="ad0b4-105">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="ad0b4-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ad0b4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad0b4-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ad0b4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad0b4-108">Security</span><span class="sxs-lookup"><span data-stu-id="ad0b4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad0b4-109">**So zeigen Sie den Inhalt eines Sicherungsbands oder einer -datei an mit**</span><span class="sxs-lookup"><span data-stu-id="ad0b4-109">**To view the content of a backup tape or file, using:**</span></span>  
  
     [<span data-ttu-id="ad0b4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad0b4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ad0b4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad0b4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad0b4-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ad0b4-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad0b4-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad0b4-113">Security</span></span>  
 <span data-ttu-id="ad0b4-114">Weitere Informationen zur Sicherheit finden Sie unter [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-114">For information about security, see [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad0b4-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ad0b4-115">Permissions</span></span>  
 <span data-ttu-id="ad0b4-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und höheren Versionen benötigen Sie die CREATE DATABASE-Berechtigung, um Informationen zu Sicherungssätzen oder Sicherungsmedien abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="ad0b4-117">Weitere Informationen finden Sie unter [GRANT (Datenbankberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-117">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad0b4-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad0b4-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="ad0b4-119">So zeigen Sie den Inhalt eines Sicherungsbands oder einer Sicherungsdatei an</span><span class="sxs-lookup"><span data-stu-id="ad0b4-119">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="ad0b4-120">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ad0b4-121">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="ad0b4-122">Klicken Sie mit der rechten Maustaste auf die Datenbank, die Sie sichern möchten, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-122">Right-click the database you want to backup, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="ad0b4-123">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="ad0b4-124">Klicken Sie auf der Seite **Allgemein** im Abschnitt **Ziel** auf **Datenträger** oder auf **Band**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-124">In the **Destination** section of the **General** page, click either **Disk** or **Tape**.</span></span> <span data-ttu-id="ad0b4-125">Suchen Sie im Listenfeld **Sichern auf** nach der gewünschten Datenträgerdatei oder dem gewünschten Band.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-125">In the **Back up to** list box, look for the disk file or tape you want.</span></span>  
  
     <span data-ttu-id="ad0b4-126">Falls die Datenträgerdatei oder das Band nicht im Listenfeld angezeigt wird, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-126">If the disk file or tape is not displayed in the list-box, click **Add**.</span></span> <span data-ttu-id="ad0b4-127">Wählen Sie einen Dateinamen oder ein Bandlaufwerk aus.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-127">Select a file name or tape drive.</span></span> <span data-ttu-id="ad0b4-128">Klicken Sie auf **OK** , um ihn bzw. es dem Listenfeld **Sichern auf**hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-128">To add it to the **Back up to** list-box, click **OK**.</span></span>  
  
5.  <span data-ttu-id="ad0b4-129">Wählen Sie im Listenfeld **Sichern auf** den Pfad des Datenträgers oder Bandlaufwerkes aus, den/das Sie anzeigen möchten, und klicken Sie auf **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-129">In the **Back up to** list-box, select the path of the disk or tape drive you want to view, and click **Contents**.</span></span> <span data-ttu-id="ad0b4-130">Das Dialogfeld **Medieninhalt** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-130">This opens the **Device Contents** dialog box.</span></span>  
  
6.  <span data-ttu-id="ad0b4-131">Im rechten Fensterbereich werden Informationen zum Mediensatz und zu den Sicherungssätzen auf dem ausgewählten Band oder in der ausgewählten Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-131">The right-hand pane displays information about the media set and backup sets on the selected tape or file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad0b4-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad0b4-132">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="ad0b4-133">So zeigen Sie den Inhalt eines Sicherungsbands oder einer Sicherungsdatei an</span><span class="sxs-lookup"><span data-stu-id="ad0b4-133">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="ad0b4-134">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad0b4-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ad0b4-136">Verwenden Sie die [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-136">Use the [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) statement.</span></span> <span data-ttu-id="ad0b4-137">In diesem Beispiel werden Informationen über die Datei `AdventureWorks2012-FullBackup.bak`zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ad0b4-137">This example returns information about the file named `AdventureWorks2012-FullBackup.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
RESTORE HEADERONLY   
FROM DISK = N'C:\AdventureWorks2012-FullBackup.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad0b4-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad0b4-138">See Also</span></span>  
 <span data-ttu-id="ad0b4-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="ad0b4-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="ad0b4-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="ad0b4-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="ad0b4-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="ad0b4-144">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-144">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="ad0b4-145">[Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad0b4-145">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="ad0b4-146">Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0b4-146">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
