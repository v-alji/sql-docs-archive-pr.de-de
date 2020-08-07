---
title: Wiederherstellen einer Transaktionsprotokollsicherung (SQL Server) | Microsoft-Datenbank
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.options.f1
- sql12.swb.restoretlog.general.f1
helpviewer_keywords:
- restore log
- backing up transaction logs [SQL Server], restoring
- transaction log backups [SQL Server], restoring
- restoring transaction logs [SQL Server], restoring backups
- transaction log restores [SQL Server], SQL Server Management Studio
ms.assetid: 1de2b888-78a6-4fb2-a647-ba4bf097caf3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fe4bbc199d6555bd490d25f92491100b8bbfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620461"
---
# <a name="restore-a-transaction-log-backup-sql-server"></a><span data-ttu-id="f88cc-102">Wiederherstellen einer Transaktionsprotokollsicherung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f88cc-102">Restore a Transaction Log Backup (SQL Server)</span></span>
  <span data-ttu-id="f88cc-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] eine Transaktionsprotokollsicherung mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-103">This topic describes how to restore a transaction log backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f88cc-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f88cc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f88cc-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f88cc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f88cc-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f88cc-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f88cc-107">Security</span><span class="sxs-lookup"><span data-stu-id="f88cc-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f88cc-108">**Wiederherstellen einer Transaktionsprotokollsicherung mit:**</span><span class="sxs-lookup"><span data-stu-id="f88cc-108">**To restore a transaction log backup, using:**</span></span>  
  
     [<span data-ttu-id="f88cc-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f88cc-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f88cc-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f88cc-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="f88cc-111">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f88cc-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f88cc-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f88cc-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f88cc-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f88cc-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="f88cc-114">Sicherungen müssen in der Reihenfolge wiederhergestellt werden, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-114">Backups must be restored in the order in which they were created.</span></span> <span data-ttu-id="f88cc-115">Bevor Sie eine bestimmte Transaktionsprotokollsicherung wiederherstellen können, müssen Sie zuerst die folgenden vorherigen Sicherungen wiederherstellen, ohne für Transaktionen ohne Commit ein Rollback auszuführen, also mit der Option WITH NORECOVERY:</span><span class="sxs-lookup"><span data-stu-id="f88cc-115">Before you can restore a particular transaction log backup, you must first restore the following previous backups without rolling back uncommitted transactions, that is WITH NORECOVERY:</span></span>  
  
    -   <span data-ttu-id="f88cc-116">Die vollständige Datenbanksicherung und die letzte, differenzielle Sicherung, die ggf. vor der betreffenden Transaktionsprotokollsicherung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f88cc-116">The full database backup and the last differential backup, if any, taken before the particular transaction log backup.</span></span> <span data-ttu-id="f88cc-117">Bevor die letzte vollständige oder differenzielle Datenbanksicherung erstellt wurde, muss die Datenbank das vollständige Wiederherstellungsmodell oder das massenprotokollierte Wiederherstellungsmodell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="f88cc-117">Before the most recent full or differential database backup was created, the database must have been using the full recovery model or bulk-logged recovery model.</span></span>  
  
    -   <span data-ttu-id="f88cc-118">Alle Transaktionsprotokollsicherungen, die nach der vollständigen Datenbanksicherung oder der differenziellen Sicherung (falls Sie eine solche Sicherung wiederherstellen) und vor der betreffenden Transaktionsprotokollsicherung durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-118">All transaction log backups taken after the full database backup or the differential backup (if you restore one) and before the particular transaction log backup.</span></span> <span data-ttu-id="f88cc-119">Protokollsicherungen müssen ohne Lücken in der Protokollkette in der Reihenfolge angewendet werden, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-119">Log backups must be applied in the sequence in which they were created, without any gaps in the log chain.</span></span>  
  
         <span data-ttu-id="f88cc-120">Weitere Informationen zu Transaktionsprotokollsicherungen finden Sie unter [ Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) und [Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f88cc-120">For more information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) and [Apply Transaction Log Backups &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f88cc-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f88cc-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f88cc-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f88cc-122">Permissions</span></span>  
 <span data-ttu-id="f88cc-123">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f88cc-123">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="f88cc-124">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-124">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f88cc-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f88cc-125">Using SQL Server Management Studio</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f88cc-126">Beim üblichen Prozess der Wiederherstellung wählen Sie im Dialogfeld **Datenbank wiederherstellen** die Protokollsicherungen zusammen mit den Datensicherungen und den differenziellen Sicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-126">The normal process of a restore is to select the log backups in the **Restore Database** dialog box along with the data and differential backups.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="f88cc-127">So stellen Sie eine Transaktionsprotokollsicherung wieder her</span><span class="sxs-lookup"><span data-stu-id="f88cc-127">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="f88cc-128">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f88cc-128">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f88cc-129">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-129">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="f88cc-130">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen**, und klicken Sie dann auf **Transaktionsprotokoll**. Daraufhin wird das Dialogfeld **Transaktionsprotokoll wiederherstellen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-130">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f88cc-131">Ist **Transaktionsprotokoll** ausgegraut, muss ggf. eine vollständige oder differenzielle Sicherung wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-131">If **Transaction Log** is grayed out, you may need to restore a full or differential backup first.</span></span> <span data-ttu-id="f88cc-132">Verwenden Sie das Sicherungsdialogfeld **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="f88cc-132">Use the **Database** backup dialog box.</span></span>  
  
4.  <span data-ttu-id="f88cc-133">Wählen Sie auf der Seite **Allgemein** im Listenfeld **Datenbank** den Namen einer Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-133">On the **General** page, in the **Database** list box, select the name of a database.</span></span> <span data-ttu-id="f88cc-134">Es werden nur Datenbanken im Wiederherstellungsstatus aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f88cc-134">Only databases in the restoring state are listed.</span></span>  
  
5.  <span data-ttu-id="f88cc-135">Zum Festlegen von Quelle und Speicherort der wiederherzustellenden Sicherungssätze klicken Sie auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="f88cc-135">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="f88cc-136">**Von vorherigen Sicherungen der Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f88cc-136">**From previous backups of database**</span></span>  
  
         <span data-ttu-id="f88cc-137">Wählen Sie die wiederherzustellende Datenbank aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-137">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="f88cc-138">Die Liste enthält nur Datenbanken, die entsprechend dem Sicherungsverlauf von **msdb** gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-138">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="f88cc-139">**Aus Datei oder von Band**</span><span class="sxs-lookup"><span data-stu-id="f88cc-139">**From file or tape**</span></span>  
  
         <span data-ttu-id="f88cc-140">Klicken Sie auf die Schaltfläche zum Durchsuchen ( **...** ), um das Dialogfeld **Sicherungsmedien auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-140">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="f88cc-141">Wählen Sie im Feld **Sicherungsmedientyp** einen der aufgeführten Medientypen aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-141">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="f88cc-142">Wenn Sie ein oder mehrere Medien für das Feld **Sicherungsmedien** auswählen möchten, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f88cc-142">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="f88cc-143">Klicken Sie nach dem Hinzufügen der gewünschten Medien zum Listenfeld **Sicherungsmedien** auf **OK** , um zur Seite **Allgemein** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f88cc-143">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
6.  <span data-ttu-id="f88cc-144">Wählen Sie im Raster **Wählen Sie die wiederherzustellenden Transaktionsprotokollsicherungen aus** die wiederherzustellenden Sicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-144">In the **Select the transaction log backups to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="f88cc-145">In diesem Raster werden die für die ausgewählte Datenbank zur Verfügung stehenden Transaktionsprotokollsicherungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f88cc-145">This grid lists the transaction log backups available for the selected database.</span></span> <span data-ttu-id="f88cc-146">Eine Protokollsicherung ist nur verfügbar, wenn der entsprechende Wert für **Erste LSN** größer als der Wert für **Letzte LSN** der Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="f88cc-146">A log backup is available only if its **First LSN** greater than the **Last LSN** of the database.</span></span> <span data-ttu-id="f88cc-147">Protokollsicherungen werden in der Reihenfolge der enthaltenen Protokollsequenznummern (Log Sequence Number, LSN) angezeigt und müssen in dieser Reihenfolge wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-147">Log backups are listed in the order of the log sequence numbers (LSN) they contain, and they must be restored in this order.</span></span>  
  
     <span data-ttu-id="f88cc-148">In der folgenden Tabelle werden die Spaltenheader des Rasters aufgelistet und deren Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f88cc-148">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="f88cc-149">Header</span><span class="sxs-lookup"><span data-stu-id="f88cc-149">Header</span></span>|<span data-ttu-id="f88cc-150">Wert</span><span class="sxs-lookup"><span data-stu-id="f88cc-150">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="f88cc-151">**Wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="f88cc-151">**Restore**</span></span>|<span data-ttu-id="f88cc-152">Aktivierte Kontrollkästchen zeigen die wiederherzustellenden Sicherungssätze an.</span><span class="sxs-lookup"><span data-stu-id="f88cc-152">Selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="f88cc-153">**Name**</span><span class="sxs-lookup"><span data-stu-id="f88cc-153">**Name**</span></span>|<span data-ttu-id="f88cc-154">Name des Sicherungssatzes.</span><span class="sxs-lookup"><span data-stu-id="f88cc-154">Name of the backup set.</span></span>|  
    |<span data-ttu-id="f88cc-155">**Komponente**</span><span class="sxs-lookup"><span data-stu-id="f88cc-155">**Component**</span></span>|<span data-ttu-id="f88cc-156">Gesicherte Komponente: **Datenbank**, **Datei** oder \<blank> (bei Transaktionsprotokollen).</span><span class="sxs-lookup"><span data-stu-id="f88cc-156">Backed-up component: **Database**, **File**, or \<blank> (for transaction logs).</span></span>|  
    |<span data-ttu-id="f88cc-157">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f88cc-157">**Database**</span></span>|<span data-ttu-id="f88cc-158">Name der an dem Sicherungsvorgang beteiligten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f88cc-158">Name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="f88cc-159">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="f88cc-159">**Start Date**</span></span>|<span data-ttu-id="f88cc-160">Datum und Uhrzeit des Sicherungsbeginns, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="f88cc-160">Date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="f88cc-161">**Beendigungsdatum**</span><span class="sxs-lookup"><span data-stu-id="f88cc-161">**Finish Date**</span></span>|<span data-ttu-id="f88cc-162">Datum und Uhrzeit des Sicherungsabschlusses, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="f88cc-162">Date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="f88cc-163">**Erste LSN**</span><span class="sxs-lookup"><span data-stu-id="f88cc-163">**First LSN**</span></span>|<span data-ttu-id="f88cc-164">Protokollsequenznummer der ersten Transaktion im Sicherungssatz.</span><span class="sxs-lookup"><span data-stu-id="f88cc-164">Log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="f88cc-165">Bei Dateisicherungen leer.</span><span class="sxs-lookup"><span data-stu-id="f88cc-165">Blank for file backups.</span></span>|  
    |<span data-ttu-id="f88cc-166">**Erste LSN**</span><span class="sxs-lookup"><span data-stu-id="f88cc-166">**Last LSN**</span></span>|<span data-ttu-id="f88cc-167">Protokollsequenznummer der letzten Transaktion im Sicherungssatz.</span><span class="sxs-lookup"><span data-stu-id="f88cc-167">Log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="f88cc-168">Bei Dateisicherungen leer.</span><span class="sxs-lookup"><span data-stu-id="f88cc-168">Blank for file backups.</span></span>|  
    |<span data-ttu-id="f88cc-169">**Prüfpunkt-LSN**</span><span class="sxs-lookup"><span data-stu-id="f88cc-169">**Checkpoint LSN**</span></span>|<span data-ttu-id="f88cc-170">Protokollsequenznummer des letzten Prüfpunkts zum Zeitpunkt der Erstellung der Sicherung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-170">Log sequence number of the most recent checkpoint at the time the backup was created.</span></span>|  
    |<span data-ttu-id="f88cc-171">**Vollständige LSN**</span><span class="sxs-lookup"><span data-stu-id="f88cc-171">**Full LSN**</span></span>|<span data-ttu-id="f88cc-172">Protokollsequenznummer der neuesten vollständigen Datenbanksicherung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-172">Log sequence number of the most recent full database backup.</span></span>|  
    |<span data-ttu-id="f88cc-173">**Server**</span><span class="sxs-lookup"><span data-stu-id="f88cc-173">**Server**</span></span>|<span data-ttu-id="f88cc-174">Name der Instanz der Datenbank-Engine, durch die der Sicherungsvorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f88cc-174">Name of the Database Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="f88cc-175">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="f88cc-175">**User Name**</span></span>|<span data-ttu-id="f88cc-176">Name des Benutzers, der den Sicherungsvorgang ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="f88cc-176">Name of the user who performed the backup operation.</span></span>|  
    |<span data-ttu-id="f88cc-177">**Größe**</span><span class="sxs-lookup"><span data-stu-id="f88cc-177">**Size**</span></span>|<span data-ttu-id="f88cc-178">Größe des Sicherungssatzes in Byte.</span><span class="sxs-lookup"><span data-stu-id="f88cc-178">Size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="f88cc-179">**Position**</span><span class="sxs-lookup"><span data-stu-id="f88cc-179">**Position**</span></span>|<span data-ttu-id="f88cc-180">Position des Sicherungssatzes auf dem Volume.</span><span class="sxs-lookup"><span data-stu-id="f88cc-180">Position of the backup set in the volume.</span></span>|  
    |<span data-ttu-id="f88cc-181">**Ablauf**</span><span class="sxs-lookup"><span data-stu-id="f88cc-181">**Expiration**</span></span>|<span data-ttu-id="f88cc-182">Datum und Uhrzeit des Zeitpunkts, zu dem die Gültigkeit des Sicherungssatzes endet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-182">Date and time the backup set expires.</span></span>|  
  
7.  <span data-ttu-id="f88cc-183">Wählen Sie eines der folgenden Szenarien aus:</span><span class="sxs-lookup"><span data-stu-id="f88cc-183">Select one of the following:</span></span>  
  
    -   <span data-ttu-id="f88cc-184">**Zeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="f88cc-184">**Point in time**</span></span>  
  
         <span data-ttu-id="f88cc-185">Behalten Sie entweder die Standardeinstellung bei (**Aktuellster möglicher Status**), oder wählen Sie Datum und Uhrzeit aus, indem Sie auf die Schaltfläche zum Durchsuchen klicken. Daraufhin wird das Dialogfeld **Zeitpunktwiederherstellung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-185">Either retain the default (**Most recent possible**) or select a specific date and time by clicking the browse button, which opens the **Point in Time Restore** dialog box.</span></span>  
  
    -   <span data-ttu-id="f88cc-186">**Markierte Transaktion**</span><span class="sxs-lookup"><span data-stu-id="f88cc-186">**Marked transaction**</span></span>  
  
         <span data-ttu-id="f88cc-187">Stellen Sie für die Datenbank den Zustand zum Zeitpunkt einer zuvor markierten Transaktion wieder her.</span><span class="sxs-lookup"><span data-stu-id="f88cc-187">Restore the database to a previously marked transaction.</span></span> <span data-ttu-id="f88cc-188">Nach Auswahl dieser Option wird das Dialogfeld **Markierte Transaktion auswählen** geöffnet, in dem ein Raster mit den in den ausgewählten Transaktionsprotokollsicherungen verfügbaren markierten Transaktionen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f88cc-188">Selecting this option launches the **Select Marked Transaction** dialog box, which displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
         <span data-ttu-id="f88cc-189">Standardmäßig erfolgt die Wiederherstellung bis zur markierten Transaktion (die jedoch nicht eingeschlossen wird).</span><span class="sxs-lookup"><span data-stu-id="f88cc-189">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="f88cc-190">Um die markierte Transaktion ebenfalls wiederherzustellen, wählen Sie **Markierte Transaktion einschließen**aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-190">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
         <span data-ttu-id="f88cc-191">In der folgenden Tabelle werden die Spaltenheader des Rasters aufgelistet und deren Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f88cc-191">The following table lists the column headers of the grid and describes their values.</span></span>  
  
        |<span data-ttu-id="f88cc-192">Header</span><span class="sxs-lookup"><span data-stu-id="f88cc-192">Header</span></span>|<span data-ttu-id="f88cc-193">Wert</span><span class="sxs-lookup"><span data-stu-id="f88cc-193">Value</span></span>|  
        |------------|-----------|  
        |\<blank>|<span data-ttu-id="f88cc-194">Zeigt ein Kontrollkästchen zur Auswahl der Markierung an.</span><span class="sxs-lookup"><span data-stu-id="f88cc-194">Displays a checkbox for selecting the mark.</span></span>|  
        |<span data-ttu-id="f88cc-195">**Transaktionsmarkierung**</span><span class="sxs-lookup"><span data-stu-id="f88cc-195">**Transaction Mark**</span></span>|<span data-ttu-id="f88cc-196">Name der markierten Transaktion, der vom Benutzer zugewiesen wurde, als für die Transaktion der Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f88cc-196">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
        |<span data-ttu-id="f88cc-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="f88cc-197">**Date**</span></span>|<span data-ttu-id="f88cc-198">Datum und Uhrzeit, zu der für die Transaktion der Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f88cc-198">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="f88cc-199">Als Transaktionsdatum und -uhrzeit werden das Datum und die Uhrzeit angezeigt, die in der **msdbgmarkhistory** -Tabelle aufgezeichnet wurden, nicht das Datum und die Uhrzeit des Clientcomputers.</span><span class="sxs-lookup"><span data-stu-id="f88cc-199">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
        |<span data-ttu-id="f88cc-200">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f88cc-200">**Description**</span></span>|<span data-ttu-id="f88cc-201">Die Beschreibung der markierten Transaktion, die der Benutzer angegeben hat, als für die Transaktion ein Commit ausgeführt wurde (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="f88cc-201">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
        |<span data-ttu-id="f88cc-202">**LSN**</span><span class="sxs-lookup"><span data-stu-id="f88cc-202">**LSN**</span></span>|<span data-ttu-id="f88cc-203">Die Protokollfolgenummer (LSN, Log Sequence Number) der markierten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="f88cc-203">Log sequence number of the marked transaction.</span></span>|  
        |<span data-ttu-id="f88cc-204">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f88cc-204">**Database**</span></span>|<span data-ttu-id="f88cc-205">Der Name der Datenbank, in der für die markierte Transaktion ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f88cc-205">Name of the database where the marked transaction was committed.</span></span>|  
        |<span data-ttu-id="f88cc-206">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="f88cc-206">**User Name**</span></span>|<span data-ttu-id="f88cc-207">Der Name des Datenbankbenutzers, der für die markierte Transaktion ein Commit ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="f88cc-207">Name of the database user who committed the marked transaction.</span></span>|  
  
8.  <span data-ttu-id="f88cc-208">Zum Anzeigen oder Auswählen der erweiterten Optionen klicken Sie auf **Optionen** im Bereich **Seite auswählen** .</span><span class="sxs-lookup"><span data-stu-id="f88cc-208">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
9. <span data-ttu-id="f88cc-209">Im Abschnitt **Wiederherstellungsoptionen** stehen folgende Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f88cc-209">In the **Restore options** section, the choices are:</span></span>  
  
    -   <span data-ttu-id="f88cc-210">**Replikationseinstellungen beibehalten (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="f88cc-210">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
         <span data-ttu-id="f88cc-211">Behält die Replikationseinstellungen bei, wenn eine veröffentlichte Datenbank auf einem Server wiederhergestellt wird, auf dem die Datenbank nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f88cc-211">Preserves the replication settings when restoring a published database to a server other than the server where the database was created.</span></span>  
  
         <span data-ttu-id="f88cc-212">Diese Option ist nur in Verbindung mit der Option **Datenbank betriebsbereit belassen, indem für Transaktionen ohne Commit ein Rollback ausgeführt wird...** (wird weiter unten beschrieben) verfügbar. Dies entspricht der Wiederherstellung einer Sicherung mit der `RECOVERY` Option.</span><span class="sxs-lookup"><span data-stu-id="f88cc-212">This option is available only with the **Leave the database ready for use by rolling back the uncommitted transactions...** option (described later), which is equivalent to restoring a backup with the `RECOVERY` option.</span></span>  
  
         <span data-ttu-id="f88cc-213">Das Überprüfen dieser Option entspricht der Verwendung der- `KEEP_REPLICATION` Option in einer- [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-213">Checking this option is equivalent to using the `KEEP_REPLICATION` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
    -   <span data-ttu-id="f88cc-214">**Bestätigung vor Wiederherstellen jeder einzelnen Sicherung**</span><span class="sxs-lookup"><span data-stu-id="f88cc-214">**Prompt before restoring each backup**</span></span>  
  
         <span data-ttu-id="f88cc-215">Bei Auswahl dieser Option wird vor dem Wiederherstellen jedes Sicherungssatzes (nach dem ersten) das Dialogfeld **Wiederherstellung fortsetzen** angezeigt, in dem Sie angeben müssen, ob Sie die Wiederherstellungssequenz fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="f88cc-215">Before restoring each backup set (after the first), this option brings up the **Continue with Restore** dialog box, which asks you to indicate whether you want to continue the restore sequence.</span></span> <span data-ttu-id="f88cc-216">Das Dialogfeld enthält den Namen des nächsten Mediensatzes (sofern vorhanden), den Namen des Sicherungssatzes und die Beschreibung des Sicherungssatzes.</span><span class="sxs-lookup"><span data-stu-id="f88cc-216">This dialog displays the name of the next media set (if available), the backup set name, and backup set description.</span></span>  
  
         <span data-ttu-id="f88cc-217">Diese Option ist besonders dann hilfreich, wenn Sie für verschiedene Mediensätze Bänder austauschen müssen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-217">This option is particularly useful when you must swap tapes for different media sets.</span></span> <span data-ttu-id="f88cc-218">Sie können die Option beispielsweise dann verwenden, wenn der Server nur über ein Bandlaufwerk verfügt.</span><span class="sxs-lookup"><span data-stu-id="f88cc-218">For example, you can use it when the server has only one tape device.</span></span> <span data-ttu-id="f88cc-219">Klicken Sie erst auf **OK**, wenn Sie soweit sind, den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-219">Wait until you are ready to proceed before clicking **OK**.</span></span>  
  
         <span data-ttu-id="f88cc-220">Wenn Sie auf **Nein** klicken, verbleibt die Datenbank im Wiederherstellungsstatus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-220">Clicking **No** leaves the database in the restoring state.</span></span> <span data-ttu-id="f88cc-221">Sie können die Wiederherstellungssequenz nach der letzten abgeschlossenen Wiederherstellung fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-221">At your convenience, you can continue the restore sequence after the last restore that completed.</span></span> <span data-ttu-id="f88cc-222">Verwenden Sie den Task **Datenbank wiederherstellen** erneut, wenn die nächste Sicherung eine Datensicherung oder differenzielle Sicherung ist.</span><span class="sxs-lookup"><span data-stu-id="f88cc-222">If the next backup is a data or differential backup, use the **Restore Database** task again.</span></span> <span data-ttu-id="f88cc-223">Wenn die nächste Sicherung eine Protokollsicherung ist, verwenden Sie den Task **Transaktionsprotokoll wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="f88cc-223">If the next backup is a log backup, use the **Restore Transaction Log** task.</span></span>  
  
    -   <span data-ttu-id="f88cc-224">**Zugriff auf die wiederhergestellte Datenbank einschränken (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="f88cc-224">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
         <span data-ttu-id="f88cc-225">Macht die wiederhergestellte Datenbank nur Mitgliedern von **db_owner**, **dbcreator** oder **sysadmin**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f88cc-225">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
         <span data-ttu-id="f88cc-226">Das Aktivieren dieser Option ist gleichbedeutend mit der Verwendung der- `RESTRICTED_USER` Option in einer- [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-226">Checking this option is synonymous to using the `RESTRICTED_USER` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
10. <span data-ttu-id="f88cc-227">Geben Sie für die Optionen zum **Wiederherstellungsstatus** den Status der Datenbank nach dem Wiederherstellungsvorgang an.</span><span class="sxs-lookup"><span data-stu-id="f88cc-227">For the **Recovery state** options, specify the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="f88cc-228">**Belassen Sie die Datenbank betriebsbereit, indem für Transaktionen ohne Commit ein Rollback ausgeführt wird. Zusätzliche Transaktionsprotokolle können nicht wiederhergestellt werden. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="f88cc-228">**Leave the database ready for use by rolling back uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
  
         <span data-ttu-id="f88cc-229">Stellt die Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="f88cc-229">Recovers the database.</span></span> <span data-ttu-id="f88cc-230">Diese Option entspricht der- `RECOVERY` Option in einer- [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-230">This option is equivalent to the `RECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="f88cc-231">Wählen Sie diese Option nur dann aus, wenn Sie keine Protokolldateien besitzen, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f88cc-231">Choose this option only if you have no log files you want to restore.</span></span>  
  
    -   <span data-ttu-id="f88cc-232">**Belassen Sie die Datenbank nicht betriebsbereit, und führen Sie kein Rollback für Transaktionen ohne Commit aus. Zusätzliche Transaktionsprotokolle können wiederhergestellt werden. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="f88cc-232">**Leave the database non-operational, and do not roll back uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
  
         <span data-ttu-id="f88cc-233">Belässt die Datenbank im nicht wiederhergestellten Status `RESTORING`.</span><span class="sxs-lookup"><span data-stu-id="f88cc-233">Leaves the database unrecovered, in the `RESTORING` state.</span></span> <span data-ttu-id="f88cc-234">Diese Option entspricht der Verwendung der- `NORECOVERY` Option in einer- [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-234">This option is equivalent to using the `NORECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="f88cc-235">Wenn Sie diese Option auswählen, ist die Option **Replikationseinstellungen beibehalten** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f88cc-235">When you choose this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="f88cc-236">Aktivieren Sie diese Option stets bei einer Spiegelung oder sekundären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f88cc-236">For a mirror or secondary database, always select this option.</span></span>  
  
    -   <span data-ttu-id="f88cc-237">**Datenbank im schreibgeschützten Modus belassen. Transaktionen ohne Commit werden rückgängig gemacht, die Rückgängigaktionen werden jedoch in einer Datei gespeichert, sodass die Auswirkungen der Wiederherstellung umgekehrt werden können. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="f88cc-237">**Leave the database in read-only mode. Undo uncommitted transactions, but save the undo actions in a file so that recovery effects can be reversed. (RESTORE WITH STANDBY)**</span></span>  
  
         <span data-ttu-id="f88cc-238">Belässt die Datenbank in einem Standbystatus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-238">Leaves the database in a standby state.</span></span> <span data-ttu-id="f88cc-239">Diese Option entspricht der Verwendung der- `STANDBY` Option in einer- [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-239">This option is equivalent to using the `STANDBY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="f88cc-240">Bei Auswahl dieser Option müssen Sie eine Standbydatei angeben.</span><span class="sxs-lookup"><span data-stu-id="f88cc-240">Choosing this option requires that you specify a standby file.</span></span>  
  
11. <span data-ttu-id="f88cc-241">Geben Sie optional im Textfeld **Standbydatei** einen Dateinamen für die Standbydatei an.</span><span class="sxs-lookup"><span data-stu-id="f88cc-241">Optionally, specify a standby file name in the **Standby file** text box.</span></span> <span data-ttu-id="f88cc-242">Diese Option ist erforderlich, wenn Sie die Datenbank im schreibgeschützten Modus belassen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-242">This option is required if you leave the database in read-only mode.</span></span> <span data-ttu-id="f88cc-243">Sie können nach der Standbydatei suchen oder den Pfadnamen im Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="f88cc-243">You can browse for the standby file or type its pathname in the text box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f88cc-244">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f88cc-244">Using Transact-SQL</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f88cc-245">Es ist empfehlenswert, entweder WITH NORECOVERY oder WITH RECOVERY in jeder RESTORE-Anweisung immer explizit anzugeben, um Mehrdeutigkeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-245">We recommend that you always explicitly specify either WITH NORECOVERY or WITH RECOVERY in every RESTORE statement to eliminate ambiguity.</span></span> <span data-ttu-id="f88cc-246">Dies ist besonders beim Schreiben von Skripts wichtig.</span><span class="sxs-lookup"><span data-stu-id="f88cc-246">This is particularly important when writing scripts.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="f88cc-247">So stellen Sie eine Transaktionsprotokollsicherung wieder her</span><span class="sxs-lookup"><span data-stu-id="f88cc-247">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="f88cc-248">Führen Sie die RESTORE LOG-Anweisung aus, um die Transaktionsprotokollsicherung anzuwenden, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="f88cc-248">Execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="f88cc-249">Den Namen der Datenbank, auf die das zu sichernde Transaktionsprotokoll angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f88cc-249">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="f88cc-250">Das Sicherungsmedium, von dem die Transaktionsprotokollsicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f88cc-250">The backup device where the transaction log backup will be restored from.</span></span>  
  
    -   <span data-ttu-id="f88cc-251">Die NORECOVERY-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f88cc-251">The NORECOVERY clause.</span></span>  
  
     <span data-ttu-id="f88cc-252">Diese Anweisung weist die folgende Basissyntax auf:</span><span class="sxs-lookup"><span data-stu-id="f88cc-252">The basic syntax for this statement is as follows:</span></span>  
  
     <span data-ttu-id="f88cc-253">RESTORE LOG *Datenbankname* FROM <Sicherungsgerät> WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f88cc-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="f88cc-254">Dabei ist *Datenbankname* der Name der Datenbank und <Sicherungsgerät> der Name des Mediums, auf dem sich die wiederherzustellende Protokollsicherung befindet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-254">Where *database_name* is the name of database and <backup_device>is the name of the device that contains the log backup being restored.</span></span>  
  
2.  <span data-ttu-id="f88cc-255">Wiederholen Sie Schritt 1 für jede anzuwendende Transaktionsprotokollsicherung.</span><span class="sxs-lookup"><span data-stu-id="f88cc-255">Repeat step 1 for each transaction log backup you have to apply.</span></span>  
  
3.  <span data-ttu-id="f88cc-256">Verwenden Sie nach dem Wiederherstellen der letzten Sicherung in der Wiederherstellungssequenz die folgenden Anweisungen, um die Datenbank wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="f88cc-256">After restoring the last backup in your restore sequence, to recover the database use one of the following statements:</span></span>  
  
    -   <span data-ttu-id="f88cc-257">Wiederherstellen der Datenbank als Teil der letzten RESTORE LOG-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="f88cc-257">Recover the database as part of the last RESTORE LOG statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH RECOVERY;  
        GO  
        ```  
  
    -   <span data-ttu-id="f88cc-258">Warten, bis die Datenbank durch Verwendung einer getrennten RESTORE DATABASE-Anweisung wiederhergestellt wird:</span><span class="sxs-lookup"><span data-stu-id="f88cc-258">Wait to recover the database by using a separate RESTORE DATABASE statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH NORECOVERY;   
        RESTORE DATABASE <database_name> WITH RECOVERY;  
        GO  
        ```  
  
         <span data-ttu-id="f88cc-259">Das Warten mit der Wiederherstellung der Datenbank ermöglicht eine Überprüfung, ob alle erforderlichen Protokollsicherungen wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-259">Waiting to recover the database gives you the opportunity to verify that you have restored all of the necessary log backups.</span></span> <span data-ttu-id="f88cc-260">Diese Vorgehensweise ist oft ratsam, wenn Sie eine Wiederherstellung bis zu einem bestimmten Zeitpunkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="f88cc-260">This approach is often advisable when you are performing a point-in-time restore.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f88cc-261">Wenn Sie eine Spiegeldatenbank erstellen, lassen Sie den Wiederherstellungsschritt aus.</span><span class="sxs-lookup"><span data-stu-id="f88cc-261">If you are creating a mirror database, omit the recovery step.</span></span> <span data-ttu-id="f88cc-262">Eine Spiegeldatenbank muss im Status RESTORING verbleiben.</span><span class="sxs-lookup"><span data-stu-id="f88cc-262">A mirror database must remain in the RESTORING state.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="f88cc-263">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f88cc-263">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="f88cc-264">Standardmäßig verwendet die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank das einfache Wiederherstellungsmodell.</span><span class="sxs-lookup"><span data-stu-id="f88cc-264">By default, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="f88cc-265">Für die folgenden Beispiele ist es erforderlich, dass die Datenbank folgendermaßen für die Verwendung des vollständigen Wiederherstellungsmodells geändert wird:</span><span class="sxs-lookup"><span data-stu-id="f88cc-265">The following examples require modifying the database to use the full recovery model, as follows:</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
```  
  
#### <a name="a-applying-a-single-transaction-log-backup"></a><span data-ttu-id="f88cc-266">A.</span><span class="sxs-lookup"><span data-stu-id="f88cc-266">A.</span></span> <span data-ttu-id="f88cc-267">Anwenden einer einzelnen Transaktionsprotokollsicherung</span><span class="sxs-lookup"><span data-stu-id="f88cc-267">Applying a single transaction log backup</span></span>  
 <span data-ttu-id="f88cc-268">Im folgenden Beispiel wird mit der Wiederherstellung der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank mithilfe einer vollständigen Datenbanksicherung begonnen, die sich auf einem Sicherungsmedium mit dem Namen `AdventureWorks2012_1`befindet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-268">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="f88cc-269">Dann wird die erste Transaktionsprotokollsicherung angewendet, die sich auf einem Sicherungsmedium mit dem Namen `AdventureWorks2012_log`befindet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-269">The example then applies the first transaction log backup that resides on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="f88cc-270">Schließlich wird die Datenbank im Beispiel wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f88cc-270">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
#### <a name="b-applying-multiple-transaction-log-backups"></a><span data-ttu-id="f88cc-271">B.</span><span class="sxs-lookup"><span data-stu-id="f88cc-271">B.</span></span> <span data-ttu-id="f88cc-272">Anwenden mehrerer Transaktionsprotokollsicherungen</span><span class="sxs-lookup"><span data-stu-id="f88cc-272">Applying multiple transaction log backups</span></span>  
 <span data-ttu-id="f88cc-273">Im folgenden Beispiel wird mit der Wiederherstellung der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank mithilfe einer vollständigen Datenbanksicherung begonnen, die sich auf einem Sicherungsmedium mit dem Namen `AdventureWorks2012_1`befindet.</span><span class="sxs-lookup"><span data-stu-id="f88cc-273">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="f88cc-274">Dann werden nacheinander die ersten drei Transaktionsprotokollsicherungen angewendet, die sich auf einem Sicherungsmedium mit dem Namen `AdventureWorks2012_log`befinden.</span><span class="sxs-lookup"><span data-stu-id="f88cc-274">The example then applies, one by one, the first three transaction log backups that reside on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="f88cc-275">Schließlich wird die Datenbank im Beispiel wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f88cc-275">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 2,  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 3,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f88cc-276">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f88cc-276">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f88cc-277">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f88cc-277">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="f88cc-278">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f88cc-278">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="f88cc-279">Wiederherstellen einer Datenbank bis zum Fehlerzeitpunkt im vollständigen Wiederherstellungsmodell &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f88cc-279">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="f88cc-280">Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="f88cc-280">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="f88cc-281">Wiederherstellen einer Datenbank bis zu einer markierten Transaktion &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f88cc-281">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="f88cc-282">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f88cc-282">See Also</span></span>  
 <span data-ttu-id="f88cc-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f88cc-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="f88cc-284">Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f88cc-284">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  
