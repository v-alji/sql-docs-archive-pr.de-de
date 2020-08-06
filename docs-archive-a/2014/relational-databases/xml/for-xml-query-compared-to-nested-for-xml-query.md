---
title: FOR XML-Abfragen im Vergleich zu geschachtelten FOR XML-Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], comparing query types
ms.assetid: 19225b4a-ee3f-47cf-8bcc-52699eeda32c
author: rothja
ms.author: jroth
ms.openlocfilehash: ca10060702d0c7e50f2be79310c55e177dca358d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726781"
---
# <a name="for-xml-query-compared-to-nested-for-xml-query"></a><span data-ttu-id="ad5bb-102">FOR XML-Abfragen im Vergleich zu geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="ad5bb-102">FOR XML Query Compared to Nested FOR XML Query</span></span>
  <span data-ttu-id="ad5bb-103">In diesem Thema wird eine einstufige FOR XML-Abfrage mit einer geschachtelten FOR XML-Abfrage verglichen.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-103">This topic compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="ad5bb-104">Ein Vorteil, den die Verwendung geschachtelter FOR XML-Abfragen bietet, besteht darin, dass Sie eine Kombination aus attributzentriertem und elementzentriertem XML-Code für Abfrageergebnisse angeben können.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-104">One of the benefits of using nested FOR XML queries is that you can specify a combination of attribute-centric and element-centric XML for query results.</span></span> <span data-ttu-id="ad5bb-105">Das Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-105">The example demonstrates this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad5bb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad5bb-106">Example</span></span>  
 <span data-ttu-id="ad5bb-107">Die folgende `SELECT` -Abfrage ruft Informationen zur Produktkategorie und Produktunterkategorie aus der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-107">The following `SELECT` query retrieves product category and subcategory information in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="ad5bb-108">In der Abfrage gibt es keine geschachtelte FOR XML-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-108">There is no nested FOR XML in the query.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductCategory.ProductCategoryID,   
         ProductCategory.Name as CategoryName,  
         ProductSubCategory.ProductSubCategoryID,   
         ProductSubCategory.Name  
FROM     Production.ProductCategory, Production.ProductSubCategory  
WHERE    ProductCategory.ProductCategoryID = ProductSubCategory.ProductCategoryID  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="ad5bb-109">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-109">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory ProductSubCategoryID="1" Name="Mountain Bike"/>  
  <ProductSubCategory ProductSubCategoryID="2" Name="Road Bike"/>  
  <ProductSubCategory ProductSubCategoryID="3" Name="Touring Bike"/>  
</ProductCategory>  
...  
```  
  
 <span data-ttu-id="ad5bb-110">Wenn Sie die `ELEMENTS` -Direktive in der Abfrage angeben, erhalten Sie ein elementzentriertes Ergebnis, wie es im folgenden Ergebnisfragment gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-110">If you specify the `ELEMENTS` directive in the query, you receive an element-centric result, as shown in the following result fragment:</span></span>  
  
```  
<ProductCategory>  
  <ProductCategoryID>1</ProductCategoryID>  
  <CategoryName>Bike</CategoryName>  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <Name>Mountain Bike</Name>  
  </ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  </ProductSubCategory>  
</ProductCategory>  
```  
  
 <span data-ttu-id="ad5bb-111">Gehen wir nun davon aus, dass Sie eine XML-Hierarchie generieren möchten, die eine Kombination aus attributzentriertem und elementzentriertem XML-Code darstellt, wie das im folgenden Fragment gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-111">Next, assume that you want to generate an XML hierarchy that is a combination of attribute-centric and element-centric XML, as shown in the following fragment:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="ad5bb-112">Im oben gezeigten Fragment sind die Informationen zur Produktkategorie (z. B. die Kategorie-ID und der Kategoriename) Attribute.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-112">In the previous fragment, product category information such as category ID and category name are attributes.</span></span> <span data-ttu-id="ad5bb-113">Allerdings sind die Informationen zur Unterkategorie elementzentriert.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-113">However, the subcategory information is element-centric.</span></span> <span data-ttu-id="ad5bb-114">Zum Konstruieren des <`ProductCategory`>-Elements können Sie eine `FOR XML`-Abfrage wie die folgende schreiben:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-114">To construct the <`ProductCategory`> element, you can write a `FOR XML` query as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName  
FROM Production.ProductCategory ProdCat  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="ad5bb-115">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-115">This is the result:</span></span>  
  
```  
< ProdCat ProductCategoryID="1" CategoryName="Bikes" />  
< ProdCat ProductCategoryID="2" CategoryName="Components" />  
< ProdCat ProductCategoryID="3" CategoryName="Clothing" />  
< ProdCat ProductCategoryID="4" CategoryName="Accessories" />  
```  
  
 <span data-ttu-id="ad5bb-116">Zum Konstruieren der geschachtelten <`ProductSubCategory`>-Elemente im angestrebten XML-Code fügen Sie anschließend eine geschachtelte `FOR XML`-Abfrage hinzu, wie es im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-116">To construct the nested <`ProductSubCategory`> elements in the XML you want, you then add a nested `FOR XML` query, as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName  
        FROM   Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="ad5bb-117">Beachten Sie in der vorhergehenden Abfrage Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-117">Note the following in the previous query:</span></span>  
  
-   <span data-ttu-id="ad5bb-118">Mit der inneren `FOR XML` -Abfrage werden Informationen zur Produktunterkategorie abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-118">The inner `FOR XML` query retrieves product subcategory information.</span></span> <span data-ttu-id="ad5bb-119">Die `ELEMENTS` -Direktive wird der inneren `FOR XML` -Abfrage hinzugefügt, um elementzentrierten XML-Code zu generieren, der dem von der äußeren Abfrage generierten XML-Code hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-119">The `ELEMENTS` directive is added in the inner `FOR XML` to generate element-centric XML that is added to the XML generated by the outer query.</span></span> <span data-ttu-id="ad5bb-120">Standardmäßig generiert die äußere Abfrage attributzentrierten XML-Code.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-120">By default, the outer query generates attribute-centric XML.</span></span>  
  
-   <span data-ttu-id="ad5bb-121">In der inneren Abfrage wird die `TYPE` -Direktive angegeben, sodass das Ergebnis den **xml** -Typ aufweist.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-121">In the inner query, the `TYPE` directive is specified so the result is of **xml** type.</span></span> <span data-ttu-id="ad5bb-122">Wenn `TYPE` nicht angegeben wird, wird das Ergebnis als `nvarchar(max)`-Typ zurückgegeben, und die XML-Daten werden als Entitäten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-122">If `TYPE` is not specified, the result is returned as `nvarchar(max)` type and the XML data is returned as entities.</span></span>  
  
-   <span data-ttu-id="ad5bb-123">Die `TYPE` -Direktive wird auch in der äußeren Abfrage angegeben.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-123">The outer query also specifies the `TYPE` directive.</span></span> <span data-ttu-id="ad5bb-124">Deshalb wird das Ergebnis dieser Abfrage als **xml** -Typ an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-124">Therefore, the result of this query is returned to the client as **xml** type.</span></span>  
  
 <span data-ttu-id="ad5bb-125">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-125">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="ad5bb-126">Die folgende Abfrage ist lediglich eine Erweiterung der vorherigen Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-126">The following query is just an extension of the previous query.</span></span> <span data-ttu-id="ad5bb-127">Sie zeigt die vollständige Produkthierarchie in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-127">It shows the full product hierarchy in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="ad5bb-128">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-128">This includes the following:</span></span>  
  
-   <span data-ttu-id="ad5bb-129">Produktkategorien</span><span class="sxs-lookup"><span data-stu-id="ad5bb-129">Product categories</span></span>  
  
-   <span data-ttu-id="ad5bb-130">Produktunterkategorien in jeder Kategorie</span><span class="sxs-lookup"><span data-stu-id="ad5bb-130">Product subcategories in each category</span></span>  
  
-   <span data-ttu-id="ad5bb-131">Produktmodelle in jeder Unterkategorie</span><span class="sxs-lookup"><span data-stu-id="ad5bb-131">Product models in each subcategory</span></span>  
  
-   <span data-ttu-id="ad5bb-132">Produkte in jedem Produktmodell</span><span class="sxs-lookup"><span data-stu-id="ad5bb-132">Products in each model</span></span>  
  
 <span data-ttu-id="ad5bb-133">Die folgende Abfrage kann ggf. für das Verständnis der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-133">You might find the following query useful in understanding the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName,  
               (SELECT ProductModel.ProductModelID,   
                       ProductModel.Name as ModelName,  
                       (SELECT ProductID, Name as ProductName, Color  
                        FROM   Production.Product  
                        WHERE  Product.ProductModelID =   
                               ProductModel.ProductModelID  
                        FOR XML AUTO, TYPE)  
                FROM   (SELECT distinct ProductModel.ProductModelID,   
                               ProductModel.Name  
                        FROM   Production.ProductModel,   
                               Production.Product  
                        WHERE  ProductModel.ProductModelID =   
                               Product.ProductModelID  
                        AND    Product.ProductSubCategoryID =   
                               ProductSubCategory.ProductSubCategoryID)   
                                  ProductModel  
                FOR XML AUTO, type  
               )  
        FROM Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="ad5bb-134">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="ad5bb-134">This is the partial result:</span></span>  
  
```  
<Production.ProductCategory ProductCategoryID="1" CategoryName="Bikes">  
  <Production.ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bikes</SubCategoryName>  
    <ProductModel ProductModelID="19" ModelName="Mountain-100">  
      <Production.Product ProductID="771"   
                ProductName="Mountain-100 Silver, 38" Color="Silver" />  
      <Production.Product ProductID="772"   
                ProductName="Mountain-100 Silver, 42" Color="Silver" />  
      <Production.Product ProductID="773"   
                ProductName="Mountain-100 Silver, 44" Color="Silver" />  
        ...  
    </ProductModel>  
     ...  
```  
  
 <span data-ttu-id="ad5bb-135">Wenn Sie die `ELEMENTS` -Direktive aus der geschachtelten `FOR XML` -Abfrage entfernen, mit der die Produktunterkategorien generiert werden, ist das gesamte Ergebnis attributzentriert.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-135">If you remove the `ELEMENTS` directive from the nested `FOR XML` query that generates product subcategories, the whole result is attribute-centric.</span></span> <span data-ttu-id="ad5bb-136">Sie können diese Abfrage dann ohne Schachtelung schreiben.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-136">You can then write this query without nesting.</span></span> <span data-ttu-id="ad5bb-137">Das Hinzufügen der `ELEMENTS` -Direktive ergibt einen XML-Code, der teilweise attributzentriert und teilweise elementzentriert ist.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-137">The addition of `ELEMENTS` results in an XML that is partly attribute-centric and partly element-centric.</span></span> <span data-ttu-id="ad5bb-138">Dieses Ergebnis kann nicht durch eine FOR XML-Abfrage mit nur einer einzigen Ebene generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad5bb-138">This result cannot be generated by a single-level, FOR XML query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5bb-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad5bb-139">See Also</span></span>  
 [<span data-ttu-id="ad5bb-140">Verwenden von geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="ad5bb-140">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
