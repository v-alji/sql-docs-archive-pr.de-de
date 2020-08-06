---
title: Leistungsindikatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], performance counters
- performance counters [Integration Services]
- data flow [Integration Services], performance
- counters [Integration Services]
- data flow engine [Integration Services]
ms.assetid: 11e17f4e-72ed-44d7-a71d-a68937a78e4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b20ac056894066114883153030943bec1c05963
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617159"
---
# <a name="performance-counters"></a><span data-ttu-id="9e1ef-102">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="9e1ef-102">Performance Counters</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="9e1ef-103">installiert eine Reihe von Leistungsindikatoren, mit denen Sie die Leistung der Datenfluss-Engine überwachen können.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-103">installs a set of performance counters that you can use to monitor the performance of the data flow engine.</span></span> <span data-ttu-id="9e1ef-104">Sie können beispielsweise den Indikator "Gespoolte Puffer" überwachen, um zu bestimmen, ob Datenpuffer vorübergehend auf den Datenträger geschrieben werden, während ein Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-104">For example, you can watch the "Buffers spooled" counter to determine whether data buffers are being written to disk temporarily while a package is running.</span></span> <span data-ttu-id="9e1ef-105">Diese Auslagerung reduziert die Leistung und weist darauf hin, dass der Computer nicht genügend Arbeitsspeicher hat.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-105">This swapping reduces performance and indicates that the computer has insufficient memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e1ef-106">Wenn Sie [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] auf einem Computer installieren, auf dem [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)]ausgeführt wird, und anschließend ein Upgrade des betreffenden Computers auf [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]ausführen, werden beim Upgradeprozess die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Leistungsindikatoren vom Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-106">If you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="9e1ef-107">Zum Wiederherstellen der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Leistungsindikatoren auf dem Computer führen Sie Setup von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im Reparaturmodus aus.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-107">To restore the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
 <span data-ttu-id="9e1ef-108">In der folgenden Tabelle sind diese Leistungsindikatoren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-108">The following table describes the performance counters.</span></span>  
  
|<span data-ttu-id="9e1ef-109">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="9e1ef-109">Performance counter</span></span>|<span data-ttu-id="9e1ef-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9e1ef-110">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="9e1ef-111">Gelesene BLOB-Bytes</span><span class="sxs-lookup"><span data-stu-id="9e1ef-111">BLOB bytes read</span></span>|<span data-ttu-id="9e1ef-112">Die Anzahl der Bytes der BLOB-Daten (Binary Large Object), die die Datenfluss-Engine in allen Datenquellen gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-112">The number of bytes of binary large object (BLOB) data that the data flow engine has read from all sources.</span></span>|  
|<span data-ttu-id="9e1ef-113">Geschriebene BLOB-Bytes</span><span class="sxs-lookup"><span data-stu-id="9e1ef-113">BLOB bytes written</span></span>|<span data-ttu-id="9e1ef-114">Die Anzahl der Bytes der BLOB-Daten (Binary Large Object), die die Datenfluss-Engine in alle Ziele geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-114">The number of bytes of BLOB data that the data flow engine has written to all destinations.</span></span>|  
|<span data-ttu-id="9e1ef-115">Verwendete BLOB-Dateien</span><span class="sxs-lookup"><span data-stu-id="9e1ef-115">BLOB files in use</span></span>|<span data-ttu-id="9e1ef-116">Die Anzahl von BLOB-Dateien, die die Datenfluss-Engine zurzeit zum Spoolen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-116">The number of BLOB files that the data flow engine currently is using for spooling.</span></span>|  
|<span data-ttu-id="9e1ef-117">Pufferspeicher</span><span class="sxs-lookup"><span data-stu-id="9e1ef-117">Buffer memory</span></span>|<span data-ttu-id="9e1ef-118">Die zurzeit verwendete Arbeitsspeichermenge.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-118">The amount of memory that is in use.</span></span> <span data-ttu-id="9e1ef-119">Hier kann sowohl der physische als auch der virtuelle Speicher enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-119">This may include both physical and virtual memory.</span></span> <span data-ttu-id="9e1ef-120">Wenn diese Zahl den physischen Speicher übersteigt, vergrößert sich der Wert für **Gespoolte Puffer** , um anzuzeigen, dass Speicherauslagerungsvorgänge zunehmen.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-120">When this number is larger than the amount of physical memory, the **Buffers Spooled** count rises as an indication that memory swapping is increasing.</span></span> <span data-ttu-id="9e1ef-121">Umfangreiche Speicherauslagerungsvorgänge beeinträchtigen die Leistung der Datenfluss-Engine.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-121">Increased memory swapping slows performance of the data flow engine.</span></span>|  
|<span data-ttu-id="9e1ef-122">Verwendete Puffer</span><span class="sxs-lookup"><span data-stu-id="9e1ef-122">Buffers in use</span></span>|<span data-ttu-id="9e1ef-123">Die Anzahl von Pufferobjekten aller Typen, die alle Datenflusskomponenten und die Datenfluss-Engine zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-123">The number of buffer objects, of all types, that all data flow components and the data flow engine is currently using.</span></span>|  
|<span data-ttu-id="9e1ef-124">Gespoolte Puffer</span><span class="sxs-lookup"><span data-stu-id="9e1ef-124">Buffers spooled</span></span>|<span data-ttu-id="9e1ef-125">Der Anzahl von zurzeit auf den Datenträger geschriebenen Puffern.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-125">The number of buffers currently written to the disk.</span></span> <span data-ttu-id="9e1ef-126">Wenn der Datenfluss-Engine nur wenig physischer Speicher zur Verfügung steht, werden die Puffer, die zurzeit nicht verwendet werden, auf den Datenträger geschrieben und anschließend, falls erforderlich, neu geladen.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-126">If the data flow engine runs low on physical memory, buffers not currently used are written to disk and then reloaded when needed.</span></span>|  
|<span data-ttu-id="9e1ef-127">Flatpufferspeicher</span><span class="sxs-lookup"><span data-stu-id="9e1ef-127">Flat buffer memory</span></span>|<span data-ttu-id="9e1ef-128">Die Gesamtanzahl der Bytes des Speichers, der von allen Flatpuffern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-128">The total amount of memory, in bytes, that all flat buffers use.</span></span> <span data-ttu-id="9e1ef-129">Als Flatpuffer werden Speicherblöcke bezeichnet, die von einer Komponente zum Speichern von Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-129">Flat buffers are blocks of memory that a component uses to store data.</span></span> <span data-ttu-id="9e1ef-130">Ein Flatpuffer ist ein großer Byteblock, auf den byteweise zugegriffen wird (also ein Byte nach dem anderen).</span><span class="sxs-lookup"><span data-stu-id="9e1ef-130">A flat buffer is a large block of bytes that is accessed byte by byte.</span></span>|  
|<span data-ttu-id="9e1ef-131">Verwendete Flatpuffer</span><span class="sxs-lookup"><span data-stu-id="9e1ef-131">Flat buffers in use</span></span>|<span data-ttu-id="9e1ef-132">Die Anzahl der von der Datenfluss-Engine verwendeten Flatpuffer.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-132">The number of flat buffers that the Data flow engine uses.</span></span> <span data-ttu-id="9e1ef-133">Alle Flatpuffer sind private Puffer.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-133">All flat buffers are private buffers.</span></span>|  
|<span data-ttu-id="9e1ef-134">Privater Pufferspeicher</span><span class="sxs-lookup"><span data-stu-id="9e1ef-134">Private buffer memory</span></span>|<span data-ttu-id="9e1ef-135">Der Gesamtspeicher, der von allen privaten Puffern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-135">The total amount of memory in use by all private buffers.</span></span> <span data-ttu-id="9e1ef-136">Ein Puffer ist nicht privat, wenn die Datenfluss-Engine ihn zur Unterstützung des Datenflusses erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-136">A buffer is not private if the data flow engine creates it to support data flow.</span></span> <span data-ttu-id="9e1ef-137">Ein Puffer wird als privat bezeichnet, wenn er von einer Transformation für temporäre Arbeitsvorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-137">A private buffer is a buffer that a transformation uses for temporary work only.</span></span> <span data-ttu-id="9e1ef-138">Private Puffer werden beispielsweise von der Aggregationstransformation verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-138">For example, the Aggregation transformation uses private buffers to do its work.</span></span>|  
|<span data-ttu-id="9e1ef-139">Private verwendete Puffer</span><span class="sxs-lookup"><span data-stu-id="9e1ef-139">Private buffers in use</span></span>|<span data-ttu-id="9e1ef-140">Die Anzahl der von Transformationen verwendeten Puffer.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-140">The number of buffers that transformations use.</span></span>|  
|<span data-ttu-id="9e1ef-141">Gelesene Zeilen</span><span class="sxs-lookup"><span data-stu-id="9e1ef-141">Rows read</span></span>|<span data-ttu-id="9e1ef-142">Die Anzahl der Zeilen, die von einer Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-142">The number of rows that a source produces.</span></span> <span data-ttu-id="9e1ef-143">In dieser Anzahl sind die von der Transformation für Suche aus Verweistabellen gelesenen Zeilen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-143">The number does not include rows read from reference tables by the Lookup transformation.</span></span>|  
|<span data-ttu-id="9e1ef-144">Geschriebene Zeilen</span><span class="sxs-lookup"><span data-stu-id="9e1ef-144">Rows written</span></span>|<span data-ttu-id="9e1ef-145">Die Anzahl der Zeilen, die für ein Ziel verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-145">The number of rows offered to a destination.</span></span> <span data-ttu-id="9e1ef-146">In dieser Anzahl sind die in den Zieldatenspeicher geschriebenen Zeilen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-146">The number does not reflect rows written to the destination data store.</span></span>|  
  
 <span data-ttu-id="9e1ef-147">Verwenden Sie das Leistungs-Snap-In von Microsoft Management Console (MMC), um ein Protokoll zu erstellen, in dem die Leistungsindikatoren aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-147">You use the Performance Microsoft Management Console (MMC) snap-in to create a log that captures performance counters.</span></span>  
  
 <span data-ttu-id="9e1ef-148">Weitere Informationen zur Verbesserung der Leistung finden Sie unter [Funktionen für die Datenflussleistung](../data-flow/data-flow-performance-features.md).</span><span class="sxs-lookup"><span data-stu-id="9e1ef-148">For information about how to improve performance, see [Data Flow Performance Features](../data-flow/data-flow-performance-features.md).</span></span>  
  
## <a name="obtain-performance-counter-statistics"></a><span data-ttu-id="9e1ef-149">Abrufen von Leistungsindikatorstatistiken</span><span class="sxs-lookup"><span data-stu-id="9e1ef-149">Obtain Performance Counter Statistics</span></span>  
 <span data-ttu-id="9e1ef-150">Für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekte, die auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Server bereitgestellt werden, können Sie Leistungsindikatorstatistiken mithilfe der Funktion [dm_execution_performance_counters &#40;SSISDB-Datenbank&#41;](/sql/integration-services/functions-dm-execution-performance-counters) abrufen.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-150">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you can obtain performance counter statistics by using the [dm_execution_performance_counters &#40;SSISDB Database&#41;](/sql/integration-services/functions-dm-execution-performance-counters) function.</span></span>  
  
 <span data-ttu-id="9e1ef-151">Im folgenden Beispiel gibt die Funktion Statistiken für eine aktive Ausführung mit einer ID von 34 zurück.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-151">In the following example, the function returns statistics for a running execution with an ID of 34.</span></span>  
  
```  
select * from [catalog].[dm_execution_performance_counters] (34)  
```  
  
 <span data-ttu-id="9e1ef-152">Im folgenden Beispiel gibt die Funktion Statistiken für alle Ausführungen zurück, die auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-152">In the following example, the function returns statistics for all the executions running on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
```  
select * from [catalog].[dm_execution_performance_counters] (NULL)  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9e1ef-153">Wenn Sie ein Mitglied der `ssis_admin`-Datenbankrolle sind, werden Leistungsstatistiken für alle aktiven Ausführungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-153">If you are a member of the `ssis_admin` database role, performance statistics for all running executions are returned.</span></span>  <span data-ttu-id="9e1ef-154">Wenn Sie kein Mitglied der `ssis_admin`-Datenbankrolle sind, werden Leistungsstatistiken zu den aktiven Ausführungen zurückgegeben, für die Sie Leseberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-154">If you are not a member of the `ssis_admin` database role, performance statistics for the running executions for which you have read permissions, are returned.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="9e1ef-155">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9e1ef-155">Related Content</span></span>  
  
-   <span data-ttu-id="9e1ef-156">Tool, [SSIS Performance Visualization für Business Intelligence Development Studio (CodePlex-Projekt)](https://go.microsoft.com/fwlink/?LinkId=146626)auf codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-156">Tool, [SSIS Performance Visualization for Business Intelligence Development Studio (CodePlex Project)](https://go.microsoft.com/fwlink/?LinkId=146626), on codeplex.com.</span></span>  
  
-   <span data-ttu-id="9e1ef-157">Video [Messen und Verstehen der Leistung der SSIS-Pakete in Enterprise (SQL Server-Video)](https://go.microsoft.com/fwlink/?LinkId=150497)auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-157">Video, [Measuring and Understanding the Performance of Your SSIS Packages in the Enterprise (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=150497), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="9e1ef-158">Supportartikel [Der SSIS-Leistungsindikator ist im Systemmonitor nicht mehr verfügbar, wenn Sie ein Upgrade auf Windows Server 2008 ausführen](https://go.microsoft.com/fwlink/?LinkId=235319)auf support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9e1ef-158">Support article, [The SSIS performance counter is no longer available in the Performance Monitor after you upgrade to Windows Server 2008](https://go.microsoft.com/fwlink/?LinkId=235319), on support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1ef-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e1ef-159">See Also</span></span>  
 [<span data-ttu-id="9e1ef-160">Ausführung von Projekten und Paketen</span><span class="sxs-lookup"><span data-stu-id="9e1ef-160">Execution of Projects and Packages</span></span>](../packages/run-integration-services-ssis-packages.md)  
  
  