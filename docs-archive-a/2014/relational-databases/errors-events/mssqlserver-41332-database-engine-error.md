---
title: MSSQLSERVER_41332 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619875"
---
# <a name="mssqlserver_41332"></a><span data-ttu-id="213b1-102">MSSQLSERVER_41332</span><span class="sxs-lookup"><span data-stu-id="213b1-102">MSSQLSERVER_41332</span></span>
    
## <a name="details"></a><span data-ttu-id="213b1-103">Details</span><span class="sxs-lookup"><span data-stu-id="213b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="213b1-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="213b1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="213b1-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="213b1-105">Event ID</span></span>|<span data-ttu-id="213b1-106">41332</span><span class="sxs-lookup"><span data-stu-id="213b1-106">41332</span></span>|  
|<span data-ttu-id="213b1-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="213b1-107">Event Source</span></span>|<span data-ttu-id="213b1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="213b1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="213b1-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="213b1-109">Component</span></span>|<span data-ttu-id="213b1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="213b1-110">SQLEngine</span></span>|  
|<span data-ttu-id="213b1-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="213b1-111">Symbolic Name</span></span>|<span data-ttu-id="213b1-112">SQL_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="213b1-112">SQL_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="213b1-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="213b1-113">Message Text</span></span>|<span data-ttu-id="213b1-114">Wenn der TRANSACTION ISOLATION LEVEL der Sitzung auf SNAPSHOT festgelegt ist, kann nicht auf speicheroptimierte Tabellen und systemintern kompilierte gespeicherte Prozeduren zugegriffen werden, und diese können nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="213b1-114">Memory optimized tables and natively compiled stored procedures cannot be accessed or created when the session TRANSACTION ISOLATION LEVEL is set to SNAPSHOT.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="213b1-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="213b1-115">Explanation</span></span>  
 <span data-ttu-id="213b1-116">Die Transaktion wurde auf der Momentaufnahmeisolationsstufe gestartet, und anschließend wurde versucht, eine nicht kompatible Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="213b1-116">The transaction was started in snapshot isolation level and then attempted to use an incompatible feature.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="213b1-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="213b1-117">User Action</span></span>  
 <span data-ttu-id="213b1-118">Starten Sie die Transaktion mit einer anderen Isolationsstufe.</span><span class="sxs-lookup"><span data-stu-id="213b1-118">Start the transaction with a different isolation level.</span></span> <span data-ttu-id="213b1-119">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="213b1-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="213b1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="213b1-120">See Also</span></span>  
 [<span data-ttu-id="213b1-121">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="213b1-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
