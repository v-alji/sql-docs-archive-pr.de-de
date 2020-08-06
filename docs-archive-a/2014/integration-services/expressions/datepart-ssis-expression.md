---
title: DATEPART (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aed7146c74c6738ba979f422bd65b7e1b539e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700064"
---
# <a name="datepart-ssis-expression"></a><span data-ttu-id="ed546-102">DATEPART (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="ed546-102">DATEPART (SSIS Expression)</span></span>
  <span data-ttu-id="ed546-103">Gibt eine ganze Zahl zurück, die einen datepart-Wert eines Datums darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed546-103">Returns an integer representing a datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed546-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed546-104">Syntax</span></span>  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ed546-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ed546-105">Arguments</span></span>  
 <span data-ttu-id="ed546-106">*datepart*</span><span class="sxs-lookup"><span data-stu-id="ed546-106">*datepart*</span></span>  
 <span data-ttu-id="ed546-107">Der Parameter, der angibt, für welche Datumseinheit ein neuer Wert zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed546-107">Is the parameter that specifies for which part of the date to return a new value.</span></span>  
  
 <span data-ttu-id="ed546-108">*date*</span><span class="sxs-lookup"><span data-stu-id="ed546-108">*date*</span></span>  
 <span data-ttu-id="ed546-109">Ein Ausdruck, der ein gültiges Datum oder eine Zeichenfolge im Datumsformat zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ed546-109">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ed546-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="ed546-110">Result Types</span></span>  
 <span data-ttu-id="ed546-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="ed546-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed546-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ed546-112">Remarks</span></span>  
 <span data-ttu-id="ed546-113">DATEPART gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ed546-113">DATEPART returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="ed546-114">Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ed546-114">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="ed546-115">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ed546-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ed546-116">In der folgenden Tabelle sind die datepart-Werte und Abkürzungen aufgeführt, die von der Ausdrucksauswertung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ed546-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="ed546-117">Bei datepart-Namen wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ed546-117">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="ed546-118">datepart</span><span class="sxs-lookup"><span data-stu-id="ed546-118">Datepart</span></span>|<span data-ttu-id="ed546-119">Abkürzungen</span><span class="sxs-lookup"><span data-stu-id="ed546-119">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="ed546-120">Jahr</span><span class="sxs-lookup"><span data-stu-id="ed546-120">Year</span></span>|<span data-ttu-id="ed546-121">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="ed546-121">yy, yyyy</span></span>|  
|<span data-ttu-id="ed546-122">Quarter</span><span class="sxs-lookup"><span data-stu-id="ed546-122">Quarter</span></span>|<span data-ttu-id="ed546-123">qq, q</span><span class="sxs-lookup"><span data-stu-id="ed546-123">qq, q</span></span>|  
|<span data-ttu-id="ed546-124">Month (Monat)</span><span class="sxs-lookup"><span data-stu-id="ed546-124">Month</span></span>|<span data-ttu-id="ed546-125">mm, m</span><span class="sxs-lookup"><span data-stu-id="ed546-125">mm, m</span></span>|  
|<span data-ttu-id="ed546-126">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="ed546-126">Dayofyear</span></span>|<span data-ttu-id="ed546-127">dy, y</span><span class="sxs-lookup"><span data-stu-id="ed546-127">dy, y</span></span>|  
|<span data-ttu-id="ed546-128">Day (Tag)</span><span class="sxs-lookup"><span data-stu-id="ed546-128">Day</span></span>|<span data-ttu-id="ed546-129">dd, d</span><span class="sxs-lookup"><span data-stu-id="ed546-129">dd, d</span></span>|  
|<span data-ttu-id="ed546-130">Week</span><span class="sxs-lookup"><span data-stu-id="ed546-130">Week</span></span>|<span data-ttu-id="ed546-131">wk, ww</span><span class="sxs-lookup"><span data-stu-id="ed546-131">wk, ww</span></span>|  
|<span data-ttu-id="ed546-132">Wochentag</span><span class="sxs-lookup"><span data-stu-id="ed546-132">Weekday</span></span>|<span data-ttu-id="ed546-133">dw</span><span class="sxs-lookup"><span data-stu-id="ed546-133">dw</span></span>|  
|<span data-ttu-id="ed546-134">Hour</span><span class="sxs-lookup"><span data-stu-id="ed546-134">Hour</span></span>|<span data-ttu-id="ed546-135">Hh</span><span class="sxs-lookup"><span data-stu-id="ed546-135">Hh</span></span>|  
|<span data-ttu-id="ed546-136">Minute</span><span class="sxs-lookup"><span data-stu-id="ed546-136">Minute</span></span>|<span data-ttu-id="ed546-137">mi, n</span><span class="sxs-lookup"><span data-stu-id="ed546-137">mi, n</span></span>|  
|<span data-ttu-id="ed546-138">Sekunde</span><span class="sxs-lookup"><span data-stu-id="ed546-138">Second</span></span>|<span data-ttu-id="ed546-139">ss, s</span><span class="sxs-lookup"><span data-stu-id="ed546-139">ss, s</span></span>|  
|<span data-ttu-id="ed546-140">Millisekunde</span><span class="sxs-lookup"><span data-stu-id="ed546-140">Millisecond</span></span>|<span data-ttu-id="ed546-141">Ms</span><span class="sxs-lookup"><span data-stu-id="ed546-141">Ms</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="ed546-142">Beispiele für SSIS-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ed546-142">SSIS Expression Examples</span></span>  
 <span data-ttu-id="ed546-143">In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Monat in einem Datumsliteral darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed546-143">This example returns the integer that represents the month in a date literal.</span></span> <span data-ttu-id="ed546-144">Falls das Datum das Format „MM/TT/JJJJ“ aufweist, gibt dieses Beispiel „11“ zurück.</span><span class="sxs-lookup"><span data-stu-id="ed546-144">If the date is in mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 <span data-ttu-id="ed546-145">In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Tag in der **ModifiedDate** -Spalte darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed546-145">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 <span data-ttu-id="ed546-146">In diesem Beispiel wird die ganze Zahl zurückgegeben, die das Jahr des aktuellen Datums darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed546-146">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed546-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed546-147">See Also</span></span>  
 <span data-ttu-id="ed546-148">[DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ed546-148">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="ed546-149">[DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ed546-149">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="ed546-150">[DAY &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ed546-150">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="ed546-151">[MONTH &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ed546-151">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="ed546-152">[YEAR &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ed546-152">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="ed546-153">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="ed546-153">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
