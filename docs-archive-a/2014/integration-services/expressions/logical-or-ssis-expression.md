---
title: '|| (Logisches OR) (SSIS-Ausdruck) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OR operator
- logical OR (||)
- '|| (logical OR)'
ms.assetid: a3c07c09-f121-4187-9617-b01adcf843c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72d4a1c7b54856675f0faa7f5f58452cb8bca450
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697030"
---
# <a name="-logical-or-ssis-expression"></a><span data-ttu-id="e2c45-102">|| (Logisches OR) (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="e2c45-102">|| (Logical OR) (SSIS Expression)</span></span>
  <span data-ttu-id="e2c45-103">Führt eine logische OR-Operation aus.</span><span class="sxs-lookup"><span data-stu-id="e2c45-103">Performs a logical OR operation.</span></span> <span data-ttu-id="e2c45-104">Der Ausdruck wird zu TRUE ausgewertet, falls mindestens eine Bedingung TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="e2c45-104">The expression evaluates to TRUE if one or both conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c45-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2c45-105">Syntax</span></span>  
  
```  
  
boolean_expression1 || boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2c45-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="e2c45-106">Arguments</span></span>  
 <span data-ttu-id="e2c45-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="e2c45-107">*boolean_expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="e2c45-108">Ein gültiger Ausdruck, der zu TRUE, FALSE oder NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e2c45-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e2c45-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="e2c45-109">Result Types</span></span>  
 <span data-ttu-id="e2c45-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="e2c45-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2c45-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e2c45-111">Remarks</span></span>  
 <span data-ttu-id="e2c45-112">In der folgenden Tabelle wird das Ergebnis des ||-Operators dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2c45-112">The following table shows the result of the || operator.</span></span>  
  
|<span data-ttu-id="e2c45-113">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="e2c45-113">Result</span></span>|<span data-ttu-id="e2c45-114">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e2c45-114">Expression</span></span>|<span data-ttu-id="e2c45-115">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e2c45-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="e2c45-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-116">TRUE</span></span>|<span data-ttu-id="e2c45-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-117">TRUE</span></span>|<span data-ttu-id="e2c45-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-118">TRUE</span></span>|  
|<span data-ttu-id="e2c45-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-119">TRUE</span></span>|<span data-ttu-id="e2c45-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-120">TRUE</span></span>|<span data-ttu-id="e2c45-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="e2c45-121">FALSE</span></span>|  
|<span data-ttu-id="e2c45-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="e2c45-122">FALSE</span></span>|<span data-ttu-id="e2c45-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="e2c45-123">FALSE</span></span>|<span data-ttu-id="e2c45-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="e2c45-124">FALSE</span></span>|  
|<span data-ttu-id="e2c45-125">NULL</span><span class="sxs-lookup"><span data-stu-id="e2c45-125">NULL</span></span>|<span data-ttu-id="e2c45-126">NULL</span><span class="sxs-lookup"><span data-stu-id="e2c45-126">NULL</span></span>|<span data-ttu-id="e2c45-127">NULL</span><span class="sxs-lookup"><span data-stu-id="e2c45-127">NULL</span></span>|  
|<span data-ttu-id="e2c45-128">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-128">TRUE</span></span>|<span data-ttu-id="e2c45-129">NULL</span><span class="sxs-lookup"><span data-stu-id="e2c45-129">NULL</span></span>|<span data-ttu-id="e2c45-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="e2c45-130">TRUE</span></span>|  
|<span data-ttu-id="e2c45-131">NULL</span><span class="sxs-lookup"><span data-stu-id="e2c45-131">NULL</span></span>|<span data-ttu-id="e2c45-132">NULL</span><span class="sxs-lookup"><span data-stu-id="e2c45-132">NULL</span></span>|<span data-ttu-id="e2c45-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="e2c45-133">FALSE</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="e2c45-134">Beispiele für SSIS-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e2c45-134">SSIS Expression Examples</span></span>  
 <span data-ttu-id="e2c45-135">In diesem Beispiel werden die Spalten **StandardCost** und **ListPrice** verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2c45-135">This example uses the **StandardCost** and **ListPrice** columns.</span></span> <span data-ttu-id="e2c45-136">In diesem Beispiel wird zu TRUE ausgewertet, falls der Wert der **StandardCost** -Spalte kleiner als 300 oder falls die **ListPrice** -Spalte größer als 500 ist.</span><span class="sxs-lookup"><span data-stu-id="e2c45-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 or the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 || ListPrice > 500  
```  
  
 <span data-ttu-id="e2c45-137">In diesem Beispiel werden die Variablen **SPrice** und **LPrice** anstelle numerischer Literale verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2c45-137">This example uses the variables **SPrice** and **LPrice** instead of numeric literals.</span></span>  
  
```  
StandardCost < @SPrice || ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2c45-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2c45-138">See Also</span></span>  
 <span data-ttu-id="e2c45-139">[&#124; &#40;Bitweises inklusives OR&#41; &#40;SSIS-Ausdruck&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2c45-139">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="e2c45-140">[^ &#40;Bitweises exklusives OR&#41; &#40;SSIS-Ausdruck&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2c45-140">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="e2c45-141">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="e2c45-141">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="e2c45-142">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="e2c45-142">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
