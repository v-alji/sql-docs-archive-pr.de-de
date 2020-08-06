---
title: + (Addieren) (SSIS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- + (add)
- add operator (+)
- adding expressions
ms.assetid: 44df4154-fed5-4e7f-9995-e703a0164f6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fe1e8f2118e6328582cb24abfd44eef5f3b15f79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619976"
---
# <a name="-add-ssis"></a><span data-ttu-id="3e3a8-102">+ (Addieren) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="3e3a8-102">+ (Add) (SSIS)</span></span>
  <span data-ttu-id="3e3a8-103">Addiert zwei numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-103">Adds two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e3a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e3a8-104">Syntax</span></span>  
  
```  
  
numeric_expression1 + numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e3a8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3e3a8-105">Arguments</span></span>  
 <span data-ttu-id="3e3a8-106">*numeric_expression1, numeric_ expression2*</span><span class="sxs-lookup"><span data-stu-id="3e3a8-106">*numeric_expression1, numeric_ expression2*</span></span>  
 <span data-ttu-id="3e3a8-107">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-107">Is any valid expression of a numeric data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3e3a8-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="3e3a8-108">Result Types</span></span>  
 <span data-ttu-id="3e3a8-109">Die Ergebnistypen werden von den Datentypen der beiden Argumente bestimmt.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-109">Determined by data types of the two arguments.</span></span> <span data-ttu-id="3e3a8-110">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3e3a8-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e3a8-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3e3a8-111">Remarks</span></span>  
 <span data-ttu-id="3e3a8-112">Wenn einer der Operanden NULL ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-112">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3e3a8-113">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3e3a8-113">Expression Examples</span></span>  
 <span data-ttu-id="3e3a8-114">In diesem Beispiel werden numerische Literale addiert.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-114">This example adds numeric literals.</span></span>  
  
```  
5 + 6.09 + 7.0  
```  
  
 <span data-ttu-id="3e3a8-115">In diesem Beispiel werden Werte in den Spalten **VacationHours** und **SickLeaveHours** addiert.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-115">This example adds values in the **VacationHours** and **SickLeaveHours** columns.</span></span>  
  
```  
VacationHours + SickLeaveHours  
```  
  
 <span data-ttu-id="3e3a8-116">In diesem Beispiel wird ein berechneter Wert zur **StandardCost** -Spalte addiert.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-116">This example adds a calculated value to the **StandardCost** column.</span></span> <span data-ttu-id="3e3a8-117">Die **Profit%** -Variable muss in eckige Klammern eingeschlossen werden, weil der Name das Zeichen % enthält.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-117">The variable **Profit%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="3e3a8-118">Weitere Informationen finden Sie unter [Bezeichner &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="3e3a8-118">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
StandardCost + (StandardCost * @[Profit%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e3a8-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e3a8-119">See Also</span></span>  
 <span data-ttu-id="3e3a8-120">[Operatorenrangfolge und -assoziativität](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="3e3a8-120">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="3e3a8-121">Operatoren &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3a8-121">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
