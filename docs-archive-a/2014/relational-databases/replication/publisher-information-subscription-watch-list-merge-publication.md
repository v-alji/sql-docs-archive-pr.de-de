---
title: Verleger Informationen, Überwachungsliste für Abonnements (Mergeveröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.merge.f1
ms.assetid: 4ec956bf-5cef-4377-a1d1-8c7f0107a6cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cd38540533e3e663fa23eee2c651f0beb9463546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721283"
---
# <a name="publisher-information-subscription-watch-list-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="1be88-102">Verlegerinformationen, Überwachungsliste für Abonnements (Mergeveröffentlichung, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="1be88-102">Publisher Information, Subscription Watch List (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="1be88-103"> Die Registerkarte **Überwachungsliste für Abonnements** ist für Verteiler verfügbar, auf denen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höhere Versionen ausgeführt werden. Sie ist dafür konzipiert, Informationen zu Abonnements von allen Veröffentlichungen anzuzeigen, die für den ausgewählten Verleger verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1be88-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="1be88-104">Sie können die Liste der Abonnements filtern, um Fehler, Warnungen und Abonnements mit schlechter Leistung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1be88-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="1be88-105">Diese Registerkarte stellt einen einzelnen Speicherort für Administratoren bereit, um alle Replikationsaktivitäten bei einem Verleger zu überwachen: Der Replikationsmonitor zeigt alle Abonnements an, die Aufmerksamkeit erfordern. Grundlage hierfür ist der ausgewählte Replikationstyp und die im Dropdownlistenfeld **Anzeigen** ausgewählte Option.</span><span class="sxs-lookup"><span data-stu-id="1be88-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="1be88-106">Da die auf dieser Registerkarte angezeigten Elemente auf den aktuellen Daten für Status und Leistung basieren, werden auf dieser Seite nur Abonnements angezeigt, die mit der Option im Listenfeld **Anzeigen** zum aktuellen Zeitpunkt übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1be88-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1be88-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1be88-107">Options</span></span>  
 <span data-ttu-id="1be88-108">Ausführliche Informationen und eine Liste der Aufträge für ein Abonnement können Sie anzeigen, indem Sie mit der rechten Maustaste in die Zeile des jeweiligen Abonnements klicken und eine Option im Kontextmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="1be88-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="1be88-109">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="1be88-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="1be88-110">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="1be88-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="1be88-111">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1be88-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="1be88-112">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="1be88-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="1be88-113">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="1be88-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="1be88-114">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="1be88-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="1be88-115">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="1be88-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="1be88-116">**Mergeabonnements anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1be88-116">**Show Merge Subscriptions**</span></span>  
 <span data-ttu-id="1be88-117">Wählen Sie den Typ der Abonnements (Transaktionsreplikation, Momentaufnahme oder Mergereplikation) aus, die für den ausgewählten Verleger angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1be88-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="1be88-118">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1be88-118">**Show**</span></span>  
 <span data-ttu-id="1be88-119">Wählen Sie die Abonnementstatus aus, die für Abonnements des ausgewählten Typs angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1be88-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="1be88-120">Sie können z. B. auswählen, dass nur die Abonnements angezeigt werden, die einen Fehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1be88-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="1be88-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="1be88-121">**Status**</span></span>  
 <span data-ttu-id="1be88-122">Der Status der einzelnen Abonnements, der durch den Status des Merge-Agents bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="1be88-122">The status of each subscription, which is determined by the status of the Merge Agent.</span></span>  
  
 <span data-ttu-id="1be88-123">Standardmäßig wird das Raster mit den Abonnementinformationen nach den Werten in der **Status** -Spalte sortiert (bei Abonnements mit demselben Status wird nach den Werten unter **Leistung** sortiert).</span><span class="sxs-lookup"><span data-stu-id="1be88-123">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="1be88-124">In der folgenden Liste werden die möglichen Statuswerte und ihre Sortierreihenfolge aufgeführt (Fehler werden z. B. immer oben im Raster angezeigt).</span><span class="sxs-lookup"><span data-stu-id="1be88-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="1be88-125">Fehler</span><span class="sxs-lookup"><span data-stu-id="1be88-125">Error</span></span>  
  
-   <span data-ttu-id="1be88-126">Leistung ist kritisch</span><span class="sxs-lookup"><span data-stu-id="1be88-126">Performance critical</span></span>  
  
-   <span data-ttu-id="1be88-127">Langer Mergevorgang</span><span class="sxs-lookup"><span data-stu-id="1be88-127">Long-running merge</span></span>  
  
-   <span data-ttu-id="1be88-128">Läuft demnächst ab/Abgelaufen</span><span class="sxs-lookup"><span data-stu-id="1be88-128">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="1be88-129">Nicht initialisiertes Abonnement</span><span class="sxs-lookup"><span data-stu-id="1be88-129">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="1be88-130">fehlerhafter Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="1be88-130">Retrying failed command</span></span>  
  
-   <span data-ttu-id="1be88-131">Wird synchronisiert</span><span class="sxs-lookup"><span data-stu-id="1be88-131">Synchronizing</span></span>  
  
-   <span data-ttu-id="1be88-132">Synchronisierung wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="1be88-132">Not synchronizing</span></span>  
  
 <span data-ttu-id="1be88-133">Die Sortierreihenfolge bestimmt auch, welcher Wert angezeigt wird, wenn ein Abonnement mehr als einen Statuswert aufweist.</span><span class="sxs-lookup"><span data-stu-id="1be88-133">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="1be88-134">Wenn ein Abonnement z. B. einen Fehler aufweist und bald abläuft, dann wird in der **Status** -Spalte der Eintrag **Fehler**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1be88-134">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="1be88-135">Die Statuswerte **Leistung ist kritisch**, **Langer Mergevorgang**, **Läuft demnächst ab/Abgelaufen**und **Nicht initialisiertes Abonnement** stellen Warnungen dar.</span><span class="sxs-lookup"><span data-stu-id="1be88-135">The status values **Performance critical**, **Long-running merge**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="1be88-136">Wenn eine Warnung angezeigt wird, wird unter **Status** auch angezeigt, ob ein Agent synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1be88-136">When a warning is displayed, the **Status** column also displays if an agent is synchronizing.</span></span> <span data-ttu-id="1be88-137">Der Status kann also beispielsweise **Wird synchronisiert, Leistungskritisch**sein.</span><span class="sxs-lookup"><span data-stu-id="1be88-137">For example, the status could be **Synchronizing, Performance critical**.</span></span>  
  
 <span data-ttu-id="1be88-138">Die Statuswerte **Läuft demnächst ab/Abgelaufen** und **Langer Mergevorgang** können nur angezeigt werden, wenn Schwellenwerte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1be88-138">The status values **Expiring soon/Expired** and **Long-running merge** can be displayed only if thresholds are set.</span></span> <span data-ttu-id="1be88-139">Der Statuswert **Leistung ist kritisch** kann nur angezeigt werden, nachdem fünf Synchronisierungen mit demselben Verbindungstyp (DFÜ oder LAN) stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="1be88-139">The status value **Performance critical** can be displayed only after five synchronizations of subscriptions with the same connection type (dial-up or LAN).</span></span> <span data-ttu-id="1be88-140">Informationen zu Leistungsmessungen und zum Festlegen von Schwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md) und [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="1be88-140">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="1be88-141">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="1be88-141">**Subscription**</span></span>  
 <span data-ttu-id="1be88-142">Der Name des jeweiligen Abonnements in folgendem Format:*SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="1be88-142">The name of each subscription, in the form:*SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="1be88-143">**Anzeigename**</span><span class="sxs-lookup"><span data-stu-id="1be88-143">**Friendly Name**</span></span>  
 <span data-ttu-id="1be88-144">Die Beschreibung der einzelnen Abonnements.</span><span class="sxs-lookup"><span data-stu-id="1be88-144">The description of each subscription.</span></span> <span data-ttu-id="1be88-145">Die Beschreibung wird im Dialogfeld **Abonnementeigenschaften** eingegeben oder mit dem **@description** -Parameter von [sp_addmergesubscription](/sql/relational-databases/system-stored-procedures/sp-addmergesubscription-transact-sql) oder [sp_addmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-transact-sql)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1be88-145">The description is entered in the **Subscription Properties** dialog box or specified with the **@description** parameter of [sp_addmergesubscription](/sql/relational-databases/system-stored-procedures/sp-addmergesubscription-transact-sql) or [sp_addmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="1be88-146">Benutzer verwenden die Beschreibung häufig als Anzeigename oder Spitzname des Abonnements.</span><span class="sxs-lookup"><span data-stu-id="1be88-146">Users often use the description as a "friendly name" or nickname for the subscription.</span></span>  
  
 <span data-ttu-id="1be88-147">**Veröffentlichung**</span><span class="sxs-lookup"><span data-stu-id="1be88-147">**Publication**</span></span>  
 <span data-ttu-id="1be88-148">Der Name der Veröffentlichung, mit der ein Abonnement synchronisiert wird, in folgendem Format: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="1be88-148">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="1be88-149">**Leistung**</span><span class="sxs-lookup"><span data-stu-id="1be88-149">**Performance**</span></span>  
 <span data-ttu-id="1be88-150">Die Leistungsbewertung für die einzelnen Abonnements auf der Grundlage der neuesten Messungen der Übermittlungsrate mithilfe des Replikationsmonitors.</span><span class="sxs-lookup"><span data-stu-id="1be88-150">The performance rating for each subscription, based on the most recent measurements of delivery rate taken by Replication Monitor.</span></span> <span data-ttu-id="1be88-151">Die Bewertung wird bestimmt, indem die Leistung der einzelnen Abonnements mit der durchschnittlichen bisherigen Leistung der Veröffentlichungsabonnements mit dem gleichen Verbindungstyp (DFÜ oder LAN) verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="1be88-151">The rating is determined by comparing individual subscription performance to the average historical performance of subscriptions to the publication that have the same connection type (dial-up or LAN).</span></span> <span data-ttu-id="1be88-152">Der Replikationsmonitor zeigt einen Wert an, nachdem fünf Synchronisierungen mit jeweils mindestens 50 Änderungen über denselben Verbindungstyp stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="1be88-152">Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection.</span></span> <span data-ttu-id="1be88-153">Falls weniger als fünf Synchronisierungen mit mindestens 50 Änderungen stattgefunden haben, oder wenn die letzte Synchronisierung nicht mindestens 50 Änderungen umfasst hat, ist diese Spalte leer.</span><span class="sxs-lookup"><span data-stu-id="1be88-153">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1be88-154">Die Leistung basiert auf dem in der **Verbindung** -Spalte angezeigten Verbindungstyp. Deshalb ist es möglich, dass für ein Abonnement mit einer geringeren Übermittlungsrate eine bessere Leistungsbewertung angezeigt wird, als für ein anderes Abonnement, wenn das erste Abonnement über eine langsamere Verbindung synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1be88-154">Performance is based on the connection type displayed in the **Connection** column; therefore it is possible for a subscription with a lower delivery rate to display a better performance rating than another subscription if the first subscription is synchronized over a slower connection.</span></span>  
  
 <span data-ttu-id="1be88-155">Die folgenden Werte sind für die Leistungsbewertung möglich:</span><span class="sxs-lookup"><span data-stu-id="1be88-155">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="1be88-156">Ausgezeichnet</span><span class="sxs-lookup"><span data-stu-id="1be88-156">Excellent</span></span>  
  
-   <span data-ttu-id="1be88-157">Gut</span><span class="sxs-lookup"><span data-stu-id="1be88-157">Good</span></span>  
  
-   <span data-ttu-id="1be88-158">Mittelmäßig</span><span class="sxs-lookup"><span data-stu-id="1be88-158">Fair</span></span>  
  
-   <span data-ttu-id="1be88-159">Schlecht</span><span class="sxs-lookup"><span data-stu-id="1be88-159">Poor</span></span>  
  
 <span data-ttu-id="1be88-160">Weitere Informationen zur Definition von Leistungsbewertungen und zum Festlegen von Leistungsschwellenwerten finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="1be88-160">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="1be88-161">**Übermittlungsrate**</span><span class="sxs-lookup"><span data-stu-id="1be88-161">**Delivery Rate**</span></span>  
 <span data-ttu-id="1be88-162">Die Anzahl an Zeilen, die pro Sekunde vom Merge-Agent verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1be88-162">The number of rows per second processed by the Merge Agent.</span></span>  
  
 <span data-ttu-id="1be88-163">**Letzte Synchronisierung**</span><span class="sxs-lookup"><span data-stu-id="1be88-163">**Last Synchronization**</span></span>  
 <span data-ttu-id="1be88-164">Der Zeitpunkt der letzten Ausführung von Merge-Agent.</span><span class="sxs-lookup"><span data-stu-id="1be88-164">The time at which the Merge Agent last ran.</span></span> <span data-ttu-id="1be88-165">Während dieser Synchronisierung können Änderungen verarbeitet worden sein oder nicht.</span><span class="sxs-lookup"><span data-stu-id="1be88-165">Changes may or may not have been processed during this synchronization.</span></span> <span data-ttu-id="1be88-166">Wenn sich eine Synchronisierung in Bearbeitung befindet, wird ein vollständiger Prozentwert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1be88-166">If synchronization is in progress, a percentage complete value is displayed.</span></span>  
  
 <span data-ttu-id="1be88-167">**Duration**</span><span class="sxs-lookup"><span data-stu-id="1be88-167">**Duration**</span></span>  
 <span data-ttu-id="1be88-168">Der Zeitraum der Ausführung von Merge-Agent während der letzten Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="1be88-168">The amount of time the Merge Agent has run during the last synchronization.</span></span> <span data-ttu-id="1be88-169">Dieser Wert gibt entweder die verstrichene Zeit eines zurzeit synchronisierten Merge-Agents oder die Gesamtzeit des zuvor synchronisierten Merge-Agents an.</span><span class="sxs-lookup"><span data-stu-id="1be88-169">The time represents elapsed time if the Merge Agent is currently synchronizing and total time if the Merge Agent has synchronized previously.</span></span>  
  
 <span data-ttu-id="1be88-170">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1be88-170">**Connection**</span></span>  
 <span data-ttu-id="1be88-171">Die Art der Verbindung zwischen dem Abonnenten und dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="1be88-171">The type of connection between the Subscriber and the Publisher.</span></span> <span data-ttu-id="1be88-172">Die Werte **LAN**, **DFÜ**und **Internet**sind möglich.</span><span class="sxs-lookup"><span data-stu-id="1be88-172">The possible values are **LAN**, **Dialup**, and **Internet**.</span></span> <span data-ttu-id="1be88-173">Der Wert **Internet** wird angezeigt, wenn für das Abonnement die Websynchronisierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1be88-173">The **Internet** value is displayed if the subscription uses Web synchronization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be88-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1be88-174">See Also</span></span>  
 <span data-ttu-id="1be88-175">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1be88-175">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="1be88-176">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1be88-176">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="1be88-177">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1be88-177">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="1be88-178">Websynchronisierung für die Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="1be88-178">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  