---
title: MSSQLSERVER_8645 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8645 (Database Engine error)
ms.assetid: 63d6d6d7-3850-4061-8e96-b1fa665e3180
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7be9774452e2008c34ecb52d228a0123992c5368
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619854"
---
# <a name="mssqlserver_8645"></a><span data-ttu-id="2b8dc-102">MSSQLSERVER_8645</span><span class="sxs-lookup"><span data-stu-id="2b8dc-102">MSSQLSERVER_8645</span></span>
    
## <a name="details"></a><span data-ttu-id="2b8dc-103">Details</span><span class="sxs-lookup"><span data-stu-id="2b8dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b8dc-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2b8dc-104">Product Name</span></span>|<span data-ttu-id="2b8dc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b8dc-105">SQL Server</span></span>|  
|<span data-ttu-id="2b8dc-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2b8dc-106">Event ID</span></span>|<span data-ttu-id="2b8dc-107">8645</span><span class="sxs-lookup"><span data-stu-id="2b8dc-107">8645</span></span>|  
|<span data-ttu-id="2b8dc-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2b8dc-108">Event Source</span></span>|<span data-ttu-id="2b8dc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b8dc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b8dc-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2b8dc-110">Component</span></span>|<span data-ttu-id="2b8dc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2b8dc-111">SQLEngine</span></span>|  
|<span data-ttu-id="2b8dc-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2b8dc-112">Symbolic Name</span></span>|<span data-ttu-id="2b8dc-113">MEMTIMEDOUT_ERR</span><span class="sxs-lookup"><span data-stu-id="2b8dc-113">MEMTIMEDOUT_ERR</span></span>|  
|<span data-ttu-id="2b8dc-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2b8dc-114">Message Text</span></span>|<span data-ttu-id="2b8dc-115">Timeout beim Warten auf die Arbeitsspeicherressourcen für die Abfrageausführung.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-115">A time out occurred while waiting for memory resources to execute the query.</span></span> <span data-ttu-id="2b8dc-116">Führen Sie die Abfrage erneut aus.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-116">Rerun the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b8dc-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2b8dc-117">Explanation</span></span>  
 <span data-ttu-id="2b8dc-118">Timeout beim Warten auf die Arbeitsspeicherressourcen für die Abfrageausführung im Ressourcenpool 'default' (257).</span><span class="sxs-lookup"><span data-stu-id="2b8dc-118">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b8dc-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2b8dc-119">User Action</span></span>  
 <span data-ttu-id="2b8dc-120">Wenn Sie keine Ressourcenkontrolle verwenden, empfehlen wir, dass Sie den gesamten Serverstatus und die Auslastung oder die Ressourcenpooleinstellungen bzw. Einstellungen für Arbeitsauslastungsgruppen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-120">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="2b8dc-121">In der folgenden Liste werden allgemeine Schritte erläutert, die bei der Problembehandlung von Arbeitsspeicherfehlern helfen:</span><span class="sxs-lookup"><span data-stu-id="2b8dc-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="2b8dc-122">Überprüfen Sie, ob andere Anwendungen oder Dienste Arbeitsspeicher auf dem Server beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="2b8dc-123">Rekonfigurieren Sie weniger kritische Anwendungen oder Dienste, damit sie weniger Speicher beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="2b8dc-124">Beginnen Sie mit der Erfassung von Leistungsüberwachungsindikatoren für **SQL Server: Puffer-Manager**, **SQL Server: Speicher-Manager**.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="2b8dc-125">Überprüfen Sie die folgenden SQL Server-Speicherkonfigurationsparameter:</span><span class="sxs-lookup"><span data-stu-id="2b8dc-125">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="2b8dc-126">**Max. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="2b8dc-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="2b8dc-127">**Min. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="2b8dc-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="2b8dc-128">**Min. Arbeitsspeicher pro Abfrage**</span><span class="sxs-lookup"><span data-stu-id="2b8dc-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="2b8dc-129">Achten Sie auf ungewöhnliche Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-129">Notice unusual settings.</span></span> <span data-ttu-id="2b8dc-130">Berichtigen Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-130">Correct them as necessary.</span></span> <span data-ttu-id="2b8dc-131">Konto für erhöhte Arbeitsspeicheranforderungen für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b8dc-131">Account for increased memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2b8dc-132">Die Standardeinstellungen werden unter "Festlegen von Serverkonfigurationsoptionen" in der SQL Server-Onlinedokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-132">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="2b8dc-133">Verfolgen Sie die Ausgabe von DBCC MEMORYSTATUS und deren Veränderungen beim Anzeigen der Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-133">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="2b8dc-134">Überprüfen Sie die Arbeitsauslastung (z. B. Anzahl gleichzeitiger Sitzungen, derzeit ausgeführte Abfragen).</span><span class="sxs-lookup"><span data-stu-id="2b8dc-134">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="2b8dc-135">Durch die folgenden Aktionen kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mehr Arbeitsspeicher zur Verfügung gestellt werden:</span><span class="sxs-lookup"><span data-stu-id="2b8dc-135">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="2b8dc-136">Wenn Anwendungen außer SQL Server Ressourcen verbrauchen, sollten Sie diese Anwendungen beenden oder auf einem separaten Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-136">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="2b8dc-137">Dadurch fällt der Mangel an externem Arbeitsspeicher weg.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-137">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="2b8dc-138">Wenn Sie **Max. Serverarbeitsspeicher**  konfiguriert haben, erhöhen Sie dessen Wert.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-138">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="2b8dc-139">Führen Sie die folgenden DBCC-Befehle aus, um mehrere SQL Server-Speichercaches freizugeben.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-139">Run the following DBCC commands to free several SQL Server memory caches.</span></span>  
  
-   <span data-ttu-id="2b8dc-140">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="2b8dc-140">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="2b8dc-141">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="2b8dc-141">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="2b8dc-142">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="2b8dc-142">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="2b8dc-143">Wenn das Problem weiterhin besteht, müssen Sie weitere Untersuchungen ausführen und möglicherweise die Arbeitsauslastung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="2b8dc-143">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
