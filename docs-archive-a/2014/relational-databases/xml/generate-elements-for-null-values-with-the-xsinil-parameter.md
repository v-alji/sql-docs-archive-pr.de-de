---
title: Generieren von NULL-Werten mithilfe des XSINIL-Parameters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 602de12b5aa9be8997fbd49a2f23e0b73444aac0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726742"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a><span data-ttu-id="4a8e0-102">Generieren von NULL-Werten mithilfe des XSINIL-Parameters</span><span class="sxs-lookup"><span data-stu-id="4a8e0-102">Generate Elements for NULL Values with the XSINIL Parameter</span></span>
  <span data-ttu-id="4a8e0-103">Von der **ELEMENTS** -Direktive wird XML konstruiert, in der jede Spalte zu einem Element im XML-Code zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="4a8e0-103">The **ELEMENTS** directive constructs XML in which each column value maps to an element in the XML.</span></span> <span data-ttu-id="4a8e0-104">Wenn der Spaltenwert NULL ist, wird kein Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4a8e0-104">If the column value is NULL, no element is added.</span></span> <span data-ttu-id="4a8e0-105">Durch Angeben des optionalen Parameters **XSINIL** für die ELEMENTS-Direktive können Sie anfordern, dass auch für den NULL-Wert ein Element erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4a8e0-105">By specifying the optional **XSINIL** parameter on the ELEMENTS directive, you can request that an element also be created for the NULL value.</span></span> <span data-ttu-id="4a8e0-106">In diesem Fall wird für ein Element das **xsi:nil** -Attribut, das auf TRUE festgelegt ist, für jeden NULL-Spaltenwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a8e0-106">In this case, an element that has the **xsi:nil** attribute set to TRUE is returned for each NULL column value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8e0-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a8e0-107">See Also</span></span>  
 [<span data-ttu-id="4a8e0-108">Verwenden des RAW-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="4a8e0-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
