---
title: MSSQLSERVER_2522 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608729"
---
# <a name="mssqlserver_2522"></a><span data-ttu-id="a91ef-102">MSSQLSERVER_2522</span><span class="sxs-lookup"><span data-stu-id="a91ef-102">MSSQLSERVER_2522</span></span>
    
## <a name="details"></a><span data-ttu-id="a91ef-103">Details</span><span class="sxs-lookup"><span data-stu-id="a91ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a91ef-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a91ef-104">Product Name</span></span>|<span data-ttu-id="a91ef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a91ef-105">SQL Server</span></span>|  
|<span data-ttu-id="a91ef-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a91ef-106">Event ID</span></span>|<span data-ttu-id="a91ef-107">2522</span><span class="sxs-lookup"><span data-stu-id="a91ef-107">2522</span></span>|  
|<span data-ttu-id="a91ef-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a91ef-108">Event Source</span></span>|<span data-ttu-id="a91ef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a91ef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a91ef-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a91ef-110">Component</span></span>|<span data-ttu-id="a91ef-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a91ef-111">SQLEngine</span></span>|  
|<span data-ttu-id="a91ef-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a91ef-112">Symbolic Name</span></span>|<span data-ttu-id="a91ef-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="a91ef-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span></span>|  
|<span data-ttu-id="a91ef-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a91ef-114">Message Text</span></span>|<span data-ttu-id="a91ef-115">Der I_NAME-Index der O_NAME-Tabelle kann nicht verarbeitet werden, da die Dateigruppe F_NAME ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="a91ef-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is invalid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a91ef-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a91ef-116">Explanation</span></span>  
 <span data-ttu-id="a91ef-117">Diese Informationsmeldung gibt an, dass der Index nicht überprüft werden kann, da eine der Dateigruppen-IDs, die in den Metadaten des Indexes gespeichert ist, nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a91ef-117">This informational message indicates that the index cannot be checked because one of the filegroup IDs that is stored in the metadata of the index does not exist.</span></span> <span data-ttu-id="a91ef-118">Die ungültige Dateigruppen-ID bezieht sich möglicherweise auf die Daten selbst, auf die LOB-Daten (Large Object) oder auf die Zeilenüberlaufdaten.</span><span class="sxs-lookup"><span data-stu-id="a91ef-118">The filegroup ID that is not valid might pertain to the data itself, or to the large object (LOB) data, or to the row-overflow data.</span></span>  
  
 <span data-ttu-id="a91ef-119">Wenn keine Probleme vorhanden sind, werden alle anderen Indizes des gleichen Objekts überprüft.</span><span class="sxs-lookup"><span data-stu-id="a91ef-119">If there are no problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a91ef-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a91ef-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a91ef-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="a91ef-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a91ef-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="a91ef-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a91ef-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a91ef-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a91ef-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a91ef-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a91ef-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="a91ef-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a91ef-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a91ef-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a91ef-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="a91ef-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a91ef-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="a91ef-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a91ef-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="a91ef-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a91ef-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="a91ef-130">Restore from Backup</span></span>  
 <span data-ttu-id="a91ef-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a91ef-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a91ef-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a91ef-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a91ef-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a91ef-133">Not applicable.</span></span> <span data-ttu-id="a91ef-134">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="a91ef-134">This error cannot be repaired automatically.</span></span>  
  
  
