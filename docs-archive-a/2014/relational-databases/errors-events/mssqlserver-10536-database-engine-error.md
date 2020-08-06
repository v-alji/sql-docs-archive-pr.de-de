---
title: MSSQLSERVER_10536 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10536 (Database Engine error)
ms.assetid: 9f97b41f-0ef8-4ad2-aec0-906a5d7522ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 00d08f4555f38b61661a917ba94c023f9dd6c4a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718226"
---
# <a name="mssqlserver_10536"></a><span data-ttu-id="87124-102">MSSQLSERVER_10536</span><span class="sxs-lookup"><span data-stu-id="87124-102">MSSQLSERVER_10536</span></span>
    
## <a name="details"></a><span data-ttu-id="87124-103">Details</span><span class="sxs-lookup"><span data-stu-id="87124-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87124-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="87124-104">Product Name</span></span>|<span data-ttu-id="87124-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="87124-105">SQL Server</span></span>|  
|<span data-ttu-id="87124-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="87124-106">Event ID</span></span>|<span data-ttu-id="87124-107">10536</span><span class="sxs-lookup"><span data-stu-id="87124-107">10536</span></span>|  
|<span data-ttu-id="87124-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="87124-108">Event Source</span></span>|<span data-ttu-id="87124-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="87124-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="87124-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="87124-110">Component</span></span>|<span data-ttu-id="87124-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="87124-111">SQLEngine</span></span>|  
|<span data-ttu-id="87124-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="87124-112">Symbolic Name</span></span>|<span data-ttu-id="87124-113">PG_TOO_MANY_STMTS</span><span class="sxs-lookup"><span data-stu-id="87124-113">PG_TOO_MANY_STMTS</span></span>|  
|<span data-ttu-id="87124-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="87124-114">Message Text</span></span>|<span data-ttu-id="87124-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil der entsprechende Batch bzw. das Modul für das angegebene `@plan_handle` mehr als 1000 geeignete Anweisungen enthält.</span><span class="sxs-lookup"><span data-stu-id="87124-115">Cannot create plan guide '%.\*ls' because the batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span> <span data-ttu-id="87124-116">Erstellen Sie eine Planhinweisliste für jede Anweisung im Batch oder Modul, und geben Sie dabei einen `statement_start_offset`-Wert für jede Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="87124-116">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87124-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="87124-117">Explanation</span></span>  
 <span data-ttu-id="87124-118">Der entsprechende Batch bzw. das Modul für das angegebene `@plan_handle` enthält mehr als 1000 geeignete Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="87124-118">The batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87124-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="87124-119">User Action</span></span>  
 <span data-ttu-id="87124-120">Erstellen Sie eine Planhinweisliste für jede Anweisung im Batch oder Modul, und geben Sie dabei einen `statement_start_offset`-Wert für jede Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="87124-120">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87124-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87124-121">See Also</span></span>  
 <span data-ttu-id="87124-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="87124-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="87124-123">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="87124-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="87124-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87124-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
