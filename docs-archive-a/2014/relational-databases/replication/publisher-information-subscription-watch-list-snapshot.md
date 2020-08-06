---
title: Verleger Informationen, Überwachungsliste für Abonnements (Momentaufnahme Veröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.snapshot.f1
ms.assetid: 2ebeee62-7f54-4c77-9d37-15708bc5cc23
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ea44958c81465570c036ab7dd83247fb55652f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701049"
---
# <a name="publisher-information-subscription-watch-list-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="5c9e6-102">Verlegerinformationen, Überwachungsliste für Abonnements (Momentaufnahmeveröffentlichung, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="5c9e6-102">Publisher Information, Subscription Watch List (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="5c9e6-103"> Die Registerkarte **Überwachungsliste für Abonnements** ist für Verteiler verfügbar, auf denen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höhere Versionen ausgeführt werden. Sie ist dafür konzipiert, Informationen zu Abonnements von allen Veröffentlichungen anzuzeigen, die für den ausgewählten Verleger verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="5c9e6-104">Sie können die Liste der Abonnements filtern, um Fehler, Warnungen und Abonnements mit schlechter Leistung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="5c9e6-105">Diese Registerkarte stellt einen einzelnen Speicherort für Administratoren bereit, um alle Replikationsaktivitäten bei einem Verleger zu überwachen: Der Replikationsmonitor zeigt alle Abonnements an, die Aufmerksamkeit erfordern. Grundlage hierfür ist der ausgewählte Replikationstyp und die im Dropdownlistenfeld **Anzeigen** ausgewählte Option.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="5c9e6-106">Da die auf dieser Registerkarte angezeigten Elemente auf den aktuellen Daten für Status und Leistung basieren, werden auf dieser Seite nur Abonnements angezeigt, die mit der Option im Listenfeld **Anzeigen** zum aktuellen Zeitpunkt übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c9e6-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5c9e6-107">Options</span></span>  
 <span data-ttu-id="5c9e6-108">Ausführliche Informationen und eine Liste der Aufträge für ein Abonnement können Sie anzeigen, indem Sie mit der rechten Maustaste in die Zeile des jeweiligen Abonnements klicken und eine Option im Kontextmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="5c9e6-109">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="5c9e6-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="5c9e6-110">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="5c9e6-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="5c9e6-111">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="5c9e6-112">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="5c9e6-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="5c9e6-113">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="5c9e6-114">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="5c9e6-115">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="5c9e6-116">**Momentaufnahmeabonnements anzeigen**</span><span class="sxs-lookup"><span data-stu-id="5c9e6-116">**Show Snapshot Subscriptions**</span></span>  
 <span data-ttu-id="5c9e6-117">Wählen Sie den Typ der Abonnements (Transaktionsreplikation, Momentaufnahme oder Mergereplikation) aus, die für den ausgewählten Verleger angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="5c9e6-118">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="5c9e6-118">**Show**</span></span>  
 <span data-ttu-id="5c9e6-119">Wählen Sie die Abonnementstatus aus, die für Abonnements des ausgewählten Typs angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="5c9e6-120">Sie können z. B. auswählen, dass nur die Abonnements angezeigt werden, die einen Fehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="5c9e6-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="5c9e6-121">**Status**</span></span>  
 <span data-ttu-id="5c9e6-122">Der Status jedes Abonnements, der vom Status des Momentaufnahme-Agents oder des Verteilungs-Agents bestimmt wird (der Status mit der höheren Priorität wird angezeigt).</span><span class="sxs-lookup"><span data-stu-id="5c9e6-122">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="5c9e6-123">Standardmäßig wird das Raster mit den Abonnementinformationen nach der **Status** -Spalte sortiert.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-123">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="5c9e6-124">In der folgenden Liste werden die möglichen Statuswerte und ihre Sortierreihenfolge aufgeführt (Fehler werden z. B. immer oben im Raster angezeigt).</span><span class="sxs-lookup"><span data-stu-id="5c9e6-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="5c9e6-125">Fehler</span><span class="sxs-lookup"><span data-stu-id="5c9e6-125">Error</span></span>  
  
-   <span data-ttu-id="5c9e6-126">Läuft demnächst ab/Abgelaufen</span><span class="sxs-lookup"><span data-stu-id="5c9e6-126">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="5c9e6-127">Nicht initialisiertes Abonnement</span><span class="sxs-lookup"><span data-stu-id="5c9e6-127">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="5c9e6-128">fehlerhafter Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="5c9e6-128">Retrying failed command</span></span>  
  
-   <span data-ttu-id="5c9e6-129">Wird synchronisiert</span><span class="sxs-lookup"><span data-stu-id="5c9e6-129">Synchronizing</span></span>  
  
-   <span data-ttu-id="5c9e6-130">Synchronisierung wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5c9e6-130">Not synchronizing</span></span>  
  
 <span data-ttu-id="5c9e6-131">Die Sortierreihenfolge bestimmt auch, welcher Wert angezeigt wird, wenn ein Abonnement mehr als einen Statuswert aufweist.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-131">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="5c9e6-132">Wenn ein Abonnement z. B. einen Fehler aufweist und bald abläuft, dann wird in der **Status** -Spalte der Eintrag **Fehler**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-132">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="5c9e6-133">Die Statuswerte **Läuft demnächst ab/Abgelaufen** und **Nicht initialisiertes Abonnement** stellen Warnungen dar.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-133">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="5c9e6-134">Wenn eine Warnung angezeigt wird, wird unter **Status** auch angezeigt, ob ein Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-134">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="5c9e6-135">Der Status kann beispielsweise **Wird ausgeführt, Läuft demnächst ab/Abgelaufen**lauten.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-135">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="5c9e6-136">Der Statuswert **Läuft demnächst ab/Abgelaufen** wird nur angezeigt, wenn ein Schwellenwert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-136">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="5c9e6-137">Informationen zum Festlegen von Schwellenwerten finden Sie unter [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="5c9e6-137">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="5c9e6-138">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="5c9e6-138">**Subscription**</span></span>  
 <span data-ttu-id="5c9e6-139">Der Name des jeweiligen Abonnements in folgendem Format: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-139">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="5c9e6-140">**Veröffentlichung**</span><span class="sxs-lookup"><span data-stu-id="5c9e6-140">**Publication**</span></span>  
 <span data-ttu-id="5c9e6-141">Der Name der Veröffentlichung, mit der ein Abonnement synchronisiert wird, in folgendem Format: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-141">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="5c9e6-142">**Letzte Synchronisierung**</span><span class="sxs-lookup"><span data-stu-id="5c9e6-142">**Last Synchronization**</span></span>  
 <span data-ttu-id="5c9e6-143">Der Zeitpunkt der letzten Ausführung des Verteilungs-Agents.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-143">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="5c9e6-144">Wenn eine Synchronisierung ausgeführt wird, wird **Vorgang wird ausgeführt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c9e6-144">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9e6-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c9e6-145">See Also</span></span>  
 <span data-ttu-id="5c9e6-146">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5c9e6-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="5c9e6-147">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5c9e6-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="5c9e6-148">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="5c9e6-148">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
