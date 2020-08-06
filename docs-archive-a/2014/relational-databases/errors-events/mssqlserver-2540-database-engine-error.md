---
title: MSSQLSERVER_2540 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2540 (Database Engine error)
ms.assetid: eb5ee2be-acbb-4fb7-9b45-dc6200bde06e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4a49abeadcd49263ea7d0701ee468a36882179cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696874"
---
# <a name="mssqlserver_2540"></a><span data-ttu-id="24719-102">MSSQLSERVER_2540</span><span class="sxs-lookup"><span data-stu-id="24719-102">MSSQLSERVER_2540</span></span>
    
## <a name="details"></a><span data-ttu-id="24719-103">Details</span><span class="sxs-lookup"><span data-stu-id="24719-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24719-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="24719-104">Product Name</span></span>|<span data-ttu-id="24719-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="24719-105">SQL Server</span></span>|  
|<span data-ttu-id="24719-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="24719-106">Event ID</span></span>|<span data-ttu-id="24719-107">2540</span><span class="sxs-lookup"><span data-stu-id="24719-107">2540</span></span>|  
|<span data-ttu-id="24719-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="24719-108">Event Source</span></span>|<span data-ttu-id="24719-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="24719-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="24719-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="24719-110">Component</span></span>|<span data-ttu-id="24719-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="24719-111">SQLEngine</span></span>|  
|<span data-ttu-id="24719-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="24719-112">Symbolic Name</span></span>|<span data-ttu-id="24719-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span><span class="sxs-lookup"><span data-stu-id="24719-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span></span>|  
|<span data-ttu-id="24719-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="24719-114">Message Text</span></span>|<span data-ttu-id="24719-115">Dieser Fehler kann nicht automatisch vom System behoben werden.</span><span class="sxs-lookup"><span data-stu-id="24719-115">The system cannot self repair this error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24719-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="24719-116">Explanation</span></span>  
 <span data-ttu-id="24719-117">Diese Fehlermeldung weist auf Probleme hin, die nicht automatisch behoben werden können, z. B. beschädigte Metadaten, beschädigte PFS-Seiten (Page Free Space) oder Beschädigungen in bestimmten kritischen Systembasistabellen.</span><span class="sxs-lookup"><span data-stu-id="24719-117">This error message indicates problems that cannot be repaired automatically, such as corrupt metadata, Page Free Space (PFS) page corruptions, or corruptions in certain critical system base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24719-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="24719-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="24719-119">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="24719-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="24719-120">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="24719-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="24719-121">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="24719-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="24719-122">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="24719-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="24719-123">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="24719-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="24719-124">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="24719-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="24719-125">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="24719-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="24719-126">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="24719-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="24719-127">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="24719-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="24719-128">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="24719-128">Restore from Backup</span></span>  
 <span data-ttu-id="24719-129">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="24719-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="24719-130">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="24719-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="24719-131">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="24719-131">Not applicable.</span></span> <span data-ttu-id="24719-132">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="24719-132">This error cannot be repaired automatically.</span></span>  
  
  
