---
title: Suchen von Schlüsselausdrücken in Dokumenten mit der semantischen Suche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], key phrase queries
ms.assetid: 6ee3676e-ed5d-43ec-aeca-1eed78967111
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8388fb704bf13f44d025e6e32a1450d537f61832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697863"
---
# <a name="find-key-phrases-in-documents-with-semantic-search"></a><span data-ttu-id="01483-102">Suchen von Schlüsselausdrücken in Dokumenten mit der semantischen Suche</span><span class="sxs-lookup"><span data-stu-id="01483-102">Find Key Phrases in Documents with Semantic Search</span></span>
  <span data-ttu-id="01483-103">Beschreibt, wie Schlüsselausdrücke in Dokumenten oder Textspalten gesucht werden, die für die statistische semantische Indizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="01483-103">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-key-phrases-in-documents"></a><a name="BasicsQueryKey"></a><span data-ttu-id="01483-104">Suchen von Schlüssel Ausdrücken in Dokumenten</span><span class="sxs-lookup"><span data-stu-id="01483-104">Finding Key Phrases in Documents</span></span>  
  
###  <a name="how-to-find-the-key-phrases-in-documents-with-semantickeyphrasetable"></a><a name="howtofind"></a><span data-ttu-id="01483-105">Gewusst wie: Suchen der Schlüssel Ausdrücke in Dokumenten mit semantickeyphraabtable</span><span class="sxs-lookup"><span data-stu-id="01483-105">How to: Find the Key Phrases in Documents with SEMANTICKEYPHRASETABLE</span></span>  
 <span data-ttu-id="01483-106">Um die Schlüsselausdrücke in bestimmten Dokumenten bzw. Dokumente zu identifizieren, die bestimmte Schlüsselausdrücke enthalten, fragen Sie die Funktion [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="01483-106">To identify the key phrases in specific documents, or to identify documents that contain specific key phrases, query the function [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
 <span data-ttu-id="01483-107">SEMANTICKEYPHRASETABLE gibt eine Tabelle mit keiner, einer oder mehreren Zeilen für die Schlüsselausdrücke zurück, die in der angegebenen Tabelle Spalten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="01483-107">SEMANTICKEYPHRASETABLE returns a table with zero, one, or more rows for those key phrases associated with columns in the specified table.</span></span> <span data-ttu-id="01483-108">Auf diese Rowsetfunktion kann in der FROM-Klausel einer SELECT-Anweisung so verwiesen werden, als handelte es sich dabei um einen regulären Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="01483-108">This rowset function can be referenced in the FROM clause of a SELECT statement as if it were a regular table name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01483-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]werden nur einzelne Wörter für die semantische Suche in den Index aufgenommen. Multiwort-Ausdrücke (ngrams) werden nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="01483-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], only single words are indexed for semantic search; multi-word phrases (ngrams) are not indexed.</span></span> <span data-ttu-id="01483-110">Auch werden verschiedene Formen des gleichen Wortes getrennt indiziert. Beispielsweise werden "Agent" und "Agents" getrennt indiziert.</span><span class="sxs-lookup"><span data-stu-id="01483-110">Also, various forms of the same word are indexed separately; for example, "computer" and "computers" are indexed separately.</span></span>  
  
 <span data-ttu-id="01483-111">Ausführliche Informationen zu den für die SEMANTICKEYPHRASETABLE-Funktion erforderlichen Parametern und zu der von ihr zurückgegebenen Ergebnistabelle finden Sie unter [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="01483-111">For detailed information about the parameters required by the SEMANTICKEYPHRASETABLE function, and about the table of results that it returns, see [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="01483-112">Für die Spalten, auf die Sie abzielen, muss die Volltext- und die semantische Indizierung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="01483-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a><span data-ttu-id="01483-113">Beispiel 1: Suchen der wichtigsten Schlüssel Ausdrücke in einem bestimmten Dokument</span><span class="sxs-lookup"><span data-stu-id="01483-113">Example 1: Find the Top Key Phrases in a Specific Document</span></span>  
 <span data-ttu-id="01483-114">Im folgenden Beispiel werden die obersten 10 Schlüsselausdrücke aus dem von der @DocumentId-Variable in der Spalte "Dokument" der Production.Document-Tabelle der AdventureWorks-Beispieldatenbank angegebenen Dokument abgerufen.</span><span class="sxs-lookup"><span data-stu-id="01483-114">The following example retrieves the top 10 key phrases from the document specified by the @DocumentId variable in the Document column of the Production.Document table of the AdventureWorks sample database.</span></span> <span data-ttu-id="01483-115">Die @DocumentId-Variable stellt einen Wert aus der Schlüsselspalte des Volltextindexes dar.</span><span class="sxs-lookup"><span data-stu-id="01483-115">The @DocumentId variable represents a value from the key column of the full-text index.</span></span>  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
GO  
```  
  
 <span data-ttu-id="01483-116">Die **SEMANTICKEYPHRASETABLE** -Funktion ruft diese Ergebnisse effizient mithilfe eines Indexsuchvorgangs anstelle eines Tabellenscans ab.</span><span class="sxs-lookup"><span data-stu-id="01483-116">The **SEMANTICKEYPHRASETABLE** function retrieves these results efficiently by using an index seek instead of a table scan.</span></span>  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a><span data-ttu-id="01483-117">Beispiel 2: Suchen der wichtigsten Dokumente, die einen bestimmten Schlüssel Ausdruck enthalten</span><span class="sxs-lookup"><span data-stu-id="01483-117">Example 2: Find the Top Documents that Contain a Specific Key Phrase</span></span>  
 <span data-ttu-id="01483-118">Im folgenden Beispiel werden die obersten 25 Dokumente mit dem Schlüsselausdruck „Bracket“ in der Spalte „Document“ der Production.Document-Tabelle der AdventureWorks-Beispieldatenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="01483-118">The following example retrieves the top 25 documents that contain the key phrase "Bracket" from the Document column of the Production.Document table of the AdventureWorks sample database.</span></span>  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
GO  
```  
  
  
