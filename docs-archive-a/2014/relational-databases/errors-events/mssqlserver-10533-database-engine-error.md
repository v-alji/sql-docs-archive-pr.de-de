---
title: MSSQLSERVER_10533 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10533 (Database Engine error)
ms.assetid: cc2fbdab-7b90-415f-a1f9-066824344283
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccef25bc8f594cb6ea0b60aefab838ef27cda6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618057"
---
# <a name="mssqlserver_10533"></a><span data-ttu-id="5a371-102">MSSQLSERVER_10533</span><span class="sxs-lookup"><span data-stu-id="5a371-102">MSSQLSERVER_10533</span></span>
    
## <a name="details"></a><span data-ttu-id="5a371-103">Details</span><span class="sxs-lookup"><span data-stu-id="5a371-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a371-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5a371-104">Product Name</span></span>|<span data-ttu-id="5a371-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a371-105">SQL Server</span></span>|  
|<span data-ttu-id="5a371-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5a371-106">Event ID</span></span>|<span data-ttu-id="5a371-107">10533</span><span class="sxs-lookup"><span data-stu-id="5a371-107">10533</span></span>|  
|<span data-ttu-id="5a371-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5a371-108">Event Source</span></span>|<span data-ttu-id="5a371-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a371-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a371-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5a371-110">Component</span></span>|<span data-ttu-id="5a371-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a371-111">SQLEngine</span></span>|  
|<span data-ttu-id="5a371-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5a371-112">Symbolic Name</span></span>|<span data-ttu-id="5a371-113">PG_NAME_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="5a371-113">PG_NAME_TOO_BIG</span></span>|  
|<span data-ttu-id="5a371-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5a371-114">Message Text</span></span>|<span data-ttu-id="5a371-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil der Name der Planhinweisliste länger als die maximal zulässige Zeichenanzahl von 124 ist.</span><span class="sxs-lookup"><span data-stu-id="5a371-115">Cannot create plan guide '%.\*ls' because the plan guide name exceeds 124 characters, the maximum number allowed.</span></span> <span data-ttu-id="5a371-116">Legen Sie einen Namen mit weniger als 125 Zeichen fest.</span><span class="sxs-lookup"><span data-stu-id="5a371-116">Specify a name that contains fewer than 125 characters.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a371-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5a371-117">Explanation</span></span>  
 <span data-ttu-id="5a371-118">Die Planhinweisliste überschreitet die maximal zulässige Zeichenanzahl von 124.</span><span class="sxs-lookup"><span data-stu-id="5a371-118">The plan guide name exceeds 124 characters, the maximum number allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a371-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5a371-119">User Action</span></span>  
 <span data-ttu-id="5a371-120">Legen Sie einen Namen mit weniger als 125 Zeichen fest.</span><span class="sxs-lookup"><span data-stu-id="5a371-120">Specify a name that contains fewer than 125 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a371-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a371-121">See Also</span></span>  
 <span data-ttu-id="5a371-122">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="5a371-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="5a371-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a371-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="5a371-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5a371-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
