---
title: MONTH (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1f56906b4d25f2ba01f54fbdbc404d2c9ae4704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617197"
---
# <a name="month-ssis-expression"></a><span data-ttu-id="e2675-102">MONTH (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="e2675-102">MONTH (SSIS Expression)</span></span>
  <span data-ttu-id="e2675-103">Gibt eine ganze Zahl zurück, die den datepart-Wert für die Monatsangabe in einem Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2675-103">Returns an integer that represents the month datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2675-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2675-104">Syntax</span></span>  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2675-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e2675-105">Arguments</span></span>  
 <span data-ttu-id="e2675-106">*date*</span><span class="sxs-lookup"><span data-stu-id="e2675-106">*date*</span></span>  
 <span data-ttu-id="e2675-107">Ein Datum in einem beliebigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="e2675-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e2675-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="e2675-108">Result Types</span></span>  
 <span data-ttu-id="e2675-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="e2675-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2675-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e2675-110">Remarks</span></span>  
 <span data-ttu-id="e2675-111">MONTH gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="e2675-111">MONTH returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="e2675-112">Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e2675-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="e2675-113">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e2675-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2675-114">Der Ausdruck wird nicht überprüft, wenn ein Datumsliteral explizit in einen der folgenden Datumsdatentypen umgewandelt wird: DT_DBTIMESTAMPOFFSET oder DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="e2675-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="e2675-115">Die MONTH-Funktion entspricht bezüglich der Verwendung der DATEPART("Month", date)-Funktion, ist jedoch schneller.</span><span class="sxs-lookup"><span data-stu-id="e2675-115">Using the MONTH function is briefer but equivalent to using DATEPART("Month", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e2675-116">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e2675-116">Expression Examples</span></span>  
 <span data-ttu-id="e2675-117">In diesem Beispiel wird der Monat eines Datumsliterals zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e2675-117">This example returns the number of the month in a date literal.</span></span> <span data-ttu-id="e2675-118">Falls das Datum das Format "mm/dd/yyyy" aufweist, wird 11 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e2675-118">If the date is in "mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="e2675-119">In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Monat in der **ModifiedDate** -Spalte darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2675-119">This example returns the integer that represents the month in the **ModifiedDate** column.</span></span>  
  
```  
MONTH(ModifiedDate)  
```  
  
 <span data-ttu-id="e2675-120">In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Monat des aktuellen Datums darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2675-120">This example returns the integer that represents the month of the current date.</span></span>  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2675-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2675-121">See Also</span></span>  
 <span data-ttu-id="e2675-122">[DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2675-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="e2675-123">[DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2675-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="e2675-124">[DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2675-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="e2675-125">[DAY &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2675-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="e2675-126">[YEAR &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e2675-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e2675-127">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="e2675-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
