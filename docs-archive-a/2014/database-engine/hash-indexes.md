---
title: Hash Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f4bdc9c1-7922-4fac-8183-d11ec58fec4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8d1e3a5d92078cc2ec3fe7cd5b6d3fb5b47c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724909"
---
# <a name="hash-indexes"></a><span data-ttu-id="4f6a7-102">Hashindizes</span><span class="sxs-lookup"><span data-stu-id="4f6a7-102">Hash Indexes</span></span>
  <span data-ttu-id="4f6a7-103">Indizes werden als Einstiegspunkte für speicheroptimierte Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-103">Indexes are used as entry points for memory-optimized tables.</span></span> <span data-ttu-id="4f6a7-104">Das Lesen von Zeilen aus einer Tabelle erfordert einen Index, um Daten im Arbeitsspeicher zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-104">Reading rows from a table requires an index to locate the data in memory.</span></span>  
  
 <span data-ttu-id="4f6a7-105">Ein Hashindex besteht aus einer Sammlung von Buckets, die in einem Array organisiert sind.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-105">A hash index consists of a collection of buckets organized in an array.</span></span> <span data-ttu-id="4f6a7-106">Eine Hashfunktion ordnet Indexschlüssel den entsprechenden Buckets im Hashindex zu.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-106">A hash function maps index keys to corresponding buckets in the hash index.</span></span> <span data-ttu-id="4f6a7-107">Die folgende Abbildung zeigt drei Indexschlüssel, die drei verschiedenen Buckets im Hashindex zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-107">The following figure shows three index keys that are mapped to three different buckets in the hash index.</span></span> <span data-ttu-id="4f6a7-108">Zur Veranschaulichung lautet der Hashfunktionsname f(x).</span><span class="sxs-lookup"><span data-stu-id="4f6a7-108">For illustration purposes the hash function name is f(x).</span></span>  
  
 <span data-ttu-id="4f6a7-109">![Indexschlüssel, die unterschiedlichen Buckets zugeordnet sind.](../../2014/database-engine/media/hekaton-tables-2.gif "Indexschlüssel, die unterschiedlichen Buckets zugeordnet sind.")</span><span class="sxs-lookup"><span data-stu-id="4f6a7-109">![Index keys mapped to different buckets.](../../2014/database-engine/media/hekaton-tables-2.gif "Index keys mapped to different buckets.")</span></span>  
  
 <span data-ttu-id="4f6a7-110">Die Hashfunktion, die für Hashindizes verwendet wird, weist die folgenden Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="4f6a7-110">The hashing function used for hash indexes has the following characteristics:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4f6a7-111">hat eine Hashfunktion, die für alle Hashindizes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-111">has one hash function that is used for all hash indexes.</span></span>  
  
-   <span data-ttu-id="4f6a7-112">Die Hashfunktion ist deterministisch.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-112">The hash function is deterministic.</span></span> <span data-ttu-id="4f6a7-113">Der gleiche Indexschlüssel wird immer dem gleichen Bucket im Hashindex zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-113">The same index key is always mapped to the same bucket in the hash index.</span></span>  
  
-   <span data-ttu-id="4f6a7-114">Mehrere Indexschlüssel können dem gleichen Hashbucket zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-114">Multiple index keys may be mapped to the same hash bucket.</span></span>  
  
-   <span data-ttu-id="4f6a7-115">Die Hashfunktion ist ausgeglichen. Dies bedeutet, dass die Verteilung der Indexschlüsselwerte auf Hashbuckets üblicherweise einer Poisson-Verteilung entspricht.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-115">The hash function is balanced, meaning that the distribution of index key values over hash buckets typically follows a Poisson distribution.</span></span>  
  
     <span data-ttu-id="4f6a7-116">Eine Poisson-Verteilung ist keine gleichmäßige Verteilung.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-116">Poisson distribution is not an even distribution.</span></span> <span data-ttu-id="4f6a7-117">Indexschlüsselwerte werden in die Hashbuckets nicht gleichmäßig verteilt.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-117">Index key values are not evenly distributed in the hash buckets.</span></span> <span data-ttu-id="4f6a7-118">So führt beispielsweise eine Poisson-Verteilung von *n* unterschiedlichen Indexschlüsseln auf *n* Hashbuckets dazu, dass ungefähr ein Drittel der Buckets leer ist, ein Drittel der Buckets einen Indexschlüssel enthält und das letzte Drittel der Buckets zwei Indexschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-118">For example, a Poisson distribution of *n* distinct index keys over *n* hash buckets results in approximately one third empty buckets, one third of the buckets containing one index key, and the other third containing two index keys.</span></span> <span data-ttu-id="4f6a7-119">Eine kleine Anzahl von Buckets enthält mehr als zwei Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-119">A small number of buckets will contain more than two keys.</span></span>  
  
 <span data-ttu-id="4f6a7-120">Wenn zwei Indexschlüssel dem gleichen Hashbucket zugeordnet werden, gibt es einen Hashkonflikt.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-120">If two index keys are mapped to the same hash bucket, there is a hash collision.</span></span> <span data-ttu-id="4f6a7-121">Eine große Anzahl von Hashkonflikten kann sich auf die Leistung bei Lesevorgängen auswirken.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-121">A large number of hash collisions can have a performance impact on read operations.</span></span>  
  
 <span data-ttu-id="4f6a7-122">Die Hashindexstruktur im Arbeitsspeicher besteht aus einem Array von Speicherzeigern.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-122">The in-memory hash index structure consists of an array of memory pointers.</span></span> <span data-ttu-id="4f6a7-123">Jedes Bucket ist einem Offset in diesem Array zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-123">Each bucket maps to an offset in this array.</span></span> <span data-ttu-id="4f6a7-124">Jeder Bucket im Array zeigt auf die erste Zeile in diesem Hashbucket.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-124">Each bucket in the array points to the first row in that hash bucket.</span></span> <span data-ttu-id="4f6a7-125">Jede Zeile im Bucket zeigt auf die nächste Zeile, was eine Kette von Zeilen für jeden Hashbucket ergibt, wie in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-125">Each row in the bucket points to the next row, thus resulting in a chain of rows for each hash bucket, as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="4f6a7-126">![Die Hashindexstruktur im Arbeitsspeicher.](../../2014/database-engine/media/hekaton-tables-3.gif "Die Hashindexstruktur im Arbeitsspeicher.")</span><span class="sxs-lookup"><span data-stu-id="4f6a7-126">![The in-memory hash index structure.](../../2014/database-engine/media/hekaton-tables-3.gif "The in-memory hash index structure.")</span></span>  
  
 <span data-ttu-id="4f6a7-127">Die Abbildung weist drei Buckets mit Zeilen auf.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-127">The figure has three buckets with rows.</span></span> <span data-ttu-id="4f6a7-128">Der zweite Bucket von oben enthält die drei roten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-128">The second bucket from the top contains the three red rows.</span></span> <span data-ttu-id="4f6a7-129">Der vierte Bucket enthält die einzelne blaue Zeile.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-129">The fourth bucket contains the single blue row.</span></span> <span data-ttu-id="4f6a7-130">Der untere Bucket enthält die zwei grünen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-130">The bottom bucket contains the two green rows.</span></span> <span data-ttu-id="4f6a7-131">Diese können unterschiedliche Versionen derselben Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="4f6a7-131">These could be different versions of the same row.</span></span>  
  
 <span data-ttu-id="4f6a7-132">Weitere Informationen zu Indizes für speicheroptimierte Tabellen finden Sie unter [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4f6a7-132">For more information about indexes for memory-optimized tables, see [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f6a7-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f6a7-133">See Also</span></span>  
 [<span data-ttu-id="4f6a7-134">Indizes für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="4f6a7-134">Indexes on Memory-Optimized Tables</span></span>](../../2014/database-engine/indexes-on-memory-optimized-tables.md)  
  
  
