---
title: REPLICATE (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9502df5bc20c6ad85f1f98fb57fe6b3cf431cc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701414"
---
# <a name="replicate-ssis-expression"></a><span data-ttu-id="51f57-102">REPLICATE (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="51f57-102">REPLICATE (SSIS Expression)</span></span>
  <span data-ttu-id="51f57-103">Gibt einen Zeichenausdruck zurück, der mehrfach repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="51f57-103">Returns a character expression that is replicated a number of times.</span></span> <span data-ttu-id="51f57-104">Das *times* -Argument muss zu einer ganzen Zahl ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="51f57-104">The *times* argument must evaluate to an integer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51f57-105">Die REPLICATE-Funktion verwendet häufig lange Zeichenfolgen und wird daher eher Probleme mit der auf 4.000 Zeichen beschränkten Länge von Ausdrücken verursachen.</span><span class="sxs-lookup"><span data-stu-id="51f57-105">The REPLICATE function frequently uses long strings, and therefore is more likely to incur the 4000-character limit on expression length.</span></span> <span data-ttu-id="51f57-106">Hat das Auswertungsergebnis eines Ausdrucks den Integration Services-Datentyp DT_WSTR oder DT_STR, wird der Ausdruck nach 4.000 Zeichen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="51f57-106">If the evaluation result of an expression has the Integration Services data type DT_WSTR or DT_STR, the expression will be truncated at 4000 characters.</span></span> <span data-ttu-id="51f57-107">Ist der Ergebnistyp eines Unterausdrucks DT_STR oder DT_WSTR, wird dieser Unterausdruck unabhängig vom Ergebnistyp des Gesamtausdrucks ebenfalls nach 4.000 Zeichen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="51f57-107">If the result type of a sub-expression is DT_STR or DT_WSTR, that sub-expression likewise will be truncated to 4000 characters, regardless of the overall expression result type.</span></span> <span data-ttu-id="51f57-108">Die Folgen der Kürzung können unauffällig behandelt werden oder eine Warnung oder einen Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="51f57-108">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="51f57-109">Weitere Informationen finden Sie unter [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="51f57-109">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f57-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="51f57-110">Syntax</span></span>  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a><span data-ttu-id="51f57-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="51f57-111">Arguments</span></span>  
 <span data-ttu-id="51f57-112">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="51f57-112">*character_expression*</span></span>  
 <span data-ttu-id="51f57-113">Ein Zeichenausdruck, der repliziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="51f57-113">Is a character expression to replicate.</span></span>  
  
 <span data-ttu-id="51f57-114">*times*</span><span class="sxs-lookup"><span data-stu-id="51f57-114">*times*</span></span>  
 <span data-ttu-id="51f57-115">Eine ganzzahliger Ausdruck, der angibt, wie oft *character_expression* repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="51f57-115">Is an integer expression that specifies the number of times *character_expression* is replicated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="51f57-116">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="51f57-116">Result Types</span></span>  
 <span data-ttu-id="51f57-117">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="51f57-117">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51f57-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="51f57-118">Remarks</span></span>  
 <span data-ttu-id="51f57-119">Falls *times* null ist, gibt die Funktion eine leere Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="51f57-119">If *times* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="51f57-120">Falls *times* eine negative Zahl ist, gibt die Funktion einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="51f57-120">If *times* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="51f57-121">Für das *times* -Argument sind auch Variablen und Spalten möglich.</span><span class="sxs-lookup"><span data-stu-id="51f57-121">The *times* argument can also use variables and columns.</span></span>  
  
 <span data-ttu-id="51f57-122">REPLICATE kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51f57-122">REPLICATE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="51f57-123">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor REPLICATE ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="51f57-123">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before REPLICATE performs its operation.</span></span> <span data-ttu-id="51f57-124">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="51f57-124">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="51f57-125">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="51f57-125">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="51f57-126">REPLICATE gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.</span><span class="sxs-lookup"><span data-stu-id="51f57-126">REPLICATE returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="51f57-127">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="51f57-127">Expression Examples</span></span>  
 <span data-ttu-id="51f57-128">In diesem Beispiel wird ein Zeichenfolgenliteral dreimal repliziert.</span><span class="sxs-lookup"><span data-stu-id="51f57-128">This example replicates a string literal three times.</span></span> <span data-ttu-id="51f57-129">Als Ergebnis wird "Mountain BikeMountain BikeMountain Bike" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51f57-129">The return result is "Mountain BikeMountain BikeMountain Bike".</span></span>  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 <span data-ttu-id="51f57-130">In diesem Beispiel werden Werte in der **Name** -Spalte mit dem Wert in der **Times** -Variablen repliziert.</span><span class="sxs-lookup"><span data-stu-id="51f57-130">This example replicates values in the **Name** column by the value in the **Times** variable.</span></span> <span data-ttu-id="51f57-131">Falls **Times** 3 und **Name** Touring Front Wheel ist, wird als Ergebnis Touring Front WheelTouring Front WheelTouring Front Wheel zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51f57-131">If **Times** is 3 and **Name** is Touring Front Wheel, the return result is Touring Front WheelTouring Front WheelTouring Front Wheel.</span></span>  
  
```  
REPLICATE(Name, @Times)  
```  
  
 <span data-ttu-id="51f57-132">In diesem Beispiel wird der Wert in der **Name** -Variablen mit dem Wert in der **Times** -Spalte repliziert.</span><span class="sxs-lookup"><span data-stu-id="51f57-132">This example replicates the value in the **Name** variable by the value in the **Times** column.</span></span> <span data-ttu-id="51f57-133">**Times** weist einen nicht ganzzahligen Datentyp auf, und der Ausdruck schließt eine explizite Umwandlung in einen ganzzahligen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="51f57-133">**Times** has a non-integer data type and the expression includes an explicit cast to an integer data type.</span></span> <span data-ttu-id="51f57-134">Falls **Name** Helmet einschließt und **Times** 2 ist, wird als Ergebnis "HelmetHelmet" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51f57-134">If **Name** contains Helmet and **Times** is 2, the return result is "HelmetHelmet".</span></span>  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="51f57-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51f57-135">See Also</span></span>  
 [<span data-ttu-id="51f57-136">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="51f57-136">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
