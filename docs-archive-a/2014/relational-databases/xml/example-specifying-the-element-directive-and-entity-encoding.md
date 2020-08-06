---
title: 'Beispiel: Angeben der ELEMENT-Direktive und Entitätscodierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
- entity encoding [XML]
ms.assetid: 50cda5c1-7293-4080-93b3-872e3b8d484e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ba4e419d31aa7c02cc2dc8f19a3350c233f042b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695473"
---
# <a name="example-specifying-the-element-directive-and-entity-encoding"></a><span data-ttu-id="6a967-102">Beispiel: Angeben der ELEMENT-Anweisung und Entitätscodierung</span><span class="sxs-lookup"><span data-stu-id="6a967-102">Example: Specifying the ELEMENT Directive and Entity Encoding</span></span>
  <span data-ttu-id="6a967-103">Dieses Beispiel veranschaulicht den Unterschied zwischen der **ELEMENT** - und der **XML** -Direktive.</span><span class="sxs-lookup"><span data-stu-id="6a967-103">This example illustrates the difference between the **ELEMENT** and **XML** directives.</span></span> <span data-ttu-id="6a967-104">Bei der **ELEMENT** -Direktive werden die Daten in Entitäten geändert, während dies bei der **XML** -Direktive nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="6a967-104">The **ELEMENT** directive entitizes the data, but the **XML** directive does not.</span></span> <span data-ttu-id="6a967-105">Dem \<Summary>-Element wird in der Abfrage XML zugewiesen: `<Summary>This is summary description</Summary>`.</span><span class="sxs-lookup"><span data-stu-id="6a967-105">The \<Summary> element is assigned XML, `<Summary>This is summary description</Summary>`, in the query.</span></span>  
  
 <span data-ttu-id="6a967-106">Angenommen, die folgende Abfrage wird ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="6a967-106">Consider this query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription!ELEMENT]  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        NULL,  
       '<Summary>This is summary description</Summary>'  
FROM   Production.ProductModel  
WHERE  ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="6a967-107">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="6a967-107">This is the result.</span></span> <span data-ttu-id="6a967-108">Die Zusammenfassungsbeschreibung wird im Ergebnis in eine Entität geändert.</span><span class="sxs-lookup"><span data-stu-id="6a967-108">The summary description is entitized in the result.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription><Summary>This is summary description</Summary></SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="6a967-109">Wenn Sie nun im Spaltennamen die **XML** -Direktive angeben, also `Summary!2!SummaryDescription!XML`statt der **ELEMENT** -Direktive, erhalten Sie eine zusammenfassende Beschreibung, ohne dass die Daten in Entitäten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6a967-109">Now, if you specify the **XML** directive in the column name, `Summary!2!SummaryDescription!XML`, instead of the **ELEMENT** directive, you will receive the summary description without entitization.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <Summary>This is summary description</Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="6a967-110">Die folgende Abfrage weist keinen statischen XML-Wert zu, sondern verwendet die **query()** -Methode vom **XML** -Typ, um die Produktmodell-Zusammenfassungsbeschreibung aus der CatalogDescription-Spalte vom **XML** -Typ abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6a967-110">Instead of assigning a static XML value, the following query uses the **query()** method of the **xml** type to retrieve the product model summary description from the CatalogDescription column of **xml** type.</span></span> <span data-ttu-id="6a967-111">Da bekannt ist, dass das Ergebnis vom Typ **xml** ist, werden die Daten nicht in Entitäten geändert.</span><span class="sxs-lookup"><span data-stu-id="6a967-111">Because the result is known to be of **xml** type, no entitization is applied.</span></span>  
  
```  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
       (SELECT CatalogDescription.query('  
            declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
          /pd:ProductDescription/pd:Summary'))  
FROM     Production.ProductModel  
WHERE    CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],Tag  
FOR XML EXPLICIT  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a967-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a967-112">See Also</span></span>  
 [<span data-ttu-id="6a967-113">Verwenden des EXPLICIT-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="6a967-113">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
