---
title: MSSQLSERVER_41399 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e134cbc8b39a3c65d9c515183243f0b4caed434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616573"
---
# <a name="mssqlserver_41399"></a><span data-ttu-id="dc1cb-102">MSSQLSERVER_41399</span><span class="sxs-lookup"><span data-stu-id="dc1cb-102">MSSQLSERVER_41399</span></span>
    
## <a name="details"></a><span data-ttu-id="dc1cb-103">Details</span><span class="sxs-lookup"><span data-stu-id="dc1cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc1cb-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="dc1cb-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="dc1cb-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="dc1cb-105">Event ID</span></span>|<span data-ttu-id="dc1cb-106">41399</span><span class="sxs-lookup"><span data-stu-id="dc1cb-106">41399</span></span>|  
|<span data-ttu-id="dc1cb-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="dc1cb-107">Event Source</span></span>|<span data-ttu-id="dc1cb-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc1cb-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc1cb-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="dc1cb-109">Component</span></span>|<span data-ttu-id="dc1cb-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc1cb-110">SQLEngine</span></span>|  
|<span data-ttu-id="dc1cb-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="dc1cb-111">Symbolic Name</span></span>|<span data-ttu-id="dc1cb-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="dc1cb-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span></span>|  
|<span data-ttu-id="dc1cb-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="dc1cb-113">Message Text</span></span>|<span data-ttu-id="dc1cb-114">Der Sortiervorgang ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-114">The sort operation is too complex.</span></span> <span data-ttu-id="dc1cb-115">Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-115">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc1cb-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="dc1cb-116">Explanation</span></span>  
 <span data-ttu-id="dc1cb-117">Durch das Sortieren der Ergebnisse eines Join -und Aggregationsvorgangs erhöht sich die Komplexität des Sortiervorgangs, da die Größe der Zeile im Sortierungspuffer zunimmt.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-117">Sorting the result of join and aggregation operations increases the complexity of the sort operation by increasing the size of the row in the sort buffer.</span></span> <span data-ttu-id="dc1cb-118">Dieser Fehler bewirkt, dass die Größe der Zeile größer als die maximale Größe ist, die vom SORT-Operator in systemintern kompilierten gespeicherten Prozeduren unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-118">This error means that the size of the row is larger than the maximum size supported by the sort operator in natively compiled stored procedures.</span></span> <span data-ttu-id="dc1cb-119">Beachten Sie, dass die Größe einer Zeile im Sortierungspuffer ausschließlich von der Anzahl der Joins sowie der Anzahl und dem Typ der Aggregatfunktionen bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-119">Note that the size of a row in the sort buffer is determined solely by the number of joins and the number and type of aggregate functions.</span></span> <span data-ttu-id="dc1cb-120">Die Größe der Zeilen in den Basistabellen wirkt sich nicht auf die Größe der Zeile im Puffer aus.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-120">The size of the rows in the base tables does not affect the size of the row in the buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc1cb-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="dc1cb-121">User Action</span></span>  
 <span data-ttu-id="dc1cb-122">Verringern Sie die Komplexität der Abfrage, indem Sie Joins oder Aggregatfunktionen entfernen.</span><span class="sxs-lookup"><span data-stu-id="dc1cb-122">Decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1cb-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc1cb-123">See Also</span></span>  
 [<span data-ttu-id="dc1cb-124">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="dc1cb-124">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
