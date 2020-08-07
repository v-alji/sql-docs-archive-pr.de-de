---
title: MSSQLSERVER_41305 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619142"
---
# <a name="mssqlserver_41305"></a><span data-ttu-id="f64f9-102">MSSQLSERVER_41305</span><span class="sxs-lookup"><span data-stu-id="f64f9-102">MSSQLSERVER_41305</span></span>
    
## <a name="details"></a><span data-ttu-id="f64f9-103">Details</span><span class="sxs-lookup"><span data-stu-id="f64f9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f64f9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f64f9-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f64f9-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f64f9-105">Event ID</span></span>|<span data-ttu-id="f64f9-106">41305</span><span class="sxs-lookup"><span data-stu-id="f64f9-106">41305</span></span>|  
|<span data-ttu-id="f64f9-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f64f9-107">Event Source</span></span>|<span data-ttu-id="f64f9-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f64f9-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f64f9-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="f64f9-109">Component</span></span>|<span data-ttu-id="f64f9-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f64f9-110">SQLEngine</span></span>|  
|<span data-ttu-id="f64f9-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f64f9-111">Symbolic Name</span></span>|<span data-ttu-id="f64f9-112">HK_TX_COMMIT_RR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="f64f9-112">HK_TX_COMMIT_RR_VALIDATION</span></span>|  
|<span data-ttu-id="f64f9-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f64f9-113">Message Text</span></span>|<span data-ttu-id="f64f9-114">Fehler beim Ausführen eines Commits für die aktuelle Transaktion aufgrund eines REPEATABLE READ-Überprüfungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="f64f9-114">The current transaction failed to commit due to a repeatable read validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f64f9-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f64f9-115">Explanation</span></span>  
 <span data-ttu-id="f64f9-116">Bei der Transaktion trat ein Überprüfungsfehler auf, sie kann nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f64f9-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
 <span data-ttu-id="f64f9-117">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="f64f9-117">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f64f9-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f64f9-118">User Action</span></span>  
 <span data-ttu-id="f64f9-119">Wiederholen Sie die fehlgeschlagene Transaktion.</span><span class="sxs-lookup"><span data-stu-id="f64f9-119">Retry the failed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64f9-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f64f9-120">See Also</span></span>  
 [<span data-ttu-id="f64f9-121">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="f64f9-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
