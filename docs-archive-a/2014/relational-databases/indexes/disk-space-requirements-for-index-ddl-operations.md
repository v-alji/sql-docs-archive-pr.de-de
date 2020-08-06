---
title: Speicherplatzanforderungen für Index-DDL-Vorgänge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- index disk space [SQL Server]
- space [SQL Server], indexes
- indexes [SQL Server], disk space requirements
- temporary disk space [SQL Server]
ms.assetid: 35930826-c870-44c1-a966-a6a4638f62ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4ac25fc1555d6b6cfd8ee97b50d261cf5788f587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622107"
---
# <a name="disk-space-requirements-for-index-ddl-operations"></a><span data-ttu-id="e0ad3-102">Speicherplatzanforderungen für Index-DDL-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="e0ad3-102">Disk Space Requirements for Index DDL Operations</span></span>
  <span data-ttu-id="e0ad3-103">Der Speicherplatz ist beim Erstellen, Neuerstellen oder Löschen von Indizes ein wichtiger Aspekt, der berücksichtigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-103">Disk space is an important consideration when you create, rebuild, or drop indexes.</span></span> <span data-ttu-id="e0ad3-104">Unzureichender Speicherplatz kann die Leistung verringern oder sogar bewirken, dass der Indexvorgang einen Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-104">Inadequate disk space can degrade performance or even cause the index operation to fail.</span></span> <span data-ttu-id="e0ad3-105">Dieses Thema stellt allgemeine Informationen bereit, die Sie beim Ermitteln des Speicherplatzes unterstützen können, der für DDL-Vorgänge (Data Definition Language) des Indexes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-105">This topic provides general information that can help you determine the amount of disk space required for index data definition language (DDL) operations.</span></span>  
  
## <a name="index-operations-that-require-no-additional-disk-space"></a><span data-ttu-id="e0ad3-106">Indexvorgänge, für die kein zusätzlicher Speicherplatz erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="e0ad3-106">Index Operations That Require No Additional Disk Space</span></span>  
 <span data-ttu-id="e0ad3-107">Für die folgenden Indexvorgänge ist kein zusätzlicher Speicherplatz erforderlich:</span><span class="sxs-lookup"><span data-stu-id="e0ad3-107">The following index operations require no additional disk space:</span></span>  
  
-   <span data-ttu-id="e0ad3-108">ALTER INDEX REORGANIZE; jedoch ist Speicherplatz im Protokoll erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-108">ALTER INDEX REORGANIZE; however, log space is required.</span></span>  
  
-   <span data-ttu-id="e0ad3-109">DROP INDEX, wenn Sie einen nicht gruppierten Index löschen.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-109">DROP INDEX when you are dropping a nonclustered index.</span></span>  
  
-   <span data-ttu-id="e0ad3-110">DROP INDEX, wenn Sie einen gruppierten Index offline löschen, ohne die MOVE TO-Klausel anzugeben, und es sind keine nicht gruppierten Indizes vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-110">DROP INDEX when you are dropping a clustered index offline without specifying the MOVE TO clause and nonclustered indexes do not exist.</span></span>  
  
-   <span data-ttu-id="e0ad3-111">CREATE TABLE (PRIMARY KEY- oder UNIQUE-Einschränkung)</span><span class="sxs-lookup"><span data-stu-id="e0ad3-111">CREATE TABLE (PRIMARY KEY or UNIQUE constraints)</span></span>  
  
## <a name="index-operations-that-require-additional-disk-space"></a><span data-ttu-id="e0ad3-112">Indexvorgänge, für die zusätzlicher Speicherplatz erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="e0ad3-112">Index Operations That Require Additional Disk Space</span></span>  
 <span data-ttu-id="e0ad3-113">Für alle anderen Index-DDL-Vorgänge ist zusätzlicher temporärer Speicherplatz erforderlich, der während des Vorgangs verwendet werden soll, sowie dauerhafter Speicherplatz, der für das Speichern der neuen Indexstruktur(en) benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-113">All other index DDL operations require additional temporary disk space to use during the operation, and permanent disk space to store the new index structure or structures.</span></span>  
  
 <span data-ttu-id="e0ad3-114">Beim Erstellen einer neuen Indexstruktur wird Speicherplatz sowohl für die alte Struktur (Quelle) als auch für die neue Struktur (Ziel) in den jeweiligen Dateien und Dateigruppen benötigt.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-114">When a new index structure is created, disk space for both the old (source) and new (target) structures is required in their appropriate files and filegroups.</span></span> <span data-ttu-id="e0ad3-115">Die Zuordnung der alten Struktur wird erst aufgehoben, nachdem die Indexerstellungstransaktion den Commitvorgang ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-115">The old structure is not deallocated until the index creation transaction commits.</span></span>  
  
 <span data-ttu-id="e0ad3-116">Die folgenden Index-DDL-Vorgänge erstellen neue Indexstrukturen und erfordern zusätzlichen Speicherplatz:</span><span class="sxs-lookup"><span data-stu-id="e0ad3-116">The following index DDL operations create new index structures and require additional disk space:</span></span>  
  
-   <span data-ttu-id="e0ad3-117">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="e0ad3-117">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="e0ad3-118">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="e0ad3-118">CREATE INDEX WITH DROP_EXISTING</span></span>  
  
-   <span data-ttu-id="e0ad3-119">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="e0ad3-119">ALTER INDEX REBUILD</span></span>  
  
-   <span data-ttu-id="e0ad3-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY oder UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="e0ad3-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY or UNIQUE)</span></span>  
  
-   <span data-ttu-id="e0ad3-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY oder UNIQUE), wenn die Einschränkung auf einem gruppierten Index basiert</span><span class="sxs-lookup"><span data-stu-id="e0ad3-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY or UNIQUE) when the constraint is based on a clustered index</span></span>  
  
-   <span data-ttu-id="e0ad3-122">DROP INDEX MOVE TO (Gilt nur für gruppierte Indizes.)</span><span class="sxs-lookup"><span data-stu-id="e0ad3-122">DROP INDEX MOVE TO (Applies only to clustered indexes.)</span></span>  
  
## <a name="temporary-disk-space-for-sorting"></a><span data-ttu-id="e0ad3-123">Temporärer Speicherplatz für Sortiervorgänge</span><span class="sxs-lookup"><span data-stu-id="e0ad3-123">Temporary Disk Space for Sorting</span></span>  
 <span data-ttu-id="e0ad3-124">Neben dem für die Quell- und Zielstrukturen benötigten Speicherplatz ist temporärer Speicherplatz für Sortiervorgänge erforderlich, es sei denn, der Abfrageoptimierer ermittelt einen Ausführungsplan, für den keine Sortierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-124">Besides the disk space required for the source and target structures, temporary disk space is required for sorting, unless the query optimizer finds an execution plan that does not require sorting.</span></span>  
  
 <span data-ttu-id="e0ad3-125">Wenn Sortierung erforderlich ist, findet die Sortierung für die neuen Indizes nacheinander statt.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-125">If sorting is required, sorting occurs one new index at a time.</span></span> <span data-ttu-id="e0ad3-126">Wenn Sie z. B. einen gruppierten Index und die zugehörigen nicht gruppierten Indizes mit einer einzigen Anweisung neu erstellen, werden die Indizes nacheinander sortiert.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-126">For example, when you rebuild a clustered index and associated nonclustered indexes within a single statement, the indexes are sorted one after the other.</span></span> <span data-ttu-id="e0ad3-127">Daher muss der zusätzliche temporäre Speicherplatz, der für die Sortierung erforderlich ist, nur so umfangreich wie der größte Index im Vorgang sein.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-127">Therefore, the additional temporary disk space that is required for sorting only has to be as large as the largest index in the operation.</span></span> <span data-ttu-id="e0ad3-128">Dies ist fast immer der gruppierte Index.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-128">This is almost always the clustered index.</span></span>  
  
 <span data-ttu-id="e0ad3-129">Wenn die Option SORT_IN_TEMPDB auf ON festgelegt wurde, muss der größte Index in **tempdb**passen.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-129">If the SORT_IN_TEMPDB option is set to ON, the largest index must fit into **tempdb**.</span></span> <span data-ttu-id="e0ad3-130">Obwohl durch diese Option die Menge des temporären Speicherplatzes erhöht wird, die zur Indexerstellung verwendet wird, kann sich die Zeitspanne verringern, die zum Erstellen eines Indexes erforderlich ist, wenn **tempdb** auf einem anderen Satz von Datenträgern gespeichert ist als die Benutzerdatenbank.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-130">Although this option increases the amount of temporary disk space that is used to create an index, it may reduce the time that is required to create an index when **tempdb** is on a set of disks different from the user database.</span></span>  
  
 <span data-ttu-id="e0ad3-131">Wenn SORT_IN_TEMPDB auf OFF festgelegt wurde (die Standardeinstellung), wird jeder Index einschließlich partitionierter Indizes an seinem Zielspeicherplatz sortiert; in diesem Fall ist nur der Speicherplatz für die neuen Indexstrukturen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-131">If SORT_IN_TEMPDB is set to OFF (the default) each index, including partitioned indexes, is sorted in its destination disk space; and only the disk space for the new index structures is required.</span></span>  
  
 <span data-ttu-id="e0ad3-132">Ein Beispiel zum Berechnen des Speicherplatzes finden Sie unter [Index Disk Space Example](index-disk-space-example.md).</span><span class="sxs-lookup"><span data-stu-id="e0ad3-132">For an example of calculating disk space, see [Index Disk Space Example](index-disk-space-example.md).</span></span>  
  
## <a name="temporary-disk-space-for-online-index-operations"></a><span data-ttu-id="e0ad3-133">Temporärer Speicherplatz für Onlineindexvorgänge</span><span class="sxs-lookup"><span data-stu-id="e0ad3-133">Temporary Disk Space for Online Index Operations</span></span>  
 <span data-ttu-id="e0ad3-134">Wenn Sie Indexvorgänge online ausführen, ist zusätzlicher temporärer Speicherplatz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-134">When you perform index operations online, additional temporary disk space is required.</span></span>  
  
 <span data-ttu-id="e0ad3-135">Wenn ein gruppierter Index online erstellt, neu erstellt oder gelöscht wird, wird ein temporärer nicht gruppierter Index erstellt, um alte Lesezeichen neuen Lesezeichen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-135">If a clustered index is created, rebuilt, or dropped online, a temporary nonclustered index is created to map old bookmarks to new bookmarks.</span></span> <span data-ttu-id="e0ad3-136">Wenn die Option SORT_IN_TEMPDB auf ON festgelegt wurde, wird dieser temporäre Index in **tempdb**erstellt.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-136">If the SORT_IN_TEMPDB option is set to ON, this temporary index is created in **tempdb**.</span></span> <span data-ttu-id="e0ad3-137">Wurde SORT_IN_TEMPDB auf OFF festgelegt, wird die gleiche Dateigruppe oder das gleiche Partitionsschema wie für den Zielindex verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-137">If SORT_IN_TEMPDB is set to OFF, the same filegroup or partition scheme as the target index is used.</span></span> <span data-ttu-id="e0ad3-138">Der temporäre Zuordnungsindex enthält einen Datensatz für jede Zeile in der Tabelle. Sein Inhalt ist die Vereinigung der alten und der neuen Lesezeichenspalten, einschließlich uniqueifiers und Datensatzbezeichnern sowie einer einzigen Kopie jeder Spalte, die in beiden Lesezeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-138">The temporary mapping index contains one record for each row in the table, and its contents is the union of the old and new bookmark columns, including uniqueifiers and record identifiers and including only a single copy of any column used in both bookmarks.</span></span> <span data-ttu-id="e0ad3-139">Weitere Informationen zu Onlineindexvorgängen finden Sie unter [Ausführen von Onlineindexvorgängen](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="e0ad3-139">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0ad3-140">Die SORT_IN_TEMPDB-Option kann nicht für DROP INDEX-Anweisungen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-140">The SORT_IN_TEMPDB option cannot be set for DROP INDEX statements.</span></span> <span data-ttu-id="e0ad3-141">Der temporäre Zuordnungsindex wird immer in der gleichen Dateigruppe oder dem gleichen Partitionsschema wie der Zielindex erstellt.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-141">The temporary mapping index is always created in the same filegroup or partition scheme as the target index.</span></span>  
  
 <span data-ttu-id="e0ad3-142">Onlineindexvorgänge verwenden die Zeilenversionsverwaltung, um den Indexvorgang von den Auswirkungen der Änderungen zu isolieren, die von anderen Transaktionen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-142">Online index operations use row versioning to isolate the index operation from the effects of modifications made by other transactions.</span></span> <span data-ttu-id="e0ad3-143">Auf diese Weise ist es nicht erforderlich, freigegebene Sperren für Zeilen anzufordern, die gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-143">This avoids the need for requesting share locks on rows that have been read.</span></span> <span data-ttu-id="e0ad3-144">Gleichzeitige Update- und Löschvorgänge durch Benutzer während Onlineindexvorgänge erfordern Speicherplatz für Versionsdatensätze in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="e0ad3-144">Concurrent user update and delete operations during online index operations require space for version records in **tempdb**.</span></span> <span data-ttu-id="e0ad3-145">Weitere Informationen finden Sie unter [Ausführen von Onlineindexvorgängen](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="e0ad3-145">For more information, see [Perform Index Operations Online](perform-index-operations-online.md) .</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e0ad3-146">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e0ad3-146">Related Tasks</span></span>  
 [<span data-ttu-id="e0ad3-147">Beispiel für den zum Speichern eines Indexes belegten Speicherplatz</span><span class="sxs-lookup"><span data-stu-id="e0ad3-147">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
 [<span data-ttu-id="e0ad3-148">Transaktionsprotokollspeicherplatz für Indexvorgänge</span><span class="sxs-lookup"><span data-stu-id="e0ad3-148">Transaction Log Disk Space for Index Operations</span></span>](transaction-log-disk-space-for-index-operations.md)  
  
 [<span data-ttu-id="e0ad3-149">Schätzen der Größe einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="e0ad3-149">Estimate the Size of a Table</span></span>](../databases/estimate-the-size-of-a-table.md)  
  
 [<span data-ttu-id="e0ad3-150">Schätzen der Größe eines gruppierten Indexes</span><span class="sxs-lookup"><span data-stu-id="e0ad3-150">Estimate the Size of a Clustered Index</span></span>](../databases/estimate-the-size-of-a-clustered-index.md)  
  
 [<span data-ttu-id="e0ad3-151">Schätzen der Größe eines nicht gruppierten Index</span><span class="sxs-lookup"><span data-stu-id="e0ad3-151">Estimate the Size of a Nonclustered Index</span></span>](../databases/estimate-the-size-of-a-nonclustered-index.md)  
  
 [<span data-ttu-id="e0ad3-152">Schätzen der Größe eines Heaps</span><span class="sxs-lookup"><span data-stu-id="e0ad3-152">Estimate the Size of a Heap</span></span>](../databases/estimate-the-size-of-a-heap.md)  
  
## <a name="related-content"></a><span data-ttu-id="e0ad3-153">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="e0ad3-153">Related Content</span></span>  
 [<span data-ttu-id="e0ad3-154">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0ad3-154">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="e0ad3-155">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0ad3-155">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
 [<span data-ttu-id="e0ad3-156">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0ad3-156">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="e0ad3-157">Angeben des Füllfaktors für einen Index</span><span class="sxs-lookup"><span data-stu-id="e0ad3-157">Specify Fill Factor for an Index</span></span>](specify-fill-factor-for-an-index.md)  
  
 [<span data-ttu-id="e0ad3-158">Neuorganisieren und Neuerstellen von Indizes</span><span class="sxs-lookup"><span data-stu-id="e0ad3-158">Reorganize and Rebuild Indexes</span></span>](indexes.md)  
  
  
