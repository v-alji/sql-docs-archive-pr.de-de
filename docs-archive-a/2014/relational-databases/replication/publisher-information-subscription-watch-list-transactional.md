---
title: Verleger Informationen, Überwachungsliste für Abonnements (Transaktions Veröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.tran.f1
ms.assetid: 6bc64ddb-5c86-4681-a391-77fc1d3c4e6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bf6d151b75bca1dbfd2e5ad8f7601fb1002e84be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607642"
---
# <a name="publisher-information-subscription-watch-list-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="fa2c8-102">Verlegerinformationen, Überwachungsliste für Abonnements (Transaktionsveröffentlichung, SQL Server 2005 und später)</span><span class="sxs-lookup"><span data-stu-id="fa2c8-102">Publisher Information, Subscription Watch List (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="fa2c8-103">Die Registerkarte **Überwachungsliste für Abonnements** ist für Verteiler verfügbar, die SQL Server 2005 oder spätere Versionen ausführen. Sie ist dafür konzipiert, Informationen zu Abonnements von allen Veröffentlichungen anzuzeigen, die für den ausgewählten Verleger verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-103">The **Subscription Watch List** tab is available for Distributors running SQL Server 2005 and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="fa2c8-104">Sie können die Liste der Abonnements filtern, um Fehler, Warnungen und Abonnements mit schlechter Leistung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="fa2c8-105">Diese Registerkarte stellt einen einzelnen Speicherort für Administratoren bereit, um alle Replikationsaktivitäten bei einem Verleger zu überwachen: Der Replikationsmonitor zeigt alle Abonnements an, die Aufmerksamkeit erfordern. Grundlage hierfür ist der ausgewählte Replikationstyp und die im Dropdownlistenfeld **Anzeigen** ausgewählte Option.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="fa2c8-106">Da die auf dieser Registerkarte angezeigten Elemente auf den aktuellen Daten für Status und Leistung basieren, werden auf dieser Seite nur Abonnements angezeigt, die mit der Option im Listenfeld **Anzeigen** zum aktuellen Zeitpunkt übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa2c8-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fa2c8-107">Options</span></span>  
 <span data-ttu-id="fa2c8-108">Ausführliche Informationen und eine Liste der Aufträge für ein Abonnement können Sie anzeigen, indem Sie mit der rechten Maustaste in die Zeile des jeweiligen Abonnements klicken und eine Option im Kontextmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="fa2c8-109">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="fa2c8-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="fa2c8-110">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="fa2c8-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="fa2c8-111">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="fa2c8-112">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="fa2c8-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="fa2c8-113">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="fa2c8-114">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="fa2c8-115">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="fa2c8-116">**Transaktionsabonnements anzeigen**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-116">**Show Transactional Subscriptions**</span></span>  
 <span data-ttu-id="fa2c8-117">Wählen Sie den Typ der Abonnements (Transaktionsreplikation, Momentaufnahme oder Mergereplikation) aus, die für den ausgewählten Verleger angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="fa2c8-118">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-118">**Show**</span></span>  
 <span data-ttu-id="fa2c8-119">Wählen Sie die Abonnementstatus aus, die für Abonnements des ausgewählten Typs angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="fa2c8-120">Sie können z. B. auswählen, dass nur die Abonnements angezeigt werden, die einen Fehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="fa2c8-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-121">**Status**</span></span>  
 <span data-ttu-id="fa2c8-122">Der Status des jeweiligen Abonnements, der vom Status des Verteilungs-Agents bzw. Protokolllese-Agents bestimmt wird. (Es wird der Status mit der höheren Priorität angezeigt. Der Status kann auch durch den Warteschlangenlese-Agent bestimmt werden, wenn Abonnements mit verzögertem Update über eine Warteschlange verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="fa2c8-122">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="fa2c8-123">Standardmäßig wird das Raster mit den Abonnementinformationen nach den Werten in der **Status** -Spalte sortiert (bei Abonnements mit demselben Status wird nach den Werten unter **Leistung** sortiert).</span><span class="sxs-lookup"><span data-stu-id="fa2c8-123">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="fa2c8-124">In der folgenden Liste werden die möglichen Statuswerte und ihre Sortierreihenfolge aufgeführt (Fehler werden z. B. immer oben im Raster angezeigt).</span><span class="sxs-lookup"><span data-stu-id="fa2c8-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="fa2c8-125">Fehler</span><span class="sxs-lookup"><span data-stu-id="fa2c8-125">Error</span></span>  
  
-   <span data-ttu-id="fa2c8-126">Leistung ist kritisch</span><span class="sxs-lookup"><span data-stu-id="fa2c8-126">Performance critical</span></span>  
  
-   <span data-ttu-id="fa2c8-127">Läuft demnächst ab/Abgelaufen</span><span class="sxs-lookup"><span data-stu-id="fa2c8-127">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="fa2c8-128">Nicht initialisiertes Abonnement</span><span class="sxs-lookup"><span data-stu-id="fa2c8-128">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="fa2c8-129">fehlerhafter Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="fa2c8-129">Retrying failed command</span></span>  
  
-   <span data-ttu-id="fa2c8-130">Wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="fa2c8-130">Not Running</span></span>  
  
-   <span data-ttu-id="fa2c8-131">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="fa2c8-131">Running</span></span>  
  
 <span data-ttu-id="fa2c8-132">Die Sortierreihenfolge bestimmt auch, welcher Wert angezeigt wird, wenn ein Abonnement mehr als einen Statuswert aufweist.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-132">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="fa2c8-133">Wenn ein Abonnement z. B. einen Fehler aufweist und bald abläuft, dann wird in der **Status** -Spalte der Eintrag **Fehler**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-133">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="fa2c8-134">Die Statuswerte **Leistung ist kritisch**, **Läuft demnächst ab/Abgelaufen**und **Nicht initialisiertes Abonnement** stellen Warnungen dar.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-134">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="fa2c8-135">Wenn eine Warnung angezeigt wird, wird unter **Status** auch angezeigt, ob ein Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-135">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="fa2c8-136">Der Status kann also beispielsweise **Wird ausgeführt, Leistungskritisch**sein.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-136">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="fa2c8-137">Die Statuswerte **Leistung ist kritisch** und **Läuft demnächst ab/Abgelaufen** werden nur angezeigt, wenn Schwellenwerte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-137">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="fa2c8-138">Informationen zu Leistungsmessungen und zum Festlegen von Schwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md) und [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fa2c8-138">For information about performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="fa2c8-139">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-139">**Subscription**</span></span>  
 <span data-ttu-id="fa2c8-140">Der Name des jeweiligen Abonnements in folgendem Format: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-140">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="fa2c8-141">**Veröffentlichung**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-141">**Publication**</span></span>  
 <span data-ttu-id="fa2c8-142">Der Name der Veröffentlichung, mit der ein Abonnement synchronisiert wird, in folgendem Format: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-142">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="fa2c8-143">**Leistung**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-143">**Performance**</span></span>  
 <span data-ttu-id="fa2c8-144">Die Leistungsbewertung für jedes Abonnement basiert auf den neuesten Messungen, die vom Replikationsmonitor vorgenommen wurden, und reflektiert keinen Leistungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-144">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="fa2c8-145">Die Leistung wird für Abonnements von Veröffentlichungen gemessen, für die Leistungsschwellenwerte festgelegt sind. Wenn keine Leistungsschwellenwerte für eine Veröffentlichung festgelegt sind, wird in dieser Spalte **Nicht aktiviert**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-145">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="fa2c8-146">Die folgenden Werte sind für die Leistungsbewertung möglich:</span><span class="sxs-lookup"><span data-stu-id="fa2c8-146">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="fa2c8-147">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="fa2c8-147">Excellent</span></span>  
  
-   <span data-ttu-id="fa2c8-148">Gut</span><span class="sxs-lookup"><span data-stu-id="fa2c8-148">Good</span></span>  
  
-   <span data-ttu-id="fa2c8-149">Durchschnittlich</span><span class="sxs-lookup"><span data-stu-id="fa2c8-149">Fair</span></span>  
  
-   <span data-ttu-id="fa2c8-150">Schlecht</span><span class="sxs-lookup"><span data-stu-id="fa2c8-150">Poor</span></span>  
  
-   <span data-ttu-id="fa2c8-151">Kritisch</span><span class="sxs-lookup"><span data-stu-id="fa2c8-151">Critical</span></span>  
  
 <span data-ttu-id="fa2c8-152">Wenn die Leistung kritisch ist, wird **Leistungskritisch** in der **Status** -Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-152">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="fa2c8-153">Weitere Informationen zur Definition von Leistungsbewertungen und zum Festlegen von Leistungsschwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fa2c8-153">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="fa2c8-154">**Latenz**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-154">**Latency**</span></span>  
 <span data-ttu-id="fa2c8-155">Die durchschnittliche Zeit zwischen dem Ausführen eines Commits für eine Transaktion beim Verleger und der entsprechenden Ausführung des Commits für die Transaktion beim Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-155">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="fa2c8-156">Die angezeigte Latenzzeit basiert auf den neuesten Messungen des Replikationsmonitors.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-156">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="fa2c8-157">Weitere Informationen zur Messung von Latenzzeiten finden Sie unter [Messen der Latenzzeit und Überprüfen der Verbindungen bei Transaktionsreplikationen](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="fa2c8-157">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="fa2c8-158">**Letzte Synchronisierung**</span><span class="sxs-lookup"><span data-stu-id="fa2c8-158">**Last Synchronization**</span></span>  
 <span data-ttu-id="fa2c8-159">Der Zeitpunkt der letzten Ausführung des Verteilungs-Agents.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-159">The time when the Distribution Agent last ran.</span></span> <span data-ttu-id="fa2c8-160">Wenn eine Synchronisierung ausgeführt wird, wird **Vorgang wird ausgeführt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-160">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2c8-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa2c8-161">See Also</span></span>  
 <span data-ttu-id="fa2c8-162">[Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fa2c8-162">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="fa2c8-163">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fa2c8-163">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="fa2c8-164">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="fa2c8-164">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
