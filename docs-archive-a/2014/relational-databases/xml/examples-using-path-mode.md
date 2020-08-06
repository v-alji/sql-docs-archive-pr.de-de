---
title: 'Beispiele: Verwenden des PATH-Modus | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, examples
ms.assetid: 3564e13b-9b97-49ef-8cf9-6a78677b09a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0876d93ffe246b6129a3838f8dbae47f3be7ffaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726782"
---
# <a name="examples-using-path-mode"></a><span data-ttu-id="e0c92-102">Beispiele: Verwenden des PATH-Modus</span><span class="sxs-lookup"><span data-stu-id="e0c92-102">Examples: Using PATH Mode</span></span>
  <span data-ttu-id="e0c92-103">Diese Beispiele veranschaulichen die Verwendung des PATH-Modus beim Generieren von XML-Code aus einer SELECT-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="e0c92-103">The following examples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="e0c92-104">Viele dieser Abfragen beziehen sich auf die XML-Dokumente mit den Fahrradfertigungsanweisungen, die in der Instructions-Spalte der ProductModel-Tabelle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e0c92-104">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="specifying-a-simple-path-mode-query"></a><span data-ttu-id="e0c92-105">Angeben einer einfachen Abfrage im PATH-Modus</span><span class="sxs-lookup"><span data-stu-id="e0c92-105">Specifying a simple PATH mode query</span></span>  
 <span data-ttu-id="e0c92-106">Diese Abfrage gibt einen FOR XML PATH-Modus an.</span><span class="sxs-lookup"><span data-stu-id="e0c92-106">This query specifies a FOR XML PATH mode.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   
       ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH;  
GO  
```  
  
 <span data-ttu-id="e0c92-107">Das folgende Ergebnis ist elementzentrierter XML-Code, wobei jeder Spaltenwert des resultierenden Rowsets in ein Element eingebunden wird.</span><span class="sxs-lookup"><span data-stu-id="e0c92-107">The following result is element-centric XML where each column value in the resulting rowset is wrapped in an element.</span></span> <span data-ttu-id="e0c92-108">Da die `SELECT`-Klausel keine Aliase für die Spaltennamen angibt, sind die Namen der generierten untergeordneten Elemente mit denen der entsprechenden Spalten in der `SELECT`-Klausel identisch.</span><span class="sxs-lookup"><span data-stu-id="e0c92-108">Because the `SELECT` clause does not specify any aliases for the column names, the child element names generated are the same as the corresponding column names in the `SELECT` clause.</span></span> <span data-ttu-id="e0c92-109">Für jede Zeile des Rowsets wird ein <`row`>-Tag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e0c92-109">For each row in the rowset a <`row`> tag is added.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</row>`  
  
 `<row>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</row>`  
  
 <span data-ttu-id="e0c92-110">Das folgende Ergebnis ist mit dem der Abfrage im `RAW` -Modus mit angegebener Option `ELEMENTS` identisch.</span><span class="sxs-lookup"><span data-stu-id="e0c92-110">The following result is the same as the `RAW` mode query with the `ELEMENTS` option specified.</span></span> <span data-ttu-id="e0c92-111">Es wird elementzentrierter XML-Code mit einem standardmäßigen <`row`>-Element für jede Zeile des Resultsets zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e0c92-111">It returns element-centric XML with a default <`row`> element for each row in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML RAW, ELEMENTS;  
```  
  
 <span data-ttu-id="e0c92-112">Sie können optional angeben, dass der Name des Zeilenelements den Standard für <`row`> überschreibt.</span><span class="sxs-lookup"><span data-stu-id="e0c92-112">You can optionally specify the row element name to overwrite the default <`row`>.</span></span> <span data-ttu-id="e0c92-113">Die folgende Abfrage gibt beispielsweise das <`ProductModel`>-Element für jede Zeile des Rowsets zurück.</span><span class="sxs-lookup"><span data-stu-id="e0c92-113">For example, the following query returns the <`ProductModel`> element for each row in the rowset.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModel');  
GO  
```  
  
 <span data-ttu-id="e0c92-114">Das XML-Ergebnis weist den angegebenen Zeilenelementnamen auf.</span><span class="sxs-lookup"><span data-stu-id="e0c92-114">The resulting XML will have a specified row element name.</span></span>  
  
 `<ProductModel>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ProductModel>`  
  
 `<ProductModel>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ProductModel>`  
  
 <span data-ttu-id="e0c92-115">Wenn Sie eine leere Zeichenfolge angeben, wird das Wrapperelement nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="e0c92-115">If you specify a zero-length string, the wrapping element is not produced.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('');  
GO  
```  
  
 <span data-ttu-id="e0c92-116">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e0c92-116">This is the result:</span></span>  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
## <a name="specifying-xpath-like-column-names"></a><span data-ttu-id="e0c92-117">Angeben von XPath-ähnlichen Spaltennamen</span><span class="sxs-lookup"><span data-stu-id="e0c92-117">Specifying XPath-like column names</span></span>  
 <span data-ttu-id="e0c92-118">In der folgenden Abfrage beginnt der `ProductModelID`-Spaltenname mit dem Zeichen \@ und enthält keinen Schrägstrich (/).</span><span class="sxs-lookup"><span data-stu-id="e0c92-118">In the following query the `ProductModelID` column name specified starts with '\@' and does not contain a slash mark ('/').</span></span> <span data-ttu-id="e0c92-119">Daher wird im XML-Ergebnis für das <`row`>-Element mit dem entsprechenden Spaltenwert ein Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="e0c92-119">Therefore, an attribute of the <`row`> element that has the corresponding column value is created in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('ProductModelData');  
GO  
```  
  
 <span data-ttu-id="e0c92-120">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e0c92-120">This is the result:</span></span>  
  
 `< ProductModelData id="122">`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ ProductModelData >`  
  
 `< ProductModelData id="119">`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ ProductModelData >`  
  
 <span data-ttu-id="e0c92-121">Sie können ein einzelnes Element auf höchster Ebene hinzufügen, indem Sie in `root` die Option `FOR XML`angeben.</span><span class="sxs-lookup"><span data-stu-id="e0c92-121">You can add a single top-level element by specifying the `root` option in `FOR XML`.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="e0c92-122">Um eine Hierarchie zu generieren, können Sie eine PATH-ähnliche Syntax einfügen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-122">To generate a hierarchy, you can include PATH-like syntax.</span></span> <span data-ttu-id="e0c92-123">Wenn Sie beispielsweise den Spaltennamen für die `Name` -Spalte zu "SomeChild/ModelName" ändern, erhalten Sie ein hierarchisiertes XML-Ergebnis, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e0c92-123">For example, change the column name for the `Name` column to "SomeChild/ModelName" and you will obtain XML with hierarchy, as shown in this result:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="122">`  
  
 `<SomeChild>`  
  
 `<ModelName>All-Purpose Bike Stand</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData id="119">`  
  
 `<SomeChild>`  
  
 `<ModelName>Bike Wash</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="e0c92-124">Außer der ID und dem Namen des Produktmodells ruft die folgende Abfrage die Speicherorte der Fertigungsanweisungen dieses Produktmodells ab.</span><span class="sxs-lookup"><span data-stu-id="e0c92-124">Besides the product model ID and name, the following query retrieves the manufacturing instruction locations for the product model.</span></span> <span data-ttu-id="e0c92-125">Nachdem die Instructions-Spalte vom Typ `xml` ist, wird die `query()`-Methode vom `xml`-Datentyp angegeben, um den Speicherort abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-125">Because the Instructions column is of `xml` type, the `query()` method of `xml` data type is specified to retrieve the location.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') AS ManuInstr  
FROM Production.ProductModel  
WHERE ProductModelID = 7  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="e0c92-126">Dies ist das Teilergebnis.</span><span class="sxs-lookup"><span data-stu-id="e0c92-126">This is the partial result.</span></span> <span data-ttu-id="e0c92-127">Da in der Abfrage "ManuInstr" als Spaltenname angegeben ist, wird der von der-Methode zurückgegebene XML-Code `query()` in ein <>-Tag umschließt, `ManuInstr` wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e0c92-127">Because the query specifies ManuInstr as the column name, the XML returned by the `query()` method is wrapped in a <`ManuInstr`> tag as shown in the following:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="7">`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<ManuInstr>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `<MI:step>...</MI:step>...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ManuInstr>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="e0c92-128">In die vorherige FOR XML-Abfrage können Sie eventuell für das <`Root`>- und das <`ProductModelData`>-Element Namespaces einschließen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-128">In the previous FOR XML query, you may want to include namespaces for the <`Root`> and <`ProductModelData`> elements.</span></span> <span data-ttu-id="e0c92-129">Dies erreichen Sie, indem Sie zunächst mithilfe von WITH XMLNAMESPACES das an den Namespace zu bindende Präfix definieren und das Präfix anschließend in der FOR XML-Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0c92-129">You can do this by first defining the prefix to namespace binding by using WITH XMLNAMESPACES and using prefixes in the FOR XML query.</span></span> <span data-ttu-id="e0c92-130">Weitere Informationen finden Sie unter [Hinzufügen von Namespaces zu Abfragen mit WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="e0c92-130">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES (  
   'uri1' AS ns1,    
   'uri2' AS ns2,  
   'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' as MI)  
SELECT ProductModelID AS "ns1:ProductModelID",  
       Name           AS "ns1:Name",  
       Instructions.query('  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ('ns2:ProductInfo'), root('ns1:root');  
GO  
```  
  
 <span data-ttu-id="e0c92-131">Beachten Sie, dass das `MI` -Präfix auch in `WITH XMLNAMESPACES`definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0c92-131">Note that the `MI` prefix is also defined in the `WITH XMLNAMESPACES`.</span></span> <span data-ttu-id="e0c92-132">Folglich definiert die `query()`-Methode des angegebenen `xml`-Typs das Präfix nicht im Abfrageprolog.</span><span class="sxs-lookup"><span data-stu-id="e0c92-132">As a result, the `query()` method of the `xml` type specified does not define the prefix in the query prolog.</span></span> <span data-ttu-id="e0c92-133">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e0c92-133">This is the result:</span></span>  
  
 `<ns1:root xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">`  
  
 `<ns2:ProductInfo>`  
  
 `<ns1:ProductModelID>7</ns1:ProductModelID>`  
  
 `<ns1:Name>HL Touring Frame</ns1:Name>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `LaborHours="2.5" LotSize="100" MachineHours="3" SetupHours="0.5" LocationID="10" xmlns="">`  
  
 `<MI:step>`  
  
 `Insert <MI:material>aluminum sheet MS-2341</MI:material> into the <MI:tool>T-85A framing tool</MI:tool>.`  
  
 `</MI:step>`  
  
 `...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ns2:ProductInfo>`  
  
 `</ns1:root>`  
  
## <a name="generating-a-value-list-using-path-mode"></a><span data-ttu-id="e0c92-134">Generieren einer Wertliste mithilfe des PATH-Modus</span><span class="sxs-lookup"><span data-stu-id="e0c92-134">Generating a value list using PATH mode</span></span>  
 <span data-ttu-id="e0c92-135">Diese Abfrage konstruiert für jedes Produktmodell eine Wertliste mit Produkt-IDs.</span><span class="sxs-lookup"><span data-stu-id="e0c92-135">For each product model, this query constructs a value list of product IDs.</span></span> <span data-ttu-id="e0c92-136">Außerdem konstruiert die Abfrage für jede Produkt-ID geschachtelte <`ProductName`>-Elemente, wie im folgenden XML-Fragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e0c92-136">For each product ID, the query also constructs <`ProductName`> nested elements, as shown in this XML fragment:</span></span>  
  
 `<ProductModelData ProductModelID="7" ProductModelName="..."`  
  
 `ProductIDs="product id list in the product model" >`  
  
 `<ProductName>...</ProductName>`  
  
 `<ProductName>...</ProductName>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="e0c92-137">Im Folgenden wird die Abfrage gezeigt, die den gewünschten XML-Code erstellt:</span><span class="sxs-lookup"><span data-stu-id="e0c92-137">This is the query that produces the XML you want:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID     AS "@ProductModelID",  
       Name               S "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')) S "@ProductIDs",  
       (SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
        FOR XML PATH ('')) as "ProductNames"  
FROM   Production.ProductModel  
WHERE  ProductModelID= 7 or ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="e0c92-138">Beachten Sie hinsichtlich der vorherigen Abfrage Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e0c92-138">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="e0c92-139">Das erste geschachtelte `SELECT` gibt eine Liste von Product-IDs zurück und verwendet dabei `data()` als Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-139">The first nested `SELECT` returns a list of ProductIDs by using `data()` as the column name.</span></span> <span data-ttu-id="e0c92-140">Da die Abfrage eine leere Zeichenfolge für den Namen des Zeilenelements in `FOR XML PATH`angibt, wird kein Element generiert.</span><span class="sxs-lookup"><span data-stu-id="e0c92-140">Because the query specifies an empty string as the row element name in `FOR XML PATH`, no element is generated.</span></span> <span data-ttu-id="e0c92-141">Stattdessen wird die Wertliste dem `ProductID` -Attribut zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-141">Instead, the value list is assigned to the `ProductID` attribute.</span></span>  
  
-   <span data-ttu-id="e0c92-142">Das zweite geschachtelte `SELECT` ruft die Produktnamen der Produkte des Produktmodells auf.</span><span class="sxs-lookup"><span data-stu-id="e0c92-142">The second nested `SELECT` retrieves product names for products in the product model.</span></span> <span data-ttu-id="e0c92-143">Es generiert <`ProductName`>-Elemente, die eingebunden in das <`ProductNames`>-Element zurückgegeben werden, da die Abfrage `ProductNames` als Spaltennamen angibt.</span><span class="sxs-lookup"><span data-stu-id="e0c92-143">It generates <`ProductName`> elements that are returned wrapped in the <`ProductNames`> element, because the query specifies `ProductNames` as the column name.</span></span>  
  
 <span data-ttu-id="e0c92-144">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="e0c92-144">This is the partial result:</span></span>  
  
 `<ProductModelData PId="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>HL Touring Frame - Yellow, 60</ProductName>`  
  
 `<ProductName>HL Touring Frame - Yellow, 46</ProductName></ProductNames>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 `<ProductModelData PId="9"`  
  
 `ProductModelName="LL Road Frame"`  
  
 `ProductIDs="722 723 724 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>LL Road Frame - Black, 58</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 60</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 62</ProductName>`  
  
 `...`  
  
 `</ProductNames>`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="e0c92-145">Die die Produktnamen konstruierende Unterabfrage gibt das Ergebnis als Zeichenfolge zurück, die in eine Entität geändert und anschließend dem XML-Code hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e0c92-145">The subquery constructing the product names returns the result as a string that is entitized and then added to the XML.</span></span> <span data-ttu-id="e0c92-146">Wenn Sie die TYPE-Direktive hinzufügen, `FOR XML PATH (''), type`, gibt die Unterabfrage das Ergebnis als `xml`-Typ zurück, und es erfolgt keine Änderung in Entitäten.</span><span class="sxs-lookup"><span data-stu-id="e0c92-146">If you add the type directive, `FOR XML PATH (''), type`, the subquery returns the result as `xml` type and no entitization occurs.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@ProductModelID",  
      Name AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ProductIDs",  
       (  
       SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH (''), type  
       ) AS "ProductNames"  
  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
## <a name="adding-namespaces-in-the-resulting-xml"></a><span data-ttu-id="e0c92-147">Hinzufügen von Namespaces zu XML-Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="e0c92-147">Adding namespaces in the resulting XML</span></span>  
 <span data-ttu-id="e0c92-148">Wie unter [Hinzufügen von Namespaces mit WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md)beschrieben, können Sie WITH XMLNAMESPACES verwenden, um Namespaces in Abfragen im PATH-Modus aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-148">As described in [Adding Namespaces Using WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), you can use WITH XMLNAMESPACES to include namespaces in the PATH mode queries.</span></span> <span data-ttu-id="e0c92-149">Angenommen, die in der SELECT-Klausel angegebenen Namen enthalten Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="e0c92-149">For example, names specified in the SELECT clause include namespace prefixes.</span></span> <span data-ttu-id="e0c92-150">Die folgende Abfrage im `PATH` -Modus konstruiert dieses XML-Ergebnis mit Namespaces.</span><span class="sxs-lookup"><span data-stu-id="e0c92-150">The following `PATH` mode query constructs XML with namespaces.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
GO  
```  
  
 <span data-ttu-id="e0c92-151">Das dem <`English`>-Element hinzugefügte `@xml:lang`-Attribut ist im vordefinierten XML-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="e0c92-151">The `@xml:lang` attribute added to the <`English`> element is defined in the predefined xml namespace.</span></span>  
  
 <span data-ttu-id="e0c92-152">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e0c92-152">This is the result:</span></span>  
  
 `<Translation>`  
  
 `<English xml:lang="en">food</English>`  
  
 `<German xml:lang="ger">Essen</German>`  
  
 `</Translation>`  
  
 <span data-ttu-id="e0c92-153">Die folgende Abfrage ist der in Beispiel C ähnlich, mit dem Unterschied, dass sie `WITH XMLNAMESPACES` verwendet, um Namespaces in das XML-Ergebnis einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e0c92-153">The following query is similar to example C, except that it uses `WITH XMLNAMESPACES` to include namespaces in the XML result.</span></span> <span data-ttu-id="e0c92-154">Weitere Informationen finden Sie unter [Hinzufügen von Namespaces zu Abfragen mit WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="e0c92-154">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES ('uri1' AS ns1,  DEFAULT 'uri2')  
SELECT ProductModelID AS "@ns1:ProductModelID",  
      Name AS "@ns1:ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ns1:ProductIDs",  
       (  
       SELECT ProductID AS "@ns1:ProductID",   
              Name AS "@ns1:ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH , type   
       ) AS "ns1:ProductNames"  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData'), root('root');  
```  
  
 <span data-ttu-id="e0c92-155">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e0c92-155">This is the result:</span></span>  
  
 `<root xmlns="uri2" xmlns:ns1="uri1">`  
  
 `<ProductModelData ns1:ProductModelID="7" ns1:ProductModelName="HL Touring Frame" ns1:ProductIDs="885 887 888 889 890 891 892 893">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="885" ns1:ProductName="HL Touring Frame - Yellow, 60" />`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="887" ns1:ProductName="HL Touring Frame - Yellow, 46" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData ns1:ProductModelID="9" ns1:ProductModelName="LL Road Frame" ns1:ProductIDs="722 723 724 725 726 727 728 729 730 736 737 738">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="722" ns1:ProductName="LL Road Frame - Black, 58" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `</root>`  
  
## <a name="see-also"></a><span data-ttu-id="e0c92-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0c92-156">See Also</span></span>  
 [<span data-ttu-id="e0c92-157">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="e0c92-157">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
