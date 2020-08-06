---
title: MSSQLSERVER_10519 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10519 (Database Engine error)
ms.assetid: 3be393a1-b186-41ae-afb9-a3d07ff354bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ec584649842f787b1de9d2ea6d161aea6970250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721473"
---
# <a name="mssqlserver_10519"></a><span data-ttu-id="7e166-102">MSSQLSERVER_10519</span><span class="sxs-lookup"><span data-stu-id="7e166-102">MSSQLSERVER_10519</span></span>
    
## <a name="details"></a><span data-ttu-id="7e166-103">Details</span><span class="sxs-lookup"><span data-stu-id="7e166-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e166-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7e166-104">Product Name</span></span>|<span data-ttu-id="7e166-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e166-105">SQL Server</span></span>|  
|<span data-ttu-id="7e166-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7e166-106">Event ID</span></span>|<span data-ttu-id="7e166-107">10519</span><span class="sxs-lookup"><span data-stu-id="7e166-107">10519</span></span>|  
|<span data-ttu-id="7e166-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7e166-108">Event Source</span></span>|<span data-ttu-id="7e166-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7e166-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7e166-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7e166-110">Component</span></span>|<span data-ttu-id="7e166-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7e166-111">SQLEngine</span></span>|  
|<span data-ttu-id="7e166-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7e166-112">Symbolic Name</span></span>|<span data-ttu-id="7e166-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span><span class="sxs-lookup"><span data-stu-id="7e166-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span></span>|  
|<span data-ttu-id="7e166-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7e166-114">Message Text</span></span>|<span data-ttu-id="7e166-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil die in `@hints` festgelegten Hinweise nicht auf die mit `@stmt` oder `@statement_start_offset` angegebene Anweisung angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7e166-115">Cannot create plan guide '%.\*ls' because the hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span> <span data-ttu-id="7e166-116">Vergewissern Sie sich, dass die Hinweise auf die Anweisung angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7e166-116">Verify that the hints can be applied to the statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e166-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7e166-117">Explanation</span></span>  
 <span data-ttu-id="7e166-118">Die in `@hints` festgelegten Hinweise können nicht auf die mit `@stmt` oder `@statement_start_offset` angegebene Anweisung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e166-118">The hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e166-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7e166-119">User Action</span></span>  
 <span data-ttu-id="7e166-120">Legen Sie Hinweise fest, die auf die Anweisung angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7e166-120">Specify hints that can be applied to the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e166-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e166-121">See Also</span></span>  
 <span data-ttu-id="7e166-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e166-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="7e166-123">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="7e166-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="7e166-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7e166-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
