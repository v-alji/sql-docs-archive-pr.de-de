---
title: 'Beispiel: Abrufen von Binärdaten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving binary data example
ms.assetid: 5cea5d49-58ac-403a-a933-c4fd91de400b
author: rothja
ms.author: jroth
ms.openlocfilehash: 516c7d91d0a6ebac7366b4bb3cbafe5d05aaa232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622454"
---
# <a name="example-retrieving-binary-data"></a><span data-ttu-id="96ecf-102">Beispiel: Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="96ecf-102">Example: Retrieving Binary Data</span></span>
  <span data-ttu-id="96ecf-103">Die folgende Abfrage gibt das Produktfoto zurück, das in einer Spalte des `varbinary(max)`-Typs gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="96ecf-103">The following query returns the product photo stored in a `varbinary(max)` type column.</span></span> <span data-ttu-id="96ecf-104">Durch die Angabe der Option `BINARY BASE64` in der Abfrage werden die Binärdaten im Base64-codierten Format zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96ecf-104">The `BINARY BASE64` option is specified in the query to return the binary data in base64-encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96ecf-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="96ecf-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductPhotoID, ThumbNailPhoto  
FROM Production.ProductPhoto  
WHERE ProductPhotoID=1  
FOR XML RAW, BINARY BASE64 ;  
GO  
```  
  
 <span data-ttu-id="96ecf-106">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="96ecf-106">This is the result:</span></span>  
  
```  
<row ProductModelID="1" ThumbNailPhoto="base64 encoded binary data"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96ecf-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96ecf-107">See Also</span></span>  
 [<span data-ttu-id="96ecf-108">Verwenden des RAW-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="96ecf-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
