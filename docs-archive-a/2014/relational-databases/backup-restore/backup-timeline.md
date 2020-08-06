---
title: Sicherungszeitachse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b075f8c9ec32cfe483c64e34e9f9b4e4b6e80e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622727"
---
# <a name="backup-timeline"></a><span data-ttu-id="a2a22-102">Sicherungszeitachse</span><span class="sxs-lookup"><span data-stu-id="a2a22-102">Backup Timeline</span></span>
  <span data-ttu-id="a2a22-103">Verwenden Sie das Dialogfeld **Sicherungszeitachse** , um Sicherungen zum Wiederherstellen einer Datenbank entsprechend einem bestimmten Zeitpunkt zu suchen und anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a2a22-103">Use the **Backup Timeline** dialog box to locate and specify backups to restore a database to a point-in-time.</span></span> <span data-ttu-id="a2a22-104">Auf das Dialogfeld **Sicherungszeitachse** greifen Sie zu, indem Sie im Bereich **Datenbank wiederherstellen (Seite „Allgemein“)** auf **Zeitachse** klicken.</span><span class="sxs-lookup"><span data-stu-id="a2a22-104">The **Backup Timeline** dialog box is accessed by clicking **Timeline** on the **Restore Database (General Page)** pane.</span></span> <span data-ttu-id="a2a22-105">In diesem Dialogfeld können Sie eine Zeitachse der für die Datenbank ausgeführten Wiederherstellungsvorgänge anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2a22-105">This dialog box allows you to view a timeline of the restore operations performed on the database.</span></span>  
  
 <span data-ttu-id="a2a22-106">Der Datenbankwiederherstellungsberater stellt sicher, dass nur Sicherungen ausgewählt werden, die für die Wiederherstellung auf diesen Zeitpunkt benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a2a22-106">The Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected.</span></span> <span data-ttu-id="a2a22-107">Die ausgewählten Sicherungen machen den empfohlenen Wiederherstellungsplan für die Wiederherstellung aus.</span><span class="sxs-lookup"><span data-stu-id="a2a22-107">These selected backups make up the recommended restore plan for your restore operation.</span></span> <span data-ttu-id="a2a22-108">Sie sollten nur die ausgewählten Sicherungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2a22-108">You should use only the selected backups.</span></span> <span data-ttu-id="a2a22-109">Informationen zum Datenbankwiederherstellungsberater finden Sie unter [Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a2a22-109">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
## <a name="restore-to"></a><span data-ttu-id="a2a22-110">Wiederherstellen in</span><span class="sxs-lookup"><span data-stu-id="a2a22-110">Restore to</span></span>  
 <span data-ttu-id="a2a22-111">Standardmäßig ist**Letzte Sicherung** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a2a22-111">**Last backup taken** is selected by default.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a2a22-112">wählt die entsprechenden Sicherungen zum Wiederherstellen der Datenbank aus und stellt die Datenbank entsprechend dem Zeitpunkt der letzten Sicherung wieder her.</span><span class="sxs-lookup"><span data-stu-id="a2a22-112">will select the appropriate backups to restore the database, and will restore the database to the point of the last backup.</span></span> <span data-ttu-id="a2a22-113">Klicken Sie auf **Bestimmtes Datum und bestimmte Uhrzeit** , um das Datum und die Uhrzeit manuell festzulegen (und so einen bestimmten Zeitpunkt auszuwählen).</span><span class="sxs-lookup"><span data-stu-id="a2a22-113">Click **A specific date and time** to manually set the date and time (selecting a specific point in time).</span></span>  
  
 <span data-ttu-id="a2a22-114">Mit**Bestimmtes Datum und bestimmte Uhrzeit** können Sie die Wiederherstellung zu einem bestimmten ausgewählten Datum und einer bestimmten Uhrzeit beenden.</span><span class="sxs-lookup"><span data-stu-id="a2a22-114">**Specific date and time** permits you stop the restore at a specific date and time that you select.</span></span> <span data-ttu-id="a2a22-115">Die Zeitachse zeigt die Sicherungsvorgänge in den 24 Stunden um das ausgewählte Datum und die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="a2a22-115">The timeline shows a representation of the backup operations performed in the 24 hours around the select date and time.</span></span>  
  
 <span data-ttu-id="a2a22-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="a2a22-116">**Date**</span></span>  
 <span data-ttu-id="a2a22-117">Wählen Sie in der Dropdownliste ein Datum aus, oder geben Sie ein Datum ein.</span><span class="sxs-lookup"><span data-stu-id="a2a22-117">Enter or select a date from the drop-down list.</span></span>  
  
 <span data-ttu-id="a2a22-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="a2a22-118">**Time**</span></span>  
 <span data-ttu-id="a2a22-119">Geben Sie ein Datum ein, oder wählen Sein ein Datum aus, um den bestimmten Zeitpunkt anzugeben, bis zu dem die Wiederherstellung durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2a22-119">Enter or select a date to designate the specific point-in-time for the restore to stop.</span></span>  
  
 <span data-ttu-id="a2a22-120">**Zeitachsenintervall**</span><span class="sxs-lookup"><span data-stu-id="a2a22-120">**Timeline Interval**</span></span>  
 <span data-ttu-id="a2a22-121">Zeigt die Optionen für die Intervalltypen an, die auf der Zeitachse angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="a2a22-121">Displays the options for the interval types viewable on the timeline.</span></span>  
  
## <a name="timeline-and-legend"></a><span data-ttu-id="a2a22-122">Zeitachse und Legende</span><span class="sxs-lookup"><span data-stu-id="a2a22-122">Timeline and Legend</span></span>  
 <span data-ttu-id="a2a22-123">Verwenden Sie die Bildlaufleiste unter der Zeitachse, um den Cursor auf der Zeitachse vorwärts und rückwärts zu bewegen.</span><span class="sxs-lookup"><span data-stu-id="a2a22-123">Use the scroll bar beneath the timeline to move the cursor forward and backward along the timeline.</span></span> <span data-ttu-id="a2a22-124">Klicken Sie auf eine Sicherung, um die Bildlaufleiste an das Ende dieser Sicherung zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a2a22-124">Click on a backup to move the scroll bar to the end of that backup.</span></span> <span data-ttu-id="a2a22-125">Zeigen Sie mit der Maus auf einen Marker, um eine QuickInfo mit Informationen zum ausgewählten Sicherungssatz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2a22-125">Hover the mouse over a marker to display a ScreenTip providing information about the selected backup set.</span></span> <span data-ttu-id="a2a22-126">Die Sicherungsinformationen werden mit den folgenden Markern auf der Zeitachse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a2a22-126">Backup information is shown on the timeline by the following markers.</span></span>  
  
 <span data-ttu-id="a2a22-127">Größeres Dreieck</span><span class="sxs-lookup"><span data-stu-id="a2a22-127">Larger triangle</span></span>  
 <span data-ttu-id="a2a22-128">Stellt die für die Datenbank ausgeführten vollständigen Sicherungen dar und bezeichnet den jeweiligen Ausführungszeitpunkt der einzelnen vollständigen Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="a2a22-128">Represents the full backups performed on the database, denoting the specific point in time each full backup was performed.</span></span>  
  
 <span data-ttu-id="a2a22-129">Kleineres Dreieck</span><span class="sxs-lookup"><span data-stu-id="a2a22-129">Smaller triangle</span></span>  
 <span data-ttu-id="a2a22-130">Stellt die für die Datenbank ausgeführten differenziellen Sicherungen dar und bezeichnet den jeweiligen Ausführungszeitpunkt der einzelnen differenziellen Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="a2a22-130">Represents the differential backups performed on the database, denoting the specific point in time that each differential backup was performed.</span></span>  
  
 <span data-ttu-id="a2a22-131">Grün schattierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="a2a22-131">Green shaded areas</span></span>  
 <span data-ttu-id="a2a22-132">Stellen den Sicherungsumfang des Transaktionsprotokolls dar.</span><span class="sxs-lookup"><span data-stu-id="a2a22-132">Represents the transaction log backup coverage.</span></span>  
  
 <span data-ttu-id="a2a22-133">Rote Linie</span><span class="sxs-lookup"><span data-stu-id="a2a22-133">Red line</span></span>  
 <span data-ttu-id="a2a22-134">Kann nur an Stellen auf der Zeitachse positioniert werden, für die eine Wiederherstellung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a2a22-134">Can only be positioned along the timeline where the restore is possible.</span></span> <span data-ttu-id="a2a22-135">Wenn Sie die rote Linie entlang der Zeitachse verschieben, werden die oben angezeigten Felder **Datum** und **Uhrzeit** angepasst.</span><span class="sxs-lookup"><span data-stu-id="a2a22-135">Moving the red line along the timeline adjusts the date and time displayed in the **Date** and **Time** boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a22-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2a22-136">See Also</span></span>  
 [<span data-ttu-id="a2a22-137">Datenbank wiederherstellen &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="a2a22-137">Restore Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
