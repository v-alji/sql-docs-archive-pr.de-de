---
title: MSSQLSERVER_8689 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698222"
---
# <a name="mssqlserver_8689"></a><span data-ttu-id="a0897-102">MSSQLSERVER_8689</span><span class="sxs-lookup"><span data-stu-id="a0897-102">MSSQLSERVER_8689</span></span>
    
## <a name="details"></a><span data-ttu-id="a0897-103">Details</span><span class="sxs-lookup"><span data-stu-id="a0897-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0897-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a0897-104">Product Name</span></span>|<span data-ttu-id="a0897-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0897-105">SQL Server</span></span>|  
|<span data-ttu-id="a0897-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a0897-106">Event ID</span></span>|<span data-ttu-id="a0897-107">8689</span><span class="sxs-lookup"><span data-stu-id="a0897-107">8689</span></span>|  
|<span data-ttu-id="a0897-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a0897-108">Event Source</span></span>|<span data-ttu-id="a0897-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a0897-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a0897-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a0897-110">Component</span></span>|<span data-ttu-id="a0897-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a0897-111">SQLEngine</span></span>|  
|<span data-ttu-id="a0897-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a0897-112">Symbolic Name</span></span>|<span data-ttu-id="a0897-113">USEPLAN_ERR_NO_DB</span><span class="sxs-lookup"><span data-stu-id="a0897-113">USEPLAN_ERR_NO_DB</span></span>|  
|<span data-ttu-id="a0897-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a0897-114">Message Text</span></span>|<span data-ttu-id="a0897-115">Die im USE PLAN-Hinweis angegebene Datenbank '%.\*ls' ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a0897-115">Database '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="a0897-116">Geben Sie eine vorhandene Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="a0897-116">Specify an existing database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0897-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a0897-117">Explanation</span></span>  
 <span data-ttu-id="a0897-118">Eine im USE PLAN-Hinweis angegebene Datenbank ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a0897-118">A database that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0897-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a0897-119">User Action</span></span>  
 <span data-ttu-id="a0897-120">Stellen Sie sicher, dass alle im USE PLAN-Hinweis angegebenen Datenbanken vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a0897-120">Ensure all databases that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0897-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0897-121">See Also</span></span>  
 <span data-ttu-id="a0897-122">[Abfragehinweise (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="a0897-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="a0897-123">Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="a0897-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
