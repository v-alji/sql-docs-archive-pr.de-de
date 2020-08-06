---
title: Auffüllen von Zeichenfolgen (SSIS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- padding strings [Integration Services]
- expressions [Integration Services], string padding
- string padding
ms.assetid: d3fed73d-e0d4-4c67-9355-fb7083a72dd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3985fd1b2f29260e2313a761797d2528f5d0e328
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701366"
---
# <a name="string-padding-ssis"></a><span data-ttu-id="2fe45-102">Auffüllen von Zeichenfolgen (SSIS)</span><span class="sxs-lookup"><span data-stu-id="2fe45-102">String Padding (SSIS)</span></span>
  <span data-ttu-id="2fe45-103">Die Ausdrucksauswertung überprüft nicht, ob eine Zeichenfolge führende und nachfolgende Leerzeichen enthält, und Zeichenfolgen werden vor dem Vergleichen nicht auf die gleiche Länge aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2fe45-103">The expression evaluator does not check if a string contains leading and trailing spaces, and it does not pad strings to make them the same length before it compares them.</span></span> <span data-ttu-id="2fe45-104">Falls Ausdrücke das Auffüllen von Zeichenfolgen erfordern, können Sie mit dem +-Operator Spaltenwerte und leere Zeichenfolgen verketten.</span><span class="sxs-lookup"><span data-stu-id="2fe45-104">If expressions requires string padding, you can use the + operator to concatenate column values and blank strings.</span></span> <span data-ttu-id="2fe45-105">Weitere Informationen finden Sie unter [+ &#40;Verketten, SSIS-Ausdruck&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2fe45-105">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="2fe45-106">Wenn Sie andererseits Leerzeichen entfernen möchten, stellt die Ausdrucksauswertung die Funktionen LTRIM, RTRIM und TRIM bereit, die führende und/oder nachfolgende Leerzeichen entfernen.</span><span class="sxs-lookup"><span data-stu-id="2fe45-106">On the other hand, if you want to remove spaces, the expression evaluator provides the LTRIM, RTRIM, and TRIM functions, which remove leading or trailing spaces, or both.</span></span> <span data-ttu-id="2fe45-107">Weitere Informationen finden Sie unter [LTRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS-Ausdruck&#41;](rtrim-ssis-expression.md) und [TRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2fe45-107">For more information, see [LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md), and [TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fe45-108">Die LEN-Funktion berücksichtigt beim Zählen führende und nachfolgende Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="2fe45-108">The LEN function includes leading and trailing blanks in its count.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="2fe45-109">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="2fe45-109">Related Content</span></span>  
 <span data-ttu-id="2fe45-110">Technischer Artikel, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), auf pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="2fe45-110">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), on pragmaticworks.com</span></span>  
  
  
