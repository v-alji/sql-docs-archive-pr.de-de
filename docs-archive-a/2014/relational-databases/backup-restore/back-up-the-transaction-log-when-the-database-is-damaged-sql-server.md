---
title: Sichern des Transaktionsprotokolls bei beschädigter Datenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], damaged
- backing up [SQL Server]. damaged database
- transaction log backups [SQL Server], damaged databases
ms.assetid: 9b8873cc-df54-4336-ab9b-8f525132c2b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea712e6bc4e73119a4f07a7775f9f25e212f8534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607854"
---
# <a name="back-up-the-transaction-log-when-the-database-is-damaged-sql-server"></a><span data-ttu-id="00b38-102">Sichern des Transaktionsprotokolls bei beschädigter Datenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="00b38-102">Back Up the Transaction Log When the Database Is Damaged (SQL Server)</span></span>
  <span data-ttu-id="00b38-103">In diesem Thema wird beschrieben, wie Sie ein Transaktionsprotokoll in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]sichern können, wenn die Datenbank beschädigt ist.</span><span class="sxs-lookup"><span data-stu-id="00b38-103">This topic describes how to back up a transaction log when the database is damaged in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="00b38-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="00b38-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="00b38-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="00b38-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="00b38-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="00b38-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="00b38-107">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="00b38-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="00b38-108">Security</span><span class="sxs-lookup"><span data-stu-id="00b38-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="00b38-109">**Sichern des Transaktionsprotokolls bei beschädigter Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="00b38-109">**To back up the transaction log when the database is damaged, using:**</span></span>  
  
     [<span data-ttu-id="00b38-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00b38-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="00b38-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00b38-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="00b38-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="00b38-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="00b38-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="00b38-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="00b38-114">Die BACKUP-Anweisung ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="00b38-114">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="00b38-115">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="00b38-115">Recommendations</span></span>  
  
-   <span data-ttu-id="00b38-116">Im Allgemeinen müssen Sie für eine Datenbank, die entweder das vollständige oder das massenprotokollierte Wiederherstellungsmodell verwendet, das Protokollfragment sichern, bevor Sie mit der Wiederherstellung der Datenbank beginnen.</span><span class="sxs-lookup"><span data-stu-id="00b38-116">For a database that uses either the full or bulk-logged recovery model, you generally need to back up the tail of the log before beginning to restore the database.</span></span> <span data-ttu-id="00b38-117">Vor dem Ausführen eines Failovers einer Protokollversandkonfiguration sollten Sie ebenfalls das Protokollfragment der primären Datenbank sichern.</span><span class="sxs-lookup"><span data-stu-id="00b38-117">You also should back up the tail of the log of the primary database before failing over a log shipping configuration.</span></span> <span data-ttu-id="00b38-118">Das Sichern des Protokollfragments als abschließende Protokollsicherung vor dem Wiederherstellen der Datenbank vermeidet den Datenverlust nach einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="00b38-118">Restoring the tail-log backup as the final log backup before recovering the database avoids work loss after a failure.</span></span> <span data-ttu-id="00b38-119">Weitere Informationen zu Sicherungen des Protokollfragments finden Sie unter [Protokollfragmentsicherungen &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00b38-119">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="00b38-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="00b38-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="00b38-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="00b38-121">Permissions</span></span>  
 <span data-ttu-id="00b38-122">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="00b38-122">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="00b38-123">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="00b38-123">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="00b38-124">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="00b38-124">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="00b38-125">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="00b38-125">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="00b38-126">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="00b38-126">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="00b38-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00b38-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-the-tail-of-the-transaction-log"></a><span data-ttu-id="00b38-128">So sichern Sie das Transaktionsprotokollfragment</span><span class="sxs-lookup"><span data-stu-id="00b38-128">To back up the tail of the transaction log</span></span>  
  
1.  <span data-ttu-id="00b38-129">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="00b38-129">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="00b38-130">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="00b38-130">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="00b38-131">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="00b38-131">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="00b38-132">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b38-132">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="00b38-133">Überprüfen Sie den Datenbanknamen im Listenfeld **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="00b38-133">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="00b38-134">Sie können optional eine andere Datenbank aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="00b38-134">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="00b38-135">Überprüfen Sie, ob als Wiederherstellungsmodell entweder **FULL** oder **BULK_LOGGED**ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="00b38-135">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="00b38-136">Wählen Sie im Listenfeld **Sicherungstyp** den Eintrag **Transaktionsprotokoll**aus.</span><span class="sxs-lookup"><span data-stu-id="00b38-136">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="00b38-137">Lassen Sie **Nur Sicherung kopieren** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="00b38-137">Leave **Copy Only Backup** deselected.</span></span>  
  
8.  <span data-ttu-id="00b38-138">Akzeptieren Sie im Bereich **Sicherungssatz** entweder den im Textfeld **Name** vorgeschlagenen Standardnamen für den Sicherungssatz, oder geben Sie einen anderen Namen für den Sicherungssatz ein.</span><span class="sxs-lookup"><span data-stu-id="00b38-138">In the **Backup set** area, either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="00b38-139">Geben Sie im Textfeld **Beschreibung** eine Beschreibung für die Sicherung des Protokollfragments ein.</span><span class="sxs-lookup"><span data-stu-id="00b38-139">In the **Description** text box, enter a description for the tail-log backup.</span></span>  
  
10. <span data-ttu-id="00b38-140">Geben Sie an, wann der Sicherungssatz ablaufen soll:</span><span class="sxs-lookup"><span data-stu-id="00b38-140">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="00b38-141">Wenn der Sicherungssatz nach einer bestimmten Anzahl von Tagen ablaufen soll, klicken Sie auf **Nach** (die Standardoption), und geben Sie an, nach wie vielen Tagen der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="00b38-141">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="00b38-142">Dieser Wert kann zwischen 0 und 99999 Tagen liegen. Ein Wert von 0 Tagen bedeutet, dass der Sicherungssatz nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="00b38-142">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="00b38-143">Der Standardwert wird im Dialogfeld **Servereigenschaften** (Seite **Datenbankeinstellungen** ) über die Option**Standardbeibehaltung für Sicherungsmedien (in Tagen)** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00b38-143">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="00b38-144">Klicken Sie zum Zugreifen auf dieses Dialogfeld im Objekt-Explorer mit der rechten Maustaste auf den Servernamen, und wählen Sie „Eigenschaften“ aus. Wählen Sie anschließend die Seite **Datenbankeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="00b38-144">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="00b38-145">Zum Speichern des Sicherungssatzes an einem bestimmten Datum klicken Sie auf **Am**. Geben Sie das Datum ein, an dem der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="00b38-145">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="00b38-146">Wählen Sie den Sicherungszieltyp aus, indem Sie auf **Datenträger** oder **Band**klicken.</span><span class="sxs-lookup"><span data-stu-id="00b38-146">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="00b38-147">Klicken Sie auf **Hinzufügen**, um die Pfade von bis zu 64 Datenträgern oder Bandlaufwerken, die einen einzelnen Mediensatz enthalten, auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="00b38-147">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="00b38-148">Die ausgewählten Pfade werden im Listenfeld **Sichern auf** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b38-148">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="00b38-149">Um einen Sicherungsziel zu entfernen, wählen Sie ihn aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="00b38-149">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="00b38-150">Zum Anzeigen des Inhalts eines Sicherungsziels wählen Sie es aus, und klicken Sie auf **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="00b38-150">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="00b38-151">Wählen Sie auf der Seite **Optionen** eine Option von **Medium überschreiben** aus, indem Sie auf eine der folgenden Optionen klicken:</span><span class="sxs-lookup"><span data-stu-id="00b38-151">On the **Options** page, select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="00b38-152">**Auf vorhandenen Mediensatz sichern**</span><span class="sxs-lookup"><span data-stu-id="00b38-152">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="00b38-153">Klicken Sie bei dieser Option entweder auf **An vorhandenen Sicherungssatz anfügen** oder auf **Alle vorhandenen Sicherungssätze überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="00b38-153">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span>  
  
         <span data-ttu-id="00b38-154">Sie können bei Bedarf das Kontrollkästchen **Mediensatznamen und Ablaufzeit des Sicherungssatzes überprüfen** aktivieren, damit beim Sicherungsvorgang das Datum und die Uhrzeit überprüft werden, an dem bzw. zu der der Mediensatz und der Sicherungssatz ablaufen.</span><span class="sxs-lookup"><span data-stu-id="00b38-154">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="00b38-155">Geben Sie optional einen Namen im Textfeld **Mediensatzname** ein.</span><span class="sxs-lookup"><span data-stu-id="00b38-155">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="00b38-156">Wenn kein Name angegeben wurde, wird ein Mediensatz mit leerem Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="00b38-156">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="00b38-157">Wenn Sie einen Mediensatznamen angeben, wird überprüft, ob der tatsächliche Name des Mediums (Band oder Datenträger) mit dem eingegebenen Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="00b38-157">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="00b38-158">Wenn Sie den Mediennamen leer lassen und das Kontrollkästchen aktivieren, um ihn anhand des Mediums zu überprüfen, ist die Prüfung erfolgreich, wenn der Medienname auf dem Medium ebenfalls leer ist.</span><span class="sxs-lookup"><span data-stu-id="00b38-158">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="00b38-159">**Auf neuen Mediensatz sichern und alle vorhandenen Sicherungssätze löschen**</span><span class="sxs-lookup"><span data-stu-id="00b38-159">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="00b38-160">Geben Sie bei dieser Option einen Namen in das Textfeld **Name für neuen Mediensatz** und optional eine Beschreibung des Mediensatzes in das Textfeld **Beschreibung für neuen Mediensatz** ein.</span><span class="sxs-lookup"><span data-stu-id="00b38-160">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
     <span data-ttu-id="00b38-161">Weitere Informationen über Mediensätze finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00b38-161">For more information about media set options, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
13. <span data-ttu-id="00b38-162">Im Bereich **Zuverlässigkeit** können Sie folgende Optionen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="00b38-162">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="00b38-163">**Sicherung nach dem Abschluss überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="00b38-163">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="00b38-164">**Vor dem Schreiben auf die Medien Prüfsumme bilden**</span><span class="sxs-lookup"><span data-stu-id="00b38-164">**Perform checksum before writing to media**.</span></span>  
  
    -   <span data-ttu-id="00b38-165">**Bei Prüfsummenfehler fortfahren**</span><span class="sxs-lookup"><span data-stu-id="00b38-165">**Continue on checksum error**</span></span>  
  
     <span data-ttu-id="00b38-166">Weitere Informationen finden Sie unter [Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00b38-166">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="00b38-167">Aktivieren Sie im Abschnitt **Transaktionsprotokoll** die Option **Protokollfragment sichern und Datenbank im Wiederherstellungsstatus belassen**.</span><span class="sxs-lookup"><span data-stu-id="00b38-167">In the **Transaction log** section, check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
     <span data-ttu-id="00b38-168">Dies entspricht dem Angeben der folgenden [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung:</span><span class="sxs-lookup"><span data-stu-id="00b38-168">This is equivalent to specifying the following [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
     `BACKUP LOG <database_name> TO <backup_device> WITH NORECOVERY`  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="00b38-169">Zur Wiederherstellungszeit wird im Dialogfeld „Datenbank wiederherstellen“ der Typ einer Protokollfragmentsicherung als **Transaktionsprotokoll (Nur Kopie)** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b38-169">At restore time, the Restore Database dialog box displays the type of a tail-log backup as **Transaction Log (Copy Only)**.</span></span>  
  
15. <span data-ttu-id="00b38-170">Wenn Sie auf ein Bandlaufwerk sichern (gemäß der Konfiguration im Abschnitt **Ziel** der Seite **Allgemein** ), ist die Option **Band nach dem Sichern entladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="00b38-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="00b38-171">Wenn Sie auf diese Option klicken, wird die Option **Band vor dem Entladen zurückspulen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="00b38-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
16. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="00b38-172">und höheren Versionen wird die [Sicherungskomprimierung](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00b38-172">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="00b38-173">Ob eine Sicherung standardmäßig komprimiert wird, ist abhängig vom Wert der Serverkonfigurationsoption **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="00b38-173">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="00b38-174">Sie können jedoch unabhängig von der aktuellen Standardeinstellung auf Serverebene eine Sicherung komprimieren, indem Sie die Option **Sicherung komprimieren**aktivieren, oder die Komprimierung verhindern, indem Sie die Option **Sicherung nicht komprimieren**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="00b38-174">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="00b38-175">**So zeigen Sie die aktuelle Standardeinstellung für die Sicherungskomprimierung (Option "backup compression default") an**</span><span class="sxs-lookup"><span data-stu-id="00b38-175">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="00b38-176">Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="00b38-176">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="00b38-177">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00b38-177">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-backup-of-the-currently-active-transaction-log"></a><span data-ttu-id="00b38-178">So erstellen Sie eine Sicherung des aktuell aktiven Transaktionsprotokolls</span><span class="sxs-lookup"><span data-stu-id="00b38-178">To create a backup of the currently active transaction log</span></span>  
  
1.  <span data-ttu-id="00b38-179">Führen Sie die BACKUP LOG-Anweisung aus, um das aktuell aktive Transaktionsprotokoll zu sichern, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="00b38-179">Execute the BACKUP LOG statement to back up the currently active transaction log, specifying:</span></span>  
  
    -   <span data-ttu-id="00b38-180">Den Namen der Datenbank, zu der das zu sichernde Transaktionsprotokoll gehört.</span><span class="sxs-lookup"><span data-stu-id="00b38-180">The name of the database to which the transaction log to back up belongs.</span></span>  
  
    -   <span data-ttu-id="00b38-181">Das Sicherungsmedium, auf das die Transaktionsprotokollsicherung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="00b38-181">The backup device where the transaction log backup will be written.</span></span>  
  
    -   <span data-ttu-id="00b38-182">Die NO_TRUNCATE-Klausel.</span><span class="sxs-lookup"><span data-stu-id="00b38-182">The NO_TRUNCATE clause.</span></span>  
  
         <span data-ttu-id="00b38-183">Mit dieser Klausel ist ein Sichern des aktiven Teils des Transaktionsprotokolls auch dann möglich, wenn nicht auf die Datenbank zugegriffen werden kann. Voraussetzung hierfür ist allerdings, dass auf die Transaktionsprotokolldateien zugegriffen werden kann und diese unbeschädigt sind.</span><span class="sxs-lookup"><span data-stu-id="00b38-183">This clause allows the active part of the transaction log to be backed up even if the database is inaccessible, provided that the transaction log file is accessible and undamaged.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="00b38-184">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="00b38-184">Example (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00b38-185">In diesem Beispiel wird [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]verwendet, das das einfache Wiederherstellungsmodell verwendet.</span><span class="sxs-lookup"><span data-stu-id="00b38-185">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], which uses the simple recovery model.</span></span> <span data-ttu-id="00b38-186">Um Protokollsicherungen zu ermöglichen, wurde für die Datenbank vor dem Erstellen einer vollständigen Datenbanksicherung die Verwendung des vollständigen Wiederherstellungsmodells festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00b38-186">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="00b38-187">Weitere Informationen finden Sie unter [Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00b38-187">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="00b38-188">In diesem Beispiel wird das derzeit aktive Transaktionsprotokoll bei einer beschädigten oder nicht erreichbaren Datenbank gesichert, sofern das Transaktionsprotokoll unbeschädigt und erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="00b38-188">This example backs up the currently active transaction log when a database is damaged and inaccessible, if the transaction log is undamaged and accessible.</span></span>  
  
```scr  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1  
   WITH NO_TRUNCATE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="00b38-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00b38-189">See Also</span></span>  
 <span data-ttu-id="00b38-190">[Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00b38-190">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="00b38-191">[Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="00b38-191">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="00b38-192">[Datenbank sichern &#40;Seite 'Sicherungsoptionen'&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="00b38-192">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="00b38-193">[Datenbank sichern &#40;Seite Allgemein&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="00b38-193">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="00b38-194">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00b38-194">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="00b38-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="00b38-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="00b38-196">[Dateiwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="00b38-196">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="00b38-197">Dateiwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="00b38-197">File Restores &#40;Full Recovery Model&#41;</span></span>](file-restores-full-recovery-model.md)  
  
  
