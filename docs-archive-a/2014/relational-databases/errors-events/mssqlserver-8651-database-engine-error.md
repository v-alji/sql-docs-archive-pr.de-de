---
title: MSSQLSERVER_8651 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8651 (Database Engine error)
ms.assetid: 4cc3498d-5449-4c4e-b1f9-3271831c725a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a385350a05edee3759ab83d318e365f5b4f3e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698234"
---
# <a name="mssqlserver_8651"></a><span data-ttu-id="c0692-102">MSSQLSERVER_8651</span><span class="sxs-lookup"><span data-stu-id="c0692-102">MSSQLSERVER_8651</span></span>
    
## <a name="details"></a><span data-ttu-id="c0692-103">Details</span><span class="sxs-lookup"><span data-stu-id="c0692-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0692-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c0692-104">Product Name</span></span>|<span data-ttu-id="c0692-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c0692-105">SQL Server</span></span>|  
|<span data-ttu-id="c0692-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c0692-106">Event ID</span></span>|<span data-ttu-id="c0692-107">8651</span><span class="sxs-lookup"><span data-stu-id="c0692-107">8651</span></span>|  
|<span data-ttu-id="c0692-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c0692-108">Event Source</span></span>|<span data-ttu-id="c0692-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c0692-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c0692-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c0692-110">Component</span></span>|<span data-ttu-id="c0692-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c0692-111">SQLEngine</span></span>|  
|<span data-ttu-id="c0692-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c0692-112">Symbolic Name</span></span>|<span data-ttu-id="c0692-113">MEMGRANT_ERR</span><span class="sxs-lookup"><span data-stu-id="c0692-113">MEMGRANT_ERR</span></span>|  
|<span data-ttu-id="c0692-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c0692-114">Message Text</span></span>|<span data-ttu-id="c0692-115">Der angeforderte Vorgang konnte nicht ausgeführt werden, da das benötigte Minimum an Arbeitsspeicher für die Abfrage nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c0692-115">Could not perform the requested operation because the minimum query memory is not available.</span></span> <span data-ttu-id="c0692-116">Verwenden Sie einen niedrigeren Wert für die Serverkonfigurationsoption 'Min. Arbeitsspeicher pro Abfrage'.</span><span class="sxs-lookup"><span data-stu-id="c0692-116">Decrease the configured value for the 'min memory per query' server configuration option.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c0692-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c0692-117">Explanation</span></span>  
 <span data-ttu-id="c0692-118">Andere Prozesse verbrauchen Serverarbeitsspeicher (Arbeitsspeicherknappheit im Server).</span><span class="sxs-lookup"><span data-stu-id="c0692-118">Other processes are consuming server memory (exerting memory pressure in the server).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c0692-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c0692-119">User Action</span></span>  
 <span data-ttu-id="c0692-120">Entweder muss der konfigurierte Wert für die Serverkonfigurationsoption 'Min. Arbeitsspeicher pro Abfrage' verringert werden, oder die Abfrageauslastung auf dem Server muss reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="c0692-120">Either decrease the configured value for the min memory per query' server configuration option or reduce the query load to the server.</span></span>  
  
 <span data-ttu-id="c0692-121">In der folgenden Liste werden allgemeine Schritte erläutert, die bei der Problembehandlung von Arbeitsspeicherfehlern helfen:</span><span class="sxs-lookup"><span data-stu-id="c0692-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="c0692-122">Überprüfen Sie, ob andere Anwendungen oder Dienste Arbeitsspeicher auf dem Server beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="c0692-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="c0692-123">Rekonfigurieren Sie weniger kritische Anwendungen oder Dienste, damit sie weniger Speicher beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="c0692-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="c0692-124">Beginnen Sie mit der Erfassung von Leistungsüberwachungsindikatoren für **SQL Server: Puffer-Manager**, **SQL Server: Speicher-Manager**.</span><span class="sxs-lookup"><span data-stu-id="c0692-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="c0692-125">Überprüfen Sie die folgenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speicherkonfigurationsparameter:</span><span class="sxs-lookup"><span data-stu-id="c0692-125">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="c0692-126">**Max. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="c0692-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="c0692-127">**Min. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="c0692-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="c0692-128">**Min. Arbeitsspeicher pro Abfrage**</span><span class="sxs-lookup"><span data-stu-id="c0692-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="c0692-129">Achten Sie auf ungewöhnliche Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c0692-129">Notice unusual settings.</span></span> <span data-ttu-id="c0692-130">Berichtigen Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="c0692-130">Correct them as necessary.</span></span> <span data-ttu-id="c0692-131">Die Standardeinstellungen werden unter "Festlegen von Serverkonfigurationsoptionen" in der SQL Server-Onlinedokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c0692-131">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="c0692-132">Überprüfen Sie die Arbeitsauslastung (z. B. Anzahl gleichzeitiger Sitzungen, derzeit ausgeführte Abfragen).</span><span class="sxs-lookup"><span data-stu-id="c0692-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="c0692-133">Durch die folgenden Aktionen kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mehr Arbeitsspeicher zur Verfügung gestellt werden:</span><span class="sxs-lookup"><span data-stu-id="c0692-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c0692-134">Wenn andere Anwendungen als [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Ressourcen verbrauchen, versuchen Sie, diese Anwendungen zu beenden, oder führen Sie sie auf einem separaten Server aus.</span><span class="sxs-lookup"><span data-stu-id="c0692-134">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="c0692-135">Dadurch fällt der Mangel an externem Arbeitsspeicher weg.</span><span class="sxs-lookup"><span data-stu-id="c0692-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="c0692-136">Wenn Sie **Max. Serverarbeitsspeicher**  konfiguriert haben, erhöhen Sie dessen Wert.</span><span class="sxs-lookup"><span data-stu-id="c0692-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="c0692-137">Führen Sie die folgenden DBCC-Befehle aus, um mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speichercaches freizugeben.</span><span class="sxs-lookup"><span data-stu-id="c0692-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="c0692-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="c0692-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="c0692-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="c0692-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="c0692-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="c0692-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="c0692-141">Wenn das Problem weiterhin besteht, müssen Sie weitere Untersuchungen ausführen und möglicherweise die Arbeitsauslastung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="c0692-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0692-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0692-142">See Also</span></span>  
 <span data-ttu-id="c0692-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0692-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span></span>  
 <span data-ttu-id="c0692-144">[DBCC freesessioncache &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0692-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span></span>  
 <span data-ttu-id="c0692-145">[DBCC freproccache &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0692-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span></span>  
 <span data-ttu-id="c0692-146">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c0692-146">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="c0692-147">[SQL Server, Puffer-Manager-Objekt](../performance-monitor/sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="c0692-147">[SQL Server, Buffer Manager Object](../performance-monitor/sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="c0692-148">SQL Server, Speicher-Manager-Objekt</span><span class="sxs-lookup"><span data-stu-id="c0692-148">SQL Server, Memory Manager Object</span></span>](../performance-monitor/sql-server-memory-manager-object.md)  
  
  
