---
title: MSSQLSERVER_701 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 701 (Database Engine error)
ms.assetid: 3b975000-63a1-43c2-a40f-89d0a8a36bef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 542535223d3e394c72079092411add143de61545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616082"
---
# <a name="mssqlserver_701"></a><span data-ttu-id="c436b-102">MSSQLSERVER_701</span><span class="sxs-lookup"><span data-stu-id="c436b-102">MSSQLSERVER_701</span></span>
    
## <a name="details"></a><span data-ttu-id="c436b-103">Details</span><span class="sxs-lookup"><span data-stu-id="c436b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c436b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c436b-104">Product Name</span></span>|<span data-ttu-id="c436b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c436b-105">SQL Server</span></span>|  
|<span data-ttu-id="c436b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c436b-106">Event ID</span></span>|<span data-ttu-id="c436b-107">701</span><span class="sxs-lookup"><span data-stu-id="c436b-107">701</span></span>|  
|<span data-ttu-id="c436b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c436b-108">Event Source</span></span>|<span data-ttu-id="c436b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c436b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c436b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c436b-110">Component</span></span>|<span data-ttu-id="c436b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c436b-111">SQLEngine</span></span>|  
|<span data-ttu-id="c436b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c436b-112">Symbolic Name</span></span>|<span data-ttu-id="c436b-113">NOSYSMEM</span><span class="sxs-lookup"><span data-stu-id="c436b-113">NOSYSMEM</span></span>|  
|<span data-ttu-id="c436b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c436b-114">Message Text</span></span>|<span data-ttu-id="c436b-115">Nicht genügend Systemarbeitsspeicher vorhanden, um diese Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c436b-115">There is insufficient system memory to run this query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c436b-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c436b-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c436b-117">konnte nicht genügend Arbeitsspeicher zuordnen, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c436b-117">has failed to allocate sufficient memory to run the query.</span></span> <span data-ttu-id="c436b-118">Dies kann viele unterschiedliche Gründe haben, z. B. Betriebssystemeinstellungen, Verfügbarkeit des physischen Arbeitsspeichers oder Speicherlimits für die aktuelle Workload.</span><span class="sxs-lookup"><span data-stu-id="c436b-118">This can be caused by a variety of reasons including operating system settings, physical memory availability, or memory limits on the current workload.</span></span> <span data-ttu-id="c436b-119">In den meisten Fällen ist die fehlgeschlagene Transaktion nicht die Ursache dieses Fehlers.</span><span class="sxs-lookup"><span data-stu-id="c436b-119">In most cases, the transaction that failed is not the cause of this error.</span></span>  
  
 <span data-ttu-id="c436b-120">Diagnoseabfragen, wie beispielsweise DBCC-Anweisungen, erzeugen möglicherweise einen Fehler, da dem Server nicht genügend Arbeitsspeicher zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c436b-120">Diagnostic queries, such as DBCC statements, may fail because server the does not have sufficient memory.</span></span>  
  
 <span data-ttu-id="c436b-121">Timeout beim Warten auf die Arbeitsspeicherressourcen für die Abfrageausführung im Ressourcenpool 'default' (257).</span><span class="sxs-lookup"><span data-stu-id="c436b-121">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c436b-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c436b-122">User Action</span></span>  
 <span data-ttu-id="c436b-123">Wenn Sie keine Ressourcenkontrolle verwenden, empfehlen wir, dass Sie den gesamten Serverstatus und die Auslastung oder die Ressourcenpooleinstellungen bzw. Einstellungen für Arbeitsauslastungsgruppen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c436b-123">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="c436b-124">In der folgenden Liste werden allgemeine Schritte erläutert, die bei der Problembehandlung von Arbeitsspeicherfehlern helfen:</span><span class="sxs-lookup"><span data-stu-id="c436b-124">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="c436b-125">Überprüfen Sie, ob andere Anwendungen oder Dienste Arbeitsspeicher auf dem Server beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="c436b-125">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="c436b-126">Rekonfigurieren Sie weniger kritische Anwendungen oder Dienste, damit sie weniger Speicher beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="c436b-126">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="c436b-127">Beginnen Sie die Sammlung der Systemmonitorzähler für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Puffer-Manager**, **SQL Server: Speicher-Manager**.</span><span class="sxs-lookup"><span data-stu-id="c436b-127">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="c436b-128">Überprüfen Sie die folgenden SQL Server-Speicherkonfigurationsparameter:</span><span class="sxs-lookup"><span data-stu-id="c436b-128">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="c436b-129">**Max. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="c436b-129">**max server memory**</span></span>  
  
    -   <span data-ttu-id="c436b-130">**Min. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="c436b-130">**min server memory**</span></span>  
  
    -   <span data-ttu-id="c436b-131">**Min. Arbeitsspeicher pro Abfrage**</span><span class="sxs-lookup"><span data-stu-id="c436b-131">**min memory per query**</span></span>  
  
     <span data-ttu-id="c436b-132">Achten Sie auf ungewöhnliche Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c436b-132">Notice unusual settings.</span></span> <span data-ttu-id="c436b-133">Berichtigen Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="c436b-133">Correct them as necessary.</span></span> <span data-ttu-id="c436b-134">Konto für erhöhte Arbeitsspeicheranforderungen.</span><span class="sxs-lookup"><span data-stu-id="c436b-134">Account for increased memory requirements.</span></span> <span data-ttu-id="c436b-135">Die Standardeinstellungen werden unter "Festlegen von Serverkonfigurationsoptionen" in der SQL Server-Onlinedokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c436b-135">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="c436b-136">Verfolgen Sie die Ausgabe von DBCC MEMORYSTATUS und deren Veränderungen beim Anzeigen der Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="c436b-136">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="c436b-137">Überprüfen Sie die Arbeitsauslastung (z. B. Anzahl gleichzeitiger Sitzungen, derzeit ausgeführte Abfragen).</span><span class="sxs-lookup"><span data-stu-id="c436b-137">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="c436b-138">Durch die folgenden Aktionen kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mehr Arbeitsspeicher zur Verfügung gestellt werden:</span><span class="sxs-lookup"><span data-stu-id="c436b-138">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c436b-139">Wenn andere Anwendungen als [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Ressourcen verbrauchen, versuchen Sie, diese Anwendungen zu beenden, oder führen Sie sie auf einem separaten Server aus.</span><span class="sxs-lookup"><span data-stu-id="c436b-139">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="c436b-140">Dadurch fällt der Mangel an externem Arbeitsspeicher weg.</span><span class="sxs-lookup"><span data-stu-id="c436b-140">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="c436b-141">Wenn Sie **Max. Serverarbeitsspeicher**  konfiguriert haben, erhöhen Sie dessen Wert.</span><span class="sxs-lookup"><span data-stu-id="c436b-141">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="c436b-142">Führen Sie die folgenden DBCC-Befehle aus, um mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speichercaches freizugeben.</span><span class="sxs-lookup"><span data-stu-id="c436b-142">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="c436b-143">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="c436b-143">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="c436b-144">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="c436b-144">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="c436b-145">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="c436b-145">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="c436b-146">Wenn das Problem weiterhin besteht, müssen Sie weitere Untersuchungen ausführen und möglicherweise die Arbeitsauslastung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="c436b-146">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
