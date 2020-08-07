---
title: MSSQLSERVER_41301 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41301 (Database Engine error)
ms.assetid: c6127e1e-2846-4ee9-bc42-2d896ea9730e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d4fa78b334f32033f96df002aeaf039994b396cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619147"
---
# <a name="mssqlserver_41301"></a><span data-ttu-id="81bc2-102">MSSQLSERVER_41301</span><span class="sxs-lookup"><span data-stu-id="81bc2-102">MSSQLSERVER_41301</span></span>
    
## <a name="details"></a><span data-ttu-id="81bc2-103">Details</span><span class="sxs-lookup"><span data-stu-id="81bc2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81bc2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="81bc2-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="81bc2-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="81bc2-105">Event ID</span></span>|<span data-ttu-id="81bc2-106">41301</span><span class="sxs-lookup"><span data-stu-id="81bc2-106">41301</span></span>|  
|<span data-ttu-id="81bc2-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="81bc2-107">Event Source</span></span>|<span data-ttu-id="81bc2-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81bc2-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81bc2-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="81bc2-109">Component</span></span>|<span data-ttu-id="81bc2-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81bc2-110">SQLEngine</span></span>|  
|<span data-ttu-id="81bc2-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="81bc2-111">Symbolic Name</span></span>|<span data-ttu-id="81bc2-112">COMMIT_DEPENDENCY_FAILURE</span><span class="sxs-lookup"><span data-stu-id="81bc2-112">COMMIT_DEPENDENCY_FAILURE</span></span>|  
|<span data-ttu-id="81bc2-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="81bc2-113">Message Text</span></span>|<span data-ttu-id="81bc2-114">Eine vorherige Transaktion, zu der die aktuelle Transaktion eine Abhängigkeit eingegangen war, wurde abgebrochen. Die aktuelle Transaktion kann keinen Commit mehr ausführen.</span><span class="sxs-lookup"><span data-stu-id="81bc2-114">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81bc2-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="81bc2-115">Explanation</span></span>  
 <span data-ttu-id="81bc2-116">Bei der Transaktion trat ein Abhängigkeitsfehler auf, sie kann nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="81bc2-116">The transaction encountered a dependency failure, and is now doomed.</span></span>  
  
 <span data-ttu-id="81bc2-117">Dieser Fehler kann auch durch zu viele abhängige Transaktionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="81bc2-117">This error can also be caused by too many dependent transactions.</span></span> <span data-ttu-id="81bc2-118">Jede Schreibtransaktion kann über eine begrenzte Anzahl abhängiger Transaktionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="81bc2-118">Any write transaction can have a limited number of dependent transactions.</span></span> <span data-ttu-id="81bc2-119">Dieser Fehler kann beispielsweise auftreten, wenn zu viele Lesetransaktionen versuchen, eine Abhängigkeit von der Updatetransaktion herzustellen.</span><span class="sxs-lookup"><span data-stu-id="81bc2-119">For example, this error can occur if too many read transactions try to take a dependency on the update transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81bc2-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="81bc2-120">User Action</span></span>  
 <span data-ttu-id="81bc2-121">Erledigen Sie keine Bearbeitung der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="81bc2-121">Don't do any work on the transaction.</span></span> <span data-ttu-id="81bc2-122">Rufen Sie ROLLBACK TRAN auf, um ein Rollback für die Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="81bc2-122">Call ROLLBACK TRAN to roll back the transaction.</span></span> <span data-ttu-id="81bc2-123">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="81bc2-123">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bc2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81bc2-124">See Also</span></span>  
 [<span data-ttu-id="81bc2-125">Aktivieren und Deaktivieren von Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="81bc2-125">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md)  
  
  
