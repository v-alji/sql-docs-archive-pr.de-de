---
title: MSSQLSERVER_10539 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd1f190b8f5d3ab9755409bdd034fa374ea5314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699711"
---
# <a name="mssqlserver_10539"></a><span data-ttu-id="79169-102">MSSQLSERVER_10539</span><span class="sxs-lookup"><span data-stu-id="79169-102">MSSQLSERVER_10539</span></span>
    
## <a name="details"></a><span data-ttu-id="79169-103">Details</span><span class="sxs-lookup"><span data-stu-id="79169-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79169-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="79169-104">Product Name</span></span>|<span data-ttu-id="79169-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="79169-105">SQL Server</span></span>|  
|<span data-ttu-id="79169-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="79169-106">Event ID</span></span>|<span data-ttu-id="79169-107">10539</span><span class="sxs-lookup"><span data-stu-id="79169-107">10539</span></span>|  
|<span data-ttu-id="79169-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="79169-108">Event Source</span></span>|<span data-ttu-id="79169-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="79169-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="79169-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="79169-110">Component</span></span>|<span data-ttu-id="79169-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="79169-111">SQLEngine</span></span>|  
|<span data-ttu-id="79169-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="79169-112">Symbolic Name</span></span>|<span data-ttu-id="79169-113">PG_NO_PLAN_FOR_STMT</span><span class="sxs-lookup"><span data-stu-id="79169-113">PG_NO_PLAN_FOR_STMT</span></span>|  
|<span data-ttu-id="79169-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="79169-114">Message Text</span></span>|<span data-ttu-id="79169-115">Die Planhinweisliste '%.\*ls' kann nicht aus dem Cache erstellt werden, weil kein Abfrageplan für die Anweisung mit dem Startoffset %d verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="79169-115">Cannot create plan guide '%.\*ls' from cache because a query plan is not available for the statement with start offset %d.</span></span> <span data-ttu-id="79169-116">Dieses Problem kann auftreten, wenn die Anweisung von Datenbankobjekten abhängig ist, die noch nicht erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="79169-116">This problem can occur if the statement depends on database objects that have not yet been created.</span></span> <span data-ttu-id="79169-117">Stellen Sie sicher, dass alle erforderlichen Datenbankobjekte vorhanden sind, und führen Sie die Anweisung vor dem Erstellen der Planhinweisliste aus.</span><span class="sxs-lookup"><span data-stu-id="79169-117">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79169-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="79169-118">Explanation</span></span>  
 <span data-ttu-id="79169-119">Im Plancache ist kein Abfrageplan für die Anweisung mit dem angegebenen Startoffset vorhanden.</span><span class="sxs-lookup"><span data-stu-id="79169-119">A query plan is not available in the plan cache for the statement with the specified starting offset.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79169-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="79169-120">User Action</span></span>  
 <span data-ttu-id="79169-121">Stellen Sie sicher, dass alle erforderlichen Datenbankobjekte vorhanden sind, und führen Sie die Anweisung vor dem Erstellen der Planhinweisliste aus.</span><span class="sxs-lookup"><span data-stu-id="79169-121">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79169-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79169-122">See Also</span></span>  
 [<span data-ttu-id="79169-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="79169-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
