---
title: Gestalten von XML mit geschachtelten FOR XML-Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], nested FOR XML
- XML [SQL Server], FOR XML queries
ms.assetid: 8dc42c05-16e8-4b7b-a5d3-550b55acae26
author: rothja
ms.author: jroth
ms.openlocfilehash: 738b5b3ec67dada90c851d284ccc8b3009a51aa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619676"
---
# <a name="shape-xml-with-nested-for-xml-queries"></a><span data-ttu-id="e909e-102">Gestalten von XML mit geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e909e-102">Shape XML with Nested FOR XML Queries</span></span>
  <span data-ttu-id="e909e-103">Das folgende Beispiel ist eine Abfrage der `Production.Product`-Tabelle zum Abrufen der Werte von `ListPrice` und `StandardCost` eines bestimmten Produkts.</span><span class="sxs-lookup"><span data-stu-id="e909e-103">The following example queries the `Production.Product` table to retrieve the `ListPrice` and `StandardCost` values of a specific product.</span></span> <span data-ttu-id="e909e-104">Damit die Abfrage interessant wird, werden beide Preise in einem <`Price`>-Element zurückgegeben, und jedes <`Price`>-Element verfügt über ein `PriceType`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="e909e-104">To make the query interesting, both prices are returned in a <`Price`> element, and each <`Price`> element has a `PriceType` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e909e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e909e-105">Example</span></span>  
 <span data-ttu-id="e909e-106">Der erwartete XML-Code hat die folgende Form:</span><span class="sxs-lookup"><span data-stu-id="e909e-106">This is the expected shape of the XML:</span></span>  
  
```  
<xsd:schema xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet2" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet2" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.Product" type="xsd:anyType" />  
</xsd:schema>  
<Production.Product xmlns="urn:schemas-microsoft-com:sql:SqlRowSet2" ProductID="520">  
  <Price xmlns="" PriceType="ListPrice">133.34</Price>  
  <Price xmlns="" PriceType="StandardCost">98.77</Price>  
</Production.Product>  
```  
  
 <span data-ttu-id="e909e-107">Dies ist die geschachtelte FOR XML-Abfrage:</span><span class="sxs-lookup"><span data-stu-id="e909e-107">This is the nested FOR XML query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Product.ProductID,   
          (SELECT 'ListPrice' as PriceType,   
                   CAST(CAST(ListPrice as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE),  
          (SELECT  'StandardCost' as PriceType,   
                   CAST(CAST(StandardCost as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE)  
FROM Production.Product  
WHERE ProductID=520  
for XML AUTO, TYPE, XMLSCHEMA  
```  
  
 <span data-ttu-id="e909e-108">Beachten Sie hinsichtlich der vorherigen Abfrage Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e909e-108">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="e909e-109">Die äußere SELECT-Anweisung konstruiert das <`Product`>-Element, das über ein **ProductID**-Attribut und zwei untergeordnete <`Price`>-Elemente verfügt.</span><span class="sxs-lookup"><span data-stu-id="e909e-109">The outer SELECT statement constructs the <`Product`> element that has a **ProductID** attribute and two <`Price`> child elements.</span></span>  
  
-   <span data-ttu-id="e909e-110">Die beiden inneren SELECT-Anweisungen konstruieren zwei <`Price`>-Elemente, von denen jedes über ein **PriceType**-Attribut verfügt, sowie XML-Code, der den Produktpreis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e909e-110">The two inner SELECT statements construct two <`Price`> elements, each with a **PriceType** attribute and XML that returns the product price.</span></span>  
  
-   <span data-ttu-id="e909e-111">Die XMLSCHEMA-Direktive in der äußeren SELECT-Anweisung generiert das XSD-Inlineschema, das die Form des resultierenden XML-Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e909e-111">The XMLSCHEMA directive in the outer SELECT statement generates the inline XSD schema that describes the shape of the resulting XML.</span></span>  
  
 <span data-ttu-id="e909e-112">Um die Abfrage interessant zu machen, können Sie die FOR XML-Abfrage schreiben und dann eine XQuery-Abfrage für das Ergebnis schreiben, um den XML-Code umzuformen, wie das in der folgenden Abfrage gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="e909e-112">To make the query interesting, you can write the FOR XML query and then write an XQuery against the result to reshape the XML, as shown in the following query:</span></span>  
  
```  
SELECT ProductID,   
 ( SELECT p2.ListPrice, p2.StandardCost  
   FROM Production.Product p2   
   WHERE Product.ProductID = p2.ProductID  
   FOR XML AUTO, ELEMENTS XSINIL, type ).query('  
                                   for $p in /p2/*  
                                   return   
                                    <Price PriceType = "{local-name($p)}">  
                                     { data($p) }  
                                    </Price>  
                                  ')  
FROM Production.Product  
WHERE ProductID = 520  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="e909e-113">Im oben gezeigten Beispiel wird die `query()`-Methode des `xml`-Datentyps verwendet, um den durch die innere FOR XML-Abfrage zurückgegebenen XML-Code abzufragen und das erwartete Ergebnis zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="e909e-113">The previous example uses the `query()` method of the `xml` data type to query the XML returned by the inner FOR XML query and construct the expected result.</span></span>  
  
 <span data-ttu-id="e909e-114">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e909e-114">This is the result:</span></span>  
  
```  
<Production.Product ProductID="520">  
  <Price PriceType="ListPrice">133.3400</Price>  
  <Price PriceType="StandardCost">98.7700</Price>  
</Production.Product>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e909e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e909e-115">See Also</span></span>  
 [<span data-ttu-id="e909e-116">Verwenden von geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e909e-116">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
