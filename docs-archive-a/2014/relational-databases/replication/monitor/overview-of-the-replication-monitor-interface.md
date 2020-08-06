---
title: Übersicht über die Benutzeroberfläche des Replikationsmonitors | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor
- Replication Monitor, about Replication Monitor
ms.assetid: 078f0e34-7153-45c4-8725-778b5bef88da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d9b7edbd76153f23168ec9bcf4a286d5f7cbe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615932"
---
# <a name="overview-of-the-replication-monitor-interface"></a><span data-ttu-id="ac09b-102">Übersicht über die Benutzeroberfläche des Replikationsmonitors</span><span class="sxs-lookup"><span data-stu-id="ac09b-102">Overview of the Replication Monitor Interface</span></span>
  <span data-ttu-id="ac09b-103">Der Replikationsmonitor in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] bietet eine Sicht aller Replikationsaktivitäten, bei der der Verleger oder der Verteiler im Vordergrund steht, in einem Format mit zwei Bereichen an.</span><span class="sxs-lookup"><span data-stu-id="ac09b-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor presents a Publisher-focused view or Distributor-focused view of all replication activity in a two pane format.</span></span> <span data-ttu-id="ac09b-104">Im linken Bereich fügen Sie dem Monitor einen Verleger hinzu, und im rechten Bereich zeigt der Monitor die Informationen zum Verleger, dessen Veröffentlichungen, Abonnements für diese Veröffentlichungen und die verschiedenen Replikations-Agents an.</span><span class="sxs-lookup"><span data-stu-id="ac09b-104">You add a Publisher to the monitor in the left pane, and in the right pane the monitor displays information on the Publisher, its publications, the subscriptions to those publications, and the various replication agents.</span></span> <span data-ttu-id="ac09b-105">Neben der Darstellung der Informationen zur Replikationstopologie ermöglicht der Replikationsmonitor die Ausführung zahlreicher Aufgaben, wie beispielsweise des Startens und Anhaltens von Agents und des Überprüfens von Daten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-105">In addition to presenting information for the replication topology, Replication Monitor allows you to perform a number of tasks, such as starting and stopping agents, and validating data.</span></span>  
  
## <a name="viewing-information-for-the-entire-topology"></a><span data-ttu-id="ac09b-106">Anzeigen von Informationen zur ganzen Topologie</span><span class="sxs-lookup"><span data-stu-id="ac09b-106">Viewing Information for the Entire Topology</span></span>  
 <span data-ttu-id="ac09b-107">Anzeige im linken Bereich des Replikationsmonitors</span><span class="sxs-lookup"><span data-stu-id="ac09b-107">The left pane of Replication Monitor displays</span></span>  
  
-   <span data-ttu-id="ac09b-108">Verlegergruppen, Verleger und Veröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-108">Publisher groups, Publishers, and publications.</span></span>  
  
-   <span data-ttu-id="ac09b-109">Verteiler, Verleger und Veröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-109">Distributors, Publishers, and publications.</span></span>  
  
 <span data-ttu-id="ac09b-110">Um Informationen im Replikationsmonitor anzeigen zu können, müssen Sie zunächst einen Verleger hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-110">To view any information in Replication Monitor, you must first add a Publisher.</span></span> <span data-ttu-id="ac09b-111">Weitere Informationen finden Sie unter [Hinzufügen und Entfernen von Verlegern vom Replikationsmonitor aus](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-111">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ac09b-112">Mithilfe des linken Bereichs lassen sich Antworten auf folgende Fragen finden:</span><span class="sxs-lookup"><span data-stu-id="ac09b-112">The left pane helps answer the following questions:</span></span>  
  
-   <span data-ttu-id="ac09b-113">Arbeitet das System fehlerfrei?</span><span class="sxs-lookup"><span data-stu-id="ac09b-113">Is my replication system healthy?</span></span>  
  
     <span data-ttu-id="ac09b-114">Das Replikationssystem ist relativ fehlerfrei, wenn im linken Bereich keine Fehlersymbole für Knoten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-114">The replication system is relatively healthy if there are no error icons on nodes in the left pane.</span></span> <span data-ttu-id="ac09b-115">Um einen vollständigeren Überblick über die Systemintegrität zu erhalten, sollten Sie zusätzlich die Registerkarte **Überwachungsliste für Abonnements** überprüfen, auf der Informationen zu Abonnements angezeigt werden, die möglicherweise ein Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="ac09b-115">To get a more complete view of system health, you should also check the **Subscription Watch List** tab, which displays information on subscriptions that might require attention.</span></span>  
  
-   <span data-ttu-id="ac09b-116">Warum wird ein Agent nicht ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="ac09b-116">Why is an agent not running?</span></span>  
  
     <span data-ttu-id="ac09b-117">Ein Agent wird zu einem bestimmten Zeitpunkt nicht ausgeführt, weil entweder die Ausführung nicht geplant ist oder weil ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ac09b-117">An agent is not running at a particular time either because it is not scheduled to run or because an error has occurred.</span></span> <span data-ttu-id="ac09b-118">Wenn ein Fehler aufgetreten ist, wird für die entsprechenden Knoten im linken Bereich ein Fehlersymbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-118">If an error has occurred, an error icon is displayed on the appropriate nodes in the left pane.</span></span> <span data-ttu-id="ac09b-119">Wenn der Momentaufnahme-Agent für eine Veröffentlichung beispielsweise aufgrund eines Fehlers angehalten wird, wird für die Verlegergruppe, den Verleger und die Veröffentlichungsknoten ein Fehlersymbol angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ac09b-119">For example, if the Snapshot Agent for a publication stopped because of an error, an error icon is displayed on the Publisher group, Publisher, and publication nodes.</span></span> <span data-ttu-id="ac09b-120">Die Zusammenfassungsinformationen für den Momentaufnahme-Agent werden für die Veröffentlichung auf der Registerkarte **Agents** angezeigt. Doppelklicken Sie auf dieser Registerkarte auf den Momentaufnahme-Agent, um detaillierte Fehlerinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-120">Summary information for the Snapshot Agent is displayed on the **Agents** tab for the publication; double click the Snapshot Agent on this tab for detailed error information.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-distributors"></a><span data-ttu-id="ac09b-121">Anzeigen von Informationen und Ausführen von veröffentlichungsbezogenen Aufgaben für Verteiler</span><span class="sxs-lookup"><span data-stu-id="ac09b-121">Viewing Information and Performing Tasks Related to Distributors</span></span>  
 <span data-ttu-id="ac09b-122">Im Replikationsmonitor werden auf drei Registerkarten Informationen zu Verteilern angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ac09b-122">Replication Monitor displays information about Distributors on three tabs:</span></span>  
  
-   <span data-ttu-id="ac09b-123">Registerkarte**Veröffentlichungen**</span><span class="sxs-lookup"><span data-stu-id="ac09b-123">**Publications** tab</span></span>  
  
     <span data-ttu-id="ac09b-124">Diese Registerkarte enthält Zusammenfassungsinformationen für alle Veröffentlichungen eines Verteilers.</span><span class="sxs-lookup"><span data-stu-id="ac09b-124">This tab provides summary information for all publications of a Distributor.</span></span>  
  
-   <span data-ttu-id="ac09b-125">Registerkarte**Überwachungsliste für Abonnements**</span><span class="sxs-lookup"><span data-stu-id="ac09b-125">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="ac09b-126">Diese Registerkarte stellt Informationen zu Abonnements für den ausgewählten Verteiler bereit.</span><span class="sxs-lookup"><span data-stu-id="ac09b-126">This tab provides information about subscriptions for the selected Distributor.</span></span> <span data-ttu-id="ac09b-127">Sie können die Liste der Abonnements filtern, um Fehler, Warnungen und Abonnements mit schlechter Leistung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-127">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="ac09b-128">Zudem können Sie auf der Registerkarte auf Abonnementeigenschaften zugreifen, auf detaillierte Informationen zum Agent oder Agents, die mit einem Abonnement in Zusammenhang stehen, zugreifen, Abonnements erneut initialisieren und Abonnements überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-128">The tab also lets you to perform the following tasks: access subscription properties, access detailed information about the agent or agents associated with a subscription, reinitialize subscriptions, and validate subscriptions.</span></span>  
  
     <span data-ttu-id="ac09b-129">Mithilfe der Registerkarte **Überwachungsliste für Abonnements** lassen sich die folgenden Fragen beantworten:</span><span class="sxs-lookup"><span data-stu-id="ac09b-129">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="ac09b-130">Welche Abonnements sind langsam?</span><span class="sxs-lookup"><span data-stu-id="ac09b-130">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="ac09b-131">Legen Sie die Optionen auf dieser Registerkarte so fest, dass die Abonnements im Raster nach relativer Leistung sortiert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-131">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="ac09b-132">Arbeitet das System fehlerfrei?</span><span class="sxs-lookup"><span data-stu-id="ac09b-132">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="ac09b-133">Im Raster der Registerkarte werden Fehler- und Warnungssymbole für alle Abonnements angezeigt, die ein Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="ac09b-133">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="ac09b-134">Diese Registerkarte ist nicht verfügbar für Verteiler mit [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] oder einer früheren Version.</span><span class="sxs-lookup"><span data-stu-id="ac09b-134">This tab is not available for Distributors that are running versions of [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span>  
  
-   <span data-ttu-id="ac09b-135">Registerkarte**Agents**</span><span class="sxs-lookup"><span data-stu-id="ac09b-135">**Agents** tab</span></span>  
  
     <span data-ttu-id="ac09b-136">Diese Registerkarte zeigt ausführliche Informationen zu den Agents und Aufträgen an, die von allen Replikationstypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-136">This tab displays detailed information about the agents and jobs that are used by all types of replication.</span></span> <span data-ttu-id="ac09b-137">Über diese Registerkarte können Sie zudem alle Agents und Aufträge starten und beenden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-137">The tab also let you start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="ac09b-138">Der Replikationsmonitor enthält zudem ein Kontextmenü für den Verteilerknoten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-138">Replication Monitor also provides a context menu for the Distributor node.</span></span> <span data-ttu-id="ac09b-139">Klicken Sie mit der rechten Maustaste im linken Bereich auf einen Verteiler, um die folgenden Tasks auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ac09b-139">Right-click a Distributor in the left pane to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ac09b-140">Fügen Sie dem Replikationsmonitor einen Verleger hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac09b-140">Add a Publisher to Replication Monitor.</span></span>  
  
-   <span data-ttu-id="ac09b-141">Bearbeiten Sie die Replikationsmonitor-Einstellungen für den Verleger.</span><span class="sxs-lookup"><span data-stu-id="ac09b-141">Edit Replication Monitor settings for the Distributor.</span></span>  
  
-   <span data-ttu-id="ac09b-142">Wechseln Sie zur Sicht für die Verlegergruppe.</span><span class="sxs-lookup"><span data-stu-id="ac09b-142">Switch to the Publisher Group view.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publishers"></a><span data-ttu-id="ac09b-143">Anzeigen von Informationen und Ausführen von verlegerbezogenen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ac09b-143">Viewing Information and Performing Tasks Related to Publishers</span></span>  
 <span data-ttu-id="ac09b-144">Im Replikationsmonitor werden auf drei Registerkarten Informationen zu Verlegern angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ac09b-144">Replication Monitor displays information about Publishers on three tabs:</span></span>  
  
-   <span data-ttu-id="ac09b-145">Registerkarte**Veröffentlichungen**</span><span class="sxs-lookup"><span data-stu-id="ac09b-145">**Publications** tab</span></span>  
  
     <span data-ttu-id="ac09b-146">Diese Registerkarte enthält Zusammenfassungsinformationen für alle Veröffentlichungen auf einem Verleger.</span><span class="sxs-lookup"><span data-stu-id="ac09b-146">This tab provides summary information for all publications at a Publisher.</span></span>  
  
-   <span data-ttu-id="ac09b-147">Registerkarte**Überwachungsliste für Abonnements**</span><span class="sxs-lookup"><span data-stu-id="ac09b-147">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="ac09b-148">Diese Registerkarte dient der Anzeige von Informationen zu Abonnements für alle verfügbaren Veröffentlichungen auf dem ausgewählten Verleger.</span><span class="sxs-lookup"><span data-stu-id="ac09b-148">This tab is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="ac09b-149">Sie können die Liste der Abonnements filtern, um Fehler, Warnungen und Abonnements mit schlechter Leistung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-149">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="ac09b-150">Zudem können Sie auf der Registerkarte auf Abonnementeigenschaften zugreifen, auf detaillierte Informationen zum Agent oder Agents, die mit einem Abonnement in Zusammenhang stehen, zugreifen, Abonnements erneut initialisieren und Abonnements überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-150">The tab also allows you to: access subscription properties; access detailed information about the agent or agents associated with a subscription; reinitialize subscriptions; and validate subscriptions.</span></span>  
  
     <span data-ttu-id="ac09b-151">Mithilfe der Registerkarte **Überwachungsliste für Abonnements** lassen sich die folgenden Fragen beantworten:</span><span class="sxs-lookup"><span data-stu-id="ac09b-151">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="ac09b-152">Welche Abonnements sind langsam?</span><span class="sxs-lookup"><span data-stu-id="ac09b-152">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="ac09b-153">Legen Sie die Optionen auf dieser Registerkarte so fest, dass die Abonnements im Raster nach relativer Leistung sortiert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-153">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="ac09b-154">Arbeitet das System fehlerfrei?</span><span class="sxs-lookup"><span data-stu-id="ac09b-154">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="ac09b-155">Im Raster der Registerkarte werden Fehler- und Warnungssymbole für alle Abonnements angezeigt, die ein Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="ac09b-155">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="ac09b-156">Diese Registerkarte wird nicht für Verteiler angezeigt, auf denen niedrigere Versionen als [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-156">This tab is not displayed for Distributors running versions prior to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="ac09b-157">Registerkarte**Agents**</span><span class="sxs-lookup"><span data-stu-id="ac09b-157">**Agents** tab</span></span>  
  
     <span data-ttu-id="ac09b-158">Diese Registerkarte zeigt ausführliche Informationen zu den Agents und Aufträgen an, die von allen Replikationstypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-158">This tab displays detailed information about the agents and jobs used by all types of replication.</span></span> <span data-ttu-id="ac09b-159">Über diese Registerkarte können Sie zudem alle Agents und Aufträge starten und beenden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-159">The tab also allows you to start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="ac09b-160">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-160">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ac09b-161">Der Replikationsmonitor enthält zudem ein Kontextmenü für den Verlegerknoten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-161">Replication Monitor also provides a context menu for the Publisher node.</span></span> <span data-ttu-id="ac09b-162">Klicken Sie im linken Bereich mit der rechten Maustaste auf einen Verleger, um Folgendes auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ac09b-162">Right-click a Publisher in the left pane to:</span></span>  
  
-   <span data-ttu-id="ac09b-163">Hinzufügen von Replikationsmonitor-Einstellungen für den Verleger</span><span class="sxs-lookup"><span data-stu-id="ac09b-163">Edit Replication Monitor settings for the Publisher</span></span>  
  
-   <span data-ttu-id="ac09b-164">Entfernen des Verlegers aus dem Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="ac09b-164">Remove the Publisher from Replication Monitor</span></span>  
  
-   <span data-ttu-id="ac09b-165">Anzeigen und Bearbeiten von Agentprofilen</span><span class="sxs-lookup"><span data-stu-id="ac09b-165">View and edit agent profiles</span></span>  
  
-   <span data-ttu-id="ac09b-166">Verbinden oder Trennen der Verbindung mit dem Verteiler, auf dem die Informationen zum Verleger gespeichert sind</span><span class="sxs-lookup"><span data-stu-id="ac09b-166">Connect to or disconnect from the Distributor that stores information about the Publisher</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publications"></a><span data-ttu-id="ac09b-167">Anzeigen von Informationen und Ausführen von veröffentlichungsbezogenen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ac09b-167">Viewing Information and Performing Tasks Related to Publications</span></span>  
 <span data-ttu-id="ac09b-168">Im Replikationsmonitor werden auf drei Registerkarten und in mehreren Detailfenstern Informationen zu Veröffentlichungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ac09b-168">Replication Monitor displays information about publications on three tabs and a number of detail windows:</span></span>  
  
-   <span data-ttu-id="ac09b-169">Registerkarte**Alle Abonnements**</span><span class="sxs-lookup"><span data-stu-id="ac09b-169">**All Subscriptions** tab</span></span>  
  
     <span data-ttu-id="ac09b-170">Auf dieser Registerkarte werden Informationen zu allen Abonnements für die ausgewählte Veröffentlichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-170">This tab displays information about all subscriptions to the selected publication.</span></span> <span data-ttu-id="ac09b-171">Diese Registerkarte wird standardmäßig nach Priorität sortiert: Zuerst werden Fehler, dann Warnungen und anschließend aufsteigend nach Leistung Abonnements mit schlechter Leistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-171">By default, this tab is sorted in priority order: errors, then warnings, then in increasing order of performance, with any poorly performing subscriptions at the top.</span></span>  
  
     <span data-ttu-id="ac09b-172">Mithilfe der Registerkarte **Alle Abonnements** lassen sich die folgenden Fragen beantworten:</span><span class="sxs-lookup"><span data-stu-id="ac09b-172">The **All Subscriptions** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="ac09b-173">Welche Abonnements sind langsam?</span><span class="sxs-lookup"><span data-stu-id="ac09b-173">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="ac09b-174">Legen Sie die Optionen auf dieser Registerkarte so fest, dass die Abonnements im Raster nach relativer Leistung sortiert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-174">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="ac09b-175">Arbeitet das System fehlerfrei?</span><span class="sxs-lookup"><span data-stu-id="ac09b-175">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="ac09b-176">Im Raster der Registerkarte werden Fehler- und Warnungssymbole für alle Abonnements angezeigt, die ein Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="ac09b-176">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
-   <span data-ttu-id="ac09b-177">Registerkarte**Agents**</span><span class="sxs-lookup"><span data-stu-id="ac09b-177">**Agents** tab</span></span>  
  
     <span data-ttu-id="ac09b-178">Diese Registerkarte zeigt Informationen zu den Agents an, die von der Replikation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-178">This tab displays information about the agents that are used by replication.</span></span> <span data-ttu-id="ac09b-179">Diese Registerkarte enthält Informationen zu folgenden Agents:</span><span class="sxs-lookup"><span data-stu-id="ac09b-179">This tab displays information about the following agents:</span></span>  
  
    -   <span data-ttu-id="ac09b-180">Momentaufnahme-Agent, der von allen Veröffentlichungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac09b-180">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="ac09b-181">Protokolllese-Agent, der von allen Transaktionsveröffentlichungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac09b-181">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="ac09b-182">Warteschlangenlese-Agent, der von Transaktionsveröffentlichungen verwendet wird, die für Abonnements mit verzögertem Update über eine Warteschlange aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-182">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="ac09b-183">Darüber hinaus können Sie auf der Registerkarte die folgenden Aufgaben ausführen: auf detaillierte Informationen zu den Agents zugreifen und die einzelnen Agents starten und anhalten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-183">The tab also allows for you to perform the following tasks: access detailed information about each agent, and start and stop each agent.</span></span> <span data-ttu-id="ac09b-184">Informationen zu den Agents, die den Abonnements zugeordnet sind (Verteilungs-Agent und Merge-Agent), finden Sie in diesem Thema im Abschnitt zum Anzeigen von Informationen und zum Ausführen von veröffentlichungsbezogenen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="ac09b-184">For information about agents that are associated with subscriptions (the Distribution Agent and Merge Agent), see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
-   <span data-ttu-id="ac09b-185">Registerkarte**Warnungen**</span><span class="sxs-lookup"><span data-stu-id="ac09b-185">**Warnings** tab</span></span>  
  
     <span data-ttu-id="ac09b-186">Auf dieser Registerkarte können Sie Warnungen für Agents angeben.</span><span class="sxs-lookup"><span data-stu-id="ac09b-186">This tab enables you to specify warnings and alerts for agents.</span></span> <span data-ttu-id="ac09b-187">Weitere Informationen finden Sie unter [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-187">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="ac09b-188">Registerkarte**Überwachungstoken** (nur für Transaktionsreplikationen)</span><span class="sxs-lookup"><span data-stu-id="ac09b-188">**Tracer Tokens** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="ac09b-189">Über diese Registerkarte können Sie die Latenzzeit messen, d. h. die Zeitspanne zwischen dem Ausführen des Commit für eine Transaktion auf dem Verleger und dem Ausführen des Commit für die entsprechende Aktion auf dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-189">This tab allows you to measure latency, the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="ac09b-190">Mithilfe dieser Registerkarte können Sie folgende Frage beantworten:</span><span class="sxs-lookup"><span data-stu-id="ac09b-190">This tab helps answers the following question:</span></span>  
  
    -   <span data-ttu-id="ac09b-191">Wie lange dauert es bei der Transaktionsreplikation, bis eine Transaktion, für die ein Commit ausgeführt wurde, den Abonnenten erreicht?</span><span class="sxs-lookup"><span data-stu-id="ac09b-191">How long will it take a transaction committed now to reach a Subscriber in transactional replication?</span></span>  
  
         <span data-ttu-id="ac09b-192">Zeigen Sie die Gesamtzeit an, die benötigt wird, um eine Transaktion über das System zu übertragen, und vergleichen Sie sie mit älteren Zeiten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-192">View the total time for a transaction to travel through the system and also compare it to previous times.</span></span>  
  
     <span data-ttu-id="ac09b-193">Diese Registerkarte wird nicht für Verteiler mit [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] oder einer früheren Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-193">This tab is not displayed for Distributors running [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span> <span data-ttu-id="ac09b-194">Weitere Informationen zu Überwachungstoken finden Sie unter [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-194">For more information on tracer tokens, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="ac09b-195">Detailfenster für die Agents, die einer Veröffentlichung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ac09b-195">Detail windows for the agents associated with a publication.</span></span> <span data-ttu-id="ac09b-196">Folgende Agents sind Veröffentlichungen zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="ac09b-196">The following agents are associated with publications:</span></span>  
  
    -   <span data-ttu-id="ac09b-197">Momentaufnahme-Agent, der von allen Veröffentlichungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac09b-197">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="ac09b-198">Protokolllese-Agent, der von allen Transaktionsveröffentlichungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac09b-198">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="ac09b-199">Warteschlangenlese-Agent, der von Transaktionsveröffentlichungen verwendet wird, die für Abonnements mit verzögertem Update über eine Warteschlange aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-199">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="ac09b-200">Doppelklicken Sie im Replikationsmonitor auf einen Agent, um auf die entsprechenden Informationen in einem Detailfenster zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-200">Double-click an agent in Replication Monitor to access information in a detail window.</span></span> <span data-ttu-id="ac09b-201">Neben den oben aufgeführten Agents sind folgende Agents Abonnements zugeordnet: Der Verteilungs-Agent für Abonnements ist Momentaufnahme- und Transaktionsveröffentlichungen zu geordnet, und der Merge-Agent ist Abonnements für Mergeveröffentlichungen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac09b-201">In addition to the agents listed above, there are agents associated with subscriptions: the Distribution Agent for subscriptions to snapshot and transactional publications; and the Merge Agent for subscriptions to merge publications.</span></span> <span data-ttu-id="ac09b-202">Weitere Informationen hierzu finden Sie in diesem Thema im Abschnitt zum Anzeigen von Informationen und zum Ausführen von veröffentlichungsbezogenen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="ac09b-202">For more information, see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
     <span data-ttu-id="ac09b-203">Die Detailfenster des Agents enthalten Informationen zu Agentsitzungen angezeigt, einschließlich Startzeit, Beendigungszeit, Dauer und während einer Sitzung ausgeführter Aktionen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-203">The agent detail windows provide information about agent sessions, including start time, end time, duration, and the actions performed in a session.</span></span> <span data-ttu-id="ac09b-204">Sie sind hilfreich zum Beantworten der folgenden Frage:</span><span class="sxs-lookup"><span data-stu-id="ac09b-204">They help to answer the following question:</span></span>  
  
    -   <span data-ttu-id="ac09b-205">Warum wird ein Agent nicht ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="ac09b-205">Why is an agent not running?</span></span>  
  
         <span data-ttu-id="ac09b-206">In den verfügbaren Fehlermeldungen werden detaillierte Informationen dazu angegeben, warum ein Agent nicht ausgeführt wird. Sie bilden einen Ausgangspunkt für die Behebung von Problemen in Agents, die einer Veröffentlichung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ac09b-206">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a publication.</span></span>  
  
 <span data-ttu-id="ac09b-207">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-207">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ac09b-208">Der Replikationsmonitor enthält zudem ein Kontextmenü für den Veröffentlichungsknoten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-208">Replication Monitor also provides a context menu for the publications node.</span></span> <span data-ttu-id="ac09b-209">Klicken Sie im linken Bereich mit der rechten Maustaste auf eine Veröffentlichung, um Folgendes auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ac09b-209">Right-click a publication in the left pane to:</span></span>  
  
-   <span data-ttu-id="ac09b-210">Erneutes Initialisieren aller Abonnements für eine Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="ac09b-210">Reinitialize all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="ac09b-211">Überprüfen aller Abonnements für eine Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="ac09b-211">Validate all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="ac09b-212">Generieren einer Momentaufnahme für eine Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="ac09b-212">Generate a snapshot for a publication</span></span>  
  
-   <span data-ttu-id="ac09b-213">Anzeigen und Bearbeiten von Veröffentlichungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="ac09b-213">View and edit publication properties</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-subscriptions"></a><span data-ttu-id="ac09b-214">Anzeigen von Informationen und Ausführen von abonnementbezogenen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ac09b-214">Viewing Information and Performing Tasks Related to Subscriptions</span></span>  
 <span data-ttu-id="ac09b-215">Im Replikationsmonitor werden auf mehreren verschiedenen Registerkarten Informationen zu Abonnements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-215">Replication Monitor displays information about subscriptions on a number of different tabs.</span></span> <span data-ttu-id="ac09b-216">Doppelklicken Sie im Replikationsmonitor auf ein Abonnement, um auf die entsprechenden Registerkarten in einem Detailfenster zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-216">Double-click a subscription in Replication Monitor to access these tabs in a detail window.</span></span> <span data-ttu-id="ac09b-217">Alle Registerkarte sind hilfreich, um die Frage "Warum wird ein Agent nicht ausgeführt?" zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-217">All of the tabs are useful in answering the question "Why is an agent not running?"</span></span> <span data-ttu-id="ac09b-218">In den verfügbaren Fehlermeldungen werden detaillierte Informationen dazu angegeben, warum ein Agent nicht ausgeführt wird. Sie bilden einen Ausgangspunkt für die Behebung von Problemen in Agents, die einem Abonnement zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ac09b-218">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a subscription.</span></span>  
  
-   <span data-ttu-id="ac09b-219">Registerkarten**Alle Abonnements** und **Überwachungsliste für Abonnements**.</span><span class="sxs-lookup"><span data-stu-id="ac09b-219">**All Subscriptions tab** and **Subscription Watch List tab.**</span></span>  
  
     <span data-ttu-id="ac09b-220">Diese Registerkarten werden weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac09b-220">These tabs are described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="ac09b-221">Registerkarte**Verlauf Verleger zu Verteiler** (nur für Transaktionsreplikationen)</span><span class="sxs-lookup"><span data-stu-id="ac09b-221">**Publisher to Distributor History** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="ac09b-222">Auf dieser Registerkarte werden Informationen zum Protokolllese-Agent für eine Veröffentlichung angezeigt (diese Registerkarte entspricht dem Detailfenster Protokolllese-Agent).</span><span class="sxs-lookup"><span data-stu-id="ac09b-222">This tab displays information on the Log Reader Agent for a publication (the tab is identical to the Log Reader Agent details window).</span></span>  
  
-   <span data-ttu-id="ac09b-223">Registerkarte**Verlauf Verteiler zu Abonnent** (Momentaufnahmereplikation und Transaktionsreplikation)</span><span class="sxs-lookup"><span data-stu-id="ac09b-223">**Distributor to Subscriber History** tab (snapshot replication and transactional replication)</span></span>  
  
     <span data-ttu-id="ac09b-224">Auf dieser Registerkarte werden Informationen zum Verteilungs-Agent für ein Abonnement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-224">This tab displays information on the Distribution Agent for a subscription.</span></span>  
  
-   <span data-ttu-id="ac09b-225">Registerkarte**Nicht verteilte Befehle** (nur für Transaktionsreplikationen)</span><span class="sxs-lookup"><span data-stu-id="ac09b-225">**Undistributed Commands** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="ac09b-226">Auf diese Registerkarte werden Informationen zur Anzahl der Befehle in der Verteilungsdatenbank angezeigt, die nicht an den ausgewählten Abonnenten übermittelt wurden. Zudem wird die geschätzte Zeit angegeben, die die Übermittlung dieser Befehle in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-226">This tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="ac09b-227">Mithilfe dieser Registerkarte kann die Frage "Wie weit ist mein Abonnement in Verzug?" beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-227">The tab helps answer the question, "How far behind is my subscription?"</span></span> <span data-ttu-id="ac09b-228">Diese Registerkarte wird nicht für Verteiler angezeigt, auf denen niedrigere Versionen als SQL Server 2005 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ac09b-228">This tab is not displayed for Distributors running versions prior to SQL Server 2005.</span></span>  
  
-   <span data-ttu-id="ac09b-229">Registerkarte**Synchronisierungsverlauf** (nur für Mergereplikationen)</span><span class="sxs-lookup"><span data-stu-id="ac09b-229">**Synchronization History** tab (merge replication only)</span></span>  
  
     <span data-ttu-id="ac09b-230">Auf dieser Registerkarte werden Informationen zum Merge-Agent für ein Abonnement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac09b-230">This tab displays information on the Merge Agent for a subscription.</span></span> <span data-ttu-id="ac09b-231">Mithilfe dieser Registerkarte können Sie folgende Frage beantworten:</span><span class="sxs-lookup"><span data-stu-id="ac09b-231">This tab helps answer the following question:</span></span>  
  
    -   <span data-ttu-id="ac09b-232">Warum ist das Mergeabonnement langsam?</span><span class="sxs-lookup"><span data-stu-id="ac09b-232">Why is my merge subscription slow?</span></span>  
  
         <span data-ttu-id="ac09b-233">Diese Registerkarte zeigt detaillierte Statistiken für jeden während der Synchronisierung verarbeiteten Artikel an, einschließlich der aufgewendeten Zeit in jeder Verarbeitungsphase (Hochladen von Änderungen, Herunterladen von Änderungen usw.)</span><span class="sxs-lookup"><span data-stu-id="ac09b-233">This tab provides detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="ac09b-234">Dadurch kann genau festgestellt werden, welche Tabellen zu einer Verlangsamung führen. Darüber hinaus bieten diese Statistiken eine optimale Plattform, Leistungsprobleme bei Mergeabonnements zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ac09b-234">It can help pinpoint specific tables that are causing slowdowns and is the best place to troubleshoot performance issues with merge subscriptions.</span></span>  
  
 <span data-ttu-id="ac09b-235">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-235">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>
  
## <a name="viewing-information-and-performing-tasks-related-to-agent-profiles"></a><span data-ttu-id="ac09b-236">Anzeigen von Informationen und Ausführen von Aufgaben, die sich auf Agentprofile beziehen</span><span class="sxs-lookup"><span data-stu-id="ac09b-236">Viewing Information and Performing Tasks Related to Agent Profiles</span></span>  
 <span data-ttu-id="ac09b-237">Der Replikationsmonitor enthält mehrere Dialogfelder zum Verwalten von Agentprofilen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-237">Replication Monitor includes a number of dialog boxes for managing agent profiles.</span></span> <span data-ttu-id="ac09b-238">Bei Agentprofilen handelt es sich um Parametersätze für einen Agent, mit denen das Verhalten des Agents festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ac09b-238">Agent profiles are sets of parameters for an agent that determine agent behavior.</span></span> <span data-ttu-id="ac09b-239">Weitere Informationen finden Sie unter [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ac09b-239">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span> <span data-ttu-id="ac09b-240">Die Dialogfelder lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac09b-240">The dialog boxes are:</span></span>  
  
-   <span data-ttu-id="ac09b-241">**Agentprofile**</span><span class="sxs-lookup"><span data-stu-id="ac09b-241">**Agent Profiles**</span></span>  
  
     <span data-ttu-id="ac09b-242">In diesem Dialogfeld können Sie die Eigenschaften von Profilen ändern, Profile erstellen und löschen, ein Standardprofil angeben und angeben, dass alle Agents eines bestimmten Typs (beispielsweise Momentaufnahme-Agents) ein bestimmtes Profil verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-242">This dialog box allows you to: change the properties of profiles; create and delete profiles; specify a default profile; and specify that all agents of a specific type (such as Snapshot Agents) should use a given profile.</span></span>  
  
-   <span data-ttu-id="ac09b-243">**\<AgentProfileName> Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="ac09b-243">**\<AgentProfileName> Properties**</span></span>  
  
     <span data-ttu-id="ac09b-244">In diesem Dialogfeld können Sie die Parametereinstellungen in einem Profil anzeigen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ac09b-244">This dialog box allows you to view and edit the parameter settings in a profile.</span></span>  
  
-   <span data-ttu-id="ac09b-245">**Neues Agentprofil**</span><span class="sxs-lookup"><span data-stu-id="ac09b-245">**New Agent Profile**</span></span>  
  
     <span data-ttu-id="ac09b-246">In diesem Dialogfeld können Sie ein neues Profil erstellen und dabei optional die Werte eines vorhandenen Profils aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="ac09b-246">This dialog box allows you to create a new profile, optionally including the values from an existing profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac09b-247">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac09b-247">See Also</span></span>  
 [<span data-ttu-id="ac09b-248">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="ac09b-248">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
