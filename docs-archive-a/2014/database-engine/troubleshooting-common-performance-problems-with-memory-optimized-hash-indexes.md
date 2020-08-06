---
title: Problembehandlung bei häufigen Leistungsproblemen mit Speicher optimierten Hash Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 1954a997-7585-4713-81fd-76d429b8d095
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cef98571edd7736bc45ba8caf17451007a74cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696030"
---
# <a name="troubleshooting-common-performance-problems-with-memory-optimized-hash-indexes"></a><span data-ttu-id="f196c-102">Problembehandlung für häufige Leistungsprobleme bei speicheroptimierten Hashindizes</span><span class="sxs-lookup"><span data-stu-id="f196c-102">Troubleshooting Common Performance Problems with Memory-Optimized Hash Indexes</span></span>
  <span data-ttu-id="f196c-103">Der Schwerpunkt dieses Themas liegt auf der Problembehandlung und dem Umgehen von häufigen Problemen mit Hashindizes.</span><span class="sxs-lookup"><span data-stu-id="f196c-103">This topic will focus on troubleshooting and working around common issues with hash indexes.</span></span>  
  
## <a name="search-requires-a-subset-of-hash-index-key-columns"></a><span data-ttu-id="f196c-104">Suche erfordert eine Teilmenge von Hashindex-Schlüsselspalten</span><span class="sxs-lookup"><span data-stu-id="f196c-104">Search Requires a Subset of Hash Index Key Columns</span></span>  
 <span data-ttu-id="f196c-105">**Problem:** Bei Hashindizes sind Werte für alle Indexschlüsselspalten erforderlich, um den Hashwert zu berechnen und die entsprechenden Zeilen in der Hashtabelle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f196c-105">**Issue:** Hash indexes require values for all index key columns in order to compute the hash value, and locate the corresponding rows in the hash table.</span></span> <span data-ttu-id="f196c-106">Wenn eine Abfrage nur Gleichheitsprädikate für eine Teilmenge der Indexschlüssel in der WHERE-Klausel enthält, kann [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] daher nicht mithilfe einer Indexsuche die Zeilen suchen, die den Prädikaten in der WHERE-Klausel entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f196c-106">Therefore, if a query includes equality predicates for only a subset of the index keys in the WHERE clause, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot use an index seek to locate the rows corresponding to the predicates in the WHERE clause.</span></span>  
  
 <span data-ttu-id="f196c-107">Im Gegensatz dazu unterstützen geordnete Indizes wie datenträgerbasierte nicht gruppierte Indizes und speicheroptimierte nicht gruppierte Indizes die Indexsuche mit einer Teilmenge der Indexschlüsselspalten, sofern es sich um die führenden Spalten im Index handelt.</span><span class="sxs-lookup"><span data-stu-id="f196c-107">In contrast, ordered indexes like the disk-based nonclustered indexes and the memory-optimized nonclustered indexes support index seek on a subset of the index key columns, as long as they are the leading columns in the index.</span></span>  
  
 <span data-ttu-id="f196c-108">**Symptom:** Dies führt zu einer Leistungsverringerung, da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vollständige Tabellenscans anstelle einer Indexsuche ausführen muss, die normalerweise schneller ist.</span><span class="sxs-lookup"><span data-stu-id="f196c-108">**Symptom:** This results in a performance degradation, as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] needs to execute full table scans rather than an index seek, which is typically a faster operation.</span></span>  
  
 <span data-ttu-id="f196c-109">**Problembehandlung:** Neben der Leistungsverringerung zeigt die Überprüfung der Abfragepläne einen Scan anstelle einer Indexsuche.</span><span class="sxs-lookup"><span data-stu-id="f196c-109">**How to troubleshoot:** Besides the performance degradation, inspection of the query plans will show a scan instead of an index seek.</span></span> <span data-ttu-id="f196c-110">Bei einer relativ einfachen Abfrage zeigt die Überprüfung des Abfragetexts und der Indexdefinition auch, ob für die Suche eine Teilmenge der Indexschlüsselspalten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f196c-110">If the query is fairly simple, inspection of the query text and index definition will also show whether the search requires a subset of the index key columns.</span></span>  
  
 <span data-ttu-id="f196c-111">Betrachten Sie die folgende Tabelle und Abfrage:</span><span class="sxs-lookup"><span data-stu-id="f196c-111">Consider the following table and query:</span></span>  
  
```sql  
CREATE TABLE [dbo].[od]  
(  
     o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
     CONSTRAINT PK_od PRIMARY KEY NONCLUSTERED HASH (o_id, od_id) WITH (BUCKET_COUNT = 10000)  
)  
WITH (MEMORY_OPTIMIZED = ON)  
  
 SELECT p_id  
 FROM dbo.od  
 WHERE o_id=1  
```  
  
 <span data-ttu-id="f196c-112">Die Tabelle verfügt über einen Hashindex für die beiden Spalten (o_id, od_id), während die Abfrage ein Gleichheitsprädikat für (o_id) enthält.</span><span class="sxs-lookup"><span data-stu-id="f196c-112">The table has a hash index on the two columns (o_id, od_id), while the query has an equality predicate on (o_id).</span></span> <span data-ttu-id="f196c-113">Da die Abfrage nur Gleichheitsprädikate für eine Teilmenge der Indexschlüsselspalten enthält, kann [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] keinen Indexsuchvorgang mit "PK_od" ausführen. Stattdessen muss [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf einen vollständigen Indexscan zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="f196c-113">As the query has equality predicates on only a subset of the index key columns, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot perform an index seek operation using PK_od; instead, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has to revert to a full index scan.</span></span>  
  
 <span data-ttu-id="f196c-114">**Problemumgehungen:** Es gibt eine Reihe von möglichen Problemumgehungen.</span><span class="sxs-lookup"><span data-stu-id="f196c-114">**Workarounds:** There are a number of possible workarounds.</span></span> <span data-ttu-id="f196c-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f196c-115">For example:</span></span>  
  
-   <span data-ttu-id="f196c-116">Erstellen Sie den Index mit dem Typ eines nicht gruppierten Indexes anstelle eines nicht gruppierten Hash erneut.</span><span class="sxs-lookup"><span data-stu-id="f196c-116">Recreate the index as type nonclustered instead of nonclustered hash.</span></span> <span data-ttu-id="f196c-117">Der speicheroptimierte nicht gruppierte Index wird sortiert, und somit kann [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] eine Indexsuche der führenden Indexschlüsselspalten ausführen.</span><span class="sxs-lookup"><span data-stu-id="f196c-117">The memory-optimized nonclustered index is ordered, and thus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can perform an index seek on the leading index key columns.</span></span> <span data-ttu-id="f196c-118">Die resultierende Primärschlüsseldefinition für das Beispiel lautet `constraint PK_od primary key nonclustered`.</span><span class="sxs-lookup"><span data-stu-id="f196c-118">The resulting primary key definition for the example would be `constraint PK_od primary key nonclustered`.</span></span>  
  
-   <span data-ttu-id="f196c-119">Ändern Sie den aktuellen Indexschlüssel, sodass er den Spalten in der WHERE-Klausel entspricht.</span><span class="sxs-lookup"><span data-stu-id="f196c-119">Change the current index key to match the columns in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="f196c-120">Fügen Sie einen neuen Hashindex hinzu, der den Spalten in der WHERE-Klausel der Abfrage entspricht.</span><span class="sxs-lookup"><span data-stu-id="f196c-120">Add a new hash index that matches with the columns in the WHERE clause of the query.</span></span> <span data-ttu-id="f196c-121">Im Beispiel würde dies zu folgender Tabellendefinition führen:</span><span class="sxs-lookup"><span data-stu-id="f196c-121">In the example, the resulting table definition would look at follows:</span></span>  
  
    ```sql  
    CREATE TABLE dbo.od  
     ( o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
  
     CONSTRAINT PK_od PRIMARY KEY   
     NONCLUSTERED HASH (o_id,od_id) WITH (BUCKET_COUNT=10000),  
  
     INDEX ix_o_id NONCLUSTERED HASH (o_id) WITH (BUCKET_COUNT=10000)  
  
     ) WITH (MEMORY_OPTIMIZED=ON)  
    ```  
  
 <span data-ttu-id="f196c-122">Beachten Sie, dass ein speicheroptimierter Hashindex nicht einwandfrei funktioniert, wenn viele doppelte Zeilen für einen angegebenen Indexschlüsselwert vorhanden sind: Wenn im Beispiel die Anzahl der eindeutigen Werte für die Spalte "o_id" erheblich kleiner als die Anzahl der Zeilen in der Tabelle ist, wäre es nicht optimal, einen Index für (o_id) hinzuzufügen. Die bessere Lösung würde darin bestehen, den Typ des Indexes "PK_od" von Hash zu nicht gruppiert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f196c-122">Note that a memory-optimized hash index does not perform optimally if there are a lot of duplicate rows for a given index key value: in the example, if the number of unique values for the column o_id is much smaller than the number of rows in the table, it would not be optimal to add an index on (o_id); instead, changing the type of the index PK_od from hash to nonclustered would be the better solution.</span></span> <span data-ttu-id="f196c-123">Weitere Informationen finden Sie unter [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="f196c-123">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f196c-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f196c-124">See Also</span></span>  
 [<span data-ttu-id="f196c-125">Indizes für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="f196c-125">Indexes on Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
