---
title: POWER (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- POWER function
ms.assetid: db48ae65-bfa6-4db1-8d3c-d0d4f8a399bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1f5742f482ae52620ec11d95b84cb3d06199fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618780"
---
# <a name="power-ssis-expression"></a><span data-ttu-id="4c660-102">POWER (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="4c660-102">POWER (SSIS Expression)</span></span>
  <span data-ttu-id="4c660-103">Gibt das Ergebnis eines in eine Potenz erhobenen numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="4c660-103">Returns the result of raising a numeric expression to a power.</span></span> <span data-ttu-id="4c660-104">Der power-Parameter muss zu einer ganzen Zahl ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="4c660-104">The power parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c660-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c660-105">Syntax</span></span>  
  
```  
  
POWER(numeric_expression,power)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c660-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="4c660-106">Arguments</span></span>  
 <span data-ttu-id="4c660-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="4c660-107">*numeric_expression*</span></span>  
 <span data-ttu-id="4c660-108">Ein gültiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c660-108">Is a valid numeric expression.</span></span>  
  
 <span data-ttu-id="4c660-109">*power*</span><span class="sxs-lookup"><span data-stu-id="4c660-109">*power*</span></span>  
 <span data-ttu-id="4c660-110">Ein gültiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c660-110">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4c660-111">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="4c660-111">Result Types</span></span>  
 <span data-ttu-id="4c660-112">DT_R8</span><span class="sxs-lookup"><span data-stu-id="4c660-112">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c660-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4c660-113">Remarks</span></span>  
 <span data-ttu-id="4c660-114">Die Argumente *numeric_expression* und *power* werden in den „DT_R8“-Datentyp umgewandelt, bevor der Potenzwert berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="4c660-114">The *numeric_expression* and *power* arguments are cast to the DT_R8 data type before the power is computed.</span></span> <span data-ttu-id="4c660-115">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4c660-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="4c660-116">Falls *numeric_expression* in 0 (null) ausgewertet wird und *power* negativ ist, gibt die Ausdrucksauswertung einen Fehler zurück und legt das zurückgegebene Ergebnis auf NULL fest.</span><span class="sxs-lookup"><span data-stu-id="4c660-116">If *numeric_expression* evaluates to zero and *power* is negative, the expression evaluator returns an error and sets the return result to null.</span></span>  
  
 <span data-ttu-id="4c660-117">Falls *numeric_expression* oder *power* in unbestimmte Ergebnisse ausgewertet werden, wird als Ergebnis NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c660-117">If *numeric_expression* or *power* evaluate to indeterminate results, the return result is null.</span></span>  
  
 <span data-ttu-id="4c660-118">Das *power* -Argument kann eine Bruchzahl sein.</span><span class="sxs-lookup"><span data-stu-id="4c660-118">The *power* argument can be a fraction.</span></span> <span data-ttu-id="4c660-119">Sie können z. B. 0.5 als Potenzwert verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c660-119">For example, you can use the value 0.5 as the power.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4c660-120">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4c660-120">Expression Examples</span></span>  
 <span data-ttu-id="4c660-121">In diesem Beispiel wird ein numerisches Literal verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c660-121">This example uses a numeric literal.</span></span> <span data-ttu-id="4c660-122">Die Funktion potenziert 4 mit 3 und gibt 64 zurück.</span><span class="sxs-lookup"><span data-stu-id="4c660-122">The function raises 4 to the power of 3 and returns 64.</span></span>  
  
```  
POWER(4,3)  
```  
  
 <span data-ttu-id="4c660-123">In diesem Beispiel wird die **Length** -Spalte und die **DimensionCount** -Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c660-123">This example uses the **Length** column and the **DimensionCount** variable.</span></span> <span data-ttu-id="4c660-124">Falls **Length** gleich 8 ist und **DimensionCount** gleich 2, wird als Ergebnis 64 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c660-124">If **Length** is 8, and **DimensionCount** is 2, the return result is 64.</span></span>  
  
```  
POWER(Length, @DimensionCount)   
```  
  
## <a name="see-also"></a><span data-ttu-id="4c660-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c660-125">See Also</span></span>  
 [<span data-ttu-id="4c660-126">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="4c660-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
