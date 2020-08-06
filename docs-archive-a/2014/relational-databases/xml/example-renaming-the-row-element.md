---
title: 'Beispiel: Umbenennen des &lt;row&gt;-Elements | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, renaming <row> example
ms.assetid: b042292a-0b6e-40a3-b254-71c06e626706
author: rothja
ms.author: jroth
ms.openlocfilehash: 39375fa125f451f21d936b3a6897b93928fa2f02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608429"
---
# <a name="example-renaming-the-ltrowgt-element"></a><span data-ttu-id="619d2-102">Beispiel: Umbenennen des &lt;row&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="619d2-102">Example: Renaming the &lt;row&gt; Element</span></span>
  <span data-ttu-id="619d2-103">Für jede Zeile im Resultset generiert der RAW-Modus ein `<row>`-Element.</span><span class="sxs-lookup"><span data-stu-id="619d2-103">For each row in the result set, the RAW mode generates an element `<row>`.</span></span> <span data-ttu-id="619d2-104">Sie können optional einen anderen Namen für dieses Element angeben, indem Sie ein optionales Argument für den RAW-Modus angeben, wie es in der folgenden Abfrage gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="619d2-104">You can optionally specify another name for this element by specifying an optional argument to the RAW mode, as shown in this query.</span></span> <span data-ttu-id="619d2-105">Die Abfrage gibt ein <`ProductModel`>-Element für jede Zeile im Rowset zurück.</span><span class="sxs-lookup"><span data-stu-id="619d2-105">The query returns a <`ProductModel`> element for each row in the rowset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="619d2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="619d2-106">Example</span></span>  
  
```  
SELECT ProductModelID, Name   
FROM Production.ProductModel  
WHERE ProductModelID=122  
FOR XML RAW ('ProductModel'), ELEMENTS  
GO  
```  
  
 <span data-ttu-id="619d2-107">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="619d2-107">This is the result.</span></span> <span data-ttu-id="619d2-108">Da der Abfrage die `ELEMENTS` -Direktive hinzugefügt wurde, ist das Ergebnis elementzentriert.</span><span class="sxs-lookup"><span data-stu-id="619d2-108">Because the `ELEMENTS` directive is added in the query, the result is element-centric.</span></span>  
  
```  
<ProductModel>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</ProductModel>   
```  
  
## <a name="see-also"></a><span data-ttu-id="619d2-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="619d2-109">See Also</span></span>  
 [<span data-ttu-id="619d2-110">Verwenden des RAW-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="619d2-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
