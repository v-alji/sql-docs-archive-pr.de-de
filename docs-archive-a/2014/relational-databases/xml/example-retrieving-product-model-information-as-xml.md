---
title: 'Beispiel: Abrufen von Produktmodellinformationen als XML | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving XML information example
ms.assetid: 3828b4ca-3ab2-444f-9c58-8be6e7f064a6
author: rothja
ms.author: jroth
ms.openlocfilehash: d580f53c4b5185a8b1b1467c75a08fc6929bdcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618574"
---
# <a name="example-retrieving-product-model-information-as-xml"></a><span data-ttu-id="0ad9a-102">Beispiel: Abrufen von Produktmodellinformationen als XML</span><span class="sxs-lookup"><span data-stu-id="0ad9a-102">Example: Retrieving Product Model Information as XML</span></span>
  <span data-ttu-id="0ad9a-103">Die folgende Abfrage gibt Produktmodellinformationen zurück.</span><span class="sxs-lookup"><span data-stu-id="0ad9a-103">The following query returns product model information.</span></span> <span data-ttu-id="0ad9a-104">`RAW` -Modus wird in der `FOR XML` -Klausel angegeben.</span><span class="sxs-lookup"><span data-stu-id="0ad9a-104">`RAW` mode is specified in the `FOR XML` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ad9a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ad9a-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW;  
GO  
```  
  
 <span data-ttu-id="0ad9a-106">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="0ad9a-106">This is the partial result:</span></span>  
  
 `<row ProductModelID="122" Name="All-Purpose Bike Stand" />`  
  
 `<row ProductModelID="119" Name="Bike Wash" />`  
  
 <span data-ttu-id="0ad9a-107">Sie können elementzentrierte XML-Daten abrufen, indem Sie die `ELEMENTS` -Direktive angeben.</span><span class="sxs-lookup"><span data-stu-id="0ad9a-107">You can retrieve element-centric XML by specifying the `ELEMENTS` directive.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="0ad9a-108">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="0ad9a-108">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</row>  
<row>  
  <ProductModelID>119</ProductModelID>  
  <Name>Bike Wash</Name>  
</row>  
```  
  
 <span data-ttu-id="0ad9a-109">Optional können Sie die `TYPE`-Direktive angeben, um die Ergebnisse als `xml`-Datentyp abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0ad9a-109">You can optionally specify the `TYPE` directive to retrieve the results as `xml` type.</span></span> <span data-ttu-id="0ad9a-110">Die `TYPE` -Direktive ändert nicht den Inhalt der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="0ad9a-110">The `TYPE` directive does not change the content of the results.</span></span> <span data-ttu-id="0ad9a-111">Nur der Datentyp der Ergebnisse wird geändert.</span><span class="sxs-lookup"><span data-stu-id="0ad9a-111">Only the data type of the results is affected.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, TYPE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ad9a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ad9a-112">See Also</span></span>  
 [<span data-ttu-id="0ad9a-113">Verwenden des RAW-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="0ad9a-113">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
