---
title: MSSQLSERVER_847 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 847 (Database Engine error)
ms.assetid: 67208b7c-bd8d-48a1-9f70-a6488e0f5f9b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b2d5c0a35533700606a44867d2a51cf9087e399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619862"
---
# <a name="mssqlserver_847"></a><span data-ttu-id="ea0c4-102">MSSQLSERVER_847</span><span class="sxs-lookup"><span data-stu-id="ea0c4-102">MSSQLSERVER_847</span></span>
    
## <a name="details"></a><span data-ttu-id="ea0c4-103">Details</span><span class="sxs-lookup"><span data-stu-id="ea0c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea0c4-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ea0c4-104">Product Name</span></span>|<span data-ttu-id="ea0c4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea0c4-105">SQL Server</span></span>|  
|<span data-ttu-id="ea0c4-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ea0c4-106">Event ID</span></span>|<span data-ttu-id="ea0c4-107">847</span><span class="sxs-lookup"><span data-stu-id="ea0c4-107">847</span></span>|  
|<span data-ttu-id="ea0c4-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ea0c4-108">Event Source</span></span>|<span data-ttu-id="ea0c4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ea0c4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ea0c4-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="ea0c4-110">Component</span></span>|<span data-ttu-id="ea0c4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ea0c4-111">SQLEngine</span></span>|  
|<span data-ttu-id="ea0c4-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="ea0c4-112">Symbolic Name</span></span>|<span data-ttu-id="ea0c4-113">–</span><span class="sxs-lookup"><span data-stu-id="ea0c4-113">N/A</span></span>|  
|<span data-ttu-id="ea0c4-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ea0c4-114">Message Text</span></span>|<span data-ttu-id="ea0c4-115">Timeout beim Warten auf einen Latch: Klasse „%ls“, ID „%p“, Typ „%d“, Task „0x%p“ : „%d“, Wartezeit „%d“, Flags „0x%I64x“, besitzender Task „0x%p“.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-115">Time-out occurred while waiting for latch: class '%ls', id %p, type %d, Task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span> <span data-ttu-id="ea0c4-116">Der Wartevorgang wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ea0c4-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ea0c4-117">Explanation</span></span>  
 <span data-ttu-id="ea0c4-118">Möglicherweise reagiert ein Computer nicht mehr, oder ein Timeout bzw. eine andere Unterbrechung des regulären Betriebs tritt auf, während [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gleichzeitig Pufferlatchfehler in das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-118">A computer might stop responding, or a time-out or some other disruption of regular operations might occur at the same time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] writes buffer latch errors to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="ea0c4-119">Wenn im STAT-Feld in der Meldung der Wert 0x04 aktiviert ist, wird in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein E/A-Vorgang erwartet.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-119">If the stat field in the message has the value of 0x04 on, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for an I/O operation.</span></span> <span data-ttu-id="ea0c4-120">Zudem wird möglicherweise die Meldung [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Fehlerprotokoll ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-120">You may also receive message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="ea0c4-121">Wenn im STAT-Feld in der Meldung der Wert 0x04 deaktiviert ist, bestehen für eine Seite schwerwiegende Konflikte.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-121">If the stat field in the message has the value 0x04 off, there is heavy contention for a page.</span></span> <span data-ttu-id="ea0c4-122">Wenn es sich bei dem Objekt um eine Datenseite handelt, kann dies auf ineffiziente Codeentwürfe zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-122">If the object is a data page, this can be caused by inefficient code design.</span></span> <span data-ttu-id="ea0c4-123">Wenn die Seite keine Daten darstellt, wird der Fehler möglicherweise durch Serverengpässe wie unzureichende Hardwareressourcen verursacht.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-123">If the page is nondata, the error might be caused by server bottlenecks, such as insufficient hardware resources.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea0c4-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ea0c4-124">User Action</span></span>  
 <span data-ttu-id="ea0c4-125">Wenn Sie dieses Problem umgehen möchten, werden die Fehlermeldungen in Abhängigkeit von Ihrer Umgebung durch einen oder mehrere der folgenden Schritte möglicherweise reduziert oder behoben:</span><span class="sxs-lookup"><span data-stu-id="ea0c4-125">To work around this problem, depending on your environment, one or more of the following steps might reduce or eliminate the error messages:</span></span>  
  
-   <span data-ttu-id="ea0c4-126">Ermitteln Sie, ob Hardware-Engpässe vorliegen.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-126">Determine whether you have any hardware bottlenecks.</span></span> <span data-ttu-id="ea0c4-127">Rüsten Sie gegebenenfalls Ihre Hardware auf, sodass die Konfigurations-, Abfrage- und Ladeanforderungen Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-127">If it is necessary, upgrade your hardware so that it can support the configuration, query, and load requirements of your environment.</span></span> <span data-ttu-id="ea0c4-128">Weitere Informationen zu Engpässen finden Sie unter [Identifizieren von Engpässen](../performance/identify-bottlenecks.md).</span><span class="sxs-lookup"><span data-stu-id="ea0c4-128">For more information about bottlenecks, see [Identify Bottlenecks](../performance/identify-bottlenecks.md).</span></span>  
  
-   <span data-ttu-id="ea0c4-129">Überprüfen Sie alle protokollierten Fehler, und führen Sie alle von Ihrem Hardwarehersteller bereitgestellten Diagnosen aus.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-129">Check for any logged errors and run any diagnostics provided by your hardware vendor.</span></span>  
  
-   <span data-ttu-id="ea0c4-130">Stellen Sie sicher, dass Ihre Laufwerke nicht komprimiert sind.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-130">Make sure that your disk drives are not compressed.</span></span> <span data-ttu-id="ea0c4-131">Das Speichern von Daten bzw. Protokolldateien auf komprimierten Laufwerken wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-131">Storing data or log files on compressed drives is not supported.</span></span> <span data-ttu-id="ea0c4-132">Weitere Informationen zu Dateien und Dateigruppen finden Sie unter [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="ea0c4-132">For more information about physical files, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
-   <span data-ttu-id="ea0c4-133">Prüfen Sie, ob die Fehlermeldungen behoben werden, wenn Sie folgende Optionen deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="ea0c4-133">See whether the error messages disappear when you set the following options to off:</span></span>  
  
    -   <span data-ttu-id="ea0c4-134">SQL Server-Prioritätserhöhung (Konfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="ea0c4-134">SQL Server priority boost configuration option</span></span>  
  
    -   <span data-ttu-id="ea0c4-135">Lightweightpooling (Fibermodus), Option</span><span class="sxs-lookup"><span data-stu-id="ea0c4-135">Lightweight pooling (fiber mode) option</span></span>  
  
    -   <span data-ttu-id="ea0c4-136">Festgelegte Workingsetgröße (Option)</span><span class="sxs-lookup"><span data-stu-id="ea0c4-136">Set working set size option</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea0c4-137">Die vorherigen Einstellungen können häufig kontraproduktiv sein, wenn Sie die Standardeinstellung OFF ändern.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-137">The previous settings can frequently be counter-productive if you change them from their default setting of OFF.</span></span> <span data-ttu-id="ea0c4-138">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea0c4-138">For more information about the settings, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ea0c4-139">Optimieren Sie die Abfragen, um die für das System verwendeten Ressourcen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-139">Tune queries to reduce resources used on the system.</span></span> <span data-ttu-id="ea0c4-140">Durch Leistungsoptimierung kann die Belastung für ein System reduziert und die Reaktionszeit für einzelne Abfragen verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-140">Performance tuning will help reduce the stress on a system and improve response time for individual queries.</span></span>  
  
-   <span data-ttu-id="ea0c4-141">Legen Sie die Option AUTO_SHRINK auf OFF fest, um den Aufwand für Änderungen an der Datenbankgröße zu verringern.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-141">Set the AUTO_SHRINK option to OFF to reduce the overhead of changes to the database size.</span></span>  
  
-   <span data-ttu-id="ea0c4-142">Stellen Sie sicher, dass Sie die Option FILEGROWTH auf Inkremente festlegen, die groß genug sind und somit nicht häufig auftreten.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-142">Make sure that you set the FILEGROWTH option to increments that are large enough to be infrequent.</span></span> <span data-ttu-id="ea0c4-143">Planen Sie einen Auftrag, um den verfügbaren Speicherplatz in den Datenbanken zu überprüfen, und erhöhen Sie dann die Datenbankgröße außerhalb der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="ea0c4-143">Schedule a job to check the available space in the databases, and then increase the database size during nonpeak hours.</span></span>  
  
  
