---
title: Suchen von ähnlichen und verwandten Dokumenten mit semantischer Suche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], document similarity queries
ms.assetid: 9f527883-031b-442f-8e95-24bc0151ecbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b11493b5b04fa9308e3afbe56176251225248338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622515"
---
# <a name="find-similar-and-related-documents-with-semantic-search"></a><span data-ttu-id="17a68-102">Suchen von ähnlichen und verwandten Dokumenten mit semantischer Suche</span><span class="sxs-lookup"><span data-stu-id="17a68-102">Find Similar and Related Documents with Semantic Search</span></span>
  <span data-ttu-id="17a68-103">Beschreibt, wie ähnliche oder verwandte Dokumente oder Textwerte sowie Informationen zur Ähnlichkeit oder Verwandtschaft über Spalten gesucht werden, die für die statistische semantische Indizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="17a68-103">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-similar-or-related-documents"></a><a name="BasicsQuerySimilar"></a><span data-ttu-id="17a68-104">Suchen von ähnlichen oder verwandten Dokumenten</span><span class="sxs-lookup"><span data-stu-id="17a68-104">Finding Similar or Related Documents</span></span>  
  
###  <a name="how-to-find-similar-or-related-documents-with-semanticsimilaritytable"></a><a name="HowToQuerySimilar"></a><span data-ttu-id="17a68-105">Gewusst wie: Suchen von ähnlichen oder verwandten Dokumenten mit semanticsimilaritytable</span><span class="sxs-lookup"><span data-stu-id="17a68-105">How To: Find Similar or Related Documents with SEMANTICSIMILARITYTABLE</span></span>  
 <span data-ttu-id="17a68-106">Fragen Sie zum Identifizieren ähnlicher oder verwandter Dokumente in einer bestimmten Spalte die Funktion [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="17a68-106">To identify similar or related documents in a specific column, query the function [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
 <span data-ttu-id="17a68-107">**SEMANTICSIMILARITYTABLE** gibt eine Tabelle mit keiner Zeile, einer Zeile oder mehreren Zeilen zurück, deren Inhalt in der angegebenen Spalte dem angegebenen Dokument semantisch ähnelt.</span><span class="sxs-lookup"><span data-stu-id="17a68-107">**SEMANTICSIMILARITYTABLE** returns a table of zero, one, or more rows whose content in the specified column is semantically similar to the specified document.</span></span> <span data-ttu-id="17a68-108">Auf diese Rowsetfunktion kann in der FROM-Klausel einer SELECT-Anweisung wie auf einen regulären Tabellennamen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="17a68-108">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="17a68-109">Ähnliche Dokumente können nicht über Spalten hinweg abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="17a68-109">You cannot query across columns for similar documents.</span></span> <span data-ttu-id="17a68-110">Die **SEMANTICSIMILARITYTABLE** -Funktion ruft nur Ergebnisse aus derselben Spalte wie die Quellspalte ab, die durch das **source_key** -Argument identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="17a68-110">The **SEMANTICSIMILARITYTABLE** function only retrieves results from the same column as the source column, which is identified by the **source_key** argument.</span></span>  
  
 <span data-ttu-id="17a68-111">Ausführliche Informationen zu den für die **SEMANTICSIMILARITYTABLE**-Funktion erforderlichen Parametern und zu der von ihr zurückgegebenen Ergebnistabelle finden Sie unter [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17a68-111">For detailed information about the parameters required by the **SEMANTICSIMILARITYTABLE** function, and about the table of results that it returns, see [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="17a68-112">Für die Spalten, auf die Sie abzielen, muss die Volltext- und die semantische Indizierung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="17a68-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-documents-that-are-similar-to-another-document"></a><a name="HowToIdentifySimilar"></a><span data-ttu-id="17a68-113">Beispiel: Suchen der wichtigsten Dokumente, die einem anderen Dokument ähneln</span><span class="sxs-lookup"><span data-stu-id="17a68-113">Example: Find the Top Documents That Are Similar to Another Document</span></span>  
 <span data-ttu-id="17a68-114">Im folgenden Beispiel werden die ersten 10 Kandidaten abgerufen, die dem von angegebenen Kandidaten *@CandidateID* aus der HumanResources. JobCandidate-Tabelle in der AdventureWorks2012-Beispieldatenbank ähneln.</span><span class="sxs-lookup"><span data-stu-id="17a68-114">The following example retrieves the top 10 candidates who are similar to the candidate specified by *@CandidateID* from the HumanResources.JobCandidate table in the AdventureWorks2012 sample database.</span></span>  
  
```scr  
SELECT TOP(10) KEY_TBL.matched_document_key AS Candidate_ID  
FROM SEMANTICSIMILARITYTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume,  
    @CandidateID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
##  <a name="finding-information-about-how-documents-are-similar-or-related"></a><a name="BasicsQuerySimilarity"></a><span data-ttu-id="17a68-115">Suchen von Informationen zur Art und Weise, wie Dokumente ähnlich oder verwandt sind</span><span class="sxs-lookup"><span data-stu-id="17a68-115">Finding Information about How Documents Are Similar or Related</span></span>  
  
###  <a name="how-to-find-information-about-how-documents-are-similar-or-related-with-semanticsimilaritydetailstable"></a><a name="HowToQuerySimilarity"></a><span data-ttu-id="17a68-116">Gewusst wie: Suchen nach Informationen zur Ähnlichkeit von Dokumenten mit semanticsimilaritydetailstable</span><span class="sxs-lookup"><span data-stu-id="17a68-116">How To: Find Information about How Documents Are Similar or Related with SEMANTICSIMILARITYDETAILSTABLE</span></span>  
 <span data-ttu-id="17a68-117">Um weitere Informationen zu den Schlüsselausdrücken abzurufen, die bewirken, dass Dokumente ähnlich oder verwandt sind, können Sie die Funktion [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) abfragen.</span><span class="sxs-lookup"><span data-stu-id="17a68-117">To get information about the key phrases that make documents similar or related, you can query the function [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
 <span data-ttu-id="17a68-118">**SEMANTICSIMILARITYDETAILSTABLE** gibt eine Tabelle mit keiner, einer oder mehreren Zeilen von Schlüsselausdrücken zurück, die in zwei Dokumenten (einem Quelldokument und einem verglichenen Dokument) vorkommen, deren Inhalt semantisch ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="17a68-118">**SEMANTICSIMILARITYDETAILSTABLE** returns a table of zero, one, or more rows of key phrases common across two documents (a source document and a matched document) whose content is semantically similar.</span></span> <span data-ttu-id="17a68-119">Auf diese Rowsetfunktion kann in der FROM-Klausel einer SELECT-Anweisung wie auf einen regulären Tabellennamen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="17a68-119">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="17a68-120">Ausführliche Informationen zu den für die **SEMANTICSIMILARITYDETAILSTABLE**-Funktion erforderlichen Parametern und zu der von ihr zurückgegebenen Ergebnistabelle finden Sie unter [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17a68-120">For detailed information about the parameters required by the **SEMANTICSIMILARITYDETAILSTABLE** function, and about the table of results that it returns, see [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="17a68-121">Für die Spalten, auf die Sie abzielen, muss die Volltext- und die semantische Indizierung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="17a68-121">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-key-phrases-that-are-similar-between-documents"></a><a name="HowToSimilarPhrases"></a><span data-ttu-id="17a68-122">Beispiel: Suchen der wichtigsten Schlüssel Ausdrücke, die zwischen Dokumenten ähnlich sind</span><span class="sxs-lookup"><span data-stu-id="17a68-122">Example: Find the Top Key Phrases That Are Similar between Documents</span></span>  
 <span data-ttu-id="17a68-123">Im folgenden Beispiel werden die fünf Schlüsselausdrücke mit der größten Ähnlichkeit zwischen den in der **HumanResources.JobCandidate** -Tabelle angegebenen Kandidaten der AdventureWorks2012-Beispieldatenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="17a68-123">The following example retrieves the 5 key phrases that have the highest similarity score between the specified candidates in **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span>  
  
```sql  
SELECT TOP(5) KEY_TBL.keyphrase, KEY_TBL.score  
FROM SEMANTICSIMILARITYDETAILSTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume, @CandidateID,  
    Resume, @MatchedID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
  
