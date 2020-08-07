---
title: MSSQLSERVER_8649 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8649 (Database Engine error)
ms.assetid: 992dbc74-7c3a-498b-9f1b-b28387640677
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b39ed0d8ffe5f7f601b6cb1393596d0d6546e557
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619853"
---
# <a name="mssqlserver_8649"></a><span data-ttu-id="39dd4-102">MSSQLSERVER_8649</span><span class="sxs-lookup"><span data-stu-id="39dd4-102">MSSQLSERVER_8649</span></span>
    
## <a name="details"></a><span data-ttu-id="39dd4-103">Details</span><span class="sxs-lookup"><span data-stu-id="39dd4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39dd4-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="39dd4-104">Product Name</span></span>|<span data-ttu-id="39dd4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="39dd4-105">SQL Server</span></span>|  
|<span data-ttu-id="39dd4-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="39dd4-106">Event ID</span></span>|<span data-ttu-id="39dd4-107">8649</span><span class="sxs-lookup"><span data-stu-id="39dd4-107">8649</span></span>|  
|<span data-ttu-id="39dd4-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="39dd4-108">Event Source</span></span>|<span data-ttu-id="39dd4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="39dd4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="39dd4-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="39dd4-110">Component</span></span>|<span data-ttu-id="39dd4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="39dd4-111">SQLEngine</span></span>|  
|<span data-ttu-id="39dd4-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="39dd4-112">Symbolic Name</span></span>|<span data-ttu-id="39dd4-113">COST_TOO_HIGH</span><span class="sxs-lookup"><span data-stu-id="39dd4-113">COST_TOO_HIGH</span></span>|  
|<span data-ttu-id="39dd4-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="39dd4-114">Message Text</span></span>|<span data-ttu-id="39dd4-115">Die Abfrage wurde abgebrochen, da die geschätzten Kosten der Abfrage (%d) den konfigurierten Schwellenwert %d überschreiten.</span><span class="sxs-lookup"><span data-stu-id="39dd4-115">The query has been canceled because the estimated cost of this query (%d) exceeds the configured threshold of %d.</span></span> <span data-ttu-id="39dd4-116">Wenden Sie sich an den Systemadministrator.</span><span class="sxs-lookup"><span data-stu-id="39dd4-116">Contact the system administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="39dd4-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="39dd4-117">Explanation</span></span>  
 <span data-ttu-id="39dd4-118">Die Abfrage wurde abgebrochen, weil die geschätzten Kosten dieser Abfrage den für QUERY_GOVERNOR_COST_LIMIT festgelegten konfigurierten Schwellenwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="39dd4-118">The query was canceled because the estimated cost of this query exceeds the configured threshold set for the QUERY_GOVERNOR_COST_LIMIT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39dd4-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="39dd4-119">User Action</span></span>  
 <span data-ttu-id="39dd4-120">Setzen Sie die Option QUERY_GOVERNOR_COST_LIMIT auf einen höheren Wert.</span><span class="sxs-lookup"><span data-stu-id="39dd4-120">Set the QUERY_GOVERNOR_COST_LIMIT option to a higher value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39dd4-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39dd4-121">See Also</span></span>  
 [<span data-ttu-id="39dd4-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39dd4-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql)  
  
  
