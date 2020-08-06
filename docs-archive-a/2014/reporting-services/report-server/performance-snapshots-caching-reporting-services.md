---
title: Leistung, Momentaufnahmen, Zwischenspeichern (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- performance [Reporting Services]
- Reporting Services, performance
ms.assetid: 85afd00f-e8d7-4ef7-9174-2ff84d82f960
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f171586e136b36bd694fa40b15272f62e1cb1378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700803"
---
# <a name="performance-snapshots-caching-reporting-services"></a><span data-ttu-id="0e297-102">Leistung, Momentaufnahmen, Zwischenspeichern (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="0e297-102">Performance, Snapshots, Caching (Reporting Services)</span></span>
  <span data-ttu-id="0e297-103">Die Leistung des Berichtsservers wird von einer Reihe von Faktoren beeinflusst. Dazu zählen Hardware, Anzahl der Benutzer, die gleichzeitig auf Berichte zugreifen, Datenmenge in einem Bericht und Ausgabeformat.</span><span class="sxs-lookup"><span data-stu-id="0e297-103">Report server performance is affected by a combination of factors that include hardware, number of concurrent users accessing reports, the amount of data in a report, and output format.</span></span> <span data-ttu-id="0e297-104">Um die Leistungsfaktoren, die spezifisch für Ihre Installation sind, und entsprechende Abhilfemaßnahmen zu ermitteln, müssen Sie sich zunächst mit den Basisdaten beschäftigen und Tests ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e297-104">To understand the performance factors that are specific to your installation and which remedies will produce the results you want, you will need to get baseline data and run tests.</span></span> <span data-ttu-id="0e297-105">Weitere Informationen zu Tools und Richtlinien stehen in den folgenden Publikationen auf MSDN zur Verfügung: [Leistungsoptimierung bei Reporting Services](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) und [Verwenden von Visual Studio 2005 zum Ausführen von Ladetests für einen SQL Server 2005 Reporting Services-Berichtsserver](https://go.microsoft.com/fwlink/?LinkID=77519).</span><span class="sxs-lookup"><span data-stu-id="0e297-105">For more information about tools and guidelines, see the following publications on MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) and [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519).</span></span>  
  
 <span data-ttu-id="0e297-106">Folgende allgemeine Aspekte sind zu beachten:</span><span class="sxs-lookup"><span data-stu-id="0e297-106">General principles to consider include the following:</span></span>  
  
-   <span data-ttu-id="0e297-107">Die Berichtsverarbeitung und das Berichtsrendering sind speicherintensive Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="0e297-107">Report processing and rendering are memory intensive operations.</span></span> <span data-ttu-id="0e297-108">Wählen Sie wenn möglich einen Computer mit viel Arbeitsspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="0e297-108">When possible, choose a computer that has a lot of memory.</span></span>  
  
-   <span data-ttu-id="0e297-109">Das Hosten von Berichtsserver und Berichtsserver-Datenbank auf verschiedenen Computern liefert in der Regel bessere Ergebnisse als das gemeinsame Hosten auf einem einzelnen leistungsstarken Computer.</span><span class="sxs-lookup"><span data-stu-id="0e297-109">Hosting the report server and the report server database on separate computers tends to provide better performance than hosting both on a single high-end computer.</span></span>  
  
-   <span data-ttu-id="0e297-110">Wenn alle Berichte langsam verarbeitet werden, sollten Sie eine Bereitstellung für dezentrales Skalieren in Erwägung ziehen. Dabei unterstützen mehrere Berichtsserverinstanzen eine einzelne Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0e297-110">If all reports are processing slowly, consider a scale-out deployment where multiple report server instances support a single report server database.</span></span> <span data-ttu-id="0e297-111">Verwenden Sie für beste Ergebnisse eine Lastenausgleichssoftware, die Anforderungen gleichmäßig über die Bereitstellung verteilt.</span><span class="sxs-lookup"><span data-stu-id="0e297-111">For best results, use load balancing software to distribute requests evenly across the deployment.</span></span>  
  
-   <span data-ttu-id="0e297-112">Wird ein einzelner Bericht langsam verarbeitet, optimieren Sie die Datasetabfragen des Berichts, wenn der Bericht bei Bedarf ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0e297-112">If a single report is processing slowly, tune report dataset queries if the report must run on demand.</span></span> <span data-ttu-id="0e297-113">Weitere Möglichkeiten sind das Verwenden freigegebener Datasets, die Sie zwischenspeichern können, das Zwischenspeichern des Berichts oder das Ausführen des Berichts als Momentaufnahme.</span><span class="sxs-lookup"><span data-stu-id="0e297-113">You might also consider using shared datasets that you can cache, caching the report, or running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="0e297-114">Wenn alle Berichte in einem spezifischen Format langsam verarbeitet werden (z. B. Rendern im PDF-Format), sollten Sie eine Dateifreigabeübermittlung, das Hinzufügen von Arbeitsspeicher oder die Auswahl eines anderen Formats erwägen.</span><span class="sxs-lookup"><span data-stu-id="0e297-114">If all reports process slowly in a specific format (for example, while rendering to PDF), consider file share delivery, adding more memory, or choosing a different format.</span></span>  
  
-   <span data-ttu-id="0e297-115">Die Dauer der Berichtsverarbeitung und andere Nutzungsdaten können Sie im Ausführungsprotokoll des Berichtsservers ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0e297-115">To find out how long it takes to process a report and other usage metrics, review the report server execution log.</span></span> <span data-ttu-id="0e297-116">Weitere Informationen finden Sie unter [Berichts Server-Ausführungs Protokoll und die ExecutionLog3-Sicht](report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="0e297-116">For more information, see [Report Server Execution Log and the ExecutionLog3 View](report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
-   <span data-ttu-id="0e297-117">Weitere Informationen zum Minimieren von Leistungsproblemen durch das Optimieren der Speicherverwaltungs-Konfigurationseinstellungen finden Sie unter [Konfigurieren von verfügbarem Speicher für Berichtsserveranwendungen](../report-server/configure-available-memory-for-report-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0e297-117">For more information about how to mitigate performance issues by tuning memory management configuration settings, see [Configure Available Memory for Report Server Applications](../report-server/configure-available-memory-for-report-server-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e297-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0e297-118">In This Section</span></span>  
 [<span data-ttu-id="0e297-119">Monitoring Report Server Performance (Überwachen der Leistung des Berichtsservers)</span><span class="sxs-lookup"><span data-stu-id="0e297-119">Monitoring Report Server Performance</span></span>](monitoring-report-server-performance.md)  
 <span data-ttu-id="0e297-120">Beschreibt die Leistungsobjekte, die Sie verwenden können, um die Verarbeitungslast auf dem Server zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="0e297-120">Describes the performance objects you can use to track the processing load on your server.</span></span>  
  
 [<span data-ttu-id="0e297-121">Set Report Processing Properties (Festlegen von Berichtsverarbeitungseigenschaften)</span><span class="sxs-lookup"><span data-stu-id="0e297-121">Set Report Processing Properties</span></span>](set-report-processing-properties.md)  
 <span data-ttu-id="0e297-122">Beschreibt Möglichkeiten, einen Bericht so zu konfigurieren, dass er bedarfsgesteuert aus dem Cache oder nach Zeitplan als Berichtsmomentaufnahme ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e297-122">Describes ways of configuring a report to run on demand, from cache, or on a schedule as a report snapshot.</span></span>  
  
 [<span data-ttu-id="0e297-123">Configure Available Memory for Report Server Applications (Konfigurieren von verfügbarem Speicher für Berichtsserveranwendungen)</span><span class="sxs-lookup"><span data-stu-id="0e297-123">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
 <span data-ttu-id="0e297-124">Beschreibt, wie Sie das Standardverhalten bei der Arbeitsspeicherverwaltung überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="0e297-124">Describes how you can override default memory management behavior.</span></span>  
  
 [<span data-ttu-id="0e297-125">Zwischenspeichern von Berichten &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e297-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
 <span data-ttu-id="0e297-126">Beschreibt das Verhalten beim Zwischenspeichern auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="0e297-126">Describes report caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="0e297-127">Zwischenspeichern von freigegebenen Datasets &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e297-127">Cache Shared Datasets &#40;SSRS&#41;</span></span>](cache-shared-datasets-ssrs.md)  
 <span data-ttu-id="0e297-128">Beschreibt das Verhalten beim Zwischenspeichern freigegebener Datasets auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="0e297-128">Describes shared dataset caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="0e297-129">Process Large Reports (Verarbeiten von großen Berichten)</span><span class="sxs-lookup"><span data-stu-id="0e297-129">Process Large Reports</span></span>](process-large-reports.md)  
 <span data-ttu-id="0e297-130">Stellt Empfehlungen dazu bereit, wie ein großer Bericht konfiguriert und verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="0e297-130">Provides recommendations on how to configure and distribute a large report.</span></span>  
  
 [<span data-ttu-id="0e297-131">Festlegen von Timeoutwerten für die Verarbeitung von Berichten und freigegebenen Datasets &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e297-131">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
 <span data-ttu-id="0e297-132">Erklärt, wie Timeouts für die Abfrage- und Berichtsverarbeitung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0e297-132">Explains how to set time outs on query and report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e297-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e297-133">See Also</span></span>  
 <span data-ttu-id="0e297-134">[Verwalten eines ausgeführten Prozesses](../subscriptions/manage-a-running-process.md) </span><span class="sxs-lookup"><span data-stu-id="0e297-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span></span>  
 [<span data-ttu-id="0e297-135">Verifying a Report Run (Überprüfen der Berichtsausführung)</span><span class="sxs-lookup"><span data-stu-id="0e297-135">Verifying a Report Run</span></span>](verifying-a-report-run.md)  
  
  
