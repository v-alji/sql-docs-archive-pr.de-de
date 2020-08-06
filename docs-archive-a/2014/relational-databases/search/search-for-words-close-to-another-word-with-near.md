---
title: Suchen von Wörtern in der Nähe eines anderen Worts mit NEAR | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- word searches [full-text search]
- NEAR option [full-text search]
- phrase searches [full-text search]
- proximity searches [full-text search]
- full-text search [SQL Server], proximity searches
- full-text queries [SQL Server], proximity
- queries [full-text search], proximity
ms.assetid: 87520646-4865-49ae-8790-f766b80a41f3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c2d187ea3ed951ac6f17eb4babc5f4f77451d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719819"
---
# <a name="search-for-words-close-to-another-word-with-near"></a><span data-ttu-id="c8844-102">Suchen von Wörtern in der Nähe eines anderen Worts mit NEAR</span><span class="sxs-lookup"><span data-stu-id="c8844-102">Search for Words Close to Another Word with NEAR</span></span>
  <span data-ttu-id="c8844-103">Sie können in einem [CONTAINS](/sql/t-sql/queries/contains-transact-sql) -Prädikat oder in einer [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) -Funktion mithilfe eines NEAR-Begriffs nach Wörtern oder Wendungen suchen, die nahe beieinander liegen.</span><span class="sxs-lookup"><span data-stu-id="c8844-103">You can use a proximity term (NEAR) in a [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate or [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) function to search for words or phrases near one another.</span></span> <span data-ttu-id="c8844-104">Sie können auch die maximale Anzahl von nicht als Suchkriterium festgelegten Begriffen angeben, die zwischen dem ersten und dem letzten Suchbegriff liegen.</span><span class="sxs-lookup"><span data-stu-id="c8844-104">You can also specify the maximum number of non-search terms that separate the first and last search terms.</span></span> <span data-ttu-id="c8844-105">Außerdem können Sie in einer beliebigen Reihenfolge oder in der angegebenen Reihenfolge nach Wörtern oder Ausdrücken suchen.</span><span class="sxs-lookup"><span data-stu-id="c8844-105">In addition, you can search for words or phrases in any order, or you can search for words and phrases in the order in which you specify them.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="c8844-106">unterstützt sowohl den früheren [generischen NEAR-Begriff](#Generic_NEAR), der nun veraltet ist, als auch den [benutzerdefinierten NEAR-Begriff](#Custom_NEAR), der in neu ist [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8844-106">supports both the earlier [generic proximity term](#Generic_NEAR), which is now deprecated, and the [custom proximity term](#Custom_NEAR), which is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
##  <a name="the-custom-proximity-term"></a><a name="Custom_NEAR"></a><span data-ttu-id="c8844-107">Der benutzerdefinierte NEAR-Begriff</span><span class="sxs-lookup"><span data-stu-id="c8844-107">The Custom Proximity Term</span></span>  
 <span data-ttu-id="c8844-108">Mit dem benutzerdefinierten NEAR-Begriff werden die folgenden neuen Funktionen eingeführt:</span><span class="sxs-lookup"><span data-stu-id="c8844-108">The custom proximity term introduces the following new capabilities:</span></span>  
  
-   <span data-ttu-id="c8844-109">Sie können die maximale Anzahl von nicht als Suchkriterium angegebenen Begriffen oder den *maximalen Abstand*zwischen dem ersten Suchbegriff und dem letzten Suchbegriff angeben, bei dem eine Übereinstimmung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c8844-109">You can specify the maximum number of non-search terms, or *maximum distance*, that separates the first and last search terms in order to constitute a match.</span></span>  
  
-   <span data-ttu-id="c8844-110">Wenn Sie die maximale Anzahl von Begriffen angeben, können Sie auch angeben, dass Übereinstimmungen die Suchbegriffe in der angegebenen Reihenfolge enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="c8844-110">If you specify the maximum number of terms, you can also specify that matches must contain the search terms in the specified order.</span></span>  
  
 <span data-ttu-id="c8844-111">Um als Übereinstimmung zu gelten, muss eine Textzeichenfolge folgende Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="c8844-111">To qualify as a match, a string of text must:</span></span>  
  
-   <span data-ttu-id="c8844-112">Sie muss mit einem der angegebenen Suchbegriffe beginnen und mit einem der anderen angegebenen Suchbegriffe enden.</span><span class="sxs-lookup"><span data-stu-id="c8844-112">Start with one of the specified search terms and end with the one of the other specified search terms.</span></span>  
  
-   <span data-ttu-id="c8844-113">Sie muss alle angegebenen Suchbegriffe enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8844-113">Contain all of the specified search terms.</span></span>  
  
-   <span data-ttu-id="c8844-114">Die Anzahl der nicht als Suchkriterien angegebenen Begriffe (einschließlich von Stoppwörtern), die zwischen dem ersten Suchbegriff und dem letzten Suchbegriff liegen, muss kleiner oder gleich dem ggf. festgelegten maximalen Abstand sein.</span><span class="sxs-lookup"><span data-stu-id="c8844-114">The number of non-search terms, including stopwords, that occur between the first and last search terms must be less than or equal to the maximum distance, if specified.</span></span>  
  
 <span data-ttu-id="c8844-115">Die grundlegende Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="c8844-115">The basic syntax is:</span></span>  
  
 <span data-ttu-id="c8844-116">NEAR (</span><span class="sxs-lookup"><span data-stu-id="c8844-116">NEAR (</span></span>  
  
 <span data-ttu-id="c8844-117">{</span><span class="sxs-lookup"><span data-stu-id="c8844-117">{</span></span>  
  
 <span data-ttu-id="c8844-118">*SEARCH_TERM* [,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="c8844-118">*search_term* [ ,...*n* ]</span></span>  
  
 |  
  
 <span data-ttu-id="c8844-119">(*SEARCH_TERM* [,... *n* ]) [, <maximum_distance> [, <match_order>]]</span><span class="sxs-lookup"><span data-stu-id="c8844-119">(*search_term* [ ,...*n* ] ) [, <maximum_distance> [, <match_order> ] ]</span></span>  
  
 <span data-ttu-id="c8844-120">}</span><span class="sxs-lookup"><span data-stu-id="c8844-120">}</span></span>  
  
 <span data-ttu-id="c8844-121">)</span><span class="sxs-lookup"><span data-stu-id="c8844-121">)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8844-122">Weitere Informationen zur <custom_proximity_term>-Syntax finden Sie unter [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8844-122">For more information about the <custom_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="c8844-123">Sie können z. B. innerhalb der zwei Begriffe von 'Smith' wie folgt nach 'John' suchen:</span><span class="sxs-lookup"><span data-stu-id="c8844-123">For example, you could search for 'John' within two terms of 'Smith', as follows:</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((John, Smith), 2)')  
```  
  
 <span data-ttu-id="c8844-124">Zwei Beispiele für Übereinstimmungszeichenfolgen sind "`John Jacob Smith`" und "`Smith, John`."</span><span class="sxs-lookup"><span data-stu-id="c8844-124">Some examples of strings that match are "`John Jacob Smith`" and "`Smith, John`".</span></span> <span data-ttu-id="c8844-125">Die Zeichenfolge "`John Jones knows Fred Smith`" enthält drei dazwischenliegende Nicht-Suchbegriffe, daher handelt es sich um keine Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="c8844-125">The string "`John Jones knows Fred Smith`" contains three intervening non-search terms, so it is not a match.</span></span>  
  
 <span data-ttu-id="c8844-126">Um festzulegen, dass die Begriffe in der angegebenen Reihenfolge gefunden werden müssen, müssen Sie den NEAR-Begriff im Beispiel in `NEAR((John, Smith),2, TRUE).` ändern. Damit wird in zwei Begriffen von "`John`" nach "`Smith`" gesucht, jedoch nur, wenn "`John`" vor "`Smith`" enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c8844-126">To require that the terms be found in the specified order, you would change the example proximity term to `NEAR((John, Smith),2, TRUE).` This searches for "`John`" within two terms of "`Smith`" but only when "`John`" precedes "`Smith`".</span></span> <span data-ttu-id="c8844-127">In einer von links nach rechts geschriebenen Sprache wie Englisch ist "`John Jacob Smith`" ein Beispiel für eine übereinstimmende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c8844-127">In a language that reads from left to right, such as English, an example of a string that matches is "`John Jacob Smith`".</span></span>  
  
 <span data-ttu-id="c8844-128">Beachten Sie, dass die Volltext-Engine bei von rechts nach links geschriebenen Sprachen (z. B. Arabisch oder Hebräisch) die angegebenen Begriffe in umgekehrter Reihenfolge anwendet.</span><span class="sxs-lookup"><span data-stu-id="c8844-128">Note that for a language that reads from right to left, such as Arabic or Hebrew, the Full-Text Engine applies the specified terms in reverse order.</span></span> <span data-ttu-id="c8844-129">Auch der Objekt-Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] kehrt die Anzeigereihenfolge von angegebenen Wörtern in Sprachen mit einer Leserichtung von rechts nach links automatisch um.</span><span class="sxs-lookup"><span data-stu-id="c8844-129">Also, Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] automatically reverses the display order of words specified in right-to-left languages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8844-130">Weitere Informationen finden Sie unter[Weitere Überlegungen zu NEAR-Suchen](#Additional_Considerations)an späterer Stelle in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="c8844-130">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="how-maximum-distance-is-measured"></a><span data-ttu-id="c8844-131">Messen des maximalen Abstands</span><span class="sxs-lookup"><span data-stu-id="c8844-131">How Maximum Distance Is Measured</span></span>  
 <span data-ttu-id="c8844-132">Ein bestimmter maximaler Abstand (z. B. 10 oder 25) gibt an, wie viele Nicht-Suchbegriffe (einschließlich von Stoppwörtern) in einer angegebenen Zeichenfolge zwischen dem Suchbegriff und dem letzten Suchbegriff auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c8844-132">A specific maximum distance, such as 10 or 25, determines how many non-search terms, including stopwords, can occur between the first and last search terms in a given string.</span></span> <span data-ttu-id="c8844-133">`NEAR((dogs, cats, "hunting mice"), 3)` gibt z. B. die folgende Zeile zurück, in der die Gesamtzahl der Nicht-Suchbegriffe gleich 3 ist ("`enjoy`", "`but`" und "`avoid`"):</span><span class="sxs-lookup"><span data-stu-id="c8844-133">For example, `NEAR((dogs, cats, "hunting mice"), 3)` would return the following row, in which the total number of non-search terms is three ("`enjoy`", "`but`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="c8844-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="c8844-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span></span>  
  
 <span data-ttu-id="c8844-135">Derselbe NEAR-Begriff würde nicht die folgende Zeile zurückgeben, da der maximale Abstand durch die vier Nicht-Suchbegriffe ("`enjoy`", "`but`", "`usually`" und "`avoid`") überschritten wird:</span><span class="sxs-lookup"><span data-stu-id="c8844-135">The same proximity term would not return the following row, because the maximum distance is exceeded by the four non-search terms ("`enjoy`", "`but`", "`usually`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="c8844-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="c8844-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span></span>  
  
### <a name="combining-a-custom-proximity-term-with-other-terms"></a><span data-ttu-id="c8844-137">Kombinieren eines benutzerdefinierten NEAR-Begriffs mit anderen Begriffen</span><span class="sxs-lookup"><span data-stu-id="c8844-137">Combining a Custom Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="c8844-138">Sie können einen benutzerdefinierten NEAR-Begriff mit einigen anderen Begriffen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="c8844-138">You can combine a custom proximity term with some other terms.</span></span> <span data-ttu-id="c8844-139">Sie können einen benutzerdefinierten NEAR-Begriff mit AND (&), OR (|) oder AND NOT (&!) mit einem anderen benutzerdefinierten NEAR-Begriff, einem einfachen Begriff oder einem Präfixbegriff kombinieren.</span><span class="sxs-lookup"><span data-stu-id="c8844-139">You can use AND (&), OR (|), or AND NOT (&!) to combine a custom proximity term with another custom proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="c8844-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8844-140">For example:</span></span>  
  
-   <span data-ttu-id="c8844-141">CONTAINS('NEAR((*Begriff1*,*Begriff2*),5) AND *Begriff3*')</span><span class="sxs-lookup"><span data-stu-id="c8844-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span></span>  
  
-   <span data-ttu-id="c8844-142">CONTAINS('NEAR((*Begriff1*,*Begriff2*),5) OR *Begriff3*')</span><span class="sxs-lookup"><span data-stu-id="c8844-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span></span>  
  
-   <span data-ttu-id="c8844-143">CONTAINS('NEAR((*Begriff1*,*Begriff2*),5) AND NOT *Begriff3*')</span><span class="sxs-lookup"><span data-stu-id="c8844-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span></span>  
  
-   <span data-ttu-id="c8844-144">CONTAINS('NEAR((*Begriff1*,*Begriff2*),5) AND NEAR((*Begriff3*,*Begriff4*),2)')</span><span class="sxs-lookup"><span data-stu-id="c8844-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span></span>  
  
-   <span data-ttu-id="c8844-145">CONTAINS('NEAR((*Begriff1*,*Begriff2*),5) OR NEAR((*Begriff3*,*Begriff4*),2, TRUE)')</span><span class="sxs-lookup"><span data-stu-id="c8844-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span></span>  
  
 <span data-ttu-id="c8844-146">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="c8844-146">For example,</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((term1, term2), 5, TRUE) AND term3')  
```  
  
 <span data-ttu-id="c8844-147">Sie können einen benutzerdefinierten NEAR-Begriff nicht mit einem generischen NEAR-Begriff (*Begriff1* near *Begriff2*), einem Generierungs Begriff (ISABOUT...) oder einem gewichteten Begriff (FORMSOF...) kombinieren.</span><span class="sxs-lookup"><span data-stu-id="c8844-147">You cannot combine a custom proximity term with a generic proximity term (*term1* NEAR *term2*), a generation term (ISABOUT ...), or a weighted term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-custom-proximity-term"></a><span data-ttu-id="c8844-148">Beispiel: Verwenden des benutzerdefinierten NEAR-Begriffs</span><span class="sxs-lookup"><span data-stu-id="c8844-148">Example: Using the Custom Proximity Term</span></span>  
 <span data-ttu-id="c8844-149">Im folgenden Beispiel wird die Tabelle `Production.Document` der Beispieldatenbank `AdventureWorks2012` nach allen Dokumentzusammenfassungen durchsucht, bei denen das Wort "reflector" im selben Dokument wie das Wort "bracket" enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c8844-149">The following example searches the `Production.Document` table of the `AdventureWorks2012` sample database for all document summaries that contain the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  

  
##  <a name="additional-considerations-for-proximity-searches"></a><a name="Additional_Considerations"></a><span data-ttu-id="c8844-150">Weitere Überlegungen zu near-suchen</span><span class="sxs-lookup"><span data-stu-id="c8844-150">Additional Considerations for Proximity Searches</span></span>  
 <span data-ttu-id="c8844-151">In diesem Abschnitt werden Aspekte erläutert, die sich sowohl auf generische als auch auf benutzerdefinierte NEAR-Suchen auswirken:</span><span class="sxs-lookup"><span data-stu-id="c8844-151">This section discusses consideration that affect both generic and custom proximity searches:</span></span>  
  
-   <span data-ttu-id="c8844-152">Einander überschneidende Vorkommen von Suchbegriffen</span><span class="sxs-lookup"><span data-stu-id="c8844-152">Overlapping occurrences of search terms</span></span>  
  
     <span data-ttu-id="c8844-153">In allen NEAR-Suchen wird ausschließlich nach einander nicht überschneidenden Vorkommen gesucht.</span><span class="sxs-lookup"><span data-stu-id="c8844-153">All proximity searches always look for only non-overlapping occurrences.</span></span> <span data-ttu-id="c8844-154">Einander überschneidende Vorkommen von Suchbegriffen gelten nie als Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="c8844-154">Overlapping occurrences of search terms never qualify as matches.</span></span> <span data-ttu-id="c8844-155">Betrachten Sie z. B. den folgenden NEAR-Begriff, der nach "`A`" und "`AA`" sucht, wobei diese Reihenfolge mit einem maximalen Abstand von zwei Begriffen gilt:</span><span class="sxs-lookup"><span data-stu-id="c8844-155">For example, consider the following proximity term, which searches "`A`" and "`AA`" in this order with a maximum distance of two terms:</span></span>  
  
    ```  
    CONTAINS(column_name, 'NEAR((A,AA),2, TRUE')  
    ```  
  
     <span data-ttu-id="c8844-156">Die möglichen Übereinstimmungen sind "`AAA`", "`A.AA`" und "`A..AA`".</span><span class="sxs-lookup"><span data-stu-id="c8844-156">The possible matches are as "`AAA`", "`A.AA`", and "`A..AA`".</span></span> <span data-ttu-id="c8844-157">Zeilen, die nur "`AA`" enthalten, sind keine Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="c8844-157">Rows containing just "`AA`" would not match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8844-158">Sie können Begriffe angeben, die einander überschneiden, z. B. `NEAR("mountain bike", "bike trails")` oder `(NEAR(comfort*, comfortable), 5)`.</span><span class="sxs-lookup"><span data-stu-id="c8844-158">You can specify terms that overlap, for example, `NEAR("mountain bike", "bike trails")` or `(NEAR(comfort*, comfortable), 5)`.</span></span> <span data-ttu-id="c8844-159">Durch das Angeben einander überschneidender Begriffe wird die Abfrage komplexer, da die möglichen Übereinstimmungspermutationen vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="c8844-159">Specifying a overlapping terms increases the complexity of the query by increasing the possible match permutations.</span></span> <span data-ttu-id="c8844-160">Wenn Sie eine große Anzahl von einander überschneidenden Begriffen angeben, verfügt die Abfrage möglicherweise nicht über ausreichende Ressourcen, und sie schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="c8844-160">If you specify a large number of such overlapping terms, the query can run out of resources and fail.</span></span> <span data-ttu-id="c8844-161">Vereinfachen Sie in einem solchen Fall die Abfrage, und führen Sie sie noch einmal aus.</span><span class="sxs-lookup"><span data-stu-id="c8844-161">If this occurs, simplify the query and try again.</span></span>  
  
-   <span data-ttu-id="c8844-162">Sowohl das generische NEAR als auch das benutzerdefinierte NEAR (unabhängig von der Angabe eines maximalen Abstands) geben den logischen Abstand zwischen Begriffen und nicht deren absoluten Abstand an.</span><span class="sxs-lookup"><span data-stu-id="c8844-162">Both generic NEAR and custom NEAR (regardless of whether a maximum distance is specified) indicate the logical distance between terms, rather than the absolute distance between them.</span></span> <span data-ttu-id="c8844-163">Begriffe, die sich innerhalb eines Absatzes innerhalb verschiedener Ausdrücke oder Sätze befinden, werden beispielsweise als weiter voneinander entfernt behandelt als Begriffe im gleichen Ausdruck oder im gleichen Satz, und zwar unabhängig von ihrer tatsächlichen Nähe und unter der Annahme, dass sie weniger verwandt sind.</span><span class="sxs-lookup"><span data-stu-id="c8844-163">For example, terms within different phrases or sentences within a paragraph are treated as farther apart than terms in the same phrase or sentence, regardless of their actual proximity, on the assumption that they are less related.</span></span> <span data-ttu-id="c8844-164">Begriffe in anderen Absätzen werden entsprechend so behandelt, als wären sie noch weiter entfernt.</span><span class="sxs-lookup"><span data-stu-id="c8844-164">Likewise, terms in different paragraphs are treated as being even farther apart.</span></span> <span data-ttu-id="c8844-165">Wenn sich eine Übereinstimmung über das Ende eines Satzes, Absatzes oder Kapitels erstreckt, wird die Lücke, die zum Generieren der Rangfolge eines Dokuments verwendet wird, um 8, 128 bzw. 1024 vergrößert.</span><span class="sxs-lookup"><span data-stu-id="c8844-165">If a match spans the end of a sentence, paragraph, or chapter, the gap used for ranking a document is increased by 8, 128, or 1024, respectively.</span></span>  
  
-   <span data-ttu-id="c8844-166">Auswirkungen von NEAR-Begriffen auf das Generieren der Rangfolge durch die CONTAINSTABLE-Funktion</span><span class="sxs-lookup"><span data-stu-id="c8844-166">Impact of proximity terms on ranking by the CONTAINSTABLE function</span></span>  
  
     <span data-ttu-id="c8844-167">Wenn NEAR in der CONTAINSTABLE-Funktion verwendet wird, wirken sich die Anzahl der Treffer in einem Dokument relativ zu seiner Länge sowie der Abstand zwischen dem ersten und dem letzten Suchbegriff in den einzelnen Treffern auf die Rangfolge des jeweiligen Dokuments aus.</span><span class="sxs-lookup"><span data-stu-id="c8844-167">When NEAR is used in the CONTAINSTABLE function, the number of hits in a document relative to its length as well as the distance between the first and last search terms in each of the hits affects the ranking of each document.</span></span> <span data-ttu-id="c8844-168">Wenn für einen generischen NEAR-Begriff die gefundenen Suchbegriffe >50 logische Begriffe auseinander liegen, ist der für ein Dokument zurückgegebene Rang gleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="c8844-168">For a generic proximity term, if the matched search terms are >50 logical terms apart, the rank returned on a document is 0.</span></span> <span data-ttu-id="c8844-169">Wenn für einen benutzerdefinierten NEAR-Begriff keine ganze Zahl als maximaler Abstand angegeben ist, erhält ein Dokument, das nur Treffer mit einer Lücke >100 logische Begriffe aufweist, den Rang 0 (null).</span><span class="sxs-lookup"><span data-stu-id="c8844-169">For a custom proximity term that does not specify an integer as the maximum distance, a document that contains only hits whose gap is >100 logical terms will receive a ranking of 0.</span></span> <span data-ttu-id="c8844-170">Weitere Informationen zum Generieren der Rangfolge bei benutzerdefinierten NEAR-Suchen finden Sie unter [Einschränken von Suchergebnissen mit RANK](limit-search-results-with-rank.md).</span><span class="sxs-lookup"><span data-stu-id="c8844-170">For more information about ranking of custom proximity searches, see [Limit Search Results with RANK](limit-search-results-with-rank.md).</span></span>  
  
-   <span data-ttu-id="c8844-171">**Füllwörtertransformation** (Serveroption)</span><span class="sxs-lookup"><span data-stu-id="c8844-171">The **transform noise words** server option</span></span>  
  
     <span data-ttu-id="c8844-172">Der Wert von **Füllwörtertransformation** wirkt sich darauf aus, wie von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Stoppwörter behandelt werden, wenn diese in NEAR-Suchen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c8844-172">The value of **transform noise words** impacts how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats stopwords if they are specified in proximity searches.</span></span> <span data-ttu-id="c8844-173">Weitere Informationen finden Sie unter [Füllwörtertransformation (Serverkonfigurationsoption)](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="c8844-173">For more information, see [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span></span>  
  

  
##  <a name="the-deprecated-generic-proximity-term"></a><a name="Generic_NEAR"></a><span data-ttu-id="c8844-174">Der veraltete generische NEAR-Begriff</span><span class="sxs-lookup"><span data-stu-id="c8844-174">The Deprecated Generic Proximity Term</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<span data-ttu-id="c8844-175">Es wird empfohlen, den [benutzerdefinierten NEAR-Begriff](#Custom_NEAR)zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8844-175">We recommend that you use the [custom proximity term](#Custom_NEAR).</span></span>  
  
 <span data-ttu-id="c8844-176">Ein generischer NEAR-Begriff gibt an, dass die angegebenen Suchbegriffe alle in einem Dokument enthalten sein müssen, damit eine Übereinstimmung zurückgegeben wird, unabhängig von der Anzahl der nicht als Suchkriterium angegebenen Begriffe (der *Abstand*zwischen den Suchbegriffen).</span><span class="sxs-lookup"><span data-stu-id="c8844-176">A generic proximity term indicates that the specified search terms must all occur in a document for a match to be returned, regardless of the number of non-search terms (the *distance*) between the search terms.</span></span> <span data-ttu-id="c8844-177">Die grundlegende Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="c8844-177">The basic syntax is:</span></span>  
  
 <span data-ttu-id="c8844-178">{ *SEARCH_TERM* {near | ~} *SEARCH_TERM* } [ ,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="c8844-178">{ *search_term* { NEAR | ~ } *search_term* } [ ,...*n* ]</span></span>  
  
 <span data-ttu-id="c8844-179">In den folgenden Beispielen müssen die Wörter 'fox' und 'chicken' in beliebiger Reihenfolge enthalten sein, damit eine Übereinstimmung zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="c8844-179">For example, in the following examples, the words 'fox' and 'chicken' must both appear, in either order, to produce a match:</span></span>  
  
-   `CONTAINS(column_name, 'fox NEAR chicken')`  
  
-   `CONTAINSTABLE(table_name, column_name, 'fox ~ chicken')`  
  
> [!NOTE]  
>  <span data-ttu-id="c8844-180">Informationen zur <generic_proximity_term>-Syntax finden Sie unter [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8844-180">For information about the <generic_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="c8844-181">Weitere Informationen finden Sie unter[Weitere Überlegungen zu NEAR-Suchen](#Additional_Considerations)an späterer Stelle in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="c8844-181">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="combining-a-generic-proximity-term-with-other-terms"></a><span data-ttu-id="c8844-182">Kombinieren eines generischen NEAR-Begriffs mit anderen Begriffen</span><span class="sxs-lookup"><span data-stu-id="c8844-182">Combining a Generic Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="c8844-183">Sie können einen generischen NEAR-Begriff mit AND (&), OR (|) oder AND NOT (&!) mit einem anderen generischen NEAR-Begriff, einem einfachen Begriff oder einem Präfixbegriff kombinieren.</span><span class="sxs-lookup"><span data-stu-id="c8844-183">You can use AND (&), OR (|), or AND NOT (&!) to combine a generic proximity term with another generic proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="c8844-184">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8844-184">For example:</span></span>  
  
```  
CONTAINSTABLE (Production.ProductDescription,  
   Description,   
   '(light NEAR aluminum) OR  
   (lightweight NEAR aluminum)'  
)  
```  
  
 <span data-ttu-id="c8844-185">Es ist nicht möglich, einen generischen NEAR-Begriff mit einem benutzerdefinierten NEAR-Begriff zu kombinieren, z. b. `NEAR((term1,term2),5)` , einem gewichteten Begriff (ISABOUT...) oder einem Generations Begriff (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="c8844-185">You cannot combine a generic proximity term with a custom proximity term, such as `NEAR((term1,term2),5)`, a weighted term (ISABOUT ...), or a generational term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-generic-proximity-term"></a><span data-ttu-id="c8844-186">Beispiel: Verwenden des generischen NEAR-Begriffs</span><span class="sxs-lookup"><span data-stu-id="c8844-186">Example: Using the Generic Proximity Term</span></span>  
 <span data-ttu-id="c8844-187">Im folgenden Beispiel wird mit dem generischen NEAR-Begriff in dem Dokument nach dem Wort "reflector" gesucht, in dem auch das Wort "bracket" gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="c8844-187">The following example uses the generic proximity term to search for the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable INNER JOIN  
  CONTAINSTABLE(Production.Document, Document,  
  '(reflector NEAR bracket)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
 <span data-ttu-id="c8844-188">Beachten Sie, dass Sie die Reihenfolge der Begriffe in CONTAINSTABLE auch umdrehen können und dasselbe Ergebnis erhalten:</span><span class="sxs-lookup"><span data-stu-id="c8844-188">Notice that you can also reverse the terms in CONTAINSTABLE to get the same result:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(bracket NEAR reflector)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="c8844-189">Sie können das Tildezeichen (~) anstelle des NEAR-Schlüsselworts in der oben dargestellten Abfrage verwenden und erhalten dieselben Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="c8844-189">You can use the tilde character (~) in place of the NEAR keyword in the earlier query, and get the same results:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="c8844-190">Es können mehr als zwei Wörter oder Ausdrücke in den Suchbedingungen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c8844-190">More than two words or phrases can be specified in the search conditions.</span></span> <span data-ttu-id="c8844-191">Folgendes kann beispielsweise geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="c8844-191">For example, it is possible to write:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket ~ installation)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="c8844-192">Dies bedeutet, dass "reflector" im selben Dokument wie "bracket" enthalten sein muss und "bracket" im selben Dokument wie "installation".</span><span class="sxs-lookup"><span data-stu-id="c8844-192">This means that "reflector" must be in the same document as "bracket", and "bracket" must be in the same document as "installation".</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="c8844-193">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8844-193">See Also</span></span>  
 <span data-ttu-id="c8844-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8844-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="c8844-195">[Abfragen mit Volltextsuche](query-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="c8844-195">[Query with Full-Text Search](query-with-full-text-search.md) </span></span>  
 [<span data-ttu-id="c8844-196">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8844-196">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
