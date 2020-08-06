---
title: MSSQLSERVER_10502 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eeec3a3adf318cadc96501938f8a5565f1c07670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608744"
---
# <a name="mssqlserver_10502"></a><span data-ttu-id="7929f-102">MSSQLSERVER_10502</span><span class="sxs-lookup"><span data-stu-id="7929f-102">MSSQLSERVER_10502</span></span>
    
## <a name="details"></a><span data-ttu-id="7929f-103">Details</span><span class="sxs-lookup"><span data-stu-id="7929f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7929f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7929f-104">Product Name</span></span>|<span data-ttu-id="7929f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7929f-105">SQL Server</span></span>|  
|<span data-ttu-id="7929f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7929f-106">Event ID</span></span>|<span data-ttu-id="7929f-107">10502</span><span class="sxs-lookup"><span data-stu-id="7929f-107">10502</span></span>|  
|<span data-ttu-id="7929f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7929f-108">Event Source</span></span>|<span data-ttu-id="7929f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7929f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7929f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7929f-110">Component</span></span>|<span data-ttu-id="7929f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7929f-111">SQLEngine</span></span>|  
|<span data-ttu-id="7929f-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7929f-112">Symbolic Name</span></span>|<span data-ttu-id="7929f-113">PG_DUP_FOUND</span><span class="sxs-lookup"><span data-stu-id="7929f-113">PG_DUP_FOUND</span></span>|  
|<span data-ttu-id="7929f-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7929f-114">Message Text</span></span>|<span data-ttu-id="7929f-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil die mit @stmt und @module_or_batch oder @plan_handle und @statement_start_offset angegebene Anweisung mit der vorhandenen Planhinweisliste „%.\*ls“ in der Datenbank übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="7929f-115">Cannot create plan guide '%.\*ls' because the statement specified by @stmt and @module_or_batch, or by @plan_handle and @statement_start_offset, matches the existing plan guide '%.\*ls' in the database.</span></span> <span data-ttu-id="7929f-116">Löschen Sie die vorhandene Planhinweisliste, bevor Sie die neue Planhinweisliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="7929f-116">Drop the existing plan guide before creating the new plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7929f-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7929f-117">Explanation</span></span>  
 <span data-ttu-id="7929f-118">Für die angegebene Anweisung ist eine Planhinweisliste vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7929f-118">A plan guide exists for the specified statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7929f-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7929f-119">User Action</span></span>  
 <span data-ttu-id="7929f-120">Löschen Sie die vorhandene Planhinweisliste, bevor Sie die neue Planhinweisliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="7929f-120">Drop the existing plan guide before creating the new plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7929f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7929f-121">See Also</span></span>  
 <span data-ttu-id="7929f-122">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="7929f-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="7929f-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7929f-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="7929f-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7929f-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
