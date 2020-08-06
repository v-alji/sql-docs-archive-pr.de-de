---
title: ^ (Bitweises exklusives OR) (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- bitwise exclusive OR (^)
ms.assetid: 6ac53cab-29c4-4835-9f87-371b058b2f38
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d86c3d810e9e5572af93c97f82c2275db2c979b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619972"
---
# <a name="-bitwise-exclusive-or-ssis-expression"></a><span data-ttu-id="9d321-102">^ (Bitweises exklusives OR) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="9d321-102">^ (Bitwise Exclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="9d321-103">Führt eine bitweise exklusive OR-Operation mit zwei ganzzahligen Werten aus.</span><span class="sxs-lookup"><span data-stu-id="9d321-103">Performs a bitwise exclusive OR operation of two integer values.</span></span> <span data-ttu-id="9d321-104">Jedes Bit des ersten Operanden wird mit dem entsprechenden Bit des zweiten Operanden verglichen.</span><span class="sxs-lookup"><span data-stu-id="9d321-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="9d321-105">Wenn ein Bit 0 und das andere 1 ist, wird das entsprechende Ergebnisbit auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9d321-105">If one bit is 0 and the other bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="9d321-106">Wenn beide Bits 0 oder 1 sind, wird das entsprechende Ergebnisbit auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9d321-106">If both bits are 0 or both bits are 1, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="9d321-107">Beide Bedingungen müssen als Datentyp eine ganze Zahl mit Vorzeichen oder aber eine ganze Zahl ohne Vorzeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9d321-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d321-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d321-108">Syntax</span></span>  
  
```  
  
integer_expression1 ^ integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d321-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="9d321-109">Arguments</span></span>  
 <span data-ttu-id="9d321-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="9d321-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="9d321-111">Ein gültiger Ausdruck eines integer-Datentyps mit oder ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="9d321-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="9d321-112">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="9d321-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9d321-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="9d321-113">Result Types</span></span>  
 <span data-ttu-id="9d321-114">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="9d321-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="9d321-115">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9d321-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d321-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d321-116">Remarks</span></span>  
 <span data-ttu-id="9d321-117">Wenn eine der Bedingungen NULL ist, lautet das Ergebnis des Ausdrucks NULL.</span><span class="sxs-lookup"><span data-stu-id="9d321-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="9d321-118">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9d321-118">Expression Examples</span></span>  
 <span data-ttu-id="9d321-119">In diesem Beispiel wird eine bitweise exklusive OR-Operation mit den Variablen **NumberA** und **NumberB**ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9d321-119">This example performs a bitwise exclusive OR operation between variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="9d321-120">**NumberA** enthält 3 (00000011) und **NumberB** enthält 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="9d321-120">**NumberA** contains 3 (00000011) and **NumberB** contains 7 (00000111).</span></span>  
  
```  
@NumberA ^ @NumberB  
```  
  
 <span data-ttu-id="9d321-121">Der Ausdruck wird zu 4 (00000100) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9d321-121">The expression evaluates to 4 (00000100).</span></span>  
  
 <span data-ttu-id="9d321-122">00000011</span><span class="sxs-lookup"><span data-stu-id="9d321-122">00000011</span></span>  
  
 <span data-ttu-id="9d321-123">00000111</span><span class="sxs-lookup"><span data-stu-id="9d321-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="9d321-124">00000100</span><span class="sxs-lookup"><span data-stu-id="9d321-124">00000100</span></span>  
  
 <span data-ttu-id="9d321-125">In diesem Beispiel wird eine bitweise exklusive OR-Operation mit den Spalten **ReorderPoint** und **SafetyStockLevel** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9d321-125">This example performs a bitwise exclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint ^ SafetyStockLevel  
```  
  
 <span data-ttu-id="9d321-126">Falls **ReorderPoint** gleich 10 und **SafetyStockLevel** gleich 8 ist, wird der Ausdruck zu 2 (00000010) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9d321-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 2 (00000010).</span></span>  
  
 <span data-ttu-id="9d321-127">00001010</span><span class="sxs-lookup"><span data-stu-id="9d321-127">00001010</span></span>  
  
 <span data-ttu-id="9d321-128">00001000</span><span class="sxs-lookup"><span data-stu-id="9d321-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="9d321-129">00000010</span><span class="sxs-lookup"><span data-stu-id="9d321-129">00000010</span></span>  
  
 <span data-ttu-id="9d321-130">In diesem Beispiel wird eine bitweise exklusive OR-Operation mit zwei ganzen Zahlen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9d321-130">This example performs a bitwise exclusive OR operation between two integers.</span></span>  
  
```  
3 ^ 5   
```  
  
 <span data-ttu-id="9d321-131">Der Ausdruck wird zu 6 (00000110) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9d321-131">The expression evaluates to 6 (00000110).</span></span>  
  
 <span data-ttu-id="9d321-132">00000011</span><span class="sxs-lookup"><span data-stu-id="9d321-132">00000011</span></span>  
  
 <span data-ttu-id="9d321-133">00000101</span><span class="sxs-lookup"><span data-stu-id="9d321-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="9d321-134">00000110</span><span class="sxs-lookup"><span data-stu-id="9d321-134">00000110</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d321-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d321-135">See Also</span></span>  
 <span data-ttu-id="9d321-136">[&#124;&#124; &#40;Logisches OR&#41; &#40;SSIS-Ausdruck&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="9d321-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="9d321-137">[&#124; &#40;Bitweises inklusives OR&#41; &#40;SSIS-Ausdruck&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="9d321-137">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="9d321-138">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="9d321-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="9d321-139">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="9d321-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
