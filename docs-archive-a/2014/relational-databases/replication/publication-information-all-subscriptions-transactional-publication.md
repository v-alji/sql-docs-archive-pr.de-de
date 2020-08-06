---
title: 'Veröffentlichungsinformationen: Alle Abonnements (Transaktionsveröffentlichung) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.tran.f1
ms.assetid: 7073350c-f667-4f70-88e9-152c9a1b08dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccc34bbe0933f4558478bd1d8276898219016e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609828"
---
# <a name="publication-information-all-subscriptions-transactional-publication"></a><span data-ttu-id="e73c4-102">Veröffentlichungsinformationen: Alle Abonnements (Transaktionsveröffentlichung)</span><span class="sxs-lookup"><span data-stu-id="e73c4-102">Publication Information, All Subscriptions (Transactional Publication)</span></span>
  <span data-ttu-id="e73c4-103">Auf der Registerkarte **Alle Abonnements** werden Informationen zu allen Abonnements der ausgewählten Transaktionsveröffentlichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e73c4-103">The **All Subscriptions** tab displays information on all subscriptions to the selected transactional publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e73c4-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e73c4-104">Options</span></span>  
 <span data-ttu-id="e73c4-105">Ausführliche Informationen und eine Liste der Aufträge für ein Abonnement können Sie anzeigen, indem Sie mit der rechten Maustaste in die Zeile des jeweiligen Abonnements klicken und eine Option im Kontextmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="e73c4-106">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="e73c4-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="e73c4-107">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="e73c4-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="e73c4-108">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="e73c4-109">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="e73c4-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="e73c4-110">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="e73c4-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="e73c4-111">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="e73c4-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="e73c4-112">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="e73c4-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="e73c4-113">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="e73c4-113">**Show**</span></span>  
 <span data-ttu-id="e73c4-114">Nur in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="e73c4-115">Wählen Sie die Abonnementstatus aus, die für Abonnements des ausgewählten Typs angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="e73c4-116">Sie können z. B. auswählen, dass nur die Abonnements angezeigt werden, die einen Fehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="e73c4-117">**Status**</span><span class="sxs-lookup"><span data-stu-id="e73c4-117">**Status**</span></span>  
 <span data-ttu-id="e73c4-118">Der Status des jeweiligen Abonnements, der vom Status des Verteilungs-Agents bzw. Protokolllese-Agents bestimmt wird. (Es wird der Status mit der höheren Priorität angezeigt. Der Status kann auch durch den Warteschlangenlese-Agent bestimmt werden, wenn Abonnements mit verzögertem Update über eine Warteschlange verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="e73c4-118">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="e73c4-119">Standardmäßig wird das Raster mit den Abonnementinformationen nach den Werten in der **Status** -Spalte sortiert (bei Abonnements mit demselben Status wird nach den Werten unter **Leistung** sortiert).</span><span class="sxs-lookup"><span data-stu-id="e73c4-119">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="e73c4-120">In der folgenden Liste werden die möglichen Statuswerte und ihre Sortierreihenfolge aufgeführt (Fehler werden z. B. immer oben im Raster angezeigt).</span><span class="sxs-lookup"><span data-stu-id="e73c4-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="e73c4-121">Fehler</span><span class="sxs-lookup"><span data-stu-id="e73c4-121">Error</span></span>  
  
-   <span data-ttu-id="e73c4-122">Leistung ist kritisch (nur in[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen)</span><span class="sxs-lookup"><span data-stu-id="e73c4-122">Performance critical ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="e73c4-123">Läuft demnächst ab/Abgelaufen (nur in[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen)</span><span class="sxs-lookup"><span data-stu-id="e73c4-123">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="e73c4-124">Nicht initialisiertes Abonnement (nur in[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen)</span><span class="sxs-lookup"><span data-stu-id="e73c4-124">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="e73c4-125">fehlerhafter Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="e73c4-125">Retrying failed command</span></span>  
  
-   <span data-ttu-id="e73c4-126">Wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="e73c4-126">Not Running</span></span>  
  
-   <span data-ttu-id="e73c4-127">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="e73c4-127">Running</span></span>  
  
 <span data-ttu-id="e73c4-128">Die Sortierreihenfolge bestimmt auch, welcher Wert angezeigt wird, wenn ein Abonnement mehr als einen Statuswert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e73c4-128">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="e73c4-129">Wenn ein Abonnement z. B. einen Fehler aufweist und bald abläuft, dann wird in der **Status** -Spalte der Eintrag **Fehler**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e73c4-129">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="e73c4-130">Die Statuswerte **Leistung ist kritisch**, **Läuft demnächst ab/Abgelaufen**und **Nicht initialisiertes Abonnement** stellen Warnungen dar.</span><span class="sxs-lookup"><span data-stu-id="e73c4-130">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="e73c4-131">Wenn eine Warnung angezeigt wird, wird unter **Status** auch angezeigt, ob ein Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e73c4-131">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="e73c4-132">Der Status kann also beispielsweise **Wird ausgeführt, Leistungskritisch**sein.</span><span class="sxs-lookup"><span data-stu-id="e73c4-132">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="e73c4-133">Die Statuswerte **Leistung ist kritisch** und **Läuft demnächst ab/Abgelaufen** werden nur angezeigt, wenn Schwellenwerte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e73c4-133">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="e73c4-134">Informationen zu Leistungsmessungen und zum Festlegen von Schwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md) und [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="e73c4-134">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="e73c4-135">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="e73c4-135">**Subscription**</span></span>  
 <span data-ttu-id="e73c4-136">Der Name des jeweiligen Abonnements in folgendem Format: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="e73c4-136">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="e73c4-137">**Leistung**</span><span class="sxs-lookup"><span data-stu-id="e73c4-137">**Performance**</span></span>  
 <span data-ttu-id="e73c4-138">Nur in[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="e73c4-139">Die Leistungsbewertung für jedes Abonnement basiert auf den neuesten Messungen, die vom Replikationsmonitor vorgenommen wurden, und reflektiert keinen Leistungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="e73c4-139">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="e73c4-140">Die Leistung wird für Abonnements von Veröffentlichungen gemessen, für die Leistungsschwellenwerte festgelegt sind. Wenn keine Leistungsschwellenwerte für eine Veröffentlichung festgelegt sind, wird in dieser Spalte **Nicht aktiviert**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e73c4-140">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="e73c4-141">Die folgenden Werte sind für die Leistungsbewertung möglich:</span><span class="sxs-lookup"><span data-stu-id="e73c4-141">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="e73c4-142">Ausgezeichnet</span><span class="sxs-lookup"><span data-stu-id="e73c4-142">Excellent</span></span>  
  
-   <span data-ttu-id="e73c4-143">Gut</span><span class="sxs-lookup"><span data-stu-id="e73c4-143">Good</span></span>  
  
-   <span data-ttu-id="e73c4-144">Mittelmäßig</span><span class="sxs-lookup"><span data-stu-id="e73c4-144">Fair</span></span>  
  
-   <span data-ttu-id="e73c4-145">Schlecht</span><span class="sxs-lookup"><span data-stu-id="e73c4-145">Poor</span></span>  
  
-   <span data-ttu-id="e73c4-146">Kritisch</span><span class="sxs-lookup"><span data-stu-id="e73c4-146">Critical</span></span>  
  
 <span data-ttu-id="e73c4-147">Wenn die Leistung kritisch ist, wird **Leistungskritisch** in der **Status** -Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e73c4-147">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="e73c4-148">Weitere Informationen zur Definition von Leistungsbewertungen und zum Festlegen von Leistungsschwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="e73c4-148">For more information on how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="e73c4-149">**Latenz**</span><span class="sxs-lookup"><span data-stu-id="e73c4-149">**Latency**</span></span>  
 <span data-ttu-id="e73c4-150">Nur in[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="e73c4-150">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="e73c4-151">Die durchschnittliche Zeit zwischen dem Ausführen eines Commits für eine Transaktion beim Verleger und der entsprechenden Ausführung des Commits für die Transaktion beim Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="e73c4-151">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="e73c4-152">Die angezeigte Latenzzeit basiert auf den neuesten Messungen des Replikationsmonitors.</span><span class="sxs-lookup"><span data-stu-id="e73c4-152">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="e73c4-153">Weitere Informationen zur Messung von Latenzzeiten finden Sie unter [Messen der Latenzzeit und Überprüfen der Verbindungen bei Transaktionsreplikationen](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e73c4-153">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73c4-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e73c4-154">See Also</span></span>  
 <span data-ttu-id="e73c4-155">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e73c4-155">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="e73c4-156">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e73c4-156">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="e73c4-157">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="e73c4-157">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
