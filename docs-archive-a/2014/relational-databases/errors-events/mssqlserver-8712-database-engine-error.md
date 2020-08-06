---
title: MSSQLSERVER_8712 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9285d4846cac5af2dd6e87ab55d5fd0610586d07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630662"
---
# <a name="mssqlserver_8712"></a><span data-ttu-id="fc6e9-102">MSSQLSERVER_8712</span><span class="sxs-lookup"><span data-stu-id="fc6e9-102">MSSQLSERVER_8712</span></span>
    
## <a name="details"></a><span data-ttu-id="fc6e9-103">Details</span><span class="sxs-lookup"><span data-stu-id="fc6e9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc6e9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="fc6e9-104">Product Name</span></span>|<span data-ttu-id="fc6e9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc6e9-105">SQL Server</span></span>|  
|<span data-ttu-id="fc6e9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="fc6e9-106">Event ID</span></span>|<span data-ttu-id="fc6e9-107">8712</span><span class="sxs-lookup"><span data-stu-id="fc6e9-107">8712</span></span>|  
|<span data-ttu-id="fc6e9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="fc6e9-108">Event Source</span></span>|<span data-ttu-id="fc6e9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fc6e9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fc6e9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="fc6e9-110">Component</span></span>|<span data-ttu-id="fc6e9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fc6e9-111">SQLEngine</span></span>|  
|<span data-ttu-id="fc6e9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="fc6e9-112">Symbolic Name</span></span>|<span data-ttu-id="fc6e9-113">USEPLAN_ERR_NO_INDEX</span><span class="sxs-lookup"><span data-stu-id="fc6e9-113">USEPLAN_ERR_NO_INDEX</span></span>|  
|<span data-ttu-id="fc6e9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="fc6e9-114">Message Text</span></span>|<span data-ttu-id="fc6e9-115">Der im USE PLAN-Hinweis angegebene Index '%.\*ls' ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fc6e9-115">Index '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="fc6e9-116">Geben Sie einen vorhandenen Index an, oder erstellen Sie einen Index mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="fc6e9-116">Specify an existing index, or create an index with the specified name.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fc6e9-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="fc6e9-117">Explanation</span></span>  
 <span data-ttu-id="fc6e9-118">Ein im USE PLAN-Hinweis angegebener Index ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fc6e9-118">An index that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc6e9-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="fc6e9-119">User Action</span></span>  
 <span data-ttu-id="fc6e9-120">Stellen Sie sicher, dass alle im USE PLAN-Hinweis angegebenen Indizes vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fc6e9-120">Ensure all indexes that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6e9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc6e9-121">See Also</span></span>  
 <span data-ttu-id="fc6e9-122">[Abfragehinweise (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="fc6e9-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="fc6e9-123">Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="fc6e9-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
