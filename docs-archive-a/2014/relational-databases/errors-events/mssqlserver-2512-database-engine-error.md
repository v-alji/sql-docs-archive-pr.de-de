---
title: MSSQLSERVER_2512 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2512 (Database Engine error)
ms.assetid: 989b527f-5b02-403c-9b7f-51580f4e7688
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da121c8b49ab8290c494d33f0f2a0ba6fded9e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698258"
---
# <a name="mssqlserver_2512"></a><span data-ttu-id="fd3d8-102">MSSQLSERVER_2512</span><span class="sxs-lookup"><span data-stu-id="fd3d8-102">MSSQLSERVER_2512</span></span>
    
## <a name="details"></a><span data-ttu-id="fd3d8-103">Details</span><span class="sxs-lookup"><span data-stu-id="fd3d8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd3d8-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="fd3d8-104">Product Name</span></span>|<span data-ttu-id="fd3d8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd3d8-105">SQL Server</span></span>|  
|<span data-ttu-id="fd3d8-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="fd3d8-106">Event ID</span></span>|<span data-ttu-id="fd3d8-107">2512</span><span class="sxs-lookup"><span data-stu-id="fd3d8-107">2512</span></span>|  
|<span data-ttu-id="fd3d8-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="fd3d8-108">Event Source</span></span>|<span data-ttu-id="fd3d8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fd3d8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fd3d8-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="fd3d8-110">Component</span></span>|<span data-ttu-id="fd3d8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fd3d8-111">SQLEngine</span></span>|  
|<span data-ttu-id="fd3d8-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="fd3d8-112">Symbolic Name</span></span>|<span data-ttu-id="fd3d8-113">DBCC_DUPLICATE_KEYS</span><span class="sxs-lookup"><span data-stu-id="fd3d8-113">DBCC_DUPLICATE_KEYS</span></span>|  
|<span data-ttu-id="fd3d8-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="fd3d8-114">Message Text</span></span>|<span data-ttu-id="fd3d8-115">Tabellenfehler: Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ).</span><span class="sxs-lookup"><span data-stu-id="fd3d8-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="fd3d8-116">Doppelte Schlüssel auf Seite P_ID1, Slot SLOT1 und Seite P_ID2, Slot SLOT2.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-116">Duplicate keys on page P_ID1 slot SLOT1 and page P_ID2 slot SLOT2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fd3d8-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="fd3d8-117">Explanation</span></span>  
 <span data-ttu-id="fd3d8-118">Die zwei angegebenen Slots verfügen über identische Schlüssel, einschließlich der `uniqueifiers`.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-118">The two specified slots have identical keys, including any `uniqueifiers`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd3d8-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="fd3d8-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="fd3d8-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="fd3d8-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="fd3d8-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="fd3d8-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="fd3d8-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="fd3d8-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="fd3d8-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="fd3d8-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="fd3d8-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="fd3d8-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="fd3d8-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="fd3d8-129">Restore from Backup</span></span>  
 <span data-ttu-id="fd3d8-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="fd3d8-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="fd3d8-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="fd3d8-132">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="fd3d8-133">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="fd3d8-134">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fd3d8-135">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="fd3d8-136">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="fd3d8-137">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="fd3d8-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="fd3d8-138">Wenn einer der Datensätze inaktiv oder der Index nicht eindeutig ist, kann dieses Problem von DBCC durch erneute Indexgenerierung repariert werden.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-138">If either record is a ghost or the index is nonunique, DBCC can repair this problem by rebuilding the index.</span></span> <span data-ttu-id="fd3d8-139">Andernfalls wird durch REPAIR der Slot *SLOT2* auf Seite *P_ID2* gelöscht oder als inaktiv markiert.</span><span class="sxs-lookup"><span data-stu-id="fd3d8-139">Otherwise, if necessary, REPAIR will delete slot *SLOT2* on page *P_ID2* or mark the slot as a ghost.</span></span>  
  
  
