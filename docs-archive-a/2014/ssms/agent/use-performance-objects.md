---
title: Verwenden von Leistungsobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7c1fe3f4a7d9a5fec901f84d8e913e49a4dbd1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619530"
---
# <a name="use-performance-objects"></a><span data-ttu-id="cf5ed-102">Verwenden von Leistungsobjekten</span><span class="sxs-lookup"><span data-stu-id="cf5ed-102">Use Performance Objects</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cf5ed-103">Agent umfasst Leistungsobjekte und -indikatoren zum Überwachen der Leistung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="cf5ed-103">Agent includes performance objects and counters to monitor how the service is performing.</span></span> <span data-ttu-id="cf5ed-104">Mithilfe dieser Leistungsobjekte können Sie das Windows-Tool Systemmonitor verwenden, um festzustellen, welche Vorgänge vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst im Hintergrund ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf5ed-104">These performance objects allow you to use Performance Monitor, a Windows tool, to identify what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is doing in the background.</span></span> <span data-ttu-id="cf5ed-105">Sie können beispielsweise die Anzahl der aktiven Aufträge feststellen, die vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst aktuell ausgeführt werden, um blockierte Aufträge zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cf5ed-105">For example, you can identify how many active jobs the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is currently running to identify those jobs that are blocked.</span></span>  
  
 <span data-ttu-id="cf5ed-106">Die Leistungsobjekte und Leistungsindikatoren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Diensts sind für jede Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vorhanden, die auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cf5ed-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects and counters exist for each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is installed on a computer.</span></span> <span data-ttu-id="cf5ed-107">Leistungsobjekte sind nach der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] benannt, die jedes Objekt repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="cf5ed-107">Performance objects are named according to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that each object represents.</span></span>  
  
 <span data-ttu-id="cf5ed-108">Die folgende Tabelle veranschaulicht, wie die Leistungsobjekte des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Diensts benannt werden:</span><span class="sxs-lookup"><span data-stu-id="cf5ed-108">The following table shows how the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects are named:</span></span>  
  
|<span data-ttu-id="cf5ed-109">Instanztyp</span><span class="sxs-lookup"><span data-stu-id="cf5ed-109">Instance type</span></span>|<span data-ttu-id="cf5ed-110">Objektname</span><span class="sxs-lookup"><span data-stu-id="cf5ed-110">Object name</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="cf5ed-111">Standard</span><span class="sxs-lookup"><span data-stu-id="cf5ed-111">Default</span></span>|<span data-ttu-id="cf5ed-112">**SQLAgent:** *Objekt*:*Indikator*</span><span class="sxs-lookup"><span data-stu-id="cf5ed-112">**SQLAgent:** *object*:*counter*</span></span>|  
|<span data-ttu-id="cf5ed-113">benannt</span><span class="sxs-lookup"><span data-stu-id="cf5ed-113">Named</span></span>|<span data-ttu-id="cf5ed-114">**SQLAgent$**</span><span class="sxs-lookup"><span data-stu-id="cf5ed-114">**SQLAgent$**</span></span><br /> <span data-ttu-id="cf5ed-115">***instance_name* :** *Objekt*:*Counter*</span><span class="sxs-lookup"><span data-stu-id="cf5ed-115">***instance_name* :** *object*:*counter*</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cf5ed-116">beinhaltet die folgenden Leistungsobjekte für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent.</span><span class="sxs-lookup"><span data-stu-id="cf5ed-116">includes the following performance objects for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
|<span data-ttu-id="cf5ed-117">Objektname</span><span class="sxs-lookup"><span data-stu-id="cf5ed-117">Object name</span></span>|<span data-ttu-id="cf5ed-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf5ed-118">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="cf5ed-119">SQLAgent:Aufträge</span><span class="sxs-lookup"><span data-stu-id="cf5ed-119">SQLAgent:Jobs</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobs-object.md)|<span data-ttu-id="cf5ed-120">Leistungsinformationen zu gestarteten Aufträgen, Erfolgsrate und aktuellem Status</span><span class="sxs-lookup"><span data-stu-id="cf5ed-120">Performance information about jobs that have been started, success rates, and current status</span></span>|  
|[<span data-ttu-id="cf5ed-121">SQLAgent:Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="cf5ed-121">SQLAgent:JobSteps</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobsteps-object.md)|<span data-ttu-id="cf5ed-122">Statusinformationen zu Auftragsschritten</span><span class="sxs-lookup"><span data-stu-id="cf5ed-122">Status information about job steps</span></span>|  
|[<span data-ttu-id="cf5ed-123">SQLAgent:Warnungen</span><span class="sxs-lookup"><span data-stu-id="cf5ed-123">SQLAgent:Alerts</span></span>](../../relational-databases/performance-monitor/sql-server-agent-alerts-object.md)|<span data-ttu-id="cf5ed-124">Informationen zur Anzahl der Warnungen und Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="cf5ed-124">Information about number of alerts and notifications</span></span>|  
|[<span data-ttu-id="cf5ed-125">SQLAgent:Statistik</span><span class="sxs-lookup"><span data-stu-id="cf5ed-125">SQLAgent:Statistics</span></span>](../../relational-databases/performance-monitor/sql-server-agent-statistics-object.md)|<span data-ttu-id="cf5ed-126">Allgemeine Leistungsinformationen</span><span class="sxs-lookup"><span data-stu-id="cf5ed-126">General performance information</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf5ed-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf5ed-127">See Also</span></span>  
 <span data-ttu-id="cf5ed-128">[Überwachen und Optimieren der Leistung](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span><span class="sxs-lookup"><span data-stu-id="cf5ed-128">[Monitor and Tune for Performance](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span></span>  
 [<span data-ttu-id="cf5ed-129">Starten des Systemmonitors &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="cf5ed-129">Start System Monitor &#40;Windows&#41;</span></span>](../../relational-databases/performance/start-system-monitor-windows.md)  
  
  
