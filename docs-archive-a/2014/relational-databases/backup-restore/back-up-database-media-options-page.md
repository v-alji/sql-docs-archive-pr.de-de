---
title: Datenbank sichern (Seite „Medienoptionen“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- swb.backupdatabase.mediaoptions.f1
- sql12.swb.backupdatabase.mediaoptions.f1
ms.assetid: eff36228-710c-4ed5-9af5-95859575dc0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cd09eb091a7f488f891bc2e69d19ad039b65e065
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720107"
---
# <a name="back-up-database-media-options-page"></a><span data-ttu-id="0e80a-102">Datenbank sichern (Seite 'Medienoptionen')</span><span class="sxs-lookup"><span data-stu-id="0e80a-102">Back Up Database (Media Options Page)</span></span>
  <span data-ttu-id="0e80a-103">Auf der Seite  **Medienoptionen** des Dialogfelds **Datenbank sichern** können Sie Medienoptionen zur Sicherung der Datenbank anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="0e80a-103">Use the  **Media Options** page of the **Back Up Database** dialog box to view or modify database media options.</span></span>  
  
 <span data-ttu-id="0e80a-104">**So erstellen Sie eine Sicherung mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0e80a-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="0e80a-105">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e80a-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="0e80a-106">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e80a-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0e80a-107">Sie können einen Datenbank-Wartungsplan definieren, um Datenbanksicherungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e80a-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="0e80a-108">Weitere Informationen finden Sie unter [Wartungspläne](../maintenance-plans/maintenance-plans.md) und [Verwenden des Wartungsplanungs-Assistenten](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0e80a-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e80a-109">Wenn Sie eine Sicherungsaufgabe mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]angeben, können Sie das entsprechende [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) -Skript generieren, indem Sie auf die Schaltfläche **Skript** klicken und anschließend ein Ziel für das Skript auswählen.</span><span class="sxs-lookup"><span data-stu-id="0e80a-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0e80a-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0e80a-110">Options</span></span>  
  
### <a name="overwrite-media"></a><span data-ttu-id="0e80a-111">Medium überschreiben</span><span class="sxs-lookup"><span data-stu-id="0e80a-111">Overwrite media</span></span>  
 <span data-ttu-id="0e80a-112">Mit den Optionen des Bereichs **Medium überschreiben** kann gesteuert werden, wie die Sicherung auf das Medium geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0e80a-112">The options of the **Overwrite media** panel control how the backup is written to the media.</span></span> <span data-ttu-id="0e80a-113">Wenn Sie im Dialogfeld „Datenbank sichern“ auf der Seite „Allgemein“ die Option „URL“ (Azure Storage) als Sicherungsziel auswählen, sind die Optionen im Abschnitt „Medium überschreiben“ deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0e80a-113">IF you selected URL (Azure Storage) as the backup destination on the General page of the Back Up Database dialog box, the options under the Overwrite media section are disabled.</span></span> <span data-ttu-id="0e80a-114">Sie können eine Sicherung mithilfe der Transact-SQL-Anweisung `BACKUP TO URL.. WITH FORMAT` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0e80a-114">You can overwrite a backup using the `BACKUP TO URL.. WITH FORMAT` Transact-SQL statement.</span></span> <span data-ttu-id="0e80a-115">Weitere Informationen finden Sie unter [SQL Server Backup to URL](sql-server-backup-to-url.md).</span><span class="sxs-lookup"><span data-stu-id="0e80a-115">For more information, see [SQL Server Backup to URL](sql-server-backup-to-url.md).</span></span>  
  
 <span data-ttu-id="0e80a-116">Nur die Option **Auf neuen Mediensatz sichern und alle vorhandenen Sicherungssätze löschen** wird mit Verschlüsselungsoptionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0e80a-116">Only the option, **Backup to a new media, and erase all existing backup sets** is supported with encryption options.</span></span> <span data-ttu-id="0e80a-117">Wenn Sie die Optionen im Abschnitt **Auf vorhandenen Mediensatz sichern** auswählen, werden die Verschlüsselungsoptionen auf der Seite **Sicherungsoptionen** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0e80a-117">If you select the options under the **Back up to existing media** section, the encryptions options on the **Backup Options** page will be disabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e80a-118">Informationen über Mediensätze finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e80a-118">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="0e80a-119">**Auf vorhandenen Mediensatz sichern**</span><span class="sxs-lookup"><span data-stu-id="0e80a-119">**Back up to the existing media set**</span></span>  
 <span data-ttu-id="0e80a-120">Sichert eine Datenbank auf einen vorhandenen Mediensatz.</span><span class="sxs-lookup"><span data-stu-id="0e80a-120">Back up a database to an existing media set.</span></span> <span data-ttu-id="0e80a-121">Durch Auswahl dieser Option werden drei weitere Optionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0e80a-121">Selecting this option button activates three options.</span></span>  
  
 <span data-ttu-id="0e80a-122">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="0e80a-122">Choose one of the following options:</span></span>  
  
 <span data-ttu-id="0e80a-123">**An vorhandenen Sicherungs Satz anfügen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-123">**Append to the existing backup set**</span></span>  
 <span data-ttu-id="0e80a-124">Fügt den Sicherungssatz unter Beibehaltung vorheriger Sicherungen an den vorhandenen Mediensatz an.</span><span class="sxs-lookup"><span data-stu-id="0e80a-124">Append the backup set to the existing media set, preserving any prior backups.</span></span>  
  
 <span data-ttu-id="0e80a-125">**Alle vorhandenen Sicherungssätze überschreiben**</span><span class="sxs-lookup"><span data-stu-id="0e80a-125">**Overwrite all existing backup sets**</span></span>  
 <span data-ttu-id="0e80a-126">Ersetzt alle vorherigen Sicherungen auf dem vorhandenen Mediensatz durch die aktuelle Sicherung.</span><span class="sxs-lookup"><span data-stu-id="0e80a-126">Replace any prior backups on the existing media set with the current backup.</span></span>  
  
 <span data-ttu-id="0e80a-127">**Mediensatznamen und Ablaufzeit des Sicherungssatzes überprüfen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-127">**Check media set name and backup set expiration**</span></span>  
 <span data-ttu-id="0e80a-128">Legen Sie optional beim Sichern auf einen vorhandenen Mediensatz fest, dass während des Sicherungsvorgangs der Name und das Ablaufdatum der Sicherungssätze überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0e80a-128">Optionally, if backing up to an existing media set, require the backup operation to verify the name and the expiration date of the backup sets.</span></span>  
  
 <span data-ttu-id="0e80a-129">**Mediensatzname**</span><span class="sxs-lookup"><span data-stu-id="0e80a-129">**Media set name**</span></span>  
 <span data-ttu-id="0e80a-130">Wenn **Mediensatznamen und Ablaufzeit des Sicherungssatzes überprüfen** ausgewählt ist, geben Sie optional den Namen des Mediensatzes an, der für diesen Sicherungsvorgang verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e80a-130">If **Check media set name and backup set expiration** is selected, optionally, specify the name of the media set to be used for this backup operation.</span></span>  
  
 <span data-ttu-id="0e80a-131">**Auf neuen Mediensatz sichern und alle vorhandenen Sicherungssätze löschen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-131">**Back up to a new media set, and erase all existing backup sets**</span></span>  
 <span data-ttu-id="0e80a-132">Mit dieser Option erstellen Sie einen neuen Mediensatz, wobei die vorherigen Sicherungssätze gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0e80a-132">Use a new media set, erasing the previous backup sets.</span></span>  
  
 <span data-ttu-id="0e80a-133">Durch Auswählen dieser Option werden die folgenden Optionen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="0e80a-133">Clicking this option activates the following options:</span></span>  
  
 <span data-ttu-id="0e80a-134">**Name für neuen Mediensatz**</span><span class="sxs-lookup"><span data-stu-id="0e80a-134">**New media set name**</span></span>  
 <span data-ttu-id="0e80a-135">Geben Sie optional einen neuen Namen für den Mediensatz ein.</span><span class="sxs-lookup"><span data-stu-id="0e80a-135">Optionally, enter a new name for the media set.</span></span>  
  
 <span data-ttu-id="0e80a-136">**Beschreibung für neuen Mediensatz**</span><span class="sxs-lookup"><span data-stu-id="0e80a-136">**New media set description**</span></span>  
 <span data-ttu-id="0e80a-137">Geben Sie optional eine aussagekräftige Beschreibung für den neuen Mediensatz ein.</span><span class="sxs-lookup"><span data-stu-id="0e80a-137">Optionally, enter a meaningful description of the new media set.</span></span> <span data-ttu-id="0e80a-138">Die Beschreibung sollte genau genug sein, um den Inhalt akkurat zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="0e80a-138">This description should be specific enough to communicate the contents accurately.</span></span>  
  
### <a name="reliability"></a><span data-ttu-id="0e80a-139">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="0e80a-139">Reliability</span></span>  
 <span data-ttu-id="0e80a-140">Mit den Optionen des Bereichs **Transaktionsprotokoll** wird die Fehlerverwaltung durch den Sicherungsvorgang gesteuert.</span><span class="sxs-lookup"><span data-stu-id="0e80a-140">The options of the **Transaction log** panel control error management by the backup operation.</span></span>  
  
 <span data-ttu-id="0e80a-141">**Sicherung nach dem Abschluss überprüfen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-141">**Verify backup when finished**</span></span>  
 <span data-ttu-id="0e80a-142">Überprüft, ob der Sicherungssatz vollständig ist und alle Volumes lesbar sind.</span><span class="sxs-lookup"><span data-stu-id="0e80a-142">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="0e80a-143">**Vor dem Schreiben auf die Medien Prüfsumme ausführen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-143">**Perform checksum before writing to media**</span></span>  
 <span data-ttu-id="0e80a-144">Überprüft vor dem Schreiben auf die Sicherungsmedien die Prüfsummen.</span><span class="sxs-lookup"><span data-stu-id="0e80a-144">Verify the checksums before writing to the backup media.</span></span> <span data-ttu-id="0e80a-145">Das Auswählen dieser Option entspricht der Angabe der Option CHECKSUM in der BACKUP-Anweisung von [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e80a-145">Selecting this option is equivalent to specifying the CHECKSUM option in the BACKUP statement of [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0e80a-146">Durch Auswahl dieser Option kann die Arbeitsauslastung erhöht und der Sicherungsdurchsatz des Sicherungsvorgangs verringert werden.</span><span class="sxs-lookup"><span data-stu-id="0e80a-146">Selecting this option may increase the workload, and decrease the backup throughput of the backup operation.</span></span> <span data-ttu-id="0e80a-147">Weitere Informationen zu Sicherungsprüfsummen finden Sie unter [Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e80a-147">For information about backup checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
 <span data-ttu-id="0e80a-148">**Bei Fehler fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-148">**Continue on error**</span></span>  
 <span data-ttu-id="0e80a-149">Der Sicherungsvorgang wird auch nach Auftreten eines oder mehrerer Fehler fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0e80a-149">The backup operation is to continue even after encountering one or more errors.</span></span>  
  
### <a name="transaction-log"></a><span data-ttu-id="0e80a-150">Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="0e80a-150">Transaction log</span></span>  
 <span data-ttu-id="0e80a-151">Mit den Optionen des Bereichs **Transaktionsprotokoll** wird das Verhalten einer Transaktionsprotokollsicherung gesteuert.</span><span class="sxs-lookup"><span data-stu-id="0e80a-151">The options of the **Transaction log** panel control the behavior of a transaction log backup.</span></span> <span data-ttu-id="0e80a-152">Diese Optionen sind nur beim vollständigen Wiederherstellungsmodell oder beim massenprotokollierten Wiederherstellungsmodell relevant.</span><span class="sxs-lookup"><span data-stu-id="0e80a-152">These options are relevant only under the full recovery model or bulk-logged recovery model.</span></span> <span data-ttu-id="0e80a-153">Sie sind nur aktiviert, wenn im Dialogfeld **Datenbank sichern** auf der Seite **Allgemein** im Feld [Sicherungstyp](../../integration-services/general-page-of-integration-services-designers-options.md) die Option **Transaktionsprotokoll** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0e80a-153">They are activated only if **Transaction log** has been selected in the **Backup type** field on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e80a-154">Informationen zu Transaktionsprotokollsicherungen finden Sie unter [Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e80a-154">For information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="0e80a-155">**Transaktionsprotokoll abschneiden**</span><span class="sxs-lookup"><span data-stu-id="0e80a-155">**Truncate the transaction log**</span></span>  
 <span data-ttu-id="0e80a-156">Das Transaktionsprotokoll wird gesichert und abgeschnitten, um Protokollspeicherplatz freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0e80a-156">Back up the transaction log and truncate it to free log space.</span></span> <span data-ttu-id="0e80a-157">Die Datenbank bleibt dabei online.</span><span class="sxs-lookup"><span data-stu-id="0e80a-157">The database remains online.</span></span> <span data-ttu-id="0e80a-158">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="0e80a-158">This is the default option.</span></span>  
  
 <span data-ttu-id="0e80a-159">**Protokollfragment sichern und Datenbank im Wiederherstellungsstatus belassen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-159">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="0e80a-160">Das Protokollfragment wird gesichert und die Datenbank im Wiederherstellungsstatus belassen.</span><span class="sxs-lookup"><span data-stu-id="0e80a-160">Back up the tail of the log and leave the database in a restoring state.</span></span> <span data-ttu-id="0e80a-161">Diese Option erstellt eine *Sicherung des Protokollfragments*. Dabei werden Protokolle gesichert, die bisher (vom aktiven Protokoll) noch nicht gesichert wurden, i.d.R. als Vorbereitung für die Wiederherstellung einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0e80a-161">This option creates a *tail-log backup*, which backs up logs that have not yet been backed up (the active log), typically, in preparation for restoring a database.</span></span> <span data-ttu-id="0e80a-162">Die Datenbank steht Benutzern erst wieder zur Verfügung, wenn sie vollständig wiederhergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="0e80a-162">The database will be unavailable to users until it is completely restored.</span></span>  
  
 <span data-ttu-id="0e80a-163">Das Auswählen dieser Option entspricht der Angabe von WITH NO_TRUNCATE und NORECOVERY in einer [BACKUP](/sql/t-sql/statements/backup-transact-sql)-Anweisung ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0e80a-163">Selecting this option is equivalent to specifying WITH NO_TRUNCATE, NORECOVERY in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span></span> <span data-ttu-id="0e80a-164">Weitere Informationen finden Sie unter [Protokollfragmentsicherungen &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e80a-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
### <a name="tape-drive"></a><span data-ttu-id="0e80a-165">Bandlaufwerk</span><span class="sxs-lookup"><span data-stu-id="0e80a-165">Tape drive</span></span>  
 <span data-ttu-id="0e80a-166">Mit den Optionen des Bereichs **Bandlaufwerk** wird die Bandverwaltung während des Sicherungsvorgangs gesteuert.</span><span class="sxs-lookup"><span data-stu-id="0e80a-166">The options of the **Tape drive** panel control tape management during the backup operation.</span></span> <span data-ttu-id="0e80a-167">Diese Optionen sind nur aktiviert, wenn im Dialogfeld **Datenbank sichern** auf der Seite **Allgemein** im Feld [Ziel](../../integration-services/general-page-of-integration-services-designers-options.md) die Option **Band** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0e80a-167">These options are activated only if **Tape** has been selected in the **Destination** panel on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e80a-168">Weitere Informationen zum Verwenden von Bandmedien finden Sie unter [Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e80a-168">For information about how to use tape devices, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
 <span data-ttu-id="0e80a-169">**Band nach dem Sichern entladen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-169">**Unload the tape after backup**</span></span>  
 <span data-ttu-id="0e80a-170">Nach Abschluss der Sicherung wird das Band entladen.</span><span class="sxs-lookup"><span data-stu-id="0e80a-170">After the backup is complete, unload the tape.</span></span>  
  
 <span data-ttu-id="0e80a-171">**Band vor dem Entladen zurückspulen**</span><span class="sxs-lookup"><span data-stu-id="0e80a-171">**Rewind the tape before unloading**</span></span>  
 <span data-ttu-id="0e80a-172">Das Band wird vor dem Entladen freigegeben und zurückgespult.</span><span class="sxs-lookup"><span data-stu-id="0e80a-172">Before unloading the tape, release and rewind it.</span></span> <span data-ttu-id="0e80a-173">Diese Option ist nur aktiviert, wenn **Band nach dem Sichern entladen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0e80a-173">This is enabled only if **Unload the tape after backup** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e80a-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e80a-174">See Also</span></span>  
 <span data-ttu-id="0e80a-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e80a-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="0e80a-176">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e80a-176">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="0e80a-177">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e80a-177">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="0e80a-178">Sichern des Transaktionsprotokolls bei beschädigter Datenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e80a-178">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
