---
title: SQRT (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQRT function
- square root of given expression
ms.assetid: 54a75389-c501-4e22-87b8-905f66d6a3a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9efa3f8da2e5280692aa65a25610211aba2fa40f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701378"
---
# <a name="sqrt-ssis-expression"></a><span data-ttu-id="3792d-102">SQRT (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="3792d-102">SQRT (SSIS Expression)</span></span>
  <span data-ttu-id="3792d-103">Gibt die Quadratwurzel eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="3792d-103">Returns the square root of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3792d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3792d-104">Syntax</span></span>  
  
```  
  
SQRT(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="3792d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3792d-105">Arguments</span></span>  
 <span data-ttu-id="3792d-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="3792d-106">*numeric_expression*</span></span>  
 <span data-ttu-id="3792d-107">Ein numerischer Ausdruck mit einem beliebigen numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="3792d-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="3792d-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3792d-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3792d-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="3792d-109">Result Types</span></span>  
 <span data-ttu-id="3792d-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="3792d-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3792d-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3792d-111">Remarks</span></span>  
 <span data-ttu-id="3792d-112">SQRT gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="3792d-112">SQRT returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="3792d-113">SQRT schlägt fehl, wenn das Argument einen negativen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="3792d-113">SQRT fails if the argument is a negative value.</span></span>  
  
 <span data-ttu-id="3792d-114">Das Argument wird in einen DT_R8-Datentyp umgewandelt, bevor die Quadratwurzel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="3792d-114">The argument is cast to the DT_R8 data type before the square root operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3792d-115">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3792d-115">Expression Examples</span></span>  
 <span data-ttu-id="3792d-116">In diesem Beispiel wird die Quadratwurzel eines numerischen Literals zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3792d-116">This example returns the square root of a numeric literal.</span></span> <span data-ttu-id="3792d-117">Als Ergebnis wird 12 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3792d-117">The return result is 12.</span></span>  
  
```  
SQRT(144)  
```  
  
 <span data-ttu-id="3792d-118">In diesem Beispiel wird die Quadratwurzel eines Ausdrucks zurückgegeben, die das Ergebnis der Subtraktion von Werten in den Spalten **Value1** und **Value2** ist.</span><span class="sxs-lookup"><span data-stu-id="3792d-118">This example returns the square root of an expression, the result of subtracting values in the **Value1** and **Value2** columns.</span></span>  
  
```  
SQRT(Value1 - Value2)  
```  
  
 <span data-ttu-id="3792d-119">In diesem Beispiel wird die Länge der dritten Seite eines rechtwinkligen Dreiecks zurückgegeben, indem die SQUARE-Funktion auf zwei Variablen angewendet und dann die Quadratwurzel der Summe berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="3792d-119">This example returns the length of the third side of a right triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="3792d-120">Falls **Side1** 3 und **Side2** 4 enthält, gibt die SQRT-Funktion 5 zurück.</span><span class="sxs-lookup"><span data-stu-id="3792d-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3792d-121">In Ausdrücken schließen Variablennamen immer das \@-Präfix ein.</span><span class="sxs-lookup"><span data-stu-id="3792d-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3792d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3792d-122">See Also</span></span>  
 [<span data-ttu-id="3792d-123">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="3792d-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
