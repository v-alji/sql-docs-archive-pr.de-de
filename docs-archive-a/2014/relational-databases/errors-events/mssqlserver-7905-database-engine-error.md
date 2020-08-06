---
title: MSSQLSERVER_7905 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7905 (Database Engine error)
ms.assetid: cf19fbbb-7158-45f2-8778-8f3cad7f574a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 253bf03c1bfacccfd809cd417163eb9d54644f28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618005"
---
# <a name="mssqlserver_7905"></a><span data-ttu-id="d5e9d-102">MSSQLSERVER_7905</span><span class="sxs-lookup"><span data-stu-id="d5e9d-102">MSSQLSERVER_7905</span></span>
    
## <a name="details"></a><span data-ttu-id="d5e9d-103">Details</span><span class="sxs-lookup"><span data-stu-id="d5e9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5e9d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d5e9d-104">Product Name</span></span>|<span data-ttu-id="d5e9d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5e9d-105">SQL Server</span></span>|  
|<span data-ttu-id="d5e9d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d5e9d-106">Event ID</span></span>|<span data-ttu-id="d5e9d-107">7905</span><span class="sxs-lookup"><span data-stu-id="d5e9d-107">7905</span></span>|  
|<span data-ttu-id="d5e9d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d5e9d-108">Event Source</span></span>|<span data-ttu-id="d5e9d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d5e9d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d5e9d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d5e9d-110">Component</span></span>|<span data-ttu-id="d5e9d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d5e9d-111">SQLEngine</span></span>|  
|<span data-ttu-id="d5e9d-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d5e9d-112">Symbolic Name</span></span>|<span data-ttu-id="d5e9d-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="d5e9d-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="d5e9d-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d5e9d-114">Message Text</span></span>|<span data-ttu-id="d5e9d-115">Datenbankfehler: Das Verzeichnis 'DIRECTORY' stellt kein gültiges Filestream-Verzeichnis dar.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-115">Database error: The directory 'DIRECTORY' is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5e9d-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d5e9d-116">Explanation</span></span>  
 <span data-ttu-id="d5e9d-117">Der Name eines Rowsetverzeichnisses ist die Partitions-ID der Partition. Dies gilt nicht für spezielle Rowsetverzeichnisnamen, z. B. "ghost".</span><span class="sxs-lookup"><span data-stu-id="d5e9d-117">The name of a rowset directory is the partition ID of the partition, except for the special rowset directory names such as 'ghost'.</span></span> <span data-ttu-id="d5e9d-118">Wenn ein Rowsetverzeichnisname nicht in eine Partitions-ID konvertiert werden kann, handelt es sich bei dem Verzeichnis nicht um ein gültiges Rowsetverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-118">If a rowset directory name cannot be converted to a partition ID, the directory is not a valid rowset directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5e9d-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d5e9d-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="d5e9d-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="d5e9d-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="d5e9d-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="d5e9d-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="d5e9d-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="d5e9d-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="d5e9d-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="d5e9d-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="d5e9d-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="d5e9d-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="d5e9d-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d5e9d-129">Restore from Backup</span></span>  
 <span data-ttu-id="d5e9d-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="d5e9d-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="d5e9d-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="d5e9d-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d5e9d-132">Not applicable.</span></span> <span data-ttu-id="d5e9d-133">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="d5e9d-133">This error cannot be repaired.</span></span> <span data-ttu-id="d5e9d-134">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5e9d-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
