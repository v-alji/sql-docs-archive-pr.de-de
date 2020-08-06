---
title: (Division) (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 5bde9223-872d-443e-8a27-57735e1d8f3d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4541cd4601047770d1bf361077b1c474219e8833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609963"
---
# <a name="divide-ssis-expression"></a><span data-ttu-id="15054-102">(Division) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="15054-102">Divide (SSIS Expression)</span></span>
  <span data-ttu-id="15054-103">Dividiert den ersten numerischen Ausdruck durch den zweiten numerischen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="15054-103">Divides the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15054-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15054-104">Syntax</span></span>  
  
```  
  
dividend / divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="15054-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="15054-105">Arguments</span></span>  
 <span data-ttu-id="15054-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="15054-106">*dividend*</span></span>  
 <span data-ttu-id="15054-107">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="15054-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="15054-108">*dividend* kann ein beliebiger numerischer Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="15054-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="15054-109">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="15054-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="15054-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="15054-110">*divisor*</span></span>  
 <span data-ttu-id="15054-111">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="15054-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="15054-112">*divisor* kann ein beliebiger numerischer Ausdruck außer Null sein.</span><span class="sxs-lookup"><span data-stu-id="15054-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="15054-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="15054-113">Result Types</span></span>  
 <span data-ttu-id="15054-114">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="15054-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="15054-115">Weitere Informationen finden Sie unter [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="15054-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15054-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="15054-116">Remarks</span></span>  
 <span data-ttu-id="15054-117">Wenn einer der Operanden NULL ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="15054-117">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="15054-118">Division durch Null ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="15054-118">Dividing by zero is not legal.</span></span> <span data-ttu-id="15054-119">Je nachdem, wie der *divisor* -Teilausdruck ausgewertet wird, wird einer der folgenden Fehler gemeldet:</span><span class="sxs-lookup"><span data-stu-id="15054-119">Depending on how the *divisor* subexpression is evaluated, one of following errors occurs:</span></span>  
  
-   <span data-ttu-id="15054-120">Falls der zu Null ausgewertete *divisor* -Teilausdruck eine Konstante ist, wird der Fehler zur Entwurfszeit angezeigt, und der Ausdruck kann deshalb nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="15054-120">If the *divisor* subexpression that evaluates to zero is a constant, the error appears at design time, causing the expression to fail validation.</span></span>  
  
-   <span data-ttu-id="15054-121">Falls der zu Null ausgewertete *divisor* -Teilausdruck Variablen, aber keine Eingabespalten enthält, wird für die zugehörige Komponente bei der Überprüfung vor der Ausführung (die vor der Ausführung des Pakets erfolgt) ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="15054-121">If the *divisor* subexpression that evaluates to zero contains variables, but no input columns, the component to which the expression belongs fails the pre-execution validation that occurs before the package runs.</span></span>  
  
-   <span data-ttu-id="15054-122">Falls der zu 0 (null) ausgewertete *divisor* -Teilausdruck Eingabespalten enthält, wird der Fehler zur Laufzeit gemeldet und gemäß den Fehlerflussregeln der Datenflusskomponente behandelt.</span><span class="sxs-lookup"><span data-stu-id="15054-122">If the *divisor* subexpression that evaluates to zero contains input columns, the error appears at run time and is handled according to the error flow rules of the data flow component.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="15054-123">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="15054-123">Expression Examples</span></span>  
 <span data-ttu-id="15054-124">In diesem Beispiel werden zwei numerische Literale dividiert.</span><span class="sxs-lookup"><span data-stu-id="15054-124">This example divides two numeric literals.</span></span>  
  
```  
25 / 5  
```  
  
 <span data-ttu-id="15054-125">In diesem Beispiel werden Werte in der **ListPrice** -Spalte durch die Werte in der **StandardCost** -Spalte dividiert.</span><span class="sxs-lookup"><span data-stu-id="15054-125">This example divides values in the **ListPrice** column by values in the **StandardCost** column.</span></span>  
  
```  
ListPrice / StandardCost  
```  
  
## <a name="see-also"></a><span data-ttu-id="15054-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15054-126">See Also</span></span>  
 <span data-ttu-id="15054-127">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="15054-127">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="15054-128">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="15054-128">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
