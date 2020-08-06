---
title: MSSQLSERVER_7932 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7932 (Database Engine error)
ms.assetid: e2ad218a-3249-4f18-8b32-09f0030765a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 237d9be3e0f22664adb061d3bba526c9878d3bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618705"
---
# <a name="mssqlserver_7932"></a><span data-ttu-id="304f6-102">MSSQLSERVER_7932</span><span class="sxs-lookup"><span data-stu-id="304f6-102">MSSQLSERVER_7932</span></span>
    
## <a name="details"></a><span data-ttu-id="304f6-103">Details</span><span class="sxs-lookup"><span data-stu-id="304f6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="304f6-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="304f6-104">Product Name</span></span>|<span data-ttu-id="304f6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="304f6-105">SQL Server</span></span>|  
|<span data-ttu-id="304f6-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="304f6-106">Event ID</span></span>|<span data-ttu-id="304f6-107">7932</span><span class="sxs-lookup"><span data-stu-id="304f6-107">7932</span></span>|  
|<span data-ttu-id="304f6-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="304f6-108">Event Source</span></span>|<span data-ttu-id="304f6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="304f6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="304f6-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="304f6-110">Component</span></span>|<span data-ttu-id="304f6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="304f6-111">SQLEngine</span></span>|  
|<span data-ttu-id="304f6-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="304f6-112">Symbolic Name</span></span>|<span data-ttu-id="304f6-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="304f6-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="304f6-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="304f6-114">Message Text</span></span>|<span data-ttu-id="304f6-115">Tabellenfehler: Die FileStream-Verzeichnis-ID ID F_ID für die Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID befindet sich in der Dateigruppe FG_ID1, sollte jedoch in der Dateigruppe FG_ID2 enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="304f6-115">Table error: The FileStream directory ID F_ID for object ID O_ID, index ID I_ID, partition ID PN_ID is in filegroup FG_ID1, but should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="304f6-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="304f6-116">Explanation</span></span>  
 <span data-ttu-id="304f6-117">Während DBCC CHECKDB wurde die FILESTREAM-Speicherung für das angegebene Objekt in der falschen Dateigruppe erkannt.</span><span class="sxs-lookup"><span data-stu-id="304f6-117">During DBCC CHECKDB, the FILESTREAM storage for the specified object was detected in the wrong filegroup.</span></span> <span data-ttu-id="304f6-118">Dabei handelt es sich möglicherweise um eine Beschädigung der Metadaten des Objekts.</span><span class="sxs-lookup"><span data-stu-id="304f6-118">This could be a corruption in the metadata of the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="304f6-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="304f6-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="304f6-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="304f6-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="304f6-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="304f6-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="304f6-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="304f6-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="304f6-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="304f6-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="304f6-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="304f6-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="304f6-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="304f6-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="304f6-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="304f6-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="304f6-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="304f6-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="304f6-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="304f6-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="304f6-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="304f6-129">Restore from Backup</span></span>  
 <span data-ttu-id="304f6-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="304f6-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="304f6-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="304f6-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="304f6-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="304f6-132">Not applicable.</span></span> <span data-ttu-id="304f6-133">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="304f6-133">This error cannot be repaired automatically.</span></span> <span data-ttu-id="304f6-134">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="304f6-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
