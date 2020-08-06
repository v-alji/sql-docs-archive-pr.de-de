---
title: MSSQLSERVER_7906 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7906 (Database Engine error)
ms.assetid: 9638a764-4ac1-40ae-a614-2726ebcc6ba4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57485a8f330f186a4abd83182c6035168ed38e0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618003"
---
# <a name="mssqlserver_7906"></a><span data-ttu-id="4ebdc-102">MSSQLSERVER_7906</span><span class="sxs-lookup"><span data-stu-id="4ebdc-102">MSSQLSERVER_7906</span></span>
    
## <a name="details"></a><span data-ttu-id="4ebdc-103">Details</span><span class="sxs-lookup"><span data-stu-id="4ebdc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ebdc-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4ebdc-104">Product Name</span></span>|<span data-ttu-id="4ebdc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ebdc-105">SQL Server</span></span>|  
|<span data-ttu-id="4ebdc-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4ebdc-106">Event ID</span></span>|<span data-ttu-id="4ebdc-107">7906</span><span class="sxs-lookup"><span data-stu-id="4ebdc-107">7906</span></span>|  
|<span data-ttu-id="4ebdc-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4ebdc-108">Event Source</span></span>|<span data-ttu-id="4ebdc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4ebdc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4ebdc-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4ebdc-110">Component</span></span>|<span data-ttu-id="4ebdc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4ebdc-111">SQLEngine</span></span>|  
|<span data-ttu-id="4ebdc-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4ebdc-112">Symbolic Name</span></span>|<span data-ttu-id="4ebdc-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span><span class="sxs-lookup"><span data-stu-id="4ebdc-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span></span>|  
|<span data-ttu-id="4ebdc-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4ebdc-114">Message Text</span></span>|<span data-ttu-id="4ebdc-115">Datenbankfehler: Die Datei 'FILE' ist keine gültige Filestream-Datei.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-115">Database error: The file 'FILE' is not a valid Filestream file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4ebdc-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4ebdc-116">Explanation</span></span>  
 <span data-ttu-id="4ebdc-117">Außer einigen speziellen Dateien wie filestream.hdr sollten keine Dateien direkt unter dem Filestream-Datenspeicher vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-117">Except for some special files such as, 'filestream.hdr', no files should be found directly under the Filestream dataspace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ebdc-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4ebdc-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4ebdc-119">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="4ebdc-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4ebdc-120">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4ebdc-121">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4ebdc-122">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4ebdc-123">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4ebdc-124">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4ebdc-125">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4ebdc-126">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4ebdc-127">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4ebdc-128">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="4ebdc-128">Restore from Backup</span></span>  
 <span data-ttu-id="4ebdc-129">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4ebdc-130">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4ebdc-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4ebdc-131">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4ebdc-131">Not applicable.</span></span> <span data-ttu-id="4ebdc-132">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="4ebdc-132">This error cannot be repaired.</span></span> <span data-ttu-id="4ebdc-133">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ebdc-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
