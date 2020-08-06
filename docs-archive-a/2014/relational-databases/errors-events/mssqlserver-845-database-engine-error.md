---
title: MSSQLSERVER_845 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 24bfb8b3758d0656dad96e4af4ed3b94aa51e07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616568"
---
# <a name="mssqlserver_845"></a><span data-ttu-id="cab2a-102">MSSQLSERVER_845</span><span class="sxs-lookup"><span data-stu-id="cab2a-102">MSSQLSERVER_845</span></span>
    
## <a name="details"></a><span data-ttu-id="cab2a-103">Details</span><span class="sxs-lookup"><span data-stu-id="cab2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cab2a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="cab2a-104">Product Name</span></span>|<span data-ttu-id="cab2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cab2a-105">SQL Server</span></span>|  
|<span data-ttu-id="cab2a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="cab2a-106">Event ID</span></span>|<span data-ttu-id="cab2a-107">845</span><span class="sxs-lookup"><span data-stu-id="cab2a-107">845</span></span>|  
|<span data-ttu-id="cab2a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="cab2a-108">Event Source</span></span>|<span data-ttu-id="cab2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cab2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cab2a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="cab2a-110">Component</span></span>|<span data-ttu-id="cab2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cab2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="cab2a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="cab2a-112">Symbolic Name</span></span>|<span data-ttu-id="cab2a-113">BUFLATCH_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cab2a-113">BUFLATCH_TIMEOUT</span></span>|  
|<span data-ttu-id="cab2a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="cab2a-114">Message Text</span></span>|<span data-ttu-id="cab2a-115">Timeout beim Warten auf Pufferlatchtyp %d für Seite %S_PGID, Datenbank-ID %d.</span><span class="sxs-lookup"><span data-stu-id="cab2a-115">Time-out occurred while waiting for buffer latch type %d for page %S_PGID, database ID %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cab2a-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="cab2a-116">Explanation</span></span>  
 <span data-ttu-id="cab2a-117">Ein Prozess hat auf die Beschaffung eines Latchs gewartet, aber für den Prozess wurde so lange gewartet, bis das Zeitlimit abgelaufen und die Beschaffung nicht mehr möglich war.</span><span class="sxs-lookup"><span data-stu-id="cab2a-117">A process was waiting to acquire a latch, but the process waited until the time limit expired and failed to acquire one.</span></span> <span data-ttu-id="cab2a-118">Dies kann auftreten, wenn das Ausführen eines E/A-Vorgangs zu lange dauert, was normalerweise daraus resultiert, dass Systemprozesse durch andere Tasks blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="cab2a-118">This can occur if an I/O operation takes too long to complete, usually as a result of other tasks blocking system processes.</span></span> <span data-ttu-id="cab2a-119">In manchen Fällen kann dieser Fehler auch das Ergebnis eines Hardwarefehlers sein.</span><span class="sxs-lookup"><span data-stu-id="cab2a-119">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cab2a-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="cab2a-120">User Action</span></span>  
 <span data-ttu-id="cab2a-121">Durch folgende Aktionen kann dieser Fehler verhindert werden:</span><span class="sxs-lookup"><span data-stu-id="cab2a-121">Performing the following tasks may prevent this error:</span></span>  
  
-   <span data-ttu-id="cab2a-122">Reduzieren Sie die Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="cab2a-122">Reduce the workload.</span></span>  
  
-   <span data-ttu-id="cab2a-123">Überprüfen Sie, ob zugehörige E/A-Fehler im Fehlerprotokoll oder Ereignisprotokoll vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cab2a-123">Verify whether there are associated I/O failures in the error log or event log.</span></span> <span data-ttu-id="cab2a-124">E/A-Fehler werden typischerweise durch Datenträgerfehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="cab2a-124">I/O failures are typically caused by disk malfunction.</span></span>  
  
-   <span data-ttu-id="cab2a-125">Überprüfen Sie das Fehlerprotokoll auf Tasks, die kein Ergebnis bereitstellen, sowie auf andere kritische Fehler.</span><span class="sxs-lookup"><span data-stu-id="cab2a-125">Check error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="cab2a-126">Wenn kritische Fehler, z. B. Assert-Vorgänge, häufig auftreten, beheben Sie diese Probleme.</span><span class="sxs-lookup"><span data-stu-id="cab2a-126">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="cab2a-127">Wenn der Fehler wiederholt auftritt, wenden Sie sich an den Microsoft-Kundendienst und -Support.</span><span class="sxs-lookup"><span data-stu-id="cab2a-127">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
