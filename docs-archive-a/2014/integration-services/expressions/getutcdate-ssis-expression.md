---
title: GETUTCDATE (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f157ab5641e521a42cb3c96c96446b31de5dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701468"
---
# <a name="getutcdate-ssis-expression"></a><span data-ttu-id="67c7c-102">GETUTCDATE (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="67c7c-102">GETUTCDATE (SSIS Expression)</span></span>
  <span data-ttu-id="67c7c-103">Gibt das aktuelle Datum des Systems als UTC-Zeit (Universal Time Coordinate oder Greenwich Mean Time) in einem DT_DBTIMESTAMP-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="67c7c-103">Returns the current date of the system in UTC time (Universal Time Coordinate or Greenwich Mean Time) using a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="67c7c-104">Die GETUTCDATE-Funktion weist keine Argumente auf.</span><span class="sxs-lookup"><span data-stu-id="67c7c-104">The GETUTCDATE function takes no arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c7c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="67c7c-105">Syntax</span></span>  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="67c7c-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="67c7c-106">Arguments</span></span>  
 <span data-ttu-id="67c7c-107">Keine</span><span class="sxs-lookup"><span data-stu-id="67c7c-107">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="67c7c-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="67c7c-108">Result Types</span></span>  
 <span data-ttu-id="67c7c-109">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="67c7c-109">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="67c7c-110">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="67c7c-110">Expression Examples</span></span>  
 <span data-ttu-id="67c7c-111">In diesem Beispiel wird das Jahr des aktuellen Datums als UTC-Zeit zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="67c7c-111">This example returns the year of the current date in UTC time.</span></span>  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 <span data-ttu-id="67c7c-112">In diesem Beispiel wird die Anzahl von Tagen zwischen einem Datum in der **ModifiedDate** -Spalte und dem aktuellen UTC-Datum zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="67c7c-112">This example returns the number of days between a date in the **ModifiedDate** column and the current UTC date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 <span data-ttu-id="67c7c-113">In diesem Beispiel werden dem aktuellen UTC-Datum drei Monate hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="67c7c-113">This example adds three months to the current UTC date.</span></span>  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="67c7c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67c7c-114">See Also</span></span>  
 <span data-ttu-id="67c7c-115">[GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="67c7c-115">[GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="67c7c-116">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="67c7c-116">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
