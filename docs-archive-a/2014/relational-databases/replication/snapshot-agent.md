---
title: Momentaufnahme-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.snapshotagent.f1
helpviewer_keywords:
- Snapshot Agent dialog box
ms.assetid: b715e621-2cd5-4a15-8f58-a341aa8ef5e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 925f2d3841b5dded6c8504a4a05dc60e61024161
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622540"
---
# <a name="snapshot-agent"></a><span data-ttu-id="cc64a-102">Momentaufnahme-Agent</span><span class="sxs-lookup"><span data-stu-id="cc64a-102">Snapshot Agent</span></span>
  <span data-ttu-id="cc64a-103">Im Dialogfeld **Momentaufnahme-Agent** werden detaillierte Informationen zum Momentaufnahme-Agent, wie Status, Verlauf, Informationsmeldungen und alle Fehlermeldungen, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc64a-103">The **Snapshot Agent** dialog box displays detailed information on the Snapshot Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc64a-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="cc64a-104">Options</span></span>  
 <span data-ttu-id="cc64a-105">Wählen Sie im Menü **Sicht** aus, welche Sitzungen des Momentaufnahme-Agents angezeigt werden, und wählen Sie dann eine bestimmte Sitzung aus dem Raster mit der Bezeichnung **Sitzungen des Momentaufnahme-Agents**aus.</span><span class="sxs-lookup"><span data-stu-id="cc64a-105">Select which Snapshot Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Snapshot Agent**.</span></span> <span data-ttu-id="cc64a-106">Detaillierte Informationen zu dieser Sitzung werden im Raster mit der Bezeichnung **Aktionen in der ausgewählten Sitzung**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc64a-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="cc64a-107">Wenn die ausgewählte Sitzung mit einem Fehler beendet wurde, wird auch der Textbereich mit der Bezeichnung **Fehlerdetails oder Meldung der ausgewählten Sitzung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc64a-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="cc64a-108">**Ansicht**</span><span class="sxs-lookup"><span data-stu-id="cc64a-108">**View**</span></span>  
 <span data-ttu-id="cc64a-109">Wählen Sie aus, welche Sitzungen des Momentaufnahme-Agents angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc64a-109">Select which Snapshot Agent sessions to view.</span></span>  
  
 <span data-ttu-id="cc64a-110">**Status**</span><span class="sxs-lookup"><span data-stu-id="cc64a-110">**Status**</span></span>  
 <span data-ttu-id="cc64a-111">Der Status des Momentaufnahme-Agents.</span><span class="sxs-lookup"><span data-stu-id="cc64a-111">The status of the Snapshot Agent.</span></span> <span data-ttu-id="cc64a-112">In der folgenden Liste sind die möglichen Statuswerte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="cc64a-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="cc64a-113">Fehler</span><span class="sxs-lookup"><span data-stu-id="cc64a-113">Error</span></span>  
  
-   <span data-ttu-id="cc64a-114">Fehlgeschlagener Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="cc64a-114">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="cc64a-115">Wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="cc64a-115">Not running</span></span>  
  
-   <span data-ttu-id="cc64a-116">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="cc64a-116">Completed</span></span>  
  
 <span data-ttu-id="cc64a-117">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="cc64a-117">**Start Time**</span></span>  
 <span data-ttu-id="cc64a-118">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cc64a-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="cc64a-119">**Beendigungszeit**</span><span class="sxs-lookup"><span data-stu-id="cc64a-119">**End Time**</span></span>  
 <span data-ttu-id="cc64a-120">Beendigungszeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cc64a-120">The end time of the session.</span></span> <span data-ttu-id="cc64a-121">Wenn der Agent noch nicht beendet wurde, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="cc64a-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="cc64a-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="cc64a-122">**Duration**</span></span>  
 <span data-ttu-id="cc64a-123">Die Zeitspanne, für die der Momentaufnahme-Agent in dieser Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc64a-123">The amount of time the Snapshot Agent has run in this session.</span></span> <span data-ttu-id="cc64a-124">Dieser Wert stellt die bisher abgelaufene Zeit dar, wenn der Agent immer noch ausgeführt wird, und die Gesamtzeit, wenn die Agentsitzung beendet ist.</span><span class="sxs-lookup"><span data-stu-id="cc64a-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="cc64a-125">**Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="cc64a-125">**Error Message**</span></span>  
 <span data-ttu-id="cc64a-126">Wenn eine Sitzung mit einem Fehler beendet wurde, wird in diesem Feld die Fehlermeldung angezeigt, die vom Momentaufnahme-Agent protokolliert wurde.</span><span class="sxs-lookup"><span data-stu-id="cc64a-126">If a session ended in an error, this field displays the last error message logged by the Snapshot Agent.</span></span> <span data-ttu-id="cc64a-127">Wurde die Sitzung nicht mit einem Fehler beendet, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="cc64a-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="cc64a-128">**Aktionsmeldung**</span><span class="sxs-lookup"><span data-stu-id="cc64a-128">**Action Message**</span></span>  
 <span data-ttu-id="cc64a-129">Alle Informationsmeldungen und Fehlermeldungen, die der Momentaufnahme-Agent während der ausgewählten Sitzung protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="cc64a-129">All informational messages and error messages that the Snapshot Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="cc64a-130">**Aktionszeit**</span><span class="sxs-lookup"><span data-stu-id="cc64a-130">**Action Time**</span></span>  
 <span data-ttu-id="cc64a-131">Zeit, zu der die unter **Aktionsmeldung** beschriebene Aktion ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc64a-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="cc64a-132">**Fehlerdetails oder Meldung der ausgewählten Sitzung**</span><span class="sxs-lookup"><span data-stu-id="cc64a-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="cc64a-133">Wird nur angezeigt, wenn in der ausgewählten Sitzung in der **Status** -Spalte der Wert **Fehler** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc64a-133">Is displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="cc64a-134">Dieser Textbereich zeigt detaillierte Fehlerinformationen sowie den Befehl an, der zum Zeitpunkt des Fehlers auszuführen versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="cc64a-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="cc64a-135">Er enthält außerdem Links zu weiteren Informationen, die sich auf den Fehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="cc64a-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc64a-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc64a-136">See Also</span></span>  
 <span data-ttu-id="cc64a-137">[Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cc64a-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="cc64a-138">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cc64a-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="cc64a-139">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="cc64a-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="cc64a-140">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="cc64a-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
