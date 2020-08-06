---
title: Schätzen der Arbeitsspeicheranforderungen speicheroptimierter Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5c5cc1fc-1fdf-4562-9443-272ad9ab5ba8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5c5218a96d3650cbae22501ab2794b1b553996b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722825"
---
# <a name="estimate-memory-requirements-for-memory-optimized-tables"></a><span data-ttu-id="664ea-102">Schätzen der Arbeitsspeicheranforderungen speicheroptimierter Tabellen</span><span class="sxs-lookup"><span data-stu-id="664ea-102">Estimate Memory Requirements for Memory-Optimized Tables</span></span>
  <span data-ttu-id="664ea-103">Unabhängig davon, ob Sie eine neue [!INCLUDE[hek_2](../../includes/hek-2-md.md)] Speicher optimierte Tabelle erstellen oder eine vorhandene Datenträger basierte Tabelle zu einer Speicher optimierten Tabelle migrieren, ist es wichtig, dass Sie eine sinnvolle Schätzung der Arbeitsspeicher Anforderungen der einzelnen Tabellen haben, damit Sie den Server mit ausreichendem Arbeitsspeicher bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="664ea-103">Whether you are creating a new [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized table or migrating an existing disk-based table to a memory-optimized table, it is important to have a reasonable estimate of each table's memory needs so you can provision the server with sufficient memory.</span></span> <span data-ttu-id="664ea-104">In diesem Abschnitt wird beschrieben, wie die Speichermenge geschätzt wird, die für die Daten einer speicheroptimierten Tabelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="664ea-104">This section describes how to estimate the amount of memory that you need to hold data for a memory-optimized table.</span></span>  
  
 <span data-ttu-id="664ea-105">Wenn Sie die Migration von datenträgerbasierten zu speicheroptimierten Tabellen in Erwägung ziehen, finden Sie im Thema [Bestimmen, ob eine Tabelle oder eine gespeicherte Prozedur zu In-Memory OLTP portiert werden soll](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) Informationen dazu, welche Tabellen sich am besten migrieren lassen. Anschließend können Sie mit diesem Thema fortfahren.</span><span class="sxs-lookup"><span data-stu-id="664ea-105">If you are contemplating migrating from disk-based tables to memory-optimized tables, before you proceed in this topic, see the topic [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) for guidance on which tables are best to migrate.</span></span> <span data-ttu-id="664ea-106">Alle Themen unter [Migrieren zu In-Memory OLTP](migrating-to-in-memory-oltp.md) bieten eine Anleitung zum Migrieren von datenträgerbasierten zu speicheroptimierten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="664ea-106">All the topics under [Migrating to In-Memory OLTP](migrating-to-in-memory-oltp.md) provide guidance on migrating from disk-based to memory-optimized tables.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="664ea-107">Abschnitte in diesem Thema</span><span class="sxs-lookup"><span data-stu-id="664ea-107">Sections in this topic</span></span>  
  
-   [<span data-ttu-id="664ea-108">Beispiel für eine speicheroptimierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="664ea-108">Example memory-optimized table</span></span>](#bkmk_ExampleTable)  
  
-   [<span data-ttu-id="664ea-109">Arbeitsspeicher für die Tabelle</span><span class="sxs-lookup"><span data-stu-id="664ea-109">Memory for the table</span></span>](#bkmk_MemoryForTable)  
  
-   [<span data-ttu-id="664ea-110">Arbeitsspeicher für Indizes</span><span class="sxs-lookup"><span data-stu-id="664ea-110">Memory for indexes</span></span>](#bkmk_IndexMeemory)  
  
-   [<span data-ttu-id="664ea-111">Arbeitsspeicher für die Zeilenversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="664ea-111">Memory for row versioning</span></span>](#bkmk_MemoryForRowVersions)  
  
-   [<span data-ttu-id="664ea-112">Arbeitsspeicher für Tabellenvariablen</span><span class="sxs-lookup"><span data-stu-id="664ea-112">Memory for table variables</span></span>](#bkmk_TableVariables)  
  
-   [<span data-ttu-id="664ea-113">Arbeitsspeicher für zukünftiges Wachstum</span><span class="sxs-lookup"><span data-stu-id="664ea-113">Memory for growth</span></span>](#bkmk_MemoryForGrowth)  
  
##  <a name="example-memory-optimized-table"></a><a name="bkmk_ExampleTable"></a> <span data-ttu-id="664ea-114">Beispiel für eine speicheroptimierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="664ea-114">Example memory-optimized table</span></span>  
 <span data-ttu-id="664ea-115">Betrachten Sie das folgende speicheroptimierte Tabellenschema:</span><span class="sxs-lookup"><span data-stu-id="664ea-115">Consider the following memory-optimized table schema:</span></span>  
  
```sql  
  
CREATE TABLE t_hk (  
col1 int NOT NULL PRIMARY KEY NONCLUSTERED,  
col2 int NOT NULL INDEX t1c2_index   
     HASH WITH (bucket_count = 5000000),  
col3 int NOT NULL INDEX t1c3_index   
     HASH WITH (bucket_count = 5000000),  
col4 int NOT NULL INDEX t1c4_index   
     HASH WITH (bucket_count = 5000000),  
col5 int NOT NULL INDEX t1c5_index NONCLUSTERED,  
col6 char (50) NOT NULL,  
col7 char (50) NOT NULL,   
col8 char (30) NOT NULL,   
col9 char (50) NOT NULL  
     WITH (memory_optimized = on)  
GO  
  
```  
  
 <span data-ttu-id="664ea-116">Mithilfe dieses Schemas wird der minimale Arbeitsspeicherbedarf dieser speicheroptimierten Tabelle bestimmt.</span><span class="sxs-lookup"><span data-stu-id="664ea-116">Using this schema we will determine the minimum memory needed for this memory-optimized table.</span></span>  
  
##  <a name="memory-for-the-table"></a><a name="bkmk_MemoryForTable"></a> <span data-ttu-id="664ea-117">Arbeitsspeicher für die Tabelle</span><span class="sxs-lookup"><span data-stu-id="664ea-117">Memory for the table</span></span>  
 <span data-ttu-id="664ea-118">Eine Zeile einer speicheroptimierten Tabelle umfasst drei Teile:</span><span class="sxs-lookup"><span data-stu-id="664ea-118">A memory-optimized table row is comprised of three parts:</span></span>  
  
-   <span data-ttu-id="664ea-119">**Zeitstempel** </span><span class="sxs-lookup"><span data-stu-id="664ea-119">**Timestamps** </span></span>  
    <span data-ttu-id="664ea-120">Zeilenkopf/Zeitstempel = 24 Bytes.</span><span class="sxs-lookup"><span data-stu-id="664ea-120">Row header/timestamps = 24 bytes.</span></span>  
  
-   <span data-ttu-id="664ea-121">**Indexzeiger** </span><span class="sxs-lookup"><span data-stu-id="664ea-121">**Index pointers** </span></span>  
    <span data-ttu-id="664ea-122">Für jeden Hashindex in der Tabelle weist jede Zeile einen 8-Byte-Adresszeiger auf die nächste Zeile im Index auf.</span><span class="sxs-lookup"><span data-stu-id="664ea-122">For each hash index in the table, each row has an 8-byte address pointer to the next row in the index.</span></span>  <span data-ttu-id="664ea-123">Da es vier Indizes gibt, belegt jede Zeile 32 Bytes für Indexzeiger (einen 8-Byte-Zeiger für jeden Index).</span><span class="sxs-lookup"><span data-stu-id="664ea-123">Since there are 4 indexes, each row will allocate 32 bytes for index pointers (an 8 byte pointer for each index).</span></span>  
  
-   <span data-ttu-id="664ea-124">**Daten** </span><span class="sxs-lookup"><span data-stu-id="664ea-124">**Data** </span></span>  
    <span data-ttu-id="664ea-125">Die Größe des Datenanteils der Zeile wird bestimmt, indem die Typgröße für jede Datenspalte summiert wird.</span><span class="sxs-lookup"><span data-stu-id="664ea-125">The size of the data portion of the row is determined by summing the type size for each data column.</span></span>  <span data-ttu-id="664ea-126">Die Tabelle enthält fünf ganze 4-Byte-Zahlen, drei 50-Byte-Zeichenspalten und eine 30-Byte-Zeichenspalte.</span><span class="sxs-lookup"><span data-stu-id="664ea-126">In our table we have five 4-byte integers, three 50-byte character columns, and one 30-byte character column.</span></span>  <span data-ttu-id="664ea-127">Daher beträgt der Datenanteil jeder Zeile 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 oder 200 Bytes.</span><span class="sxs-lookup"><span data-stu-id="664ea-127">Therefore the data portion of each row is 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 or 200 bytes.</span></span>  
  
 <span data-ttu-id="664ea-128">Im Folgenden eine Größenberechnung für 5.000.000 (5 Millionen) Zeilen in einer speicheroptimierten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="664ea-128">The following is a size computation for 5,000,000 (5 million) rows in a memory-optimized table.</span></span> <span data-ttu-id="664ea-129">Der von den Datenzeilen belegte Gesamtspeicher wird wie folgt geschätzt:</span><span class="sxs-lookup"><span data-stu-id="664ea-129">The total memory used by data rows is estimated as follows:</span></span>  
  
 <span data-ttu-id="664ea-130">**Arbeitsspeicher für die Tabellenzeilen**</span><span class="sxs-lookup"><span data-stu-id="664ea-130">**Memory for the table's rows**</span></span>  
  
 <span data-ttu-id="664ea-131">Aus den vorherigen Berechnungen ergibt sich für jede Zeile in der speicheroptimierten Tabelle eine Größe von 24 + 32 + 200 oder 256 Bytes.</span><span class="sxs-lookup"><span data-stu-id="664ea-131">From the above calculations, the size of each row in the memory-optimized table is 24 + 32 + 200, or 256 bytes.</span></span>  <span data-ttu-id="664ea-132">Da sie 5 Million Zeilen enthält, belegt die Tabelle 5.000.000 \* 256 Bytes oder 1.280.000.000 Bytes, also ungefähr 1,28 GB.</span><span class="sxs-lookup"><span data-stu-id="664ea-132">Since we have 5 million rows, the table will consume 5,000,000 \* 256 bytes, or 1,280,000,000 bytes - approximately 1.28 GB.</span></span>  
  
##  <a name="memory-for-indexes"></a><a name="bkmk_IndexMeemory"></a> <span data-ttu-id="664ea-133">Arbeitsspeicher für Indizes</span><span class="sxs-lookup"><span data-stu-id="664ea-133">Memory for indexes</span></span>  
 <span data-ttu-id="664ea-134">**Arbeitsspeicher für jeden Hashindex**</span><span class="sxs-lookup"><span data-stu-id="664ea-134">**Memory for each hash index**</span></span>  
  
 <span data-ttu-id="664ea-135">Jeder Hashindex ist ein Hasharray aus 8-Byte-Adresszeigern.</span><span class="sxs-lookup"><span data-stu-id="664ea-135">Each hash index is a hash array of 8-byte address pointers.</span></span>  <span data-ttu-id="664ea-136">Die Größe des Arrays wird am besten anhand der Anzahl eindeutiger Indexwerte für diesen Index bestimmt. Beispielsweise ist die Anzahl eindeutiger Col2-Werte ein guter Ausgangspunkt für die Arraygröße von „t1c2_index“.</span><span class="sxs-lookup"><span data-stu-id="664ea-136">The size of the array is best determined by the number of unique index values for that index - e.g., the number of unique Col2 values is a good starting point for the array size for the t1c2_index.</span></span> <span data-ttu-id="664ea-137">Durch ein übergroßes Hasharray wird Arbeitsspeicher vergeudet.</span><span class="sxs-lookup"><span data-stu-id="664ea-137">A hash array that is too big wastes memory.</span></span>  <span data-ttu-id="664ea-138">Ein zu kleines Hasharray verlangsamt die Leistung, da zu viele Konflikte durch Indexwerte entstehen, die demselben Hashindex zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="664ea-138">A hash array that is too small slows performance since there will be too many collisions by index values that hash to the same index.</span></span>  
  
 <span data-ttu-id="664ea-139">Mit Hashindizes erzielen Sie sehr schnelle Übereinstimmungssuchen wie:</span><span class="sxs-lookup"><span data-stu-id="664ea-139">Hash indexes achieve very fast equality lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 = 3  
  
```  
  
 <span data-ttu-id="664ea-140">Nicht gruppierte Indizes liefern schneller Ergebnisse bei Bereichssuchen wie:</span><span class="sxs-lookup"><span data-stu-id="664ea-140">Nonclustered indexes are faster for range lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 >= 3  
  
```  
  
 <span data-ttu-id="664ea-141">Beim Migrieren einer datenträgerbasierten Tabelle können Sie die Anzahl der eindeutigen Werte für den Index "t1c2_index" wie folgt bestimmen.</span><span class="sxs-lookup"><span data-stu-id="664ea-141">If you are migrating a disk-based table you can use the following to determine the number of unique values for the index t1c2_index.</span></span>  
  
```sql  
  
SELECT COUNT(DISTINCT [Col2])  
  FROM t_hk  
  
```  
  
 <span data-ttu-id="664ea-142">Wenn Sie eine neue Tabelle erstellen, müssen Sie vor der Bereitstellung die Arraygröße schätzen oder mithilfe von Tests ermitteln.</span><span class="sxs-lookup"><span data-stu-id="664ea-142">If you are creating a new table, you'll need to estimate the array size or gather data from your testing prior to deployment.</span></span>  
  
 <span data-ttu-id="664ea-143">Informationen zur Funktionsweise von Hashindizes in speicheroptimierten [!INCLUDE[hek_2](../../includes/hek-2-md.md)] -Tabellen finden Sie unter [Hashindizes](../../database-engine/hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="664ea-143">For information on how hash indexes work in [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized tables, see [Hash Indexes](../../database-engine/hash-indexes.md).</span></span>  
  
 <span data-ttu-id="664ea-144">**Hinweis:** Sie können die Array Größe des Hash Indexes nicht dynamisch ändern.</span><span class="sxs-lookup"><span data-stu-id="664ea-144">**Note:** You cannot change the hash index array size on the fly.</span></span> <span data-ttu-id="664ea-145">Um die Arraygröße des Hashindexes zu ändern, müssen Sie die Tabelle löschen, den bucket_count-Wert ändern und die Tabelle erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="664ea-145">To change the hash index array size you must drop the table, change the bucket_count value and recreate the table.</span></span>  
  
 <span data-ttu-id="664ea-146">**Festlegen der Arraygröße des Hashindexes**</span><span class="sxs-lookup"><span data-stu-id="664ea-146">**Setting the hash index array size**</span></span>  
  
 <span data-ttu-id="664ea-147">Die Hasharraygröße wird mit `(bucket_count= <value>)` festgelegt, wobei \<value> eine ganze Zahl größer als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="664ea-147">The hash array size is set by `(bucket_count= <value>)` where \<value> is an integer value greater than zero.</span></span> <span data-ttu-id="664ea-148">Wenn \<value> keine Zweierpotenz ist, wird der tatsächliche bucket_count-Wert auf die nächste Zweierpotenz aufgerundet.</span><span class="sxs-lookup"><span data-stu-id="664ea-148">If \<value> is not a power of 2, the actual bucket_count is rounded up to the next closest power of 2.</span></span>  <span data-ttu-id="664ea-149">In der Beispiel Tabelle (bucket_count = 5 Millionen) wird die tatsächliche Bucketanzahl auf 8.388.608 (2<sup>23</sup>) gerundet, da 5 Millionen keine Potenz von 2 ist.</span><span class="sxs-lookup"><span data-stu-id="664ea-149">In our example table, (bucket_count = 5000000), since 5,000,000 is not a power of 2, the actual bucket count rounds up to 8,388,608 (2<sup>23</sup>).</span></span>  <span data-ttu-id="664ea-150">Wenn Sie den vom Hasharray benötigten Arbeitsspeicher berechnen, müssen Sie diesen Wert und nicht 5.000.000 verwenden.</span><span class="sxs-lookup"><span data-stu-id="664ea-150">You must use this number, not 5,000,000 when calculating memory needed by the hash array.</span></span>  
  
 <span data-ttu-id="664ea-151">Daher beträgt der für jedes Hasharray erforderliche Arbeitsspeicher im Beispiel:</span><span class="sxs-lookup"><span data-stu-id="664ea-151">Thus, in our example, the memory needed for each hash array is:</span></span>  
  
 <span data-ttu-id="664ea-152">8.388.608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67.108.864 oder ungefähr 64 MB.</span><span class="sxs-lookup"><span data-stu-id="664ea-152">8,388,608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67,108,864 or approximately 64 MB.</span></span>  
  
 <span data-ttu-id="664ea-153">Da wir über drei Hashindizes verfügen, ist der für die Hashindizes erforderliche Arbeitsspeicher 3 \* 64 MB = 192 MB.</span><span class="sxs-lookup"><span data-stu-id="664ea-153">Since we have three hash indexes, the memory needed for the hash indexes is 3 \* 64MB = 192MB.</span></span>  
  
 <span data-ttu-id="664ea-154">**Arbeitsspeicher für nicht gruppierte Indizes**</span><span class="sxs-lookup"><span data-stu-id="664ea-154">**Memory for nonclustered indexes**</span></span>  
  
 <span data-ttu-id="664ea-155">Nicht gruppierte Indizes werden als BTrees implementiert, deren innere Knoten den Indexwert und Zeiger auf nachfolgende Knoten enthalten.</span><span class="sxs-lookup"><span data-stu-id="664ea-155">Nonclustered indexes are implemented as BTrees with the inner nodes containing the index value and pointers to subsequent nodes.</span></span>  <span data-ttu-id="664ea-156">Blattknoten enthalten den Indexwert und einen Zeiger auf die Tabellenzeile im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="664ea-156">Leaf nodes contain the index value and a pointer to the table row in memory.</span></span>  
  
 <span data-ttu-id="664ea-157">Nicht gruppierte Indizes verfügen im Gegensatz Hashindizes nicht über eine feste Bucketgröße.</span><span class="sxs-lookup"><span data-stu-id="664ea-157">Unlike hash indexes, nonclustered indexes do not have a fixed bucket size.</span></span> <span data-ttu-id="664ea-158">Der Index vergrößert bzw. verkleinert sich dynamisch mit den Daten.</span><span class="sxs-lookup"><span data-stu-id="664ea-158">The index grows and shrinks dynamically with the data.</span></span>  
  
 <span data-ttu-id="664ea-159">Der von nicht gruppierten Indizes benötigte Arbeitsspeicher kann wie folgt berechnet werden:</span><span class="sxs-lookup"><span data-stu-id="664ea-159">Memory needed by nonclustered indexes can be computed as follows:</span></span>  
  
-   <span data-ttu-id="664ea-160">**Arbeitsspeicher, der Nichtblattknoten zugeordnet ist** </span><span class="sxs-lookup"><span data-stu-id="664ea-160">**Memory allocated to non-leaf nodes** </span></span>  
    <span data-ttu-id="664ea-161">Bei einer typischen Konfiguration hat der Arbeitsspeicher, der Nichtblattknotenden zugeordnet wird, einen geringen prozentualen Anteil am gesamten vom Index belegten Arbeitsspeicher,</span><span class="sxs-lookup"><span data-stu-id="664ea-161">For a typical configuration, the memory allocated to non-leaf nodes is a small percentage of the overall memory taken by the index.</span></span> <span data-ttu-id="664ea-162">der so klein ist, dass er problemlos ignoriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="664ea-162">This is so small it can safely be ignored.</span></span>  
  
-   <span data-ttu-id="664ea-163">**Arbeitsspeicher für Blattknoten** </span><span class="sxs-lookup"><span data-stu-id="664ea-163">**Memory for leaf nodes** </span></span>  
    <span data-ttu-id="664ea-164">Die Blattknoten weisen eine Zeile für jeden eindeutigen Schlüssel in der Tabelle auf, die auf die Datenzeilen mit dem eindeutigen Schlüssel verweist.</span><span class="sxs-lookup"><span data-stu-id="664ea-164">The leaf nodes have one row for each unique key in the table that points to the data rows with that unique key.</span></span>  <span data-ttu-id="664ea-165">Wenn Sie über mehrere Zeilen mit demselben Schlüssel (also über einen nicht eindeutigen nicht gruppierten Index) verfügen, enthält der Indexblattknoten nur eine Zeile, die auf eine der Zeilen verweist, während die anderen Zeilen miteinander verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="664ea-165">If you have multiple rows with the same key (i.e., you have a non-unique nonclustered index), there is only one row in the index leaf node that points to one of the rows with the other rows linked to each other.</span></span>  <span data-ttu-id="664ea-166">Folglich kann für den insgesamt erforderlichen Arbeitsspeicher wie folgt ein Näherungswert ermittelt werden:</span><span class="sxs-lookup"><span data-stu-id="664ea-166">Thus, the total memory required can be approximated by:</span></span>   
    <span data-ttu-id="664ea-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span><span class="sxs-lookup"><span data-stu-id="664ea-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span></span>  
  
 <span data-ttu-id="664ea-168">Nicht gruppierte Indizes eignen sich wie in der folgenden Abfrage veranschaulicht am besten für Bereichssuchen:</span><span class="sxs-lookup"><span data-stu-id="664ea-168">Nonclustered indexes are best when used for range lookups, as exemplified by the following query:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE c2 > 5  
```  
  
##  <a name="memory-for-row-versioning"></a><a name="bkmk_MemoryForRowVersions"></a> <span data-ttu-id="664ea-169">Arbeitsspeicher für die Zeilenversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="664ea-169">Memory for row versioning</span></span>  
 <span data-ttu-id="664ea-170">Um Sperren zu vermeiden, nutzt In-Memory OLTP beim Aktualisieren oder Löschen von Zeilen optimistische Nebenläufigkeit.</span><span class="sxs-lookup"><span data-stu-id="664ea-170">To avoid locks, In-Memory OLTP uses optimistic concurrency when updating or deleting rows.</span></span> <span data-ttu-id="664ea-171">Dies bedeutet, dass bei jedem Zeilenupdate eine zusätzliche Version der Zeile erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="664ea-171">This means that when a row is updated, an additional version of the row is created.</span></span> <span data-ttu-id="664ea-172">Die vorherigen Versionen bleiben im System verfügbar, bis alle Transaktionen, von denen die Version möglicherweise verwendet werden könnte, abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="664ea-172">The system keeps the previous versions available until all transactions that could possibly use the version have finished execution.</span></span> <span data-ttu-id="664ea-173">Wenn eine Zeile gelöscht wird, verhält sich das System auf ähnliche Weise wie bei einem Update und behält die Version bei, bis sie nicht mehr erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="664ea-173">When a row is deleted, the system acts in a similar way to an update, keeping the version available until it is no longer necessary.</span></span> <span data-ttu-id="664ea-174">Durch Lese- und Einfügevorgänge werden keine zusätzlichen Zeilenversionen erstellt.</span><span class="sxs-lookup"><span data-stu-id="664ea-174">Reads and inserts do not create additional row versions.</span></span>  
  
 <span data-ttu-id="664ea-175">Da der Arbeitsspeicher jederzeit einige zusätzliche Zeilen enthalten kann, während darauf gewartet wird, dass der von den Zeilen belegte Speicher im nächsten Zyklus der Garbage Collection freigegeben wird, benötigen Sie genügend Arbeitsspeicher für diese zusätzlichen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="664ea-175">Because there may be a number of additional rows in memory at any time waiting for the garbage collection cycle to release their memory, you must have sufficient memory to accommodate these additional rows.</span></span>  
  
 <span data-ttu-id="664ea-176">Die Anzahl der zusätzlichen Zeilen kann geschätzt werden, indem Sie die Höchstanzahl von Zeilenupdates und -löschungen pro Sekunde berechnen und den Wert mit der Anzahl von Sekunden multiplizieren, die die längste Transaktion dauert (mindestens eine Sekunde).</span><span class="sxs-lookup"><span data-stu-id="664ea-176">The number of additional rows can be estimated by computing the peak number of row updates and deletions per second, then multiplying that by the number of seconds the longest transaction takes (minimum of 1).</span></span>  
  
 <span data-ttu-id="664ea-177">Anschließend wird dieser Wert mit der Zeilengröße multipliziert, um die Anzahl der Bytes zu erhalten, die für die Zeilenversionsverwaltung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="664ea-177">That value is then multiplied by the row size to get the number of bytes you need for row versioning.</span></span>  
  
 `rowVersions = durationOfLongestTransactionInSeconds * peakNumberOfRowUpdatesOrDeletesPerSecond`  
  
 <span data-ttu-id="664ea-178">Der Arbeitsspeicher Bedarf für veraltete Zeilen wird dann geschätzt, indem die Anzahl veralteter Zeilen um die Größe einer Speicher optimierten Tabellenzeile multipliziert wird (siehe Arbeits [Speicher für die Tabelle](#bkmk_MemoryForTable) oben).</span><span class="sxs-lookup"><span data-stu-id="664ea-178">Memory needs for stale rows is then estimated by multiplying the number of stale rows by the size of a memory-optimized table row (see [Memory for the table](#bkmk_MemoryForTable) above).</span></span>  
  
 `memoryForRowVersions = rowVersions * rowSize`  
  
##  <a name="memory-for-table-variables"></a><a name="bkmk_TableVariables"></a> <span data-ttu-id="664ea-179">Arbeitsspeicher für Tabellenvariablen</span><span class="sxs-lookup"><span data-stu-id="664ea-179">Memory for table variables</span></span>  
 <span data-ttu-id="664ea-180">Der für eine Tabellenvariable verwendete Arbeitsspeicher wird erst freigegeben, wenn die Tabellenvariable den Gültigkeitsbereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="664ea-180">Memory used for a table variable is released only when the table variable goes out of scope.</span></span> <span data-ttu-id="664ea-181">Gelöschte Zeilen, einschließlich der während eines Updates gelöschten Zeilen, aus einer Tabellenvariablen unterliegen nicht der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="664ea-181">Deleted rows, including rows deleted as part of an update, from a table variable are not subject to garbage collection.</span></span> <span data-ttu-id="664ea-182">Es wird erst Arbeitsspeicher freigegeben, wenn die Tabellenvariable den Bereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="664ea-182">No memory is released until the table variable exits scope.</span></span>  
  
 <span data-ttu-id="664ea-183">Tabellenvariablen, die in einem umfangreichen SQL-Batch und nicht in einem Prozedurbereich definiert und in zahlreichen Transaktionen verwendet werden, können viel Arbeitsspeicher beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="664ea-183">Table variables defined in a large SQL batch, as opposed to a procedure scope, which are used in many transactions, can consume a lot of memory.</span></span> <span data-ttu-id="664ea-184">Da sie nicht von der Garbage Collection bereinigt werden, können gelöschte Zeilen in einer Tabellenvariablen viel Arbeitsspeicher beanspruchen und die Leistung beeinträchtigen, da Lesevorgänge auch die gelöschten Zeilen durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="664ea-184">Because they are not garbage collected, deleted rows in a table variable can consume a lot memory and degrade performance since read operations need to scan past the deleted rows.</span></span>  
  
##  <a name="memory-for-growth"></a><a name="bkmk_MemoryForGrowth"></a> <span data-ttu-id="664ea-185">Arbeitsspeicher für zukünftiges Wachstum</span><span class="sxs-lookup"><span data-stu-id="664ea-185">Memory for growth</span></span>  
 <span data-ttu-id="664ea-186">Mit den oben aufgeführten Berechnungen wird der Arbeitsspeicherbedarf für die derzeit bestehende Tabelle geschätzt.</span><span class="sxs-lookup"><span data-stu-id="664ea-186">The above calculations estimate your memory needs for the table as it currently exists.</span></span> <span data-ttu-id="664ea-187">Zusätzlich zu diesem Arbeitsspeicher müssen Sie einplanen, dass die Tabelle anwächst, und ausreichend Arbeitsspeicher für zukünftiges Wachstum vorsehen.</span><span class="sxs-lookup"><span data-stu-id="664ea-187">In addition to this memory, you need to estimate the growth of the table and provide sufficient memory to accommodate that growth.</span></span>  <span data-ttu-id="664ea-188">Wenn Sie beispielsweise ein zehnprozentiges Wachstum erwarten, müssen Sie die oben ermittelten Ergebnisse mit 1,1 multiplizieren, um den insgesamt erforderlichen Arbeitsspeicher für die Tabelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="664ea-188">For example, if you anticipate 10% growth then you need to multiple the results from above by 1.1 to get the total memory needed for your table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664ea-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="664ea-189">See Also</span></span>  
 [<span data-ttu-id="664ea-190">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="664ea-190">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
