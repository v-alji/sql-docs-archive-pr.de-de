---
title: CEILING (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- smallest integer great than or equal to expression
- CEILING function [SSIS]
ms.assetid: c35bd4ee-1ab6-46ab-89a7-cf771527faa2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd2f9f455226925d6bf00842e80a8713e6c72771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622788"
---
# <a name="ceiling-ssis-expression"></a><span data-ttu-id="c5a19-102">CEILING (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="c5a19-102">CEILING (SSIS Expression)</span></span>
  <span data-ttu-id="c5a19-103">Gibt die kleinste ganze Zahl zurück, die größer oder gleich einem numerischen Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="c5a19-103">Returns the smallest integer that is greater than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5a19-104">Syntax</span></span>  
  
```  
  
CEILING(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5a19-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c5a19-105">Arguments</span></span>  
 <span data-ttu-id="c5a19-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="c5a19-106">*numeric_expression*</span></span>  
 <span data-ttu-id="c5a19-107">Ein gültiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c5a19-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c5a19-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="c5a19-108">Result Types</span></span>  
 <span data-ttu-id="c5a19-109">Der Datentyp des numerischen Ausdrucks, der an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5a19-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5a19-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c5a19-110">Remarks</span></span>  
 <span data-ttu-id="c5a19-111">CEILING gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="c5a19-111">CEILING returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c5a19-112">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c5a19-112">Expression Examples</span></span>  
 <span data-ttu-id="c5a19-113">In diesen Beispielen wird die CEILING-Funktion auf positive und negative Werte und auf Null angewendet.</span><span class="sxs-lookup"><span data-stu-id="c5a19-113">These examples apply the CEILING function to positive, negative, and zero values.</span></span>  
  
```  
CEILING(123.74)  
```  
  
 <span data-ttu-id="c5a19-114">Gibt 124,00 zurück.</span><span class="sxs-lookup"><span data-stu-id="c5a19-114">Returns 124.00</span></span>  
  
```  
CEILING(-124.27)  
```  
  
 <span data-ttu-id="c5a19-115">Gibt -124.00 zurück.</span><span class="sxs-lookup"><span data-stu-id="c5a19-115">Returns -124.00</span></span>  
  
```  
CEILING(0.00)  
```  
  
 <span data-ttu-id="c5a19-116">Gibt 0.00 zurück.</span><span class="sxs-lookup"><span data-stu-id="c5a19-116">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a19-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5a19-117">See Also</span></span>  
 <span data-ttu-id="c5a19-118">[FLOOR &#40;SSIS-Ausdruck&#41;](floor-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5a19-118">[FLOOR &#40;SSIS Expression&#41;](floor-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c5a19-119">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="c5a19-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
