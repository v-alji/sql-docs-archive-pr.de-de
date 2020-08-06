---
title: SQL Server-Agent, Auftragsschritte-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3759303807714e2bb7f71f59e644bc485d36cfcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615340"
---
# <a name="sql-server-agent-jobsteps-object"></a><span data-ttu-id="6fa1a-102">SQL Server-Agent, Auftragsschritte-Objekt</span><span class="sxs-lookup"><span data-stu-id="6fa1a-102">SQL Server Agent, JobSteps Object</span></span>
  <span data-ttu-id="6fa1a-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent: **Auftragsschritte** -Leistungsobjekt enthält Leistungsindikatoren, die Informationen zu den Auftragsschritten des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents angeben.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **JobSteps** performance object contains performance counters that report information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="6fa1a-104">In der nachfolgenden Tabelle sind die in diesem Objekt enthaltenen Indikatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="6fa1a-105">Die folgende Tabelle enthält die Leistungsindikatoren von **SQLAgent:Auftragsschritte** .</span><span class="sxs-lookup"><span data-stu-id="6fa1a-105">The table below contains the **SQLAgent:JobSteps** counters.</span></span>  
  
|<span data-ttu-id="6fa1a-106">Name</span><span class="sxs-lookup"><span data-stu-id="6fa1a-106">Name</span></span>|<span data-ttu-id="6fa1a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6fa1a-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="6fa1a-108">**Aktive Schritte**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-108">**Active steps**</span></span>|<span data-ttu-id="6fa1a-109">Dieser Indikator gibt die Anzahl der aktuell ausgeführten Auftragsschritte an.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-109">This counter reports the number of job steps currently running.</span></span>|  
|<span data-ttu-id="6fa1a-110">**Schritte in Warteschlange**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-110">**Queued steps**</span></span>|<span data-ttu-id="6fa1a-111">Dieser Indikator gibt die Anzahl der Auftragsschritte an, die für das Ausführen durch den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent bereitstehen, deren Ausführung jedoch noch nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-111">This counter reports the number of job steps that are ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="6fa1a-112">**Wiederholungen von Schritten gesamt**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-112">**Total step retries**</span></span>|<span data-ttu-id="6fa1a-113">Dieser Indikator gibt an, wie oft [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seit dem letzten Serverneustart insgesamt versucht hat, einen Auftragsschritt neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-113">This counter reports the total number of times that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has retried a job step since the last server restart.</span></span>|  
  
 <span data-ttu-id="6fa1a-114">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="6fa1a-114">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="6fa1a-115">Instanz</span><span class="sxs-lookup"><span data-stu-id="6fa1a-115">Instance</span></span>|<span data-ttu-id="6fa1a-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6fa1a-116">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6fa1a-117">**_Total**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-117">**_Total**</span></span>|<span data-ttu-id="6fa1a-118">Informationen für alle Auftragsschritte.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-118">Information for all job steps.</span></span>|  
|<span data-ttu-id="6fa1a-119">**ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-119">**ActiveScripting**</span></span>|<span data-ttu-id="6fa1a-120">Informationen für Auftragsschritte, die das **ActiveScripting** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-120">Information for job steps that use the **ActiveScripting** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-121">**ANALYSISCOMMAND**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-121">**ANALYSISCOMMAND**</span></span>|<span data-ttu-id="6fa1a-122">Informationen für Auftragsschritte, die das ANALYSISCOMMAND-Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-122">Information for job steps that use the ANALYSISCOMMAND subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-123">**ANALYSISQUERY**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-123">**ANALYSISQUERY**</span></span>|<span data-ttu-id="6fa1a-124">Informationen für Auftragsschritte, die das ANALYSISQUERY-Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-124">Information for job steps that use the ANALYSISQUERY subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-125">**CmdExec**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-125">**CmdExec**</span></span>|<span data-ttu-id="6fa1a-126">Informationen für Auftragsschritte, die das **CmdExec** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-126">Information for job steps that use the **CmdExec** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-127">**Distribution**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-127">**Distribution**</span></span>|<span data-ttu-id="6fa1a-128">Informationen für Auftragsschritte, die das **Distribution** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-128">Information for job steps that use the **Distribution** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-129">**Dts**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-129">**Dts**</span></span>|<span data-ttu-id="6fa1a-130">Informationen für Auftragsschritte, die das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-130">Information for job steps that use the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-131">**LogReader**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-131">**LogReader**</span></span>|<span data-ttu-id="6fa1a-132">Informationen für Auftragsschritte, die das **LogReader** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-132">Information for job steps that use the **LogReader** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-133">**Merge** (Zusammenführen)</span><span class="sxs-lookup"><span data-stu-id="6fa1a-133">**Merge**</span></span>|<span data-ttu-id="6fa1a-134">Informationen für Auftragsschritte, die das **Merge** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-134">Information for job steps that use the **Merge** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-135">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-135">**PowerShell**</span></span>|<span data-ttu-id="6fa1a-136">Informationen für Auftragsschritte, die das **PowerShell** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-136">Information for job steps that use the **PowerShell** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-137">**QueueReader**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-137">**QueueReader**</span></span>|<span data-ttu-id="6fa1a-138">Informationen für Auftragsschritte, die das **QueueReader** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-138">Information for job steps that use the **QueueReader** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-139">**Momentaufnahme**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-139">**Snapshot**</span></span>|<span data-ttu-id="6fa1a-140">Informationen für Auftragsschritte, die das **Momentaufnahme** -Subsystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-140">Information for job steps that use the **Snapshot** subsystem.</span></span>|  
|<span data-ttu-id="6fa1a-141">**TSQL**</span><span class="sxs-lookup"><span data-stu-id="6fa1a-141">**TSQL**</span></span>|<span data-ttu-id="6fa1a-142">Informationen für Auftragsschritte, die [!INCLUDE[tsql](../../includes/tsql-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-142">Information for job steps that execute [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fa1a-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fa1a-143">See Also</span></span>  
 <span data-ttu-id="6fa1a-144">[Verwalten von Auftragsschritten](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="6fa1a-144">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 <span data-ttu-id="6fa1a-145">[Verwenden von Leistungsobjekten](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="6fa1a-145">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="6fa1a-146">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="6fa1a-146">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
