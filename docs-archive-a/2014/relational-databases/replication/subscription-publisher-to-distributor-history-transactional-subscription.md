---
title: Abonnement, Verlauf Verleger zu Verteiler (Transaktionsabonnement) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.tran.f1
ms.assetid: d5a4c697-1342-49fd-8b7b-b059af32556a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3806c59e545e325fa7e60f2cd92a4b990b0505cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726885"
---
# <a name="subscription-publisher-to-distributor-history-transactional-subscription"></a><span data-ttu-id="40d9c-102">Abonnement, Verlauf Verleger zu Verteiler (Transaktionsabonnement)</span><span class="sxs-lookup"><span data-stu-id="40d9c-102">Subscription, Publisher to Distributor History (Transactional Subscription)</span></span>
  <span data-ttu-id="40d9c-103"> Die Registerkarte **Verlauf Verleger zu Verteiler** zeigt detaillierte Informationen zum Protokolllese-Agent an, u.a. Status, Verlauf, Informationsmeldungen und alle Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="40d9c-103">The **Publisher to Distributor History** tab displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40d9c-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="40d9c-104">Options</span></span>  
 <span data-ttu-id="40d9c-105">Wählen Sie im Menü **Sicht** aus, welche Sitzungen des Protokolllese-Agents angezeigt werden, und wählen Sie dann eine bestimmte Sitzung aus dem Raster mit der Bezeichnung **Sitzungen des Protokolllese-Agents**aus.</span><span class="sxs-lookup"><span data-stu-id="40d9c-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="40d9c-106">Detaillierte Informationen zu dieser Sitzung werden im Raster mit der Bezeichnung **Aktionen in der ausgewählten Sitzung**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40d9c-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="40d9c-107">Wenn die ausgewählte Sitzung mit einem Fehler beendet wurde, wird auch der Textbereich mit der Bezeichnung **Fehlerdetails oder Meldung der ausgewählten Sitzung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40d9c-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="40d9c-108">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="40d9c-108">**View**</span></span>  
 <span data-ttu-id="40d9c-109">Wählen Sie aus, welche Sitzungen des Protokolllese-Agents angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="40d9c-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="40d9c-110">Da der Protokolllese-Agent in der Regel kontinuierlich ausgeführt wird, kann möglicherweise nur eine Sitzung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="40d9c-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="40d9c-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="40d9c-111">**Status**</span></span>  
 <span data-ttu-id="40d9c-112">Status des Protokolllese-Agents.</span><span class="sxs-lookup"><span data-stu-id="40d9c-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="40d9c-113">In der folgenden Liste sind die möglichen Statuswerte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="40d9c-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="40d9c-114">Fehler</span><span class="sxs-lookup"><span data-stu-id="40d9c-114">Error</span></span>  
  
-   <span data-ttu-id="40d9c-115">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="40d9c-115">Completed</span></span>  
  
-   <span data-ttu-id="40d9c-116">Wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="40d9c-116">Retrying</span></span>  
  
-   <span data-ttu-id="40d9c-117">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="40d9c-117">Running</span></span>  
  
 <span data-ttu-id="40d9c-118">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="40d9c-118">**Start Time**</span></span>  
 <span data-ttu-id="40d9c-119">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="40d9c-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="40d9c-120">**Endzeit**</span><span class="sxs-lookup"><span data-stu-id="40d9c-120">**End Time**</span></span>  
 <span data-ttu-id="40d9c-121">Beendigungszeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="40d9c-121">The end time of the session.</span></span> <span data-ttu-id="40d9c-122">Wenn der Agent noch nicht beendet wurde, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="40d9c-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="40d9c-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="40d9c-123">**Duration**</span></span>  
 <span data-ttu-id="40d9c-124">Zeitspanne, für die der Protokolllese-Agent in dieser Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="40d9c-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="40d9c-125">Dieser Wert stellt die bisher abgelaufene Zeit dar, wenn der Agent immer noch ausgeführt wird, und die Gesamtzeit, wenn die Agentsitzung beendet ist.</span><span class="sxs-lookup"><span data-stu-id="40d9c-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="40d9c-126">**Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="40d9c-126">**Error Message**</span></span>  
 <span data-ttu-id="40d9c-127">Wenn eine Sitzung mit einem Fehler beendet wurde, wird in diesem Feld die Fehlermeldung angezeigt, die vom Protokolllese-Agent protokolliert wurde.</span><span class="sxs-lookup"><span data-stu-id="40d9c-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="40d9c-128">Wurde die Sitzung nicht mit einem Fehler beendet, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="40d9c-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="40d9c-129">**Aktionsmeldung**</span><span class="sxs-lookup"><span data-stu-id="40d9c-129">**Action Message**</span></span>  
 <span data-ttu-id="40d9c-130">Alle Informationsmeldungen und Fehlermeldungen, die der Protokolllese-Agent während der ausgewählten Sitzung protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="40d9c-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="40d9c-131">**Aktionszeit**</span><span class="sxs-lookup"><span data-stu-id="40d9c-131">**Action Time**</span></span>  
 <span data-ttu-id="40d9c-132">Zeit, zu der die unter **Aktionsmeldung** beschriebene Aktion ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="40d9c-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="40d9c-133">**Fehlerdetails oder Meldung der ausgewählten Sitzung**</span><span class="sxs-lookup"><span data-stu-id="40d9c-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="40d9c-134">Wird nur angezeigt, wenn in der ausgewählten Sitzung in der **Status** -Spalte der Wert **Fehler** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="40d9c-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="40d9c-135">Dieser Textbereich zeigt detaillierte Fehlerinformationen sowie den Befehl an, der zum Zeitpunkt des Fehlers auszuführen versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="40d9c-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="40d9c-136">Er enthält außerdem Links zu weiteren Informationen, die sich auf den Fehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="40d9c-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d9c-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40d9c-137">See Also</span></span>  
 <span data-ttu-id="40d9c-138">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="40d9c-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="40d9c-139">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="40d9c-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="40d9c-140">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="40d9c-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="40d9c-141">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="40d9c-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
