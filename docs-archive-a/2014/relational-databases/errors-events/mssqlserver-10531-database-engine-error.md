---
title: MSSQLSERVER_10531 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10531 (Database Engine error)
ms.assetid: bb40e994-231c-44ce-933f-8d767fb2f450
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6230c046a9eb7b900377888c59a3a492f2b89f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699746"
---
# <a name="mssqlserver_10531"></a><span data-ttu-id="c12ce-102">MSSQLSERVER_10531</span><span class="sxs-lookup"><span data-stu-id="c12ce-102">MSSQLSERVER_10531</span></span>
    
## <a name="details"></a><span data-ttu-id="c12ce-103">Details</span><span class="sxs-lookup"><span data-stu-id="c12ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c12ce-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c12ce-104">Product Name</span></span>|<span data-ttu-id="c12ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c12ce-105">SQL Server</span></span>|  
|<span data-ttu-id="c12ce-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c12ce-106">Event ID</span></span>|<span data-ttu-id="c12ce-107">10531</span><span class="sxs-lookup"><span data-stu-id="c12ce-107">10531</span></span>|  
|<span data-ttu-id="c12ce-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c12ce-108">Event Source</span></span>|<span data-ttu-id="c12ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c12ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c12ce-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c12ce-110">Component</span></span>|<span data-ttu-id="c12ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c12ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="c12ce-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c12ce-112">Symbolic Name</span></span>|<span data-ttu-id="c12ce-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="c12ce-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="c12ce-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c12ce-114">Message Text</span></span>|<span data-ttu-id="c12ce-115">Die Planhinweisliste '%.\*ls' kann nicht aus dem Cache erstellt werden, weil der Benutzer nicht über die erforderlichen Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="c12ce-115">Cannot create plan guide '%.\*ls' from cache because the user does not have adequate permissions.</span></span> <span data-ttu-id="c12ce-116">Gewähren Sie dem Benutzer, der die Planhinweisliste erstellt, die VIEW SERVER STATE-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="c12ce-116">Grant the VIEW SERVER STATE permission to the user creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c12ce-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c12ce-117">Explanation</span></span>  
 <span data-ttu-id="c12ce-118">Der Benutzer verfügt nicht über die erforderlichen Berechtigungen zum Erstellen der angegebenen Planhinweisliste aus dem Plancache.</span><span class="sxs-lookup"><span data-stu-id="c12ce-118">The user does not have adequate permissions to create the specified plan guide from the plan cache.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c12ce-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c12ce-119">User Action</span></span>  
 <span data-ttu-id="c12ce-120">Gewähren Sie dem Benutzer, der die Planhinweisliste erstellt, die Berechtigung „VIEW SERVER STATE“.</span><span class="sxs-lookup"><span data-stu-id="c12ce-120">Grant VIEW SERVER STATE permission to the user creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12ce-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c12ce-121">See Also</span></span>  
 <span data-ttu-id="c12ce-122">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="c12ce-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="c12ce-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c12ce-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="c12ce-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c12ce-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
