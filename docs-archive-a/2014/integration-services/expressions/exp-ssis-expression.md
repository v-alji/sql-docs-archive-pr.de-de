---
title: EXP (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exponential functions
- EXP function
ms.assetid: 4cd96d3c-58c9-4a67-a6f6-b72758232912
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 150c92355ab3e0d3a028c98defe2e2fa9a1bf8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618783"
---
# <a name="exp-ssis-expression"></a><span data-ttu-id="f7aff-102">EXP (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f7aff-102">EXP (SSIS Expression)</span></span>
  <span data-ttu-id="f7aff-103">Gibt den Exponenten für die Basis e eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="f7aff-103">Returns the exponent to base e of a numeric expression.</span></span> <span data-ttu-id="f7aff-104">Die EXP-Funktion ergänzt die Aktion der LN-Funktion und wird auch als Antilogarithmus bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f7aff-104">The EXP function complements the action of the LN function and is sometimes referred to as the antilogarithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7aff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7aff-105">Syntax</span></span>  
  
```  
  
EXP(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f7aff-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f7aff-106">Arguments</span></span>  
 <span data-ttu-id="f7aff-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="f7aff-107">*numeric_expression*</span></span>  
 <span data-ttu-id="f7aff-108">Ein gültiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f7aff-108">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f7aff-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="f7aff-109">Result Types</span></span>  
 <span data-ttu-id="f7aff-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="f7aff-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7aff-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f7aff-111">Remarks</span></span>  
 <span data-ttu-id="f7aff-112">Der numerische Ausdruck wird in den DT_R8-Datentyp umgewandelt, bevor der Exponent berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="f7aff-112">The numeric expression is cast to the DT_R8 data type before the exponent is computed.</span></span> <span data-ttu-id="f7aff-113">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f7aff-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="f7aff-114">Als Ergebnis wird immer eine positive Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f7aff-114">The return result is always a positive number.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f7aff-115">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f7aff-115">Expression Examples</span></span>  
 <span data-ttu-id="f7aff-116">Diese Beispiele wenden die EXP-Funktion auf positive und negative Werte und auf Null an.</span><span class="sxs-lookup"><span data-stu-id="f7aff-116">These examples apply the EXP function to positive and negative values and to zero.</span></span>  
  
```  
EXP(74)  
```  
  
 <span data-ttu-id="f7aff-117">Gibt 1.373382979540176E+32 zurück.</span><span class="sxs-lookup"><span data-stu-id="f7aff-117">Returns 1.373382979540176E+32.</span></span>  
  
```  
EXP(-27)  
```  
  
 <span data-ttu-id="f7aff-118">Gibt 1.879528816539083E-12 zurück.</span><span class="sxs-lookup"><span data-stu-id="f7aff-118">Returns 1.879528816539083E-12.</span></span>  
  
```  
EXP(0)  
```  
  
 <span data-ttu-id="f7aff-119">Gibt 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="f7aff-119">Returns 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7aff-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7aff-120">See Also</span></span>  
 <span data-ttu-id="f7aff-121">[LOG &#40;SSIS-Ausdruck&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f7aff-121">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="f7aff-122">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="f7aff-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
