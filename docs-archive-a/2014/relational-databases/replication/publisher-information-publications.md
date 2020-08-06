---
title: Dialogfeld "Herausgeber Informationen" SQL Server-Replikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.publications.f1
ms.assetid: 0b2e3d4e-03b7-4c31-8f96-48648d750010
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3797ae4f9fe8f42b4abec715c63bc627c2a62cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697887"
---
# <a name="sql-server-replication-publisher-information-dialog-box"></a><span data-ttu-id="9cedc-102">Dialogfeld ' Verleger Informationen ' SQL Server-Replikation</span><span class="sxs-lookup"><span data-stu-id="9cedc-102">SQL Server Replication 'Publisher Information' dialog box</span></span>
  <span data-ttu-id="9cedc-103">Die Registerkarte **Veröffentlichungen** enthält Zusammenfassungsinformationen zu allen Veröffentlichungen auf dem Verleger, die Sie im linken Bereich ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="9cedc-103">The **Publications** tab provides summary information for all publications at the Publisher selected in the left pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9cedc-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9cedc-104">Options</span></span>  
 <span data-ttu-id="9cedc-105">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="9cedc-105">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="9cedc-106">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="9cedc-106">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="9cedc-107">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9cedc-107">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="9cedc-108">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="9cedc-108">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="9cedc-109">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="9cedc-109">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="9cedc-110">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="9cedc-110">Filter settings are specific to each grid.</span></span> <span data-ttu-id="9cedc-111">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="9cedc-111">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="9cedc-112">**Status**</span><span class="sxs-lookup"><span data-stu-id="9cedc-112">**Status**</span></span>  
 <span data-ttu-id="9cedc-113">Status der einzelnen Veröffentlichungen, der anhand des höchsten Prioritätsstatus der Abonnements bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="9cedc-113">The status of each publication, which is determined by the highest priority status of its subscriptions.</span></span> <span data-ttu-id="9cedc-114">Standardmäßig wird das Raster mit den Veröffentlichungsinformationen nach der **Status** -Spalte sortiert.</span><span class="sxs-lookup"><span data-stu-id="9cedc-114">By default, the grid containing publication information is sorted by the **Status** column.</span></span> <span data-ttu-id="9cedc-115">In der folgenden Liste werden die möglichen Statuswerte und ihre Sortierreihenfolge aufgeführt (Fehler werden z. B. immer oben im Raster angezeigt):</span><span class="sxs-lookup"><span data-stu-id="9cedc-115">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid):</span></span>  
  
-   <span data-ttu-id="9cedc-116">Fehler</span><span class="sxs-lookup"><span data-stu-id="9cedc-116">Error</span></span>  
  
-   <span data-ttu-id="9cedc-117">Leistung ist kritisch</span><span class="sxs-lookup"><span data-stu-id="9cedc-117">Performance critical</span></span>  
  
-   <span data-ttu-id="9cedc-118">fehlerhafter Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="9cedc-118">Retrying failed command</span></span>  
  
-   <span data-ttu-id="9cedc-119">OK</span><span class="sxs-lookup"><span data-stu-id="9cedc-119">OK</span></span>  
  
 <span data-ttu-id="9cedc-120">Der Statuswert **Leistungskritisch** ist für Transaktionsabonnements und für Mergeabonnements relevant. Er kann nur angezeigt werden, wenn ein Schwellenwert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9cedc-120">The status value **Performance critical** is relevant for transactional subscriptions and merge subscriptions; for transactional subscriptions, it can be displayed only if a threshold is set.</span></span> <span data-ttu-id="9cedc-121">Informationen zu Leistungsmessungen und zum Festlegen von Schwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md) und [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9cedc-121">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="9cedc-122">**Veröffentlichung**</span><span class="sxs-lookup"><span data-stu-id="9cedc-122">**Publication**</span></span>  
 <span data-ttu-id="9cedc-123">Der Name der jeweiligen Veröffentlichung im Format *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="9cedc-123">The name of each publication, in the form *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="9cedc-124">**Abonnements**</span><span class="sxs-lookup"><span data-stu-id="9cedc-124">**Subscriptions**</span></span>  
 <span data-ttu-id="9cedc-125">Die Anzahl der Abonnements pro Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="9cedc-125">The number of subscriptions for each publication.</span></span>  
  
 <span data-ttu-id="9cedc-126">**Wird synchronisiert**</span><span class="sxs-lookup"><span data-stu-id="9cedc-126">**Synchronizing**</span></span>  
 <span data-ttu-id="9cedc-127">Die Anzahl der Abonnements pro Veröffentlichung, die gerade synchronisiert werden:</span><span class="sxs-lookup"><span data-stu-id="9cedc-127">The number of subscriptions for each publication that are currently synchronizing:</span></span>  
  
-   <span data-ttu-id="9cedc-128">Bei Transaktionsreplikationen bedeutet "Wird synchronisiert", dass zwar der Verteilungs-Agent ausgeführt wird, aber nicht unbedingt Daten repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="9cedc-128">For transactional replication, "synchronizing" means that the Distribution Agent is running, but data is not necessarily being replicated.</span></span>  
  
-   <span data-ttu-id="9cedc-129">Bei Mergereplikationen bedeutet "Wird synchronisiert", dass der Merge-Agent ausgeführt wird und gerade Daten repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="9cedc-129">For merge replication, "synchronizing" means that the Merge Agent is running and that data is currently being replicated.</span></span>  
  
-   <span data-ttu-id="9cedc-130">Bei Momentaufnahmereplikationen bedeutet "Wird synchronisiert", dass der Verteilungs-Agent ausgeführt wird und gerade Daten repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="9cedc-130">For snapshot replication, "synchronizing" means that the Distribution Agent is running and that data is currently being replicated.</span></span>  
  
 <span data-ttu-id="9cedc-131">**Aktuelle Durchschnittsleistung** und **Die derzeit schlechteste Leistung**</span><span class="sxs-lookup"><span data-stu-id="9cedc-131">**Current Average Performance** and **Current Worst Performance**</span></span>  
 <span data-ttu-id="9cedc-132">Nur in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="9cedc-132">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="9cedc-133">Die Bewertung für die aktuelle Durchschnittsleistung und die Bewertung für die derzeit schlechteste Leistung gelten jeweils für alle Abonnements einer Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="9cedc-133">The average performance rating and the worst performance rating, respectively, for all subscriptions to a publication.</span></span> <span data-ttu-id="9cedc-134">Die Bewertungen basieren auf den neuesten Messungen des Replikationsmonitors und spiegeln nicht die Leistung eines Abonnements über einen längeren Zeitraum wider.</span><span class="sxs-lookup"><span data-stu-id="9cedc-134">Ratings are based on the most recent measurements taken by Replication Monitor and do not reflect the performance of a subscription over time.</span></span>  
  
 <span data-ttu-id="9cedc-135">Bei Transaktionsreplikationen zeigt der Replikationsmonitor einen Wert nur für Veröffentlichungen an, für die Leistungsschwellenwerte definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9cedc-135">For transactional replication, Replication Monitor displays a value only for publications that have performance thresholds defined.</span></span> <span data-ttu-id="9cedc-136">Sind für eine Veröffentlichung keine Leistungsschwellenwerte definiert, wird in dieser Spalte **Nicht aktiviert**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cedc-136">If performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="9cedc-137">Bei Mergereplikationen zeigt der Replikationsmonitor einen Wert an, nachdem fünf Synchronisierungen mit jeweils mindestens 50 Änderungen über denselben Verbindungstyp (DFÜ oder LAN) stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="9cedc-137">For merge replication, Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection (dial-up or LAN).</span></span> <span data-ttu-id="9cedc-138">Falls weniger als fünf Synchronisierungen mit mindestens 50 Änderungen stattgefunden haben, oder wenn die letzte Synchronisierung nicht mindestens 50 Änderungen umfasst hat, ist diese Spalte leer.</span><span class="sxs-lookup"><span data-stu-id="9cedc-138">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
 <span data-ttu-id="9cedc-139">Die folgenden Werte sind für die Leistungsbewertung möglich:</span><span class="sxs-lookup"><span data-stu-id="9cedc-139">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="9cedc-140">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="9cedc-140">Excellent</span></span>  
  
-   <span data-ttu-id="9cedc-141">Gut</span><span class="sxs-lookup"><span data-stu-id="9cedc-141">Good</span></span>  
  
-   <span data-ttu-id="9cedc-142">Durchschnittlich</span><span class="sxs-lookup"><span data-stu-id="9cedc-142">Fair</span></span>  
  
-   <span data-ttu-id="9cedc-143">Schlecht</span><span class="sxs-lookup"><span data-stu-id="9cedc-143">Poor</span></span>  
  
-   <span data-ttu-id="9cedc-144">Kritisch</span><span class="sxs-lookup"><span data-stu-id="9cedc-144">Critical</span></span>  
  
 <span data-ttu-id="9cedc-145">Weitere Informationen zur Definition von Leistungsbewertungen und zum Festlegen von Leistungsschwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9cedc-145">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cedc-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cedc-146">See Also</span></span>  
 <span data-ttu-id="9cedc-147">[Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9cedc-147">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="9cedc-148">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9cedc-148">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="9cedc-149">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="9cedc-149">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
