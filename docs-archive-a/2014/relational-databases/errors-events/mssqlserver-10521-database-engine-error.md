---
title: MSSQLSERVER_10521 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c034bd13e212b9b39bfd348353d59e23fc748079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699747"
---
# <a name="mssqlserver_10521"></a><span data-ttu-id="5b7c6-102">MSSQLSERVER_10521</span><span class="sxs-lookup"><span data-stu-id="5b7c6-102">MSSQLSERVER_10521</span></span>
    
## <a name="details"></a><span data-ttu-id="5b7c6-103">Details</span><span class="sxs-lookup"><span data-stu-id="5b7c6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b7c6-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5b7c6-104">Product Name</span></span>|<span data-ttu-id="5b7c6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b7c6-105">SQL Server</span></span>|  
|<span data-ttu-id="5b7c6-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5b7c6-106">Event ID</span></span>|<span data-ttu-id="5b7c6-107">10521</span><span class="sxs-lookup"><span data-stu-id="5b7c6-107">10521</span></span>|  
|<span data-ttu-id="5b7c6-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5b7c6-108">Event Source</span></span>|<span data-ttu-id="5b7c6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5b7c6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5b7c6-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5b7c6-110">Component</span></span>|<span data-ttu-id="5b7c6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5b7c6-111">SQLEngine</span></span>|  
|<span data-ttu-id="5b7c6-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5b7c6-112">Symbolic Name</span></span>|<span data-ttu-id="5b7c6-113">PG_PARAM_NEEDED</span><span class="sxs-lookup"><span data-stu-id="5b7c6-113">PG_PARAM_NEEDED</span></span>|  
|<span data-ttu-id="5b7c6-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5b7c6-114">Message Text</span></span>|<span data-ttu-id="5b7c6-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil `@type` als „%ls“ angegeben wurde und der „%ls“-Parameter NULL ist.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-115">Cannot create plan guide '%.\*ls' because `@type` was specified as '%ls' and the parameter '%ls' is NULL.</span></span> <span data-ttu-id="5b7c6-116">Dieser Typ erfordert einen Wert ungleich NULL für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-116">This type requires a non-NULL value for the parameter.</span></span> <span data-ttu-id="5b7c6-117">Geben Sie einen Wert ungleich NULL für den Parameter an, oder ändern Sie den Typ in einen Typ, der NULL-Werte für den Parameter zulässt.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-117">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b7c6-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5b7c6-118">Explanation</span></span>  
 <span data-ttu-id="5b7c6-119">Der in `@type` angegebene Typ erfordert einen Wert ungleich NULL für den angegebenen Parameter. Es wurde jedoch ein NULL-Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-119">The type specified in `@type` requires a non-NULL value for the specified parameter; however a NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b7c6-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5b7c6-120">User Action</span></span>  
 <span data-ttu-id="5b7c6-121">Geben Sie einen Wert ungleich NULL für den Parameter an, oder ändern Sie den Typ in einen Typ, der NULL-Werte für den Parameter zulässt.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-121">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7c6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b7c6-122">See Also</span></span>  
 <span data-ttu-id="5b7c6-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b7c6-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="5b7c6-124">[Plan Hinweis Listen](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="5b7c6-124">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="5b7c6-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b7c6-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
