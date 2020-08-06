---
title: Medieninhalt (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617134"
---
# <a name="device-contents-sql-server"></a><span data-ttu-id="f991d-102">Medieninhalt (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f991d-102">Device Contents (SQL Server)</span></span>
  <span data-ttu-id="f991d-103">Mithilfe dieses Dialogfelds können Sie die Sicherungsinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f991d-103">Use this dialog box to view the backup information.</span></span> <span data-ttu-id="f991d-104">Diese Informationen beschreiben das Gerät, die Medien, den Mediensatz und den Sicherungssatz bzw. die Sicherungssätze.</span><span class="sxs-lookup"><span data-stu-id="f991d-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="f991d-105">**So verwenden Sie SQL Server Management Studio zum Anzeigen des Inhalts eines Sicherungsmediums**</span><span class="sxs-lookup"><span data-stu-id="f991d-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="f991d-106">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f991d-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="f991d-107">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f991d-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="f991d-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f991d-108">Options</span></span>  
 <span data-ttu-id="f991d-109">**Medien**</span><span class="sxs-lookup"><span data-stu-id="f991d-109">**Media**</span></span>  
 <span data-ttu-id="f991d-110">Ein Datenträger oder ein Satz von Bändern, auf dem Sicherungsinformationen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="f991d-110">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="f991d-111">**Mediensequenz**</span><span class="sxs-lookup"><span data-stu-id="f991d-111">**Media sequence**</span></span>  
 <span data-ttu-id="f991d-112">Führt die Mediensequenznummer, die Familiensequenznummer und ggf. den Spiegelbezeichner auf.</span><span class="sxs-lookup"><span data-stu-id="f991d-112">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="f991d-113">Die physischen Sicherungsmedien sind jeweils mit einer Mediensequenznummer gekennzeichnet, die die Reihenfolge angibt, in der die Medien verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f991d-113">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="f991d-114">Das erste Sicherungsmedium wird mit 1 markiert, das zweite Medium (das erste Anschlussband) mit 2 usw.</span><span class="sxs-lookup"><span data-stu-id="f991d-114">The initial backup medium is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="f991d-115">Beim Wiederherstellen des Sicherungssatzes stellen die Sequenznummern sicher, dass der Operator, der die Sicherung wiederherstellt, das richtige Medium in der richtigen Reihenfolge einlegt.</span><span class="sxs-lookup"><span data-stu-id="f991d-115">When the backup set is restored, the media sequence numbers ensure that the operator that restores the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="f991d-116">**Erstellt am**</span><span class="sxs-lookup"><span data-stu-id="f991d-116">**Created on**</span></span>  
 <span data-ttu-id="f991d-117">Zeigt das Erstellungsdatum des Mediums an.</span><span class="sxs-lookup"><span data-stu-id="f991d-117">Displays the media date.</span></span>  
  
 <span data-ttu-id="f991d-118">**Mediensatz**</span><span class="sxs-lookup"><span data-stu-id="f991d-118">**Media Set**</span></span>  
 <span data-ttu-id="f991d-119">Ein Mediensatz ist eine geordnete Sammlung von Sicherungsmedien, auf die mithilfe einer konstanten Anzahl von Sicherungsmedien ein oder mehrere Sicherungsvorgänge geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="f991d-119">A media set is an ordered collection of backup media to which one or more backup operations have written using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="f991d-120">**Name**</span><span class="sxs-lookup"><span data-stu-id="f991d-120">**Name**</span></span>  
 <span data-ttu-id="f991d-121">Zeigt den Namen des Mediensatzes an.</span><span class="sxs-lookup"><span data-stu-id="f991d-121">Displays the name of the media set.</span></span>  
  
 <span data-ttu-id="f991d-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f991d-122">**Description**</span></span>  
 <span data-ttu-id="f991d-123">Zeigt die Beschreibung des Mediensatzes an.</span><span class="sxs-lookup"><span data-stu-id="f991d-123">Displays the description media set.</span></span>  
  
 <span data-ttu-id="f991d-124">**Anzahl von Medienfamilien**</span><span class="sxs-lookup"><span data-stu-id="f991d-124">**Media family count**</span></span>  
 <span data-ttu-id="f991d-125">Zeigt die Anzahl der Medienfamilien an.</span><span class="sxs-lookup"><span data-stu-id="f991d-125">Displays the media family count.</span></span> <span data-ttu-id="f991d-126">Jeder Mediensatz ist eine Sammlung, die sich aus einer oder mehreren Medienfamilien zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="f991d-126">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="f991d-127">Die gesamte Ausgabe auf ein angegebenes einzelnes Sicherungsmedium (oder eine Gruppe gespiegelter Sicherungsmedien) bildet eine einzelne Medienfamilie.</span><span class="sxs-lookup"><span data-stu-id="f991d-127">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="f991d-128">Jeder Mediensatz enthält eine Medienfamilie pro separates Medium (oder Gruppe gespiegelter Medien). Wenn ein Mediensatz beispielsweise zwei nicht gespiegelte Sicherungsmedien verwendet, enthält der Mediensatz zwei Medienfamilien.</span><span class="sxs-lookup"><span data-stu-id="f991d-128">Each media set contains one media family per separate device (or group of mirrored devices); for example, if a media set uses two nonmirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="f991d-129">**Sicherungssätze**</span><span class="sxs-lookup"><span data-stu-id="f991d-129">**Backup sets**</span></span>  
 <span data-ttu-id="f991d-130">Zeigt Informationen zum Sicherungssatz bzw. den Sicherungssätzen an, der oder die auf dem Medium enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f991d-130">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="f991d-131">Ein Sicherungssatz ist das Ergebnis eines erfolgreichen Sicherungsvorgangs, dessen Inhalt auf die Medien im Satz von Sicherungsmedien verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="f991d-131">A backup set is the result of a successful backup operation whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="f991d-132">Header</span><span class="sxs-lookup"><span data-stu-id="f991d-132">Header</span></span>|<span data-ttu-id="f991d-133">Werte</span><span class="sxs-lookup"><span data-stu-id="f991d-133">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="f991d-134">**Name**</span><span class="sxs-lookup"><span data-stu-id="f991d-134">**Name**</span></span>|<span data-ttu-id="f991d-135">Name des Sicherungssatzes.</span><span class="sxs-lookup"><span data-stu-id="f991d-135">The name of the backup set.</span></span>|  
|<span data-ttu-id="f991d-136">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f991d-136">**Type**</span></span>|<span data-ttu-id="f991d-137">Der Typ des ausgeführten Sicherungsvorgangs: Vollständig, Differenziell oder Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="f991d-137">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="f991d-138">**Komponente**</span><span class="sxs-lookup"><span data-stu-id="f991d-138">**Component**</span></span>|<span data-ttu-id="f991d-139">Die gesicherte Komponente: Datenbank, Datei oder *\<blank>* (bei Transaktionsprotokollen).</span><span class="sxs-lookup"><span data-stu-id="f991d-139">The backed-up component: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="f991d-140">**Server**</span><span class="sxs-lookup"><span data-stu-id="f991d-140">**Server**</span></span>|<span data-ttu-id="f991d-141">Name der Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] , durch die der Sicherungsvorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f991d-141">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="f991d-142">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f991d-142">**Database**</span></span>|<span data-ttu-id="f991d-143">Name der Datenbank, die gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="f991d-143">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="f991d-144">**Position**</span><span class="sxs-lookup"><span data-stu-id="f991d-144">**Position**</span></span>|<span data-ttu-id="f991d-145">Position des Sicherungssatzes auf dem Volume.</span><span class="sxs-lookup"><span data-stu-id="f991d-145">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="f991d-146">**Date**</span><span class="sxs-lookup"><span data-stu-id="f991d-146">**Date**</span></span>|<span data-ttu-id="f991d-147">Datum und Uhrzeit des Endes des Sicherungsvorgangs, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="f991d-147">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="f991d-148">**Größe**</span><span class="sxs-lookup"><span data-stu-id="f991d-148">**Size**</span></span>|<span data-ttu-id="f991d-149">Größe des Sicherungssatzes in Byte.</span><span class="sxs-lookup"><span data-stu-id="f991d-149">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="f991d-150">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="f991d-150">**User Name**</span></span>|<span data-ttu-id="f991d-151">Name des Benutzers, der den Sicherungsvorgang ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="f991d-151">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="f991d-152">**Ablauf**</span><span class="sxs-lookup"><span data-stu-id="f991d-152">**Expiration**</span></span>|<span data-ttu-id="f991d-153">Datum und Uhrzeit des Zeitpunkts, an dem der Sicherungssatz verfällt.</span><span class="sxs-lookup"><span data-stu-id="f991d-153">The date and time the backup set expires.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f991d-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f991d-154">See Also</span></span>  
 [<span data-ttu-id="f991d-155">Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f991d-155">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
