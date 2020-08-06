---
title: 'Beispiel: Abfragen von Spalten des Typs XML | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: rothja
ms.author: jroth
ms.openlocfilehash: 0eedfa5a5a265f3715a76a6ca80d489bbec199bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608430"
---
# <a name="example-querying-xmltype-columns"></a><span data-ttu-id="ba02c-102">Beispiel: Abfragen von Spalten des Typs XML</span><span class="sxs-lookup"><span data-stu-id="ba02c-102">Example: Querying XMLType Columns</span></span>
  <span data-ttu-id="ba02c-103">Die folgende Abfrage schließt Spalten vom Typ `xml` ein.</span><span class="sxs-lookup"><span data-stu-id="ba02c-103">The following query includes columns of `xml` type.</span></span> <span data-ttu-id="ba02c-104">Die Abfrage ruft die Produktmodell-ID, den Namen und die Produktionsschritte am ersten Standort aus der `Instructions`-Spalte vom Typ `xml` ab.</span><span class="sxs-lookup"><span data-stu-id="ba02c-104">The query retrieves product model ID, name, and manufacturing steps at the first location from the `Instructions` column of the `xml` type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba02c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba02c-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 <span data-ttu-id="ba02c-106">Im Folgenden wird das Ergebnis gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba02c-106">The following is the result.</span></span> <span data-ttu-id="ba02c-107">Beachten Sie, dass die Tabelle nur für einige Produktmodelle Fertigungsanweisungen speichert.</span><span class="sxs-lookup"><span data-stu-id="ba02c-107">Note that the table stores manufacturing instructions for only some product models.</span></span> <span data-ttu-id="ba02c-108">Die Fertigungsschritte werden als Unterelemente des <`ProductModelData`>-Elements im Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ba02c-108">The manufacturing steps are returned as subelements of the <`ProductModelData`> element in the result.</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 <span data-ttu-id="ba02c-109">Wenn in der Abfrage ein Spaltenname für die durch die XQuery-Abfrage zurückgegebenen XML-Daten angegeben wird (wie in der folgenden `SELECT` -Anweisung angegeben), werden die Produktionsschritte von dem Element umschlossen, das den angegebenen Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="ba02c-109">If the query specifies a column name for the XML returned by the XQuery, as specified in the following `SELECT` statement, the manufacturing steps are wrapped in the element that has the specified name.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 <span data-ttu-id="ba02c-110">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ba02c-110">This is the result:</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 <span data-ttu-id="ba02c-111">In der folgenden Abfrage wird die `ELEMENTS` -Direktive angegeben.</span><span class="sxs-lookup"><span data-stu-id="ba02c-111">The following query specifies the `ELEMENTS` directive.</span></span> <span data-ttu-id="ba02c-112">Deshalb ist das zurückgegebene Ergebnis elementzentriert.</span><span class="sxs-lookup"><span data-stu-id="ba02c-112">Therefore, the result returned is element-centric.</span></span> <span data-ttu-id="ba02c-113">Die Option `XSINIL`, die zusammen mit der `ELEMENTS`-Direktive angegeben wird, gibt selbst dann <`ManuSteps`>-Elemente zurück, wenn die entsprechende Spalte im Rowset NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ba02c-113">The `XSINIL` option specified with the `ELEMENTS` directive returns the <`ManuSteps`> elements, even if the corresponding column in the rowset is NULL.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 <span data-ttu-id="ba02c-114">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ba02c-114">This is the result:</span></span>  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba02c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba02c-115">See Also</span></span>  
 [<span data-ttu-id="ba02c-116">Verwenden des RAW-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="ba02c-116">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
