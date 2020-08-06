---
title: Überwachen der Speicherauslastung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723722"
---
# <a name="monitor-memory-usage"></a><span data-ttu-id="b85ec-102">Überwachen der Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="b85ec-102">Monitor Memory Usage</span></span>
  <span data-ttu-id="b85ec-103">Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sollten regelmäßig überwacht werden, um sicherzustellen, dass sich die Speicherauslastung im normalen Bereich bewegt.</span><span class="sxs-lookup"><span data-stu-id="b85ec-103">Monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to confirm that memory usage is within typical ranges.</span></span>  
  
 <span data-ttu-id="b85ec-104">Um den Arbeitsspeicherstatus niedrig zu halten, verwenden Sie bei der Überwachung folgende Objektleistungsindikatoren:</span><span class="sxs-lookup"><span data-stu-id="b85ec-104">To monitor for a low-memory condition, use the following object counters:</span></span>  
  
-   <span data-ttu-id="b85ec-105">**Arbeitsspeicher: Verfügbare Byte**</span><span class="sxs-lookup"><span data-stu-id="b85ec-105">**Memory: Available Bytes**</span></span>  
  
-   <span data-ttu-id="b85ec-106">**Arbeitsspeicher: Seiten/s**</span><span class="sxs-lookup"><span data-stu-id="b85ec-106">**Memory: Pages/sec**</span></span>  
  
 <span data-ttu-id="b85ec-107">Der **Verfügbare Bytes** -Leistungsindikator gibt an, wie viele Bytes an Arbeitsspeicher derzeit für die Verwendung durch Prozesse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b85ec-107">The **Available Bytes** counter indicates how many bytes of memory are currently available for use by processes.</span></span> <span data-ttu-id="b85ec-108">Der Indikator **Seiten/s** gibt die Anzahl der Seiten an, die entweder aufgrund von harten Seitenfehlern vom Datenträger abgerufen oder auf den Datenträger geschrieben wurden, um Speicherplatz im Arbeitssatz aufgrund von Seitenfehlern freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b85ec-108">The **Pages/sec** counter indicates the number of pages that either were retrieved from disk due to hard page faults or written to disk to free space in the working set due to page faults.</span></span>  
  
 <span data-ttu-id="b85ec-109">Niedrige Werte für den **Verfügbare Bytes** -Leistungsindikator können ein Anzeichen dafür sein, dass insgesamt zu wenig Arbeitsspeicher auf dem Computer vorhanden ist oder dass eine Anwendung keinen Arbeitsspeicher freigibt.</span><span class="sxs-lookup"><span data-stu-id="b85ec-109">Low values for the **Available Bytes** counter can indicate that there is an overall shortage of memory on the computer or that an application is not releasing memory.</span></span> <span data-ttu-id="b85ec-110">Ein hoher Wert für den Indikator **Seiten/s** kann auf überhöhte Auslagerungen hindeuten.</span><span class="sxs-lookup"><span data-stu-id="b85ec-110">A high rate for the **Pages/sec** counter could indicate excessive paging.</span></span> <span data-ttu-id="b85ec-111">Überwachen Sie den **Speicher: Seitenfehler/s**-Zähler, um sicherzustellen, dass die Datenträgeraktivität nicht durch Paging verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="b85ec-111">Monitor the **Memory: Page Faults/sec** counter to make sure that the disk activity is not caused by paging.</span></span>  
  
 <span data-ttu-id="b85ec-112">Ein geringes Maß an Auslagerungen (und somit an Seitenfehlern) ist normal, selbst wenn der Computer über ausreichend Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="b85ec-112">A low rate of paging (and hence page faults) is typical, even if the computer has plenty of available memory.</span></span> <span data-ttu-id="b85ec-113">Der Microsoft-Manager für virtuellen Arbeitsspeicher (VMM, Virtual Memory Manager) entnimmt Seiten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und anderen Prozessen, um die Größen der Workingsets dieser Prozesse anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b85ec-113">The Microsoft Windows Virtual Memory Manager (VMM) takes pages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and other processes as it trims the working-set sizes of those processes.</span></span> <span data-ttu-id="b85ec-114">Infolge der VMM-Aktivität kommt es häufig zu Seitenfehlern.</span><span class="sxs-lookup"><span data-stu-id="b85ec-114">This VMM activity tends to cause page faults.</span></span> <span data-ttu-id="b85ec-115">Um zu ermitteln, ob die überhöhten Auslagerungen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder einem anderen Prozess verursacht werden, sollten Sie den **Prozess: Seitenfehler/s**-Zähler der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozessinstanz überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b85ec-115">To determine whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or another process is the cause of excessive paging, monitor the **Process: Page Faults/sec** counter for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process instance.</span></span>  
  
 <span data-ttu-id="b85ec-116">Weitere Informationen zum Auflösen überhöhter Auslagerungen finden Sie in der Dokumentation des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="b85ec-116">For more information about resolving excessive paging, see the Windows operating system documentation.</span></span>  
  
## <a name="isolating-memory-used-by-sql-server"></a><span data-ttu-id="b85ec-117">Isolieren des von SQL Server verwendeten Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="b85ec-117">Isolating Memory Used by SQL Server</span></span>  
 <span data-ttu-id="b85ec-118">In der Standardkonfiguration werden Arbeitsspeicheranforderungen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] basierend auf den verfügbaren Systemressourcen dynamisch geändert.</span><span class="sxs-lookup"><span data-stu-id="b85ec-118">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes its memory requirements dynamically, on the basis of available system resources.</span></span> <span data-ttu-id="b85ec-119">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mehr Arbeitsspeicher benötigt, wird das Betriebssystem nach der Verfügbarkeit von freiem physischem Arbeitsspeicher abgefragt. Anschließend wird der verfügbare Arbeitsspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="b85ec-119">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs more memory, it queries the operating system to determine whether free physical memory is available and uses the available memory.</span></span> <span data-ttu-id="b85ec-120">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] den derzeit zugeordneten Arbeitsspeicher nicht benötigt, wird der Arbeitsspeicher für das Betriebssystem freigegeben.</span><span class="sxs-lookup"><span data-stu-id="b85ec-120">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not need the memory currently allocated to it, it releases the memory to the operating system.</span></span> <span data-ttu-id="b85ec-121">Sie können die Option zur dynamischen Verwendung des Arbeitsspeichers jedoch auch mithilfe der Serverkonfigurationsoptionen **minservermemory**und **maxservermemory** überschreiben.</span><span class="sxs-lookup"><span data-stu-id="b85ec-121">However, you can override the option to dynamically use memory by using the **minservermemory**, and **maxservermemory** server configuration options.</span></span> <span data-ttu-id="b85ec-122">Weitere Informationen finden Sie unter [Arbeitsspeicheroptionen für den Server](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="b85ec-122">For more information, see [Server Memory Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
 <span data-ttu-id="b85ec-123">Um die Menge des von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendeten Arbeitsspeichers zu überwachen, sollten Sie die folgenden Leistungsindikatoren überprüfen:</span><span class="sxs-lookup"><span data-stu-id="b85ec-123">To monitor the amount of memory that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses, examine the following performance counters:</span></span>  
  
-   <span data-ttu-id="b85ec-124">**Prozess: Arbeitssatz**</span><span class="sxs-lookup"><span data-stu-id="b85ec-124">**Process: Working Set**</span></span>  
  
-   <span data-ttu-id="b85ec-125">**SQL Server: Puffer-Manager: Puffercache-Trefferquote**</span><span class="sxs-lookup"><span data-stu-id="b85ec-125">**SQL Server: Buffer Manager: Buffer Cache Hit Ratio**</span></span>  
  
-   <span data-ttu-id="b85ec-126">**SQL Server: Puffer-Manager: Datenbankseiten**</span><span class="sxs-lookup"><span data-stu-id="b85ec-126">**SQL Server: Buffer Manager: Database Pages**</span></span>  
  
-   <span data-ttu-id="b85ec-127">**SQL Server: Speicher-Manager: Serverspeicher gesamt (KB)**</span><span class="sxs-lookup"><span data-stu-id="b85ec-127">**SQL Server: Memory Manager: Total Server Memory (KB)**</span></span>  
  
 <span data-ttu-id="b85ec-128">Der Indikator **WorkingSet** gibt die Menge an Arbeitsspeicher an, die von einem Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b85ec-128">The **WorkingSet** counter shows the amount of memory that is used by a process.</span></span> <span data-ttu-id="b85ec-129">Wenn dieser Wert konstant unter der Menge an Arbeitsspeicher liegt, die in den Serveroptionen **Min. Serverarbeitsspeicher** und **Max. Serverarbeitsspeicher** festgelegt ist, wurde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] so konfiguriert, dass zu viel Arbeitsspeicher beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="b85ec-129">If this number is consistently below the amount of memory that is set by the **min server memory** and **max server memory** server options, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use too much memory.</span></span>  
  
 <span data-ttu-id="b85ec-130">Der **Puffercache-Trefferquote** -Leistungsindikator ist anwendungsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="b85ec-130">The **Buffer Cache Hit Ratio** counter is specific to an application.</span></span> <span data-ttu-id="b85ec-131">Eine Rate von 90 Prozent oder höher ist jedoch wünschenswert.</span><span class="sxs-lookup"><span data-stu-id="b85ec-131">However, a rate of 90 percent or higher is desirable.</span></span> <span data-ttu-id="b85ec-132">Fügen Sie so lange Arbeitsspeicher hinzu, bis der Wert konstant über 90 Prozent liegt.</span><span class="sxs-lookup"><span data-stu-id="b85ec-132">Add more memory until the value is consistently greater than 90 percent.</span></span> <span data-ttu-id="b85ec-133">Ein Wert von über 90 Prozent gibt an, dass mehr als 90 Prozent aller Datenanforderungen vom Datencache erfüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="b85ec-133">A value greater than 90 percent indicates that more than 90 percent of all requests for data were satisfied from the data cache.</span></span>  
  
 <span data-ttu-id="b85ec-134">Wenn der Indikator **TotalServerMemory (KB)** gegenüber der auf dem Computer verfügbaren Menge an physischem Arbeitsspeicher konstant hoch ist, kann dies bedeuten, dass zusätzlicher Arbeitsspeicher erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b85ec-134">If the **TotalServerMemory (KB)** counter is consistently high compared to the amount of physical memory in the computer, it may indicate that more memory is required.</span></span>  
  
## <a name="determining-current-memory-allocation"></a><span data-ttu-id="b85ec-135">Bestimmen der aktuellen Speicherbelegung</span><span class="sxs-lookup"><span data-stu-id="b85ec-135">Determining Current Memory Allocation</span></span>  
 <span data-ttu-id="b85ec-136">Mit der folgenden Abfrage werden Informationen zur aktuellen Speicherbelegung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b85ec-136">The following query returns information about currently allocated memory.</span></span>  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
