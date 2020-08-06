---
title: MSSQLSERVER_17884 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17884 (Database Engine error)
ms.assetid: 8d05ba05-3f71-4dc3-bd81-2ea5ac9fe843
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd5beca2a7dfd20afbf9eff196d89452ef3533d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718202"
---
# <a name="mssqlserver_17884"></a><span data-ttu-id="b9164-102">MSSQLSERVER_17884</span><span class="sxs-lookup"><span data-stu-id="b9164-102">MSSQLSERVER_17884</span></span>
    
## <a name="details"></a><span data-ttu-id="b9164-103">Details</span><span class="sxs-lookup"><span data-stu-id="b9164-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9164-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b9164-104">Product Name</span></span>|<span data-ttu-id="b9164-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9164-105">SQL Server</span></span>|  
|<span data-ttu-id="b9164-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b9164-106">Event ID</span></span>|<span data-ttu-id="b9164-107">17884</span><span class="sxs-lookup"><span data-stu-id="b9164-107">17884</span></span>|  
|<span data-ttu-id="b9164-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b9164-108">Event Source</span></span>|<span data-ttu-id="b9164-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b9164-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b9164-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b9164-110">Component</span></span>|<span data-ttu-id="b9164-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b9164-111">SQLEngine</span></span>|  
|<span data-ttu-id="b9164-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b9164-112">Symbolic Name</span></span>|<span data-ttu-id="b9164-113">SRV_SCHEDULER_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="b9164-113">SRV_SCHEDULER_DEADLOCK</span></span>|  
|<span data-ttu-id="b9164-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b9164-114">Message Text</span></span>|<span data-ttu-id="b9164-115">Neue Abfragen, die dem Prozess im %d-Knoten zugewiesen sind, wurden in den letzten %d Sekunden von keinem Arbeitsthread abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b9164-115">New queries assigned to process on Node %d have not been picked  up by a worker thread in the last %d seconds.</span></span> <span data-ttu-id="b9164-116">Die Ursache hierfür können blockierende Abfragen oder Abfragen mit langer Ausführungszeit sein, wodurch die Clientantwortzeit beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9164-116">Blocking or long-running queries can contribute to this condition, and may degrade client response time.</span></span> <span data-ttu-id="b9164-117">Erhöhen Sie mithilfe der Konfigurationsoption „Max. Anzahl von Arbeitsthreads“ die Anzahl zulässiger Threads, oder optimieren Sie aktuell ausgeführte Abfragen.</span><span class="sxs-lookup"><span data-stu-id="b9164-117">Use the "max worker threads" configuration option to increase number  of allowable threads, or optimize current running queries.</span></span>  <span data-ttu-id="b9164-118">SQL-Prozessnutzung: %d%%.</span><span class="sxs-lookup"><span data-stu-id="b9164-118">SQL Process Utilization: %d%%.</span></span> <span data-ttu-id="b9164-119">Leerlauf des Systems: %d%%.</span><span class="sxs-lookup"><span data-stu-id="b9164-119">System Idle: %d%%.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9164-120">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b9164-120">Explanation</span></span>  
 <span data-ttu-id="b9164-121">In den Zeitplanungsmodulen gibt es kein Anzeichen von Fortschritt. Die Ursache können Deadlocks sein, bei denen keine Threads fortgeführt werden können und/oder keine neue Arbeit aufgenommen und verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9164-121">There is no sign of progress in each of the schedulers and could be caused by deadlocks where none of the threads can advance and/or no new work can be picked up and processed.</span></span> <span data-ttu-id="b9164-122">Wenn die Prozessnutzung niedrig ist, können andere Prozesse auf dem Computer möglicherweise dazu führen, dass auf die Serverprozess-CPU nicht mehr zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9164-122">If process utilization is low then other processes on the machine may be causing the server process CPU starvation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9164-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b9164-123">User Action</span></span>  
 <span data-ttu-id="b9164-124">Bestimmen Sie die Ursache für die Blockierung und den fehlenden Fortschritt, und lösen Sie die Situation entsprechend.</span><span class="sxs-lookup"><span data-stu-id="b9164-124">Determine why there is blocking and no progress being made and resolve situation accordingly.</span></span> <span data-ttu-id="b9164-125">Wenn die Prozessnutzung niedrig ist, prüfen Sie die Systemlast, die von anderen Prozessen verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="b9164-125">If process utilization is low check the load on the system caused by other processes.</span></span>  
  
  
