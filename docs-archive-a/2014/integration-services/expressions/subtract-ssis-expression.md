---
title: '- (Subtrahieren) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (subtract)'
- subtract operator (-)
ms.assetid: b48da086-37dd-460a-8a4b-912f52c9b158
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 79c47689baf47c33952c6b208ac622e9920d05fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701349"
---
# <a name="--subtract-ssis-expression"></a><span data-ttu-id="3abe3-102">- (Subtrahieren) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="3abe3-102">- (Subtract) (SSIS Expression)</span></span>
  <span data-ttu-id="3abe3-103">Subtrahiert den zweiten numerischen Ausdruck vom ersten.</span><span class="sxs-lookup"><span data-stu-id="3abe3-103">Subtracts the second numeric expression from the first one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abe3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3abe3-104">Syntax</span></span>  
  
```  
  
numeric_expression1 - numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3abe3-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3abe3-105">Arguments</span></span>  
 <span data-ttu-id="3abe3-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="3abe3-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="3abe3-107">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="3abe3-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="3abe3-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3abe3-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3abe3-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="3abe3-109">Result Types</span></span>  
 <span data-ttu-id="3abe3-110">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="3abe3-110">Determined by the data types of the two arguments.</span></span> <span data-ttu-id="3abe3-111">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3abe3-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3abe3-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3abe3-112">Remarks</span></span>  
 <span data-ttu-id="3abe3-113">Schließen Sie den unären Minusausdruck in Klammern ein, um sicherzustellen, dass der Ausdruck in der richtigen Reihenfolge ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="3abe3-113">Enclose the minus unary expression in parenthesis to ensure that the expression is evaluated in the correct order</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3abe3-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3abe3-114">Remarks</span></span>  
 <span data-ttu-id="3abe3-115">Wenn einer der Operanden NULL ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="3abe3-115">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3abe3-116">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3abe3-116">Expression Examples</span></span>  
 <span data-ttu-id="3abe3-117">In diesem Beispiel werden numerische Literale subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="3abe3-117">This example subtracts numeric literals.</span></span>  
  
```  
5 - 6.09  
```  
  
 <span data-ttu-id="3abe3-118">In diesem Beispiel wird der Wert in der **StandardCost** -Spalte vom Wert in der **ListPrice** -Spalte subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="3abe3-118">This example subtracts the value in the **StandardCost** column from the value in the **ListPrice** column.</span></span>  
  
```  
ListPrice - StandardCost  
```  
  
 <span data-ttu-id="3abe3-119">In diesem Beispiel wird ein berechneter Wert von der **ListPrice** -Spalte subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="3abe3-119">This example subtracts a calculated value from the **ListPrice** column.</span></span> <span data-ttu-id="3abe3-120">Die **Discount%** -Variable muss in eckige Klammern eingeschlossen werden, weil der Name das Zeichen % enthält.</span><span class="sxs-lookup"><span data-stu-id="3abe3-120">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="3abe3-121">Weitere Informationen finden Sie unter [Bezeichner &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="3abe3-121">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="3abe3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3abe3-122">See Also</span></span>  
 <span data-ttu-id="3abe3-123">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="3abe3-123">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="3abe3-124">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="3abe3-124">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
