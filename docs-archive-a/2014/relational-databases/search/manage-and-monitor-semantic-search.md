---
title: Verwalten und Überwachen der semantischen Suche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], managing
- semantic search [SQL Server], monitoring
ms.assetid: eb5c3b29-da70-42aa-aa97-7d35a3f1eb98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16e3af1d37f177dfe6d4e0cb090e7b8b0a4988d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717680"
---
# <a name="manage-and-monitor-semantic-search"></a><span data-ttu-id="7ffdf-102">Verwalten und Überwachen der semantischen Suche</span><span class="sxs-lookup"><span data-stu-id="7ffdf-102">Manage and Monitor Semantic Search</span></span>
  <span data-ttu-id="7ffdf-103">In diesem Thema werden der Prozess der semantischen Indizierung sowie die Tasks im Zusammenhang mit der Verwaltung und Überwachung der Indizes beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-103">Describes the process of semantic indexing and the tasks related to managing and monitoring the indexes.</span></span>  
  
##  <a name="how-to-check-the-status-of-semantic-indexing"></a><a name="HowToMonitorStatus"></a><span data-ttu-id="7ffdf-104">Vorgehensweise: Überprüfen des Status der semantischen Indizierung</span><span class="sxs-lookup"><span data-stu-id="7ffdf-104">How To: Check the Status of Semantic Indexing</span></span>  
 <span data-ttu-id="7ffdf-105">**Ist die erste Phase der semantischen Indizierung abgeschlossen?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-105">**Is the first phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="7ffdf-106">Fragen Sie die dynamische Verwaltungssicht ab, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), und überprüfen Sie die **status**- und **status_description**-Spalten.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-106">Query the dynamic management view, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), and check the **status** and **status_description** columns.</span></span>  
  
 <span data-ttu-id="7ffdf-107">Die erste Phase der Indizierung umfasst die Auffüllung des Volltextschlüsselwortindexes und des semantischen Schlüsselausdruckindexes sowie die Extraktion der Dokumentähnlichkeitsdaten.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-107">The first phase of indexing includes the population of the full-text keyword index and the semantic key phrase index, as well as the extraction of document similarity data.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_index_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="7ffdf-108">**Ist die zweite Phase der semantischen Indizierung abgeschlossen?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-108">**Is the second phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="7ffdf-109">Fragen Sie die dynamische Verwaltungssicht ab, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), und überprüfen Sie die **status**- und **status_description**-Spalten.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-109">Query the dynamic management view, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), and check the **status** and **status_description** columns..</span></span>  
  
 <span data-ttu-id="7ffdf-110">Die zweite Phase der Indizierung umfasst die Auffüllung des semantischen Dokumentähnlichkeitsindexes.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-110">The second phase of indexing includes the population of the semantic document similarity index.</span></span>  
  
```wql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_semantic_similarity_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
##  <a name="how-to-check-the-size-of-the-semantic-indexes"></a><a name="HowToCheckSize"></a><span data-ttu-id="7ffdf-111">Gewusst wie: Überprüfen der Größe der semantischen Indizes</span><span class="sxs-lookup"><span data-stu-id="7ffdf-111">How To: Check the Size of the Semantic Indexes</span></span>  
 <span data-ttu-id="7ffdf-112">**Was ist die logische Größe eines semantischen Schlüsselausdruckindexes oder eines semantischen Dokumentähnlichkeitsindexes?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-112">**What is the logical size of a semantic key phrase index or a semantic document similarity index?**</span></span>  
 <span data-ttu-id="7ffdf-113">Fragen Sie die dynamische Verwaltungssicht ab, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ffdf-113">Query the dynamic management view, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="7ffdf-114">Die logische Größe wird in Anzahl von Indexseiten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-114">The logical size is displayed in number of index pages.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_db_fts_index_physical_stats WHERE object_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="7ffdf-115">**Wie groß sind die Volltext- und die semantischen Indizes für einen Volltextkatalog insgesamt?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-115">**What is the total size of the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="7ffdf-116">Fragen Sie die Eigenschaft **IndexSize** der Metadatenfunktion [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-116">Query the **IndexSize** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'IndexSize')  
GO  
```  
  
 <span data-ttu-id="7ffdf-117">**Wie viele Elemente werden in den Volltext- und den semantischen Indizes für einen Volltextkatalog indiziert?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-117">**How many items are indexed in the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="7ffdf-118">Fragen Sie die Eigenschaft **ItemCount** der Metadatenfunktion [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-118">Query the **ItemCount** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'ItemCount')  
GO  
```  
  
##  <a name="how-to-force-the-population-of-the-semantic-indexes"></a><a name="HowToForcePopulation"></a><span data-ttu-id="7ffdf-119">Gewusst wie: Erzwingen der Auffüllung der semantischen Indizes</span><span class="sxs-lookup"><span data-stu-id="7ffdf-119">How To: Force the Population of the Semantic Indexes</span></span>  
 <span data-ttu-id="7ffdf-120">Sie können die Auffüllung der Volltextindizes und semantischen Indizes mit der START/STOP/PAUSE-Klausel oder der RESUME POPULATION-Klausel mit der gleichen Syntax und dem für Volltextindizes beschriebenen Verhalten erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-120">You can force the population of full-text and semantic indexes by using the START/STOP/PAUSE or RESUME POPULATION clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="7ffdf-121">Weitere Informationen finden Sie unter [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) und [Auffüllen von Volltextindizes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="7ffdf-121">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) and [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="7ffdf-122">Da die semantische Indizierung von der Volltextindizierung abhängig ist, werden semantische Indizes nur dann aufgefüllt, wenn die zugeordneten Volltextindizes aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-122">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="7ffdf-123">**Beispiel: Starten einer vollständigen Auffüllung von Volltext- und semantischen Indizes**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-123">**Example: Start a full population of full-text and semantic indexes**</span></span>  
  
 <span data-ttu-id="7ffdf-124">Im folgenden Beispiel wird die vollständige Auffüllung von sowohl Volltext- als auch semantischen Indizes gestartet, indem ein vorhandener Volltextindex in der **Production.Document** -Tabelle in der AdventureWorks2012-Beispieldatenbank geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-124">The following example starts full population of both full-text and semantic indexes by altering an existing full-text index on the **Production.Document** table in the AdventureWorks2012 sample database.</span></span>  
  
```vb  
USE AdventureWorks2012  
GO  
  
ALTER FULLTEXT INDEX ON Production.Document  
    START FULL POPULATION  
GO  
```  
  
##  <a name="how-to-disable-or-re-enable-semantic-indexing"></a><a name="HowToDisableIndexing"></a><span data-ttu-id="7ffdf-125">Vorgehensweise: deaktivieren oder erneutes Aktivieren der semantischen Indizierung</span><span class="sxs-lookup"><span data-stu-id="7ffdf-125">How To: Disable or Re-enable Semantic Indexing</span></span>  
 <span data-ttu-id="7ffdf-126">Sie können die Volltextindizierung oder semantische Indizierung mit der ENABLE/DISABLE-Klausel mit der gleichen Syntax und dem für Volltextindizes beschriebenen Verhalten deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-126">You can enable or disable full-text or semantic indexing by using the ENABLE/DISABLE clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="7ffdf-127">Weitere Informationen finden Sie unter [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ffdf-127">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="7ffdf-128">Wenn die semantische Indizierung deaktiviert und angehalten wurde, funktionieren Abfragen über semantische Daten weiterhin und geben zuvor indizierte Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-128">When semantic indexing is disabled and suspended, queries over semantic data continue to work successfully and to return previously indexed data.</span></span> <span data-ttu-id="7ffdf-129">Dieses Verhalten ist nicht konsistent mit dem Verhalten der Volltextsuche.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-129">This behavior is not consistent with the behavior of Full-Text Search.</span></span>  
  
```sql  
-- To disable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name DISABLE  
GO  
  
-- To re-enable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name ENABLE  
GO  
```  
  
##  <a name="phases-of-semantic-indexing"></a><a name="SemanticIndexing"></a><span data-ttu-id="7ffdf-130">Phasen der semantischen Indizierung</span><span class="sxs-lookup"><span data-stu-id="7ffdf-130">Phases of Semantic Indexing</span></span>  
 <span data-ttu-id="7ffdf-131">Bei der semantischen Suche werden zwei Arten von Daten für jede Spalte indiziert, für die sie aktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="7ffdf-131">Semantic Search indexes two kinds of data for each column on which it is enabled:</span></span>  
  
1.  <span data-ttu-id="7ffdf-132">**Schlüsselbegriffe**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-132">**Key phrases**</span></span>  
  
2.  <span data-ttu-id="7ffdf-133">**Dokumentähnlichkeit**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-133">**Document similarity**</span></span>  
  
 <span data-ttu-id="7ffdf-134">Die semantische Indizierung erfolgt in zwei Phase, in Verbindung mit der Volltextindizierung:</span><span class="sxs-lookup"><span data-stu-id="7ffdf-134">Semantic indexing occurs in two phases, in conjunction with full-text indexing:</span></span>  
  
1.  <span data-ttu-id="7ffdf-135">**Phase 1**.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-135">**Phase 1**.</span></span> <span data-ttu-id="7ffdf-136">Der Volltextschlüsselwortindex und der semantische Schlüsselausdruckindex werden zur gleichen Zeit parallel aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-136">The full-text keyword index and the semantic key phrase index are populated in parallel at the same time.</span></span> <span data-ttu-id="7ffdf-137">Die zur Indizierung der Dokumentähnlichkeit erforderlichen Daten werden ebenfalls zu diesem Zeitpunkt extrahiert.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-137">The data required to index document similarity is also extracted at this time.</span></span>  
  
2.  <span data-ttu-id="7ffdf-138">**Phase 2**.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-138">**Phase 2**.</span></span> <span data-ttu-id="7ffdf-139">Anschließend wird der semantische Dokumentähnlichkeitsindex aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-139">The semantic document similarity index is then populated.</span></span> <span data-ttu-id="7ffdf-140">Dieser Index ist von beiden Indizes abhängig, die in der vorherigen Phase aufgefüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-140">This index depends on both indexes that were populated in the preceding phase.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-semantic-indexes-are-not-populated"></a><a name="ProblemNotPopulated"></a><span data-ttu-id="7ffdf-141">Problem: semantische Indizes werden nicht aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-141">Problem: Semantic Indexes Are Not Populated</span></span>  
 <span data-ttu-id="7ffdf-142">**Werden die zugeordneten Volltextindizes aufgefüllt?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-142">**Are the associated full-text indexes populated?**</span></span>  
 <span data-ttu-id="7ffdf-143">Da die semantische Indizierung von der Volltextindizierung abhängig ist, werden semantische Indizes nur dann aufgefüllt, wenn die zugeordneten Volltextindizes aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="7ffdf-143">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="7ffdf-144">**Sind die Volltextsuche und die semantische Suche ordnungsgemäß installiert und konfiguriert?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-144">**Are full-text search and semantic search properly installed and configured?**</span></span>  
 <span data-ttu-id="7ffdf-145">Weitere Informationen finden Sie unter [Installieren und Konfigurieren der semantischen Suche](install-and-configure-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="7ffdf-145">For more information, see [Install and Configure Semantic Search](install-and-configure-semantic-search.md).</span></span>  
  
 <span data-ttu-id="7ffdf-146">**Ist der FDHOST-Dienst nicht verfügbar, oder gibt es eine andere Bedingung, aufgrund der die Volltextindizierung fehlschlagen würde?**</span><span class="sxs-lookup"><span data-stu-id="7ffdf-146">**Is the FDHOST service not available, or is there another condition that would cause full-text indexing to fail?**</span></span>  
 <span data-ttu-id="7ffdf-147">Weitere Informationen finden Sie unter [Behandeln von Problemen mit der Volltextindizierung](troubleshoot-full-text-indexing.md).</span><span class="sxs-lookup"><span data-stu-id="7ffdf-147">For more information, see [Troubleshoot Full-Text Indexing](troubleshoot-full-text-indexing.md).</span></span>  
  
  
