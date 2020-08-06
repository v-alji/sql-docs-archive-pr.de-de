---
title: MSSQLSERVER_1203 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1203 (Database Engine error)
ms.assetid: 33a35f00-98c8-46c6-b432-544b326b6117
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cea816a60ccd1b90d849194766edebd2d64d0b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620438"
---
# <a name="mssqlserver_1203"></a><span data-ttu-id="5c4b4-102">MSSQLSERVER_1203</span><span class="sxs-lookup"><span data-stu-id="5c4b4-102">MSSQLSERVER_1203</span></span>
    
## <a name="details"></a><span data-ttu-id="5c4b4-103">Details</span><span class="sxs-lookup"><span data-stu-id="5c4b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c4b4-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5c4b4-104">Product Name</span></span>|<span data-ttu-id="5c4b4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c4b4-105">SQL Server</span></span>|  
|<span data-ttu-id="5c4b4-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5c4b4-106">Event ID</span></span>|<span data-ttu-id="5c4b4-107">1203</span><span class="sxs-lookup"><span data-stu-id="5c4b4-107">1203</span></span>|  
|<span data-ttu-id="5c4b4-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5c4b4-108">Event Source</span></span>|<span data-ttu-id="5c4b4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5c4b4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5c4b4-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5c4b4-110">Component</span></span>|<span data-ttu-id="5c4b4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5c4b4-111">SQLEngine</span></span>|  
|<span data-ttu-id="5c4b4-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5c4b4-112">Symbolic Name</span></span>|<span data-ttu-id="5c4b4-113">LK_NOT</span><span class="sxs-lookup"><span data-stu-id="5c4b4-113">LK_NOT</span></span>|  
|<span data-ttu-id="5c4b4-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5c4b4-114">Message Text</span></span>|<span data-ttu-id="5c4b4-115">Der Prozess mit der ID %d versuchte, die Sperre für die %.\*ls-Ressource, deren Besitzer er nicht ist, aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-115">Process ID %d attempted to unlock a resource it does not own: %.\*ls.</span></span> <span data-ttu-id="5c4b4-116">Wiederholen Sie die Transaktion, da dieser Fehler möglicherweise auf einen zeitbedingten Fehler zurückzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-116">Retry the transaction, because this error may be caused by a timing condition.</span></span> <span data-ttu-id="5c4b4-117">Falls das Problem weiterhin besteht, wenden Sie sich an den Datenbankadministrator.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-117">If the problem persists, contact the database administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5c4b4-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5c4b4-118">Explanation</span></span>  
 <span data-ttu-id="5c4b4-119">Dieser Fehler tritt auf, wenn in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] andere Aktivitäten als gewöhnliche Cleanups nach der Verarbeitung ausgeführt werden und wenn festgestellt wird, dass eine bestimmte Seite, für die die Sperre aufgehoben werden soll, bereits entsperrt ist.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-119">This error occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is engaged in some activity other than ordinary post-processing cleanup and it finds that a particular page that it is trying to unlock is already unlocked.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="5c4b4-120">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="5c4b4-120">Possible Causes</span></span>  
 <span data-ttu-id="5c4b4-121">Die zugrunde liegende Ursache dieses Fehlers hängt möglicherweise mit Strukturproblemen in der betroffenen Datenbank zusammen.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-121">The underlying cause of this error may be related to structural problems within the affected database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5c4b4-122">verwaltet den Abruf und die Freigabe von Seiten zum Aufrechterhalten der Parallelitätssteuerung in der Mehrbenutzerumgebung.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-122">manages the acquisition and release of pages to maintain concurrency control in the multiuser environment.</span></span> <span data-ttu-id="5c4b4-123">Dieser Mechanismus wird durch die Verwendung verschiedener interner Sperrstrukturen sichergestellt, mit denen die Seite und die Art der vorhandenen Sperre angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-123">This mechanism is maintained by using various internal lock structures that identify the page and the type of lock present.</span></span> <span data-ttu-id="5c4b4-124">Sperren werden für die Verarbeitung der betreffenden Seiten abgerufen, und sie werden freigegeben, wenn die Verarbeitung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-124">Locks are acquired for processing of affected pages and released when the processing is finished.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5c4b4-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5c4b4-125">User Action</span></span>  
 <span data-ttu-id="5c4b4-126">Führen Sie DBCC CHECKDB für die Datenbank aus, zu der das Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-126">Execute DBCC CHECKDB against the database in which the object belongs.</span></span> <span data-ttu-id="5c4b4-127">Wenn mithilfe von DBCC CHECKDB keine Fehler gemeldet werden, versuchen Sie, die Verbindung wiederherzustellen, und führen Sie den Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-127">If DBCC CHECKDB reports no errors, try to reestablish the connection and execute the command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5c4b4-128">Wenn durch das Ausführen von DBCC CHECKDB mit einer der REPAIR-Klauseln das Indexproblem nicht behoben wird oder wenn Sie sich nicht sicher sind, wie sich DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt, wenden Sie sich an Ihren primären Anbieter für technischen Support.</span><span class="sxs-lookup"><span data-stu-id="5c4b4-128">If you are executing DBCC CHECKDB with one of the REPAIR clauses does not correct the index problem, or if you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider.</span></span>  
  
  
