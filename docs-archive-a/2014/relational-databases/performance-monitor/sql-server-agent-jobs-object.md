---
title: SQL Server-Agent, Jobs-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 82ee57eba20d44c08eadc125e9dfd69e73c35751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615341"
---
# <a name="sql-server-agent-jobs-object"></a><span data-ttu-id="1295d-102">SQL Server-Agent, Aufträge-Objekt</span><span class="sxs-lookup"><span data-stu-id="1295d-102">SQL Server Agent, Jobs Object</span></span>
  <span data-ttu-id="1295d-103">Das **Jobs** -Leistungsobjekt des SQL Server-Agents enthält Leistungsindikatoren, die Informationen zu SQL Server-Agent-Aufträgen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="1295d-103">The SQL Server Agent **Jobs** performance object contains performance counters that report information about SQL Server Agent jobs.</span></span> <span data-ttu-id="1295d-104">In der nachfolgenden Tabelle sind die in diesem Objekt enthaltenen Indikatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1295d-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="1295d-105">Die nachfolgende Tabelle enthält die **SQLAgent:Jobs** -Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1295d-105">The table below contains the **SQLAgent:Jobs** counters.</span></span>  
  
|<span data-ttu-id="1295d-106">Name</span><span class="sxs-lookup"><span data-stu-id="1295d-106">Name</span></span>|<span data-ttu-id="1295d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1295d-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1295d-108">**Aktive Aufträge**</span><span class="sxs-lookup"><span data-stu-id="1295d-108">**Active Jobs**</span></span>|<span data-ttu-id="1295d-109">Dieser Leistungsindikator erfasst die Anzahl der gerade ausgeführten Aufträge.</span><span class="sxs-lookup"><span data-stu-id="1295d-109">This counter reports the number of jobs currently running.</span></span>|  
|<span data-ttu-id="1295d-110">**Fehlerhafte Aufträge**</span><span class="sxs-lookup"><span data-stu-id="1295d-110">**Failed jobs**</span></span>|<span data-ttu-id="1295d-111">Dieser Leistungsindikator erfasst die Anzahl der Aufträge, die mit einem Fehler beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="1295d-111">This counter reports the number of jobs that exited with failure.</span></span>|  
|<span data-ttu-id="1295d-112">**Erfolgsquote der Aufträge**</span><span class="sxs-lookup"><span data-stu-id="1295d-112">**Job success rate**</span></span>|<span data-ttu-id="1295d-113">Dieser Leistungsindikator gibt den Prozentsatz der erfolgreich abgeschlossenen Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="1295d-113">This counter reports the percentage of executed jobs that completed successfully.</span></span>|  
|<span data-ttu-id="1295d-114">**Aktivierte Aufträge/Minute**</span><span class="sxs-lookup"><span data-stu-id="1295d-114">**Jobs activated/minute**</span></span>|<span data-ttu-id="1295d-115">Dieser Leistungsindikator gibt die Anzahl der Aufträge aus, die innerhalb der letzten Minute gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1295d-115">This counter reports the number of jobs launched within the last minute.</span></span>|  
|<span data-ttu-id="1295d-116">**Aufträge in Warteschlange**</span><span class="sxs-lookup"><span data-stu-id="1295d-116">**Queued jobs**</span></span>|<span data-ttu-id="1295d-117">Dieser Leistungsindikator gibt die Anzahl der Aufträge aus, die zur Ausführung durch den SQL Server-Agent bereitstehen, jedoch noch nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1295d-117">This counter reports the number of jobs that are ready for SQL Server Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="1295d-118">**Erfolgreiche Aufträge**</span><span class="sxs-lookup"><span data-stu-id="1295d-118">**Successful jobs**</span></span>|<span data-ttu-id="1295d-119">Dieser Leistungsindikator erfasst die Anzahl der Aufträge, die erfolgreich beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="1295d-119">This counter reports the number of jobs that exited with success.</span></span>|  
  
 <span data-ttu-id="1295d-120">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="1295d-120">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="1295d-121">Instanz</span><span class="sxs-lookup"><span data-stu-id="1295d-121">Instance</span></span>|<span data-ttu-id="1295d-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1295d-122">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1295d-123">**_Total**</span><span class="sxs-lookup"><span data-stu-id="1295d-123">**_Total**</span></span>|<span data-ttu-id="1295d-124">Informationen zu allen Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="1295d-124">Information for all jobs.</span></span>|  
|<span data-ttu-id="1295d-125">**Warnungen**</span><span class="sxs-lookup"><span data-stu-id="1295d-125">**Alerts**</span></span>|<span data-ttu-id="1295d-126">Informationen zu durch Warnungen gestarteten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="1295d-126">Information for jobs started by alerts.</span></span>|  
|<span data-ttu-id="1295d-127">**Andere**</span><span class="sxs-lookup"><span data-stu-id="1295d-127">**Others**</span></span>|<span data-ttu-id="1295d-128">Informationen zu Aufträgen, die nicht durch Warnungen oder Zeitpläne gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1295d-128">Information for jobs that were not started by alerts or schedules.</span></span> <span data-ttu-id="1295d-129">Meist werden diese Aufträge manuell mithilfe von **sp_start_job**gestartet.</span><span class="sxs-lookup"><span data-stu-id="1295d-129">Typically these are jobs started manually using **sp_start_job**.</span></span>|  
|<span data-ttu-id="1295d-130">**Zeitpläne**</span><span class="sxs-lookup"><span data-stu-id="1295d-130">**Schedules**</span></span>|<span data-ttu-id="1295d-131">Informationen zu durch Zeitpläne gestarteten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="1295d-131">Information for jobs started by schedules.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1295d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1295d-132">See Also</span></span>  
 <span data-ttu-id="1295d-133">[Implementieren von Aufträgen](../../ssms/agent/implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="1295d-133">[Implement Jobs](../../ssms/agent/implement-jobs.md) </span></span>  
 <span data-ttu-id="1295d-134">[Verwenden von Leistungsobjekten](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="1295d-134">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="1295d-135">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="1295d-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
