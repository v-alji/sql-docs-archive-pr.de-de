---
title: ABS (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619978"
---
# <a name="abs-ssis-expression"></a><span data-ttu-id="2d89e-102">ABS (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2d89e-102">ABS (SSIS Expression)</span></span>
  <span data-ttu-id="2d89e-103">Gibt den absoluten, positiven Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="2d89e-103">Returns the absolute, positive value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d89e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d89e-104">Syntax</span></span>  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d89e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2d89e-105">Arguments</span></span>  
 <span data-ttu-id="2d89e-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="2d89e-106">*numeric_expression*</span></span>  
 <span data-ttu-id="2d89e-107">Ein numerischer Ausdruck mit oder ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="2d89e-107">Is a signed or unsigned numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2d89e-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="2d89e-108">Result Types</span></span>  
 <span data-ttu-id="2d89e-109">Der Datentyp des numerischen Ausdrucks, der an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d89e-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d89e-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2d89e-110">Remarks</span></span>  
 <span data-ttu-id="2d89e-111">ABS gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="2d89e-111">ABS returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2d89e-112">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2d89e-112">Expression Examples</span></span>  
 <span data-ttu-id="2d89e-113">In diesen Beispielen wird die ABS-Funktion auf eine positive und eine negative Zahl angewendet.</span><span class="sxs-lookup"><span data-stu-id="2d89e-113">These examples apply the ABS function to a positive and a negative number.</span></span> <span data-ttu-id="2d89e-114">In beiden Fällen wird 1.23 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d89e-114">Both return 1.23.</span></span>  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 <span data-ttu-id="2d89e-115">In diesem Beispiel wird die ABS-Funktion auf einen Ausdruck angewendet, der Werte in den Variablen **HighTemperature** und **LowTempature**subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="2d89e-115">This example applies the ABS function to an expression that subtracts values in the variables **HighTemperature** and **LowTempature**.</span></span>  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d89e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d89e-116">See Also</span></span>  
 [<span data-ttu-id="2d89e-117">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="2d89e-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
