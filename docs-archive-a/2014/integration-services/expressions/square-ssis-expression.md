---
title: SQUARE (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQUARE
- square values
ms.assetid: cecf1bb2-3d55-40a6-9688-ed67bcc150b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 09955e708aae707a88aa7821d2a72651a3a44d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701372"
---
# <a name="square-ssis-expression"></a><span data-ttu-id="002b6-102">SQUARE (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="002b6-102">SQUARE (SSIS Expression)</span></span>
  <span data-ttu-id="002b6-103">Gibt das Quadrat eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="002b6-103">Returns the square of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="002b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="002b6-104">Syntax</span></span>  
  
```  
  
SQUARE(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="002b6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="002b6-105">Arguments</span></span>  
 <span data-ttu-id="002b6-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="002b6-106">*numeric_expression*</span></span>  
 <span data-ttu-id="002b6-107">Ein numerischer Ausdruck mit einem beliebigen numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="002b6-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="002b6-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="002b6-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="002b6-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="002b6-109">Result Types</span></span>  
 <span data-ttu-id="002b6-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="002b6-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="002b6-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="002b6-111">Remarks</span></span>  
 <span data-ttu-id="002b6-112">SQUARE gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="002b6-112">SQUARE returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="002b6-113">Das Argument wird in einen DT_R8-Datentyp umgewandelt, bevor das Quadrat berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="002b6-113">The argument is cast to the DT_R8 data type before the square operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="002b6-114">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="002b6-114">Expression Examples</span></span>  
 <span data-ttu-id="002b6-115">In diesem Beispiel wird das Quadrat von 12 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="002b6-115">This example returns the square of 12.</span></span> <span data-ttu-id="002b6-116">Als Ergebnis wird 144 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="002b6-116">The return result is 144.</span></span>  
  
```  
SQUARE(12)  
```  
  
 <span data-ttu-id="002b6-117">In diesem Beispiel wird das Quadrat des Ergebnisses aus der Subtraktion von Werten in zwei Spalten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="002b6-117">This example returns the square of the result of subtracting values in two columns.</span></span> <span data-ttu-id="002b6-118">Falls **Value1** 12 und **Value2** 4 enthält, gibt die SQUARE-Funktion 64 zurück.</span><span class="sxs-lookup"><span data-stu-id="002b6-118">If **Value1** contains 12 and **Value2** contains 4, the SQUARE function returns 64.</span></span>  
  
```  
SQUARE(Value1 - Value2)  
```  
  
 <span data-ttu-id="002b6-119">In diesem Beispiel wird die Länge der dritten Seite eines rechtwinkligen Dreiecks zurückgegeben, indem die SQUARE-Funktion auf zwei Variablen angewendet und dann die Quadratwurzel der Summe berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="002b6-119">This example returns the length of the third side of a right angle triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="002b6-120">Falls **Side1** 3 und **Side2** 4 enthält, gibt die SQRT-Funktion 5 zurück.</span><span class="sxs-lookup"><span data-stu-id="002b6-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="002b6-121">In Ausdrücken schließen Variablennamen immer das \@-Präfix ein.</span><span class="sxs-lookup"><span data-stu-id="002b6-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002b6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="002b6-122">See Also</span></span>  
 [<span data-ttu-id="002b6-123">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="002b6-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
