---
title: Abonnement, Verlauf Verteiler zu Abonnent (Momentaufnahmeabonnement) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.snapshot.f1
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe894e23e7ad7fef9c328334740eff73164130a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724477"
---
# <a name="subscription-distributor-to-subscriber-history-snapshot-subscription"></a><span data-ttu-id="1b5f5-102">Abonnement, Verlauf Verteiler zu Abonnent (Momentaufnahmeabonnement)</span><span class="sxs-lookup"><span data-stu-id="1b5f5-102">Subscription, Distributor to Subscriber History (Snapshot Subscription)</span></span>
  <span data-ttu-id="1b5f5-103"> Die Registerkarte **Verlauf Verteiler zu Abonnent** zeigt detaillierte Informationen zum Verteilungs-Agent an, u.a. Status, Verlauf, Informationsmeldungen und alle Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b5f5-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1b5f5-104">Options</span></span>  
 <span data-ttu-id="1b5f5-105">Wählen Sie im Menü **Sicht** aus, welche Sitzungen des Verteilungs-Agents angezeigt werden, und wählen Sie dann eine bestimmte Sitzung aus dem Raster mit der Bezeichnung **Sitzungen des Verteilungs-Agents**aus.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="1b5f5-106">Detaillierte Informationen zu dieser Sitzung werden im Raster mit der Bezeichnung **Aktionen in der ausgewählten Sitzung**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="1b5f5-107">Wenn die ausgewählte Sitzung mit einem Fehler beendet wurde, wird auch der Textbereich mit der Bezeichnung **Fehlerdetails oder Meldung der ausgewählten Sitzung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="1b5f5-108">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-108">**View**</span></span>  
 <span data-ttu-id="1b5f5-109">Wählen Sie aus, welche Sitzungen des Verteilungs-Agents angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-109">Select which Distribution Agent sessions to view.</span></span>  
  
 <span data-ttu-id="1b5f5-110">**Status**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-110">**Status**</span></span>  
 <span data-ttu-id="1b5f5-111">Der Status des Verteilungs-Agents.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-111">The status of the Distribution Agent.</span></span> <span data-ttu-id="1b5f5-112">In der folgenden Liste sind die möglichen Statuswerte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1b5f5-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="1b5f5-113">Fehler</span><span class="sxs-lookup"><span data-stu-id="1b5f5-113">Error</span></span>  
  
-   <span data-ttu-id="1b5f5-114">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="1b5f5-114">Completed</span></span>  
  
-   <span data-ttu-id="1b5f5-115">Wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="1b5f5-115">Retrying</span></span>  
  
-   <span data-ttu-id="1b5f5-116">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="1b5f5-116">Running</span></span>  
  
 <span data-ttu-id="1b5f5-117">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-117">**Start Time**</span></span>  
 <span data-ttu-id="1b5f5-118">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="1b5f5-119">**Endzeit**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-119">**End Time**</span></span>  
 <span data-ttu-id="1b5f5-120">Beendigungszeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-120">The end time of the session.</span></span> <span data-ttu-id="1b5f5-121">Wenn der Agent noch nicht beendet wurde, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="1b5f5-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-122">**Duration**</span></span>  
 <span data-ttu-id="1b5f5-123">Zeitspanne, für die der Verteilungs-Agent in dieser Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-123">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="1b5f5-124">Die Zeit stellt die bisher abgelaufene Zeit dar, wenn der Agent immer noch ausgeführt wird, und die Gesamtzeit, wenn die Agentsitzung beendet ist.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session had ended.</span></span>  
  
 <span data-ttu-id="1b5f5-125">**Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-125">**Error Message**</span></span>  
 <span data-ttu-id="1b5f5-126">Wenn eine Sitzung mit einem Fehler beendet wurde, wird in diesem Feld die Fehlermeldung angezeigt, die vom Verteilungs-Agent protokolliert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-126">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="1b5f5-127">Wurde die Sitzung nicht mit einem Fehler beendet, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="1b5f5-128">**Aktionsmeldung**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-128">**Action Message**</span></span>  
 <span data-ttu-id="1b5f5-129">Alle Informationsmeldungen und Fehlermeldungen, die der Verteilungs-Agent während der ausgewählten Sitzung protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-129">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="1b5f5-130">**Aktionszeit**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-130">**Action Time**</span></span>  
 <span data-ttu-id="1b5f5-131">Zeit, zu der die unter **Aktionsmeldung** beschriebene Aktion ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="1b5f5-132">**Fehlerdetails oder Meldung der ausgewählten Sitzung**</span><span class="sxs-lookup"><span data-stu-id="1b5f5-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="1b5f5-133">Wird nur angezeigt, wenn in der ausgewählten Sitzung in der **Status** -Spalte der Wert **Fehler** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-133">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="1b5f5-134">Dieser Textbereich zeigt detaillierte Fehlerinformationen sowie den Befehl an, der zum Zeitpunkt des Fehlers auszuführen versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="1b5f5-135">Er enthält außerdem Links zu weiteren Informationen, die sich auf den Fehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="1b5f5-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5f5-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b5f5-136">See Also</span></span>  
 <span data-ttu-id="1b5f5-137">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1b5f5-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="1b5f5-138">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1b5f5-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="1b5f5-139">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1b5f5-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="1b5f5-140">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="1b5f5-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
