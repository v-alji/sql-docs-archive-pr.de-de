---
title: MSSQLSERVER_5233 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5233 (Database Engine error)
ms.assetid: 7a855afa-2d3b-49b7-adef-197b99fc98b1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a5e2c603652534a6d3093a01da0a926a7195954
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620888"
---
# <a name="mssqlserver_5233"></a><span data-ttu-id="a08a9-102">MSSQLSERVER_5233</span><span class="sxs-lookup"><span data-stu-id="a08a9-102">MSSQLSERVER_5233</span></span>
    
## <a name="details"></a><span data-ttu-id="a08a9-103">Details</span><span class="sxs-lookup"><span data-stu-id="a08a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a08a9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a08a9-104">Product Name</span></span>|<span data-ttu-id="a08a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a08a9-105">SQL Server</span></span>|  
|<span data-ttu-id="a08a9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a08a9-106">Event ID</span></span>|<span data-ttu-id="a08a9-107">5233</span><span class="sxs-lookup"><span data-stu-id="a08a9-107">5233</span></span>|  
|<span data-ttu-id="a08a9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a08a9-108">Event Source</span></span>|<span data-ttu-id="a08a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a08a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a08a9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a08a9-110">Component</span></span>|<span data-ttu-id="a08a9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a08a9-111">SQLEngine</span></span>|  
|<span data-ttu-id="a08a9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a08a9-112">Symbolic Name</span></span>|<span data-ttu-id="a08a9-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="a08a9-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="a08a9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a08a9-114">Message Text</span></span>|<span data-ttu-id="a08a9-115">Tabellenfehler: Zuordnungseinheits-ID A_ID, Seite P_ID.</span><span class="sxs-lookup"><span data-stu-id="a08a9-115">Table error: alloc unit ID A_ID, page P_ID.</span></span> <span data-ttu-id="a08a9-116">Fehler beim Test (TEST).</span><span class="sxs-lookup"><span data-stu-id="a08a9-116">The test (TEST) failed.</span></span> <span data-ttu-id="a08a9-117">Die Werte sind VAL1 und VAL2.</span><span class="sxs-lookup"><span data-stu-id="a08a9-117">The values are VAL1 and VAL2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a08a9-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a08a9-118">Explanation</span></span>  
 <span data-ttu-id="a08a9-119">Aufgrund einer Beschädigung im Seitenheader ist auf der Seite *P_ID* ein Fehler bei der Überwachung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a08a9-119">Page *P_ID* has failed auditing due to a corruption in its page header.</span></span> <span data-ttu-id="a08a9-120">Die Zeichenfolge in TEST gibt den eigentlichen Test an, bei dem der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a08a9-120">The string in TEST gives the actual test that failed.</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a08a9-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="a08a9-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a08a9-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="a08a9-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a08a9-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a08a9-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a08a9-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a08a9-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a08a9-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="a08a9-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a08a9-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a08a9-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a08a9-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="a08a9-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a08a9-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="a08a9-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a08a9-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="a08a9-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a08a9-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="a08a9-130">Restore from Backup</span></span>  
 <span data-ttu-id="a08a9-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a08a9-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a08a9-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a08a9-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a08a9-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a08a9-133">Not applicable.</span></span> <span data-ttu-id="a08a9-134">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="a08a9-134">This error cannot be repaired.</span></span> <span data-ttu-id="a08a9-135">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a08a9-135">If you cannot restore the database from a backup, contact Microsoft Customer Service and Support (CSS).</span></span>  
  
  
