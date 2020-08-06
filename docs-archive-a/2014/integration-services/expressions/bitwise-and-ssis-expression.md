---
title: '&amp; (Bitweises AND) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 06d2958e-66a5-44d8-8bc4-56209ebe1ff2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbf3c8ffcef079e25c82478947bc3b92a6b4be93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619971"
---
# <a name="amp-bitwise-and-ssis-expression"></a><span data-ttu-id="34ef8-102">&amp; (Bitweises AND) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="34ef8-102">&amp; (Bitwise AND) (SSIS Expression)</span></span>
  <span data-ttu-id="34ef8-103">Führt eine bitweise AND-Operation mit zwei ganzzahligen Werten aus.</span><span class="sxs-lookup"><span data-stu-id="34ef8-103">Performs a bitwise AND operation of two integer values.</span></span> <span data-ttu-id="34ef8-104">Jedes Bit des ersten Operanden wird mit dem entsprechenden Bit des zweiten Operanden verglichen.</span><span class="sxs-lookup"><span data-stu-id="34ef8-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="34ef8-105">Wenn beide Bits 1 sind, wird das entsprechende Ergebnisbit auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34ef8-105">If both bits are 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="34ef8-106">Andernfalls wird das entsprechende Ergebnisbit auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34ef8-106">Otherwise, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="34ef8-107">Beide Bedingungen müssen als Datentyp eine ganze Zahl mit Vorzeichen oder aber eine ganze Zahl ohne Vorzeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="34ef8-107">Both conditions must be a signed integer type or both conditions must be an unsigned integer type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ef8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="34ef8-108">Syntax</span></span>  
  
```  
  
integer_expression1 & integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="34ef8-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="34ef8-109">Arguments</span></span>  
 <span data-ttu-id="34ef8-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="34ef8-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="34ef8-111">Ein gültiger Ausdruck eines integer-Datentyps mit oder ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="34ef8-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="34ef8-112">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="34ef8-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="34ef8-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="34ef8-113">Result Types</span></span>  
 <span data-ttu-id="34ef8-114">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="34ef8-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="34ef8-115">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="34ef8-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34ef8-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34ef8-116">Remarks</span></span>  
 <span data-ttu-id="34ef8-117">Wenn eine der Bedingungen NULL ist, lautet das Ergebnis des Ausdrucks NULL.</span><span class="sxs-lookup"><span data-stu-id="34ef8-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="34ef8-118">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="34ef8-118">Expression Examples</span></span>  
 <span data-ttu-id="34ef8-119">In diesem Beispiel wird eine bitweise AND-Operation mit den Spalten **NumberA** und **NumberB**ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34ef8-119">This example performs a bitwise AND operation between the columns **NumberA** and **NumberB**.</span></span> <span data-ttu-id="34ef8-120">**NumberA** enthält 3 (0000011) und die Spalte **NumberB** enthält 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="34ef8-120">**NumberA** contains 3 (0000011) and column **NumberB** contains 7 (00000111).</span></span>  
  
```  
NumberA & NumberB  
```  
  
 <span data-ttu-id="34ef8-121">Der Ausdruck wird zu 3 (00000011) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="34ef8-121">The expression evaluates to 3 (00000011).</span></span>  
  
 <span data-ttu-id="34ef8-122">00000011</span><span class="sxs-lookup"><span data-stu-id="34ef8-122">00000011</span></span>  
  
 <span data-ttu-id="34ef8-123">00000111</span><span class="sxs-lookup"><span data-stu-id="34ef8-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="34ef8-124">00000011</span><span class="sxs-lookup"><span data-stu-id="34ef8-124">00000011</span></span>  
  
 <span data-ttu-id="34ef8-125">In diesem Beispiel wird eine bitweise AND-Operation mit den Spalten **ReorderPoint** und **SafetyStockLevel** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34ef8-125">This example performs a bitwise AND operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint & SafetyStockLevel  
```  
  
 <span data-ttu-id="34ef8-126">Falls **ReorderPoint** gleich 10 und **SafetyStockLevel** gleich 8 ist, wird der Ausdruck zu 8 (00001000) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="34ef8-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 8 (00001000).</span></span>  
  
 <span data-ttu-id="34ef8-127">00001010</span><span class="sxs-lookup"><span data-stu-id="34ef8-127">00001010</span></span>  
  
 <span data-ttu-id="34ef8-128">00001000</span><span class="sxs-lookup"><span data-stu-id="34ef8-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="34ef8-129">00001000</span><span class="sxs-lookup"><span data-stu-id="34ef8-129">00001000</span></span>  
  
 <span data-ttu-id="34ef8-130">In diesem Beispiel wird eine bitweise AND-Operation mit zwei ganzen Zahlen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34ef8-130">This example performs a bitwise AND operation between two integers.</span></span>  
  
```  
3 & 5   
```  
  
 <span data-ttu-id="34ef8-131">Der Ausdruck wird zu 1 (00000001) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="34ef8-131">The expression evaluates to 1(00000001).</span></span>  
  
 <span data-ttu-id="34ef8-132">00000011</span><span class="sxs-lookup"><span data-stu-id="34ef8-132">00000011</span></span>  
  
 <span data-ttu-id="34ef8-133">00000101</span><span class="sxs-lookup"><span data-stu-id="34ef8-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="34ef8-134">00000001</span><span class="sxs-lookup"><span data-stu-id="34ef8-134">00000001</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ef8-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34ef8-135">See Also</span></span>  
 <span data-ttu-id="34ef8-136">[&& &#40;Logisches AND&#41; &#40;SSIS-Ausdruck&#41;](logical-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="34ef8-136">[&& &#40;Logical AND&#41; &#40;SSIS Expression&#41;](logical-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="34ef8-137">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="34ef8-137">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="34ef8-138">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="34ef8-138">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
