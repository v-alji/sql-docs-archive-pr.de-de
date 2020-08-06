---
title: HEX (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- hexadecimal data
- HEX function
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 640ae38ec5d2cd5ffb448e9aebde5ba5ceba2684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721650"
---
# <a name="hex-ssis-expression"></a><span data-ttu-id="7dedb-102">HEX (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="7dedb-102">HEX (SSIS Expression)</span></span>
  <span data-ttu-id="7dedb-103">Gibt eine Zeichenfolge zurück, die den hexadezimalen Wert einer ganzen Zahl darstellt.</span><span class="sxs-lookup"><span data-stu-id="7dedb-103">Returns a string representing the hexadecimal value of an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dedb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dedb-104">Syntax</span></span>  
  
```  
  
HEX(integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dedb-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7dedb-105">Arguments</span></span>  
 <span data-ttu-id="7dedb-106">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="7dedb-106">*integer_expression*</span></span>  
 <span data-ttu-id="7dedb-107">Eine ganze Zahl mit oder ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="7dedb-107">Is a signed or unsigned integer.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7dedb-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="7dedb-108">Result Types</span></span>  
 <span data-ttu-id="7dedb-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7dedb-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dedb-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7dedb-110">Remarks</span></span>  
 <span data-ttu-id="7dedb-111">HEX gibt NULL zurück, wenn *integer_expression* NULL ist.</span><span class="sxs-lookup"><span data-stu-id="7dedb-111">HEX returns null if *integer_expression* is null.</span></span>  
  
 <span data-ttu-id="7dedb-112">Das *integer_expression* -Argument muss zu einer ganzen Zahl ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="7dedb-112">The *integer_expression* argument must evaluate to an integer.</span></span> <span data-ttu-id="7dedb-113">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7dedb-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="7dedb-114">Das zurückgegebene Ergebnis schließt keine Qualifizierer ein, wie z. B. das 0x-Präfix.</span><span class="sxs-lookup"><span data-stu-id="7dedb-114">The return result does not include qualifiers such as the 0x prefix.</span></span> <span data-ttu-id="7dedb-115">Verwenden Sie den + (Verketten)-Operator, um ein Präfix einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7dedb-115">To include a prefix, use the + (Concatenate) operator.</span></span> <span data-ttu-id="7dedb-116">Weitere Informationen finden Sie unter [+ &#40;Verketten, SSIS-Ausdruck&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="7dedb-116">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="7dedb-117">Die Buchstaben A bis F, die für die HEX-Schreibweise verwendet werden, werden in Großbuchstaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7dedb-117">The letters A - F, used in HEX notations, appear as uppercase characters.</span></span>  
  
 <span data-ttu-id="7dedb-118">Integer-Datentypen weisen für die sich ergebende Zeichenfolge die folgende Länge auf:</span><span class="sxs-lookup"><span data-stu-id="7dedb-118">The length of the resulting string for integer data types is as follows:</span></span>  
  
-   <span data-ttu-id="7dedb-119">DT_I1 und DT_UI1 geben eine Zeichenfolge mit einer maximalen Länge von 2 zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-119">DT_I1 and DT_UI1 return a string with a maximum length of 2.</span></span>  
  
-   <span data-ttu-id="7dedb-120">DT_I2 und DT_UI2 geben eine Zeichenfolge mit einer maximalen Länge von 4 zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-120">DT_I2 and DT_UI2 return a string with a maximum length of 4.</span></span>  
  
-   <span data-ttu-id="7dedb-121">DT_I4 und DT_UI4 geben eine Zeichenfolge mit einer maximalen Länge von 8 zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-121">DT_I4 and DT_UI4 return a string with a maximum length of 8.</span></span>  
  
-   <span data-ttu-id="7dedb-122">DT_I8 und DT_UI8 geben eine Zeichenfolge mit einer maximalen Länge von 16 zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-122">DT_I8 and DT_UI8 return a string with a maximum length of 16.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7dedb-123">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7dedb-123">Expression Examples</span></span>  
 <span data-ttu-id="7dedb-124">In diesem Beispiel wird ein numerisches Literal verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dedb-124">This example uses a numeric literal.</span></span> <span data-ttu-id="7dedb-125">Die Funktion gibt den Wert 190 zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-125">The function returns the value 190.</span></span>  
  
```  
HEX(400)   
```  
  
 <span data-ttu-id="7dedb-126">In diesem Beispiel wird die **ReorderPoint** -Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dedb-126">This example uses the **ReorderPoint** column.</span></span> <span data-ttu-id="7dedb-127">Der Datentyp der Spalte ist `smallint`.</span><span class="sxs-lookup"><span data-stu-id="7dedb-127">The column data type is `smallint`.</span></span> <span data-ttu-id="7dedb-128">Falls **ReorderPoint** gleich 750 ist, gibt die Funktion 2EE zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-128">If **ReorderPoint** is 750, the function returns 2EE.</span></span>  
  
```  
HEX(ReorderPoint)   
```  
  
 <span data-ttu-id="7dedb-129">In diesem Beispiel wird **LocaleID**als Systemvariable verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dedb-129">This example uses **LocaleID**, a system variable.</span></span> <span data-ttu-id="7dedb-130">Falls **LocaleID** gleich 1033 ist, gibt die Funktion 409 zurück.</span><span class="sxs-lookup"><span data-stu-id="7dedb-130">If **LocaleID** is 1033, the function returns 409.</span></span>  
  
```  
HEX(@LocaleID)  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dedb-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7dedb-131">See Also</span></span>  
 [<span data-ttu-id="7dedb-132">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="7dedb-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
