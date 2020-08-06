---
title: MSSQLSERVER_844 | Microsoft Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4870d6e43ec12b49033ea3b5f88fa0d0cdd597a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616572"
---
# <a name="mssqlserver_844"></a><span data-ttu-id="f1626-102">MSSQLSERVER_844</span><span class="sxs-lookup"><span data-stu-id="f1626-102">MSSQLSERVER_844</span></span>
    
## <a name="details"></a><span data-ttu-id="f1626-103">Details</span><span class="sxs-lookup"><span data-stu-id="f1626-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1626-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f1626-104">Product Name</span></span>|<span data-ttu-id="f1626-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1626-105">SQL Server</span></span>|  
|<span data-ttu-id="f1626-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f1626-106">Event ID</span></span>|<span data-ttu-id="f1626-107">844</span><span class="sxs-lookup"><span data-stu-id="f1626-107">844</span></span>|  
|<span data-ttu-id="f1626-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f1626-108">Event Source</span></span>|<span data-ttu-id="f1626-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f1626-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f1626-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f1626-110">Component</span></span>|<span data-ttu-id="f1626-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f1626-111">SQLEngine</span></span>|  
|<span data-ttu-id="f1626-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f1626-112">Symbolic Name</span></span>|<span data-ttu-id="f1626-113">BUFLATCH_TIMEOUT_CONTINUE</span><span class="sxs-lookup"><span data-stu-id="f1626-113">BUFLATCH_TIMEOUT_CONTINUE</span></span>|  
|<span data-ttu-id="f1626-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f1626-114">Message Text</span></span>|<span data-ttu-id="f1626-115">Timeout beim Warten auf einen Pufferlatch -- Typ %d, Pufferpool %p, Seite %d:%d, STAT %#x, Datenbank-ID %d, Zuordnungseinheits-ID: %I64d%ls, Task 0x%p : %d, Wartezeit %d, Flags 0x%I64x, besitzender Task 0x%p.</span><span class="sxs-lookup"><span data-stu-id="f1626-115">Time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span>  <span data-ttu-id="f1626-116">Der Wartevorgang wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f1626-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f1626-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f1626-117">Explanation</span></span>  
 <span data-ttu-id="f1626-118">Ein Prozess wartet darauf, einen Latch abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f1626-118">A process is waiting to acquire a latch.</span></span> <span data-ttu-id="f1626-119">Das Problem kann dadurch verursacht werden, dass ein E/A-Vorgang zu viel Zeit beansprucht, bevor er abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f1626-119">This problem can be caused by an I/O operation taking too long to complete.</span></span> <span data-ttu-id="f1626-120">Normalerweise ist der Fehler das Ergebnis des Blockierens von Systemprozessen durch andere Tasks.</span><span class="sxs-lookup"><span data-stu-id="f1626-120">Typically this type of error is the result of other tasks blocking system processes.</span></span> <span data-ttu-id="f1626-121">In manchen Fällen kann dieser Fehler auch das Ergebnis eines Hardwarefehlers sein.</span><span class="sxs-lookup"><span data-stu-id="f1626-121">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1626-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f1626-122">User Action</span></span>  
 <span data-ttu-id="f1626-123">Versuchen Sie Folgendes, um zu verhindern, dass der Fehler erneut auftritt:</span><span class="sxs-lookup"><span data-stu-id="f1626-123">Try the following to prevent this error from occurring:</span></span>  
  
-   <span data-ttu-id="f1626-124">Reduzieren Sie die Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="f1626-124">Reduce workload.</span></span>  
  
-   <span data-ttu-id="f1626-125">Führen Sie eine Überprüfung auf zugehörige E/A-Fehler im Fehlerprotokoll oder Ereignisprotokoll aus.</span><span class="sxs-lookup"><span data-stu-id="f1626-125">Check for associated I/O failures in error log or event log.</span></span> <span data-ttu-id="f1626-126">E/A-Fehler deuten normalerweise auf eine Datenträgerfehlfunktion hin.</span><span class="sxs-lookup"><span data-stu-id="f1626-126">I/O failures typically point to a disk malfunction.</span></span>  
  
-   <span data-ttu-id="f1626-127">Überprüfen Sie das Fehlerprotokoll auf Tasks, die kein Ergebnis bereitstellen, sowie auf andere kritische Fehler.</span><span class="sxs-lookup"><span data-stu-id="f1626-127">Check the error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="f1626-128">Wenn kritische Fehler, z. B. Assert-Vorgänge, häufig auftreten, beheben Sie diese Probleme.</span><span class="sxs-lookup"><span data-stu-id="f1626-128">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="f1626-129">Wenn der Fehler wiederholt auftritt, wenden Sie sich an den Microsoft-Kundendienst und -Support.</span><span class="sxs-lookup"><span data-stu-id="f1626-129">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
