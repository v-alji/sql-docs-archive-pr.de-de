---
title: Spalten ohne Namen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: 43d1cbce816e4666e6dab52fdffe5850e65740e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697618"
---
# <a name="columns-without-a-name"></a><span data-ttu-id="1b861-102">Spalten ohne Namen</span><span class="sxs-lookup"><span data-stu-id="1b861-102">Columns without a Name</span></span>
  <span data-ttu-id="1b861-103">Spalten ohne Namen werden als Inlinespalten betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1b861-103">Any column without a name will be inlined.</span></span> <span data-ttu-id="1b861-104">Beispielsweise werden namenlose Spalten für berechnete Spalten oder geschachtelte skalare Abfragen, die keinen Spaltenalias angeben, generiert.</span><span class="sxs-lookup"><span data-stu-id="1b861-104">For example, computed columns or nested scalar queries that do not specify column alias will generate columns without any name.</span></span> <span data-ttu-id="1b861-105">Wenn die Spalte vom Typ `xml` ist, wird der Inhalt dieser Datentypinstanz eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1b861-105">If the column is of `xml` type, the content of that data type instance is inserted.</span></span> <span data-ttu-id="1b861-106">Anderenfalls wird der Inhalt der Spalte als Textknoten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1b861-106">Otherwise, the column content is inserted as a text node.</span></span>  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 <span data-ttu-id="1b861-107">Erstellen Sie diesen XML-Code.</span><span class="sxs-lookup"><span data-stu-id="1b861-107">Produce this XML.</span></span> <span data-ttu-id="1b861-108">Standardmäßig wird im XML-Ergebnis für jede Zeile des Rowsets ein <`row`>-Element generiert.</span><span class="sxs-lookup"><span data-stu-id="1b861-108">By default, for each row in the rowset, a <`row`> element is generated in the resulting XML.</span></span> <span data-ttu-id="1b861-109">Dies entspricht dem RAW-Modus.</span><span class="sxs-lookup"><span data-stu-id="1b861-109">This is the same as RAW mode.</span></span>  
  
 `<row>4</row>`  
  
 <span data-ttu-id="1b861-110">Die folgende Abfrage gibt ein Rowset mit drei Spalten zurück.</span><span class="sxs-lookup"><span data-stu-id="1b861-110">The following query returns a three-column rowset.</span></span> <span data-ttu-id="1b861-111">Die dritte, namenlose Spalte enthält XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="1b861-111">The third column without a name has XML data.</span></span> <span data-ttu-id="1b861-112">Der PATH-Modus fügt eine Instanz des XML-Typs ein.</span><span class="sxs-lookup"><span data-stu-id="1b861-112">The PATH mode inserts an instance of the xml type.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 <span data-ttu-id="1b861-113">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="1b861-113">This is the partial result:</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="1b861-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b861-114">See Also</span></span>  
 [<span data-ttu-id="1b861-115">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="1b861-115">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
