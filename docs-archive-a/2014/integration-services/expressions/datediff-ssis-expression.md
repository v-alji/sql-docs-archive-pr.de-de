---
title: DATEDIFF (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DATEDIFF statement
- dates [Integration Services], DATEDIFF
ms.assetid: 449b327f-47c7-4709-8bc6-4ee9a35cc330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33edf2a152f70bb8c5bbd1f69cb87354e099b246
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700070"
---
# <a name="datediff-ssis-expression"></a><span data-ttu-id="f6c44-102">DATEDIFF (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6c44-102">DATEDIFF (SSIS Expression)</span></span>
  <span data-ttu-id="f6c44-103">Gibt die Anzahl von Datums- und Zeiteinheiten zurück, die zwischen zwei angegebenen Daten überschritten wurden.</span><span class="sxs-lookup"><span data-stu-id="f6c44-103">Returns the number of date and time boundaries crossed between two specified dates.</span></span> <span data-ttu-id="f6c44-104">Der *datepart* -Parameter identifiziert, welche Datums- und Zeiteinheiten verglichen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f6c44-104">The *datepart* parameter identifies which date and time boundaries to compare.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6c44-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6c44-105">Syntax</span></span>  
  
```  
  
DATEDIFF(datepart, startdate, endate)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6c44-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f6c44-106">Arguments</span></span>  
 <span data-ttu-id="f6c44-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="f6c44-107">*datepart*</span></span>  
 <span data-ttu-id="f6c44-108">Der Parameter, der angibt, welche Datumseinheit verglichen und für welche Datumseinheit ein Wert zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="f6c44-108">Is the parameter that specifies which part of the date to compare and return a value for.</span></span>  
  
 <span data-ttu-id="f6c44-109">*startdate*</span><span class="sxs-lookup"><span data-stu-id="f6c44-109">*startdate*</span></span>  
 <span data-ttu-id="f6c44-110">Das Startdatum des Intervalls.</span><span class="sxs-lookup"><span data-stu-id="f6c44-110">Is the start date of the interval.</span></span>  
  
 <span data-ttu-id="f6c44-111">*endate*</span><span class="sxs-lookup"><span data-stu-id="f6c44-111">*endate*</span></span>  
 <span data-ttu-id="f6c44-112">Das Enddatum des Intervalls.</span><span class="sxs-lookup"><span data-stu-id="f6c44-112">Is the end date of the interval.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f6c44-113">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="f6c44-113">Result Types</span></span>  
 <span data-ttu-id="f6c44-114">DT_I4</span><span class="sxs-lookup"><span data-stu-id="f6c44-114">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6c44-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f6c44-115">Remarks</span></span>  
 <span data-ttu-id="f6c44-116">In der folgenden Tabelle sind die datepart-Werte und Abkürzungen aufgeführt, die von der Ausdrucksauswertung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="f6c44-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span>  
  
|<span data-ttu-id="f6c44-117">datepart</span><span class="sxs-lookup"><span data-stu-id="f6c44-117">Datepart</span></span>|<span data-ttu-id="f6c44-118">Abkürzungen</span><span class="sxs-lookup"><span data-stu-id="f6c44-118">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="f6c44-119">Jahr</span><span class="sxs-lookup"><span data-stu-id="f6c44-119">Year</span></span>|<span data-ttu-id="f6c44-120">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="f6c44-120">yy, yyyy</span></span>|  
|<span data-ttu-id="f6c44-121">Quarter</span><span class="sxs-lookup"><span data-stu-id="f6c44-121">Quarter</span></span>|<span data-ttu-id="f6c44-122">qq, q</span><span class="sxs-lookup"><span data-stu-id="f6c44-122">qq, q</span></span>|  
|<span data-ttu-id="f6c44-123">Month (Monat)</span><span class="sxs-lookup"><span data-stu-id="f6c44-123">Month</span></span>|<span data-ttu-id="f6c44-124">mm, m</span><span class="sxs-lookup"><span data-stu-id="f6c44-124">mm, m</span></span>|  
|<span data-ttu-id="f6c44-125">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="f6c44-125">Dayofyear</span></span>|<span data-ttu-id="f6c44-126">dy, y</span><span class="sxs-lookup"><span data-stu-id="f6c44-126">dy, y</span></span>|  
|<span data-ttu-id="f6c44-127">Day (Tag)</span><span class="sxs-lookup"><span data-stu-id="f6c44-127">Day</span></span>|<span data-ttu-id="f6c44-128">dd, d</span><span class="sxs-lookup"><span data-stu-id="f6c44-128">dd, d</span></span>|  
|<span data-ttu-id="f6c44-129">Week</span><span class="sxs-lookup"><span data-stu-id="f6c44-129">Week</span></span>|<span data-ttu-id="f6c44-130">wk, ww</span><span class="sxs-lookup"><span data-stu-id="f6c44-130">wk, ww</span></span>|  
|<span data-ttu-id="f6c44-131">Wochentag</span><span class="sxs-lookup"><span data-stu-id="f6c44-131">Weekday</span></span>|<span data-ttu-id="f6c44-132">dw, w</span><span class="sxs-lookup"><span data-stu-id="f6c44-132">dw, w</span></span>|  
|<span data-ttu-id="f6c44-133">Hour</span><span class="sxs-lookup"><span data-stu-id="f6c44-133">Hour</span></span>|<span data-ttu-id="f6c44-134">Hh</span><span class="sxs-lookup"><span data-stu-id="f6c44-134">Hh</span></span>|  
|<span data-ttu-id="f6c44-135">Minute</span><span class="sxs-lookup"><span data-stu-id="f6c44-135">Minute</span></span>|<span data-ttu-id="f6c44-136">mi, n</span><span class="sxs-lookup"><span data-stu-id="f6c44-136">mi, n</span></span>|  
|<span data-ttu-id="f6c44-137">Sekunde</span><span class="sxs-lookup"><span data-stu-id="f6c44-137">Second</span></span>|<span data-ttu-id="f6c44-138">ss, s</span><span class="sxs-lookup"><span data-stu-id="f6c44-138">ss, s</span></span>|  
|<span data-ttu-id="f6c44-139">Millisekunde</span><span class="sxs-lookup"><span data-stu-id="f6c44-139">Millisecond</span></span>|<span data-ttu-id="f6c44-140">Ms</span><span class="sxs-lookup"><span data-stu-id="f6c44-140">Ms</span></span>|  
  
 <span data-ttu-id="f6c44-141">DATEDIFF gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.</span><span class="sxs-lookup"><span data-stu-id="f6c44-141">DATEDIFF returns a null result if any argument is null.</span></span>  
  
 <span data-ttu-id="f6c44-142">Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f6c44-142">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="f6c44-143">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f6c44-143">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="f6c44-144">Ein Fehler tritt auf, wenn ein Datum ungültig ist, die Datums- oder Zeiteinheit keine Zeichenfolge ist, das Startdatum kein Datum ist oder das Enddatum kein Datum ist.</span><span class="sxs-lookup"><span data-stu-id="f6c44-144">An error occurs if a date is not valid, if the date or time unit is not a string, if the start date is not a date, or if the end date is not a date.</span></span>  
  
 <span data-ttu-id="f6c44-145">Wenn das Enddatum vor dem Startdatum liegt, gibt die Funktion eine negative Zahl zurück.</span><span class="sxs-lookup"><span data-stu-id="f6c44-145">If the end date is earlier than the start date, the function returns a negative number.</span></span> <span data-ttu-id="f6c44-146">Wenn das Startdatum und das Enddatum identisch sind oder im gleichen Zeitraum liegen, gibt die Funktion Null zurück.</span><span class="sxs-lookup"><span data-stu-id="f6c44-146">If the start and end dates are equal or fall within the same interval, the function returns zero.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="f6c44-147">Beispiele für SSIS-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f6c44-147">SSIS Expression Examples</span></span>  
 <span data-ttu-id="f6c44-148">In diesem Beispiel wird die Anzahl von Tagen zwischen zwei Datumsliteralen berechnet.</span><span class="sxs-lookup"><span data-stu-id="f6c44-148">This example calculates the number of days between two date literals.</span></span> <span data-ttu-id="f6c44-149">Falls das Datum das Format "mm/dd/yyyy" aufweist, wird 7 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f6c44-149">If the date is in "mm/dd/yyyy" format, the function returns 7.</span></span>  
  
```  
DATEDIFF("dd", (DT_DBTIMESTAMP)"8/1/2003", (DT_DBTIMESTAMP)"8/8/2003")  
```  
  
 <span data-ttu-id="f6c44-150">In diesem Beispiel wird die Anzahl von Monaten zwischen einem Datumsliteral und dem aktuellen Datum zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f6c44-150">This example returns the number of months between a date literal and the current date.</span></span>  
  
```  
DATEDIFF("mm", (DT_DBTIMESTAMP)"8/1/2003",GETDATE())  
```  
  
 <span data-ttu-id="f6c44-151">In diesem Beispiel wird die Anzahl von Wochen zwischen dem Datum in der **ModifiedDate** -Spalte und der **YearEndDate** -Variablen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f6c44-151">This example returns the number of weeks between the date in the **ModifiedDate** column and the **YearEndDate** variable.</span></span> <span data-ttu-id="f6c44-152">Wenn **YearEndDate** einen `date` Datentyp aufweist, ist keine explizite Umwandlung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6c44-152">If **YearEndDate** has a `date` data type, no explicit casting is required.</span></span>  
  
```  
DATEDIFF("Week", ModifiedDate,@YearEndDate)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6c44-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6c44-153">See Also</span></span>  
 <span data-ttu-id="f6c44-154">[DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f6c44-154">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="f6c44-155">[DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f6c44-155">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="f6c44-156">[DAY &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f6c44-156">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="f6c44-157">[MONTH &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f6c44-157">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="f6c44-158">[YEAR &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f6c44-158">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="f6c44-159">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="f6c44-159">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
