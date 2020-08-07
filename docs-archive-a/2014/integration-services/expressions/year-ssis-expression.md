---
title: YEAR (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], YEAR
- YEAR function
ms.assetid: 9d88dead-ace8-44b9-b8e2-916c1842e155
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181375d489fbf7abf0718386efacf4167ba555d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620499"
---
# <a name="year-ssis-expression"></a><span data-ttu-id="74815-102">YEAR (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="74815-102">YEAR (SSIS Expression)</span></span>
  <span data-ttu-id="74815-103">Gibt eine ganze Zahl zurück, die den datepart-Wert für die Jahresangabe in einem Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="74815-103">Returns an integer that represents the year datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74815-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74815-104">Syntax</span></span>  
  
```  
  
YEAR(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="74815-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="74815-105">Arguments</span></span>  
 <span data-ttu-id="74815-106">*date*</span><span class="sxs-lookup"><span data-stu-id="74815-106">*date*</span></span>  
 <span data-ttu-id="74815-107">Ein Datum in einem beliebigen Datumsformat.</span><span class="sxs-lookup"><span data-stu-id="74815-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="74815-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="74815-108">Result Types</span></span>  
 <span data-ttu-id="74815-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="74815-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74815-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="74815-110">Remarks</span></span>  
 <span data-ttu-id="74815-111">YEAR gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="74815-111">YEAR returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="74815-112">Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="74815-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="74815-113">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="74815-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74815-114">Der Ausdruck wird nicht überprüft, wenn ein Datumsliteral explizit in einen der folgenden Datumsdatentypen umgewandelt wird: DT_DBTIMESTAMPOFFSET oder DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="74815-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="74815-115">Die YEAR-Funktion entspricht bezüglich der Verwendung der DATEPART("Year", date)-Funktion, ist jedoch schneller.</span><span class="sxs-lookup"><span data-stu-id="74815-115">Using the YEAR function is briefer but equivalent to using the DATEPART("Year", date) function.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="74815-116">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="74815-116">Expression Examples</span></span>  
 <span data-ttu-id="74815-117">In diesem Beispiel wird die Jahreszahl eines Datumsliterals zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74815-117">This example returns the number of the year in a date literal.</span></span> <span data-ttu-id="74815-118">Falls das Datum das Format mm/dd/yyyy aufweist, wird "2002" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74815-118">If the date is in mm/dd/yyyy format, this example returns "2002".</span></span>  
  
```  
YEAR((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="74815-119">In diesem Beispiel wird die ganze Zahl zurückgegeben, die das Jahr in der **ModifiedDate** -Spalte darstellt.</span><span class="sxs-lookup"><span data-stu-id="74815-119">This example returns the integer that represents the year in the **ModifiedDate** column.</span></span>  
  
```  
YEAR(ModifiedDate)  
```  
  
 <span data-ttu-id="74815-120">In diesem Beispiel wird die ganze Zahl zurückgegeben, die das Jahr des aktuellen Datums darstellt.</span><span class="sxs-lookup"><span data-stu-id="74815-120">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
YEAR(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="74815-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74815-121">See Also</span></span>  
 <span data-ttu-id="74815-122">[DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74815-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="74815-123">[DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74815-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="74815-124">[DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74815-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="74815-125">[DAY &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74815-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="74815-126">[MONTH &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74815-126">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 [<span data-ttu-id="74815-127">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="74815-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
