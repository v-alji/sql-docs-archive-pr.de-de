---
title: MSSQLSERVER_41396 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2386c805b61631c9b843753d74ba6616e7344223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699620"
---
# <a name="mssqlserver_41396"></a><span data-ttu-id="e013c-102">MSSQLSERVER_41396</span><span class="sxs-lookup"><span data-stu-id="e013c-102">MSSQLSERVER_41396</span></span>
    
## <a name="details"></a><span data-ttu-id="e013c-103">Details</span><span class="sxs-lookup"><span data-stu-id="e013c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e013c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e013c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="e013c-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e013c-105">Event ID</span></span>|<span data-ttu-id="e013c-106">41396</span><span class="sxs-lookup"><span data-stu-id="e013c-106">41396</span></span>|  
|<span data-ttu-id="e013c-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e013c-107">Event Source</span></span>|<span data-ttu-id="e013c-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e013c-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e013c-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="e013c-109">Component</span></span>|<span data-ttu-id="e013c-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e013c-110">SQLEngine</span></span>|  
|<span data-ttu-id="e013c-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e013c-111">Symbolic Name</span></span>|<span data-ttu-id="e013c-112">MAX_SORT_ROWS_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="e013c-112">MAX_SORT_ROWS_EXCEEDED</span></span>|  
|<span data-ttu-id="e013c-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e013c-113">Message Text</span></span>|<span data-ttu-id="e013c-114">Das Pufferlimit wurde vom Sortiervorgang überschritten.</span><span class="sxs-lookup"><span data-stu-id="e013c-114">The sort operation exceeded the buffer limit.</span></span> <span data-ttu-id="e013c-115">Die Ausführung der gespeicherten Prozedur wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="e013c-115">The stored procedure execution was aborted.</span></span> <span data-ttu-id="e013c-116">Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e013c-116">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e013c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e013c-117">Explanation</span></span>  
 <span data-ttu-id="e013c-118">Systemintern kompilierte gespeicherte Prozeduren führen Sortiervorgänge im Arbeitsspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="e013c-118">Natively compiled stored procedures perform sort operations in memory.</span></span> <span data-ttu-id="e013c-119">Es gibt eine Beschränkung bezüglich der Größe des Sortierungspuffers.</span><span class="sxs-lookup"><span data-stu-id="e013c-119">There is a limit on the size of the sort buffer.</span></span> <span data-ttu-id="e013c-120">Dieser Fehler bewirkt, dass dieser Grenzwert von der Größe des Sortierungspuffers überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="e013c-120">This error means that the size of the sort buffer exceeds this limit.</span></span> <span data-ttu-id="e013c-121">Der Sortiervorgang und die Ausführung der gespeicherten Prozedur wurden abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="e013c-121">The sort operation and the stored procedure execution aborted.</span></span>  
  
 <span data-ttu-id="e013c-122">Die Größe jeder Zeile bzw. jedes Eintrags im Sortierungspuffer hängt von der Anzahl der sortierten Zeilen, der Anzahl der Joins sowie von der Anzahl und dem Typ der Aggregatfunktionen in der Abfrage ab.</span><span class="sxs-lookup"><span data-stu-id="e013c-122">The size of each row or entry in the sort buffer is determined by the number of rows sorted as well as the number of joins and the number and type of aggregate functions in the query.</span></span> <span data-ttu-id="e013c-123">Indem Sie die Abfrage vereinfachen, können Sie die Größe jeder Zeile reduzieren, wodurch mehr Zeilen in den Sortierungspuffer passen.</span><span class="sxs-lookup"><span data-stu-id="e013c-123">By simplifying the query, you can reduce the size of each row thereby fitting more rows in the sort buffer.</span></span> <span data-ttu-id="e013c-124">Die Größe der Zeilen in den Basistabellen wirkt sich nicht auf die Größe der einzelnen Zeilen oder Einträge im Sortierungspuffer aus.</span><span class="sxs-lookup"><span data-stu-id="e013c-124">The size of the rows in the base tables does not affect the size of each row or entry in the sort buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e013c-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e013c-125">User Action</span></span>  
 <span data-ttu-id="e013c-126">Wählen Sie weniger Zeilen aus, oder verringern Sie die Komplexität der Abfrage, indem Sie Joins oder Aggregatfunktionen entfernen.</span><span class="sxs-lookup"><span data-stu-id="e013c-126">Select fewer rows or decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e013c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e013c-127">See Also</span></span>  
 [<span data-ttu-id="e013c-128">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="e013c-128">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
