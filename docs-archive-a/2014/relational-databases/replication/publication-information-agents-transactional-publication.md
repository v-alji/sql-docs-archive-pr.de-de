---
title: Veröffentlichungsinformationen, Agents (Transaktionsveröffentlichung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1a3d50da15ea653a7911e65ad888d5997f47a3f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608544"
---
# <a name="publication-information-agents-transactional-publication"></a><span data-ttu-id="5648c-102">Veröffentlichungsinformationen, Agents (Transaktionsveröffentlichung)</span><span class="sxs-lookup"><span data-stu-id="5648c-102">Publication Information, Agents (Transactional Publication)</span></span>
  <span data-ttu-id="5648c-103">Auf der Registerkarte **Agents** werden Zusammenfassungsinformationen zu den Agents für die ausgewählte Veröffentlichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5648c-103">The **Agents** tab displays summary information on the agents for the selected publication.</span></span> <span data-ttu-id="5648c-104">Die Informationen auf dem Momentaufnahme-Agent und dem Protokolllese-Agent werden für alle Transaktionsveröffentlichungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5648c-104">Information on the Snapshot Agent and Log Reader Agent is displayed for all transactional publications.</span></span> <span data-ttu-id="5648c-105">Die Informationen auf dem Warteschlangenlese-Agent werden für solche Transaktionsveröffentlichungen, die für Abonnements mit verzögertem Update über eine Warteschlange verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5648c-105">Information on the Queue Reader Agent is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5648c-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5648c-106">Options</span></span>  
 <span data-ttu-id="5648c-107">Ausführliche Informationen und eine Liste der Aufträge für einen Agent können Sie anzeigen, indem Sie mit der rechten Maustaste in die Zeile des jeweiligen Agents klicken und ein Kontextmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="5648c-107">For more detailed information and tasks related to an agent, right-click the row for that agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="5648c-108">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="5648c-108">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="5648c-109">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="5648c-109">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="5648c-110">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5648c-110">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="5648c-111">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="5648c-111">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="5648c-112">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="5648c-112">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="5648c-113">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="5648c-113">Filter settings are specific to each grid.</span></span> <span data-ttu-id="5648c-114">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="5648c-114">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="5648c-115">**Status**</span><span class="sxs-lookup"><span data-stu-id="5648c-115">**Status**</span></span>  
 <span data-ttu-id="5648c-116">Die Status der einzelnen Replikations-Agents, die der Veröffentlichung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5648c-116">The status of each replication agent associated with the publication.</span></span> <span data-ttu-id="5648c-117">In der folgenden Liste sind die möglichen Statuswerte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5648c-117">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="5648c-118">Fehler</span><span class="sxs-lookup"><span data-stu-id="5648c-118">Error</span></span>  
  
-   <span data-ttu-id="5648c-119">Fehlgeschlagener Befehl wird wiederholt</span><span class="sxs-lookup"><span data-stu-id="5648c-119">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="5648c-120">Wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5648c-120">Not running</span></span>  
  
-   <span data-ttu-id="5648c-121">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5648c-121">Running</span></span>  
  
-   <span data-ttu-id="5648c-122">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="5648c-122">Completed</span></span>  
  
 <span data-ttu-id="5648c-123">**Agent**</span><span class="sxs-lookup"><span data-stu-id="5648c-123">**Agent**</span></span>  
 <span data-ttu-id="5648c-124">Die Namen der einzelnen Replikations-Agents, die der Veröffentlichung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5648c-124">The name of each replication agent associated with the publication.</span></span> <span data-ttu-id="5648c-125">Der Verteilungs-Agent ist den Abonnements dieser Veröffentlichung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5648c-125">The Distribution Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="5648c-126">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="5648c-126">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="5648c-127">**Letzte Startzeit**</span><span class="sxs-lookup"><span data-stu-id="5648c-127">**Last Start Time**</span></span>  
 <span data-ttu-id="5648c-128">Zeitpunkt, zu dem der Agent zuletzt gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5648c-128">The last time the agent started.</span></span>  
  
 <span data-ttu-id="5648c-129">**Duration**</span><span class="sxs-lookup"><span data-stu-id="5648c-129">**Duration**</span></span>  
 <span data-ttu-id="5648c-130">Zeitdauer, für die der Agent ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5648c-130">The amount of time the agent has run.</span></span> <span data-ttu-id="5648c-131">Dieser Wert gibt entweder die verstrichene Zeit eines zurzeit ausgeführten Agents oder die Gesamtzeit des zuvor ausgeführten Agents an.</span><span class="sxs-lookup"><span data-stu-id="5648c-131">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="5648c-132">**Letzte Aktion**</span><span class="sxs-lookup"><span data-stu-id="5648c-132">**Last Action**</span></span>  
 <span data-ttu-id="5648c-133">Die letzte Aktion, die bei der letzten Ausführung des Agents ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5648c-133">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5648c-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5648c-134">See Also</span></span>  
 <span data-ttu-id="5648c-135">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5648c-135">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="5648c-136">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5648c-136">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="5648c-137">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="5648c-137">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
