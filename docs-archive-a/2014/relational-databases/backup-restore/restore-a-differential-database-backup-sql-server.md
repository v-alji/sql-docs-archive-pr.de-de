---
title: Wiederherstellen einer differenziellen Datenbanksicherung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- restoring databases [SQL Server], full differential backups
- database backups [SQL Server], full differential backups
- database restores [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
ms.assetid: 0dd971a4-ee38-4dd3-9f30-ef77fc58dd11
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a8eab18d84efc1a990715e0d5488085252f93a7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620464"
---
# <a name="restore-a-differential-database-backup-sql-server"></a><span data-ttu-id="cb2f7-102">Wiederherstellen einer differenziellen Datenbanksicherung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cb2f7-102">Restore a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="cb2f7-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] eine differenzielle Datenbanksicherung mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-103">This topic describes how to restore a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="cb2f7-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cb2f7-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cb2f7-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cb2f7-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="cb2f7-108">Security</span><span class="sxs-lookup"><span data-stu-id="cb2f7-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cb2f7-109">**So stellen Sie eine differenzielle Datenbanksicherung wieder her, und zwar mit**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-109">**To restore a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="cb2f7-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb2f7-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cb2f7-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb2f7-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="cb2f7-112">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cb2f7-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cb2f7-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cb2f7-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cb2f7-115">RESTORE ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-115">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="cb2f7-116">Sicherungen, die mit aktuelleren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellt werden, können in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-116">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="cb2f7-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]können Sie eine Benutzerdatenbank von einer Datenbanksicherung wiederherstellen, die mit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder einer höheren Version erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cb2f7-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="cb2f7-119">Im vollständigen oder im massenprotokollierten Wiederherstellungsmodell muss das Protokoll der aktiven Transaktion (wird als Protokollfragment bezeichnet) gesichert werden, bevor eine Datenbank wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-119">Under the full or bulk-logged recovery model, before you can restore a database, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="cb2f7-120">Weitere Informationen finden Sie unter [Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)bezeichnet) gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-120">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cb2f7-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cb2f7-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cb2f7-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-122">Permissions</span></span>  
 <span data-ttu-id="cb2f7-123">Ist die wiederherzustellende Datenbank nicht vorhanden, muss der Benutzer über CREATE DATABASE-Berechtigungen verfügen, um RESTORE ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="cb2f7-124">Ist die Datenbank vorhanden, werden RESTORE-Berechtigungen standardmäßig den Mitgliedern der festen Serverrollen **sysadmin** und **dbcreator** sowie dem Besitzer (**dbo**) der Datenbank erteilt (für die Option FROM DATABASE_SNAPSHOT ist die Datenbank immer vorhanden).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="cb2f7-125">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="cb2f7-126">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cb2f7-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb2f7-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="cb2f7-128">So stellen Sie eine differenzielle Datenbanksicherung wieder her</span><span class="sxs-lookup"><span data-stu-id="cb2f7-128">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="cb2f7-129">Stellen Sie eine Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und klicken Sie danach im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-129">After you connect to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="cb2f7-130">Erweitern Sie **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-130">Expand **Databases**.</span></span> <span data-ttu-id="cb2f7-131">Wählen Sie je nach Datenbank entweder eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken**, und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-131">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="cb2f7-132">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**und **Wiederherstellung**, und klicken Sie anschließend auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-132">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="cb2f7-133">Legen Sie Quelle und Speicherort der wiederherzustellenden Sicherungssätze auf der Seite **Allgemein** mithilfe des Abschnitts **Quelle** fest.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-133">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="cb2f7-134">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="cb2f7-134">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="cb2f7-135">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-135">**Database**</span></span>  
  
         <span data-ttu-id="cb2f7-136">Wählen Sie die wiederherzustellende Datenbank aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-136">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="cb2f7-137">Die Liste enthält nur Datenbanken, die entsprechend dem Sicherungsverlauf von **msdb** gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-137">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb2f7-138">Wenn die Sicherung von einem anderen Server abgerufen wird, verfügt der Zielserver über keine Sicherungsverlaufsinformationen für die angegebene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-138">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="cb2f7-139">Wählen Sie in diesem Fall **Sicherungsmedium** aus, um die wiederherzustellende Datei oder das Medium manuell anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-139">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="cb2f7-140">**Device**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-140">**Device**</span></span>  
  
         <span data-ttu-id="cb2f7-141">Klicken Sie auf die Schaltfläche zum Durchsuchen ( **...** ), um das Dialogfeld **Sicherungsmedien auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-141">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="cb2f7-142">Wählen Sie im Feld **Sicherungsmedientyp** einen der aufgeführten Medientypen aus.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-142">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="cb2f7-143">Wenn Sie ein oder mehrere Medien für das Feld **Sicherungsmedien** auswählen möchten, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-143">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="cb2f7-144">Klicken Sie nach dem Hinzufügen der gewünschten Medien zum Listenfeld **Sicherungsmedien** auf **OK** , um zur Seite **Allgemein** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-144">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="cb2f7-145">Wählen Sie im Listenfeld **Quelle: Gerät: Datenbank** den Namen der Datenbank aus, die wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-145">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="cb2f7-146">**Hinweis** Diese Liste ist nur verfügbar, wenn **Sicherungsmedium** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-146">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="cb2f7-147">Nur Datenbanken mit Sicherungen auf dem ausgewählten Medium stehen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-147">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="cb2f7-148">Im Abschnitt **Ziel** wird das Feld **Datenbank** automatisch mit dem Namen der Datenbank aufgefüllt, die wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-148">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="cb2f7-149">Geben Sie zum Ändern des Datenbanknamens den neuen Namen ins Feld **Datenbank** ein.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-149">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cb2f7-150">Klicken Sie zum Anhalten der Wiederherstellung zu einem bestimmten Zeitpunkt auf **Zeitachse** , um auf das Dialogfeld **Sicherungszeitachse** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-150">To stop the restore at a specific point in time, click **Timeline** to access the **Backup Timeline** dialog box.</span></span> <span data-ttu-id="cb2f7-151">Hilfe zum Beenden einer Wiederherstellung der Datenbank zu einem bestimmten Zeitpunkt finden Sie unter [Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-151">For help with stopping a database restore at a specific point in time, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
6.  <span data-ttu-id="cb2f7-152">Wählen Sie im Raster **Wiederherzustellende Sicherungssätze** die Sicherungen durch die differenzielle Sicherung aus, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-152">In the **Backup sets to restore** grid, select the backups through the differential backup that you wish to restore.</span></span>  
  
     <span data-ttu-id="cb2f7-153">Weitere Informationen zu den Spalten des Rasters **Wiederherzustellende Sicherungssätze** finden Sie unter [Datenbank wiederherstellen &#40;Seite „Allgemein“&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)bezeichnet) gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
7.  <span data-ttu-id="cb2f7-154">Auf der Seite **Optionen** im Bereich **Wiederherstellungsoptionen** können Sie entsprechend Ihren Anforderungen die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="cb2f7-154">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="cb2f7-155">**Vorhandene Datenbank überschreiben (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-155">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="cb2f7-156">**Replikationseinstellungen beibehalten (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-156">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="cb2f7-157">**Bestätigung vor Wiederherstellen jeder einzelnen Sicherung**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-157">**Prompt before restoring each backup**</span></span>  
  
    -   <span data-ttu-id="cb2f7-158">**Zugriff auf die wiederhergestellte Datenbank einschränken (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="cb2f7-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="cb2f7-159">Weitere Informationen zu diesen Optionen finden Sie unter [Datenbank wiederherstellen &#40;Seite „Optionen“&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
8.  <span data-ttu-id="cb2f7-160">Aktivieren Sie eine Option für das Feld **Wiederherstellungsstatus** .</span><span class="sxs-lookup"><span data-stu-id="cb2f7-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="cb2f7-161">In diesem Feld wird der Status der Datenbank nach dem Wiederherstellungsvorgang bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="cb2f7-162">**RESTORE WITH RECOVERY** ist das Standardverhalten, das die Datenbank betriebsbereit belässt, indem für Transaktionen ohne Commit ein Rollback ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="cb2f7-163">Zusätzliche Transaktionsprotokolle können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="cb2f7-164">Wählen Sie diese Option nur aus, wenn Sie alle benötigten Sicherungen jetzt wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="cb2f7-165">**RESTORE WITH NORECOVERY** belässt die Datenbank nicht betriebsbereit und führt kein Rollback für Transaktionen ohne Commit aus.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="cb2f7-166">Zusätzliche Transaktionsprotokolle können wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="cb2f7-167">Die Datenbank kann erst verwendet werden, wenn sie wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="cb2f7-168">**RESTORE WITH STANDBY** belässt die Datenbank im schreibgeschützten Modus.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="cb2f7-169">Diese Option macht Transaktionen rückgängig, für die noch kein Commit ausgeführt wurde, speichert die Umkehraktionen aber in einer Standbydatei, damit die Auswirkungen der Wiederherstellung rückgängig gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="cb2f7-170">Beschreibungen der Optionen für den Bereich finden Sie unter [Datenbank wiederherstellen &#40;Seite Optionen&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
9. <span data-ttu-id="cb2f7-171">Wiederherstellungsvorgänge schlagen fehl, wenn aktive Verbindungen zur Datenbank bestehen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-171">Restore operations will fail if there are active connections to the database.</span></span> <span data-ttu-id="cb2f7-172">Aktivieren Sie die Option **Bestehende Verbindungen schließen** , um sicherzustellen, dass alle aktiven Verbindungen zwischen [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] und der Datenbank geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-172">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span>  
  
10. <span data-ttu-id="cb2f7-173">Wählen Sie **Bestätigung vor Wiederherstellen jeder einzelnen Sicherung** aus, wenn Sie zwischen jedem Wiederherstellungsvorgang zur Bestätigung aufgefordert werden möchten.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-173">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="cb2f7-174">Dies ist in der Regel nur bei großen Datenbanken und bei der gewünschten Überwachung des Status des Wiederherstellungsvorgangs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-174">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
11. <span data-ttu-id="cb2f7-175">Optional können Sie die Seite **Dateien** verwenden, um die Datenbank an einem neuen Speicherort wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-175">Optionally, use the **Files** page to restore the database to a new location.</span></span> <span data-ttu-id="cb2f7-176">Hilfe zum Verschieben einer Datenbank finden Sie unter [Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-176">For help with moving a database, see [Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cb2f7-177">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb2f7-177">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="cb2f7-178">So stellen Sie eine differenzielle Datenbanksicherung wieder her</span><span class="sxs-lookup"><span data-stu-id="cb2f7-178">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="cb2f7-179">Führen Sie die RESTORE DATABASE-Anweisung mit der NORECOVERY-Klausel aus, um die vollständige Datenbanksicherung wiederherzustellen, die der differenziellen Datenbanksicherung vorausging.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-179">Execute the RESTORE DATABASE statement, specifying the NORECOVERY clause, to restore the full database backup that comes before the differential database backup.</span></span> <span data-ttu-id="cb2f7-180">Weitere Informationen finden Sie unter [Vorgehensweise: Wiederherstellen einer vollständigen Sicherung](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-180">For more information, see [How to: Restore a Full Backup](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="cb2f7-181">Führen Sie die RESTORE DATABASE-Anweisung aus, um die differenzielle Datenbanksicherung wiederherzustellen, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="cb2f7-181">Execute the RESTORE DATABASE statement to restore the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="cb2f7-182">Den Namen der Datenbank, auf die die differenzielle Datenbanksicherung angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-182">The name of the database to which the differential database backup is applied.</span></span>  
  
    -   <span data-ttu-id="cb2f7-183">Das Sicherungsmedium, von dem die differenzielle Datenbanksicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-183">The backup device where the differential database backup is restored from.</span></span>  
  
    -   <span data-ttu-id="cb2f7-184">Die NORECOVERY-Klausel, wenn Transaktionsprotokollsicherungen vorliegen, die nach Wiederherstellung der differenziellen Datenbanksicherung angewendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-184">The NORECOVERY clause if you have transaction log backups to apply after the differential database backup is restored.</span></span> <span data-ttu-id="cb2f7-185">Andernfalls geben Sie die RECOVERY-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-185">Otherwise, specify the RECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="cb2f7-186">Beim vollständigen oder massenprotokollierten Wiederherstellungsmodell wird die Datenbank bei einer differenziellen Datenbankwiederherstellung in dem Status wiederhergestellt, in dem sie sich zum Zeitpunkt der Fertigstellung der differenziellen Datenbanksicherung befand.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-186">With the full or bulk-logged recovery model, restoring a differential database backup restores the database to the point at which the differential database backup was completed.</span></span> <span data-ttu-id="cb2f7-187">Um die Datenbank im Status zum Zeitpunkt des Fehlers wiederherzustellen, müssen Sie alle Transaktionsprotokollsicherungen anwenden, die nach der letzten differenziellen Datenbanksicherung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-187">To recover to the point of failure, you must apply all transaction log backups created after the last differential database backup was created.</span></span> <span data-ttu-id="cb2f7-188">Weitere Informationen finden Sie unter [Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cb2f7-188">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cb2f7-189">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cb2f7-189">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-restoring-a-differential-database-backup"></a><span data-ttu-id="cb2f7-190">A.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-190">A.</span></span> <span data-ttu-id="cb2f7-191">Wiederherstellen einer differenziellen Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="cb2f7-191">Restoring a differential database backup</span></span>  
 <span data-ttu-id="cb2f7-192">In diesem Beispiel werden eine Datenbanksicherung und eine differenzielle Datenbanksicherung der `MyAdvWorks` -Datenbank wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-192">This example restores a database and differential database backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost, and restore full database,   
-- specifying the original full database backup and NORECOVERY,   
-- which allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   RECOVERY;  
GO  
```  
  
#### <a name="b-restoring-a-database-differential-database-and-transaction-log-backup"></a><span data-ttu-id="cb2f7-193">B.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-193">B.</span></span> <span data-ttu-id="cb2f7-194">Wiederherstellen einer Datenbank-, einer differenziellen Datenbank- und einer Transaktionsprotokollsicherung</span><span class="sxs-lookup"><span data-stu-id="cb2f7-194">Restoring a database, differential database, and transaction log backup</span></span>  
 <span data-ttu-id="cb2f7-195">In diesem Beispiel werden eine Datenbanksicherung, eine differenzielle Datenbanksicherung und eine Transaktionsprotokollsicherung der `MyAdvWorks` -Datenbank wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="cb2f7-195">This example restores a database, differential database, and transaction log backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost at this point. Now restore the full   
-- database. Specify the original full database backup and NORECOVERY.  
-- NORECOVERY allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   NORECOVERY;  
GO  
-- Now restore each transaction log backup created after  
-- the differential database backup.  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log1  
   WITH NORECOVERY;  
GO  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log2  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cb2f7-196">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cb2f7-196">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cb2f7-197">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb2f7-197">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="cb2f7-198">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb2f7-198">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="cb2f7-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb2f7-199">See Also</span></span>  
 <span data-ttu-id="cb2f7-200">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb2f7-200">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="cb2f7-201">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb2f7-201">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
