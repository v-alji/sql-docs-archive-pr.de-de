---
title: MSSQLSERVER_10532 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10532 (Database Engine error)
ms.assetid: 01da29ee-bf67-433f-8148-587a7e8d1d76
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26ab34c319eff62737eae337828247fdfd7e901b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723902"
---
# <a name="mssqlserver_10532"></a><span data-ttu-id="4acf8-102">MSSQLSERVER_10532</span><span class="sxs-lookup"><span data-stu-id="4acf8-102">MSSQLSERVER_10532</span></span>
    
## <a name="details"></a><span data-ttu-id="4acf8-103">Details</span><span class="sxs-lookup"><span data-stu-id="4acf8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4acf8-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4acf8-104">Product Name</span></span>|<span data-ttu-id="4acf8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4acf8-105">SQL Server</span></span>|  
|<span data-ttu-id="4acf8-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4acf8-106">Event ID</span></span>|<span data-ttu-id="4acf8-107">10532</span><span class="sxs-lookup"><span data-stu-id="4acf8-107">10532</span></span>|  
|<span data-ttu-id="4acf8-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4acf8-108">Event Source</span></span>|<span data-ttu-id="4acf8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4acf8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4acf8-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4acf8-110">Component</span></span>|<span data-ttu-id="4acf8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4acf8-111">SQLEngine</span></span>|  
|<span data-ttu-id="4acf8-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4acf8-112">Symbolic Name</span></span>|<span data-ttu-id="4acf8-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="4acf8-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="4acf8-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4acf8-114">Message Text</span></span>|<span data-ttu-id="4acf8-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil der mit `@plan_handle` angegebene Batch bzw. das Modul keine geeignete Anweisung für eine Planhinweisliste enthält.</span><span class="sxs-lookup"><span data-stu-id="4acf8-115">Cannot create plan guide '%.\*ls' because the batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span> <span data-ttu-id="4acf8-116">Geben Sie einen anderen Wert für `@plan_handle` an.</span><span class="sxs-lookup"><span data-stu-id="4acf8-116">Specify a different value for `@plan_handle`.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4acf8-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4acf8-117">Explanation</span></span>  
 <span data-ttu-id="4acf8-118">Der mit `@plan_handle` angegebene Batch bzw. das Modul enthält keine geeignete Anweisung für eine Planhinweisliste.</span><span class="sxs-lookup"><span data-stu-id="4acf8-118">The batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4acf8-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4acf8-119">User Action</span></span>  
 <span data-ttu-id="4acf8-120">Geben Sie einen anderen Wert für `@plan_handle` an.</span><span class="sxs-lookup"><span data-stu-id="4acf8-120">Specify a different value for `@plan_handle`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4acf8-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4acf8-121">See Also</span></span>  
 <span data-ttu-id="4acf8-122">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="4acf8-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="4acf8-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4acf8-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="4acf8-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4acf8-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
