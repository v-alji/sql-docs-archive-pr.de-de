---
title: '* (Multiplizieren) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '* (multiply operator)'
- multiply operator (*)
ms.assetid: d457f052-ffbb-4485-833f-f4bed4349b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16d8429a869b60be31a94244a2ce47d515770c6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617196"
---
# <a name="-multiply-ssis-expression"></a><span data-ttu-id="c0350-102">\* (Multiplizieren) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="c0350-102">\* (Multiply) (SSIS Expression)</span></span>
  <span data-ttu-id="c0350-103">Multipliziert zwei numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c0350-103">Multiplies two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0350-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0350-104">Syntax</span></span>  
  
```  
  
numeric_expression1 * numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c0350-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c0350-105">Arguments</span></span>  
 <span data-ttu-id="c0350-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="c0350-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="c0350-107">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c0350-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="c0350-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c0350-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c0350-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="c0350-109">Result Types</span></span>  
 <span data-ttu-id="c0350-110">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="c0350-110">Determined by data types of the two arguments.</span></span> <span data-ttu-id="c0350-111">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c0350-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0350-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c0350-112">Remarks</span></span>  
 <span data-ttu-id="c0350-113">Wenn einer der Operanden NULL ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="c0350-113">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c0350-114">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c0350-114">Expression Examples</span></span>  
 <span data-ttu-id="c0350-115">In diesem Beispiel werden numerische Literale multipliziert.</span><span class="sxs-lookup"><span data-stu-id="c0350-115">This example multiplies numeric literals.</span></span>  
  
```  
5 * 6.09  
```  
  
 <span data-ttu-id="c0350-116">In diesem Beispiel werden Werte in der **ListPrice** -Spalte mit 10 % multipliziert.</span><span class="sxs-lookup"><span data-stu-id="c0350-116">This example multiplies values in the **ListPrice** column by 10 percent.</span></span>  
  
```  
ListPrice * .10  
```  
  
 <span data-ttu-id="c0350-117">In diesem Beispiel wird das Ergebnis eines Ausdrucks von der **ListPrice** -Spalte subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="c0350-117">This example subtracts the result of an expression from the **ListPrice** column.</span></span> <span data-ttu-id="c0350-118">Die **Discount%** -Variable muss in eckige Klammern eingeschlossen werden, weil der Name das Zeichen % enthält.</span><span class="sxs-lookup"><span data-stu-id="c0350-118">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="c0350-119">Weitere Informationen finden Sie unter [Bezeichner &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="c0350-119">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0350-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0350-120">See Also</span></span>  
 <span data-ttu-id="c0350-121">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="c0350-121">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="c0350-122">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="c0350-122">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
