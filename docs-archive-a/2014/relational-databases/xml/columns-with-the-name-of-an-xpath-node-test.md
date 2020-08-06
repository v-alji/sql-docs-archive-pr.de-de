---
title: Spalten mit dem Namen eines XPath-Knotentests | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6555815d97308bed6e70d9fedb9858fc3abe7685
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697621"
---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a><span data-ttu-id="a49fe-102">Spalten mit Namen von XPath-Knotentests</span><span class="sxs-lookup"><span data-stu-id="a49fe-102">Columns with the Name of an XPath Node Test</span></span>
  <span data-ttu-id="a49fe-103">Wenn es sich bei dem Spaltennamen um einen der XPath-Knotentests handelt, wird der Inhalt zugeordnet, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a49fe-103">If the column name is one of the XPath node tests, the content is mapped as shown in the following table.</span></span> <span data-ttu-id="a49fe-104">Wenn der Spaltenname ein XPath-Knotentest ist, wird der Inhalt dem entsprechenden Knoten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a49fe-104">When the column name is an XPath node test, the content is mapped to the corresponding node.</span></span> <span data-ttu-id="a49fe-105">Wenn der SQL-Typ der Spalte `xml` ist, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a49fe-105">If the SQL type of the column is `xml`, an error is returned.</span></span>  
  
|<span data-ttu-id="a49fe-106">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a49fe-106">Column Name</span></span>|<span data-ttu-id="a49fe-107">Verhalten</span><span class="sxs-lookup"><span data-stu-id="a49fe-107">Behavior</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="a49fe-108">text()</span><span class="sxs-lookup"><span data-stu-id="a49fe-108">text()</span></span>|<span data-ttu-id="a49fe-109">Für eine Spalte mit dem Namen text() wird der Zeichenfolgenwert in dieser Spalte als Textknoten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a49fe-109">For a column with the name of text(), the string value in that column is added as a text node.</span></span>|  
|<span data-ttu-id="a49fe-110">comment()</span><span class="sxs-lookup"><span data-stu-id="a49fe-110">comment()</span></span>|<span data-ttu-id="a49fe-111">Für eine Spalte mit dem Namen comment() wird der Zeichenfolgenwert in dieser Spalte als XML-Kommentar hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a49fe-111">For a column with the name of comment(), the string value in that column is added as an XML comment.</span></span>|  
|<span data-ttu-id="a49fe-112">node()</span><span class="sxs-lookup"><span data-stu-id="a49fe-112">node()</span></span>|<span data-ttu-id="a49fe-113">Für eine Spalte mit dem Namen node() ist das Ergebnis mit dem eines Platzhalter-Spaltennamens (\*) identisch.</span><span class="sxs-lookup"><span data-stu-id="a49fe-113">For a column with the name of node(), the result is the same as it is when the column name is a wildcard character (\*).</span></span>|  
|<span data-ttu-id="a49fe-114">processing-instruction(name)</span><span class="sxs-lookup"><span data-stu-id="a49fe-114">processing-instruction(name)</span></span>|<span data-ttu-id="a49fe-115">Für eine Spalte mit dem Namen einer Verarbeitungsanweisung wird der Zeichenfolgenwert in dieser Spalte als PI-Wert für den Zielnamen der Verarbeitungsanweisung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a49fe-115">For a column with the name of a processing instruction, the string value in that column is added as the PI value for the processing instruction target name.</span></span>|  
  
 <span data-ttu-id="a49fe-116">Die folgende Abfrage zeigt die Verwendung der Knotentests als Spaltennamen an.</span><span class="sxs-lookup"><span data-stu-id="a49fe-116">The following query shows the use of the node tests as column names.</span></span> <span data-ttu-id="a49fe-117">Dabei werden Textknoten und Kommentare im XML-Ergebnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a49fe-117">It adds text nodes and comments in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="a49fe-118">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="a49fe-118">This is the result:</span></span>  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>S??nchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="a49fe-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a49fe-119">See Also</span></span>  
 [<span data-ttu-id="a49fe-120">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="a49fe-120">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
