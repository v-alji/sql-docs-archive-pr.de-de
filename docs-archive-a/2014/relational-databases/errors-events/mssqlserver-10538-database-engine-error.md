---
title: MSSQLSERVER_10538 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: edc6abf192a3341f9b84c99e99071343cc882c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699722"
---
# <a name="mssqlserver_10538"></a><span data-ttu-id="08eb9-102">MSSQLSERVER_10538</span><span class="sxs-lookup"><span data-stu-id="08eb9-102">MSSQLSERVER_10538</span></span>
    
## <a name="details"></a><span data-ttu-id="08eb9-103">Details</span><span class="sxs-lookup"><span data-stu-id="08eb9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08eb9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="08eb9-104">Product Name</span></span>|<span data-ttu-id="08eb9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="08eb9-105">SQL Server</span></span>|  
|<span data-ttu-id="08eb9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="08eb9-106">Event ID</span></span>|<span data-ttu-id="08eb9-107">10538</span><span class="sxs-lookup"><span data-stu-id="08eb9-107">10538</span></span>|  
|<span data-ttu-id="08eb9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="08eb9-108">Event Source</span></span>|<span data-ttu-id="08eb9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="08eb9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="08eb9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="08eb9-110">Component</span></span>|<span data-ttu-id="08eb9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="08eb9-111">SQLEngine</span></span>|  
|<span data-ttu-id="08eb9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="08eb9-112">Symbolic Name</span></span>|<span data-ttu-id="08eb9-113">PG_INVALID_PLANGUIDE_HANDLE</span><span class="sxs-lookup"><span data-stu-id="08eb9-113">PG_INVALID_PLANGUIDE_HANDLE</span></span>|  
|<span data-ttu-id="08eb9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="08eb9-114">Message Text</span></span>|<span data-ttu-id="08eb9-115">Die Planhinweisliste wurde nicht gefunden, weil die angegebene Planhinweislisten-ID NULL oder ungültig ist oder weil Sie keine Berechtigung für das Objekt besitzen, auf das die Planhinweisliste verweist.</span><span class="sxs-lookup"><span data-stu-id="08eb9-115">Cannot find the plan guide either because the specified plan guide ID is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span> <span data-ttu-id="08eb9-116">Vergewissern Sie sich, dass die Planhinweislisten-ID gültig ist, die aktuelle Sitzung auf den korrekten Datenbankkontext eingestellt ist und Sie entweder die ALTER DATABASE-Berechtigung oder die ALTER-Berechtigung für das Objekt besitzen, auf das die Planhinweisliste verweist.</span><span class="sxs-lookup"><span data-stu-id="08eb9-116">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have either ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08eb9-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="08eb9-117">Explanation</span></span>  
 <span data-ttu-id="08eb9-118">Die ID der angegebenen Planhinweisliste ist NULL oder ungültig, oder Sie besitzen nicht die Berechtigung für das Objekt, auf das die Planhinweisliste verweist.</span><span class="sxs-lookup"><span data-stu-id="08eb9-118">The ID of the specified plan guide is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08eb9-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="08eb9-119">User Action</span></span>  
 <span data-ttu-id="08eb9-120">Vergewissern Sie sich, dass die Planhinweislisten-ID gültig, die aktuelle Sitzung auf den korrekten Datenbankkontext eingestellt ist und Sie die ALTER DATABASE-Berechtigung oder die ALTER-Berechtigung für das Objekt besitzen, auf das die Planhinweisliste verweist.</span><span class="sxs-lookup"><span data-stu-id="08eb9-120">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08eb9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08eb9-121">See Also</span></span>  
 <span data-ttu-id="08eb9-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08eb9-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="08eb9-123">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="08eb9-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="08eb9-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="08eb9-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
