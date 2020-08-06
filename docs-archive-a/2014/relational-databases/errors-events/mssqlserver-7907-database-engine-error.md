---
title: MSSQLSERVER_7907 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7907 (Database Engine error)
ms.assetid: a1c94e4a-7e91-46e0-9fac-07bbbf6dd018
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e09e95d9a2416ae54c40f5c8e57d9444497c579f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618002"
---
# <a name="mssqlserver_7907"></a><span data-ttu-id="59131-102">MSSQLSERVER_7907</span><span class="sxs-lookup"><span data-stu-id="59131-102">MSSQLSERVER_7907</span></span>
    
## <a name="details"></a><span data-ttu-id="59131-103">Details</span><span class="sxs-lookup"><span data-stu-id="59131-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59131-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="59131-104">Product Name</span></span>|<span data-ttu-id="59131-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="59131-105">SQL Server</span></span>|  
|<span data-ttu-id="59131-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="59131-106">Event ID</span></span>|<span data-ttu-id="59131-107">7907</span><span class="sxs-lookup"><span data-stu-id="59131-107">7907</span></span>|  
|<span data-ttu-id="59131-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="59131-108">Event Source</span></span>|<span data-ttu-id="59131-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="59131-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="59131-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="59131-110">Component</span></span>|<span data-ttu-id="59131-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="59131-111">SQLEngine</span></span>|  
|<span data-ttu-id="59131-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="59131-112">Symbolic Name</span></span>|<span data-ttu-id="59131-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="59131-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="59131-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="59131-114">Message Text</span></span>|<span data-ttu-id="59131-115">Tabellenfehler: Das Verzeichnis 'DIRECTORY' in Partitions-ID PN_ID stellt kein gültiges Filestream-Verzeichnis dar.</span><span class="sxs-lookup"><span data-stu-id="59131-115">Table error: The directory 'DIRECTORY' in partition ID PN_ID is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="59131-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="59131-116">Explanation</span></span>  
 <span data-ttu-id="59131-117">Der Name eines Spaltenverzeichnisses stellt die Spalten-ID der Partition der relationalen Engine dar.</span><span class="sxs-lookup"><span data-stu-id="59131-117">The name of a column directory is the relational engine column ID of the partition.</span></span> <span data-ttu-id="59131-118">Wenn ein Spaltenverzeichnisname nicht in eine Spalten-ID konvertiert werden kann, stellt das Verzeichnis kein gültiges Spaltenverzeichnis dar.</span><span class="sxs-lookup"><span data-stu-id="59131-118">If a column directory name cannot be converted to a column ID, the directory is not a valid column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59131-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="59131-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="59131-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="59131-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="59131-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="59131-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="59131-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="59131-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="59131-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="59131-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="59131-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="59131-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="59131-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="59131-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="59131-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="59131-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="59131-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="59131-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="59131-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="59131-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="59131-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="59131-129">Restore from Backup</span></span>  
 <span data-ttu-id="59131-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="59131-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="59131-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="59131-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="59131-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="59131-132">Not applicable.</span></span> <span data-ttu-id="59131-133">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="59131-133">This error cannot be repaired.</span></span> <span data-ttu-id="59131-134">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59131-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
