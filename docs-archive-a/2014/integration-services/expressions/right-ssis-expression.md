---
title: RIGHT (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2584ee33ecbf0436c4e3dc6e92b957e60ae396ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701408"
---
# <a name="right-ssis-expression"></a><span data-ttu-id="32a15-102">RIGHT (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="32a15-102">RIGHT (SSIS Expression)</span></span>
  <span data-ttu-id="32a15-103">Gibt die angegebene Anzahl von Zeichen ab der äußersten rechten Position des angegebenen Zeichenausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="32a15-103">Returns the specified number of characters from the rightmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32a15-104">Syntax</span></span>  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="32a15-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="32a15-105">Arguments</span></span>  
 <span data-ttu-id="32a15-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="32a15-106">*character_expression*</span></span>  
 <span data-ttu-id="32a15-107">Ein Zeichenausdruck, von dem Zeichen extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="32a15-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="32a15-108">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="32a15-108">*integer_expression*</span></span>  
 <span data-ttu-id="32a15-109">Ein ganzzahliger Ausdruck, der die Anzahl der zurückzugebenden Zeichen angibt.</span><span class="sxs-lookup"><span data-stu-id="32a15-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="32a15-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="32a15-110">Result Types</span></span>  
 <span data-ttu-id="32a15-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="32a15-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32a15-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="32a15-112">Remarks</span></span>  
 <span data-ttu-id="32a15-113">Wenn *integer_expression* größer ist als die Länge von *character_expression*, gibt die Funktion *character_expression*zurück.</span><span class="sxs-lookup"><span data-stu-id="32a15-113">If *integer_expression* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="32a15-114">Falls *integer_expression* null ist, gibt die Funktion eine leere Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="32a15-114">If *integer_expression* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="32a15-115">Falls *integer_expression* eine negative Zahl ist, gibt die Funktion einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="32a15-115">If *integer_expression* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="32a15-116">Für das *integer_expression* -Argument sind Variablen und Spalten möglich.</span><span class="sxs-lookup"><span data-stu-id="32a15-116">The *integer_expression* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="32a15-117">RIGHT kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="32a15-117">RIGHT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="32a15-118">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor RIGHT ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32a15-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RIGHT performs its operation.</span></span> <span data-ttu-id="32a15-119">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="32a15-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="32a15-120">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="32a15-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="32a15-121">RIGHT gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.</span><span class="sxs-lookup"><span data-stu-id="32a15-121">RIGHT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="32a15-122">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="32a15-122">Expression Examples</span></span>  
 <span data-ttu-id="32a15-123">Im folgenden Beispiel wird ein Zeichenfolgenliteral verwendet.</span><span class="sxs-lookup"><span data-stu-id="32a15-123">The following example uses a string literal.</span></span> <span data-ttu-id="32a15-124">Als Ergebnis wird `"Bike"`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32a15-124">The return result is `"Bike"`.</span></span>  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 <span data-ttu-id="32a15-125">Im folgenden Beispiel wird die in der `Times` -Variablen angegebene Anzahl der äußersten rechten Zeichen aus der `Name` -Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32a15-125">The following example returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="32a15-126">Wenn `Name` den Wert `Touring Front Wheel` und `Times` den Wert 5 hat, wird als Ergebnis `"Wheel"`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32a15-126">If `Name` is `Touring Front Wheel` and `Times` is 5, the return result is `"Wheel"`.</span></span>  
  
```  
RIGHT(Name, @Times)  
```  
  
 <span data-ttu-id="32a15-127">Im folgenden Beispiel wird auch die in der `Times` -Variablen angegebene Anzahl der äußersten rechten Zeichen aus der `Name` -Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32a15-127">The following example also returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="32a15-128">`Times` weist einen anderen Datentyp als integer auf, und der Ausdruck umfasst eine explizite Umwandlung in den DT_I2-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="32a15-128">`Times` has a noninteger data type and the expression includes an explicit cast to the DT_I2 data type.</span></span> <span data-ttu-id="32a15-129">Wenn `Name` den Wert `Touring Front Wheel` und `Times` den Wert `4.32`hat, wird als Ergebnis `"heel"` zurückgegeben, da die RIGHT-Funktion den Wert 4.32 in 4 umwandelt und dann die äußersten rechten vier Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="32a15-129">If `Name` is `Touring Front Wheel` and `Times` is `4.32`, the return result is `"heel"` because the RIGHT function converts the value of 4.32 to 4, and then returns the rightmost four characters.</span></span>  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="32a15-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32a15-130">See Also</span></span>  
 <span data-ttu-id="32a15-131">[LEFT &#40;SSIS-Ausdruck&#41;](left-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="32a15-131">[LEFT &#40;SSIS Expression&#41;](left-ssis-expression.md) </span></span>  
 [<span data-ttu-id="32a15-132">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="32a15-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
