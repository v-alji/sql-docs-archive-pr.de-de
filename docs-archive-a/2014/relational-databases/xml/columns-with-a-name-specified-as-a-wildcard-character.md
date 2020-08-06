---
title: Spalten mit als Platzhalterzeichen angegebenen Namen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: d9551df1-5bb4-4c0b-880a-5bb049834884
author: rothja
ms.author: jroth
ms.openlocfilehash: 4b363baf8792628c2e17b1a695c19a6a338f4fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617836"
---
# <a name="columns-with-a-name-specified-as-a-wildcard-character"></a><span data-ttu-id="15d89-102">Spalten mit als Platzhalterzeichen angegebenen Namen</span><span class="sxs-lookup"><span data-stu-id="15d89-102">Columns with a Name Specified as a Wildcard Character</span></span>
  <span data-ttu-id="15d89-103">Wenn der angegebene Spaltenname aus einem Platzhalterzeichen (\*) besteht, wird der Inhalt der betroffenen Spalte so eingefügt, als wäre kein Spaltenname angegeben.</span><span class="sxs-lookup"><span data-stu-id="15d89-103">If the column name specified is a wildcard character (\*), the content of that column is inserted as if there is no column name specified.</span></span> <span data-ttu-id="15d89-104">Wenn die Spalte nicht vom Typ `xml` ist, wird der Inhalt der Spalte als Textknoten eingefügt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="15d89-104">If this column is a non-`xml` type column, the column content is inserted as a text node, as shown in the following example:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
       FirstName "*",   
       MiddleName "*",   
       LastName "*"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
    ON E.BusinessEntityID = P.BusinessEntityID  
WHERE E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="15d89-105">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="15d89-105">This is the result:</span></span>  
  
 `<row EmpID="1">KenJS??nchez</row>`  
  
 <span data-ttu-id="15d89-106">Wenn die Spalte vom Typ `xml` ist, wird die entsprechende XML-Struktur eingefügt.</span><span class="sxs-lookup"><span data-stu-id="15d89-106">If the column is of `xml` type, the corresponding XML tree is inserted.</span></span> <span data-ttu-id="15d89-107">Die folgende Abfrage gibt beispielsweise "\*" als Name der Spalte an, die den XML-Code enthält, der von der XQuery für die Instructions-Spalte zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="15d89-107">For example, the following query specifies "\*" for the column name that contains the XML returned by the XQuery against the Instructions column.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
                /MI:root/MI:Location   
              ') as "*"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH;   
GO  
```  
  
 <span data-ttu-id="15d89-108">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="15d89-108">This is the result.</span></span> <span data-ttu-id="15d89-109">Der von der XQuery zurückgegebene XML-Code wird ohne Wrapperelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="15d89-109">The XML returned by XQuery is inserted without a wrapping element.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location LocationID="10">...</MI:Location>`  
  
 `<MI:Location LocationID="20">...</MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="15d89-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15d89-110">See Also</span></span>  
 [<span data-ttu-id="15d89-111">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="15d89-111">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
