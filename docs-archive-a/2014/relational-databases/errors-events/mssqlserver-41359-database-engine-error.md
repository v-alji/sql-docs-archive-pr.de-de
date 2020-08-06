---
title: MSSQLSERVER_41359 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41359 (Database Engine error)
ms.assetid: 02b717c7-9170-4676-b0f6-4dec9eb5b5d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cf45a117dcda0827672c6072c603a1fc0866a33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621507"
---
# <a name="mssqlserver_41359"></a><span data-ttu-id="e347d-102">MSSQLSERVER_41359</span><span class="sxs-lookup"><span data-stu-id="e347d-102">MSSQLSERVER_41359</span></span>
    
## <a name="details"></a><span data-ttu-id="e347d-103">Details</span><span class="sxs-lookup"><span data-stu-id="e347d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e347d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e347d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="e347d-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e347d-105">Event ID</span></span>|<span data-ttu-id="e347d-106">41359</span><span class="sxs-lookup"><span data-stu-id="e347d-106">41359</span></span>|  
|<span data-ttu-id="e347d-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e347d-107">Event Source</span></span>|<span data-ttu-id="e347d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e347d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e347d-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="e347d-109">Component</span></span>|<span data-ttu-id="e347d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e347d-110">SQLEngine</span></span>|  
|<span data-ttu-id="e347d-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e347d-111">Symbolic Name</span></span>|<span data-ttu-id="e347d-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="e347d-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="e347d-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e347d-113">Message Text</span></span>|<span data-ttu-id="e347d-114">Eine Abfrage, die auf speicheroptimierte Tabellen mit der READ COMMITTED-Isolationsstufe zugreift, kann auf datenträgerbasierte Tabellen nicht zugreifen, wenn die Datenbankoption READ_COMMITTED_SNAPSHOT auf ON gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e347d-114">A query that accesses memory optimized tables using the READ COMMITTED isolation level, cannot access disk based tables when the database option READ_COMMITTED_SNAPSHOT is set to ON.</span></span> <span data-ttu-id="e347d-115">Geben Sie eine unterstützte Isolationsstufe für die speicheroptimierte Tabelle mithilfe eines Tabellentipps wie WITH (SNAPSHOT) an.</span><span class="sxs-lookup"><span data-stu-id="e347d-115">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e347d-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e347d-116">Explanation</span></span>  
 <span data-ttu-id="e347d-117">Die Datenbank mit READ_COMMITTED_SNAPSHOT=ON unterstützt nicht die Transaktionen, die sowohl auf speicheroptimierte Tabellen als auch auf datenträgerbasierte Tabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e347d-117">The database with READ_COMMITTED_SNAPSHOT=ON does not support the transactions that access both memory-optimized tables and disk based tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e347d-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e347d-118">User Action</span></span>  
 <span data-ttu-id="e347d-119">Setzen Sie READ_COMMITTED_SNAPSHOT auf OFF oder stellen Sie eine unterstützte Isolationsstufe für die speicheroptimierte Tabelle mithilfe eines Tipps auf Tabellenebene wie WITH (SNAPSHOT) bereit.</span><span class="sxs-lookup"><span data-stu-id="e347d-119">Set READ_COMMITTED_SNAPSHOT to OFF or supply a supported isolation level for the memory-optimized table using a table-level hint, such as WITH (SNAPSHOT).</span></span> <span data-ttu-id="e347d-120">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="e347d-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e347d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e347d-121">See Also</span></span>  
 [<span data-ttu-id="e347d-122">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="e347d-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
