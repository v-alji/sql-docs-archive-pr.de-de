---
title: MSSQLSERVER_41342 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c0269322b30cee88e5ba3d50b6d391464b735f54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619873"
---
# <a name="mssqlserver_41342"></a><span data-ttu-id="04cc7-102">MSSQLSERVER_41342</span><span class="sxs-lookup"><span data-stu-id="04cc7-102">MSSQLSERVER_41342</span></span>
    
## <a name="details"></a><span data-ttu-id="04cc7-103">Details</span><span class="sxs-lookup"><span data-stu-id="04cc7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04cc7-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="04cc7-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="04cc7-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="04cc7-105">Event ID</span></span>|<span data-ttu-id="04cc7-106">41342</span><span class="sxs-lookup"><span data-stu-id="04cc7-106">41342</span></span>|  
|<span data-ttu-id="04cc7-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="04cc7-107">Event Source</span></span>|<span data-ttu-id="04cc7-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="04cc7-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="04cc7-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="04cc7-109">Component</span></span>|<span data-ttu-id="04cc7-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="04cc7-110">SQLEngine</span></span>|  
|<span data-ttu-id="04cc7-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="04cc7-111">Symbolic Name</span></span>|<span data-ttu-id="04cc7-112">HK_HW_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="04cc7-112">HK_HW_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="04cc7-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="04cc7-113">Message Text</span></span>|<span data-ttu-id="04cc7-114">Das Modell des Prozessors im System unterstützt nicht die Erstellung von *construct*.</span><span class="sxs-lookup"><span data-stu-id="04cc7-114">The model of the processor on the system does not support creating *construct*.</span></span> <span data-ttu-id="04cc7-115">Dieser Fehler tritt normalerweise bei älteren Prozessoren auf.</span><span class="sxs-lookup"><span data-stu-id="04cc7-115">This error typically occurs with older processors.</span></span> <span data-ttu-id="04cc7-116">Weitere Informationen zu unterstützten Modellen finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="04cc7-116">See [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for information on supported models.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="04cc7-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="04cc7-117">Explanation</span></span>  
 <span data-ttu-id="04cc7-118">Speicheroptimierte Tabellen erfordern ein Prozessormodell, das unteilbare Vergleichs- und Austauschvorgänge für 128-Bit-Werte unterstützt. Das erfordert die Assemblyanweisung CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="04cc7-118">Memory-optimized tables require a processor model that supports atomic compare-and-exchange operations on 128-bit values, which require the assembly instruction CMPXCHG16B.</span></span> <span data-ttu-id="04cc7-119">Bestimmte ältere AMD-Prozessormodelle unterstützen nicht die CMPXCHG16B-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="04cc7-119">Certain older AMD processor models do not support the CMPXCHG16B instruction.</span></span> <span data-ttu-id="04cc7-120">Außerdem wird diese Anweisung von bestimmten Virtualisierungsumgebungen standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="04cc7-120">Also, certain virtualization environments do not enable this instruction by default.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04cc7-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="04cc7-121">User Action</span></span>  
 <span data-ttu-id="04cc7-122">Aktualisieren Sie den Prozessor.</span><span class="sxs-lookup"><span data-stu-id="04cc7-122">Upgrade your processor.</span></span> <span data-ttu-id="04cc7-123">Wenn Ihr Prozessor die Anweisung unterstützt und Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem virtuellen Computer ausführen, ändern Sie die Konfiguration, sodass die Anweisung CMPXCHG16B unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="04cc7-123">If your processor supports the instruction and you are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a virtual machine, change the configuration to support the instruction CMPXCHG16B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04cc7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04cc7-124">See Also</span></span>  
 [<span data-ttu-id="04cc7-125">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="04cc7-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
