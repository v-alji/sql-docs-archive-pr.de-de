---
title: Einschränken von Suchergebnissen mit RANK | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- row ranking [full-text search]
- relevance ranking values [full-text search]
- full-text search [SQL Server], rankings
- index rankings [full-text search]
- ranked results [full-text search]
- rankings [full-text search]
- per-row rank values [full-text search]
ms.assetid: 06a776e6-296c-4ec7-9fa5-0794709ccb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab1b930b3238cb541965e1984d1561f1a1c22d87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717701"
---
# <a name="limit-search-results-with-rank"></a><span data-ttu-id="e9bbc-102">Einschränken von Suchergebnissen mit RANK</span><span class="sxs-lookup"><span data-stu-id="e9bbc-102">Limit Search Results with RANK</span></span>
  <span data-ttu-id="e9bbc-103">Die Funktionen [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) und [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) geben eine Spalte mit dem Namen RANK zurück, die Ordinalwerte zwischen 0 und 1000 (Rangwerte) enthält.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-103">The [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) and [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) functions return a column named RANK that contains ordinal values from 0 through 1000 (rank values).</span></span> <span data-ttu-id="e9bbc-104">Diese Werte werden verwendet, um die Rangfolge der zurückgegebenen Zeilen gemäß ihrer Übereinstimmung mit den Auswahlkriterien festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-104">These values are used to rank the rows returned according to how well they match the selection criteria.</span></span> <span data-ttu-id="e9bbc-105">Die Rangwerte geben lediglich eine relative Relevanzreihenfolge der Zeilen im Resultset an, wobei ein niedrigerer Wert eine niedrigere Relevanz anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-105">The rank values indicate only a relative order of relevance of the rows in the result set, with a lower value indicating lower relevance.</span></span> <span data-ttu-id="e9bbc-106">Die tatsächlichen Werte sind nicht von Bedeutung und unterscheiden sich i. d. R. bei jeder Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-106">The actual values are unimportant and typically differ each time the query is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9bbc-107">Die CONTAINS- und FREETEXT-Prädikate geben keine Rangwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-107">The CONTAINS and FREETEXT predicates do not return any rank values.</span></span>  
  
 <span data-ttu-id="e9bbc-108">Die Anzahl der Elemente, die eine Suchbedingung erfüllen, ist oft sehr groß.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-108">The number of items matching a search condition is often very large.</span></span> <span data-ttu-id="e9bbc-109">Damit CONTAINSTABLE- oder FREETEXTTABLE-Abfragen nicht zu viele Übereinstimmungen zurückgeben, können Sie den optionalen *top_n_by_rank* -Parameter verwenden, mit dem nur eine Teilmenge der Zeilen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-109">To prevent CONTAINSTABLE or FREETEXTTABLE queries from returning too many matches, use the optional *top_n_by_rank* parameter, which returns only a subset of rows.</span></span> <span data-ttu-id="e9bbc-110">*top_n_by_rank* ist ein Integer-Wert ( *n*) mit dem festgelegt wird, dass nur die *n* höchsten Übereinstimmungen in absteigender Reihenfolge zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-110">*top_n_by_rank* is an integer value, *n*, that specifies that only the *n* highest ranked matches are to be returned, in descending order.</span></span> <span data-ttu-id="e9bbc-111">Wenn *top_n_by_rank* mit anderen Parametern kombiniert wird, werden von der Abfrage möglicherweise weniger Zeilen zurückgegeben als die Anzahl von Zeilen, die mit allen Prädikaten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-111">If *top_n_by_rank* is combined with other parameters, the query could return fewer rows than the number of rows that actually match all the predicates.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="e9bbc-112">ordnet die Übereinstimmungen nach Rang und gibt nur die angegebene Anzahl Zeilen zurück.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-112">orders the matches by rank and returns only up to the specified number of rows.</span></span> <span data-ttu-id="e9bbc-113">Diese Einschränkung kann zu einer deutlichen Leistungssteigerung führen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-113">This choice can result in a dramatic increase in performance.</span></span> <span data-ttu-id="e9bbc-114">So wird z. B. eine Abfrage, die normalerweise 100.000 Zeilen aus einer Tabelle mit 1 Million Zeilen zurückgeben würde, bedeutend schneller verarbeitet, wenn nur die obersten 100 Zeilen angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-114">For example, a query that would normally return 100,000 rows from a table of one million rows are processed more quickly if only the top 100 rows are requested.</span></span>  
  
##  <a name="examples-of-using-rank-to-limit-search-results"></a><a name="examples"></a> <span data-ttu-id="e9bbc-115">Beispiele zur Verwendung von RANK zum Einschränken der Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="e9bbc-115">Examples of Using RANK to Limit Search Results</span></span>  
  
### <a name="example-a-searching-for-only-the-top-three-matches"></a><span data-ttu-id="e9bbc-116">Beispiel A: Suchen nach ausschließlich den obersten drei Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="e9bbc-116">Example A: Searching for only the top three matches</span></span>  
 <span data-ttu-id="e9bbc-117">Im folgenden Beispiel werden mit CONTAINSTABLE nur die obersten drei Übereinstimmungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-117">The following example uses CONTAINSTABLE to return only the top three matches.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT K.RANK, AddressLine1, City  
FROM Person.Address AS A  
  INNER JOIN  
  CONTAINSTABLE(Person.Address, AddressLine1, 'ISABOUT ("des*",  
    Rue WEIGHT(0.5),  
    Bouchers WEIGHT(0.9))',  
    3) AS K  
  ON A.AddressID = K.[KEY]  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
RANK        Address                          City  
----------- -------------------------------- ------------------------------  
172         9005, rue des Bouchers           Paris  
172         5, rue des Bouchers              Orleans  
172         5, rue des Bouchers              Metz  
  
(3 row(s) affected)  
```  
  
  
### <a name="example-b-searching-for-the-top-ten-matches"></a><span data-ttu-id="e9bbc-118">Beispiel B: Suchen nach ausschließlich den obersten zehn Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="e9bbc-118">Example B: Searching for the top ten matches</span></span>  
 <span data-ttu-id="e9bbc-119">Im folgenden Beispiel wird CONTAINSTABLE verwendet, um die Beschreibung der ersten 5 Produkte zurückzugeben, bei denen die `Description` -Spalte das Wort "aluminium" in der Nähe des Worts "light" oder "lightweight" enthält.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-119">The following example uses CONTAINSTABLE to return the description of the top 5 products where the `Description` column contains the word "aluminum" near either the word "light" or the word "lightweight".</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY]  
GO  
```  
  
  
##  <a name="how-search-query-results-are-ranked"></a><a name="how"></a> <span data-ttu-id="e9bbc-120">Ordnen von Suchabfrageergebnissen nach Rang</span><span class="sxs-lookup"><span data-stu-id="e9bbc-120">How Search Query Results Are Ranked</span></span>  
 <span data-ttu-id="e9bbc-121">Die Volltextsuche in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] kann eine optionale Bewertung (einen Rangwert) generieren, die die Relevanz der von einer Volltextabfrage zurückgegebenen Daten angibt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-121">Full-text search in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can generate an optional score (or rank value) that indicates the relevance of the data returned by a full-text query.</span></span> <span data-ttu-id="e9bbc-122">Dieser Rangwert wird für jede Zeile berechnet und als Sortierkriterium verwendet, um das Resultset einer bestimmten Abfrage nach Relevanz zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-122">This rank value is calculated on every row and can be used as an ordering criteria to sort the result set of a given query by relevance.</span></span> <span data-ttu-id="e9bbc-123">Die Rangwerte geben lediglich eine relative Relevanzreihenfolge der Zeilen im Resultset an.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-123">The rank values indicate only a relative order of relevance of the rows in the result set.</span></span> <span data-ttu-id="e9bbc-124">Die tatsächlichen Werte sind nicht von Bedeutung und unterscheiden sich i. d. R. bei jeder Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-124">The actual values are unimportant and typically differ each time the query is run.</span></span> <span data-ttu-id="e9bbc-125">Der Rangwert hat keinerlei abfrageüberschreitende Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-125">The rank value does not hold any significance across queries.</span></span>  
  
### <a name="statistics-for-ranking"></a><span data-ttu-id="e9bbc-126">Statistiken für die Rangfolge</span><span class="sxs-lookup"><span data-stu-id="e9bbc-126">Statistics for Ranking</span></span>  
 <span data-ttu-id="e9bbc-127">Beim Erstellen eines Indexes werden Statistiken für die Reihenfolgebestimmung gesammelt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-127">When an index is built, statistics are collected for use in ranking.</span></span> <span data-ttu-id="e9bbc-128">Der Vorgang der Erstellung eines Volltextkatalogs führt nicht direkt zu einer einzelnen Indexstruktur.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-128">The process of building a full-text catalog does not directly result in a single index structure.</span></span> <span data-ttu-id="e9bbc-129">Stattdessen erstellt die Volltext-Engine für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] beim Indizieren der Daten Zwischenindizes.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-129">Instead, the Full-Text Engine for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] creates intermediate indexes as data is indexed.</span></span> <span data-ttu-id="e9bbc-130">Anschließend werden diese Indizes von der Volltextsuch-Engine bei Bedarf in einen größeren Index zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-130">The Full-Text Engine then merges these indexes into a larger index as needed.</span></span> <span data-ttu-id="e9bbc-131">Dieser Vorgang kann mehrfach wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-131">This process can be repeated many times.</span></span> <span data-ttu-id="e9bbc-132">Die Volltextsuch-Engine führt einen "Mastermergeprozess" aus, bei dem alle Zwischenindizes zu einem größeren Masterindex kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-132">The Full-Text Engine then conducts a "master merge" that combines all of the intermediate indexes into one large master index.</span></span>  
  
 <span data-ttu-id="e9bbc-133">Auf jeder Zwischenstufe werden Statistiken erhoben.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-133">Statistics are collected at each intermediate index level.</span></span> <span data-ttu-id="e9bbc-134">Die Statistiken werden beim Zusammenführen der Indizes zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-134">The statistics are merged when the indexes are merged.</span></span> <span data-ttu-id="e9bbc-135">Einige statistische Werte können nur während des Mastermergeprozesses generiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-135">Some statistical values can only be generated during the master merging process.</span></span>  
  
 <span data-ttu-id="e9bbc-136">Beim Generieren der Rangfolge für ein Abfrageresultset verwendet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Statistiken vom größten Zwischenindex.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-136">While ranking a query result set, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses statistics from the largest intermediate index.</span></span> <span data-ttu-id="e9bbc-137">Dies hängt davon ab, ob Zwischenindizes zusammengeführt wurden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-137">This depends on whether intermediate indexes have been merged or not.</span></span> <span data-ttu-id="e9bbc-138">Demzufolge kann die Rangfolgestatistik unterschiedlich genau ausfallen, wenn die Zwischenindizes nicht zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-138">As a result, ranking statistics can vary in accuracy if the intermediate indexes have not been merged.</span></span> <span data-ttu-id="e9bbc-139">Dies erklärt, warum dieselbe Abfrage zu verschiedenen Zeitpunkten unterschiedliche Rangergebnisse zurückgeben kann, wenn volltextindizierte Daten hinzugefügt, geändert und gelöscht werden und wenn die kleineren Indizes zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-139">This explains why the same query can return different rank results over time as full-text indexed data is added, modified, and deleted, and as the smaller indexes are merged.</span></span>  
  
 <span data-ttu-id="e9bbc-140">Häufig werden die Statistiken gerundet, um die Größe des Indexes und die Komplexität der Berechnung zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-140">To minimize the size of the index and computational complexity, statistics are often rounded.</span></span>  
  
 <span data-ttu-id="e9bbc-141">Die nachstehende Liste enthält einige häufig verwendete Begriffe und statistische Werte, die beim Berechnen des Rangs wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="e9bbc-141">The list below includes some commonly used terms and statistical values that are important in calculating rank.</span></span>  
  
 <span data-ttu-id="e9bbc-142">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e9bbc-142">Property</span></span>  
 <span data-ttu-id="e9bbc-143">Eine volltextindizierte Spalte der Zeile.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-143">A full-text indexed column of the row.</span></span>  
  
 <span data-ttu-id="e9bbc-144">Dokument</span><span class="sxs-lookup"><span data-stu-id="e9bbc-144">Document</span></span>  
 <span data-ttu-id="e9bbc-145">Die Entität, die in Abfragen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-145">The entity that is returned in queries.</span></span> <span data-ttu-id="e9bbc-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] entspricht dies einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] this corresponds to a row.</span></span> <span data-ttu-id="e9bbc-147">Ein Dokument kann mehrere Eigenschaften aufweisen, ebenso wie eine Zeile mehrere volltextindizierte Spalten aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-147">A document can have multiple properties, just as a row can have multiple full-text indexed columns.</span></span>  
  
 <span data-ttu-id="e9bbc-148">Index</span><span class="sxs-lookup"><span data-stu-id="e9bbc-148">Index</span></span>  
 <span data-ttu-id="e9bbc-149">Ein einzelner invertierter Index mindestens eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-149">A single inverted index of one or more documents.</span></span> <span data-ttu-id="e9bbc-150">Er kann sich vollständig im Arbeitsspeicher oder auf dem Datenträger befinden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-150">This may be entirely in memory or on disk.</span></span> <span data-ttu-id="e9bbc-151">Viele Abfragestatistiken sind relativ zu dem jeweiligen Index, mit dem der Vergleich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-151">Many query statistics are relative to the individual index where the match occurred.</span></span>  
  
 <span data-ttu-id="e9bbc-152">Volltextkatalog</span><span class="sxs-lookup"><span data-stu-id="e9bbc-152">Full-Text Catalog</span></span>  
 <span data-ttu-id="e9bbc-153">Eine Auflistung von Zwischenindizes, die für Abfragen als eine Entität behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-153">A collection of intermediate indexes treated as one entity for queries.</span></span> <span data-ttu-id="e9bbc-154">Kataloge sind die Organisationseinheit, die für den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Administrator sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-154">Catalogs are the unit of organization visible to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="e9bbc-155">Wort, Token oder Element</span><span class="sxs-lookup"><span data-stu-id="e9bbc-155">Word, token or item</span></span>  
 <span data-ttu-id="e9bbc-156">Die Vergleichseinheit in der Volltext-Engine.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-156">The unit of matching in the full-text engine.</span></span> <span data-ttu-id="e9bbc-157">Textströme aus Dokumenten werden durch eine sprachspezifische Wörtertrennung in Wörter oder Token zerlegt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-157">Streams of text from documents are tokenized into words, or tokens by language-specific word breakers.</span></span>  
  
 <span data-ttu-id="e9bbc-158">Vorkommen</span><span class="sxs-lookup"><span data-stu-id="e9bbc-158">Occurrence</span></span>  
 <span data-ttu-id="e9bbc-159">Der von der Wörtererkennung bestimmte Offset eines Worts in einer Dokumenteigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-159">The word offset in a document property as determined by the word breaker.</span></span> <span data-ttu-id="e9bbc-160">Das erste Wort stellt Vorkommen 1 dar, das nächste 2 usw.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-160">The first word is at occurrence 1, the next at 2, and so on.</span></span> <span data-ttu-id="e9bbc-161">Um falsche Treffer in Ausdrucks- und NEAR-Abfragen zu vermeiden, bewirken Satzende- und Absatzendezeichen größere Abstände zwischen den Vorkommen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-161">In order to avoid false positives in phrase and proximity queries, end-of-sentence and end-of-paragraph introduce larger occurrence gaps.</span></span>  
  
 <span data-ttu-id="e9bbc-162">TermFrequency</span><span class="sxs-lookup"><span data-stu-id="e9bbc-162">TermFrequency</span></span>  
 <span data-ttu-id="e9bbc-163">Die Anzahl der Vorkommen des Schlüsselwerts in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-163">The number times the key value occurs in a row.</span></span>  
  
 <span data-ttu-id="e9bbc-164">IndexedRowCount</span><span class="sxs-lookup"><span data-stu-id="e9bbc-164">IndexedRowCount</span></span>  
 <span data-ttu-id="e9bbc-165">Gesamtanzahl der indizierten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-165">Total number of rows indexed.</span></span> <span data-ttu-id="e9bbc-166">Diese wird aus den in den Zwischenindizes geführten Zählern berechnet.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-166">This is computed, based on counts maintained in the intermediate indexes.</span></span> <span data-ttu-id="e9bbc-167">Die Genauigkeit der Anzahl kann variieren.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-167">This number can vary in accuracy.</span></span>  
  
 <span data-ttu-id="e9bbc-168">KeyRowCount</span><span class="sxs-lookup"><span data-stu-id="e9bbc-168">KeyRowCount</span></span>  
 <span data-ttu-id="e9bbc-169">Gesamtanzahl der Zeilen im Volltextkatalog, die einen bestimmten Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-169">Total number of rows in the full-text catalog that contain a given key.</span></span>  
  
 <span data-ttu-id="e9bbc-170">MaxOccurrence</span><span class="sxs-lookup"><span data-stu-id="e9bbc-170">MaxOccurrence</span></span>  
 <span data-ttu-id="e9bbc-171">Das größte in einem Volltextkatalog gespeicherte Vorkommen für eine bestimmte Eigenschaft in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-171">The largest occurrence stored in a full-text catalog for a given property in a row.</span></span>  
  
 <span data-ttu-id="e9bbc-172">MaxQueryRank</span><span class="sxs-lookup"><span data-stu-id="e9bbc-172">MaxQueryRank</span></span>  
 <span data-ttu-id="e9bbc-173">Der maximale Rang, 1000, der von der Volltextsuch-Engine zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-173">The maximum rank, 1000, returned by the Full-Text Engine.</span></span>  
  
  
### <a name="rank-computation-issues"></a><span data-ttu-id="e9bbc-174">Gesichtspunkte bei der Rangberechnung</span><span class="sxs-lookup"><span data-stu-id="e9bbc-174">Rank Computation Issues</span></span>  
 <span data-ttu-id="e9bbc-175">Der Vorgang der Rangberechnung hängt von mehreren Faktoren ab.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-175">The process of computing rank, depends on a number of factors.</span></span>  <span data-ttu-id="e9bbc-176">Die Wörtererkennung für unterschiedliche Sprachen zerlegt Text unterschiedlich in Wörter.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-176">Different language word breakers tokenize text differently.</span></span> <span data-ttu-id="e9bbc-177">So könnte z. B. die Zeichenfolge "dog-house" von einer Wörtererkennung in "dog" "house" und von einer anderen in "dog-house" zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-177">For example, the string "dog-house" could be broken into "dog" "house" by one word breaker and into "dog-house" by another.</span></span> <span data-ttu-id="e9bbc-178">Dies bedeutet, dass Vergleiche und Rangfolgenberechnung je nach der angegebenen Sprache unterschiedliche Ergebnisse liefern, da nicht nur die Wörter unterschiedlich sind, sondern auch die Dokumentlänge.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-178">This means that matching and ranking will vary based on the language specified, because not only are the words different, but so is the document length.</span></span> <span data-ttu-id="e9bbc-179">Die unterschiedliche Dokumentlänge kann sich auf die Rangfolgenberechnung für alle Abfragen auswirken.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-179">The document length difference can affect ranking for all queries.</span></span>  
  
 <span data-ttu-id="e9bbc-180">Statistiken wie `IndexRowCount` können stark variieren.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-180">Statistics such as `IndexRowCount` can vary widely.</span></span> <span data-ttu-id="e9bbc-181">Hat z. B. ein Katalog 2 Milliarden Zeilen im Masterindex, wird ein einzelnes neues Dokument in einen im Arbeitsspeicher befindlichen Zwischenindex indiziert, und die Ränge für das Dokument, die auf der Anzahl der Dokumente im Index im Arbeitsspeicher basieren, können im Vergleich zu den Rängen für Dokumente aus dem Masterindex verfälscht sein.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-181">For example, if a catalog has 2 billion rows in the master index, then one new document is indexed into an in-memory intermediate index, and ranks for that document based on the number of documents in the in-memory index could be skewed compared with ranks for documents from the master index.</span></span> <span data-ttu-id="e9bbc-182">Daher wird empfohlen, dass die Indizes nach jeder Auffüllung, durch die viele Zeilen indiziert oder neu indiziert werden, in einen Masterindex zusammengeführt werden, mithilfe der ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-182">For this reason, it is recommended that after any population that results in large number of rows being indexed or re-indexed the indexes be merged into a master index using the ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e9bbc-183">Entsprechend bestimmten Parametern, wie Anzahl und Größe der Zwischenindizes, werden die Indizes auch automatisch von der Volltextsuch-Engine zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-183">The Full-Text Engine will also automatically merge the indexes based on parameters such as the number and size of intermediate indexes.</span></span>  
  
 <span data-ttu-id="e9bbc-184">`MaxOccurrence`-Werte werden in den Bereich 1 bis 32 normalisiert.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-184">`MaxOccurrence` values are normalized into 1 of 32 ranges.</span></span> <span data-ttu-id="e9bbc-185">Das heißt, dass z. B. ein 50 Wörter langes Dokument genau so behandelt wird wie ein 100 Wörter langes.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-185">This means, for example, that a document 50 words long is treated the same as a document 100 words long.</span></span> <span data-ttu-id="e9bbc-186">Die zur Normalisierung verwendete Tabelle ist unten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-186">Below is the table used for normalization.</span></span> <span data-ttu-id="e9bbc-187">Da die Dokument Längen im Bereich zwischen den benachbarten Tabellenwerten 32 und 128 liegen, werden Sie effektiv mit der gleichen Länge behandelt, 128 (32 < `docLength` <= 128).</span><span class="sxs-lookup"><span data-stu-id="e9bbc-187">Because the document lengths are in the range between adjacent table values 32 and 128, they are effectively treated as having the same length, 128 (32 < `docLength` <= 128).</span></span>  
  
```  
{ 16, 32, 128, 256, 512, 725, 1024, 1450, 2048, 2896, 4096, 5792, 8192, 11585,   
16384, 23170, 28000, 32768, 39554, 46340, 55938, 65536, 92681, 131072, 185363,   
262144, 370727, 524288, 741455, 1048576, 2097152, 4194304 };  
  
```  
  
  
### <a name="ranking-of-containstable"></a><span data-ttu-id="e9bbc-188">Rangfolge von CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="e9bbc-188">Ranking of CONTAINSTABLE</span></span>  
 <span data-ttu-id="e9bbc-189">Beim Generieren der Rangfolge für[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) wird der folgende Algorithmus verwendet:</span><span class="sxs-lookup"><span data-stu-id="e9bbc-189">[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) ranking uses the following algorithm:</span></span>  
  
```  
StatisticalWeight = Log2( ( 2 + IndexedRowCount ) / KeyRowCount )  
Rank = min( MaxQueryRank, HitCount * 16 * StatisticalWeight / MaxOccurrence )  
```  
  
 <span data-ttu-id="e9bbc-190">Der Rang von Übereinstimmungen in Ausdrücken wird genau so bestimmt wie einzelne Schlüssel, außer dass `KeyRowCount` (die Anzahl von Zeilen, die den Ausdruck enthalten) geschätzt wird, und somit ungenau und höher als die tatsächliche Anzahl ausfallen kann.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-190">Phrase matches are ranked just like individual keys except that `KeyRowCount` (the number of rows containing the phrase) is estimated and can be inaccurate and higher than the actual number.</span></span>  
  
 <span data-ttu-id="e9bbc-191">**Rangfolge von NEAR**</span><span class="sxs-lookup"><span data-stu-id="e9bbc-191">**Ranking of NEAR**</span></span>  
  
 <span data-ttu-id="e9bbc-192">CONTAINSTABLE unterstützt das Abfragen von zwei oder mehr Suchbegriffen mithilfe der NEAR-Option hinsichtlich ihrer Nähe zueinander.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-192">CONTAINSTABLE supports querying for two or more search terms in proximity to each other by using the NEAR option.</span></span> <span data-ttu-id="e9bbc-193">Der Rangwert der einzelnen zurückgegebenen Zeilen basiert auf mehreren Parametern.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-193">The rank value of each returned row is based on several parameters.</span></span> <span data-ttu-id="e9bbc-194">Ein Hauptrangfaktor ist die Gesamtzahl der Übereinstimmungen (oder *Treffer*) in Bezug auf die Länge des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-194">One major ranking factor is the total number of matches (or *hits*) relative to the length of the document.</span></span> <span data-ttu-id="e9bbc-195">Wenn beispielsweise ein Dokument mit 100 Wörtern und ein Dokument mit 900 Wörtern identische Übereinstimmungen enthalten, wird dem Dokument mit 100 Wörtern ein höherer Rangwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-195">Thus, for example, if a 100-word document and a 900-word document contain identical matches, the 100-word document is ranked higher.</span></span>  
  
 <span data-ttu-id="e9bbc-196">Die Gesamtlänge der einzelnen Treffer in einer Zeile trägt ebenfalls zum Rangwert der betreffenden Zeile bei, wobei die Entfernung zwischen dem ersten und dem letzten Suchbegriff des jeweiligen Treffers zugrunde gelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-196">The total length of each hit in a row will also contribute to the ranking of that row based on the distance between the first and last search terms of that hit.</span></span> <span data-ttu-id="e9bbc-197">Je kleiner die Entfernung, desto relevanter ist der Treffer für den Rangwert der Zeile.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-197">The smaller the distance, the more the hit contributes to the rank value of the row.</span></span> <span data-ttu-id="e9bbc-198">Wenn eine Volltextabfrage keine ganze Zahl angibt (z. B. die maximale Entfernung), weist ein Dokument, das nur Treffer enthält, deren Entfernungen weiter als 100 logische Begriffe auseinander liegen, einen Rang von 0 (null) auf.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-198">If a full-text query does not specify an integer as the maximum distance, a document that contains only hits whose distances are greater than 100 logical terms apart, will have a ranking of 0.</span></span>  
  
 <span data-ttu-id="e9bbc-199">**Rangfolge von ISABOUT**</span><span class="sxs-lookup"><span data-stu-id="e9bbc-199">**Ranking of ISABOUT**</span></span>  
  
 <span data-ttu-id="e9bbc-200">CONTAINSTABLE unterstützt das Abfragen von gewichteten Begriffen mit der ISABOUT-Option.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-200">CONTAINSTABLE supports querying for weighted terms by using the ISABOUT option.</span></span> <span data-ttu-id="e9bbc-201">ISABOUT ist eine Vektorraumabfrage in traditioneller Information Retrieval-Terminologie.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-201">ISABOUT is a vector-space query in traditional information retrieval terminology.</span></span> <span data-ttu-id="e9bbc-202">Der verwendete Standardalgorithmus zur Rangfolgenberechnung ist Jaccard, eine bekannte Formel.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-202">The default ranking algorithm used is Jaccard, a widely known formula.</span></span> <span data-ttu-id="e9bbc-203">Die Rangfolge wird für jeden Begriff in der Abfrage berechnet und anschließend wie nachstehend beschrieben kombiniert.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-203">The ranking is computed for each term in the query and then combined as described below.</span></span>  
  
```  
ContainsRank = same formula used for CONTAINSTABLE ranking of a single term (above).  
Weight = the weight specified in the query for each term. Default weight is 1.  
WeightedSum = ??[key=1 to n] ContainsRankKey * WeightKey  
Rank =  ( MaxQueryRank * WeightedSum ) / ( ( ??[key=1 to n] ContainsRankKey^2 )   
      + ( ??[key=1 to n] WeightKey^2 ) - ( WeightedSum ) )  
  
```  
  
  
### <a name="ranking-of-freetexttable"></a><span data-ttu-id="e9bbc-204">Rangfolge von FREETEXTTABLE</span><span class="sxs-lookup"><span data-stu-id="e9bbc-204">Ranking of FREETEXTTABLE</span></span>  
 <span data-ttu-id="e9bbc-205">Die Rangfolgenberechnung für[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) basiert auf der OKAPI BM25-Rangfolgenformel.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-205">[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) ranking is based on the OKAPI BM25 ranking formula.</span></span> <span data-ttu-id="e9bbc-206">Bei FREETEXTTABLE-Abfragen werden der Abfrage durch Wortformengenerierung Flexionsformen der ursprünglichen Abfragewörter hinzugefügt; diese Wörter werden als separate Wörter ohne besondere Beziehung zu den Wörtern behandelt, aus denen sie generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-206">FREETEXTTABLE queries will add words to the query via inflectional generation (inflected forms of the original query words); these words are treated as separate words with no special relationship to the words from which they were generated.</span></span> <span data-ttu-id="e9bbc-207">Aus der Thesaurus-Funktion generierte Synonyme werden als separate, gleich gewichtete Begriffe behandelt.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-207">Synonyms generated from the Thesaurus feature are treated as separate, equally weighted terms.</span></span> <span data-ttu-id="e9bbc-208">Jedes Wort in der Abfrage wird bei der Rangberechnung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="e9bbc-208">Each word in the query contributes to the rank.</span></span>  
  
```  
Rank = ??[Terms in Query] w ( ( ( k1 + 1 ) tf ) / ( K + tf ) ) * ( ( k3 + 1 ) qtf / ( k3 + qtf ) ) )  
Where:   
w is the Robertson-Sparck Jones weight.   
In simplified form, w is defined as:   
w = log10 ( ( ( r + 0.5 ) * ( N - R + r + 0.5 ) ) / ( ( R - r + 0.5 ) * ( n - r + 0.5 ) )  
N is the number of indexed rows for the property being queried.   
n is the number of rows containing the word.   
K is ( k1 * ( ( 1 - b ) + ( b * dl / avdl ) ) ).   
dl is the property length, in word occurrences.   
avdl is the average length of the property being queried, in word occurrences.   
k1, b, and k3 are the constants 1.2, 0.75, and 8.0, respectively.   
tf is the frequency of the word in the queried property in a specific row.   
qtf is the frequency of the term in the query.   
```  
  
  
## <a name="see-also"></a><span data-ttu-id="e9bbc-209">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9bbc-209">See Also</span></span>  
 [<span data-ttu-id="e9bbc-210">Abfragen mit Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="e9bbc-210">Query with Full-Text Search</span></span>](query-with-full-text-search.md)  
  
  
