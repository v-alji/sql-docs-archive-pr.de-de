---
title: Sicherungsmedium (Seite Medieninhalt) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 07204b5e05ce9fc17e6ea23450066f9f58b7cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618734"
---
# <a name="backup-device-media-contents-page"></a><span data-ttu-id="e5224-102">Sicherungsmedium (Seite Medieninhalt)</span><span class="sxs-lookup"><span data-stu-id="e5224-102">Backup Device (Media Contents Page)</span></span>
  <span data-ttu-id="e5224-103">Mithilfe des Dialogfelds **Sicherungsmedium** können Sie die Sicherungsinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5224-103">Use the **Backup Device** dialog box to view the backup information.</span></span> <span data-ttu-id="e5224-104">Diese Informationen beschreiben das Gerät, die Medien, den Mediensatz und den Sicherungssatz bzw. die Sicherungssätze.</span><span class="sxs-lookup"><span data-stu-id="e5224-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="e5224-105">**So verwenden Sie SQL Server Management Studio zum Anzeigen des Inhalts eines Sicherungsmediums**</span><span class="sxs-lookup"><span data-stu-id="e5224-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="e5224-106">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="e5224-107">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="e5224-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e5224-108">Options</span></span>  
 <span data-ttu-id="e5224-109">Zeigt Informationen zu den einzelnen Medien, zum Mediensatz und zu den Sicherungssätzen an.</span><span class="sxs-lookup"><span data-stu-id="e5224-109">View information about the individual media, media set, and backup sets.</span></span>  
  
 <span data-ttu-id="e5224-110">**Medien**</span><span class="sxs-lookup"><span data-stu-id="e5224-110">**Media**</span></span>  
 <span data-ttu-id="e5224-111">Ein Datenträger oder ein Satz von Bändern, auf dem Sicherungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e5224-111">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="e5224-112">**Mediensequenz**</span><span class="sxs-lookup"><span data-stu-id="e5224-112">**Media sequence**</span></span>  
 <span data-ttu-id="e5224-113">Führt die Mediensequenznummer, die Familiensequenznummer und ggf. den Spiegelbezeichner auf.</span><span class="sxs-lookup"><span data-stu-id="e5224-113">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="e5224-114">Die physischen Sicherungsmedien sind jeweils mit einer Mediensequenznummer gekennzeichnet, die die Reihenfolge angibt, in der die Medien verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e5224-114">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="e5224-115">Das erste Sicherungsmedium wird mit 1 markiert, das zweite Medium (das erste Anschlussband) mit 2 usw.</span><span class="sxs-lookup"><span data-stu-id="e5224-115">The initial backup media is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="e5224-116">Beim Wiederherstellen des Sicherungssatzes stellen die Sequenznummern sicher, dass der Operator, der die Sicherung wiederherstellt, das richtige Medium in der richtigen Reihenfolge einlegt.</span><span class="sxs-lookup"><span data-stu-id="e5224-116">When the backup set is restored, the media sequence numbers ensure that the operator restoring the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="e5224-117">**Erstellt am**</span><span class="sxs-lookup"><span data-stu-id="e5224-117">**Created on**</span></span>  
 <span data-ttu-id="e5224-118">Zeigt das Datum und die Uhrzeit der Erstellung des Mediensatzes an.</span><span class="sxs-lookup"><span data-stu-id="e5224-118">Displays the creation date and time of the media set.</span></span>  
  
 <span data-ttu-id="e5224-119">**Mediensatz**</span><span class="sxs-lookup"><span data-stu-id="e5224-119">**Media Set**</span></span>  
 <span data-ttu-id="e5224-120">Ein Mediensatz ist eine geordnete Sammlung von Sicherungsmedien, auf die mithilfe einer konstanten Anzahl von Sicherungsmedien ein oder mehrere Sicherungsvorgänge geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="e5224-120">A media set is an ordered collection of backup media to which one or more backup operations have written by using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="e5224-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="e5224-121">**Name**</span></span>  
 <span data-ttu-id="e5224-122">Zeigt ggf. den Namen des Mediensatzes an.</span><span class="sxs-lookup"><span data-stu-id="e5224-122">Displays the name of the media set, if any.</span></span>  
  
 <span data-ttu-id="e5224-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e5224-123">**Description**</span></span>  
 <span data-ttu-id="e5224-124">Zeigt ggf. die Beschreibung des Mediensatzes an.</span><span class="sxs-lookup"><span data-stu-id="e5224-124">Displays the description of the media set, if any.</span></span>  
  
 <span data-ttu-id="e5224-125">**Anzahl von Medienfamilien**</span><span class="sxs-lookup"><span data-stu-id="e5224-125">**Media family count**</span></span>  
 <span data-ttu-id="e5224-126">Zeigt die Anzahl von Medienfamilien im Mediensatz an.</span><span class="sxs-lookup"><span data-stu-id="e5224-126">Displays the number of families in the media set.</span></span> <span data-ttu-id="e5224-127">Jeder Mediensatz ist eine Sammlung, die sich aus einer oder mehreren Medienfamilien zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="e5224-127">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="e5224-128">Die gesamte Ausgabe auf ein angegebenes einzelnes Sicherungsmedium (oder eine Gruppe gespiegelter Sicherungsmedien) bildet eine einzelne Medienfamilie.</span><span class="sxs-lookup"><span data-stu-id="e5224-128">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="e5224-129">Jeder Mediensatz enthält eine Medienfamilie pro separates Medium (oder Gruppe gespiegelter Medien). Wenn ein Mediensatz beispielsweise zwei nicht gespiegelte Sicherungsmedien verwendet, enthält der Mediensatz zwei Medienfamilien.</span><span class="sxs-lookup"><span data-stu-id="e5224-129">Each media set contains one media family per separate device (or group of mirrored devices); for instance, if a media set uses two non-mirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="e5224-130">**Sicherungssätze**</span><span class="sxs-lookup"><span data-stu-id="e5224-130">**Backup sets**</span></span>  
 <span data-ttu-id="e5224-131">Zeigt Informationen zum Sicherungssatz bzw. den Sicherungssätzen an, der oder die auf dem Medium enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e5224-131">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="e5224-132">Ein Sicherungssatz ist das Ergebnis eines erfolgreichen Sicherungsvorgangs, dessen Inhalt auf die Medien im Satz von Sicherungsmedien verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="e5224-132">A backup set is the result of a successful backup operation, whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="e5224-133">Header</span><span class="sxs-lookup"><span data-stu-id="e5224-133">Header</span></span>|<span data-ttu-id="e5224-134">Werte</span><span class="sxs-lookup"><span data-stu-id="e5224-134">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="e5224-135">**Name**</span><span class="sxs-lookup"><span data-stu-id="e5224-135">**Name**</span></span>|<span data-ttu-id="e5224-136">Name des Sicherungssatzes.</span><span class="sxs-lookup"><span data-stu-id="e5224-136">The name of the backup set.</span></span>|  
|<span data-ttu-id="e5224-137">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e5224-137">**Type**</span></span>|<span data-ttu-id="e5224-138">Das gesicherte Objekt: Datenbank, Datei oder *\<blank>* (bei Transaktionsprotokollen).</span><span class="sxs-lookup"><span data-stu-id="e5224-138">The backed-up object: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="e5224-139">**Komponente**</span><span class="sxs-lookup"><span data-stu-id="e5224-139">**Component**</span></span>|<span data-ttu-id="e5224-140">Der Typ des ausgeführten Sicherungsvorgangs: Vollständig, Differenziell oder Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="e5224-140">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="e5224-141">**Server**</span><span class="sxs-lookup"><span data-stu-id="e5224-141">**Server**</span></span>|<span data-ttu-id="e5224-142">Name der Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] , durch die der Sicherungsvorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5224-142">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="e5224-143">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="e5224-143">**Database**</span></span>|<span data-ttu-id="e5224-144">Name der Datenbank, die gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="e5224-144">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="e5224-145">**Position**</span><span class="sxs-lookup"><span data-stu-id="e5224-145">**Position**</span></span>|<span data-ttu-id="e5224-146">Position des Sicherungssatzes auf dem Volume.</span><span class="sxs-lookup"><span data-stu-id="e5224-146">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="e5224-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="e5224-147">**Date**</span></span>|<span data-ttu-id="e5224-148">Datum und Uhrzeit des Endes des Sicherungsvorgangs, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="e5224-148">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="e5224-149">**Größe**</span><span class="sxs-lookup"><span data-stu-id="e5224-149">**Size**</span></span>|<span data-ttu-id="e5224-150">Größe des Sicherungssatzes in Byte.</span><span class="sxs-lookup"><span data-stu-id="e5224-150">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="e5224-151">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="e5224-151">**User Name**</span></span>|<span data-ttu-id="e5224-152">Name des Benutzers, der den Sicherungsvorgang ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="e5224-152">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="e5224-153">**Ablauf**</span><span class="sxs-lookup"><span data-stu-id="e5224-153">**Expiration**</span></span>|<span data-ttu-id="e5224-154">Datum und Uhrzeit des Zeitpunkts, an dem der Sicherungssatz verfällt.</span><span class="sxs-lookup"><span data-stu-id="e5224-154">The date and time the backup set expires.</span></span>|  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e5224-155">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e5224-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e5224-156">Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-156">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="e5224-157">Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-157">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="e5224-158">Angeben eines Datenträgers oder ein Bands als Sicherungsziel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-158">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="e5224-159">Löschen eines Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-159">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="e5224-160">Festlegen des Ablaufdatums für eine Sicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-160">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="e5224-161">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-161">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="e5224-162">Anzeigen der Daten und Protokolldateien in einem Sicherungssatz &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-162">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="e5224-163">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-163">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="e5224-164">Wiederherstellung einer Sicherung von einem Medium &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-164">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e5224-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5224-165">See Also</span></span>  
 <span data-ttu-id="e5224-166">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e5224-166">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="e5224-167">Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5224-167">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
