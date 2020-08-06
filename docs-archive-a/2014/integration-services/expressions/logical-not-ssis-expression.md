---
title: '! (Logisches NOT) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617201"
---
# <a name="-logical-not-ssis-expression"></a><span data-ttu-id="83a9f-103">!</span><span class="sxs-lookup"><span data-stu-id="83a9f-103">!</span></span> <span data-ttu-id="83a9f-104">(Logisches NOT) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="83a9f-104">(Logical Not) (SSIS Expression)</span></span>
  <span data-ttu-id="83a9f-105">Negiert einen booleschen Operanden.</span><span class="sxs-lookup"><span data-stu-id="83a9f-105">Negates a Boolean operand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83a9f-106">Der</span><span class="sxs-lookup"><span data-stu-id="83a9f-106">The !</span></span> <span data-ttu-id="83a9f-107">!-Operator kann nicht zusammen mit anderen Operatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83a9f-107">operator cannot be used in conjunction with other operators.</span></span> <span data-ttu-id="83a9f-108">Beispielsweise können nicht den</span><span class="sxs-lookup"><span data-stu-id="83a9f-108">For example, you cannot combine the !</span></span> <span data-ttu-id="83a9f-109">!-Operator und den >-Operator zum !>-Operator</span><span class="sxs-lookup"><span data-stu-id="83a9f-109">and the > operators into the !>.</span></span> <span data-ttu-id="83a9f-110">zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="83a9f-110">operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a9f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="83a9f-111">Syntax</span></span>  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="83a9f-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="83a9f-112">Arguments</span></span>  
 <span data-ttu-id="83a9f-113">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="83a9f-113">*boolean_expression*</span></span>  
 <span data-ttu-id="83a9f-114">Ein gültiger Ausdruck, der zu einem booleschen Wert ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="83a9f-114">Is any valid expression that evaluates to a Boolean.</span></span> <span data-ttu-id="83a9f-115">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="83a9f-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="83a9f-116">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="83a9f-116">Result Types</span></span>  
 <span data-ttu-id="83a9f-117">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="83a9f-117">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a9f-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="83a9f-118">Remarks</span></span>  
 <span data-ttu-id="83a9f-119">In der folgenden Tabelle wird das Ergebnis des</span><span class="sxs-lookup"><span data-stu-id="83a9f-119">The following table shows the result of the !</span></span> <span data-ttu-id="83a9f-120">ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="83a9f-120">operation.</span></span>  
  
|<span data-ttu-id="83a9f-121">Ursprünglicher boolescher Ausdruck</span><span class="sxs-lookup"><span data-stu-id="83a9f-121">Original Boolean expression</span></span>|<span data-ttu-id="83a9f-122">Nach dem Anwenden des !-</span><span class="sxs-lookup"><span data-stu-id="83a9f-122">After applying the !</span></span> <span data-ttu-id="83a9f-123">Operator</span><span class="sxs-lookup"><span data-stu-id="83a9f-123">operator</span></span>|  
|---------------------------------|------------------------------------|  
|<span data-ttu-id="83a9f-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="83a9f-124">TRUE</span></span>|<span data-ttu-id="83a9f-125">FALSE</span><span class="sxs-lookup"><span data-stu-id="83a9f-125">FALSE</span></span>|  
|<span data-ttu-id="83a9f-126">NULL</span><span class="sxs-lookup"><span data-stu-id="83a9f-126">NULL</span></span>|<span data-ttu-id="83a9f-127">NULL</span><span class="sxs-lookup"><span data-stu-id="83a9f-127">NULL</span></span>|  
|<span data-ttu-id="83a9f-128">FALSE</span><span class="sxs-lookup"><span data-stu-id="83a9f-128">FALSE</span></span>|<span data-ttu-id="83a9f-129">TRUE</span><span class="sxs-lookup"><span data-stu-id="83a9f-129">TRUE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="83a9f-130">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="83a9f-130">Expression Examples</span></span>  
 <span data-ttu-id="83a9f-131">In diesem Beispiel wird zu FALSE ausgewertet, falls der Wert in der **Color** -Spalte "red" ist.</span><span class="sxs-lookup"><span data-stu-id="83a9f-131">This example evaluates to FALSE if the **Color** column value is "red".</span></span>  
  
```  
!(Color == "red")  
```  
  
 <span data-ttu-id="83a9f-132">In diesem Beispiel wird zu TRUE ausgewertet, falls der Wert der **MonthNumber** -Variablen mit der ganzen Zahl identisch ist, die den aktuellen Monat darstellt.</span><span class="sxs-lookup"><span data-stu-id="83a9f-132">This example evaluates to TRUE if the value of the **MonthNumber** variable is the same as the integer that represents the current month.</span></span> <span data-ttu-id="83a9f-133">Weitere Informationen finden Sie unter [MONTH &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md) und [GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="83a9f-133">For more information, see [MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) and [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="83a9f-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83a9f-134">See Also</span></span>  
 <span data-ttu-id="83a9f-135">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="83a9f-135">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="83a9f-136">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="83a9f-136">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
