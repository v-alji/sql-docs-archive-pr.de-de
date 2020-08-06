---
title: MSSQLSERVER_10520 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b8bdf080703fa6bd02fc34b8c31f59407814b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699753"
---
# <a name="mssqlserver_10520"></a><span data-ttu-id="0eecb-102">MSSQLSERVER_10520</span><span class="sxs-lookup"><span data-stu-id="0eecb-102">MSSQLSERVER_10520</span></span>
    
## <a name="details"></a><span data-ttu-id="0eecb-103">Details</span><span class="sxs-lookup"><span data-stu-id="0eecb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0eecb-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0eecb-104">Product Name</span></span>|<span data-ttu-id="0eecb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0eecb-105">SQL Server</span></span>|  
|<span data-ttu-id="0eecb-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0eecb-106">Event ID</span></span>|<span data-ttu-id="0eecb-107">10520</span><span class="sxs-lookup"><span data-stu-id="0eecb-107">10520</span></span>|  
|<span data-ttu-id="0eecb-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0eecb-108">Event Source</span></span>|<span data-ttu-id="0eecb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0eecb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0eecb-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0eecb-110">Component</span></span>|<span data-ttu-id="0eecb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0eecb-111">SQLEngine</span></span>|  
|<span data-ttu-id="0eecb-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0eecb-112">Symbolic Name</span></span>|<span data-ttu-id="0eecb-113">PG_PARAM_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="0eecb-113">PG_PARAM_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="0eecb-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0eecb-114">Message Text</span></span>|<span data-ttu-id="0eecb-115">Die Planhinweisliste „%.\*ls“ kann nicht erstellt werden, weil @type als „%ls“ angegeben und ein Wert ungleich NULL für den „%ls“-Parameter festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="0eecb-115">Cannot create plan guide '%.\*ls' because @type was specified as '%ls' and a non-NULL value is specified for the parameter '%ls'.</span></span> <span data-ttu-id="0eecb-116">Dieser Typ erfordert einen NULL-Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="0eecb-116">This type requires a NULL value for the parameter.</span></span> <span data-ttu-id="0eecb-117">Geben Sie NULL für den Parameter an, oder ändern Sie den Typ in einen Typ, der Werte ungleich NULL für den Parameter zulässt.</span><span class="sxs-lookup"><span data-stu-id="0eecb-117">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0eecb-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0eecb-118">Explanation</span></span>  
 <span data-ttu-id="0eecb-119">Der in @type angegebene Typ erfordert einen Wert NULL für den angegebenen Parameter. Es wurde jedoch ein Wert ungleich NULL angegeben.</span><span class="sxs-lookup"><span data-stu-id="0eecb-119">The type specified in @type requires a NULL value for the specified parameter, however a non-NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0eecb-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0eecb-120">User Action</span></span>  
 <span data-ttu-id="0eecb-121">Geben Sie NULL für den Parameter an, oder ändern Sie den Typ in einen Typ, der Werte ungleich NULL für den Parameter zulässt.</span><span class="sxs-lookup"><span data-stu-id="0eecb-121">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eecb-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0eecb-122">See Also</span></span>  
 <span data-ttu-id="0eecb-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0eecb-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="0eecb-124">Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="0eecb-124">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
