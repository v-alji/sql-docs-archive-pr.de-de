---
title: Sicherungsmedium (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.general.f1
ms.assetid: c557e37d-319e-4adb-a0c1-94189b15d2ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d73bdf3ce4b88214286b5f232924d811716a247e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609274"
---
# <a name="backup-device-general-page"></a><span data-ttu-id="ea4a6-102">Sicherungsmedium (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="ea4a6-102">Backup Device (General Page)</span></span>
  <span data-ttu-id="ea4a6-103">Auf der Seite **Allgemein** können Sie die allgemeinen Eigenschaften eines logischen Sicherungsmediums angeben oder anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-103">Use the **General** page to specify or view the general properties of a logical backup device.</span></span>  
  
 <span data-ttu-id="ea4a6-104">**So verwenden Sie SQL Server Management Studio zum Anzeigen des Inhalts eines Sicherungsmediums**</span><span class="sxs-lookup"><span data-stu-id="ea4a6-104">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="ea4a6-105">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-105">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-106">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-106">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="ea4a6-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ea4a6-107">Options</span></span>  
 <span data-ttu-id="ea4a6-108">**Mediumname**</span><span class="sxs-lookup"><span data-stu-id="ea4a6-108">**Device name**</span></span>  
 <span data-ttu-id="ea4a6-109">Hier können Sie den Namen eines vorhandenen logischen Sicherungsmediums anzeigen oder den Namen eines neuen logischen Sicherungsmediums angeben.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-109">View the name of an existing logical backup device or specify the name of a new logical backup device.</span></span>  
  
 <span data-ttu-id="ea4a6-110">**Band**</span><span class="sxs-lookup"><span data-stu-id="ea4a6-110">**Tape**</span></span>  
 <span data-ttu-id="ea4a6-111">In der Liste **Band** können Sie das Zielbandmedium anzeigen oder auswählen.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-111">View or select the destination tape device in the **Tape** list.</span></span> <span data-ttu-id="ea4a6-112">Diese Option ist nur verfügbar, wenn ein Bandlaufwerk mit dem Computer verbunden ist, auf dem die Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-112">This option is available only if a tape drive is attached to the computer that is running the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea4a6-113">Bandsicherungsmedien auf Remotecomputern sind keine gültigen Sicherungsziele.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-113">Tape backup devices on remote computers are not valid backup destinations.</span></span>  
  
 <span data-ttu-id="ea4a6-114">**File**</span><span class="sxs-lookup"><span data-stu-id="ea4a6-114">**File**</span></span>  
 <span data-ttu-id="ea4a6-115">Hier können Sie die Zieldatei eines vorhandenen logischen Sicherungsmediums anzeigen oder eine Zieldatei für ein neues logisches Sicherungsmedium angeben.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-115">View the destination file of an existing logical backup device, or specify a destination file for a new logical backup device.</span></span>  
  
-   <span data-ttu-id="ea4a6-116">Für ein vorhandenes logisches Sicherungsmedium wird der Pfad der Sicherungsdatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-116">For an existing logical backup device, the path of the backup file is displayed.</span></span> <span data-ttu-id="ea4a6-117">Das Feld **Datei** ist nicht bearbeitbar, und die Schaltfläche zum Durchsuchen ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-117">The **File** field is not editable, and the Browse button is unavailable.</span></span>  
  
-   <span data-ttu-id="ea4a6-118">Für ein neues logisches Sicherungsmedium müssen Sie den Pfad der Sicherungsdatei angeben, für die Sie das logische Sicherungsmedium definieren.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-118">For a new logical backup device, you must supply the path of the backup file for which you are defining the logical backup device.</span></span> <span data-ttu-id="ea4a6-119">Die Datei muss noch nicht vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-119">This file does not have to exist yet.</span></span>  
  
     <span data-ttu-id="ea4a6-120">Sie können auf die Schaltfläche zum Durchsuchen rechts vom Textfeld **Datei** klicken, um eine lokale Sicherungsdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-120">To specify a local backup file, you can click the Browse button to the right of the **File** text box.</span></span> <span data-ttu-id="ea4a6-121">Anschließend können Sie im Dialogfeld **Datenbankdateien suchen** zu jedem Ort auf jedem festen Laufwerk auf dem Computer navigieren, auf dem die Serverinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-121">Then, in the **Locate Database Files** dialog box, you can navigate to any location on any of the fixed drives on the computer running the server instance.</span></span> <span data-ttu-id="ea4a6-122">Wenn die Sicherungsdatei noch nicht vorhanden ist, müssen Sie den gewünschten Dateinamen im Feld **Dateiname** dieses Dialogfelds eingeben.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-122">If the backup file does not exist yet, you must enter the filename you want to use in the **File name** field of that dialog box.</span></span>  
  
     <span data-ttu-id="ea4a6-123">Alternativ können Sie das Feld **Datei** manuell bearbeiten, um den Standardpfad, den Standarddateinamen und die Standarderweiterung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-123">Alternatively, you can edit the **File** field manually to override the default path, file name, and extension.</span></span> <span data-ttu-id="ea4a6-124">Zum Angeben einer Remotedatei als Sicherungsziel geben Sie ihren vollqualifizierten UNC-Namen (Universal Naming Convention) ein.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-124">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="ea4a6-125">Weitere Informationen finden Sie unter [Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md)aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-125">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ea4a6-126">Beim Sichern von Daten über ein Netzwerk können Netzwerkfehler auftreten. Aus diesem Grund wird empfohlen, dass Sie den Sicherungsvorgang nach der Fertigstellung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-126">Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="ea4a6-127">Weitere Informationen finden Sie unter [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea4a6-127">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4a6-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ea4a6-128">Remarks</span></span>  
 <span data-ttu-id="ea4a6-129">Die Sicherungen auf einem Satz von einem oder mehreren Sicherungsmedien bilden einen einzelnen Mediensatz.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-129">The backups on a set of one or more backup devices compose a single media set.</span></span> <span data-ttu-id="ea4a6-130">Ein *Mediensatz* ist eine geordnete Auflistung von Sicherungsmedien, Bändern oder Dateien auf Datenträgern, die in mindestens einem Sicherungsvorgang mithilfe eines festen Typs sowie einer festen Anzahl von Sicherungsmedien beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-130">A *media set* is an ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span> <span data-ttu-id="ea4a6-131">Informationen über Mediensätze finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-131">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="ea4a6-132">Das einem logischen Sicherungsmedium entsprechende physische Sicherungsmedium wird initialisiert, wenn die erste Sicherung im Mediensatz auf das logische Sicherungsmedium geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-132">The physical backup device corresponding to a logical backup device is initialized when the first backup in the media set is written to the logical backup device.</span></span> <span data-ttu-id="ea4a6-133">Wenn das physische Sicherungsmedium eine noch nicht vorhandene Datei ist, wird sie jetzt erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea4a6-133">If the physical backup device is a file that does not exist yet, it is created at that time.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ea4a6-134">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ea4a6-134">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ea4a6-135">Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-135">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-136">Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-136">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-137">Angeben eines Datenträgers oder ein Bands als Sicherungsziel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-137">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-138">Löschen eines Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-138">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-139">Festlegen des Ablaufdatums für eine Sicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-139">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-140">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-140">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-141">Anzeigen der Daten und Protokolldateien in einem Sicherungssatz &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-141">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-142">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-142">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="ea4a6-143">Wiederherstellung einer Sicherung von einem Medium &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-143">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea4a6-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea4a6-144">See Also</span></span>  
 <span data-ttu-id="ea4a6-145">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ea4a6-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="ea4a6-146">Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea4a6-146">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
