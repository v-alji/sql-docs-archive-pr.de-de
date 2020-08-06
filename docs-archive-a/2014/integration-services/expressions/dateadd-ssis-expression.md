---
title: DATEADD (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEADD
- dates [Integration Services]
- DATEADD function
ms.assetid: fa5c37b1-2ddc-4857-8f8e-f6d5643b654f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9feb288318bdf9705928cb930f175f5c170c384e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721654"
---
# <a name="dateadd-ssis-expression"></a><span data-ttu-id="5189a-102">DATEADD (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="5189a-102">DATEADD (SSIS Expression)</span></span>
  <span data-ttu-id="5189a-103">Gibt einen neuen DT_DBTIMESTAMP-Wert zurück, nachdem einem angegebenen datepart-Wert in einem Datum eine Zahl hinzugefügt wurde, die ein Datums- oder Zeitintervall darstellt.</span><span class="sxs-lookup"><span data-stu-id="5189a-103">Returns a new DT_DBTIMESTAMP value after adding a number that represents a date or time interval to the specified datepart in a date.</span></span> <span data-ttu-id="5189a-104">Der number-Parameter muss zu einer ganzen Zahl ausgewertet werden, und der date-Parameter muss zu einem gültigen Datum ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5189a-104">The number parameter must evaluate to an integer, and the date parameter must evaluate to a valid date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5189a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5189a-105">Syntax</span></span>  
  
```  
  
DATEADD(datepart, number, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5189a-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="5189a-106">Arguments</span></span>  
 <span data-ttu-id="5189a-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="5189a-107">*datepart*</span></span>  
 <span data-ttu-id="5189a-108">Der Parameter, der angibt, welcher Datumseinheit eine Zahl hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5189a-108">Is the parameter that specifies which part of the date to add a number to.</span></span>  
  
 <span data-ttu-id="5189a-109">*Zahl*</span><span class="sxs-lookup"><span data-stu-id="5189a-109">*number*</span></span>  
 <span data-ttu-id="5189a-110">Der Wert, um den *datepart*inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="5189a-110">Is the value used to increment *datepart*.</span></span> <span data-ttu-id="5189a-111">Dieser Wert muss ein ganzzahliger Wert sein, der beim Analysieren des Ausdrucks bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="5189a-111">The value must be an integer value that is known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="5189a-112">*date*</span><span class="sxs-lookup"><span data-stu-id="5189a-112">*date*</span></span>  
 <span data-ttu-id="5189a-113">Ein Ausdruck, der ein gültiges Datum oder eine Zeichenfolge im Datumsformat zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5189a-113">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5189a-114">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="5189a-114">Result Types</span></span>  
 <span data-ttu-id="5189a-115">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="5189a-115">DT_DBTIMESTAMP</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5189a-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5189a-116">Remarks</span></span>  
 <span data-ttu-id="5189a-117">In der folgenden Tabelle sind die datepart-Werte und Abkürzungen aufgeführt, die von der Ausdrucksauswertung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="5189a-117">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="5189a-118">Bei datepart-Namen wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5189a-118">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="5189a-119">datepart</span><span class="sxs-lookup"><span data-stu-id="5189a-119">Datepart</span></span>|<span data-ttu-id="5189a-120">Abkürzungen</span><span class="sxs-lookup"><span data-stu-id="5189a-120">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="5189a-121">Jahr</span><span class="sxs-lookup"><span data-stu-id="5189a-121">Year</span></span>|<span data-ttu-id="5189a-122">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="5189a-122">yy, yyyy</span></span>|  
|<span data-ttu-id="5189a-123">Quarter</span><span class="sxs-lookup"><span data-stu-id="5189a-123">Quarter</span></span>|<span data-ttu-id="5189a-124">qq, q</span><span class="sxs-lookup"><span data-stu-id="5189a-124">qq, q</span></span>|  
|<span data-ttu-id="5189a-125">Month (Monat)</span><span class="sxs-lookup"><span data-stu-id="5189a-125">Month</span></span>|<span data-ttu-id="5189a-126">mm, m</span><span class="sxs-lookup"><span data-stu-id="5189a-126">mm, m</span></span>|  
|<span data-ttu-id="5189a-127">Dayofyear</span><span class="sxs-lookup"><span data-stu-id="5189a-127">Dayofyear</span></span>|<span data-ttu-id="5189a-128">dy, y</span><span class="sxs-lookup"><span data-stu-id="5189a-128">dy, y</span></span>|  
|<span data-ttu-id="5189a-129">Day (Tag)</span><span class="sxs-lookup"><span data-stu-id="5189a-129">Day</span></span>|<span data-ttu-id="5189a-130">dd, d</span><span class="sxs-lookup"><span data-stu-id="5189a-130">dd, d</span></span>|  
|<span data-ttu-id="5189a-131">Week</span><span class="sxs-lookup"><span data-stu-id="5189a-131">Week</span></span>|<span data-ttu-id="5189a-132">wk, ww</span><span class="sxs-lookup"><span data-stu-id="5189a-132">wk, ww</span></span>|  
|<span data-ttu-id="5189a-133">Wochentag</span><span class="sxs-lookup"><span data-stu-id="5189a-133">Weekday</span></span>|<span data-ttu-id="5189a-134">dw, w</span><span class="sxs-lookup"><span data-stu-id="5189a-134">dw, w</span></span>|  
|<span data-ttu-id="5189a-135">Hour</span><span class="sxs-lookup"><span data-stu-id="5189a-135">Hour</span></span>|<span data-ttu-id="5189a-136">Hh</span><span class="sxs-lookup"><span data-stu-id="5189a-136">Hh</span></span>|  
|<span data-ttu-id="5189a-137">Minute</span><span class="sxs-lookup"><span data-stu-id="5189a-137">Minute</span></span>|<span data-ttu-id="5189a-138">mi, n</span><span class="sxs-lookup"><span data-stu-id="5189a-138">mi, n</span></span>|  
|<span data-ttu-id="5189a-139">Sekunde</span><span class="sxs-lookup"><span data-stu-id="5189a-139">Second</span></span>|<span data-ttu-id="5189a-140">ss, s</span><span class="sxs-lookup"><span data-stu-id="5189a-140">ss, s</span></span>|  
|<span data-ttu-id="5189a-141">Millisekunde</span><span class="sxs-lookup"><span data-stu-id="5189a-141">Millisecond</span></span>|<span data-ttu-id="5189a-142">Ms</span><span class="sxs-lookup"><span data-stu-id="5189a-142">Ms</span></span>|  
  
 <span data-ttu-id="5189a-143">Das *number* -Argument muss beim Analysieren des Ausdrucks verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="5189a-143">The *number* argument must be available when the expression is parsed.</span></span> <span data-ttu-id="5189a-144">Bei diesem Argument kann es sich um eine Konstante oder eine Variable handeln.</span><span class="sxs-lookup"><span data-stu-id="5189a-144">The argument can be a constant or a variable.</span></span> <span data-ttu-id="5189a-145">Spaltenwerte können nicht verwendet werden, weil diese Werte beim Analysieren des Ausdrucks nicht bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="5189a-145">You cannot use column values because the values are not known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="5189a-146">Das *datepart* -Argument muss in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5189a-146">The *datepart* argument must be enclosed by quotation marks.</span></span>  
  
 <span data-ttu-id="5189a-147">Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5189a-147">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="5189a-148">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5189a-148">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="5189a-149">DATEADD gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="5189a-149">DATEADD returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="5189a-150">Fehler treten auf, wenn ein Datum ungültig, die Datums- oder Zeiteinheit keine Zeichenfolge oder das Inkrement keine statische ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="5189a-150">Errors occur if a date is invalid, if the date or time unit is not a string, or if the increment is not a static integer.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="5189a-151">Beispiele für SSIS-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5189a-151">SSIS Expression Examples</span></span>  
 <span data-ttu-id="5189a-152">In diesem Beispiel wird dem aktuellen Datum ein Monat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5189a-152">This example adds one month to the current date.</span></span>  
  
```  
DATEADD("Month", 1,GETDATE())  
```  
  
 <span data-ttu-id="5189a-153">In diesem Beispiel werden den Datumsangaben in der **ModifiedDate** -Spalte 21 Tage hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5189a-153">This example adds 21 days to the dates in the **ModifiedDate** column.</span></span>  
  
```  
DATEADD("day", 21, ModifiedDate)  
```  
  
 <span data-ttu-id="5189a-154">In diesem Beispiel werden einem Datumsliteral 2 Jahre hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5189a-154">This example adds 2 years to a literal date.</span></span>  
  
```  
DATEADD("yyyy", 2, (DT_DBTIMESTAMP)"8/6/2003")  
```  
  
## <a name="see-also"></a><span data-ttu-id="5189a-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5189a-155">See Also</span></span>  
 <span data-ttu-id="5189a-156">[DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5189a-156">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="5189a-157">[DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5189a-157">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="5189a-158">[DAY &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5189a-158">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="5189a-159">[MONTH &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5189a-159">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="5189a-160">[YEAR &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5189a-160">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="5189a-161">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="5189a-161">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
