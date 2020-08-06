---
title: Richtlinien für die Verwendung von Indizes für Speicher optimierte Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- hash indexes
ms.assetid: 16ef63a4-367a-46ac-917d-9eebc81ab29b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f00d643088634c918eb626917eae64a001ce3678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701564"
---
# <a name="guidelines-for-using-indexes-on-memory-optimized-tables"></a><span data-ttu-id="c8fe7-102">Richtlinien für die Verwendung von Indizes für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="c8fe7-102">Guidelines for Using Indexes on Memory-Optimized Tables</span></span>
  <span data-ttu-id="c8fe7-103">Indizes werden für den effizienten Datenzugriff in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-103">Indexes are used for efficiently accessing data in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="c8fe7-104">Die Auswahl der richtigen Indizes kann die Abfrageleistung deutlich verbessern.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-104">Specifying the right indexes can dramatically improve query performance.</span></span> <span data-ttu-id="c8fe7-105">Stellen Sie sich beispielsweise die folgende Abfrage vor:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-105">Consider, for example, the query:</span></span>  
  
```sql  
SELECT c1, c2 FROM t WHERE c1 = 1;  
```  
  
 <span data-ttu-id="c8fe7-106">Wenn kein Index für Spalte c1 enthalten ist, muss [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die gesamte Tabelle t überprüfen und dann nach den Zeilen filtern, die die Bedingung „c1=1“ erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-106">If there is no index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will need to scan the entire table t, and then filter on the rows that satisfy the condition c1=1.</span></span> <span data-ttu-id="c8fe7-107">Wenn jedoch t über einen Index für die Spalte c1 verfügt, kann [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] direkt auf Wert 1 suchen und die gewünschten Zeilen abrufen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-107">However, if t has an index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can seek directly on the value 1 and retrieve the rows.</span></span>  
  
 <span data-ttu-id="c8fe7-108">Bei der Suche nach Datensätzen, die einen bestimmten Wert oder Wertebereich in einer oder mehreren Tabellenspalten aufweisen, kann [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] für diese Spalten einen Index nutzen, um die entsprechenden Datensätze schnell zu finden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-108">When searching for records that have a specific value, or range of values, for one or more columns in the table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can use an index on those columns to quickly locate the corresponding records.</span></span> <span data-ttu-id="c8fe7-109">Sowohl datenträgerbasierte als auch speicheroptimierte Tabellen profitieren von Indizes.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-109">Both disk-based and memory-optimized tables benefit from indexes.</span></span> <span data-ttu-id="c8fe7-110">Es gibt jedoch bestimmte Unterschiede zwischen Index Strukturen, die bei der Verwendung von Speicher optimierten Tabellen berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-110">There are, however, certain differences between index structures that need to be considered when using memory-optimized tables.</span></span> <span data-ttu-id="c8fe7-111">(Indizes für Speicher optimierte Tabellen werden als Speicher optimierte Indizes bezeichnet.) Einige der Hauptunterschiede sind:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-111">(Indexes on memory-optimized tables are referred to as memory-optimized indexes.) Some of the key differences are:</span></span>  
  
-   <span data-ttu-id="c8fe7-112">Speicher optimierte Indizes müssen mit [CREATE TABLE &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-table-transact-sql)erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-112">Memory-optimized indexes must be created with [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span> <span data-ttu-id="c8fe7-113">Datenträgerbasierte Indizes können mit `CREATE TABLE` und `CREATE INDEX` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-113">Disk-based indexes can be created with `CREATE TABLE` and `CREATE INDEX`.</span></span>  
  
-   <span data-ttu-id="c8fe7-114">Speicheroptimierte Indizes sind nur im Arbeitsspeicher vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-114">Memory-optimized indexes exist only in memory.</span></span> <span data-ttu-id="c8fe7-115">Indexstrukturen werden nicht auf dem Datenträger beibehalten und Indexvorgänge werden nicht im Transaktionsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-115">Index structures are not persisted to disk and index operations are not logged in the transaction log.</span></span> <span data-ttu-id="c8fe7-116">Die Indexstruktur wird beim Erstellen der speicheroptimierten Tabelle im Arbeitsspeicher erstellt, und zwar während CREATE TABLE wie auch während des Datenbankstarts.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-116">The index structure is created when the memory-optimized table is created in memory, both during CREATE TABLE and during database startup.</span></span>  
  
-   <span data-ttu-id="c8fe7-117">Speicheroptimierte Indizes decken grundsätzlich ab.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-117">Memory-optimized indexes are inherently covering.</span></span> <span data-ttu-id="c8fe7-118">Dies bedeutet, dass alle Spalten virtuell im Index enthalten sind, und Bookmark Lookup-Vorgänge in speicheroptimierten Tabellen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-118">Covering means that all columns are virtually included in the index and bookmark lookups are not needed for memory-optimized tables.</span></span> <span data-ttu-id="c8fe7-119">An Stelle eines Verweises auf den Primärschlüssel enthalten speicheroptimierte Indizes einfach einen Speicherzeiger auf die tatsächliche Zeile in der Tabellendatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-119">Rather than a reference to the primary key, memory-optimized indexes simply contain a memory pointer to the actual row in the table data structure.</span></span>  
  
-   <span data-ttu-id="c8fe7-120">Fragmentierung und Füllfaktor gelten nicht für speicheroptimierte Indizes.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-120">Fragmentation and fillfactor do not apply to memory-optimized indexes.</span></span> <span data-ttu-id="c8fe7-121">In datenträgerbasierte Indizes verweist die Fragmentierung auf Seiten im B-Baum, die außerhalb der Reihenfolge auf den Datenträger geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-121">In disk-based indexes, fragmentation refers to pages in the B-tree being written to disk out-of-order.</span></span> <span data-ttu-id="c8fe7-122">Speicheroptimierte Indizes werden nicht auf Datenträger geschrieben oder von dort gelesen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-122">Memory-optimized indexes are not written to or read from disk.</span></span> <span data-ttu-id="c8fe7-123">Der Füllfaktor bei datenträgerbasierte B-Baum-Indizes bezieht sich darauf, zu welchem Grad die physischen Seitenstrukturen tatsächlich mit Daten gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-123">Fillfactor in disk-based B-tree indexes refers to the degree to which the physical page structures are filled with actual data.</span></span> <span data-ttu-id="c8fe7-124">Die speicheroptimierten Indexstrukturen haben keine Seiten mit fester Größe.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-124">The memory-optimized index structures do not have fixed-size pages.</span></span>  
  
 <span data-ttu-id="c8fe7-125">Es gibt zwei Typen speicheroptimierter Indizes:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-125">There are two types of memory-optimized indexes:</span></span>  
  
-   <span data-ttu-id="c8fe7-126">Nicht gruppierte Hashindizes, die für Punktsuchen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-126">Nonclustered hash indexes, which are made for point lookups.</span></span> <span data-ttu-id="c8fe7-127">Weitere Informationen zu Hash Indizes finden Sie unter [Hash Indizes](hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-127">For more information about hash indexes, see [Hash Indexes](hash-indexes.md).</span></span>  
  
-   <span data-ttu-id="c8fe7-128">Nicht gruppierte Indizes, die für Bereichsscans und sortierte Scans vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-128">Nonclustered indexes, which are made for range scans and ordered scans.</span></span>  
  
 <span data-ttu-id="c8fe7-129">Mit einem Hashindex erfolgt der Datenzugriff über eine Hashtabelle im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-129">With a hash index, data is accessed through an in-memory hash table.</span></span> <span data-ttu-id="c8fe7-130">Hashindizes haben keine Seiten und haben immer eine feste Größe.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-130">Hash indexes do not have pages and are always of a fixed size.</span></span> <span data-ttu-id="c8fe7-131">Ein Hashindex kann jedoch leere Hashbuckets enthalten, was eine begrenzte Platzverschwendung nach sich zieht.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-131">However, a hash index can have empty hash buckets, which result in limited wasted space.</span></span> <span data-ttu-id="c8fe7-132">Die Werte, die von einer Abfrage mithilfe eines Hashindexes zurückgegeben werden, sind nicht sortiert.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-132">The values returned from a query using a hash index are not sorted.</span></span> <span data-ttu-id="c8fe7-133">Hashindizes werden für Indexsuchen auf Gleichheitsprädikaten optimiert und unterstützen auch vollständige Indexscans.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-133">Hash indexes are optimized for index seeks on equality predicates and also support full index scans.</span></span>  
  
 <span data-ttu-id="c8fe7-134">Nicht gruppierte Indizes (nicht Hashindizes) unterstützen alles, was Hashindizes unterstützen, sowie Suchvorgänge für Ungleichheitsprädikate, beispielsweise größer als oder kleiner als, und eine Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-134">Nonclustered indexes (not hash indexes) support everything that hash indexes supports plus seek operations on inequality predicates such as greater than or less than, as well as sort order.</span></span> <span data-ttu-id="c8fe7-135">Zeilen können nach der Reihenfolge abgerufen werden, die bei der Indexerstellung festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-135">Rows can be retrieved according to the order specified with index creation.</span></span> <span data-ttu-id="c8fe7-136">Wenn die Sortierreihenfolge des Indexes der Sortierreihenfolge entspricht, die für eine bestimmte Abfrage erforderlich ist, der Indexschlüssel also z. B. mit der ORDER BY-Klausel übereinstimmt, müssen die Zeilen im Rahmen der Abfrageausführung nicht sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-136">If the sort order of the index matches the sort order required for a particular query, for example if the index key matches the ORDER BY clause, there is no need to sort the rows as part of query execution.</span></span> <span data-ttu-id="c8fe7-137">Speicheroptimierte, nicht gruppierte Indizes sind unidirektional; sie unterstützen keinen Abruf von Zeilen in einer Sortierreihenfolge, die die Umkehrung der Sortierreihenfolge des Indexes ist.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-137">Memory-optimized nonclustered indexes are unidirectional; they do not support retrieving rows in a sort order that is the reverse of the sort order of the index.</span></span> <span data-ttu-id="c8fe7-138">Bei einem als (c1 ASC) angegebenen Index ist es beispielsweise nicht möglich, den Index in umgekehrter Reihenfolge zu scannen, z. B. (c1 DESC).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-138">For example, for an index specified as (c1 ASC), it is not possible to scan the index in reverse order, as (c1 DESC).</span></span>  
  
 <span data-ttu-id="c8fe7-139">Jeder Index belegt Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-139">Each index consumes memory.</span></span> <span data-ttu-id="c8fe7-140">Hashindizes belegen einen festen Speicherplatz, dessen Größe eine Funktion der Bucketanzahl ist.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-140">Hash indexes consume a fixed amount of memory, which is a function of the bucket count.</span></span> <span data-ttu-id="c8fe7-141">Bei nicht gruppierten Indizes basiert die Arbeitsspeichernutzung auf der Zeilenanzahl und Größe der Indexschlüsselspalten. Je nach Arbeitsauslastung ist dies mit etwas zusätzlichem Aufwand verbunden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-141">For nonclustered indexes, memory consumption is a function of the row count and the size of the index key columns, with some additional overhead depending on the workload.</span></span> <span data-ttu-id="c8fe7-142">Arbeitsspeicher für speicheroptimierte Indizes erfolgt zusätzlich und getrennt von dem Arbeitsspeicher, der verwendet wird, um Zeilen in den speicheroptimierten Tabellen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-142">Memory for memory-optimized indexes is in addition to and separate from the memory used to store rows in memory-optimized tables.</span></span>  
  
 <span data-ttu-id="c8fe7-143">Doppelte Schlüsselwerte sind immer dem gleichen Bucket im Hashindex zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-143">Duplicate key values always share the same hash bucket.</span></span> <span data-ttu-id="c8fe7-144">Wenn der Hashindex viele doppelte Schlüsselwerte enthält, können die entstehenden langen Hashzeichenketten die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-144">If a hash index contains many duplicate key values, the resulting long hash chains will harm performance.</span></span> <span data-ttu-id="c8fe7-145">Hashkonflikte, die in jedem Hashindex auftreten, reduzieren die Leistung in diesem Szenario noch weiter.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-145">Hash collisions, which occur in any hash index, will further reduce performance in this scenario.</span></span> <span data-ttu-id="c8fe7-146">Wenn die Anzahl eindeutiger Index Schlüssel mindestens 100-mal kleiner als die Zeilen Anzahl ist, können Sie das Risiko von Hash Konflikten verringern, indem Sie die Bucketanzahl deutlich vergrößern ( [mindestens das](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) Achtfache der Anzahl eindeutiger Index Schlüssel), oder Sie können Hash Konflikte vollständig durch die Verwendung eines nicht gruppierten Indexes eliminieren.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-146">For that reason, if the number of unique index keys is at least 100 times smaller than the row count, you can reduce the risk of hash collisions by making the bucket count much larger (at least eight times the number of unique index keys; see [Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) for more information) or you can eliminate hash collisions entirely by using a nonclustered index.</span></span>  
  
## <a name="determining-which-indexes-to-use-for-a-memory-optimized-table"></a><span data-ttu-id="c8fe7-147">Bestimmen der richtigen Indizes für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="c8fe7-147">Determining Which Indexes to Use for a Memory-Optimized Table</span></span>  
 <span data-ttu-id="c8fe7-148">Jede speicheroptimierte Tabelle muss mindestens einen Index haben.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-148">Each memory-optimized table must have at least one index.</span></span> <span data-ttu-id="c8fe7-149">Beachten Sie, dass jede PRIMARY KEY-Einschränkung implizit einen Index erstellt.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-149">Note that each PRIMARY KEY constraint implicitly creates an index.</span></span> <span data-ttu-id="c8fe7-150">Wenn eine Tabelle über einen Primärschlüssel verfügt, hat sie also einen Index.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-150">Therefore, if a table has a primary key, it has an index.</span></span> <span data-ttu-id="c8fe7-151">Ein Primärschlüssel ist eine Voraussetzung für dauerhafte speicheroptimierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-151">A primary key is a requirement for a durable memory-optimized table.</span></span>  
  
 <span data-ttu-id="c8fe7-152">Wenn Sie eine speicheroptimierte Tabelle abfragen, bieten Hashindizes eine bessere Leistung, wenn die Prädikatklausel nur Gleichheitsprädikate enthält.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-152">When querying a memory-optimized table, hash indexes perform better when the predicate clause contains only equality predicates.</span></span> <span data-ttu-id="c8fe7-153">Das Prädikat muss alle Spalten im Hashindexschlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-153">The predicate must include all columns in the hash index key.</span></span> <span data-ttu-id="c8fe7-154">Ein Hashindex wird mit einem Ungleichheitsprädikat auf einen Scan wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-154">A hash index will revert to a scan given an inequality predicate.</span></span>  
  
 <span data-ttu-id="c8fe7-155">Eine Spalte in einer speicheroptimierten Tabelle kann Teil eines Hashindexes und des nicht gruppierten Indexes sein.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-155">A column in a memory-optimized table can be part of both a hash index and a nonclustered index.</span></span>  
  
 <span data-ttu-id="c8fe7-156">Wenn Sie eine speicheroptimierte Tabelle mit Ungleichheitsprädikaten abfragen, bieten nicht gruppierte Indizes eine bessere Leistung als nicht gruppierte Hashindizes.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-156">When querying a memory-optimized table with inequality predicates, nonclustered indexes will perform better than nonclustered hash indexes.</span></span>  
  
 <span data-ttu-id="c8fe7-157">Der Hashindex erfordert einen Schlüssel (für den Hash), um den Index zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-157">The hash index requires a key (to hash) to seek into the index.</span></span> <span data-ttu-id="c8fe7-158">Wenn ein Indexschlüssel aus zwei Spalten besteht und Sie nur die erste Spalte bereitstellen, hat [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] keinen vollständigen Schlüssel für den Hash.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-158">If an index key consists of two columns and you only provide the first column, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a complete key to hash.</span></span> <span data-ttu-id="c8fe7-159">Dies führt zu einem Indexscan-Abfrageplan.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-159">This will result in an index scan query plan.</span></span> <span data-ttu-id="c8fe7-160">Die Verwendung bestimmt, welche Spalten indiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-160">Usage determines which columns should be indexed.</span></span>  
  
 <span data-ttu-id="c8fe7-161">Wenn eine Spalte in einem nicht gruppierten Index in vielen Zeilen denselben Wert hat (Indexschlüsselspalten verfügen über zahlreiche doppelte Werte), kann die Leistung bei Updates, Einfügungen und Löschungen abnehmen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-161">When a column in a nonclustered index has the same value in many rows (index key columns have a lot of duplicate values), performance can degrade for updates, inserts, and deletions.</span></span>  <span data-ttu-id="c8fe7-162">Eine Möglichkeit, die Leistung zu verbessern, ist in diesem Fall das Hinzufügen einer anderen Spalte zum nicht gruppierten Index.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-162">One way to improve performance in this situation is to add another column to the nonclustered index.</span></span>  
  
### <a name="operations-on-memory-optimized-and-disk-based-indexes"></a><span data-ttu-id="c8fe7-163">Vorgänge für speicheroptimierte und datenträgerbasierte Indizes.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-163">Operations on memory-optimized and disk-based indexes.</span></span>  
  
|<span data-ttu-id="c8fe7-164">Vorgang</span><span class="sxs-lookup"><span data-stu-id="c8fe7-164">Operation</span></span>|<span data-ttu-id="c8fe7-165">Speicheroptimierter, nicht gruppierter Hashindex</span><span class="sxs-lookup"><span data-stu-id="c8fe7-165">Memory-optimized, nonclustered hash, index</span></span>|<span data-ttu-id="c8fe7-166">Speicheroptimierter, nicht gruppierter Index</span><span class="sxs-lookup"><span data-stu-id="c8fe7-166">Memory-optimized nonclustered index</span></span>|<span data-ttu-id="c8fe7-167">Datenträgerbasierter Index</span><span class="sxs-lookup"><span data-stu-id="c8fe7-167">Disk-based index</span></span>|  
|---------------|-------------------------------------------------|------------------------------------------|-----------------------|  
|<span data-ttu-id="c8fe7-168">Indexscan, alle Tabellenzeilen abrufen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-168">Index Scan, retrieve all table rows.</span></span>|<span data-ttu-id="c8fe7-169">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-169">Yes</span></span>|<span data-ttu-id="c8fe7-170">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-170">Yes</span></span>|<span data-ttu-id="c8fe7-171">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-171">Yes</span></span>|  
|<span data-ttu-id="c8fe7-172">Indexsuche auf Gleichheitsprädikaten (=).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-172">Index seek on equality predicate(s) (=).</span></span>|<span data-ttu-id="c8fe7-173">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-173">Yes</span></span><br /><br /> <span data-ttu-id="c8fe7-174">(Vollständiger Schlüssel erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="c8fe7-174">(Full key required.)</span></span>|<span data-ttu-id="c8fe7-175">Ja<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c8fe7-175">Yes <sup>1</sup></span></span>|<span data-ttu-id="c8fe7-176">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-176">Yes</span></span>|  
|<span data-ttu-id="c8fe7-177">Index Suche auf Ungleichheits Prädikaten (>, <, \<=, > =, between).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-177">Index seek on inequality predicates (>, <, \<=, >=, BETWEEN).</span></span>|<span data-ttu-id="c8fe7-178">Nein (führt zu einem Indexscan)</span><span class="sxs-lookup"><span data-stu-id="c8fe7-178">No (results in an index scan)</span></span>|<span data-ttu-id="c8fe7-179">Ja<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c8fe7-179">Yes <sup>1</sup></span></span>|<span data-ttu-id="c8fe7-180">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-180">Yes</span></span>|  
|<span data-ttu-id="c8fe7-181">Abrufen der Zeilen in einer Sortierreihenfolge, die der Indexdefinition entspricht.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-181">Retrieve rows in a sort-order matching the index definition.</span></span>|<span data-ttu-id="c8fe7-182">Nein</span><span class="sxs-lookup"><span data-stu-id="c8fe7-182">No</span></span>|<span data-ttu-id="c8fe7-183">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-183">Yes</span></span>|<span data-ttu-id="c8fe7-184">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-184">Yes</span></span>|  
|<span data-ttu-id="c8fe7-185">Abrufen der Zeilen in einer Sortierreihenfolge, die der Umkehrung der Indexdefinition entspricht.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-185">Retrieve rows in a sort-order matching the reverse of the index definition.</span></span>|<span data-ttu-id="c8fe7-186">Nein</span><span class="sxs-lookup"><span data-stu-id="c8fe7-186">No</span></span>|<span data-ttu-id="c8fe7-187">Nein</span><span class="sxs-lookup"><span data-stu-id="c8fe7-187">No</span></span>|<span data-ttu-id="c8fe7-188">Ja</span><span class="sxs-lookup"><span data-stu-id="c8fe7-188">Yes</span></span>|  
  
 <span data-ttu-id="c8fe7-189">In dieser Tabelle bedeutet "Ja", dass der Index die Anforderung adäquat bedienen kann, und "Nein" bedeutet, dass der Index nicht erfolgreich zum Erfüllen der Anforderung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-189">In the table, Yes means that the index can adequately service the request and No means that the index cannot be used successfully to satisfy the request.</span></span>  
  
 <span data-ttu-id="c8fe7-190"><sup>1</sup> für einen nicht gruppierten Speicher optimierten Index ist der vollständige Schlüssel nicht erforderlich, um eine Index Suche auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-190"><sup>1</sup> For a nonclustered memory-optimized index, the full key is not required to perform an index seek.</span></span> <span data-ttu-id="c8fe7-191">Obwohl bei Angabe der die Spaltenreihenfolge des Indexschlüssels ein Scan auftritt, wenn ein Wert für eine Spalte nach einer fehlenden Spalte kommt.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-191">Although, given the column order of the index key, a scan will occur if a value for a column comes after a missing column.</span></span>  
  
## <a name="index-count"></a><span data-ttu-id="c8fe7-192">Indexanzahl</span><span class="sxs-lookup"><span data-stu-id="c8fe7-192">Index Count</span></span>  
 <span data-ttu-id="c8fe7-193">Eine speicheroptimierte Tabelle kann über bis zu 8 Indizes verfügen, darunter den mit dem Primärschlüssel erstellten Index.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-193">A memory-optimized table can have up to 8 indexes, including the index created with the primary key.</span></span>  
  
 <span data-ttu-id="c8fe7-194">Hinsichtlich der Indexzahl bei speicheroptimierten Tabellen sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-194">Regarding the number of indexes created on a memory-optimized table, consider the following:</span></span>  
  
-   <span data-ttu-id="c8fe7-195">Geben Sie beim Erstellen der Tabelle die erforderlichen Indizes an.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-195">Specify the indexes you need when you create the table.</span></span> <span data-ttu-id="c8fe7-196">Nach dem Erstellen einer speicheroptimierten Tabelle ist es nicht mehr möglich, einen Index zu hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-196">You cannot create an index for a memory-optimized table after the table is created.</span></span> <span data-ttu-id="c8fe7-197">Wenn Sie einer speicheroptimierten Tabelle einen Index hinzufügen möchten, verwerfen Sie diese Tabelle und erstellen Sie sie neu.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-197">If you want to add an index to a memory-optimized table, drop and recreate that table.</span></span>  
  
-   <span data-ttu-id="c8fe7-198">Erstellen Sie keinen Index, den Sie selten verwenden:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-198">Do not create an index that you rarely use:</span></span>  
  
     <span data-ttu-id="c8fe7-199">Die automatische Speicherbereinigung funktioniert am besten, wenn alle Indizes einer Tabelle häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-199">Garbage collection works best if all indexes on the table are frequently used.</span></span> <span data-ttu-id="c8fe7-200">Selten verwendete Indizes können dazu führen, dass das System der automatischen Speicherbereinigung für alte Zeilenversionen nicht optimal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-200">Rarely-used indexes may cause the garbage collection system to not perform optimally for old row versions.</span></span>  
  
## <a name="creating-a-memory-optimized-index-code-samples"></a><span data-ttu-id="c8fe7-201">Erstellen eines speicheroptimierten Indexes: Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="c8fe7-201">Creating a Memory-Optimized Index: Code Samples</span></span>  
 <span data-ttu-id="c8fe7-202">Spaltenebenen-Hashindex:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-202">Column level hash index:</span></span>  
  
```sql  
CREATE TABLE t1   
   (c1 INT NOT NULL INDEX idx HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="c8fe7-203">Tabellenebenen-Hashindex:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-203">Table level hash index:</span></span>  
  
```sql  
CREATE TABLE t1_1   
   (c1 INT NOT NULL,   
   INDEX IDX HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="c8fe7-204">Hashindex des primären Schlüssels auf Spaltenebene:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-204">Column level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="c8fe7-205">Hashindex des primären Schlüssels auf Tabellenebene:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-205">Table level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2_2   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="c8fe7-206">Nicht gruppierter Index auf Spaltenebene:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-206">Column level nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t3   
   (c1 INT NOT NULL INDEX ID)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="c8fe7-207">Nicht gruppierter Index auf Tabellenebene:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-207">Table level nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t3_3   
   (c1 INT NOT NULL,   
   INDEX IDX NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="c8fe7-208">Nicht gruppierter Index des primären Schlüssels auf Spaltenebene:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-208">Column level primary key nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t4   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="c8fe7-209">Nicht gruppierter Index des primären Schlüssels auf Tabellenebene:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-209">Table level primary key nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t4_4   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="c8fe7-210">Nach Definition der Spalten definierter mehrspaltiger Index:</span><span class="sxs-lookup"><span data-stu-id="c8fe7-210">Multicolumn index defined after columns are defined:</span></span>  
  
```sql  
create table t (  
       a int not null constraint ta primary key nonclustered,  
       b int not null,  
       c int not null,  
       d int not null,  
       index idx_t_b_c_d nonclustered (b, c asc, d desc)  
) with (memory_optimized = on, durability = SCHEMA_AND_DATA)  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8fe7-211">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8fe7-211">See Also</span></span>  
 <span data-ttu-id="c8fe7-212">[Indizes für Speicher optimierte Tabellen](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="c8fe7-212">[Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="c8fe7-213">[Bestimmen der korrekten Bucketanzahl für Hash Indizes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="c8fe7-213">[Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span></span>  
 [<span data-ttu-id="c8fe7-214">Hash Indizes</span><span class="sxs-lookup"><span data-stu-id="c8fe7-214">Hash Indexes</span></span>](hash-indexes.md)  
  
  
