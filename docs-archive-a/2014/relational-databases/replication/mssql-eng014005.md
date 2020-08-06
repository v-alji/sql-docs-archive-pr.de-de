---
title: MSSQL_ENG014005 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014005 error
ms.assetid: f168f0d6-cb11-45d4-9781-c374d7f388ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d820fd26cceee72b0d08204d6f6ce73a76508e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608566"
---
# <a name="mssql_eng014005"></a><span data-ttu-id="6820a-102">MSSQL_ENG014005</span><span class="sxs-lookup"><span data-stu-id="6820a-102">MSSQL_ENG014005</span></span>
    
## <a name="message-details"></a><span data-ttu-id="6820a-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="6820a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6820a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6820a-104">Product Name</span></span>|<span data-ttu-id="6820a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6820a-105">SQL Server</span></span>|  
|<span data-ttu-id="6820a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6820a-106">Event ID</span></span>|<span data-ttu-id="6820a-107">14005</span><span class="sxs-lookup"><span data-stu-id="6820a-107">14005</span></span>|  
|<span data-ttu-id="6820a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6820a-108">Event Source</span></span>|<span data-ttu-id="6820a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6820a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6820a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6820a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="6820a-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6820a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="6820a-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6820a-112">Message Text</span></span>|<span data-ttu-id="6820a-113">Die Veröffentlichung konnte nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="6820a-113">Could not drop publication.</span></span> <span data-ttu-id="6820a-114">Es besteht ein Abonnement für sie.</span><span class="sxs-lookup"><span data-stu-id="6820a-114">A subscription exists to it.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6820a-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6820a-115">Explanation</span></span>  
 <span data-ttu-id="6820a-116">Sie haben versucht, eine Veröffentlichung zu löschen, der ein oder mehrere Abonnements zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6820a-116">You have tried to drop a publication which has one or more associated subscriptions.</span></span> <span data-ttu-id="6820a-117">Eine Veröffentlichung kann aber nur gelöscht werden, wenn ihr keine Abonnements zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6820a-117">A publication can only be dropped if there are no associated subscriptions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6820a-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6820a-118">User Action</span></span>  
 <span data-ttu-id="6820a-119">Löschen Sie erst die Abonnements, bevor Sie die Veröffentlichung löschen.</span><span class="sxs-lookup"><span data-stu-id="6820a-119">Drop the subscriptions before dropping the publication.</span></span> <span data-ttu-id="6820a-120">Wenn Sie zum Löschen der Veröffentlichung [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verwenden, haben Sie die Möglichkeit, vor dem Löschen der Veröffentlichung automatisch alle zugeordneten Abonnements löschen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="6820a-120">If you use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to drop the publication, it will give you the option to automatically drop all associated subscriptions before dropping the publication.</span></span> <span data-ttu-id="6820a-121">Wenn Sie zum Löschen der Veröffentlichung gespeicherte Prozeduren verwenden, müssen Sie die Abonnements zuerst explizit löschen.</span><span class="sxs-lookup"><span data-stu-id="6820a-121">If you use stored procedures, you must explicitly drop the subscriptions first.</span></span> <span data-ttu-id="6820a-122">Weitere Informationen finden Sie unter [Delete a Push Subscription](delete-a-push-subscription.md) und [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6820a-122">For more information, see [Delete a Push Subscription](delete-a-push-subscription.md) and [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="6820a-123">Wenn für die Veröffentlichung keine Abonnements vorhanden zu sein scheinen oder wenn dieser Fehler beim Erstellen einer Veröffentlichung angezeigt wird, könnte noch ein vorheriges Abonnement vorhanden sein, das nicht vollständig leer war, bevor versucht wurde, es zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6820a-123">If no subscriptions appear to exist for the publication or if you see this error when you create a publication, you might have a previous subscription that was not completely cleaned up when it was removed.</span></span> <span data-ttu-id="6820a-124">Führen Sie [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) in der Datenbank aus, um alle mit der Replikation zusammenhängenden Objekte und Einstellungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6820a-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) on the database to remove all objects and settings related to replication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6820a-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6820a-125">See Also</span></span>  
 [<span data-ttu-id="6820a-126">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="6820a-126">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
