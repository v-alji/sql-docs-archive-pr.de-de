---
title: MSSQLSERVER_5256 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5256 (Database Engine error)
ms.assetid: 6fe254b4-2926-446f-8b20-0f1d921a4615
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9146b7744e78550463cbec4c05df5fd75a049898
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718163"
---
# <a name="mssqlserver_5256"></a><span data-ttu-id="bcb57-102">MSSQLSERVER_5256</span><span class="sxs-lookup"><span data-stu-id="bcb57-102">MSSQLSERVER_5256</span></span>
    
## <a name="details"></a><span data-ttu-id="bcb57-103">Details</span><span class="sxs-lookup"><span data-stu-id="bcb57-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcb57-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="bcb57-104">Product Name</span></span>|<span data-ttu-id="bcb57-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bcb57-105">SQL Server</span></span>|  
|<span data-ttu-id="bcb57-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bcb57-106">Event ID</span></span>|<span data-ttu-id="bcb57-107">5256</span><span class="sxs-lookup"><span data-stu-id="bcb57-107">5256</span></span>|  
|<span data-ttu-id="bcb57-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="bcb57-108">Event Source</span></span>|<span data-ttu-id="bcb57-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bcb57-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bcb57-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="bcb57-110">Component</span></span>|<span data-ttu-id="bcb57-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bcb57-111">SQLEngine</span></span>|  
|<span data-ttu-id="bcb57-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="bcb57-112">Symbolic Name</span></span>|<span data-ttu-id="bcb57-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="bcb57-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="bcb57-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bcb57-114">Message Text</span></span>|<span data-ttu-id="bcb57-115">Tabellenfehler: Zuordnungseinheits-ID A_ID, Seite P_ID1 enthält eine falsche Seiten-ID im Seitenheader.</span><span class="sxs-lookup"><span data-stu-id="bcb57-115">Table error: alloc unit ID A_ID, page P_ID1 contains an incorrect page ID in its page header.</span></span> <span data-ttu-id="bcb57-116">PageId-Wert im Seitenheader = P_ID2.</span><span class="sxs-lookup"><span data-stu-id="bcb57-116">The PageId in the page header = P_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bcb57-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bcb57-117">Explanation</span></span>  
 <span data-ttu-id="bcb57-118">Der Seitenheader von Seite *P_ID1* enthält die falsche Seiten-ID *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="bcb57-118">The page header of page *P_ID1* contains an incorrect page ID, *P_ID2*.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bcb57-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bcb57-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="bcb57-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="bcb57-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="bcb57-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="bcb57-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="bcb57-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bcb57-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="bcb57-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bcb57-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="bcb57-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="bcb57-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="bcb57-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bcb57-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="bcb57-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="bcb57-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="bcb57-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="bcb57-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="bcb57-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="bcb57-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="bcb57-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="bcb57-129">Restore from Backup</span></span>  
 <span data-ttu-id="bcb57-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bcb57-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="bcb57-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="bcb57-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="bcb57-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="bcb57-132">Not applicable.</span></span> <span data-ttu-id="bcb57-133">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="bcb57-133">This error cannot be repaired.</span></span> <span data-ttu-id="bcb57-134">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcb57-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
