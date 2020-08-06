---
title: MSSQLSERVER_41302 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41302 (Database Engine error)
ms.assetid: 01e75618-afec-4232-ba68-93ab7bc31003
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 751dac91378c002a7e6c6c619ddaf12be8173400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616574"
---
# <a name="mssqlserver_41302"></a><span data-ttu-id="08b56-102">MSSQLSERVER_41302</span><span class="sxs-lookup"><span data-stu-id="08b56-102">MSSQLSERVER_41302</span></span>
    
## <a name="details"></a><span data-ttu-id="08b56-103">Details</span><span class="sxs-lookup"><span data-stu-id="08b56-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08b56-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="08b56-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="08b56-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08b56-105">Event ID</span></span>|<span data-ttu-id="08b56-106">41302</span><span class="sxs-lookup"><span data-stu-id="08b56-106">41302</span></span>|  
|<span data-ttu-id="08b56-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="08b56-107">Event Source</span></span>|<span data-ttu-id="08b56-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="08b56-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="08b56-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="08b56-109">Component</span></span>|<span data-ttu-id="08b56-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="08b56-110">SQLEngine</span></span>|  
|<span data-ttu-id="08b56-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="08b56-111">Symbolic Name</span></span>|<span data-ttu-id="08b56-112">WRITE_WRITE_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="08b56-112">WRITE_WRITE_CONFLICT</span></span>|  
|<span data-ttu-id="08b56-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="08b56-113">Message Text</span></span>|<span data-ttu-id="08b56-114">Für die aktuelle Transaktion wurde versucht, einen Datensatz zu aktualisieren, der aktualisiert wurde, nachdem diese Transaktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="08b56-114">The current transaction attempted to update a record that has been updated since this transaction started.</span></span> <span data-ttu-id="08b56-115">Die Transaktion wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="08b56-115">The transaction was aborted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08b56-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="08b56-116">Explanation</span></span>  
 <span data-ttu-id="08b56-117">Bei der Transaktion trat ein Schreibkonflikt auf und die Anweisung wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="08b56-117">The transaction encountered a write/write conflict and the statement terminated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08b56-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="08b56-118">User Action</span></span>  
 <span data-ttu-id="08b56-119">Wiederholen Sie den Vorgang später in einer anderen Transaktion.</span><span class="sxs-lookup"><span data-stu-id="08b56-119">Retry the operation later in a different transaction.</span></span> <span data-ttu-id="08b56-120">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="08b56-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b56-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08b56-121">See Also</span></span>  
 [<span data-ttu-id="08b56-122">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="08b56-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
