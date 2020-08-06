---
title: GETDATE (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616602"
---
# <a name="getdate-ssis-expression"></a><span data-ttu-id="6f587-102">GETDATE (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="6f587-102">GETDATE (SSIS Expression)</span></span>
  <span data-ttu-id="6f587-103">Gibt das aktuelle Datum des Systems in einem DT_DBTIMESTAMP-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="6f587-103">Returns the current date of the system in a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="6f587-104">Die GETDATE-Funktion weist keine Argumente auf.</span><span class="sxs-lookup"><span data-stu-id="6f587-104">The GETDATE function takes no arguments.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f587-105">Die Länge des von der GETDATE-Funktion zurückgegebenen Ergebnisses beträgt 29 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6f587-105">The length of the return result from the GETDATE function is 29 characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f587-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f587-106">Syntax</span></span>  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f587-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="6f587-107">Arguments</span></span>  
 <span data-ttu-id="6f587-108">Keine</span><span class="sxs-lookup"><span data-stu-id="6f587-108">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6f587-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="6f587-109">Result Types</span></span>  
 <span data-ttu-id="6f587-110">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="6f587-110">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6f587-111">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6f587-111">Expression Examples</span></span>  
 <span data-ttu-id="6f587-112">In diesem Beispiel wird das Jahr des aktuellen Datums zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f587-112">This example returns the year of the current date.</span></span>  
  
```  
DATEPART("year",GETDATE())  
```  
  
 <span data-ttu-id="6f587-113">In diesem Beispiel wird die Anzahl von Tagen zwischen einem Datum in der **ModifiedDate** -Spalte und dem aktuellen Datum zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f587-113">This example returns the number of days between a date in the **ModifiedDate** column and the current date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 <span data-ttu-id="6f587-114">In diesem Beispiel werden dem aktuellen Datum drei Monate hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6f587-114">This example adds three months to the current date.</span></span>  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f587-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f587-115">See Also</span></span>  
 <span data-ttu-id="6f587-116">[GETUTCDATE &#40;SSIS-Ausdruck&#41;](getutcdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6f587-116">[GETUTCDATE &#40;SSIS Expression&#41;](getutcdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="6f587-117">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="6f587-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
