---
title: MSSQLSERVER_802 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 802 (Database Engine error)
ms.assetid: 5892ed24-4dcb-4bf9-a8a4-a7ca898832d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9edcdda1410d7651f7c7531ef98c64c85741f15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630671"
---
# <a name="mssqlserver_802"></a><span data-ttu-id="5fa2f-102">MSSQLSERVER_802</span><span class="sxs-lookup"><span data-stu-id="5fa2f-102">MSSQLSERVER_802</span></span>
    
## <a name="details"></a><span data-ttu-id="5fa2f-103">Details</span><span class="sxs-lookup"><span data-stu-id="5fa2f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fa2f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5fa2f-104">Product Name</span></span>|<span data-ttu-id="5fa2f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fa2f-105">SQL Server</span></span>|  
|<span data-ttu-id="5fa2f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5fa2f-106">Event ID</span></span>|<span data-ttu-id="5fa2f-107">802</span><span class="sxs-lookup"><span data-stu-id="5fa2f-107">802</span></span>|  
|<span data-ttu-id="5fa2f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5fa2f-108">Event Source</span></span>|<span data-ttu-id="5fa2f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5fa2f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5fa2f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5fa2f-110">Component</span></span>|<span data-ttu-id="5fa2f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5fa2f-111">SQLEngine</span></span>|  
|<span data-ttu-id="5fa2f-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5fa2f-112">Symbolic Name</span></span>|<span data-ttu-id="5fa2f-113">NO_BUFS</span><span class="sxs-lookup"><span data-stu-id="5fa2f-113">NO_BUFS</span></span>|  
|<span data-ttu-id="5fa2f-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5fa2f-114">Message Text</span></span>|<span data-ttu-id="5fa2f-115">Nicht genügend Arbeitsspeicher im Pufferpool.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-115">There is insufficient memory available in the buffer pool.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5fa2f-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5fa2f-116">Explanation</span></span>  
 <span data-ttu-id="5fa2f-117">Diese Meldung wird verursacht, wenn der Pufferpool voll ist und nicht weiter vergrößert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-117">This is caused when the buffer pool is full and the buffer pool can not grow any larger.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5fa2f-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5fa2f-118">User Action</span></span>  
 <span data-ttu-id="5fa2f-119">In der folgenden Liste werden allgemeine Schritte erläutert, die bei der Problembehandlung von Arbeitsspeicherfehlern helfen:</span><span class="sxs-lookup"><span data-stu-id="5fa2f-119">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="5fa2f-120">Überprüfen Sie, ob andere Anwendungen oder Dienste Arbeitsspeicher auf dem Server beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="5fa2f-121">Rekonfigurieren Sie weniger kritische Anwendungen oder Dienste, damit sie weniger Speicher beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="5fa2f-122">Beginnen Sie die Sammlung der Systemmonitorzähler für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Puffer-Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Speicher-Manager**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-122">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="5fa2f-123">Überprüfen Sie die folgenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speicherkonfigurationsparameter:</span><span class="sxs-lookup"><span data-stu-id="5fa2f-123">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="5fa2f-124">**Max. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="5fa2f-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="5fa2f-125">**Min. Serverarbeitsspeicher**</span><span class="sxs-lookup"><span data-stu-id="5fa2f-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="5fa2f-126">**Min. Arbeitsspeicher pro Abfrage**</span><span class="sxs-lookup"><span data-stu-id="5fa2f-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="5fa2f-127">Beachten Sie alle ungewöhnlichen Einstellungen, und korrigieren Sie sie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-127">Notice any unusual settings and correct them as necessary.</span></span> <span data-ttu-id="5fa2f-128">Konto für erhöhte Arbeitsspeicheranforderungen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fa2f-128">Account for increased memory requirements for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5fa2f-129">Die Standardeinstellungen werden unter "Festlegen von Serverkonfigurationsoptionen" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-129">Default settings are listed in "Setting Server Configuration Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="5fa2f-130">Verfolgen Sie die Ausgabe von DBCC MEMORYSTATUS und deren Veränderungen beim Anzeigen der Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-130">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="5fa2f-131">Überprüfen Sie die Arbeitsauslastung (Anzahl der gleichzeitigen Sitzungen, aktuell ausgeführte Abfragen).</span><span class="sxs-lookup"><span data-stu-id="5fa2f-131">Check the workload (number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="5fa2f-132">Durch die folgenden Aktionen kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mehr Arbeitsspeicher zur Verfügung gestellt werden:</span><span class="sxs-lookup"><span data-stu-id="5fa2f-132">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="5fa2f-133">Wenn Anwendungen neben [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sehr ressourcenaufwändig sind, versuchen Sie, diese Anwendungen zu beenden oder auf einem getrennten Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-133">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping these applications or running them on a separate server.</span></span>  
  
-   <span data-ttu-id="5fa2f-134">Wenn Sie **Max. Serverarbeitsspeicher** konfiguriert haben, erhöhen Sie die Einstellung.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-134">If you have configured **max server memory,** increase the setting.</span></span>  
  
 <span data-ttu-id="5fa2f-135">Führen Sie die folgenden DBCC-Befehle aus, um mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speichercaches freizugeben.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-135">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="5fa2f-136">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="5fa2f-136">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="5fa2f-137">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="5fa2f-137">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="5fa2f-138">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="5fa2f-138">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="5fa2f-139">Wenn das Problem weiterhin besteht, müssen Sie weitere Untersuchungen ausführen und möglicherweise die Arbeitsauslastung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-139">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
