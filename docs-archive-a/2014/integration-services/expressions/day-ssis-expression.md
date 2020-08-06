---
title: DAY (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b7acac3f3949cbbd07adbe6382ea3d875f94cb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700058"
---
# <a name="day-ssis-expression"></a><span data-ttu-id="56d5d-102">DAY (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="56d5d-102">DAY (SSIS Expression)</span></span>
  <span data-ttu-id="56d5d-103">Gibt eine ganze Zahl zurück, die den datepart-Wert für den Tag eines Datums darstellt.</span><span class="sxs-lookup"><span data-stu-id="56d5d-103">Returns an integer that represents the day datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56d5d-104">Syntax</span></span>  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="56d5d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="56d5d-105">Arguments</span></span>  
 <span data-ttu-id="56d5d-106">*date*</span><span class="sxs-lookup"><span data-stu-id="56d5d-106">*date*</span></span>  
 <span data-ttu-id="56d5d-107">Ein Ausdruck, der ein gültiges Datum oder eine Zeichenfolge im Datumsformat zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="56d5d-107">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="56d5d-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="56d5d-108">Result Types</span></span>  
 <span data-ttu-id="56d5d-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="56d5d-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56d5d-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="56d5d-110">Remarks</span></span>  
 <span data-ttu-id="56d5d-111">DAY gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="56d5d-111">DAY returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="56d5d-112">Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="56d5d-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="56d5d-113">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="56d5d-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56d5d-114">Der Ausdruck wird nicht überprüft, wenn ein Datumsliteral explizit in einen der folgenden Datumsdatentypen umgewandelt wird: DT_DBTIMESTAMPOFFSET oder DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="56d5d-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="56d5d-115">Die DAY-Funktion entspricht bezüglich der Verwendung der DATEPART("Day", date)-Funktion, ist jedoch schneller.</span><span class="sxs-lookup"><span data-stu-id="56d5d-115">Using the DAY function is briefer but equivalent to using DATEPART("Day", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="56d5d-116">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="56d5d-116">Expression Examples</span></span>  
 <span data-ttu-id="56d5d-117">In diesem Beispiel wird der Tag eines Datumsliterals zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="56d5d-117">This example returns the number of the day in a date literal.</span></span> <span data-ttu-id="56d5d-118">Falls das Datum das Format "mm/dd/yyyy" aufweist, wird 23 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="56d5d-118">If the date format is in "mm/dd/yyyy" format, this example returns 23.</span></span>  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="56d5d-119">In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Tag in der **ModifiedDate** -Spalte darstellt.</span><span class="sxs-lookup"><span data-stu-id="56d5d-119">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DAY(ModifiedDate)  
```  
  
 <span data-ttu-id="56d5d-120">In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Tag des aktuellen Datums darstellt.</span><span class="sxs-lookup"><span data-stu-id="56d5d-120">This example returns the integer that represents the day of the current date.</span></span>  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="56d5d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56d5d-121">See Also</span></span>  
 <span data-ttu-id="56d5d-122">[DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="56d5d-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="56d5d-123">[DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="56d5d-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="56d5d-124">[DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="56d5d-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="56d5d-125">[MONTH &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="56d5d-125">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="56d5d-126">[YEAR &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="56d5d-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="56d5d-127">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="56d5d-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
