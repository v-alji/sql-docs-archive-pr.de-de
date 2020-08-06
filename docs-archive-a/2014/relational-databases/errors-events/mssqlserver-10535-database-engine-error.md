---
title: MSSQLSERVER_10535 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 439d282f18490a4353d6528276eaf7e4231c503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699729"
---
# <a name="mssqlserver_10535"></a><span data-ttu-id="8c77a-102">MSSQLSERVER_10535</span><span class="sxs-lookup"><span data-stu-id="8c77a-102">MSSQLSERVER_10535</span></span>
    
## <a name="details"></a><span data-ttu-id="8c77a-103">Details</span><span class="sxs-lookup"><span data-stu-id="8c77a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c77a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8c77a-104">Product Name</span></span>|<span data-ttu-id="8c77a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c77a-105">SQL Server</span></span>|  
|<span data-ttu-id="8c77a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8c77a-106">Event ID</span></span>|<span data-ttu-id="8c77a-107">10535</span><span class="sxs-lookup"><span data-stu-id="8c77a-107">10535</span></span>|  
|<span data-ttu-id="8c77a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8c77a-108">Event Source</span></span>|<span data-ttu-id="8c77a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8c77a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8c77a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8c77a-110">Component</span></span>|<span data-ttu-id="8c77a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8c77a-111">SQLEngine</span></span>|  
|<span data-ttu-id="8c77a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8c77a-112">Symbolic Name</span></span>|<span data-ttu-id="8c77a-113">PG_NO_PLAN</span><span class="sxs-lookup"><span data-stu-id="8c77a-113">PG_NO_PLAN</span></span>|  
|<span data-ttu-id="8c77a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8c77a-114">Message Text</span></span>|<span data-ttu-id="8c77a-115">Die Planhinweisliste '%.\*ls' kann nicht erstellt werden, weil kein Plan im entsprechenden Plancache für das Planhandle gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="8c77a-115">Cannot create plan guide '%.\*ls' because a plan was not found in the plan cache that corresponds to the specified plan handle.</span></span> <span data-ttu-id="8c77a-116">Geben Sie ein zwischengespeichertes Planhandle an.</span><span class="sxs-lookup"><span data-stu-id="8c77a-116">Specify a cached plan handle.</span></span> <span data-ttu-id="8c77a-117">Fragen Sie die dynamische sys.dm_exec_query_stats-Verwaltungssicht ab, um eine Liste der zwischengespeicherten Planhandles zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8c77a-117">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8c77a-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8c77a-118">Explanation</span></span>  
 <span data-ttu-id="8c77a-119">Es wurde kein Plan im Plancache gefunden, der dem angegebenen Planhandle entspricht.</span><span class="sxs-lookup"><span data-stu-id="8c77a-119">A plan was not found in the plan cache that corresponds to the specified plan handle.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8c77a-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8c77a-120">User Action</span></span>  
 <span data-ttu-id="8c77a-121">Geben Sie ein zwischengespeichertes Planhandle an.</span><span class="sxs-lookup"><span data-stu-id="8c77a-121">Specify a cached plan handle.</span></span> <span data-ttu-id="8c77a-122">Fragen Sie die dynamische sys.dm_exec_query_stats-Verwaltungssicht ab, um eine Liste der zwischengespeicherten Planhandles zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8c77a-122">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c77a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c77a-123">See Also</span></span>  
 <span data-ttu-id="8c77a-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8c77a-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 [<span data-ttu-id="8c77a-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8c77a-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql)  
  
  
