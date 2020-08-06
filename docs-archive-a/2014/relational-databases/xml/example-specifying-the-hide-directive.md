---
title: 'Beispiel: Angeben der HIDE-Direktive | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- HIDE directive
ms.assetid: 87504d87-1cbd-412a-9041-47884b6efcec
author: rothja
ms.author: jroth
ms.openlocfilehash: 423ee36f679467c07a604b9754172f6e261971b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621394"
---
# <a name="example-specifying-the-hide-directive"></a><span data-ttu-id="70b2f-102">Beispiel: Angeben der HIDE-Direktive</span><span class="sxs-lookup"><span data-stu-id="70b2f-102">Example: Specifying the HIDE Directive</span></span>
  <span data-ttu-id="70b2f-103">In diesem Beispiel wird die Verwendung der **HIDE** -Direktive veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="70b2f-103">This example illustrates the use of the **HIDE** directive.</span></span> <span data-ttu-id="70b2f-104">Diese Direktive erweist sich als hilfreich, wenn die Abfrage ein Attribut zum Sortieren der Zeilen in der Universaltabelle zurückgeben soll, das Attribut jedoch nicht im endgültigen XML-Dokument enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="70b2f-104">This directive is useful when you want the query to return an attribute for ordering the rows in the universal table that is returned by the query, but you do not want that attribute in the final resulting XML document.</span></span>  
  
 <span data-ttu-id="70b2f-105">Diese Abfrage konstruiert diese XML-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="70b2f-105">This query constructs this XML:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
           <Summary> element from XML stored in CatalogDescription column  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="70b2f-106">Diese Abfrage generiert die gewünschte XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="70b2f-106">This query generates the XML you want.</span></span> <span data-ttu-id="70b2f-107">Die Abfrage identifiziert zwei Spaltengruppen, deren Spaltennamen die Tagwerte 1 und 2 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="70b2f-107">The query identifies two column groups having 1 and 2 as Tag values in the column names.</span></span>  
  
 <span data-ttu-id="70b2f-108">Diese Abfrage verwendet die [query()-Methode (xml-Datentyp)](/sql/t-sql/xml/query-method-xml-data-type) vom Datentyp **xml** , um die CatalogDescription-Spalte vom Typ **xml** abzufragen und daraus die Zusammenfassungsbeschreibung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="70b2f-108">This query uses the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) of the **xml** data type to query the CatalogDescription column of **xml** type in order to retrieve the summary description.</span></span> <span data-ttu-id="70b2f-109">Die Abfrage verwendet auch die [value()-Methode (xml-Datentyp)](/sql/t-sql/xml/value-method-xml-data-type) vom Datentyp **xml** , um den ProductModelID-Wert aus der CatalogDescription-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="70b2f-109">The query also uses the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) of the **xml** data type to retrieve the ProductModelID value from the CatalogDescription column.</span></span> <span data-ttu-id="70b2f-110">Dieser Wert wird benötigt, um die Rowsets des Ergebnisses zu sortieren, ist im XML-Ergebnis jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70b2f-110">This value is not required in the resulting XML, but is required to sort the resulting rowset.</span></span> <span data-ttu-id="70b2f-111">Deshalb beinhaltet der Spaltenname `[Summary!2!ProductModelID!HIDE]`die **HIDE** -Direktive.</span><span class="sxs-lookup"><span data-stu-id="70b2f-111">Therefore, the column name, `[Summary!2!ProductModelID!HIDE]`, includes the **HIDE** directive.</span></span> <span data-ttu-id="70b2f-112">Wenn diese Spalte nicht in der SELECT-Anweisung enthalten ist, müssen Sie das Rowset nach `[ProductModel!1!ProdModelID]` und `[Summary!2!SummaryDescription]` vom Datentyp **xml** sortieren und können die Spalte vom Typ **xml** in ORDER BY nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="70b2f-112">If this column is not included in the SELECT statement, you will have to sort the rowset by `[ProductModel!1!ProdModelID]` and `[Summary!2!SummaryDescription]` that is **xml** type and you cannot use the **xml** type column in ORDER BY.</span></span> <span data-ttu-id="70b2f-113">Daher wird die zusätzliche Spalte `[Summary!2!ProductModelID!HIDE]` hinzugefügt und in der ORDER BY-Klausel angegeben.</span><span class="sxs-lookup"><span data-stu-id="70b2f-113">Therefore, the additional `[Summary!2!ProductModelID!HIDE]` column is added and is then specified in the ORDER BY clause.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID     as [ProductModel!1!ProdModelID],  
        Name               as [ProductModel!1!Name],  
        NULL               as [Summary!2!ProductModelID!hide],  
        NULL               as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
        CatalogDescription.value('  
         declare namespace PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
       (/PD:ProductDescription/@ProductModelID)[1]', 'int'),  
        CatalogDescription.query('  
         declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
         /pd:ProductDescription/pd:Summary')  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],[Summary!2!ProductModelID!hide]  
FOR XML EXPLICIT  
go  
```  
  
 <span data-ttu-id="70b2f-114">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="70b2f-114">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <pd:Summary xmlns:pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription" xmlns="">  
        <p1:p xmlns:p1="http://www.w3.org/1999/xhtml">Our top-of-the-line competition mountain bike. Performance-enhancing options include the innovative HL Frame, super-smooth front suspension, and traction for all terrain. </p1:p>  
      </pd:Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70b2f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70b2f-115">See Also</span></span>  
 [<span data-ttu-id="70b2f-116">Verwenden des EXPLICIT-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="70b2f-116">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
