---
title: MSSQLSERVER_17883 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46488fb6f7adac2c1109871f2aad4c79352829ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696882"
---
# <a name="mssqlserver_17883"></a><span data-ttu-id="53cf5-102">MSSQLSERVER_17883</span><span class="sxs-lookup"><span data-stu-id="53cf5-102">MSSQLSERVER_17883</span></span>
    
## <a name="details"></a><span data-ttu-id="53cf5-103">Details</span><span class="sxs-lookup"><span data-stu-id="53cf5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53cf5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="53cf5-104">Product Name</span></span>|<span data-ttu-id="53cf5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53cf5-105">SQL Server</span></span>|  
|<span data-ttu-id="53cf5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="53cf5-106">Event ID</span></span>|<span data-ttu-id="53cf5-107">17883</span><span class="sxs-lookup"><span data-stu-id="53cf5-107">17883</span></span>|  
|<span data-ttu-id="53cf5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="53cf5-108">Event Source</span></span>|<span data-ttu-id="53cf5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53cf5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53cf5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="53cf5-110">Component</span></span>|<span data-ttu-id="53cf5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53cf5-111">SQLEngine</span></span>|  
|<span data-ttu-id="53cf5-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="53cf5-112">Symbolic Name</span></span>|<span data-ttu-id="53cf5-113">SRV_SCHEDULER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="53cf5-113">SRV_SCHEDULER_NONYIELDING</span></span>|  
|<span data-ttu-id="53cf5-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="53cf5-114">Message Text</span></span>|<span data-ttu-id="53cf5-115">Prozess %ld:%ld:%ld (0x%lx) Arbeitsthread 0x%p stellt im Zeitplanungsmodul %ld kein Ergebnis bereit.</span><span class="sxs-lookup"><span data-stu-id="53cf5-115">Process %ld:%ld:%ld (0x%lx) Worker 0x%p appears to be non-yielding on Scheduler %ld.</span></span> <span data-ttu-id="53cf5-116">Threaderstellungszeit: %I64d.</span><span class="sxs-lookup"><span data-stu-id="53cf5-116">Thread creation time: %I64d.</span></span> <span data-ttu-id="53cf5-117">Ungefähre Thread-CPU-Belegung: Kernel %I64d Millisek., Benutzer %I64d Millisek.</span><span class="sxs-lookup"><span data-stu-id="53cf5-117">Approx Thread CPU Used: kernel %I64d ms, user %I64d ms.</span></span> <span data-ttu-id="53cf5-118">Prozessnutzung %d%%.</span><span class="sxs-lookup"><span data-stu-id="53cf5-118">Process Utilization %d%%.</span></span> <span data-ttu-id="53cf5-119">Leerlauf des Systems: %d%%.</span><span class="sxs-lookup"><span data-stu-id="53cf5-119">System Idle %d%%.</span></span> <span data-ttu-id="53cf5-120">Intervall: % I64d Millisek.</span><span class="sxs-lookup"><span data-stu-id="53cf5-120">Interval: %I64d ms.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53cf5-121">Erklärung</span><span class="sxs-lookup"><span data-stu-id="53cf5-121">Explanation</span></span>  
 <span data-ttu-id="53cf5-122">Kennzeichnet ein mögliches Problem mit einem Thread, der in einem Zeitplanungsmodul kein Ergebnis bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="53cf5-122">Indicates that there is a possible problem with a thread not yielding on a scheduler.</span></span>  <span data-ttu-id="53cf5-123">Die Ursache könnte ein Programmfehler in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sein. Das Problem kann auch dadurch verursacht werden, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht genug Zyklen für die Ausführung abruft.</span><span class="sxs-lookup"><span data-stu-id="53cf5-123">This could be caused by a bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not getting enough cycles to execute.</span></span>  <span data-ttu-id="53cf5-124">Dieser Fehler könnte behoben werden, wenn der Thread Ergebnisse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="53cf5-124">This error could go away if the thread eventually yields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53cf5-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="53cf5-125">User Action</span></span>  
 <span data-ttu-id="53cf5-126">Bei übermäßiger Last im System reduzieren Sie die Last, wenden Sie sich andernfalls an Microsoft Support Services.</span><span class="sxs-lookup"><span data-stu-id="53cf5-126">If excessive load on system reduce load otherwise contact Microsoft Customer Support Services.</span></span>  
  
  
