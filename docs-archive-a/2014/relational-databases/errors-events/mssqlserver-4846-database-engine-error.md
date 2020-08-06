---
title: MSSQLSERVER_4846 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 923137645aae72476fb4b2ae33f0cbbf3e81c2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698241"
---
# <a name="mssqlserver_4846"></a><span data-ttu-id="29873-102">MSSQLSERVER_4846</span><span class="sxs-lookup"><span data-stu-id="29873-102">MSSQLSERVER_4846</span></span>
    
## <a name="details"></a><span data-ttu-id="29873-103">Details</span><span class="sxs-lookup"><span data-stu-id="29873-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29873-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="29873-104">Product Name</span></span>|<span data-ttu-id="29873-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="29873-105">SQL Server</span></span>|  
|<span data-ttu-id="29873-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="29873-106">Event ID</span></span>|<span data-ttu-id="29873-107">4846</span><span class="sxs-lookup"><span data-stu-id="29873-107">4846</span></span>|  
|<span data-ttu-id="29873-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="29873-108">Event Source</span></span>|<span data-ttu-id="29873-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="29873-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="29873-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="29873-110">Component</span></span>|<span data-ttu-id="29873-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="29873-111">SQLEngine</span></span>|  
|<span data-ttu-id="29873-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="29873-112">Symbolic Name</span></span>|<span data-ttu-id="29873-113">BULKPROV_MEMORY</span><span class="sxs-lookup"><span data-stu-id="29873-113">BULKPROV_MEMORY</span></span>|  
|<span data-ttu-id="29873-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="29873-114">Message Text</span></span>|<span data-ttu-id="29873-115">Der Massendatenanbieter konnte keinen Arbeitsspeicher belegen.</span><span class="sxs-lookup"><span data-stu-id="29873-115">The bulk data provider failed to allocate memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="29873-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="29873-116">Explanation</span></span>  
 <span data-ttu-id="29873-117">Die Speicherbelegung hat einen Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="29873-117">Memory allocation failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29873-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="29873-118">User Action</span></span>  
 <span data-ttu-id="29873-119">Führen Sie diese allgemeinen Schritte aus, um Speicherfehler zu beheben:</span><span class="sxs-lookup"><span data-stu-id="29873-119">Follow these general steps to troubleshoot memory errors:</span></span>  
  
1.  <span data-ttu-id="29873-120">Überprüfen Sie, ob andere Anwendungen oder Dienste Arbeitsspeicher auf dem Server beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="29873-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="29873-121">Rekonfigurieren Sie weniger kritische Anwendungen oder Dienste, damit sie weniger Speicher beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="29873-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="29873-122">Beginnen Sie mit der Erfassung von Leistungsüberwachungsindikatoren für **SQL Server: Puffer-Manager**, **SQL Server: Speicher-Manager**.</span><span class="sxs-lookup"><span data-stu-id="29873-122">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="29873-123">Überprüfen Sie die folgenden SQL Server-Speicherkonfigurationsparameter:</span><span class="sxs-lookup"><span data-stu-id="29873-123">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="29873-124">**Max. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="29873-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="29873-125">**Min. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="29873-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="29873-126">**Min. Arbeitsspeicher pro Abfrage**</span><span class="sxs-lookup"><span data-stu-id="29873-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="29873-127">Achten Sie auf ungewöhnlichen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="29873-127">Notice any unusual settings.</span></span> <span data-ttu-id="29873-128">Berichtigen Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="29873-128">Correct them as necessary.</span></span> <span data-ttu-id="29873-129">Konto für Arbeitsspeicheranforderungen für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29873-129">Account for memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="29873-130">Die Standardeinstellungen werden unter "Festlegen von Serverkonfigurationsoptionen" in der SQL Server-Onlinedokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="29873-130">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="29873-131">Verfolgen Sie die Ausgabe von DBCC MEMORYSTATUS und deren Veränderungen beim Anzeigen der Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="29873-131">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="29873-132">Überprüfen Sie die Arbeitsauslastung (z. B. Anzahl gleichzeitiger Sitzungen, derzeit ausgeführte Abfragen).</span><span class="sxs-lookup"><span data-stu-id="29873-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="29873-133">Durch die folgenden Aktionen kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mehr Arbeitsspeicher zur Verfügung gestellt werden:</span><span class="sxs-lookup"><span data-stu-id="29873-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="29873-134">Wenn Anwendungen außer SQL Server Ressourcen verbrauchen, sollten Sie diese Anwendungen beenden oder auf einem separaten Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="29873-134">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="29873-135">Dadurch fällt der Mangel an externem Arbeitsspeicher weg.</span><span class="sxs-lookup"><span data-stu-id="29873-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="29873-136">Wenn Sie **Max. Serverarbeitsspeicher**  konfiguriert haben, erhöhen Sie dessen Wert.</span><span class="sxs-lookup"><span data-stu-id="29873-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="29873-137">Führen Sie die folgenden DBCC-Befehle aus, um mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speichercaches freizugeben.</span><span class="sxs-lookup"><span data-stu-id="29873-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="29873-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="29873-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="29873-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="29873-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="29873-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="29873-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="29873-141">Wenn das Problem weiterhin besteht, müssen Sie weitere Untersuchungen ausführen und möglicherweise die Arbeitsauslastung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="29873-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
