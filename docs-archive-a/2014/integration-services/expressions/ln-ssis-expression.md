---
title: LN (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LN function
- natural logarithm of expression [Integration Services]
ms.assetid: 55d7b657-b5fd-4753-9c81-54ed7575e720
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c06d6e246cfa51f8e84eb93ab7eb73eab40c392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619963"
---
# <a name="ln-ssis-expression"></a><span data-ttu-id="042c1-102">LN (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="042c1-102">LN (SSIS Expression)</span></span>
  <span data-ttu-id="042c1-103">Gibt den natürlichen Logarithmus eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="042c1-103">Returns the natural logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="042c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="042c1-104">Syntax</span></span>  
  
```  
  
LN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="042c1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="042c1-105">Arguments</span></span>  
 <span data-ttu-id="042c1-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="042c1-106">*numeric_expression*</span></span>  
 <span data-ttu-id="042c1-107">Ein gültiger, nicht negativer numerischer Ausdruck ungleich NULL.</span><span class="sxs-lookup"><span data-stu-id="042c1-107">Is a valid non-zero and non-negative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="042c1-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="042c1-108">Result Types</span></span>  
 <span data-ttu-id="042c1-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="042c1-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="042c1-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="042c1-110">Remarks</span></span>  
 <span data-ttu-id="042c1-111">Der numerische Ausdruck wird in den DT_R8-Datentyp umgewandelt, bevor der Logarithmus berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="042c1-111">The numeric expression is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="042c1-112">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="042c1-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="042c1-113">Falls *numeric_expression* zu 0 (null) oder einem negativen Wert ausgewertet wird, wird als Ergebnis NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="042c1-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="042c1-114">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="042c1-114">Expression Examples</span></span>  
 <span data-ttu-id="042c1-115">In diesem Beispiel wird ein numerisches Literal verwendet.</span><span class="sxs-lookup"><span data-stu-id="042c1-115">This example uses a numeric literal.</span></span> <span data-ttu-id="042c1-116">Die Funktion gibt den Wert 3,737766961828337 zurück.</span><span class="sxs-lookup"><span data-stu-id="042c1-116">The function returns the value 3.737766961828337.</span></span>  
  
```  
LN(42)  
```  
  
 <span data-ttu-id="042c1-117">In diesem Beispiel wird die **Length**-Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="042c1-117">This example uses the column **Length**.</span></span> <span data-ttu-id="042c1-118">Falls der Spaltenwert 53.99 ist, gibt die Funktion 3.9887988442302 zurück.</span><span class="sxs-lookup"><span data-stu-id="042c1-118">If the column value is 53.99, the function returns 3.9887988442302.</span></span>  
  
```  
LN(Length)   
```  
  
 <span data-ttu-id="042c1-119">In diesem Beispiel wird die **Length**-Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="042c1-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="042c1-120">Die Variable muss einen numerischen Datentyp aufweisen, oder der Ausdruck muss eine explizite Umwandlung in einen numerischen Datentyp einschließen.</span><span class="sxs-lookup"><span data-stu-id="042c1-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric data type.</span></span> <span data-ttu-id="042c1-121">Falls **Length** gleich 234,567 ist, gibt die Funktion 5,45774126708797 zurück.</span><span class="sxs-lookup"><span data-stu-id="042c1-121">If **Length** is 234.567, the function returns 5.45774126708797.</span></span>  
  
```  
LN(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="042c1-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="042c1-122">See Also</span></span>  
 <span data-ttu-id="042c1-123">[LOG &#40;SSIS-Ausdruck&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="042c1-123">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="042c1-124">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="042c1-124">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
