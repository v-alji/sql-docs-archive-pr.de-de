---
title: '| (Bitweises inklusives OR) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '| (bitwise inclusive OR)'
- bitwise inclusive OR (|)
ms.assetid: 4dce9eb2-3680-4adc-81a3-816ea52cef49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 73d64886b433ffe5b4e06dc4870bbca06b2a53dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619965"
---
# <a name="-bitwise-inclusive-or-ssis-expression"></a><span data-ttu-id="75982-102">| (Bitweises inklusives OR) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="75982-102">| (Bitwise Inclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="75982-103">Führt eine bitweise OR-Operation mit zwei ganzzahligen Werten aus.</span><span class="sxs-lookup"><span data-stu-id="75982-103">Performs a bitwise OR operation of two integer values.</span></span> <span data-ttu-id="75982-104">Jedes Bit des ersten Operanden wird mit dem entsprechenden Bit des zweiten Operanden verglichen.</span><span class="sxs-lookup"><span data-stu-id="75982-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="75982-105">Wenn eines der Bits 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75982-105">If either bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="75982-106">Andernfalls wird das entsprechende Ergebnisbit auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75982-106">Otherwise, the corresponding result bit is set to zero (0).</span></span>  
  
 <span data-ttu-id="75982-107">Beide Bedingungen müssen als Datentyp eine ganze Zahl mit Vorzeichen oder aber eine ganze Zahl ohne Vorzeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="75982-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75982-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="75982-108">Syntax</span></span>  
  
```  
  
integer_expression1 | integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="75982-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="75982-109">Arguments</span></span>  
 <span data-ttu-id="75982-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="75982-110">*integer_expression1 ,integer_ expression2*</span></span>  
 <span data-ttu-id="75982-111">Ein gültiger Ausdruck eines integer-Datentyps mit oder ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="75982-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="75982-112">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="75982-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="75982-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="75982-113">Result Types</span></span>  
 <span data-ttu-id="75982-114">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="75982-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="75982-115">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="75982-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75982-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="75982-116">Remarks</span></span>  
 <span data-ttu-id="75982-117">Wenn eine der Bedingungen NULL ist, lautet das Ergebnis des Ausdrucks NULL.</span><span class="sxs-lookup"><span data-stu-id="75982-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="75982-118">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="75982-118">Expression Examples</span></span>  
 <span data-ttu-id="75982-119">In diesem Beispiel wird eine bitweise inklusive OR-Operation mit den Variablen **NumberA** und **NumberB**ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="75982-119">This example performs a bitwise inclusive OR operation between the variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="75982-120">**NumberA** enthält 3 (00000011) und **NumberB** enthält 9 (00001001).</span><span class="sxs-lookup"><span data-stu-id="75982-120">**NumberA** contains 3 (00000011) and **NumberB** contains 9 (00001001).</span></span>  
  
```  
@NumberA | @NumberB  
```  
  
 <span data-ttu-id="75982-121">Der Ausdruck wird zu 11 (00001011) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="75982-121">The expression evaluates to 11 (00001011).</span></span>  
  
 <span data-ttu-id="75982-122">00000011</span><span class="sxs-lookup"><span data-stu-id="75982-122">00000011</span></span>  
  
 <span data-ttu-id="75982-123">00001001</span><span class="sxs-lookup"><span data-stu-id="75982-123">00001001</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="75982-124">00001011</span><span class="sxs-lookup"><span data-stu-id="75982-124">00001011</span></span>  
  
 <span data-ttu-id="75982-125">In diesem Beispiel wird eine bitweise inklusive OR-Operation mit den Spalten **ReorderPoint** und **SafetyStockLevel** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="75982-125">This example performs a bitwise inclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint | SafetyStockLevel  
```  
  
 <span data-ttu-id="75982-126">Falls **ReorderPoint** gleich 10 und **SafetyStockLevel** gleich 8 ist, wird der Ausdruck zu 10 (00001010) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="75982-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 10 (00001010).</span></span>  
  
 <span data-ttu-id="75982-127">00001010</span><span class="sxs-lookup"><span data-stu-id="75982-127">00001010</span></span>  
  
 <span data-ttu-id="75982-128">00001000</span><span class="sxs-lookup"><span data-stu-id="75982-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="75982-129">00001010</span><span class="sxs-lookup"><span data-stu-id="75982-129">00001010</span></span>  
  
 <span data-ttu-id="75982-130">In diesem Beispiel wird eine bitweise inklusive OR-Operation mit zwei ganzen Zahlen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="75982-130">This example performs a bitwise inclusive OR operation between two integers.</span></span>  
  
```  
3 | 5   
```  
  
 <span data-ttu-id="75982-131">Der Ausdruck wird zu 7 (00000111) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="75982-131">The expression evaluates to 7 (00000111).</span></span>  
  
 <span data-ttu-id="75982-132">00000011</span><span class="sxs-lookup"><span data-stu-id="75982-132">00000011</span></span>  
  
 <span data-ttu-id="75982-133">00000101</span><span class="sxs-lookup"><span data-stu-id="75982-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="75982-134">00000111</span><span class="sxs-lookup"><span data-stu-id="75982-134">00000111</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75982-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75982-135">See Also</span></span>  
 <span data-ttu-id="75982-136">[&#124;&#124; &#40;Logisches OR&#41; &#40;SSIS-Ausdruck&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="75982-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="75982-137">[^ &#40;Bitweises exklusives OR&#41; &#40;SSIS-Ausdruck&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="75982-137">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="75982-138">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="75982-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="75982-139">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="75982-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
