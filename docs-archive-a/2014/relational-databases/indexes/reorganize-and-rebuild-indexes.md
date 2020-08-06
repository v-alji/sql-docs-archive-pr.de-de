---
title: Neuorganisieren und Neuerstellen von Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.fragmentation.f1
- sql12.swb.index.reorg.f1
- sql12.swb.index.rebuild.f1
helpviewer_keywords:
- large object defragmenting
- indexes [SQL Server], reorganizing
- index reorganization [SQL Server]
- reorganizing indexes
- defragmenting large object data types
- index fragmentation [SQL Server]
- index rebuilding [SQL Server]
- rebuilding indexes
- indexes [SQL Server], rebuilding
- defragmenting indexes
- nonclustered indexes [SQL Server], defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
- LOB data [SQL Server], defragmenting
- clustered indexes, defragmenting
ms.assetid: a28c684a-c4e9-4b24-a7ae-e248808b31e9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c00f2128bb4c54064511ffff9e8929c9faf4d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723873"
---
# <a name="reorganize-and-rebuild-indexes"></a><span data-ttu-id="61a84-102">Neuorganisieren und Neuerstellen von Indizes</span><span class="sxs-lookup"><span data-stu-id="61a84-102">Reorganize and Rebuild Indexes</span></span>
  <span data-ttu-id="61a84-103">In diesem Thema wird beschrieben, wie Sie einen fragmentierten Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)] neu organisieren oder neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61a84-103">This topic describes how to reorganize or rebuild a fragmented index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="61a84-104">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] verwaltet Indizes automatisch, wenn Einfüge-, Update- oder Löschvorgänge an den zugrunde liegenden Daten vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-104">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically maintains indexes whenever insert, update, or delete operations are made to the underlying data.</span></span> <span data-ttu-id="61a84-105">Im Lauf der Zeit können diese Änderungen dazu führen, dass die Informationen im Index in der Datenbank verstreut (fragmentiert) werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-105">Over time these modifications can cause the information in the index to become scattered in the database (fragmented).</span></span> <span data-ttu-id="61a84-106">Fragmentierung liegt vor, wenn Indizes über Seiten verfügen, in denen die logische Reihenfolge (basierend auf dem Schlüsselwert) nicht der physischen Reihenfolge in der Datendatei entspricht.</span><span class="sxs-lookup"><span data-stu-id="61a84-106">Fragmentation exists when indexes have pages in which the logical ordering, based on the key value, does not match the physical ordering inside the data file.</span></span> <span data-ttu-id="61a84-107">Hochgradig fragmentierte Indizes können die Abfrageleistung beeinträchtigen und dazu führen, dass Ihre Anwendung nur langsam reagiert.</span><span class="sxs-lookup"><span data-stu-id="61a84-107">Heavily fragmented indexes can degrade query performance and cause your application to respond slowly.</span></span>  
  
 <span data-ttu-id="61a84-108">Sie können die Indexfragmentierung durch Neuorganisieren oder Neuerstellen eines Indexes beheben.</span><span class="sxs-lookup"><span data-stu-id="61a84-108">You can remedy index fragmentation by reorganizing or rebuilding an index.</span></span> <span data-ttu-id="61a84-109">Für partitionierte Indizes, die auf Grundlage eines Partitionsschemas erstellt wurden, können beide Methoden für einen vollständigen Index oder für eine einzelne Partition eines Indexes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-109">For partitioned indexes built on a partition scheme, you can use either of these methods on a complete index or a single partition of an index.</span></span> <span data-ttu-id="61a84-110">Beim Neuerstellen eines Indexes wird der Index gelöscht und neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="61a84-110">Rebuilding an index drops and re-creates the index.</span></span> <span data-ttu-id="61a84-111">Bei diesem Vorgang wird die Fragmentierung entfernt, Speicherplatz wird freigegeben, indem die Seiten auf der Grundlage der angegebenen oder vorhandenen Füllfaktoreinstellung komprimiert werden, und die Indexzeilen werden in aufeinanderfolgenden Seiten neu geordnet.</span><span class="sxs-lookup"><span data-stu-id="61a84-111">This removes fragmentation, reclaims disk space by compacting the pages based on the specified or existing fill factor setting, and reorders the index rows in contiguous pages.</span></span> <span data-ttu-id="61a84-112">Wenn ALL angegeben ist, werden alle Indizes der Tabelle in einer einzelnen Transaktion gelöscht und neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="61a84-112">When ALL is specified, all indexes on the table are dropped and rebuilt in a single transaction.</span></span> <span data-ttu-id="61a84-113">Das Neuorganisieren eines Indexes beansprucht minimale Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="61a84-113">Reorganizing an index uses minimal system resources.</span></span> <span data-ttu-id="61a84-114">Dabei wird die Blattebene von gruppierten und nicht gruppierten Indizes in Tabellen und Sichten defragmentiert, indem die Blattebenenseiten physisch neu geordnet werden, damit sie mit der logischen Reihenfolge der Blattknoten von links nach rechts übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="61a84-114">It defragments the leaf level of clustered and nonclustered indexes on tables and views by physically reordering the leaf-level pages to match the logical, left to right, order of the leaf nodes.</span></span> <span data-ttu-id="61a84-115">Durch das Neuorganisieren werden die Indexseiten auch komprimiert.</span><span class="sxs-lookup"><span data-stu-id="61a84-115">Reorganizing also compacts the index pages.</span></span> <span data-ttu-id="61a84-116">Die Komprimierung basiert auf dem vorhandenen Füllfaktorwert.</span><span class="sxs-lookup"><span data-stu-id="61a84-116">Compaction is based on the existing fill factor value.</span></span>  
  
 <span data-ttu-id="61a84-117">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="61a84-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="61a84-118">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="61a84-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="61a84-119">Erkennen der Fragmentierung</span><span class="sxs-lookup"><span data-stu-id="61a84-119">Detecting Fragmentation</span></span>](#Fragmentation)  
  
     [<span data-ttu-id="61a84-120">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="61a84-120">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="61a84-121">Security</span><span class="sxs-lookup"><span data-stu-id="61a84-121">Security</span></span>](#Security)  
  
-   <span data-ttu-id="61a84-122">**Überprüfen der Fragmentierung eines Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="61a84-122">**To check the fragmentation of an index, using:**</span></span>  
  
     [<span data-ttu-id="61a84-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61a84-123">SQL Server Management Studio</span></span>](#SSMSProcedureFrag)  
  
     [<span data-ttu-id="61a84-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61a84-124">Transact-SQL</span></span>](#TsqlProcedureFrag)  
  
-   <span data-ttu-id="61a84-125">**Neuorganisieren oder Neuerstellen eines Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="61a84-125">**To reorganize or rebuild an index, using:**</span></span>  
  
     [<span data-ttu-id="61a84-126">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61a84-126">SQL Server Management Studio</span></span>](#SSMSProcedureReorg)  
  
     [<span data-ttu-id="61a84-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61a84-127">Transact-SQL</span></span>](#TsqlProcedureReorg)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61a84-128">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="61a84-128">Before You Begin</span></span>  
  
###  <a name="detecting-fragmentation"></a><a name="Fragmentation"></a><span data-ttu-id="61a84-129">Erkennen der Fragmentierung</span><span class="sxs-lookup"><span data-stu-id="61a84-129">Detecting Fragmentation</span></span>  
 <span data-ttu-id="61a84-130">Der erste Schritt bei der Entscheidung für eine Defragmentierungsmethode besteht im Analysieren des Indexes, um den Fragmentierungsgrad zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="61a84-130">The first step in deciding which defragmentation method to use is to analyze the index to determine the degree of fragmentation.</span></span> <span data-ttu-id="61a84-131">Mithilfe der Systemfunktion [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) können Sie die Fragmentierung in einem bestimmten Index, allen Indizes in einer Tabelle oder indizierten Sicht, allen Indizes in einer Datenbank oder allen Indizes in allen Datenbanken erkennen.</span><span class="sxs-lookup"><span data-stu-id="61a84-131">By using the system function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), you can detect fragmentation in a specific index, all indexes on a table or indexed view, all indexes in a database, or all indexes in all databases.</span></span> <span data-ttu-id="61a84-132">Für partitionierte Indizes stellt **sys.dm_db_index_physical_stats** außerdem Fragmentierungsinformationen für jede Partition bereit.</span><span class="sxs-lookup"><span data-stu-id="61a84-132">For partitioned indexes, **sys.dm_db_index_physical_stats** also provides fragmentation information for each partition.</span></span>  
  
 <span data-ttu-id="61a84-133">Das durch die Funktion **sys.dm_db_index_physical_stats** zurückgegebene Resultset enthält die folgenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="61a84-133">The result set returned by the **sys.dm_db_index_physical_stats** function includes the following columns.</span></span>  
  
|<span data-ttu-id="61a84-134">Spalte</span><span class="sxs-lookup"><span data-stu-id="61a84-134">Column</span></span>|<span data-ttu-id="61a84-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61a84-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="61a84-136">**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="61a84-136">**avg_fragmentation_in_percent**</span></span>|<span data-ttu-id="61a84-137">Der Prozentsatz der logischen Fragmentierung (falsche Reihenfolge der Seiten in einem Index).</span><span class="sxs-lookup"><span data-stu-id="61a84-137">The percent of logical fragmentation (out-of-order pages in the index).</span></span>|  
|<span data-ttu-id="61a84-138">**fragment_count**</span><span class="sxs-lookup"><span data-stu-id="61a84-138">**fragment_count**</span></span>|<span data-ttu-id="61a84-139">Die Anzahl der Fragmente (physisch aufeinanderfolgende Blattseiten) im Index.</span><span class="sxs-lookup"><span data-stu-id="61a84-139">The number of fragments (physically consecutive leaf pages) in the index.</span></span>|  
|<span data-ttu-id="61a84-140">**avg_fragment_size_in_pages**</span><span class="sxs-lookup"><span data-stu-id="61a84-140">**avg_fragment_size_in_pages**</span></span>|<span data-ttu-id="61a84-141">Durchschnittliche Anzahl der Seiten in einem Fragment in einem Index.</span><span class="sxs-lookup"><span data-stu-id="61a84-141">Average number of pages in one fragment in an index.</span></span>|  
  
 <span data-ttu-id="61a84-142">Nachdem der Grad der Fragmentierung bekannt ist, verwenden Sie die folgenden Tabelle, um die beste Methode zum Beheben der Fragmentierung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="61a84-142">After the degree of fragmentation is known, use the following table to determine the best method to correct the fragmentation.</span></span>  
  
|<span data-ttu-id="61a84-143">**avg_fragmentation_in_percent** -Wert</span><span class="sxs-lookup"><span data-stu-id="61a84-143">**avg_fragmentation_in_percent** value</span></span>|<span data-ttu-id="61a84-144">Korrigierende Anweisung</span><span class="sxs-lookup"><span data-stu-id="61a84-144">Corrective statement</span></span>|  
|-----------------------------------------------|--------------------------|  
|<span data-ttu-id="61a84-145">> 5% und \< = 30%</span><span class="sxs-lookup"><span data-stu-id="61a84-145">> 5% and \< = 30%</span></span>|<span data-ttu-id="61a84-146">ALTER INDEX REORGANIZE</span><span class="sxs-lookup"><span data-stu-id="61a84-146">ALTER INDEX REORGANIZE</span></span>|  
|<span data-ttu-id="61a84-147">> 30%</span><span class="sxs-lookup"><span data-stu-id="61a84-147">> 30%</span></span>|<span data-ttu-id="61a84-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61a84-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span></span>|

<span data-ttu-id="61a84-149"><sup>1</sup> Das Neuerstellen eines Indexes kann online oder offline erfolgen.</span><span class="sxs-lookup"><span data-stu-id="61a84-149"><sup>1</sup> Rebuilding an index can be executed online or offline.</span></span> <span data-ttu-id="61a84-150">Das Neuorganisieren eines Indexes erfolgt immer online.</span><span class="sxs-lookup"><span data-stu-id="61a84-150">Reorganizing an index is always executed online.</span></span> <span data-ttu-id="61a84-151">Damit eine Verfügbarkeit ähnlich der Neuorganisierungsoption erreicht wird, sollten Indizes online neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-151">To achieve availability similar to the reorganize option, you should rebuild indexes online.</span></span>  
  
> [!TIP]
> <span data-ttu-id="61a84-152">Diese Werte dienen als grobe Richtlinie, um den Punkt zu bestimmen, an dem Sie zwischen `ALTER INDEX REORGANIZE` und `ALTER INDEX REBUILD` wechseln sollten.</span><span class="sxs-lookup"><span data-stu-id="61a84-152">These values provide a rough guideline for determining the point at which you should switch between `ALTER INDEX REORGANIZE` and `ALTER INDEX REBUILD`.</span></span> <span data-ttu-id="61a84-153">Die Istwerte können jedoch von Fall zu Fall unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="61a84-153">However, the actual values may vary from case to case.</span></span> <span data-ttu-id="61a84-154">Es ist wichtig, dass Sie experimentieren, um den besten Schwellenwert für Ihre Umgebung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="61a84-154">It is important that you experiment to determine the best threshold for your environment.</span></span> <span data-ttu-id="61a84-155">Wird ein bestimmter Index beispielsweise hauptsächlich für Überprüfungsvorgänge verwendet, kann ein Entfernen der Fragmentierung die Leistung dieser Vorgänge verbessern.</span><span class="sxs-lookup"><span data-stu-id="61a84-155">For example, if a given index is used mainly for scan operations, removing fragmentation can improve performance of these operations.</span></span> <span data-ttu-id="61a84-156">Für Indizes, die in erster Linie für Suchvorgänge verwendet werden, fällt der Leistungsvorteil weniger auf.</span><span class="sxs-lookup"><span data-stu-id="61a84-156">The performance benefit is less noticeable for indexes that are used primarily for seek operations.</span></span> <span data-ttu-id="61a84-157">Ähnliches gilt für das Entfernen der Fragmentierung in einem Heap (einer Tabelle ohne gruppierten Index). Auch dies ist besonders nützlich für Überprüfungsvorgänge für nicht gruppierte Indizes, wirkt sich aber kaum auf Suchvorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="61a84-157">Similarly, removing fragmentation in a heap (a table with no clustered index) is especially useful for nonclustered index scan operations, but has little effect in lookup operations.</span></span>

<span data-ttu-id="61a84-158">Bei sehr niedrigen Fragmentierungsniveaus (unter 5 Prozent) sollten diese Befehle normalerweise nicht eingesetzt werden, da die Vorteile des Entfernens einer so geringen Fragmentierung die Kosten für das Neuorganisieren und Neuerstellen des Indexes nicht aufwiegen.</span><span class="sxs-lookup"><span data-stu-id="61a84-158">Very low levels of fragmentation (less than 5 percent) should typically not be addressed by either of these commands, because the benefit from removing such a small amount of fragmentation is almost always vastly outweighed by the cost of reorganizing or rebuilding the index.</span></span> 

> [!NOTE]
> <span data-ttu-id="61a84-159">Durch das erneute Erstellen oder Organisieren kleiner Indizes lässt sich die Fragmentierung häufig nicht verringern.</span><span class="sxs-lookup"><span data-stu-id="61a84-159">Rebuilding or reorganizing small indexes often does not reduce fragmentation.</span></span> <span data-ttu-id="61a84-160">Die Seiten kleiner Indizes werden manchmal in gemischten Blöcken gespeichert.</span><span class="sxs-lookup"><span data-stu-id="61a84-160">The pages of small indexes are sometimes stored on mixed extents.</span></span> <span data-ttu-id="61a84-161">Da gemischte Blöcke von bis zu acht Objekten gemeinsam genutzt werden, lässt sich die Fragmentierung in einem kleinen Index durch die erneute Erstellung oder Organisation des Indexes möglicherweise nicht verringern.</span><span class="sxs-lookup"><span data-stu-id="61a84-161">Mixed extents are shared by up to eight objects, so the fragmentation in a small index might not be reduced after reorganizing or rebuilding it.</span></span>

### <a name="index-defragmentation-considerations"></a><span data-ttu-id="61a84-162">Überlegungen zur Indexdefragmentierung</span><span class="sxs-lookup"><span data-stu-id="61a84-162">Index defragmentation considerations</span></span>
<span data-ttu-id="61a84-163">Bei Zutreffen bestimmter Bedingungen führt eine Neuerstellung eines gruppierten Indexes dazu, dass alle nicht gruppierten Indizes, in denen auf den Gruppierungsschlüssel verwiesen wird, automatisch neu erstellt werden, wenn die physischen oder logischen IDs geändert werden müssen, die sich in den nicht gruppierten Indexdatensätzen befinden.</span><span class="sxs-lookup"><span data-stu-id="61a84-163">Under certain conditions, rebuilding a clustered index will automatically rebuild any nonclustered index that reference the clustering key, if the physical or logical identifiers contained in the nonclustered index records needs to change.</span></span>

<span data-ttu-id="61a84-164">In diesen Szenarien wird erzwungen, dass alle nicht gruppierten Indizes automatisch für eine Tabelle neu erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="61a84-164">Scenarios that force all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="61a84-165">Erstellen eines gruppierten Indexes für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="61a84-165">Creating a clustered index on a table</span></span>
-  <span data-ttu-id="61a84-166">Entfernen eines gruppierten Indexes, was zur Folge hat, dass die Tabelle als Heap gespeichert wird</span><span class="sxs-lookup"><span data-stu-id="61a84-166">Removing a clustered index, causing the table to be stored as a heap</span></span>
-  <span data-ttu-id="61a84-167">Ändern des Gruppierungsschlüssels, um Spalten einzubeziehen oder auszuschließen</span><span class="sxs-lookup"><span data-stu-id="61a84-167">Changing the clustering key to include or exclude columns</span></span>

<span data-ttu-id="61a84-168">In diesen Szenarien ist es nicht erforderlich, dass alle nicht gruppierten Indizes automatisch für eine Tabelle neu erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="61a84-168">Scenarios that do not require all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="61a84-169">Neuerstellen eines eindeutigen gruppierten Indexes</span><span class="sxs-lookup"><span data-stu-id="61a84-169">Rebuilding a unique clustered index</span></span>
-  <span data-ttu-id="61a84-170">Neuerstellen eines nicht eindeutigen gruppierten Indexes</span><span class="sxs-lookup"><span data-stu-id="61a84-170">Rebuilding a non-unique clustered index</span></span>
-  <span data-ttu-id="61a84-171">Ändern des Indexschemas, beispielsweise Anwenden eines Partitionierungsschemas auf einen gruppierten Index oder Verschieben des gruppierten Indexes in eine andere Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="61a84-171">Changing the index schema, such as applying a partitioning scheme to a clustered index or moving the clustered index to a different filegroup</span></span>
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="61a84-172">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="61a84-172">Limitations and Restrictions</span></span>  
  
<span data-ttu-id="61a84-173">Indizes mit mehr als 128 Blöcken werden in zwei getrennten Phasen neu erstellt: der logischen und der physischen Phase.</span><span class="sxs-lookup"><span data-stu-id="61a84-173">Indexes with more than 128 extents are rebuilt in two separate phases: logical and physical.</span></span> <span data-ttu-id="61a84-174">In der logischen Phase werden die vorhandenen Zuordnungseinheiten, die vom Index verwendet werden, für die Aufhebung der Zuordnung markiert, die Datenzeilen werden kopiert und sortiert und dann in neue Zuordnungseinheiten verschoben, die erstellt werden, um den neu erstellten Index zu speichern.</span><span class="sxs-lookup"><span data-stu-id="61a84-174">In the logical phase, the existing allocation units used by the index are marked for deallocation, the data rows are copied and sorted, then moved to new allocation units created to store the rebuilt index.</span></span> <span data-ttu-id="61a84-175">In der physischen Phase werden die zuvor für die Aufhebung der Zuordnung markierten Zuordnungseinheiten in kurzen Transaktionen physisch gelöscht, die im Hintergrund ausgeführt werden und nicht viele Sperren benötigen.</span><span class="sxs-lookup"><span data-stu-id="61a84-175">In the physical phase, the allocation units previously marked for deallocation are physically dropped in short transactions that happen in the background, and do not require many locks.</span></span> <span data-ttu-id="61a84-176">Weitere Informationen zu Blöcken finden Sie im [Handbuch zur Architektur von Seiten und Blöcken](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span><span class="sxs-lookup"><span data-stu-id="61a84-176">For more information about extents, refer to the [Pages and Extents Architecture Guide](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span></span>

<span data-ttu-id="61a84-177">Die `ALTER INDEX REORGANIZE` -Anweisung erfordert, dass die Datendatei mit dem Index über Platz verfügt, da der Vorgang temporäre Arbeitsseiten nur in der gleichen Datei zuordnen kann, nicht in einer anderen Datei der Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="61a84-177">The `ALTER INDEX REORGANIZE` statement requires the data file containing the index to have space available, because the operation can only allocate temporary work pages on the same file, not another file within the filegroup.</span></span> <span data-ttu-id="61a84-178">Selbst wenn in einer Dateigruppe leere Seiten verfügbar sind, kann für den Benutzer daher trotzdem Fehler 1105 auftreten: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span><span class="sxs-lookup"><span data-stu-id="61a84-178">So although the filegroup might have free pages available, the user can still encounter error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span></span>

<span data-ttu-id="61a84-179">Das Erstellen bzw. Neuerstellen von nicht ausgerichteten Indizes für eine Tabelle mit mehr als 1.000 Partitionen ist möglich, wird aber nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="61a84-179">Creating and rebuilding non-aligned indexes on a table with more than 1,000 partitions is possible, but is not recommended.</span></span> <span data-ttu-id="61a84-180">Dies hätte Leistungseinbußen oder eine zu hohe Speicherauslastung während der Vorgänge zur Folge.</span><span class="sxs-lookup"><span data-stu-id="61a84-180">Doing so may cause degraded performance or excessive memory consumption during these operations.</span></span>

<span data-ttu-id="61a84-181">Ein Index kann nicht neu organisiert oder neu erstellt werden, wenn die Dateigruppe, in der er enthalten ist, eine Offline- oder schreibgeschützte Dateigruppe ist.</span><span class="sxs-lookup"><span data-stu-id="61a84-181">An index cannot be reorganized or rebuilt if the filegroup in which it is located is offline or set to read-only.</span></span> <span data-ttu-id="61a84-182">Wenn das Schlüsselwort `ALL` angegeben ist und mindestens ein Index in einer Offline- oder schreibgeschützten Dateigruppe enthalten ist, erzeugt die Anweisung einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="61a84-182">When the keyword `ALL` is specified and one or more indexes are in an offline or read-only filegroup, the statement fails.</span></span>
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61a84-183">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="61a84-183">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="61a84-184">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="61a84-184">Permissions</span></span>  
 <span data-ttu-id="61a84-185">Erfordert die `ALTER`-Berechtigung für die Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="61a84-185">Requires `ALTER` permission on the table or view.</span></span> <span data-ttu-id="61a84-186">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="61a84-186">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureFrag"></a> <span data-ttu-id="61a84-187">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61a84-187">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="61a84-188">So überprüfen Sie die Fragmentierung eines Indexes</span><span class="sxs-lookup"><span data-stu-id="61a84-188">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="61a84-189">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, in der Sie die Fragmentierung eines Indexes überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-189">In Object Explorer, Expand the database that contains the table on which you want to check an index's fragmentation.</span></span>  
  
2.  <span data-ttu-id="61a84-190">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="61a84-190">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="61a84-191">Erweitern Sie die Tabelle, in der Sie die Fragmentierung eines Indexes überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-191">Expand the table on which you want to check an index's fragmentation.</span></span>  
  
4.  <span data-ttu-id="61a84-192">Erweitern Sie den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="61a84-192">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="61a84-193">Klicken Sie mit der rechten Maustaste auf den Index, für den Sie die Fragmentierung überprüfen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="61a84-193">Right-click the index of which you want to check the fragmentation and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="61a84-194">Wählen Sie unter **Seite auswählen**die Option **Fragmentierung**aus.</span><span class="sxs-lookup"><span data-stu-id="61a84-194">Under **Select a page**, select **Fragmentation**.</span></span>  
  
     <span data-ttu-id="61a84-195">Die folgenden Informationen sind auf der Seite **Fragmentierung** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="61a84-195">The following information is available on the **Fragmentation** page:</span></span>  
  
     <span data-ttu-id="61a84-196">**Seitenfüllgrad**</span><span class="sxs-lookup"><span data-stu-id="61a84-196">**Page fullness**</span></span>  
     <span data-ttu-id="61a84-197">Gibt den durchschnittlichen Füllgrad der Indexseiten als Prozentwert an.</span><span class="sxs-lookup"><span data-stu-id="61a84-197">Indicates average fullness of the index pages, as a percentage.</span></span> <span data-ttu-id="61a84-198">100 % bedeutet, dass die Indexseiten vollständig gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="61a84-198">100% means the index pages are completely full.</span></span> <span data-ttu-id="61a84-199">50 % heißt, dass jede Indexseite im Durchschnitt zur Hälfte gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="61a84-199">50% means that, on average, each index page is half full.</span></span>  
  
     <span data-ttu-id="61a84-200">**Fragmentierung gesamt**</span><span class="sxs-lookup"><span data-stu-id="61a84-200">**Total fragmentation**</span></span>  
     <span data-ttu-id="61a84-201">Prozentwert der logischen Fragmentierung.</span><span class="sxs-lookup"><span data-stu-id="61a84-201">The logical fragmentation percentage.</span></span> <span data-ttu-id="61a84-202">Dieser Wert gibt die Anzahl der Seiten in einem Index an, die nicht in Reihenfolge gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="61a84-202">This indicates the number of pages in an index that are not stored in order.</span></span>  
  
     <span data-ttu-id="61a84-203">**Durchschnittliche Zeilengröße**</span><span class="sxs-lookup"><span data-stu-id="61a84-203">**Average row size**</span></span>  
     <span data-ttu-id="61a84-204">Durchschnittliche Größe einer Zeile auf Blattebene.</span><span class="sxs-lookup"><span data-stu-id="61a84-204">The average size of a leaf level row.</span></span>  
  
     <span data-ttu-id="61a84-205">**Tiefe**</span><span class="sxs-lookup"><span data-stu-id="61a84-205">**Depth**</span></span>  
     <span data-ttu-id="61a84-206">Anzahl der Ebenen im Index, einschließlich der Blattebene.</span><span class="sxs-lookup"><span data-stu-id="61a84-206">The number of levels in the index, including the leaf level.</span></span>  
  
     <span data-ttu-id="61a84-207">**Weitergeleitete Datensätze**</span><span class="sxs-lookup"><span data-stu-id="61a84-207">**Forwarded records**</span></span>  
     <span data-ttu-id="61a84-208">Anzahl der Datensätze in einem Heap, die Weiterleitungszeiger auf einen anderen Datenspeicherort besitzen.</span><span class="sxs-lookup"><span data-stu-id="61a84-208">The number of records in a heap that have forward pointers to another data location.</span></span> <span data-ttu-id="61a84-209">(Dieser Status tritt während eines Updates auf, wenn nicht genügend Speicherplatz vorhanden ist, um die neue Zeile am ursprünglichen Speicherort zu speichern.)</span><span class="sxs-lookup"><span data-stu-id="61a84-209">(This state occurs during an update, when there is not enough room to store the new row in the original location.)</span></span>  
  
     <span data-ttu-id="61a84-210">**Inaktive Zeilen**</span><span class="sxs-lookup"><span data-stu-id="61a84-210">**Ghost rows**</span></span>  
     <span data-ttu-id="61a84-211">Anzahl der Zeilen, die als gelöscht markiert sind, aber noch nicht entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="61a84-211">The number of rows that are marked as deleted but not yet removed.</span></span> <span data-ttu-id="61a84-212">Diese Zeilen werden von einem Bereinigungsthread entfernt, wenn der Server nicht ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="61a84-212">These rows will be removed by a clean-up thread, when the server is not busy.</span></span> <span data-ttu-id="61a84-213">Dieser Wert schließt keine Zeilen ein, die aufgrund einer ausstehenden Momentaufnahme-Isolationstransaktion beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-213">This value does not include rows that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
     <span data-ttu-id="61a84-214">**Indextyp**</span><span class="sxs-lookup"><span data-stu-id="61a84-214">**Index type**</span></span>  
     <span data-ttu-id="61a84-215">Der Indextyp.</span><span class="sxs-lookup"><span data-stu-id="61a84-215">The type of index.</span></span> <span data-ttu-id="61a84-216">Mögliche Werte sind **Gruppierter Index**, **Nicht gruppierter Index**und **Primär-XML**.</span><span class="sxs-lookup"><span data-stu-id="61a84-216">Possible values are **Clustered index**, **Nonclustered index**, and **Primary XML**.</span></span> <span data-ttu-id="61a84-217">Tabellen können auch als Heap gespeichert werden (ohne Indizes). Dann kann aber diese Seite Indexeigenschaften nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-217">Tables can also be stored as a heap (without indexes), but then this Index Properties page cannot be opened.</span></span>  
  
     <span data-ttu-id="61a84-218">**Zeilen auf Blattebene**</span><span class="sxs-lookup"><span data-stu-id="61a84-218">**Leaf-level rows**</span></span>  
     <span data-ttu-id="61a84-219">Anzahl der Zeilen auf Blattebene.</span><span class="sxs-lookup"><span data-stu-id="61a84-219">The number of leaf level rows.</span></span>  
  
     <span data-ttu-id="61a84-220">**Maximale Zeilengröße**</span><span class="sxs-lookup"><span data-stu-id="61a84-220">**Maximum row size**</span></span>  
     <span data-ttu-id="61a84-221">Maximale Größe von Zeilen auf Blattebene.</span><span class="sxs-lookup"><span data-stu-id="61a84-221">The maximum leaf-level row size.</span></span>  
  
     <span data-ttu-id="61a84-222">**Minimale Zeilengröße**</span><span class="sxs-lookup"><span data-stu-id="61a84-222">**Minimum row size**</span></span>  
     <span data-ttu-id="61a84-223">Minimale Größe von Zeilen auf Blattebene.</span><span class="sxs-lookup"><span data-stu-id="61a84-223">The minimum leaf-level row size.</span></span>  
  
     <span data-ttu-id="61a84-224">**Seiten**</span><span class="sxs-lookup"><span data-stu-id="61a84-224">**Pages**</span></span>  
     <span data-ttu-id="61a84-225">Gesamtanzahl der Datenseiten.</span><span class="sxs-lookup"><span data-stu-id="61a84-225">The total number of data pages.</span></span>  
  
     <span data-ttu-id="61a84-226">**Partitions-ID**</span><span class="sxs-lookup"><span data-stu-id="61a84-226">**Partition ID**</span></span>  
     <span data-ttu-id="61a84-227">Partitions-ID der B-Struktur, die den Index enthält.</span><span class="sxs-lookup"><span data-stu-id="61a84-227">The partition ID of the b-tree containing the index.</span></span>  
  
     <span data-ttu-id="61a84-228">**Inaktive Zeilen (Version)**</span><span class="sxs-lookup"><span data-stu-id="61a84-228">**Version ghost rows**</span></span>  
     <span data-ttu-id="61a84-229">Die Anzahl inaktiver Datensätze, die aufgrund einer ausstehenden Momentaufnahme-Isolationstransaktion beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="61a84-229">The number of ghost records that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureFrag"></a> <span data-ttu-id="61a84-230">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61a84-230">Using Transact-SQL</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="61a84-231">So überprüfen Sie die Fragmentierung eines Indexes</span><span class="sxs-lookup"><span data-stu-id="61a84-231">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="61a84-232">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="61a84-232">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61a84-233">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="61a84-233">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61a84-234">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="61a84-234">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find the average fragmentation percentage of all indexes  
    -- in the HumanResources.Employee table.   
    SELECT a.index_id, name, avg_fragmentation_in_percent  
    FROM sys.dm_db_index_physical_stats (DB_ID(N'AdventureWorks2012'), OBJECT_ID(N'HumanResources.Employee'), NULL, NULL, NULL) AS a  
        JOIN sys.indexes AS b ON a.object_id = b.object_id AND a.index_id = b.index_id;   
    GO  
    ```  
  
     <span data-ttu-id="61a84-235">Das von der obigen Anweisung zurückgegebene Resultset kann in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="61a84-235">The statement above might return a result set similar to the following.</span></span>  
  
    ```  
    index_id    name                                                  avg_fragmentation_in_percent  
    ----------- ----------------------------------------------------- ----------------------------  
    1           PK_Employee_BusinessEntityID                          0  
    2           IX_Employee_OrganizationalNode                        0  
    3           IX_Employee_OrganizationalLevel_OrganizationalNode    0  
    5           AK_Employee_LoginID                                   66.6666666666667  
    6           AK_Employee_NationalIDNumber                          50  
    7           AK_Employee_rowguid                                   0  
  
    (6 row(s) affected)  
    ```  
  
 <span data-ttu-id="61a84-236">Weitere Informationen finden Sie unter [sys. dm_db_index_physical_stats &#40;Transact-SQL-&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61a84-236">For more information, see  [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureReorg"></a> <span data-ttu-id="61a84-237">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61a84-237">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-reorganize-or-rebuild-an-index"></a><span data-ttu-id="61a84-238">So organisieren oder erstellen Sie einen Index neu</span><span class="sxs-lookup"><span data-stu-id="61a84-238">To reorganize or rebuild an index</span></span>  
  
1.  <span data-ttu-id="61a84-239">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, in der Sie einen Index neu organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-239">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="61a84-240">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="61a84-240">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="61a84-241">Erweitern Sie die Tabelle, in der Sie einen Index neu organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-241">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="61a84-242">Erweitern Sie den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="61a84-242">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="61a84-243">Klicken Sie mit der rechten Maustaste auf den Index, den Sie neu organisieren möchten, und wählen Sie **Neu organisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="61a84-243">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="61a84-244">Vergewissern Sie sich im Dialogfeld **Indizes neu organisieren** , dass der richtige Index im Raster **Neu zu organisierende Indizes** ausgewählt ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61a84-244">In the **Reorganize Indexes** dialog box, verify that the correct index is in the **Indexes to be reorganized** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="61a84-245">Aktivieren Sie das Kontrollkästchen **Spaltendaten großer Objekte komprimieren** , um anzugeben, dass alle Seiten mit umfangreichen Objektdaten (Large Object, LOB) komprimiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="61a84-245">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="61a84-246">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61a84-246">Click **OK.**</span></span>  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="61a84-247">So organisieren Sie alle Indizes in einer Tabelle neu</span><span class="sxs-lookup"><span data-stu-id="61a84-247">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="61a84-248">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, in der Sie die Indizes neu organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-248">In Object Explorer, Expand the database that contains the table on which you want to reorganize the indexes.</span></span>  
  
2.  <span data-ttu-id="61a84-249">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="61a84-249">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="61a84-250">Erweitern Sie die Tabelle, in der Sie die Indizes neu organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-250">Expand the table on which you want to reorganize the indexes.</span></span>  
  
4.  <span data-ttu-id="61a84-251">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes** , und wählen Sie **Alle neu organisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="61a84-251">Right-click the **Indexes** folder and select **Reorganize All**.</span></span>  
  
5.  <span data-ttu-id="61a84-252">Vergewissern Sie sich im Dialogfeld **Index neu organisieren** , dass die richtigen Indizes im Raster **Neu zu organisierende Indizes**ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="61a84-252">In the **Reorganize Indexes** dialog box, verify that the correct indexes are in the **Indexes to be reorganized**.</span></span> <span data-ttu-id="61a84-253">Um einen Index aus dem Raster **Neu zu organisierende Indizes** zu entfernen, wählen Sie den Index aus, und drücken Sie die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="61a84-253">To remove an index from the **Indexes to be reorganized** grid, select the index and then press the Delete key.</span></span>  
  
6.  <span data-ttu-id="61a84-254">Aktivieren Sie das Kontrollkästchen **Spaltendaten großer Objekte komprimieren** , um anzugeben, dass alle Seiten mit umfangreichen Objektdaten (Large Object, LOB) komprimiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="61a84-254">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
7.  <span data-ttu-id="61a84-255">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61a84-255">Click **OK.**</span></span>  
  
#### <a name="to-rebuild-an-index"></a><span data-ttu-id="61a84-256">So erstellen Sie einen Index neu</span><span class="sxs-lookup"><span data-stu-id="61a84-256">To rebuild an index</span></span>  
  
1.  <span data-ttu-id="61a84-257">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, in der Sie einen Index neu organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-257">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="61a84-258">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="61a84-258">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="61a84-259">Erweitern Sie die Tabelle, in der Sie einen Index neu organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61a84-259">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="61a84-260">Erweitern Sie den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="61a84-260">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="61a84-261">Klicken Sie mit der rechten Maustaste auf den Index, den Sie neu organisieren möchten, und wählen Sie **Neu organisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="61a84-261">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="61a84-262">Vergewissern Sie sich im Dialogfeld **Indizes neu erstellen** , dass der richtige Index im Raster **Erneut zu erstellende Indizes** ausgewählt ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61a84-262">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to be rebuilt** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="61a84-263">Aktivieren Sie das Kontrollkästchen **Spaltendaten großer Objekte komprimieren** , um anzugeben, dass alle Seiten mit umfangreichen Objektdaten (Large Object, LOB) komprimiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="61a84-263">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="61a84-264">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61a84-264">Click **OK.**</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureReorg"></a> <span data-ttu-id="61a84-265">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61a84-265">Using Transact-SQL</span></span>  
  
#### <a name="to-reorganize-a-defragmented-index"></a><span data-ttu-id="61a84-266">So organisieren Sie einen defragmentierten Index neu</span><span class="sxs-lookup"><span data-stu-id="61a84-266">To reorganize a defragmented index</span></span>  
  
1.  <span data-ttu-id="61a84-267">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="61a84-267">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61a84-268">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="61a84-268">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61a84-269">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="61a84-269">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize the IX_Employee_OrganizationalLevel_OrganizationalNode index on the HumanResources.Employee table.   
  
    ALTER INDEX IX_Employee_OrganizationalLevel_OrganizationalNode ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="61a84-270">So organisieren Sie alle Indizes in einer Tabelle neu</span><span class="sxs-lookup"><span data-stu-id="61a84-270">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="61a84-271">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="61a84-271">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61a84-272">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="61a84-272">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61a84-273">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="61a84-273">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-rebuild-a-defragmented-index"></a><span data-ttu-id="61a84-274">So erstellen Sie einen defragmentierten Index neu</span><span class="sxs-lookup"><span data-stu-id="61a84-274">To rebuild a defragmented index</span></span>  
  
1.  <span data-ttu-id="61a84-275">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="61a84-275">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61a84-276">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="61a84-276">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61a84-277">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="61a84-277">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="61a84-278">Im folgenden Beispiel wird ein einzelner Index in der `Employee` -Tabelle neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="61a84-278">The example rebuilds a single index on the `Employee` table.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex1](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex1)]  
  
#### <a name="to-rebuild-all-indexes-in-a-table"></a><span data-ttu-id="61a84-279">So erstellen Sie alle Indizes in einer Tabelle neu</span><span class="sxs-lookup"><span data-stu-id="61a84-279">To rebuild all indexes in a table</span></span>  
  
1.  <span data-ttu-id="61a84-280">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="61a84-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61a84-281">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="61a84-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61a84-282">Kopieren Sie das folgende Beispiel in das Abfragefenster. In diesem Beispiel wird das `ALL`-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="61a84-282">Copy and paste the following example into the query The example specifies the keyword `ALL`.</span></span> <span data-ttu-id="61a84-283">Hier werden alle der Tabelle zugeordneten Indizes neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="61a84-283">This rebuilds all indexes associated with the table.</span></span> <span data-ttu-id="61a84-284">Es werden drei Optionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="61a84-284">Three options are specified.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="61a84-285">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61a84-285">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a84-286">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61a84-286">See Also</span></span>  
 [<span data-ttu-id="61a84-287">Bewährte Methoden für die Indexdefragmentierung in Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="61a84-287">Microsoft SQL Server 2000 Index Defragmentation Best Practices</span></span>](https://technet.microsoft.com/library/cc966523.aspx)  
  
  
