---
title: LOG (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619959"
---
# <a name="log-ssis-expression"></a><span data-ttu-id="abd67-102">LOG (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="abd67-102">LOG (SSIS Expression)</span></span>
  <span data-ttu-id="abd67-103">Gibt den Logarithmus eines numerischen Ausdrucks zur Basis 10 zurück.</span><span class="sxs-lookup"><span data-stu-id="abd67-103">Returns the base-10 logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abd67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="abd67-104">Syntax</span></span>  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="abd67-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="abd67-105">Arguments</span></span>  
 <span data-ttu-id="abd67-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="abd67-106">*numeric_expression*</span></span>  
 <span data-ttu-id="abd67-107">Ein gültiger numerischer Ausdruck, der ungleich 0 oder nicht negativ ist.</span><span class="sxs-lookup"><span data-stu-id="abd67-107">Is a valid nonzero or nonnegative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="abd67-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="abd67-108">Result Types</span></span>  
 <span data-ttu-id="abd67-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="abd67-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abd67-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="abd67-110">Remarks</span></span>  
 <span data-ttu-id="abd67-111">Der *numerische Ausdruck* wird in den DT_R8-Datentyp umgewandelt, bevor der Logarithmus berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="abd67-111">The *numeric expression* is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="abd67-112">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="abd67-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="abd67-113">Falls *numeric_expression* zu 0 (null) oder einem negativen Wert ausgewertet wird, wird als Ergebnis NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="abd67-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="abd67-114">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="abd67-114">Expression Examples</span></span>  
 <span data-ttu-id="abd67-115">In diesem Beispiel wird ein numerisches Literal verwendet.</span><span class="sxs-lookup"><span data-stu-id="abd67-115">This example uses a numeric literal.</span></span> <span data-ttu-id="abd67-116">Die Funktion gibt den Wert 1.988291341907488 zurück.</span><span class="sxs-lookup"><span data-stu-id="abd67-116">The function returns the value 1.988291341907488.</span></span>  
  
```  
LOG(97.34)  
```  
  
 <span data-ttu-id="abd67-117">In diesem Beispiel wird die **Length**-Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="abd67-117">This example uses the column **Length**.</span></span> <span data-ttu-id="abd67-118">Falls der Spaltenwert 101.24 ist, gibt die Funktion 2.005352136486217 zurück.</span><span class="sxs-lookup"><span data-stu-id="abd67-118">If the column is 101.24, the function returns 2.005352136486217.</span></span>  
  
```  
LOG(Length)   
```  
  
 <span data-ttu-id="abd67-119">In diesem Beispiel wird die **Length**-Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="abd67-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="abd67-120">Die Variable muss einen numerischen Datentyp aufweisen, oder der Ausdruck muss eine explizite Umwandlung in einen numerischen [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Datentyp einschließen.</span><span class="sxs-lookup"><span data-stu-id="abd67-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span> <span data-ttu-id="abd67-121">Falls **Length** gleich 234.567 ist, gibt die Funktion 2.370266913465859 zurück.</span><span class="sxs-lookup"><span data-stu-id="abd67-121">If **Length** is 234.567, the function returns 2.370266913465859.</span></span>  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="abd67-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abd67-122">See Also</span></span>  
 <span data-ttu-id="abd67-123">[EXP &#40;SSIS-Ausdruck&#41;](exp-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="abd67-123">[EXP &#40;SSIS Expression&#41;](exp-ssis-expression.md) </span></span>  
 <span data-ttu-id="abd67-124">[LN &#40;SSIS-Ausdruck&#41;](ln-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="abd67-124">[LN &#40;SSIS Expression&#41;](ln-ssis-expression.md) </span></span>  
 [<span data-ttu-id="abd67-125">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="abd67-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
