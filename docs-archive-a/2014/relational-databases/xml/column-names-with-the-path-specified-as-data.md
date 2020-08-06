---
title: Spaltennamen, deren Pfad als data() angegeben ist | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
author: rothja
ms.author: jroth
ms.openlocfilehash: 61aa7f85c7ee2358ddcf99f81c87c1295fac8fb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608438"
---
# <a name="column-names-with-the-path-specified-as-data"></a><span data-ttu-id="2c409-102">Spaltennamen, deren Pfad als data() angegeben ist</span><span class="sxs-lookup"><span data-stu-id="2c409-102">Column Names with the Path Specified as data()</span></span>
  <span data-ttu-id="2c409-103">Wenn der als Spaltenname angegebene Pfad "data()" ist, wird der Wert im generierten XML-Code als unteilbarer Wert behandelt.</span><span class="sxs-lookup"><span data-stu-id="2c409-103">If the path specified as column name is "data()", the value is treated as an atomic value in the generated XML.</span></span> <span data-ttu-id="2c409-104">Dem XML-Code wird ein Leerzeichen hinzugefügt, wenn das nächste Element in der Serialisierung ebenfalls ein atomarer Wert ist.</span><span class="sxs-lookup"><span data-stu-id="2c409-104">A space character is added to the XML if the next item in the serialization is also an atomic value.</span></span> <span data-ttu-id="2c409-105">Dies erweist sich beim Erstellen von Listenelementen und Attributen als nützlich.</span><span class="sxs-lookup"><span data-stu-id="2c409-105">This is useful when you are creating list typed element and attribute values.</span></span> <span data-ttu-id="2c409-106">Die folgende Abfrage ruft die Produktmodell-ID, den Namen des Produktmodells sowie die Liste der Produkte dieses Produktmodells ab.</span><span class="sxs-lookup"><span data-stu-id="2c409-106">The following query retrieves the product model ID, name, and list of products in that product model.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="2c409-107">Das geschachtelte SELECT ruft eine Liste mit Produkt-IDs ab.</span><span class="sxs-lookup"><span data-stu-id="2c409-107">The nested SELECT retrieves a list of product IDs.</span></span> <span data-ttu-id="2c409-108">Als Spaltenname für die Produkt-IDs wird dabei "data()" angegeben.</span><span class="sxs-lookup"><span data-stu-id="2c409-108">It specifies "data()" as the column name for product IDs.</span></span> <span data-ttu-id="2c409-109">Da der PATH-Modus eine leere Zeichenfolge für den Namen des Zeilenelements angibt, wird kein Zeilenelement generiert.</span><span class="sxs-lookup"><span data-stu-id="2c409-109">Because PATH mode specifies an empty string for the row element name, there is no row element generated.</span></span> <span data-ttu-id="2c409-110">Stattdessen werden die Werte als die einem ProductIDs-Attribut zugewiesene Werte des <`ProductModelData`>-Zeilenelements des übergeordneten SELECT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2c409-110">Instead, the values are returned as assigned to a ProductIDs attribute of the <`ProductModelData`> row element of the parent SELECT.</span></span> <span data-ttu-id="2c409-111">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="2c409-111">This is the result:</span></span>  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## <a name="see-also"></a><span data-ttu-id="2c409-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c409-112">See Also</span></span>  
 [<span data-ttu-id="2c409-113">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="2c409-113">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
