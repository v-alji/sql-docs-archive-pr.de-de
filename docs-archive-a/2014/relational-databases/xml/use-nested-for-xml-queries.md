---
title: Verwenden von geschachtelten FOR XML-Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 60c4198697f8d19c9b2e5bc1b415e0787861d40a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722601"
---
# <a name="use-nested-for-xml-queries"></a><span data-ttu-id="95d9c-102">Verwenden von geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="95d9c-102">Use Nested FOR XML Queries</span></span>
  <span data-ttu-id="95d9c-103">Der `xml` -Datentyp und die [Type-Direktive in for XML-Abfragen](type-directive-in-for-xml-queries.md) ermöglichen, dass der von for XML-Abfragen zurückgegebene XML-Code sowohl auf dem Server als auch auf dem Client verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="95d9c-103">The `xml` data type and the [TYPE directive in FOR XML queries](type-directive-in-for-xml-queries.md) enable the XML returned by the FOR XML queries to be processed on the server as well as on the client.</span></span>  
  
## <a name="processing-with-xml-type-variables"></a><span data-ttu-id="95d9c-104">Verarbeiten mit XML-Typvariablen</span><span class="sxs-lookup"><span data-stu-id="95d9c-104">Processing with xml Type Variables</span></span>  
 <span data-ttu-id="95d9c-105">Sie können das Ergebnis einer FOR XML-Abfrage einer `xml`-Typvariablen zuweisen oder das Ergebnis mithilfe einer XQuery-Abfrage abfragen und das daraus entstehende Ergebnis einer `xml`-Typvariablen zur weiteren Verarbeitung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95d9c-105">You can assign the FOR XML query result to an `xml` type variable, or use XQuery to query the result, and assign that result to an `xml` type variable for more processing.</span></span>  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 <span data-ttu-id="95d9c-106">Sie können den in der Variablen `@x` zurückgegebenen XML-Code zusätzlich verarbeiten, indem Sie eine der `xml`-Datentypmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="95d9c-106">You can additionally process the XML returned in the variable, `@x`, by using one of the `xml` data type methods.</span></span> <span data-ttu-id="95d9c-107">So können Sie z. B. den Attributwert von `ProductModelID` mithilfe der [value()-Methode](/sql/t-sql/xml/value-method-xml-data-type)abrufen.</span><span class="sxs-lookup"><span data-stu-id="95d9c-107">For example, you can retrieve the `ProductModelID` attribute value by using the [value() method](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 <span data-ttu-id="95d9c-108">Im folgenden Beispiel wird das Ergebnis der `FOR XML`-Abfrage als `xml`-Typ zurückgegeben, da in der `TYPE`-Klausel die `FOR XML`-Direktive angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="95d9c-108">In the following example, the `FOR XML` query result is returned as an `xml` type, because the `TYPE` directive is specified in the `FOR XML` clause.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 <span data-ttu-id="95d9c-109">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="95d9c-109">This is the result:</span></span>  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 <span data-ttu-id="95d9c-110">Da das Ergebnis dem `xml`-Typ entspricht, können Sie eine der `xml`-Datentypmethoden direkt für diesen XML-Code angeben, wie es in der folgenden Abfrage gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="95d9c-110">Because the result is of `xml` type, you can specify one of the `xml` data type methods directly against this XML, as shown in the following query.</span></span> <span data-ttu-id="95d9c-111">In der Abfrage wird die [query()-Methode (XML-Datentyp)](/sql/t-sql/xml/query-method-xml-data-type) verwendet, um das erste untergeordnete <`row`>-Element des Elements <`myRoot`> abzurufen.</span><span class="sxs-lookup"><span data-stu-id="95d9c-111">In the query, the [query() method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) is used to retrieve the first <`row`> element child of the <`myRoot`> element.</span></span>  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 <span data-ttu-id="95d9c-112">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="95d9c-112">This is the result:</span></span>  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a><span data-ttu-id="95d9c-113">Zurückgeben von Ergebnissen innerer FOR XML-Abfragen als XML-Typinstanzen an äußere Abfragen</span><span class="sxs-lookup"><span data-stu-id="95d9c-113">Returning Inner FOR XML Query Results to Outer Queries as xml Type Instances</span></span>  
 <span data-ttu-id="95d9c-114">Sie können geschachtelte `FOR XML`-Abfragen schreiben, bei denen das Ergebnis der inneren Abfrage als `xml`-Typ an die äußere Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="95d9c-114">You can write nested `FOR XML` queries where the result of the inner query is returned as an `xml` type to the outer query.</span></span> <span data-ttu-id="95d9c-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="95d9c-115">For example:</span></span>  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="95d9c-116">Beachten Sie hinsichtlich der vorherigen Abfrage Folgendes:</span><span class="sxs-lookup"><span data-stu-id="95d9c-116">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="95d9c-117">Der von der inneren `FOR XML` -Abfrage generierte XML-Code wird dem von der äußeren `FOR XML`-Abfrage generierten XML-Code hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="95d9c-117">The XML generated by the inner `FOR XML` query is added to the XML generated by the outer `FOR XML`.</span></span>  
  
-   <span data-ttu-id="95d9c-118">Die innere Abfrage gibt die `TYPE` -Direktive an.</span><span class="sxs-lookup"><span data-stu-id="95d9c-118">The inner query specifies the `TYPE` directive.</span></span> <span data-ttu-id="95d9c-119">Die von der inneren Abfrage zurückgegebenen XML-Daten gehören daher dem `xml`-Typ an.</span><span class="sxs-lookup"><span data-stu-id="95d9c-119">Therefore, the XML data returned by the inner query is of `xml` type.</span></span> <span data-ttu-id="95d9c-120">Wenn die TYPE-Direktive nicht angegeben wird, wird das Ergebnis der inneren `FOR XML`-Abfrage als `nvarchar(max)` zurückgegeben, und die XML-Daten werden in Entitäten geändert.</span><span class="sxs-lookup"><span data-stu-id="95d9c-120">If the TYPE directive is not specified, the result of the inner `FOR XML` query is returned as `nvarchar(max)` and the XML data is entitized.</span></span>  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a><span data-ttu-id="95d9c-121">Steuern der Form der resultierenden XML-Daten</span><span class="sxs-lookup"><span data-stu-id="95d9c-121">Controlling the Shape of Resulting XML Data</span></span>  
 <span data-ttu-id="95d9c-122">Geschachtelte FOR XML-Abfragen ermöglichen eine bessere Steuerung der Form der resultierenden XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="95d9c-122">Nested FOR XML queries give you more control in defining the shape of the resulting XML data.</span></span> <span data-ttu-id="95d9c-123">Sie können jedoch mit geschachtelten FOR XML-Abfragen XML-Code erstellen, der zum Teil attributzentriert und zum Teil elementzentriert ist.</span><span class="sxs-lookup"><span data-stu-id="95d9c-123">You can use nested FOR XML queries to construct XML that is partly attribute-centric and partly element-centric.</span></span>  
  
 <span data-ttu-id="95d9c-124">Weitere Informationen über das Angeben von attributzentrierter und elementzentrierter XML mit geschachtelten FOR XML-Abfragen finden Sie unter [FOR XML-Abfragen im Vergleich zu geschachtelten FOR XML-Abfragen](../xml/for-xml-query-compared-to-nested-for-xml-query.md) und [Gestalten von XML mit geschachtelten FOR XML-Abfragen](../xml/shape-xml-with-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="95d9c-124">For more information about specifying both attribute-centric and element-centric XML with nested FOR XML queries, see [FOR XML Query Compared to Nested FOR XML Query](../xml/for-xml-query-compared-to-nested-for-xml-query.md) and [Shape XML with Nested FOR XML Queries](../xml/shape-xml-with-nested-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="95d9c-125">Sie können XML-Hierarchien generieren, die gleichgeordnete Elemente enthalten, indem Sie geschachtelte FOR XML-Abfragen im AUTO-Modus angeben.</span><span class="sxs-lookup"><span data-stu-id="95d9c-125">You can generate XML hierarchies that include siblings by specifying nested AUTO mode FOR XML queries.</span></span> <span data-ttu-id="95d9c-126">Weitere Informationen finden Sie unter [Generieren von gleichgeordneten Elementen mit einer geschachtelten AUTO-Modusabfrage](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="95d9c-126">For more information, see [Generate Siblings with a Nested AUTO Mode Query](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span></span>  
  
 <span data-ttu-id="95d9c-127">Unabhängig davon, welchen Modus Sie verwenden, bieten geschachtelte FOR XML-Abfragen größere Steuerungsmöglichkeiten beim Beschreiben der Form des resultierenden XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="95d9c-127">Regardless of which mode you use, nested FOR XML queries provide more control in describing the shape of the resulting XML.</span></span> <span data-ttu-id="95d9c-128">Diese Abfragen können anstelle von Abfragen im EXPLICIT-Modus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95d9c-128">They can be used in the place of EXPLICIT mode queries.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="95d9c-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="95d9c-129">Examples</span></span>  
 <span data-ttu-id="95d9c-130">Die folgenden Themen enthalten Beispiele für geschachtelte FOR XML-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="95d9c-130">The following topics provide examples of nested FOR XML queries.</span></span>  
  
 [<span data-ttu-id="95d9c-131">FOR XML-Abfragen im Vergleich zu geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="95d9c-131">FOR XML Query Compared to Nested FOR XML Query</span></span>](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 <span data-ttu-id="95d9c-132">In diesem Thema wird eine einstufige FOR XML-Abfrage mit einer geschachtelten FOR XML-Abfrage verglichen.</span><span class="sxs-lookup"><span data-stu-id="95d9c-132">Compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="95d9c-133">In diesem Beispiel wird unter Anderem veranschaulicht, wie sowohl attributzentriertes als auch elementzentriertes XML als Abfrageergebnis angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="95d9c-133">This example includes a demonstration of how to specify both attribute-centric and element-centric XML as the result of the query.</span></span>  
  
 [<span data-ttu-id="95d9c-134">Generieren von gleichgeordneten Elementen mit einer geschachtelten AUTO-Modusabfrage</span><span class="sxs-lookup"><span data-stu-id="95d9c-134">Generate Siblings with a Nested AUTO Mode Query</span></span>](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 <span data-ttu-id="95d9c-135">Zeigt, wie gleichgeordnete Elemente durch Verwenden einer geschachtelten Abfrage im AUTO-Modus generiert werden.</span><span class="sxs-lookup"><span data-stu-id="95d9c-135">Shows how to generate siblings by using a nested AUTO mode query</span></span>  
  
 [<span data-ttu-id="95d9c-136">Verwenden geschachtelter FOR XML-Abfragen in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="95d9c-136">Use Nested FOR XML Queries in ASP.NET</span></span>](use-nested-for-xml-queries-in-asp-net.md)  
 <span data-ttu-id="95d9c-137">Veranschaulicht, wie eine ASPX-Anwendung FOR XML verwenden kann, um XML von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="95d9c-137">Demonstrates how an ASPX application can use FOR XML to return XML from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="95d9c-138">Gestalten von XML mit geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="95d9c-138">Shape XML with Nested FOR XML Queries</span></span>](../xml/shape-xml-with-nested-for-xml-queries.md)  
 <span data-ttu-id="95d9c-139">Zeigt, wie mit geschachtelten FOR XML-Abfragen die Struktur eines von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]erstellten XML-Dokuments gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="95d9c-139">Shows how to use nested FOR XML queries to control the structure of an XML document created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
