---
title: REVERSE (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701409"
---
# <a name="reverse-ssis-expression"></a><span data-ttu-id="53e56-102">REVERSE (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="53e56-102">REVERSE (SSIS Expression)</span></span>
  <span data-ttu-id="53e56-103">Gibt einen Zeichenausdruck in umgekehrter Reihenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="53e56-103">Returns a character expression in reverse order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53e56-104">Syntax</span></span>  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="53e56-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="53e56-105">Arguments</span></span>  
 <span data-ttu-id="53e56-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="53e56-106">*character_expression*</span></span>  
 <span data-ttu-id="53e56-107">Der Zeichenausdruck, dessen Reihenfolge umgekehrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="53e56-107">Is a character expression to be reversed.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="53e56-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="53e56-108">Result Types</span></span>  
 <span data-ttu-id="53e56-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="53e56-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53e56-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="53e56-110">Remarks</span></span>  
 <span data-ttu-id="53e56-111">Das *character_expression* -Argument muss den Datentyp „DT_WSTR“ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="53e56-111">The *character_expression* argument must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="53e56-112">REVERSE gibt ein NULL-Ergebnis zurück, wenn *character_expression* NULL ist.</span><span class="sxs-lookup"><span data-stu-id="53e56-112">REVERSE returns a null result if *character_expression* is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="53e56-113">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="53e56-113">Expression Examples</span></span>  
 <span data-ttu-id="53e56-114">In diesem Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="53e56-114">This example uses a string literal.</span></span> <span data-ttu-id="53e56-115">Als Ergebnis wird "ekiB niatnuoM" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53e56-115">The return result is "ekiB niatnuoM".</span></span>  
  
```  
REVERSE("Mountain Bike")  
```  
  
 <span data-ttu-id="53e56-116">In diesem Beispiel wird eine Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="53e56-116">This example uses a variable.</span></span> <span data-ttu-id="53e56-117">Falls **Name** Touring Bike enthält, wird als Ergebnis "ekiB gniruoT" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53e56-117">If **Name** contains Touring Bike, the return result is "ekiB gniruoT".</span></span>  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="53e56-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53e56-118">See Also</span></span>  
 [<span data-ttu-id="53e56-119">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="53e56-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
