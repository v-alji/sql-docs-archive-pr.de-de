---
title: SIGN (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a34992b0029cd378274e38ce4e37fcd313d2b788
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701390"
---
# <a name="sign-ssis-expression"></a><span data-ttu-id="94b60-102">SIGN (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="94b60-102">SIGN (SSIS Expression)</span></span>
  <span data-ttu-id="94b60-103">Gibt das positive (+1) oder negative (-1) Vorzeichen oder Null (0) für einen numerischen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="94b60-103">Returns the positive (+1), negative (-1), or zero (0) sign of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94b60-104">Syntax</span></span>  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="94b60-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="94b60-105">Arguments</span></span>  
 <span data-ttu-id="94b60-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="94b60-106">*numeric_expression*</span></span>  
 <span data-ttu-id="94b60-107">Ein gültiger numerischer Ausdruck mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="94b60-107">Is a valid signed numeric expression.</span></span> <span data-ttu-id="94b60-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="94b60-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="94b60-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="94b60-109">Result Types</span></span>  
 <span data-ttu-id="94b60-110">DT_I4</span><span class="sxs-lookup"><span data-stu-id="94b60-110">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94b60-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="94b60-111">Remarks</span></span>  
 <span data-ttu-id="94b60-112">SIGN gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="94b60-112">SIGN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="94b60-113">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="94b60-113">Expression Examples</span></span>  
 <span data-ttu-id="94b60-114">In diesem Beispiel wird das Vorzeichen eines numerischen Literals zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94b60-114">This example returns the sign of a numeric literal.</span></span> <span data-ttu-id="94b60-115">Als Ergebnis wird -1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94b60-115">The return result is -1.</span></span>  
  
```  
SIGN(-123.45)  
```  
  
 <span data-ttu-id="94b60-116">In diesem Beispiel wird das Vorzeichen aus der Subtraktion der **StandardCost** -Spalte von der **DealerPrice** -Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94b60-116">This example returns the sign of the result of subtracting the **StandardCost** column from the **DealerPrice** column.</span></span>  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a><span data-ttu-id="94b60-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94b60-117">See Also</span></span>  
 [<span data-ttu-id="94b60-118">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="94b60-118">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
