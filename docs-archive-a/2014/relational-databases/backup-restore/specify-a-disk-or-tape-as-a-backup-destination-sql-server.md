---
title: Angeben eines Datenträgers oder Bands als Sicherungsziel (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
- backups [SQL Server], creating
- tape backup devices, backing up
ms.assetid: e391f452-ed8c-4b40-b846-ac3881271b94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a0f8ec5d9741e42f3b7d8eda8ebdba23622982d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699788"
---
# <a name="specify-a-disk-or-tape-as-a-backup-destination-sql-server"></a><span data-ttu-id="b0a51-102">Angeben eines Datenträgers oder ein Bands als Sicherungsziel (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b0a51-102">Specify a Disk or Tape As a Backup Destination (SQL Server)</span></span>
  <span data-ttu-id="b0a51-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]einen Datenträger oder ein Band als Sicherungsziel angeben.</span><span class="sxs-lookup"><span data-stu-id="b0a51-103">This topic describes how to specify a disk or tape as a backup destination in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0a51-104">Die Unterstützung für Bandsicherungsmedien wird in zukünftigen Versionen von SQL Server entfernt.</span><span class="sxs-lookup"><span data-stu-id="b0a51-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="b0a51-105">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0a51-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="b0a51-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b0a51-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b0a51-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b0a51-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b0a51-108">Security</span><span class="sxs-lookup"><span data-stu-id="b0a51-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b0a51-109">**So geben Sie einen Datenträger oder ein Band als Sicherungsziel an mit**</span><span class="sxs-lookup"><span data-stu-id="b0a51-109">**To specify a disk or tape as a backup destination, using:**</span></span>  
  
     [<span data-ttu-id="b0a51-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0a51-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b0a51-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0a51-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b0a51-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b0a51-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b0a51-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b0a51-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b0a51-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b0a51-114">Permissions</span></span>  
 <span data-ttu-id="b0a51-115">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b0a51-115">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="b0a51-116">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="b0a51-116">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b0a51-117">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="b0a51-117">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="b0a51-118">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b0a51-118">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="b0a51-119">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b0a51-119">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b0a51-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0a51-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="b0a51-121">So geben Sie einen Datenträger oder ein Band als Sicherungsziel an</span><span class="sxs-lookup"><span data-stu-id="b0a51-121">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="b0a51-122">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b0a51-122">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b0a51-123">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="b0a51-123">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b0a51-124">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="b0a51-124">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="b0a51-125">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0a51-125">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b0a51-126">Klicken Sie auf der Seite **Allgemein** im Abschnitt **Ziel** auf **Datenträger** oder auf **Band**.</span><span class="sxs-lookup"><span data-stu-id="b0a51-126">In the **Destination** section of the **General** page, click **Disk** or **Tape**.</span></span> <span data-ttu-id="b0a51-127">Klicken Sie auf **Hinzufügen**, um die Pfade von bis zu 64 Datenträgern oder Bandlaufwerken, die einen einzelnen Mediensatz enthalten, auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b0a51-127">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span>  
  
     <span data-ttu-id="b0a51-128">Um einen Sicherungsziel zu entfernen, wählen Sie ihn aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="b0a51-128">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="b0a51-129">Zum Anzeigen des Inhalts eines Sicherungsziels wählen Sie es aus, und klicken Sie auf **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="b0a51-129">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b0a51-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0a51-130">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="b0a51-131">So geben Sie einen Datenträger oder ein Band als Sicherungsziel an</span><span class="sxs-lookup"><span data-stu-id="b0a51-131">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="b0a51-132">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b0a51-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b0a51-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b0a51-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b0a51-134">Geben Sie in der [BACKUP](/sql/t-sql/statements/backup-transact-sql)-Anweisung die Datei oder das Gerät und seinen physischen Namen an.</span><span class="sxs-lookup"><span data-stu-id="b0a51-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the file or device and its physical name.</span></span> <span data-ttu-id="b0a51-135">In diesem Beispiel wird die `AdventureWorks2012` -Datenbank in die `Z:\SQLServerBackups\AdventureWorks2012.Bak`-Datenträgerdatei gesichert.</span><span class="sxs-lookup"><span data-stu-id="b0a51-135">This example backs up the `AdventureWorks2012` database to the disk file `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0a51-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0a51-136">See Also</span></span>  
 <span data-ttu-id="b0a51-137">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b0a51-137">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="b0a51-138">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b0a51-138">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="b0a51-139">[Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b0a51-139">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 <span data-ttu-id="b0a51-140">[Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b0a51-140">[Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="b0a51-141">Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b0a51-141">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
