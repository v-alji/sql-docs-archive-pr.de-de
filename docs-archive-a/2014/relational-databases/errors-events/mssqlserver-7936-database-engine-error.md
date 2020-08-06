---
title: MSSQLSERVER_7936 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7936 (Database Engine error)
ms.assetid: d78fc8a9-d173-4801-bb32-ed6a29257f08
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c478e998b6185b0a8e22cd99caf2be4fc2fdee33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620429"
---
# <a name="mssqlserver_7936"></a><span data-ttu-id="fd72d-102">MSSQLSERVER_7936</span><span class="sxs-lookup"><span data-stu-id="fd72d-102">MSSQLSERVER_7936</span></span>
    
## <a name="details"></a><span data-ttu-id="fd72d-103">Details</span><span class="sxs-lookup"><span data-stu-id="fd72d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd72d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="fd72d-104">Product Name</span></span>|<span data-ttu-id="fd72d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd72d-105">SQL Server</span></span>|  
|<span data-ttu-id="fd72d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="fd72d-106">Event ID</span></span>|<span data-ttu-id="fd72d-107">7936</span><span class="sxs-lookup"><span data-stu-id="fd72d-107">7936</span></span>|  
|<span data-ttu-id="fd72d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="fd72d-108">Event Source</span></span>|<span data-ttu-id="fd72d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fd72d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fd72d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="fd72d-110">Component</span></span>|<span data-ttu-id="fd72d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fd72d-111">SQLEngine</span></span>|  
|<span data-ttu-id="fd72d-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="fd72d-112">Symbolic Name</span></span>|<span data-ttu-id="fd72d-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="fd72d-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="fd72d-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="fd72d-114">Message Text</span></span>|<span data-ttu-id="fd72d-115">Tabellenfehler: Das Filestream-Verzeichnis ist für die Spalten-ID „C_ID“ der Objekt-ID „O_ID“, Index-ID „I_ID“ und Partitions-ID „PN_ID“ vorhanden. Hierbei handelt es sich allerdings um keine Filestream-Spalte.</span><span class="sxs-lookup"><span data-stu-id="fd72d-115">Table error: Filestream directory exists for column ID C_ID of object ID O_ID, index ID I_ID, partition ID PN_ID, but that column is not a Filestream column.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fd72d-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="fd72d-116">Explanation</span></span>  
 <span data-ttu-id="fd72d-117">Während DBCC CHECKDB wurde ein FILESTREAM-Verzeichnis für die angegebene Spalte gefunden; bei der Spalte handelt es sich jedoch nicht um eine Spalte vom Typ `FILESTREAM`.</span><span class="sxs-lookup"><span data-stu-id="fd72d-117">During DBCC CHECKDB, a FILESTREAM directory was found for the specified column; however, the column is not a `FILESTREAM` column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd72d-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="fd72d-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="fd72d-119">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="fd72d-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="fd72d-120">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="fd72d-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="fd72d-121">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fd72d-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="fd72d-122">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fd72d-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="fd72d-123">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="fd72d-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="fd72d-124">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fd72d-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="fd72d-125">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="fd72d-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="fd72d-126">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="fd72d-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="fd72d-127">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="fd72d-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="fd72d-128">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="fd72d-128">Restore from Backup</span></span>  
 <span data-ttu-id="fd72d-129">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fd72d-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="fd72d-130">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="fd72d-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="fd72d-131">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="fd72d-131">Not applicable.</span></span> <span data-ttu-id="fd72d-132">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="fd72d-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="fd72d-133">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd72d-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
