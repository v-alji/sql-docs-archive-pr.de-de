---
title: CODEPOINT (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf05cc0838763ba9e22707af57892133d449da07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608761"
---
# <a name="codepoint-ssis-expression"></a><span data-ttu-id="28217-102">CODEPOINT (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="28217-102">CODEPOINT (SSIS Expression)</span></span>
  <span data-ttu-id="28217-103">Gibt das Unicode-Codeelement des äußeren linken Zeichens eines Zeichenausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="28217-103">Returns the Unicode code point of the leftmost character of a character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28217-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28217-104">Syntax</span></span>  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="28217-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="28217-105">Arguments</span></span>  
 <span data-ttu-id="28217-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="28217-106">*character_expression*</span></span>  
 <span data-ttu-id="28217-107">Ein Zeichenausdruck, dessen äußeres linkes Zeichen ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="28217-107">Is a character expression whose leftmost character will be evaluated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="28217-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="28217-108">Result Types</span></span>  
 <span data-ttu-id="28217-109">DT_UI2</span><span class="sxs-lookup"><span data-stu-id="28217-109">DT_UI2</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28217-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="28217-110">Remarks</span></span>  
 <span data-ttu-id="28217-111">*character_expression* muss den Datentyp „DT_WSTR“ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="28217-111">*character_expression* must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="28217-112">CODEPOINT gibt ein NULL-Ergebnis zurück, wenn *character_expression* NULL oder eine leere Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="28217-112">CODEPOINT returns a null result if *character_expression* is null or an empty string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="28217-113">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="28217-113">Expression Examples</span></span>  
 <span data-ttu-id="28217-114">In diesem Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="28217-114">This example uses a string literal.</span></span> <span data-ttu-id="28217-115">Als Ergebnis wird 77 zurückgegeben, das Unicode-Codeelement für M.</span><span class="sxs-lookup"><span data-stu-id="28217-115">The return result is 77, the Unicode code point for M.</span></span>  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 <span data-ttu-id="28217-116">In diesem Beispiel wird eine Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="28217-116">This example uses a variable.</span></span> <span data-ttu-id="28217-117">Falls **Name** Touring Front Wheel ist, wird als Ergebnis 84 zurückgegeben, das Unicode-Codeelement für T.</span><span class="sxs-lookup"><span data-stu-id="28217-117">If **Name** is Touring Front Wheel, the return result is 84, the Unicode code point for T.</span></span>  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="28217-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28217-118">See Also</span></span>  
 [<span data-ttu-id="28217-119">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="28217-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
