---
title: FINDSTRING (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FINDSTRING function
ms.assetid: c83cb1b1-3c52-4496-b518-4c9253b9336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72f2ff21cb179ce565e60c6550b8ecc2618a5adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617202"
---
# <a name="findstring-ssis-expression"></a><span data-ttu-id="81940-102">FINDSTRING (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="81940-102">FINDSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="81940-103">Gibt den Speicherort für das angegebene Auftreten einer Zeichenfolge innerhalb eines Zeichenausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="81940-103">Returns the location of the specified occurrence of a string within a character expression.</span></span> <span data-ttu-id="81940-104">Das Ergebnis ist der einsbasierte Index für das Auftreten.</span><span class="sxs-lookup"><span data-stu-id="81940-104">The return result is the one-based index of the occurrence.</span></span> <span data-ttu-id="81940-105">Der string-Parameter muss zu einem Zeichenausdruck und der occurrence-Parameter zu einer ganzen Zahl ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="81940-105">The string parameter must evaluate to a character expression, and the occurrence parameter must evaluate to an integer.</span></span> <span data-ttu-id="81940-106">Wenn die Zeichenfolge nicht gefunden wird, wird 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-106">If the string is not found, the return value is 0.</span></span> <span data-ttu-id="81940-107">Wenn die Zeichenfolge weniger auftritt als im occurrence-Argument angegeben, wird ebenfalls 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-107">If the string occurs fewer times than the occurrence argument specifies, the return value is 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81940-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="81940-108">Syntax</span></span>  
  
```  
  
FINDSTRING(character_expression, searchstring, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="81940-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="81940-109">Arguments</span></span>  
 <span data-ttu-id="81940-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="81940-110">*character_expression*</span></span>  
 <span data-ttu-id="81940-111">Die Zeichenfolge, in der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="81940-111">Is the character string to search in.</span></span>  
  
 <span data-ttu-id="81940-112">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="81940-112">*searchstring*</span></span>  
 <span data-ttu-id="81940-113">Die Zeichenfolge, nach der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="81940-113">Is the character string to search for.</span></span>  
  
 <span data-ttu-id="81940-114">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="81940-114">*occurrence*</span></span>  
 <span data-ttu-id="81940-115">Eine ganze Zahl mit oder ohne Vorzeichen, die angibt, welches Auftreten von *searchstring* gemeldet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81940-115">Is a signed or unsigned integer specifying which occurrence of *searchstring* to report.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="81940-116">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="81940-116">Result Types</span></span>  
 <span data-ttu-id="81940-117">DT_I4</span><span class="sxs-lookup"><span data-stu-id="81940-117">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81940-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="81940-118">Remarks</span></span>  
 <span data-ttu-id="81940-119">FINDSTRING kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81940-119">FINDSTRING works only with the DT_WSTR data type.</span></span>  <span data-ttu-id="81940-120">Das*character_expression* -Argument und das *searchstring* -Argument, die Zeichenfolgenliterale oder Datenspalten mit dem DT_STR-Datentyp sind, werden implizit in den DT_WSTR-Datentyp umgewandelt, bevor FINDSTRING die Operation ausführt.</span><span class="sxs-lookup"><span data-stu-id="81940-120">*character_expression* and *searchstring* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before FINDSTRING performs its operation.</span></span> <span data-ttu-id="81940-121">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="81940-121">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="81940-122">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="81940-122">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="81940-123">FINDSTRING gibt NULL zurück, wenn *character_expression* oder *searchstring* NULL sind.</span><span class="sxs-lookup"><span data-stu-id="81940-123">FINDSTRING returns null if either *character_expression* or *searchstring* are null.</span></span>  
  
 <span data-ttu-id="81940-124">Verwenden Sie den Wert 1 für das *occurrence* -Argument, um den Index des ersten Vorkommens abzurufen, 2 für das zweite Vorkommen usw.</span><span class="sxs-lookup"><span data-stu-id="81940-124">Use a value of 1 in the *occurrence* argument to get the index of the first occurrence, 2 for the second occurrence and so forth.</span></span>  
  
 <span data-ttu-id="81940-125">*occurrence* muss eine ganze Zahl mit einem Wert größer als 0 sein.</span><span class="sxs-lookup"><span data-stu-id="81940-125">The *occurrence* must be an integer with a value greater than 0.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="81940-126">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="81940-126">Expression Examples</span></span>  
 <span data-ttu-id="81940-127">In diesem Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="81940-127">This example uses a string literal.</span></span> <span data-ttu-id="81940-128">Der Wert 11 wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-128">It returns the value 11.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 1)   
```  
  
 <span data-ttu-id="81940-129">In diesem Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="81940-129">This example uses a string literal.</span></span> <span data-ttu-id="81940-130">Da die Zeichenfolge "NY" nur zweimal auftritt, wird 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-130">Because the string "NY" occurs only two times, the return result is 0.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 3)   
```  
  
 <span data-ttu-id="81940-131">In diesem Beispiel wird die **Name** -Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="81940-131">This example uses the **Name** column.</span></span> <span data-ttu-id="81940-132">Der Speicherort des Werts n in der **Name** -Spalte wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-132">It returns the location of the value n in the **Name** column.</span></span> <span data-ttu-id="81940-133">Das Ergebnis hängt vom Wert in **Name**ab.</span><span class="sxs-lookup"><span data-stu-id="81940-133">The return result varies depending on the value in **Name**.</span></span> <span data-ttu-id="81940-134">Wenn die **Name** -Spalte „Anderson“ enthält, gibt die Funktion den Wert 8 zurück.</span><span class="sxs-lookup"><span data-stu-id="81940-134">If **Name** contains Anderson, the function returns 8.</span></span>  
  
```  
FINDSTRING(Name,"n", 2)   
```  
  
 <span data-ttu-id="81940-135">In diesem Beispiel werden die Spalten **Name** und **Size** verwendet.</span><span class="sxs-lookup"><span data-stu-id="81940-135">This example uses the **Name** and **Size** columns.</span></span> <span data-ttu-id="81940-136">Der Speicherort des äußeren linken Zeichens des **Size** -Arguments in der **Name** -Spalte wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-136">It returns the location of the leftmost character of the **Size** value in the **Name** column.</span></span> <span data-ttu-id="81940-137">Das Ergebnis hängt von den Spaltenwerten ab.</span><span class="sxs-lookup"><span data-stu-id="81940-137">The return result varies depending on column values.</span></span> <span data-ttu-id="81940-138">Falls **Name** „Mountain,500Red,42“ und **Size** „42“ enthält, wird 17 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81940-138">If **Name** contains Mountain,500Red,42 and **Size** contains 42, the return result is 17.</span></span>  
  
```  
FINDSTRING(Name,Size,1)   
```  
  
## <a name="see-also"></a><span data-ttu-id="81940-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81940-139">See Also</span></span>  
 <span data-ttu-id="81940-140">[REPLACE &#40;SSIS-Ausdruck&#41;](replace-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="81940-140">[REPLACE &#40;SSIS Expression&#41;](replace-ssis-expression.md) </span></span>  
 [<span data-ttu-id="81940-141">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="81940-141">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
