---
title: Abonnement, Synchronisierungs Verlauf (Mergeabonnement, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620813"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a><span data-ttu-id="5ef11-102">Abonnement, Synchronisierungsverlauf (Mergeabonnement, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="5ef11-102">Subscription, Synchronization History (Merge Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="5ef11-103">Die Registerkarte **Synchronisierungsverlauf** zeigt detaillierte Informationen zum Merge-Agent an, u. a. Status, Verlauf, Informationsmeldungen und alle Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-103">The **Synchronization History** tab displays detailed information on the Merge Agent, including status, article statistics, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ef11-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5ef11-104">Options</span></span>  
 <span data-ttu-id="5ef11-105">Wählen Sie im Menü **Sicht** aus, welche Sitzungen des Merge-Agents angezeigt werden, und wählen Sie dann eine bestimmte Sitzung aus dem Raster mit der Bezeichnung **Sitzungen des Merge-Agents**aus.</span><span class="sxs-lookup"><span data-stu-id="5ef11-105">Select which Merge Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Merge Agent**.</span></span> <span data-ttu-id="5ef11-106">Detaillierte Informationen zu dieser Sitzung werden im Raster mit der Bezeichnung **In der ausgewählten Sitzung verarbeitete Artikel**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ef11-106">Detailed information on this session is displayed in the grid labeled **Articles processed in the selected session**.</span></span>  
  
 <span data-ttu-id="5ef11-107">**Ansicht**</span><span class="sxs-lookup"><span data-stu-id="5ef11-107">**View**</span></span>  
 <span data-ttu-id="5ef11-108">Wählen Sie aus, welche Sitzungen des Merge-Agents angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5ef11-108">Select which Merge Agent sessions to view.</span></span>  
  
 <span data-ttu-id="5ef11-109">**Status**</span><span class="sxs-lookup"><span data-stu-id="5ef11-109">**Status**</span></span>  
 <span data-ttu-id="5ef11-110">Der Status des Merge-Agents am Ende der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5ef11-110">The status of the Merge Agent at the end of the session.</span></span> <span data-ttu-id="5ef11-111">In der folgenden Liste sind die möglichen Statuswerte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5ef11-111">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="5ef11-112">Fehler</span><span class="sxs-lookup"><span data-stu-id="5ef11-112">Error</span></span>  
  
-   <span data-ttu-id="5ef11-113">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5ef11-113">Completed</span></span>  
  
-   <span data-ttu-id="5ef11-114">Wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="5ef11-114">Retrying</span></span>  
  
-   <span data-ttu-id="5ef11-115">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5ef11-115">Running</span></span>  
  
 <span data-ttu-id="5ef11-116">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="5ef11-116">**Start Time**</span></span>  
 <span data-ttu-id="5ef11-117">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5ef11-117">The start time of the session.</span></span>  
  
 <span data-ttu-id="5ef11-118">**Beendigungszeit**</span><span class="sxs-lookup"><span data-stu-id="5ef11-118">**End Time**</span></span>  
 <span data-ttu-id="5ef11-119">Beendigungszeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5ef11-119">The end time of the session.</span></span> <span data-ttu-id="5ef11-120">Wenn der Agent noch nicht beendet wurde, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="5ef11-120">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="5ef11-121">**Duration**</span><span class="sxs-lookup"><span data-stu-id="5ef11-121">**Duration**</span></span>  
 <span data-ttu-id="5ef11-122">Die Zeitspanne, für die der Merge-Agent in einer Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ef11-122">The amount of time the Merge Agent has run in a session.</span></span> <span data-ttu-id="5ef11-123">Dieser Wert gibt entweder die verstrichene Zeit eines zurzeit ausgeführten Agents oder die Gesamtzeit des zuvor ausgeführten Agents an.</span><span class="sxs-lookup"><span data-stu-id="5ef11-123">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="5ef11-124">**Hochgeladene Befehle**</span><span class="sxs-lookup"><span data-stu-id="5ef11-124">**Uploaded Commands**</span></span>  
 <span data-ttu-id="5ef11-125">Die Anzahl der während der Merge-Agentsitzung hochgeladenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-125">The number of rows uploaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="5ef11-126">**Heruntergeladene Befehle**</span><span class="sxs-lookup"><span data-stu-id="5ef11-126">**Downloaded Commands**</span></span>  
 <span data-ttu-id="5ef11-127">Die Anzahl der während der Merge-Agentsitzung heruntergeladenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-127">The number of rows downloaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="5ef11-128">**Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="5ef11-128">**Error Message**</span></span>  
 <span data-ttu-id="5ef11-129">Wenn eine Sitzung mit einem Fehler beendet wurde, wird in diesem Feld die Fehlermeldung angezeigt, die vom Merge-Agent zuletzt protokolliert wurde.</span><span class="sxs-lookup"><span data-stu-id="5ef11-129">If a session ended in an error, this field displays the last error message logged by the Merge Agent.</span></span> <span data-ttu-id="5ef11-130">Wurde die Sitzung nicht mit einem Fehler beendet, ist dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="5ef11-130">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="5ef11-131">**Artikel**</span><span class="sxs-lookup"><span data-stu-id="5ef11-131">**Article**</span></span>  
 <span data-ttu-id="5ef11-132">Die Namen der einzelnen Artikel der Veröffentlichung und die folgenden Verarbeitungsphasen für die gesamte Veröffentlichung:</span><span class="sxs-lookup"><span data-stu-id="5ef11-132">The name of each article in the publication, and the following processing phases for the entire publication:</span></span>  
  
-   <span data-ttu-id="5ef11-133">**Initialisierung**.</span><span class="sxs-lookup"><span data-stu-id="5ef11-133">**Initialization**.</span></span> <span data-ttu-id="5ef11-134">Bezieht sich auf den Start des Merge-Agents und ist damit nicht gleichbedeutend mit der Initialisierung eines Abonnements, bei der auch eine Momentaufnahme angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ef11-134">This refers to starting the Merge Agent; this is not synonymous with initializing a subscription, which involves applying a snapshot.</span></span>  
  
-   <span data-ttu-id="5ef11-135">**Schemaänderungen und Masseneinfügungen**.</span><span class="sxs-lookup"><span data-stu-id="5ef11-135">**Schema changes and bulk inserts**.</span></span>  
  
-   <span data-ttu-id="5ef11-136">**Änderungen auf den Verleger hochladen**.</span><span class="sxs-lookup"><span data-stu-id="5ef11-136">**Upload changes to Publisher**.</span></span>  
  
-   <span data-ttu-id="5ef11-137">**Änderungen auf den Abonnenten herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="5ef11-137">**Download changes to Subscriber**.</span></span>  
  
 <span data-ttu-id="5ef11-138">Die Phasen werden eingeschlossen, damit im Raster die Werte für die Zeitdauer und der prozentuale Anteil an der Gesamtzeit angezeigt werden können, die in der ausgewählten Sitzung von den einzelnen Phasen beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="5ef11-138">The phases are included so that the grid can display the amount of time and percentage of total time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="5ef11-139">**% von Gesamt**</span><span class="sxs-lookup"><span data-stu-id="5ef11-139">**% of total**</span></span>  
 <span data-ttu-id="5ef11-140">Der prozentuale Anteil, den die einzelnen Phasen in der ausgewählten Sitzung von der Gesamtverarbeitungszeit beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-140">The percentage of total processing time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="5ef11-141">**Duration**</span><span class="sxs-lookup"><span data-stu-id="5ef11-141">**Duration**</span></span>  
 <span data-ttu-id="5ef11-142">Die Zeitdauer, die für die einzelnen Verarbeitungsphasen beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="5ef11-142">The amount of time spent in each processing phase.</span></span> <span data-ttu-id="5ef11-143">Dieser Wert gibt entweder die verstrichene Zeit eines zurzeit ausgeführten Merge-Agents oder die Gesamtzeit des zuvor ausgeführten Merge-Agents an.</span><span class="sxs-lookup"><span data-stu-id="5ef11-143">The time represents elapsed time if the Merge Agent is currently running for the session and total time if the Merge Agent has run previously.</span></span>  
  
 <span data-ttu-id="5ef11-144">**Inserts**</span><span class="sxs-lookup"><span data-stu-id="5ef11-144">**Inserts**</span></span>  
 <span data-ttu-id="5ef11-145">Die Anzahl der in dieser Phase der ausgewählten Sitzung eingefügten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-145">The number of rows inserted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="5ef11-146">**Updates**</span><span class="sxs-lookup"><span data-stu-id="5ef11-146">**Updates**</span></span>  
 <span data-ttu-id="5ef11-147">Die Anzahl der in dieser Phase der ausgewählten Sitzung aktualisierten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-147">The number of rows updated in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="5ef11-148">**Löschvorgang**</span><span class="sxs-lookup"><span data-stu-id="5ef11-148">**Deletes**</span></span>  
 <span data-ttu-id="5ef11-149">Die Anzahl der in dieser Phase der ausgewählten Sitzung gelöschten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-149">The number of rows deleted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="5ef11-150">**Konflikte**</span><span class="sxs-lookup"><span data-stu-id="5ef11-150">**Conflicts**</span></span>  
 <span data-ttu-id="5ef11-151">Die Anzahl der Konflikte in der ausgewählten Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5ef11-151">The number of conflicts in the selected session.</span></span>  
  
 <span data-ttu-id="5ef11-152">**Schemaänderungen**</span><span class="sxs-lookup"><span data-stu-id="5ef11-152">**Schema Changes**</span></span>  
 <span data-ttu-id="5ef11-153">Die Anzahl der Schemaänderungen in der ausgewählten Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5ef11-153">The number of schema changes in the selected session.</span></span> <span data-ttu-id="5ef11-154">Schemaänderungen können auf von der Veröffentlichungsdatenbank replizierte Schemaänderungen, das Hinzufügen oder Löschen von Artikeln oder Änderungen an Artikel- oder Veröffentlichungseigenschaften zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="5ef11-154">Schema changes can result from: schema changes being replicated from the publication database; adding or dropping articles; and changes to article or publication properties.</span></span>  
  
 <span data-ttu-id="5ef11-155">**Letzte Meldung der ausgewählten Sitzung**</span><span class="sxs-lookup"><span data-stu-id="5ef11-155">**Last message of the selected session**</span></span>  
 <span data-ttu-id="5ef11-156">In diesem Textbereich wird die letzte Meldung in der ausgewählten Sitzung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ef11-156">This text area displays the last message in the selected session.</span></span> <span data-ttu-id="5ef11-157">Wenn ein Fehler aufgetreten ist, werden detaillierte Informationen zu dem Fehler und der Befehl angezeigt, der zum Fehlerzeitpunkt auszuführen versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="5ef11-157">If an error has occurred, it displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="5ef11-158">Er enthält außerdem Links zu weiteren Informationen, die sich auf den Fehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="5ef11-158">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef11-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ef11-159">See Also</span></span>  
 <span data-ttu-id="5ef11-160">[Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5ef11-160">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="5ef11-161">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5ef11-161">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="5ef11-162">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="5ef11-162">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="5ef11-163">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="5ef11-163">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
