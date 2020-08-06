---
title: MSSQLSERVER_10507 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a80e48948c03b370c07742fabbb3cf8eb3e74315
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722862"
---
# <a name="mssqlserver_10507"></a><span data-ttu-id="43f10-102">MSSQLSERVER_10507</span><span class="sxs-lookup"><span data-stu-id="43f10-102">MSSQLSERVER_10507</span></span>
    
## <a name="details"></a><span data-ttu-id="43f10-103">Details</span><span class="sxs-lookup"><span data-stu-id="43f10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43f10-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="43f10-104">Product Name</span></span>|<span data-ttu-id="43f10-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="43f10-105">SQL Server</span></span>|  
|<span data-ttu-id="43f10-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="43f10-106">Event ID</span></span>|<span data-ttu-id="43f10-107">10507</span><span class="sxs-lookup"><span data-stu-id="43f10-107">10507</span></span>|  
|<span data-ttu-id="43f10-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="43f10-108">Event Source</span></span>|<span data-ttu-id="43f10-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="43f10-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="43f10-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="43f10-110">Component</span></span>|<span data-ttu-id="43f10-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="43f10-111">SQLEngine</span></span>|  
|<span data-ttu-id="43f10-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="43f10-112">Symbolic Name</span></span>|<span data-ttu-id="43f10-113">PG_STMT_DOES_NOT_MATCH</span><span class="sxs-lookup"><span data-stu-id="43f10-113">PG_STMT_DOES_NOT_MATCH</span></span>|  
|<span data-ttu-id="43f10-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="43f10-114">Message Text</span></span>|<span data-ttu-id="43f10-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil die mit `@stmt` und `@module_or_batch` oder mit `@plan_handle` und `@statement_start_offset` angegebene Anweisung keiner Anweisung im festgelegten Modul oder Batch entspricht.</span><span class="sxs-lookup"><span data-stu-id="43f10-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` and `@module_or_batch`, or by `@plan_handle` and `@statement_start_offset`, does not match any statement in the specified module or batch.</span></span> <span data-ttu-id="43f10-116">Ändern Sie die Werte, um eine Übereinstimmung mit einer Anweisung im Modul oder Batch herzustellen.</span><span class="sxs-lookup"><span data-stu-id="43f10-116">Modify the values to match a statement in the module or batch.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="43f10-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="43f10-117">Explanation</span></span>  
 <span data-ttu-id="43f10-118">Eine Anweisung im festgelegten Modul oder Batch konnte nicht der angegebenen Anweisung bzw. dem Offsetwert der Anweisung zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="43f10-118">A statement in the specified module or batch could not be matched to the specified statement or statement offset value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43f10-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="43f10-119">User Action</span></span>  
 <span data-ttu-id="43f10-120">Ändern Sie die angegebenen Parameterwerte, um eine Übereinstimmung mit einer Anweisung im Modul oder Batch herzustellen.</span><span class="sxs-lookup"><span data-stu-id="43f10-120">Modify the specified parameter values to match a statement in the module or batch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f10-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43f10-121">See Also</span></span>  
 <span data-ttu-id="43f10-122">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="43f10-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="43f10-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="43f10-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="43f10-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43f10-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
