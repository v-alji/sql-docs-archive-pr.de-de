---
title: MSSQLSERVER_10537 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10537 (Database Engine error)
ms.assetid: 728469a4-6523-4a37-925f-a950d75420fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b1baccad5236bd8c1a71024b7dd542cc9d11cbd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718229"
---
# <a name="mssqlserver_10537"></a><span data-ttu-id="2914c-102">MSSQLSERVER_10537</span><span class="sxs-lookup"><span data-stu-id="2914c-102">MSSQLSERVER_10537</span></span>
    
## <a name="details"></a><span data-ttu-id="2914c-103">Details</span><span class="sxs-lookup"><span data-stu-id="2914c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2914c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2914c-104">Product Name</span></span>|<span data-ttu-id="2914c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2914c-105">SQL Server</span></span>|  
|<span data-ttu-id="2914c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2914c-106">Event ID</span></span>|<span data-ttu-id="2914c-107">10537</span><span class="sxs-lookup"><span data-stu-id="2914c-107">10537</span></span>|  
|<span data-ttu-id="2914c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2914c-108">Event Source</span></span>|<span data-ttu-id="2914c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2914c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2914c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2914c-110">Component</span></span>|<span data-ttu-id="2914c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2914c-111">SQLEngine</span></span>|  
|<span data-ttu-id="2914c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2914c-112">Symbolic Name</span></span>|<span data-ttu-id="2914c-113">PG_DUP_ENABLED</span><span class="sxs-lookup"><span data-stu-id="2914c-113">PG_DUP_ENABLED</span></span>|  
|<span data-ttu-id="2914c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2914c-114">Message Text</span></span>|<span data-ttu-id="2914c-115">Die Planhinweisliste '%.\*ls' kann nicht aktiviert werden, weil die aktivierte Planhinweisliste '%.\*ls' denselben Bereich und Startoffsetwert wie die Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="2914c-115">Cannot enable plan guide '%.\*ls' because the enabled plan guide '%.\*ls' contains the same scope and starting offset value as the statement.</span></span> <span data-ttu-id="2914c-116">Deaktivieren Sie die vorhandene Planhinweisliste, bevor Sie die angegebene Planhinweisliste aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2914c-116">Disable the existing plan guide before enabling the specified plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2914c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2914c-117">Explanation</span></span>  
 <span data-ttu-id="2914c-118">Eine vorhandene Planhinweisliste enthält denselben Bereich und Startoffsetwert wie die Anweisung in der angegebenen Planhinweisliste.</span><span class="sxs-lookup"><span data-stu-id="2914c-118">An existing plan guide contains the same scope and starting offset value as the statement in the specified plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2914c-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2914c-119">User Action</span></span>  
 <span data-ttu-id="2914c-120">Deaktivieren Sie die vorhandene Planhinweisliste, bevor Sie die angegebene Planhinweisliste aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2914c-120">Disable the existing plan guide before enabling the specified plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2914c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2914c-121">See Also</span></span>  
 <span data-ttu-id="2914c-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2914c-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="2914c-123">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="2914c-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="2914c-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2914c-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
