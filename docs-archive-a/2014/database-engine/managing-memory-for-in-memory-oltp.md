---
title: Verwalten des Arbeitsspeichers für in-Memory OLTP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d82f21fa-6be1-4723-a72e-f2526fafd1b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90f9b638697d59a0a573a9a31c0a5faade23e870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723021"
---
# <a name="managing-memory-for-in-memory-oltp"></a><span data-ttu-id="d8ef6-102">Verwalten des Arbeitsspeichers für In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="d8ef6-102">Managing Memory for In-Memory OLTP</span></span>
  <span data-ttu-id="d8ef6-103">Speicheroptimierte Tabellen benötigen ausreichend verfügbaren Arbeitsspeicher, um alle Zeilen und Indizes im Arbeitsspeicher ablegen zu können.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-103">Memory-optimized tables require that sufficient memory exist to keep all of the rows and indexes in memory.</span></span> <span data-ttu-id="d8ef6-104">Da Arbeitsspeicher nicht unbegrenzt verfügbar ist, sollten Sie die Arbeitsspeichernutzung in Ihrem System kennen und effizient verwalten.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-104">Because memory is a finite resource, it is important that you understand and manage memory usage on your system.</span></span> <span data-ttu-id="d8ef6-105">Die Themen in diesem Abschnitt behandeln allgemeine Szenarien zur Speichernutzung und -verwaltung.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-105">The topics in this section cover common memory use and management scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8ef6-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d8ef6-106">In this section</span></span>  
  
|<span data-ttu-id="d8ef6-107">`Section`</span><span class="sxs-lookup"><span data-stu-id="d8ef6-107">Section</span></span>|<span data-ttu-id="d8ef6-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d8ef6-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8ef6-109">Schätzen der Arbeitsspeicheranforderungen speicheroptimierter Tabellen</span><span class="sxs-lookup"><span data-stu-id="d8ef6-109">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)|<span data-ttu-id="d8ef6-110">Schätzen der Arbeitsspeicher Anforderungen einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-110">Estimate a table's memory needs.</span></span>|  
|[<span data-ttu-id="d8ef6-111">Binden einer Datenbank mit speicheroptimierten Tabellen an einen Ressourcenpool</span><span class="sxs-lookup"><span data-stu-id="d8ef6-111">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)|<span data-ttu-id="d8ef6-112">Exemplarische Vorgehensweise, in der das Binden einer Datenbank an einen Ressourcenpool schrittweise erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-112">Step by step walkthrough to bind a database with a resource pool.</span></span>|  
|[<span data-ttu-id="d8ef6-113">Überwachung und Fehlerbehebung für die Arbeitsspeicherauslastung</span><span class="sxs-lookup"><span data-stu-id="d8ef6-113">Monitor and Troubleshoot Memory Usage</span></span>](../relational-databases/in-memory-oltp/monitor-and-troubleshoot-memory-usage.md)|<span data-ttu-id="d8ef6-114">Tools, die zur Überwachung der Arbeitsspeichernutzung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-114">Tools you can use to monitor your memory usage.</span></span> <span data-ttu-id="d8ef6-115">Zusätzlich werden Probleme bei zu hoher Speicherauslastung behandelt.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-115">Also covers troubleshooting if memory usage gets too high.</span></span>|  
|[<span data-ttu-id="d8ef6-116">Beheben von Problemen mit dem Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="d8ef6-116">Resolve Out Of Memory Issues</span></span>](../relational-databases/in-memory-oltp/resolve-out-of-memory-issues.md)|<span data-ttu-id="d8ef6-117">Schritte zum Beheben von OOM-Situationen (Out of Memory, nicht genügend Arbeitsspeicher).</span><span class="sxs-lookup"><span data-stu-id="d8ef6-117">Steps to recover from an OOM (Out of Memory) situation.</span></span>|  
|[<span data-ttu-id="d8ef6-118">Wiederherstellen einer Datenbank und Binden der Datenbank an einen Ressourcenpool</span><span class="sxs-lookup"><span data-stu-id="d8ef6-118">Restore a Database and Bind it to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md)|<span data-ttu-id="d8ef6-119">Schritte, durch die eine [!INCLUDE[hek_2](../includes/hek-2-md.md)] -Datenbank wiederhergestellt und an einen benannten Ressourcenpool gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-119">Steps to restore an [!INCLUDE[hek_2](../includes/hek-2-md.md)] database and bind it to a named resource pool.</span></span>|  
|[<span data-ttu-id="d8ef6-120">In-Memory OLTP-Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d8ef6-120">In-Memory OLTP Garbage Collection</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-garbage-collection.md)|<span data-ttu-id="d8ef6-121">Grundlegendes zur Funktionsweise der Garbage Collection bei gelöschten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-121">Understand how garbage collection operates on deleted rows.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8ef6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8ef6-122">See Also</span></span>  
 [<span data-ttu-id="d8ef6-123">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="d8ef6-123">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
