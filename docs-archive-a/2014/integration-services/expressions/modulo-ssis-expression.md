---
title: (Modulo) (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e23152fca9c9f2c7c3ac11490a56b03d1a1f9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617199"
---
# <a name="modulo-ssis-expression"></a><span data-ttu-id="de529-102">(Modulo) (SSIS-Ausdrücke)</span><span class="sxs-lookup"><span data-stu-id="de529-102">(Modulo) (SSIS Expression)</span></span>
  <span data-ttu-id="de529-103">Stellt den ganzzahligen Rest einer Division des ersten numerischen Ausdrucks durch den zweiten bereit.</span><span class="sxs-lookup"><span data-stu-id="de529-103">Provides the integer remainder after dividing the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de529-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de529-104">Syntax</span></span>  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="de529-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="de529-105">Arguments</span></span>  
 <span data-ttu-id="de529-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="de529-106">*dividend*</span></span>  
 <span data-ttu-id="de529-107">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de529-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="de529-108">*dividend* kann ein beliebiger numerischer Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="de529-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="de529-109">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="de529-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md)</span></span>  
  
 <span data-ttu-id="de529-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="de529-110">*divisor*</span></span>  
 <span data-ttu-id="de529-111">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="de529-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="de529-112">*divisor* kann ein beliebiger numerischer Ausdruck außer Null sein.</span><span class="sxs-lookup"><span data-stu-id="de529-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="de529-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="de529-113">Result Types</span></span>  
 <span data-ttu-id="de529-114">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="de529-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="de529-115">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="de529-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de529-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="de529-116">Remarks</span></span>  
 <span data-ttu-id="de529-117">Beide Ausdrücke müssen zu ganzzahligen Datentypen mit oder ohne Vorzeichen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="de529-117">Both expressions must evaluate to signed or unsigned integer data types.</span></span>  
  
 <span data-ttu-id="de529-118">Wenn einer der Operanden NULL ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="de529-118">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="de529-119">Modulo Null ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="de529-119">Modulo zero is not legal.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="de529-120">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="de529-120">Expression Examples</span></span>  
 <span data-ttu-id="de529-121">In diesem Beispiel wird der Teilungsrest von zwei numerischen Literalen berechnet.</span><span class="sxs-lookup"><span data-stu-id="de529-121">This example computes the modulus from two numeric literals.</span></span> <span data-ttu-id="de529-122">Das Ergebnis ist 3.</span><span class="sxs-lookup"><span data-stu-id="de529-122">The result is 3.</span></span>  
  
```  
42 % 13  
```  
  
 <span data-ttu-id="de529-123">In diesem Beispiel wird der Teilungsrest von der **SalesQuota** -Spalte und einem numerischen Literal berechnet.</span><span class="sxs-lookup"><span data-stu-id="de529-123">This example computes the modulus from the **SalesQuota** column and a numeric literal.</span></span>  
  
```  
SalesQuota % 12  
```  
  
 <span data-ttu-id="de529-124">In diesem Beispiel wird der Teilungsrest von den beiden numerischen Variablen **Sales$** und **Month**berechnet.</span><span class="sxs-lookup"><span data-stu-id="de529-124">This example computes the modulus from two numeric variables **Sales$** and **Month**.</span></span> <span data-ttu-id="de529-125">Die **Sales$** -Variable muss in eckige Klammern eingeschlossen werden, weil der Name das $-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="de529-125">The variable **Sales$** must be enclosed in brackets because the name includes the $ character.</span></span> <span data-ttu-id="de529-126">Weitere Informationen finden Sie unter [Bezeichner &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="de529-126">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
@[Sales$] % @Month  
```  
  
 <span data-ttu-id="de529-127">In diesem Beispiel wird mithilfe des Modulo-Operators ermittelt, ob der Wert der **Value** -Variablen gerade oder ungerade ist, und mit dem Bedingungsoperator wird eine Zeichenfolge zur Beschreibung des Ergebnisses zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de529-127">This example uses the modulo operator to determine if the value of the **Value** variable is even or odd, and uses the conditional operator to return a string that describes the result.</span></span> <span data-ttu-id="de529-128">Weitere Informationen finden Sie unter [? : &#40;Bedingt, SSIS-Ausdruck&#41;](conditional-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="de529-128">For more information, see [? : &#40;Conditional&#41; &#40;SSIS Expression&#41;](conditional-ssis-expression.md).</span></span>  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a><span data-ttu-id="de529-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de529-129">See Also</span></span>  
 <span data-ttu-id="de529-130">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="de529-130">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="de529-131">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="de529-131">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
