---
title: MSSQLSERVER_41365 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619141"
---
# <a name="mssqlserver_41365"></a><span data-ttu-id="f3a41-102">MSSQLSERVER_41365</span><span class="sxs-lookup"><span data-stu-id="f3a41-102">MSSQLSERVER_41365</span></span>
    
## <a name="details"></a><span data-ttu-id="f3a41-103">Details</span><span class="sxs-lookup"><span data-stu-id="f3a41-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3a41-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f3a41-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f3a41-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f3a41-105">Event ID</span></span>|<span data-ttu-id="f3a41-106">41365</span><span class="sxs-lookup"><span data-stu-id="f3a41-106">41365</span></span>|  
|<span data-ttu-id="f3a41-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f3a41-107">Event Source</span></span>|<span data-ttu-id="f3a41-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3a41-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3a41-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="f3a41-109">Component</span></span>|<span data-ttu-id="f3a41-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f3a41-110">SQLEngine</span></span>|  
|<span data-ttu-id="f3a41-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f3a41-111">Symbolic Name</span></span>|<span data-ttu-id="f3a41-112">HK_MERGE_SCHEDULE_ERROR</span><span class="sxs-lookup"><span data-stu-id="f3a41-112">HK_MERGE_SCHEDULE_ERROR</span></span>|  
|<span data-ttu-id="f3a41-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f3a41-113">Message Text</span></span>|<span data-ttu-id="f3a41-114">Mergeanforderung für Transaktionsbereich [%ld, %ld] in Datenbank %.\*ls wurde nicht geplant.</span><span class="sxs-lookup"><span data-stu-id="f3a41-114">Merge request for transaction range [%ld, %ld] on database %.\*ls was not scheduled.</span></span> <span data-ttu-id="f3a41-115">Die Prüfpunktdateien, die den Bereich darstellen, sind entweder für Merge oder als Teil eines laufenden Mergevorgangs nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3a41-115">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3a41-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f3a41-116">Explanation</span></span>  
 <span data-ttu-id="f3a41-117">Die Prüfpunktdateien, die den Bereich darstellen, sind entweder für Merge oder als Teil eines laufenden Mergevorgangs nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3a41-117">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3a41-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f3a41-118">User Action</span></span>  
 <span data-ttu-id="f3a41-119">Stellen Sie einen besseren Transaktionsbereich für den Merge-/Wartevorgang bereit, bevor Sie erneut die gleiche Anforderung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="f3a41-119">Provide a better transaction range for merge/wait before issuing the same request again.</span></span> <span data-ttu-id="f3a41-120">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="f3a41-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a41-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3a41-121">See Also</span></span>  
 [<span data-ttu-id="f3a41-122">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="f3a41-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
