---
title: Verwenden der Volltextsuche mit XML-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml columns [full-text search]
- indexes [full-text search]
ms.assetid: 8096cfc6-1836-4ed5-a769-a5d63b137171
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b6b23933fde6a09d043c7055b0daa7c07035cdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697586"
---
# <a name="use-full-text-search-with-xml-columns"></a><span data-ttu-id="8a761-102">Verwenden der Volltextsuche mit XML-Spalten</span><span class="sxs-lookup"><span data-stu-id="8a761-102">Use Full-Text Search with XML Columns</span></span>
  <span data-ttu-id="8a761-103">Sie können einen Volltextindex für XML-Spalten erstellen, bei dem der Inhalt der XML-Werte indiziert, das XML-Markup jedoch ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="8a761-103">You can create a full-text index on XML columns that indexes the content of the XML values, but ignores the XML markup.</span></span> <span data-ttu-id="8a761-104">Elementtags werden als Tokenbegrenzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a761-104">Element tags are used as token boundaries.</span></span> <span data-ttu-id="8a761-105">Folgende Elemente werden indiziert:</span><span class="sxs-lookup"><span data-stu-id="8a761-105">The following items are indexed:</span></span>  
  
-   <span data-ttu-id="8a761-106">Der Inhalt von XML-Elementen.</span><span class="sxs-lookup"><span data-stu-id="8a761-106">The content of XML elements.</span></span>  
  
-   <span data-ttu-id="8a761-107">Nur der Inhalt von XML-Attributen des Elements der obersten Ebene, außer wenn diese Werte numerische Werte sind.</span><span class="sxs-lookup"><span data-stu-id="8a761-107">The content of XML attributes of the top-level element only, unless those values are numeric values.</span></span>  
  
 <span data-ttu-id="8a761-108">Gegebenenfalls können Sie die Volltextsuche mit dem XML-Index auf folgende Weise kombinieren:</span><span class="sxs-lookup"><span data-stu-id="8a761-108">When possible, you can combine full-text search with XML index in the following way:</span></span>  
  
1.  <span data-ttu-id="8a761-109">Filtern Sie zuerst die XML-Werte von Interesse mithilfe der SQL-Volltextsuche.</span><span class="sxs-lookup"><span data-stu-id="8a761-109">First, filter the XML values of interest by using SQL full-text search.</span></span>  
  
2.  <span data-ttu-id="8a761-110">Fragen Sie als Nächstes solche XML-Werte ab, die den XML-Index für die XML-Spalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a761-110">Next, query those XML values that use XML index on the XML column.</span></span>  
  
## <a name="example-combining-full-text-search-with-xml-querying"></a><span data-ttu-id="8a761-111">Beispiel: Kombinieren der Volltextsuche mit XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="8a761-111">Example: Combining Full-text Search with XML Querying</span></span>  
 <span data-ttu-id="8a761-112">Nachdem der Volltextindex für die XML-Spalte erstellt wurde, überprüft die folgende Abfrage, ob ein XML-Wert das Wort "custom" im Titel eines Buchs enthält:</span><span class="sxs-lookup"><span data-stu-id="8a761-112">After the full-text index has been created on the XML column, the following query checks that an XML value contains the word "custom" in the title of a book:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'custom')   
AND    xCol.exist('/book/title/text()[contains(.,"custom")]') =1  
```  
  
 <span data-ttu-id="8a761-113">Die **contains()** -Methode verwendet den Volltextindex, um die XML-Werte, die das Wort „custom“ irgendwo im Dokument enthalten, zu einer Teilmenge zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="8a761-113">The **contains()** method uses the full-text index to subset the XML values that contain the word "custom" anywhere in the document.</span></span> <span data-ttu-id="8a761-114">Die **exist()** -Klausel stellt sicher, dass das Wort „custom“ im Titel eines Buchs vorkommt.</span><span class="sxs-lookup"><span data-stu-id="8a761-114">The **exist()** clause ensures that the word "custom" occurs in the title of a book.</span></span>  
  
 <span data-ttu-id="8a761-115">Eine Volltextsuche mit der **contains()** -Klausel und XQuery mithilfe der **contains()** -Klausel weisen unterschiedliche Semantiken auf.</span><span class="sxs-lookup"><span data-stu-id="8a761-115">A full-text search that uses **contains()** and XQuery **contains()** has different semantics.</span></span> <span data-ttu-id="8a761-116">Das Letztere ist eine Teilzeichenfolgenübereinstimmung, und das Erstere ist eine Tokenübereinstimmung mithilfe der Wortformgenerierung.</span><span class="sxs-lookup"><span data-stu-id="8a761-116">The latter is a substring match and the former is a token match that uses stemming.</span></span> <span data-ttu-id="8a761-117">Wenn die Suche nach der Zeichenfolge erfolgt, die „run“ im Titel enthält, gilt neben „run“ auch „runs“ und „running“ als Übereinstimmung, weil sowohl die Volltextklausel **contains()** als auch die XQuery-Klausel **contains()** erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="8a761-117">Therefore, if the search is for the string that has "run" in the title, the matches will include "run", "runs", and "running", because both the full-text **contains()** and the Xquery **contains()** are satisfied.</span></span> <span data-ttu-id="8a761-118">Allerdings ergibt die Abfrage keine Übereinstimmung des Worts "customizable" im Titel, weil die Volltextklausel **contains()** nicht erfüllt ist, obwohl die XQuery-Klausel **contains()** erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="8a761-118">However, the query does not match the word "customizable" in the title in that the full-text **contains()** fails, but the Xquery **contains()** is satisfied.</span></span> <span data-ttu-id="8a761-119">Im Allgemeinen sollte für eine reine Teilzeichenfolgenübereinstimmung die Volltextklausel **contains()** entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8a761-119">Generally, for pure substring match, the full-text **contains()** clause should be removed.</span></span>  
  
 <span data-ttu-id="8a761-120">Außerdem verwendet die Volltextsuche die Wortformgenerierung, während XQuery **contains()** eine Literalübereinstimmung ist.</span><span class="sxs-lookup"><span data-stu-id="8a761-120">Additionally, full-text search uses word stemming, but XQuery **contains()** is a literal match.</span></span> <span data-ttu-id="8a761-121">Dieser Unterschied wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8a761-121">This difference is illustrated in the next example.</span></span>  
  
## <a name="example-full-text-search-on-xml-values-using-stemming"></a><span data-ttu-id="8a761-122">Beispiel: Volltextsuche für XML-Werte mithilfe der Wortstammerkennung</span><span class="sxs-lookup"><span data-stu-id="8a761-122">Example: Full-text Search on XML Values Using Stemming</span></span>  
 <span data-ttu-id="8a761-123">Die XQuery **contains()** -Überprüfung, die im vorherigen Beispiel durchgeführt wurde, kann im Allgemeinen nicht eliminiert werden.</span><span class="sxs-lookup"><span data-stu-id="8a761-123">The XQuery **contains()** check that was performed in the previous example generally cannot be eliminated.</span></span> <span data-ttu-id="8a761-124">Angenommen, die folgende Abfrage wird ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="8a761-124">Consider this query:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'run')   
```  
  
 <span data-ttu-id="8a761-125">Das Wort "ran" im Dokument stimmt wegen der Verwendung der Wortformgenerierung mit der Suchbedingung überein.</span><span class="sxs-lookup"><span data-stu-id="8a761-125">The word "ran" in the document matches the search condition because of stemming.</span></span> <span data-ttu-id="8a761-126">Außerdem wird der Suchkontext nicht mithilfe von XQuery überprüft.</span><span class="sxs-lookup"><span data-stu-id="8a761-126">Additionally, the search context is not checked by using XQuery.</span></span>  
  
 <span data-ttu-id="8a761-127">Wenn XML in relationale Spalten zerlegt wird, indem volltextindizierte AXSD verwendet wird, führen XPath-Abfragen, die für die XML-Sicht ausgeführt werden, keine Volltextsuche der zugrunde liegenden Tabellen durch.</span><span class="sxs-lookup"><span data-stu-id="8a761-127">When XML is decomposed into relational columns by using AXSD that are full-text indexed, XPath queries that occur over the XML view do not perform full-text search on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a761-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a761-128">See Also</span></span>  
 [<span data-ttu-id="8a761-129">XML-Indizes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8a761-129">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
