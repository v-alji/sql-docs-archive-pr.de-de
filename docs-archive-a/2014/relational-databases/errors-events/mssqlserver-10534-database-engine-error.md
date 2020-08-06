---
title: MSSQLSERVER_10534 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10534 (Database Engine error)
ms.assetid: e65bb118-99d5-4fdb-b1d5-0ec70f0a677b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 793bb0bf5048e30624d9566f65e7c6752bd14386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699740"
---
# <a name="mssqlserver_10534"></a><span data-ttu-id="1f48d-102">MSSQLSERVER_10534</span><span class="sxs-lookup"><span data-stu-id="1f48d-102">MSSQLSERVER_10534</span></span>
    
## <a name="details"></a><span data-ttu-id="1f48d-103">Details</span><span class="sxs-lookup"><span data-stu-id="1f48d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f48d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="1f48d-104">Product Name</span></span>|<span data-ttu-id="1f48d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f48d-105">SQL Server</span></span>|  
|<span data-ttu-id="1f48d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="1f48d-106">Event ID</span></span>|<span data-ttu-id="1f48d-107">10534</span><span class="sxs-lookup"><span data-stu-id="1f48d-107">10534</span></span>|  
|<span data-ttu-id="1f48d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="1f48d-108">Event Source</span></span>|<span data-ttu-id="1f48d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1f48d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1f48d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="1f48d-110">Component</span></span>|<span data-ttu-id="1f48d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1f48d-111">SQLEngine</span></span>|  
|<span data-ttu-id="1f48d-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="1f48d-112">Symbolic Name</span></span>|<span data-ttu-id="1f48d-113">PG_INVALID_PARAMS</span><span class="sxs-lookup"><span data-stu-id="1f48d-113">PG_INVALID_PARAMS</span></span>|  
|<span data-ttu-id="1f48d-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="1f48d-114">Message Text</span></span>|<span data-ttu-id="1f48d-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil der für `@params` angegebene Wert ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="1f48d-115">Cannot create plan guide '%.\*ls' because the value specified for `@params` is invalid.</span></span> <span data-ttu-id="1f48d-116">Verwenden Sie für den Wert das Format *parameter_name parameter_type*, oder geben Sie NULL an.</span><span class="sxs-lookup"><span data-stu-id="1f48d-116">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1f48d-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="1f48d-117">Explanation</span></span>  
 <span data-ttu-id="1f48d-118">Der für `@params` angegebene Wert ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="1f48d-118">The value specified for `@params` is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1f48d-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="1f48d-119">User Action</span></span>  
 <span data-ttu-id="1f48d-120">Verwenden Sie für den Wert das Format *parameter_name parameter_type*, oder geben Sie NULL an.</span><span class="sxs-lookup"><span data-stu-id="1f48d-120">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f48d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f48d-121">See Also</span></span>  
 <span data-ttu-id="1f48d-122">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="1f48d-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="1f48d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f48d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="1f48d-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f48d-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
