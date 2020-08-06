---
title: '&amp;&amp; (Logisches AND) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '&& (logical AND)'
- AND, logical AND
- logical AND (&&)
ms.assetid: a8cb3517-d5d1-4861-9f04-905c719185ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8d973d7d4e86f88f7ae88c820ed4e4a5c1ce526f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697029"
---
# <a name="ampamp-logical-and-ssis-expression"></a><span data-ttu-id="66f39-102">&amp;&amp; (Logisches AND) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="66f39-102">&amp;&amp; (Logical AND) (SSIS Expression)</span></span>
  <span data-ttu-id="66f39-103">Führt eine logische AND-Operation aus.</span><span class="sxs-lookup"><span data-stu-id="66f39-103">Performs a logical AND operation.</span></span> <span data-ttu-id="66f39-104">Der Ausdruck wird zu TRUE ausgewertet, falls alle Bedingungen TRUE sind.</span><span class="sxs-lookup"><span data-stu-id="66f39-104">The expression evaluates to TRUE if all conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66f39-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="66f39-105">Syntax</span></span>  
  
```  
  
boolean_expression1 && boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="66f39-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="66f39-106">Arguments</span></span>  
 <span data-ttu-id="66f39-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="66f39-107">*boolean _expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="66f39-108">Ein gültiger Ausdruck, der zu TRUE, FALSE oder NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="66f39-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="66f39-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="66f39-109">Result Types</span></span>  
 <span data-ttu-id="66f39-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="66f39-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66f39-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="66f39-111">Remarks</span></span>  
 <span data-ttu-id="66f39-112">In der folgenden Tabelle wird das Ergebnis des &&-Operators dargestellt.</span><span class="sxs-lookup"><span data-stu-id="66f39-112">The following table shows the result of the && operator.</span></span>  
  
|<span data-ttu-id="66f39-113">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="66f39-113">Result</span></span>|<span data-ttu-id="66f39-114">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="66f39-114">Expression</span></span>|<span data-ttu-id="66f39-115">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="66f39-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="66f39-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="66f39-116">TRUE</span></span>|<span data-ttu-id="66f39-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="66f39-117">TRUE</span></span>|<span data-ttu-id="66f39-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="66f39-118">TRUE</span></span>|  
|<span data-ttu-id="66f39-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-119">FALSE</span></span>|<span data-ttu-id="66f39-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="66f39-120">TRUE</span></span>|<span data-ttu-id="66f39-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-121">FALSE</span></span>|  
|<span data-ttu-id="66f39-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-122">FALSE</span></span>|<span data-ttu-id="66f39-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-123">FALSE</span></span>|<span data-ttu-id="66f39-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-124">FALSE</span></span>|  
|<span data-ttu-id="66f39-125">NULL</span><span class="sxs-lookup"><span data-stu-id="66f39-125">NULL</span></span>|<span data-ttu-id="66f39-126">NULL</span><span class="sxs-lookup"><span data-stu-id="66f39-126">NULL</span></span>|<span data-ttu-id="66f39-127">NULL</span><span class="sxs-lookup"><span data-stu-id="66f39-127">NULL</span></span>|  
|<span data-ttu-id="66f39-128">NULL</span><span class="sxs-lookup"><span data-stu-id="66f39-128">NULL</span></span>|<span data-ttu-id="66f39-129">NULL</span><span class="sxs-lookup"><span data-stu-id="66f39-129">NULL</span></span>|<span data-ttu-id="66f39-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="66f39-130">TRUE</span></span>|  
|<span data-ttu-id="66f39-131">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-131">FALSE</span></span>|<span data-ttu-id="66f39-132">NULL</span><span class="sxs-lookup"><span data-stu-id="66f39-132">NULL</span></span>|<span data-ttu-id="66f39-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="66f39-133">FALSE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="66f39-134">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="66f39-134">Expression Examples</span></span>  
 <span data-ttu-id="66f39-135">In diesem Beispiel werden die Spalten **StandardCost** und **ListPrice** verwendet.</span><span class="sxs-lookup"><span data-stu-id="66f39-135">This example uses the **StandardCost** and the **ListPrice** columns.</span></span> <span data-ttu-id="66f39-136">In diesem Beispiel wird zu TRUE ausgewertet, falls der Wert der **StandardCost** -Spalte kleiner als 300 und falls die **ListPrice** -Spalte größer als 500 ist.</span><span class="sxs-lookup"><span data-stu-id="66f39-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 and the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 && ListPrice > 500  
```  
  
 <span data-ttu-id="66f39-137">In diesem Beispiel werden die Variablen **SPrice** und **LPrice** anstelle von Literalen verwendet.</span><span class="sxs-lookup"><span data-stu-id="66f39-137">This example uses the variables **SPrice** and **LPrice** instead of literals.</span></span>  
  
```  
StandardCost < @SPrice && ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="66f39-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66f39-138">See Also</span></span>  
 <span data-ttu-id="66f39-139">[& &#40;Bitweises AND&#41; &#40;SSIS-Ausdruck&#41;](bitwise-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="66f39-139">[& &#40;Bitwise AND&#41; &#40;SSIS Expression&#41;](bitwise-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="66f39-140">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="66f39-140">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="66f39-141">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="66f39-141">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
