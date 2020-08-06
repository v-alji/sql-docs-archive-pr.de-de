---
title: Erstellen einer differenziellen Datenbanksicherung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- database backups [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
- backups [SQL Server], creating
ms.assetid: 70f49794-b217-4519-9f2a-76ed61fa9f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c3fb53d90ce633498bc518282d1ff03ce0b926e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622710"
---
# <a name="create-a-differential-database-backup-sql-server"></a><span data-ttu-id="f4f7e-102">Erstellen einer differenziellen Datenbanksicherung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f4f7e-102">Create a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="f4f7e-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] eine differenzielle Datenbanksicherung mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]sichern.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-103">This topic describes how to create a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f4f7e-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f4f7e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f4f7e-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f4f7e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f4f7e-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f4f7e-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f4f7e-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f4f7e-109">Security</span><span class="sxs-lookup"><span data-stu-id="f4f7e-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f4f7e-110">**So erstellen Sie eine differenzielle Datenbanksicherung mit**</span><span class="sxs-lookup"><span data-stu-id="f4f7e-110">**To create a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="f4f7e-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f4f7e-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f4f7e-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f4f7e-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f4f7e-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f4f7e-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f4f7e-115">Die BACKUP-Anweisung ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-115">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f4f7e-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="f4f7e-117">Eine differenzielle Datenbanksicherung kann nur erstellt werden, wenn bereits eine frühere vollständige Datenbanksicherung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-117">Creating a differential database backup requires that a previous full database backup exist.</span></span> <span data-ttu-id="f4f7e-118">Wenn die ausgewählte Datenbank noch nie gesichert wurde, führen Sie vor dem Erstellen differenzieller Sicherungen zunächst eine vollständige Datenbanksicherung aus.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-118">If the selected database has never been backed up, run a full database backup before creating any differential backups.</span></span> <span data-ttu-id="f4f7e-119">Weitere Informationen finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f4f7e-119">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f4f7e-120">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-120">Recommendations</span></span>  
  
-   <span data-ttu-id="f4f7e-121">Mit zunehmender Größe der differenziellen Sicherungen kann das Wiederherstellen einer differenziellen Sicherung den Zeitaufwand zum Wiederherstellen einer Datenbank erheblich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-121">As the differential backups increase in size, restoring a differential backup can significantly increase the time that is required to restore a database.</span></span> <span data-ttu-id="f4f7e-122">Daher sollten Sie in regelmäßigen Abständen neue vollständige Sicherungen ausführen, um eine neue differenzielle Basis für die Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-122">Therefore, we recommend that you take a new full backup at set intervals to establish a new differential base for the data.</span></span> <span data-ttu-id="f4f7e-123">Sie können z. B. einmal wöchentlich eine vollständige Sicherung der gesamten Datenbank (also eine vollständige Datenbanksicherung) und während der Woche eine regelmäßige Serie von differenziellen Datenbanksicherungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-123">For example, you might take a weekly full backup of the whole database (that is, a full database backup) followed by a regular series of differential database backups during the week.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f4f7e-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f4f7e-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f4f7e-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-125">Permissions</span></span>  
 <span data-ttu-id="f4f7e-126">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-126">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="f4f7e-127">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-127">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f4f7e-128">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-128">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="f4f7e-129">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-129">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="f4f7e-130">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-130">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f4f7e-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f4f7e-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="f4f7e-132">So erstellen Sie eine differenzielle Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="f4f7e-132">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="f4f7e-133">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-133">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f4f7e-134">Erweitern Sie den Ordner **Datenbanken**, und wählen Sie dann je nach Datenbank entweder eine Benutzerdatenbank aus, oder erweitern Sie die Option **Systemdatenbanken** , um eine Systemdatenbank auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-134">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="f4f7e-135">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-135">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="f4f7e-136">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-136">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="f4f7e-137">Überprüfen Sie den Datenbanknamen im Listenfeld **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="f4f7e-137">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="f4f7e-138">Sie können optional eine andere Datenbank aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-138">You can optionally select a different database from the list.</span></span>  
  
     <span data-ttu-id="f4f7e-139">Sie können für jedes Wiederherstellungsmodell (vollständig, massenprotokolliert oder einfach) eine differenzielle Sicherung ausführen.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-139">You can perform a differential backup for any recovery model (full, bulk-logged, or simple).</span></span>  
  
5.  <span data-ttu-id="f4f7e-140">Wählen Sie im Listenfeld **Sicherungstyp** die Option **Differenziell**aus.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-140">In the **Backup type** list box, select **Differential**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f4f7e-141">Stellen Sie sicher, dass das Kontrollkästchen **Kopiesicherung** deaktiviert ist, wenn **Differenziell** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-141">When **Differential** is selected, verify that the **Copy Only Backup** check box is cleared.</span></span>  
  
6.  <span data-ttu-id="f4f7e-142">Klicken Sie unter **Sicherungskomponente**auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-142">For **Backup component**, click **Database**.</span></span>  
  
7.  <span data-ttu-id="f4f7e-143">Akzeptieren Sie entweder den im Textfeld **Name** vorgeschlagenen Standardnamen für den Sicherungssatz, oder geben Sie einen anderen Namen für den Sicherungssatz ein.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-143">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
8.  <span data-ttu-id="f4f7e-144">Geben Sie optional in das Textfeld **Beschreibung** eine Beschreibung des Sicherungssatzes ein.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-144">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
9. <span data-ttu-id="f4f7e-145">Geben Sie an, wann der Sicherungssatz ablaufen soll:</span><span class="sxs-lookup"><span data-stu-id="f4f7e-145">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="f4f7e-146">Wenn der Sicherungssatz nach einer bestimmten Anzahl von Tagen ablaufen soll, klicken Sie auf **Nach** (die Standardoption), und geben Sie an, nach wie vielen Tagen der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-146">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="f4f7e-147">Dieser Wert kann zwischen 0 und 99999 Tagen liegen. Ein Wert von 0 Tagen bedeutet, dass der Sicherungssatz nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-147">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="f4f7e-148">Der Standardwert wird im Dialogfeld **Servereigenschaften** (Seite **Datenbankeinstellungen** ) über die Option**Standardbeibehaltung für Sicherungsmedien (in Tagen)** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-148">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="f4f7e-149">Klicken Sie hierzu mit der rechten Maustaste auf den Servernamen im Objekt-Explorer, und wählen Sie Eigenschaften aus. Wählen Sie anschließend die Seite **Datenbankeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-149">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="f4f7e-150">Zum Speichern des Sicherungssatzes an einem bestimmten Datum klicken Sie auf **Am**. Geben Sie das Datum ein, an dem der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-150">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
10. <span data-ttu-id="f4f7e-151">Wählen Sie den Sicherungszieltyp aus, indem Sie auf **Datenträger** oder **Band**klicken.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-151">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="f4f7e-152">Um den Pfad für bis zu 64 Datenträger oder Bandlaufwerke auszuwählen, die insgesamt einen einzigen Mediensatz enthalten, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-152">To select the path of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="f4f7e-153">Die ausgewählten Pfade werden im Listenfeld **Sichern auf** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-153">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="f4f7e-154">Um einen Sicherungsziel zu entfernen, wählen Sie ihn aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-154">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="f4f7e-155">Zum Anzeigen des Inhalts eines Sicherungsziels wählen Sie es aus, und klicken Sie auf **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-155">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
11. <span data-ttu-id="f4f7e-156">Zum Anzeigen oder Auswählen der erweiterten Optionen klicken Sie auf **Optionen** im Bereich **Seite auswählen** .</span><span class="sxs-lookup"><span data-stu-id="f4f7e-156">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
12. <span data-ttu-id="f4f7e-157">Wählen Sie eine Option von **Medium überschreiben** aus, indem Sie auf eine der folgenden Optionen klicken:</span><span class="sxs-lookup"><span data-stu-id="f4f7e-157">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="f4f7e-158">**Auf vorhandenen Mediensatz sichern**</span><span class="sxs-lookup"><span data-stu-id="f4f7e-158">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="f4f7e-159">Klicken Sie bei dieser Option entweder auf **An vorhandenen Sicherungssatz anfügen** oder auf **Alle vorhandenen Sicherungssätze überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-159">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="f4f7e-160">Sie können bei Bedarf das Kontrollkästchen **Mediensatznamen und Ablaufzeit des Sicherungssatzes überprüfen** aktivieren und optional einen Namen in das Textfeld **Mediensatzname** eingeben.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-160">Optionally, check the **Check media set name and backup set expiration** check box and, optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="f4f7e-161">Wenn kein Name angegeben wurde, wird ein Mediensatz mit leerem Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-161">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="f4f7e-162">Wenn Sie einen Mediensatznamen angeben, wird das Medium (Band oder Datenträger) daraufhin geprüft, ob der tatsächliche Name mit dem hier eingegebenen Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-162">If you specify a media set name, the media (tape or disk) is checked to see if the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="f4f7e-163">Wenn Sie den Mediennamen leer lassen und das Kontrollkästchen aktivieren, um ihn anhand des Mediums zu überprüfen, ist die Prüfung erfolgreich, wenn der Medienname auf dem Medium ebenfalls leer ist.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-163">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="f4f7e-164">**Auf neuen Mediensatz sichern und alle vorhandenen Sicherungssätze löschen**</span><span class="sxs-lookup"><span data-stu-id="f4f7e-164">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="f4f7e-165">Geben Sie bei dieser Option einen Namen in das Textfeld **Name für neuen Mediensatz** und optional eine Beschreibung des Mediensatzes in das Textfeld **Beschreibung für neuen Mediensatz** ein.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-165">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
13. <span data-ttu-id="f4f7e-166">Im Bereich **Zuverlässigkeit** können Sie folgende Optionen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f4f7e-166">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="f4f7e-167">**Sicherung nach dem Abschluss überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-167">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="f4f7e-168">**Vor dem Schreiben auf die Medien Prüfsumme bilden**, und optional **Bei Prüfsummenfehler fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-168">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="f4f7e-169">Weitere Informationen zu Prüfsummen finden Sie unter [Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f4f7e-169">For information about checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="f4f7e-170">Wenn Sie auf ein Bandlaufwerk sichern (gemäß der Konfiguration im Abschnitt **Ziel** der Seite **Allgemein** ), ist die Option **Band nach dem Sichern entladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="f4f7e-171">Wenn Sie auf diese Option klicken, wird die Option **Band vor dem Entladen zurückspulen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4f7e-172">Die Optionen im Abschnitt **Transaktionsprotokoll** sind inaktiv, es sei denn, Sie sichern ein Transaktionsprotokoll (wie im Abschnitt **Sicherungstyp** der Seite **Allgemein** angegeben).</span><span class="sxs-lookup"><span data-stu-id="f4f7e-172">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
15. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="f4f7e-173">und höheren Versionen wird die [Sicherungskomprimierung](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f4f7e-173">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="f4f7e-174">Ob eine Sicherung standardmäßig komprimiert wird, ist abhängig vom Wert der Serverkonfigurationsoption **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="f4f7e-174">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="f4f7e-175">Sie können jedoch unabhängig von der aktuellen Standardeinstellung auf Serverebene eine Sicherung komprimieren, indem Sie die Option **Sicherung komprimieren**aktivieren, oder die Komprimierung verhindern, indem Sie die Option **Sicherung nicht komprimieren**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-175">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="f4f7e-176">**So zeigen Sie die aktuelle Standardeinstellung für die Sicherungskomprimierung (Option "backup compression default") an**</span><span class="sxs-lookup"><span data-stu-id="f4f7e-176">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="f4f7e-177">Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="f4f7e-177">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4f7e-178">Alternativ können Sie den Wartungsplanungs-Assistenten zum Erstellen differenzieller Datenbanksicherungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-178">Alternatively, you can use the Maintenance Plan Wizard to create differential database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f4f7e-179">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f4f7e-179">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="f4f7e-180">So erstellen Sie eine differenzielle Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="f4f7e-180">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="f4f7e-181">Führen Sie die BACKUP DATABASE-Anweisung aus, um die differenzielle Datenbanksicherung zu erstellen, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="f4f7e-181">Execute the BACKUP DATABASE statement to create the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="f4f7e-182">Den Namen der zu sichernden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-182">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="f4f7e-183">Das Sicherungsmedium, auf das die vollständige Datenbanksicherung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-183">The backup device where the full database backup is written.</span></span>  
  
    -   <span data-ttu-id="f4f7e-184">Die DIFFERENTIAL-Klausel, um anzugeben, dass nur die Abschnitte der Datenbank gesichert werden sollen, die sich nach dem Erstellen der letzten vollständigen Datenbanksicherung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="f4f7e-184">The DIFFERENTIAL clause, to specify that only the parts of the database that have changed after the last full database backup was created are backed up.</span></span>  
  
     <span data-ttu-id="f4f7e-185">Die erforderliche Syntax lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="f4f7e-185">The required syntax is:</span></span>  
  
     <span data-ttu-id="f4f7e-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="f4f7e-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="f4f7e-187">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f4f7e-187">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="f4f7e-188">In diesem Beispiel werden eine vollständige und eine differenzielle Datenbanksicherung für die `MyAdvWorks` -Datenbank erstellt</span><span class="sxs-lookup"><span data-stu-id="f4f7e-188">This example creates a full and a differential database backup for the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Create a full database backup first.  
BACKUP DATABASE MyAdvWorks   
   TO MyAdvWorks_1   
   WITH INIT;  
GO  
-- Time elapses.  
-- Create a differential database backup, appending the backup  
-- to the backup device containing the full database backup.  
BACKUP DATABASE MyAdvWorks  
   TO MyAdvWorks_1  
   WITH DIFFERENTIAL;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4f7e-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4f7e-189">See Also</span></span>  
 <span data-ttu-id="f4f7e-190">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4f7e-190">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="f4f7e-191">[Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4f7e-191">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="f4f7e-192">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4f7e-192">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="f4f7e-193">[Wiederherstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4f7e-193">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="f4f7e-194">[Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4f7e-194">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="f4f7e-195">[Wartungspläne](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="f4f7e-195">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="f4f7e-196">Vollständige Dateisicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f4f7e-196">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
  
  
