---
title: SUBSTRING (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SUBSTRING function
- part of expression returned [Integration Services]
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba53676bc6d13ed34892f48fca3b70372cb30604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701355"
---
# <a name="substring-ssis-expression"></a><span data-ttu-id="6add4-102">SUBSTRING (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="6add4-102">SUBSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="6add4-103">Gibt den Teil eines Zeichenausdrucks zurück, der an der angegebenen Position beginnt und die angegebene Länge besitzt.</span><span class="sxs-lookup"><span data-stu-id="6add4-103">Returns the part of a character expression that starts at the specified position and has the specified length.</span></span> <span data-ttu-id="6add4-104">Der *position* -Parameter und der *length* -Parameter müssen zu einer ganzen Zahl ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="6add4-104">The *position* parameter and the *length* parameter must evaluate to integers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6add4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6add4-105">Syntax</span></span>  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="6add4-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="6add4-106">Arguments</span></span>  
 <span data-ttu-id="6add4-107">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="6add4-107">*character_expression*</span></span>  
 <span data-ttu-id="6add4-108">Ein Zeichenausdruck, von dem Zeichen extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6add4-108">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="6add4-109">*position*</span><span class="sxs-lookup"><span data-stu-id="6add4-109">*position*</span></span>  
 <span data-ttu-id="6add4-110">Eine ganze Zahl, die den Beginn der Teilzeichenfolge angibt.</span><span class="sxs-lookup"><span data-stu-id="6add4-110">Is an integer that specifies where the substring begins.</span></span>  
  
 <span data-ttu-id="6add4-111">*length*</span><span class="sxs-lookup"><span data-stu-id="6add4-111">*length*</span></span>  
 <span data-ttu-id="6add4-112">Eine ganze Zahl, die die Länge der Teilzeichenfolge als Anzahl von Zeichen angibt.</span><span class="sxs-lookup"><span data-stu-id="6add4-112">Is an integer that specifies the length of the substring as number of characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6add4-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="6add4-113">Result Types</span></span>  
 <span data-ttu-id="6add4-114">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="6add4-114">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6add4-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6add4-115">Remarks</span></span>  
 <span data-ttu-id="6add4-116">SUBSTRING verwendet einen einsbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="6add4-116">SUBSTRING uses a one-based index.</span></span> <span data-ttu-id="6add4-117">Falls *position* 1 ist, beginnt die Teilzeichenfolge mit dem ersten Zeichen in *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="6add4-117">If *position* is 1, the substring begins with the first character in *character_expression*.</span></span>  
  
 <span data-ttu-id="6add4-118">SUBSTRING kann nur mit dem DT_WSTR-Datentyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6add4-118">SUBSTRING works only with the DT_WSTR data type.</span></span> <span data-ttu-id="6add4-119">Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor SUBSTRING ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6add4-119">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before SUBSTRING performs its operation.</span></span> <span data-ttu-id="6add4-120">Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6add4-120">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="6add4-121">Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="6add4-121">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="6add4-122">SUBSTRING gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="6add4-122">SUBSTRING returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="6add4-123">Für alle Argumente des Ausdrucks können Variablen und Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6add4-123">All arguments in the expression can use variables and columns.</span></span>  
  
 <span data-ttu-id="6add4-124">Das *length* -Argument kann länger als die Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="6add4-124">The *length* argument can exceed the length of the string.</span></span> <span data-ttu-id="6add4-125">In diesem Fall gibt die Funktion die restliche Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="6add4-125">In that case, the function returns the remainder of the string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6add4-126">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6add4-126">Expression Examples</span></span>  
 <span data-ttu-id="6add4-127">In diesem Beispiel werden zwei Zeichen eines Zeichenfolgenliterals zurückgegeben, und zwar beginnend mit Zeichen 4.</span><span class="sxs-lookup"><span data-stu-id="6add4-127">This example returns two characters, beginning with character 4, from a string literal.</span></span> <span data-ttu-id="6add4-128">Als Ergebnis wird "ph" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6add4-128">The return result is "ph".</span></span>  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 <span data-ttu-id="6add4-129">In diesem Beispiel wird der Rest eines Zeichenfolgenliterals zurückgegeben, und zwar beginnend mit dem vierten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6add4-129">This example returns the remainder of a string literal, beginning at the fourth character.</span></span> <span data-ttu-id="6add4-130">Als Ergebnis wird "phant" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6add4-130">The return result is "phant".</span></span> <span data-ttu-id="6add4-131">Es ist kein Fehler, wenn das *length* -Argument länger als die Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="6add4-131">It is not an error for the *length* argument to exceed the length of the string.</span></span>  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 <span data-ttu-id="6add4-132">In diesem Beispiel wird der erste Buchstabe der **MiddleName** -Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6add4-132">This example returns the first letter from the **MiddleName** column.</span></span>  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 <span data-ttu-id="6add4-133">In diesem Beispiel werden Variablen für die Argumente *position* und *length* verwendet.</span><span class="sxs-lookup"><span data-stu-id="6add4-133">This example uses variables in the *position* and *length* arguments.</span></span> <span data-ttu-id="6add4-134">Falls **Start** 1 und **Length** 5 ist, gibt die Funktion die ersten fünf Zeichen der **Name** -Spalte zurück.</span><span class="sxs-lookup"><span data-stu-id="6add4-134">If **Start** is 1 and **Length** is 5, the function returns the first five characters in the **Name** column.</span></span>  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 <span data-ttu-id="6add4-135">In diesem Beispiel werden die letzten vier Zeichen der **PostalCode** -Variable zurückgegeben, und zwar beginnend mit dem sechsten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6add4-135">This example returns the last four characters from the **PostalCode** variable beginning at the sixth character.</span></span>  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 <span data-ttu-id="6add4-136">In diesem Beispiel wird eine leere Zeichenfolge aus einem Zeichenfolgenliteral zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6add4-136">This example returns a zero-length string from a string literal.</span></span>  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="6add4-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6add4-137">See Also</span></span>  
 [<span data-ttu-id="6add4-138">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="6add4-138">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
