---
title: FLOOR (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b638c9a7215d120c562e416cdecee463f031ad2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617203"
---
# <a name="floor-ssis-expression"></a><span data-ttu-id="c5bac-102">FLOOR (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="c5bac-102">FLOOR (SSIS Expression)</span></span>
  <span data-ttu-id="c5bac-103">Gibt die größte ganze Zahl zurück, die kleiner oder gleich einem numerischen Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="c5bac-103">Returns the largest integer that is less than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5bac-104">Syntax</span></span>  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5bac-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c5bac-105">Arguments</span></span>  
 <span data-ttu-id="c5bac-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="c5bac-106">*numeric_expression*</span></span>  
 <span data-ttu-id="c5bac-107">Ein gültiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c5bac-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c5bac-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="c5bac-108">Result Types</span></span>  
 <span data-ttu-id="c5bac-109">Der numerische Datentyp des expression-Arguments.</span><span class="sxs-lookup"><span data-stu-id="c5bac-109">The numeric data type of the argument expression.</span></span> <span data-ttu-id="c5bac-110">Das Ergebnis ist der ganzzahlige Teil des berechneten Werts mit dem gleichen Datentyp wie *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="c5bac-110">The result is the integer portion of the calculated value in the same data type as *numeric_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5bac-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c5bac-111">Remarks</span></span>  
 <span data-ttu-id="c5bac-112">FLOOR gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="c5bac-112">FLOOR returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c5bac-113">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c5bac-113">Expression Examples</span></span>  
 <span data-ttu-id="c5bac-114">In diesen Beispielen wird die FLOOR-Funktion auf positive und negative Werte und auf Null angewendet.</span><span class="sxs-lookup"><span data-stu-id="c5bac-114">These examples apply the FLOOR function to positive, negative, and zero values.</span></span>  
  
```  
FLOOR(123.45)  
```  
  
 <span data-ttu-id="c5bac-115">Gibt 123.00 zurück.</span><span class="sxs-lookup"><span data-stu-id="c5bac-115">Returns 123.00</span></span>  
  
```  
FLOOR(-123.45)  
```  
  
 <span data-ttu-id="c5bac-116">Gibt -124.00 zurück.</span><span class="sxs-lookup"><span data-stu-id="c5bac-116">Returns -124.00</span></span>  
  
```  
FLOOR(0.00)  
```  
  
 <span data-ttu-id="c5bac-117">Gibt 0.00 zurück.</span><span class="sxs-lookup"><span data-stu-id="c5bac-117">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bac-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5bac-118">See Also</span></span>  
 <span data-ttu-id="c5bac-119">[CEILING &#40;SSIS-Ausdruck&#41;](ceiling-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c5bac-119">[CEILING &#40;SSIS Expression&#41;](ceiling-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c5bac-120">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="c5bac-120">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
