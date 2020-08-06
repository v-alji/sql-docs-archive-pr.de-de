---
title: Gespeicherte Prozeduren (Ereigniskategorie) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Stored Procedures event category [SQL Server]
- SQL Server event classes, Stored Procedures event category
- event classes [SQL Server], Stored Procedures event category
ms.assetid: 71bebaa3-a05a-4695-b349-078cecd0949a
author: stevestein
ms.author: sstein
ms.openlocfilehash: df2e0d9a4c077ff16eba09bc5ebb6447d5d27595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726966"
---
# <a name="stored-procedures-event-category"></a><span data-ttu-id="b389e-102">Gespeicherte Prozeduren (Ereigniskategorie)</span><span class="sxs-lookup"><span data-stu-id="b389e-102">Stored Procedures Event Category</span></span>
  <span data-ttu-id="b389e-103">Die **Gespeicherte Prozeduren** -Ereigniskategorie enthält allgemeine Ereignisse für gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="b389e-103">The **Stored Procedures** event category contains general stored procedure events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b389e-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b389e-104">In This Section</span></span>  
  
|<span data-ttu-id="b389e-105">Thema</span><span class="sxs-lookup"><span data-stu-id="b389e-105">Topic</span></span>|<span data-ttu-id="b389e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b389e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b389e-107">RPC:Completed (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-107">RPC:Completed Event Class</span></span>](rpc-completed-event-class.md)|<span data-ttu-id="b389e-108">Gibt an, dass ein Remoteprozeduraufruf (RPC, Remote Procedure Call) abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-108">Indicates that a remote procedure call (RPC) has been completed.</span></span>|  
|[<span data-ttu-id="b389e-109">PreConnect:Completed (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-109">PreConnect:Completed Event Class</span></span>](preconnect-completed-event-class.md)|<span data-ttu-id="b389e-110">Gibt an, dass die Ausführung einer Klassifizierungsfunktion der Ressourcenkontrolle beendet wird.</span><span class="sxs-lookup"><span data-stu-id="b389e-110">Indicates when the Resource Governor classifier function finishes execution.</span></span>|  
|[<span data-ttu-id="b389e-111">PreConnect:Starting-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="b389e-111">PreConnect:Starting Event Class</span></span>](preconnect-starting-event-class.md)|<span data-ttu-id="b389e-112">Gibt an, dass die Ausführung einer Klassifizierungsfunktion der Ressourcenkontrolle gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b389e-112">Indicates when the Resource Governor classifier function starts execution.</span></span>|  
|[<span data-ttu-id="b389e-113">RPC Output Parameter (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-113">RPC Output Parameter Event Class</span></span>](rpc-output-parameter-event-class.md)|<span data-ttu-id="b389e-114">Verfolgt die Ausgabeparameterwerte von Remoteprozeduraufrufen nach deren Ausführung nach.</span><span class="sxs-lookup"><span data-stu-id="b389e-114">Traces the output parameter values of remote procedure calls after execution.</span></span>|  
|[<span data-ttu-id="b389e-115">RPC:Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-115">RPC:Starting Event Class</span></span>](rpc-starting-event-class.md)|<span data-ttu-id="b389e-116">Gibt an, dass ein Remoteprozeduraufruf gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b389e-116">Indicates that a remote procedure call is starting.</span></span>|  
|[<span data-ttu-id="b389e-117">SP:CacheHit (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-117">SP:CacheHit Event Class</span></span>](sp-cachehit-event-class.md)|<span data-ttu-id="b389e-118">Gibt an, dass sich die gespeicherte Prozedur im Cache befindet.</span><span class="sxs-lookup"><span data-stu-id="b389e-118">Indicates that the stored procedure is in the cache.</span></span>|  
|[<span data-ttu-id="b389e-119">SP:CacheInsert (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-119">SP:CacheInsert Event Class</span></span>](sp-cacheinsert-event-class.md)|<span data-ttu-id="b389e-120">Gibt an, dass die gespeicherte Prozedur in den Cache übertragen wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-120">Indicates that the stored procedure has been brought into the cache.</span></span>|  
|[<span data-ttu-id="b389e-121">SP:CacheMiss (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-121">SP:CacheMiss Event Class</span></span>](sp-cachemiss-event-class.md)|<span data-ttu-id="b389e-122">Gibt an, dass die gespeicherte Prozedur nicht im Cache gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-122">Indicates that the stored procedure was not found in the cache.</span></span>|  
|[<span data-ttu-id="b389e-123">SP:CacheRemove (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-123">SP:CacheRemove Event Class</span></span>](sp-cacheremove-event-class.md)|<span data-ttu-id="b389e-124">Gibt an, dass die gespeicherte Prozedur aus dem Cache entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-124">Indicates that the stored procedure has been removed from the cache.</span></span>|  
|[<span data-ttu-id="b389e-125">SP:Completed (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-125">SP:Completed Event Class</span></span>](sp-completed-event-class.md)|<span data-ttu-id="b389e-126">Gibt an, dass die Ausführung der gespeicherten Prozedur abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-126">Indicates that execution of the stored procedure has completed.</span></span>|  
|[<span data-ttu-id="b389e-127">SP:Recompile-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="b389e-127">SP:Recompile Event Class</span></span>](sp-recompile-event-class.md)|<span data-ttu-id="b389e-128">Gibt an, dass die gespeicherte Prozedur neu kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-128">Indicates that the stored procedure has been recompiled.</span></span>|  
|[<span data-ttu-id="b389e-129">SP:Starting (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-129">SP:Starting Event Class</span></span>](sp-starting-event-class.md)|<span data-ttu-id="b389e-130">Gibt an, dass die Ausführung der gespeicherten Prozedur beginnt.</span><span class="sxs-lookup"><span data-stu-id="b389e-130">Indicates that execution of the stored procedure is starting.</span></span>|  
|[<span data-ttu-id="b389e-131">SP:StmtCompleted (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="b389e-131">SP:StmtCompleted Event Class</span></span>](sp-stmtcompleted-event-class.md)|<span data-ttu-id="b389e-132">Gibt an, dass eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung in einer gespeicherten Prozedur abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-132">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>|  
|[<span data-ttu-id="b389e-133">SP:StmtStarting-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="b389e-133">SP:StmtStarting Event Class</span></span>](sp-stmtstarting-event-class.md)|<span data-ttu-id="b389e-134">Gibt an, dass eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung in einer gespeicherten Prozedur gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b389e-134">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b389e-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b389e-135">See Also</span></span>  
 <span data-ttu-id="b389e-136">[Erweiterte Ereignisse](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="b389e-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="b389e-137">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b389e-137">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
