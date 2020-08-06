---
title: Überwachen der Leistung mit dem Abfragespeicher | Microsoft -Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: e06344a4-22a5-4c67-b6c6-a7060deb5de6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5d74b9c4def9c0314569a8d0bd87939cdcb11b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622039"
---
# <a name="monitoring-performance-by-using-the-query-store"></a><span data-ttu-id="ef959-102">Überwachen der Leistung mit dem Abfragespeicher</span><span class="sxs-lookup"><span data-stu-id="ef959-102">Monitoring Performance By Using the Query Store</span></span>
  <span data-ttu-id="ef959-103">Der Abfragespeicher bietet über DBAs Einblick in die Auswahl und die Leistung des Abfrageplans.</span><span class="sxs-lookup"><span data-stu-id="ef959-103">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="ef959-104">Er vereinfacht das Beheben von Leistungsproblemen, indem er das schnelle Auffinden von Leistungsabweichungen durch Änderungen an Abfrageplänen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ef959-104">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="ef959-105">Das Feature erfasst automatisch einen Verlauf der Abfrage-, Plan- und Laufzeitstatistiken und bewahrt diese zur Überprüfung auf.</span><span class="sxs-lookup"><span data-stu-id="ef959-105">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="ef959-106">Es unterteilt die Daten nach Zeitfenstern und ermöglicht es Ihnen so, Verwendungsmuster für Datenbanken zu erkennen und zu verstehen, wann Abfrageplanänderungen auf dem Server aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="ef959-106">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="ef959-107">Der Abfragespeicher kann mit der Option [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ef959-107">The query store can be configured by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span>

||
|-|
|<span data-ttu-id="ef959-108">**Gilt für**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)-Vorgang).</span><span class="sxs-lookup"><span data-stu-id="ef959-108">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="ef959-109">Dies ist zurzeit eine Vorschaufunktion.</span><span class="sxs-lookup"><span data-stu-id="ef959-109">This is currently a preview feature.</span></span> <span data-ttu-id="ef959-110">Für die Verwendung des Abfragespeichers müssen Sie bestätigen und sich damit einverstanden erklären, dass diese Implementierung des Abfragespeichers den Vorschaubedingungen in Ihrem Lizenzvertrag (z. B. Enterprise Agreement, Microsoft Azure Agreement oder Microsoft Online-Abonnementvertrag) und ggf. den [Zusätzlichen Nutzungsbestimmungen für Microsoft Azure-Vorschauen](https://azure.microsoft.com/support/legal/preview-supplemental-terms/)unterliegt.</span><span class="sxs-lookup"><span data-stu-id="ef959-110">To use the Query Store you must acknowledge and agree that implementation of Query Store is subject to the preview terms in your license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

##  <a name="enabling-the-query-store"></a><a name="Enabling"></a> <span data-ttu-id="ef959-111">Aktivieren des Abfragespeichers</span><span class="sxs-lookup"><span data-stu-id="ef959-111">Enabling the Query Store</span></span>
 <span data-ttu-id="ef959-112">Der Abfragespeicher ist bei neuen Datenbanken standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef959-112">Query Store is not active for new databases by default.</span></span>

#### <a name="by-using-the-query-store-page-in-management-studio"></a><span data-ttu-id="ef959-113">Mithilfe der Seite „Abfragespeicher“ in Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef959-113">By Using the Query Store Page in Management Studio</span></span>

1.  <span data-ttu-id="ef959-114">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Datenbank und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ef959-114">In Object Explorer, right-click a database, and then click **Properties**.</span></span> <span data-ttu-id="ef959-115">(Erfordert die Version [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 von [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="ef959-115">(Requires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 version of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span></span>

2.  <span data-ttu-id="ef959-116">Wählen Sie im Dialogfeld **Datenbankeigenschaften** die Seite **Abfragespeicher** aus.</span><span class="sxs-lookup"><span data-stu-id="ef959-116">In the **Database Properties** dialog box, select the **Query Store** page.</span></span>

3.  <span data-ttu-id="ef959-117">Wählen Sie im Feld **Aktivieren** die Option **Wahr**aus.</span><span class="sxs-lookup"><span data-stu-id="ef959-117">In the **Enable** box, select **True**.</span></span>

#### <a name="by-using-transact-sql-statements"></a><span data-ttu-id="ef959-118">Mithilfe von Transact-SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ef959-118">By Using Transact-SQL Statements</span></span>

1.  <span data-ttu-id="ef959-119">Mit der `ALTER DATABASE`-Anweisung können Sie den Abfragespeicher aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef959-119">Use the `ALTER DATABASE` statement to enable the query store.</span></span> <span data-ttu-id="ef959-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ef959-120">For example:</span></span>

    ```
    ALTER DATABASE AdventureWorks2012 SET QUERY_STORE = ON;
    ```

     <span data-ttu-id="ef959-121">Weitere Syntax Optionen im Zusammenhang mit dem Abfrage Speicher finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="ef959-121">For more syntax options related to the query store, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>

> [!NOTE]
>  <span data-ttu-id="ef959-122">Sie können den Abfragespeicher nicht für die Masterdatenbank aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef959-122">You cannot enable the query store for the master database.</span></span>



##  <a name="information-in-the-query-store"></a><a name="About"></a> <span data-ttu-id="ef959-123">Informationen im Abfragespeicher</span><span class="sxs-lookup"><span data-stu-id="ef959-123">Information in the Query Store</span></span>
 <span data-ttu-id="ef959-124">Die Ausführungspläne für eine bestimmte Abfrage in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verändern sich i. Allg. im Laufe der Zeit aufgrund unterschiedlicher Ursachen wie z.B. statischer Änderungen, Schemaänderungen, des Erstellens/Löschens von Indizes usw. Der Prozedurcache (in dem zwischengespeicherte Abfragepläne gespeichert werden) speichert nur den letzten Ausführungsplan.</span><span class="sxs-lookup"><span data-stu-id="ef959-124">Execution plans for any specific query in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] typically evolve over time due to a number of different reasons such as statistics changes, schema changes, creation/deletion of indexes, etc. The procedure cache (where cached query plans are stored) only stores the latest execution plan.</span></span> <span data-ttu-id="ef959-125">Pläne werden auch bei Speicherplatzknappheit aus dem Plancache entfernt.</span><span class="sxs-lookup"><span data-stu-id="ef959-125">Plans also get evicted from the plan cache due to memory pressure.</span></span> <span data-ttu-id="ef959-126">Aus diesem Grund kann die Problembehandlung bei einer Regression der Abfrageleistung schwierig und zeitaufwendig sein.</span><span class="sxs-lookup"><span data-stu-id="ef959-126">As a result, query performance regressions caused by execution plan changes can be non-trivial and time consuming to resolve.</span></span>

 <span data-ttu-id="ef959-127">Da der Abfragespeicher mehrere Ausführungspläne pro Abfrage beibehält, kann er über Richtlinien den Abfrageprozessor anweisen, für eine Abfrage einen bestimmten Ausführungsplan zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef959-127">Since the query store retains multiple execution plans per query, it can enforce policies to direct the query processor to use a specific execution plan for a query.</span></span> <span data-ttu-id="ef959-128">Dies wird als Planerzwingung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ef959-128">This is referred to as plan forcing.</span></span> <span data-ttu-id="ef959-129">Das Erzwingen eines Plans im Abfragespeicher erfolgt ähnlich wie beim Abfragehinweis [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) , es erfordert jedoch keine Änderung an Benutzeranwendungen.</span><span class="sxs-lookup"><span data-stu-id="ef959-129">Plan forcing in Query Store is provided by using a mechanism similar to the [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) query hint, but it does not require any change in user applications.</span></span> <span data-ttu-id="ef959-130">Durch das Erzwingen eines Plans können Sie eine Regression der Abfrageleistung aufgrund einer Änderung des Plans in sehr kurzer Zeit beheben.</span><span class="sxs-lookup"><span data-stu-id="ef959-130">Plan forcing can resolve a query performance regression caused by a plan change in a very short period of time.</span></span>

 <span data-ttu-id="ef959-131">Häufige Szenarios für die Verwendung des Abfragespeichers:</span><span class="sxs-lookup"><span data-stu-id="ef959-131">Common scenarios for using the Query Store feature are:</span></span>

-   <span data-ttu-id="ef959-132">Schnelles Auffinden und Beheben von Regressionen der Planleistung durch Erzwingung des vorherigen Abfrageplans</span><span class="sxs-lookup"><span data-stu-id="ef959-132">Quickly find and fix a plan performance regression by forcing the previous query plan.</span></span> <span data-ttu-id="ef959-133">Korrigieren von Abfragen, die in der Vergangenheit aufgrund von Änderungen am Ausführungsplan die Leistung vermindert haben</span><span class="sxs-lookup"><span data-stu-id="ef959-133">Fix queries that have recently regressed in performance due to execution plan changes.</span></span>

-   <span data-ttu-id="ef959-134">Bestimmen der Ausführungshäufigkeit einer Abfrage in einem festgelegten Zeitraum mit Unterstützung eines DBAs bei der Behandlung von Leistungsproblemen mit Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ef959-134">Determine the number of times a query was executed in a given time window, assisting a DBA in troubleshooting performance resource problems.</span></span>

-   <span data-ttu-id="ef959-135">Identifizieren der häufigsten *n* Abfragen (nach Ausführungszeit, Speicherverbrauch usw.) in den letzten *x* Stunden.</span><span class="sxs-lookup"><span data-stu-id="ef959-135">Identify top *n* queries (by execution time, memory consumption, etc.) in the past *x* hours.</span></span>

-   <span data-ttu-id="ef959-136">Überwachen des Verlaufs von Abfrageplänen für eine bestimmte Abfrage</span><span class="sxs-lookup"><span data-stu-id="ef959-136">Audit the history of query plans for a given query.</span></span>

-   <span data-ttu-id="ef959-137">Analysieren der Verwendungsmuster einer Ressource (CPU, E/A und Arbeitsspeicher) für eine bestimmte Datenbank</span><span class="sxs-lookup"><span data-stu-id="ef959-137">Analyze the resource (CPU, I/O, and Memory) usage patterns for a particular database.</span></span>

 <span data-ttu-id="ef959-138">Der Abfragespeicher enthält zwei Speicher: einen **Planspeicher** zum Speichern der Informationen zum Ausführungsplan und einen **Speicher für Laufzeitstatistiken** zum Speichern von Ausführungsstatistikinformationen.</span><span class="sxs-lookup"><span data-stu-id="ef959-138">The query store contains two stores; a **plan store** for persisting the execution plan information, and a **runtime stats store** for persisting the execution statistics information.</span></span> <span data-ttu-id="ef959-139">Die Anzahl der eindeutigen Pläne, die für eine Abfrage gespeichert werden können, wird durch die Konfigurationsoption `max_plans_per_query` begrenzt.</span><span class="sxs-lookup"><span data-stu-id="ef959-139">The number of unique plans that can be stored for a query in the plan store is limited by the `max_plans_per_query` configuration option.</span></span> <span data-ttu-id="ef959-140">Zum Verbessern der Leistung werden diese Informationen asynchron in zwei Speicher geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef959-140">To enhance performance, the information is written to the two stores asynchronously.</span></span> <span data-ttu-id="ef959-141">Um die Speicherverwendung zu minimieren, werden die statistischen Daten zur Laufzeitausführung im Speicher für Laufzeitstatistiken über ein festes Zeitintervall aggregiert.</span><span class="sxs-lookup"><span data-stu-id="ef959-141">To minimize space usage, the runtime execution statistics in the runtime stats store are aggregated over a fixed time window.</span></span> <span data-ttu-id="ef959-142">Die Informationen in diesen Speichern können durch Abfragen der Katalogsichten für den Abfragespeicher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef959-142">The information in these stores is visible by querying the query store catalog views.</span></span>

 <span data-ttu-id="ef959-143">Die folgende Abfrage gibt Informationen über Abfragen und Pläne im Abfragespeicher zurück.</span><span class="sxs-lookup"><span data-stu-id="ef959-143">The following query returns information about queries and plans in the query store.</span></span>

```
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*
FROM sys.query_store_plan AS Pl
JOIN sys.query_store_query AS Qry
    ON Pl.query_id = Qry.query_id
JOIN sys.query_store_query_text AS Txt
    ON Qry.query_text_id = Txt.query_text_id ;
```



## <a name="using-the-regressed-queries-feature"></a><span data-ttu-id="ef959-144">Verwenden des Features für rückläufige Abfragen</span><span class="sxs-lookup"><span data-stu-id="ef959-144">Using the Regressed Queries Feature</span></span>
 <span data-ttu-id="ef959-145">Nachdem Sie den Abfrage Speicher aktiviert haben, aktualisieren Sie den Daten Bank Teil des Objekt-Explorer Bereichs, um den Abschnitt **Abfragespeicher** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef959-145">After enabling the query store, refresh the database portion of the Object Explorer pane to add the **Query Store** section.</span></span>

 <span data-ttu-id="ef959-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span><span class="sxs-lookup"><span data-stu-id="ef959-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span></span>

 <span data-ttu-id="ef959-147">Durch Auswahl von **Regressed Queries**wird der Bereich **Regressed Queries** in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ef959-147">Selecting **Regressed Queries**, opens the **Regressed Queries** pane in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="ef959-148">Im Bereich „Regressed Queries“ werden die Abfragen und Pläne im Abfragespeicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef959-148">The Regressed Queries pane shows you the queries, and plans in the query store.</span></span> <span data-ttu-id="ef959-149">Über die Dropdownfelder oben können Sie Abfragen anhand verschiedener Kriterien auswählen.</span><span class="sxs-lookup"><span data-stu-id="ef959-149">Drop down boxes at the top allow you to select queries based on various criteria.</span></span> <span data-ttu-id="ef959-150">Wählen Sie einen Plan aus, um die grafische Darstellung des Abfrageplans anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef959-150">Select a plan to see the graphical query plan.</span></span> <span data-ttu-id="ef959-151">Über verschiedene Schaltflächen können Sie die Quellabfrage anzeigen, einen Abfrageplan erzwingen und die Erzwingung wieder aufheben und die Ansicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ef959-151">Buttons are available to view the source query, force, and unforce a query plan, and refresh the display.</span></span>

 <span data-ttu-id="ef959-152">![Regressedqueries](../../database-engine/media/regressedqueries.PNG "Regressedqueries")</span><span class="sxs-lookup"><span data-stu-id="ef959-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span></span>

 <span data-ttu-id="ef959-153">Um einen Plan zu erzwingen, wählen Sie eine Abfrage und einen Plan aus, und klicken Sie dann auf **Plan erzwingen.**</span><span class="sxs-lookup"><span data-stu-id="ef959-153">To force a plan, select a query and plan, and then click **Force Plan.**</span></span> <span data-ttu-id="ef959-154">Sie können nur Pläne erzwingen, die mit dem Abfrageplanfeature gespeichert wurden und sich noch im Abfrageplancache befinden.</span><span class="sxs-lookup"><span data-stu-id="ef959-154">You can only force plans that were saved by the query plan feature and are still retained in the query plan cache.</span></span>



##  <a name="configuration-options"></a><a name="Options"></a> <span data-ttu-id="ef959-155">Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="ef959-155">Configuration Options</span></span>
 <span data-ttu-id="ef959-156">OPERATION_MODE kann READ_WRITE oder READ_ONLY sein.</span><span class="sxs-lookup"><span data-stu-id="ef959-156">OPERATION_MODE Can be READ_WRITE or READ_ONLY.</span></span>

 <span data-ttu-id="ef959-157">CLEANUP_POLICY konfigurieren Sie das STALE_QUERY_THRESHOLD_DAYS-Argument, um die Anzahl der Tage anzugeben, für die Daten im Abfrage Speicher beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef959-157">CLEANUP_POLICY Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>

 <span data-ttu-id="ef959-158">DATA_FLUSH_INTERVAL_SECONDS Bestimmt die Häufigkeit, mit der in den Abfragespeicher geschriebene Daten auf Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ef959-158">DATA_FLUSH_INTERVAL_SECONDS Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="ef959-159">Um die Leistung zu optimieren, werden durch den Abfragespeicher gesammelte Daten asynchron auf den Datenträger geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef959-159">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="ef959-160">Die Häufigkeit, mit der diese asynchrone Übertragung erfolgt, wird mit DATA_FLUSH_INTERVAL_SECONDS konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ef959-160">The frequency at which this asynchronous transfer occurs is configured via DATA_FLUSH_INTERVAL_SECONDS.</span></span>

 <span data-ttu-id="ef959-161">MAX_SIZE_MB konfiguriert die maximale Größe des Abfrage Speicher.</span><span class="sxs-lookup"><span data-stu-id="ef959-161">MAX_SIZE_MB Configures the maximum size of the query store.</span></span> <span data-ttu-id="ef959-162">Wenn die Daten im Abfragespeicher MAX_SIZE_MB erreichen, ändert sich der Status des Abfragespeichers automatisch vom Lese-/ Schreibzugriff in den schreibgeschützten Modus, und es werden keine neuen Daten mehr erfasst.</span><span class="sxs-lookup"><span data-stu-id="ef959-162">If the data in the query store hits the MAX_SIZE_MB limit, the query store automatically changes the state from read-write to read-only and stops collecting new data.</span></span>

 <span data-ttu-id="ef959-163">INTERVAL_LENGTH_MINUTES Bestimmt das Zeitintervall, mit dem statistische Daten zur Laufzeitausführung im Abfragespeicher aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef959-163">INTERVAL_LENGTH_MINUTES Determines the time interval at which runtime execution statistics data is aggregated into the query store.</span></span> <span data-ttu-id="ef959-164">Um die Speicherverwendung zu optimieren, werden die statistischen Daten zur Laufzeitausführung im Speicher für Laufzeitstatistiken über ein festes Zeitintervall aggregiert.</span><span class="sxs-lookup"><span data-stu-id="ef959-164">To optimize for space usage, the runtime execution statistics in the Runtime Stats Store are aggregated over a fixed time window.</span></span> <span data-ttu-id="ef959-165">Dieses feste Zeitintervall wird mit dem INTERVAL_LENGTH_MINUTES-Argument konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ef959-165">This fixed time window is configured via INTERVAL_LENGTH_MINUTES.</span></span>

 <span data-ttu-id="ef959-166">Sie können die Sicht `sys.database_query_store_options` abfragen, um die aktuellen Optionen des Abfragespeichers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ef959-166">Query the `sys.database_query_store_options` view to determine the current options of the query store.</span></span>

 <span data-ttu-id="ef959-167">Weitere Informationen zum Festlegen der Optionen mit [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen finden Sie unter [Optionsverwaltung](#OptionMgmt).</span><span class="sxs-lookup"><span data-stu-id="ef959-167">For more information about setting options by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Option Management](#OptionMgmt).</span></span>

 

##  <a name="related-views-functions-and-procedures"></a><a name="Related"></a> <span data-ttu-id="ef959-168">Zugehörige Sichten, Funktionen und Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ef959-168">Related Views, Functions, and Procedures</span></span>
 <span data-ttu-id="ef959-169">Der Abfragespeicher kann in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] oder über die folgenden Sichten und Prozeduren angezeigt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ef959-169">The Query Store can be viewed and managed through [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] or by using the following views and procedures.</span></span>

-   [<span data-ttu-id="ef959-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql)

### <a name="query-store-catalog-views"></a><span data-ttu-id="ef959-171">Katalogsichten des Abfragespeichers</span><span class="sxs-lookup"><span data-stu-id="ef959-171">Query Store Catalog Views</span></span>
 <span data-ttu-id="ef959-172">Sieben Katalogsichten stellen Informationen über den Abfragespeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="ef959-172">Seven catalog views present information about the Query Store.</span></span>

-   [<span data-ttu-id="ef959-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql)

-   [<span data-ttu-id="ef959-174">sys.query_context_settings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-174">sys.query_context_settings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-context-settings-transact-sql)

-   [<span data-ttu-id="ef959-175">sys.query_store_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-175">sys.query_store_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-plan-transact-sql)

-   [<span data-ttu-id="ef959-176">sys.query_store_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-176">sys.query_store_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-transact-sql)

-   [<span data-ttu-id="ef959-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql)

-   [<span data-ttu-id="ef959-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql)

-   [<span data-ttu-id="ef959-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql)

### <a name="query-store-stored-procedures"></a><span data-ttu-id="ef959-180">Gespeicherte Prozeduren für den Abfragespeicher</span><span class="sxs-lookup"><span data-stu-id="ef959-180">Query Store Stored Procedures</span></span>
 <span data-ttu-id="ef959-181">Sechs gespeicherte Prozeduren ermöglichen das Konfigurieren des Abfragespeichers.</span><span class="sxs-lookup"><span data-stu-id="ef959-181">Six stored procedures configure the Query Store.</span></span>

-   [<span data-ttu-id="ef959-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql)

-   [<span data-ttu-id="ef959-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql)

-   [<span data-ttu-id="ef959-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql)

-   [<span data-ttu-id="ef959-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql)

-   [<span data-ttu-id="ef959-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql)

-   [<span data-ttu-id="ef959-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef959-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql)



##  <a name="key-usage-scenarios"></a><a name="Scenarios"></a> <span data-ttu-id="ef959-188">Wichtige Verwendungsszenarien</span><span class="sxs-lookup"><span data-stu-id="ef959-188">Key Usage Scenarios</span></span>

###  <a name="option-management"></a><a name="OptionMgmt"></a> <span data-ttu-id="ef959-189">Optionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ef959-189">Option Management</span></span>
 <span data-ttu-id="ef959-190">Dieser Abschnitt enthält einige Richtlinien zum Verwalten des Abfragespeichers selbst.</span><span class="sxs-lookup"><span data-stu-id="ef959-190">This section provides some guidelines on managing Query Store feature itself.</span></span>

 <span data-ttu-id="ef959-191">**Ist der Abfragespeicher derzeit aktiv?**</span><span class="sxs-lookup"><span data-stu-id="ef959-191">**Is Query Store currently active?**</span></span>

 <span data-ttu-id="ef959-192">Der Abfragespeicher speichert seine Daten in der Benutzerdatenbank und besitzt aus diesem Grund eine Größenbegrenzung (konfiguriert mit `MAX_STORAGE_SIZE_MB`).</span><span class="sxs-lookup"><span data-stu-id="ef959-192">Query Store stores its data inside the user database and that is why it has size limit (configured  with `MAX_STORAGE_SIZE_MB`).</span></span> <span data-ttu-id="ef959-193">Wenn die Daten im Abfragespeicher dieses Limit erreichen, ändert sich der Status automatisch vom Lese-/ Schreibzugriff in den schreibgeschützten Modus, und es werden keine neuen Daten mehr erfasst.</span><span class="sxs-lookup"><span data-stu-id="ef959-193">If data in Query Store hits that limit Query Store will automatically change state from read-write to read-only and stop collecting new data.</span></span>

 <span data-ttu-id="ef959-194">Führen Sie das folgende Skript aus, um zu ermitteln, ob der Abfragespeicher zurzeit aktiv ist und Laufzeitstatistiken erfasst.</span><span class="sxs-lookup"><span data-stu-id="ef959-194">Execute the following script to determine if Query Store is currently active, and whether it is currently collects runtime stats or not.</span></span>

```
DECLARE @x nvarchar(100) = CAST(newid() AS nvarchar(100));
DECLARE @query nvarchar(max) = 
N'IF EXISTS
(
    SELECT * 
    FROM sys.query_store_query_text 
    WHERE query_sql_text LIKE ''%' + @x + N'%''
)
SELECT ''Query Store is active'' ;
ELSE SELECT ''Query Store is NOT active''' ;
EXEC sp_executesql @query;
```

 <span data-ttu-id="ef959-195">**Abrufen von Optionen zum Abfragespeicher**</span><span class="sxs-lookup"><span data-stu-id="ef959-195">**Get Query Store options**</span></span>

 <span data-ttu-id="ef959-196">Führen Sie zum Abrufen detaillierter Informationen zum Status des Abfragespeichers Folgendes in einer Benutzerdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="ef959-196">To find out detailed information about Query Store status, execute following in a user database.</span></span>

```
SELECT * FROM sys.database_query_store_options;
```

 <span data-ttu-id="ef959-197">**Festlegen des Abfragespeicherintervalls**</span><span class="sxs-lookup"><span data-stu-id="ef959-197">**Setting Query Store interval**</span></span>

 <span data-ttu-id="ef959-198">Sie können das Intervall zum Sammeln von Statistiken zur Abfragelaufzeit  überschreiben (der Standardwert ist 60 Minuten).</span><span class="sxs-lookup"><span data-stu-id="ef959-198">You can override interval for aggregating query runtime statistics (default is 60 minutes).</span></span>

```

      USE master;
GO

ALTER DATABASE <database_name> 
SET QUERY_STORE (INTERVAL_LENGTH_MINUTES = 15);
```

 <span data-ttu-id="ef959-199">Beachten Sie, dass keine beliebige Werte zulässig sind, stattdessen müssen Sie einen der folgenden Werte verwenden: 1, 5, 10, 15, 30 oder 60.</span><span class="sxs-lookup"><span data-stu-id="ef959-199">Note that arbitrary values are not allowed - you should use one of the following: 1, 5, 10, 15, 30 and 60.</span></span>

 <span data-ttu-id="ef959-200">Der neue Wert für das Intervall wird in der Sicht `sys.database_query_store_options` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef959-200">New value for interval is exposed through `sys.database_query_store_options` view.</span></span>

 <span data-ttu-id="ef959-201">Mit der folgenden Anweisung können Sie den Speicher erweitern, wenn der Abfragespeicher voll ist.</span><span class="sxs-lookup"><span data-stu-id="ef959-201">If the Query Store storage is full use the following statement to extend the storage.</span></span>

```
ALTER DATABASE <database_name> 
SET QUERY_STORE (MAX_STORAGE_SIZE_MB = <new_size>);
```

 <span data-ttu-id="ef959-202">**Festlegen von Optionen zum Abfragespeicher**</span><span class="sxs-lookup"><span data-stu-id="ef959-202">**Set all Query Store options**</span></span>

 <span data-ttu-id="ef959-203">Sie können mehrere Optionen zum Abfragespeicher gleichzeitig mit einer einzigen ALTER DATABASE-Anweisung festlegen.</span><span class="sxs-lookup"><span data-stu-id="ef959-203">You can set multiple Query Store options at once with a single ALTER DATABASE statement.</span></span>

```
ALTER DATABASE <database name> 
SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    CLEANUP_POLICY = 
    (STALE_QUERY_THRESHOLD_DAYS = 30),
    DATA_FLUSH_INTERVAL_SECONDS = 3000,
    MAX_STORAGE_SIZE_MB = 500,
    INTERVAL_LENGTH_MINUTES = 15
);
```

 <span data-ttu-id="ef959-204">**Bereinigen des Speicherplatzes**</span><span class="sxs-lookup"><span data-stu-id="ef959-204">**Cleaning up the space**</span></span>

 <span data-ttu-id="ef959-205">Die internen Tabellen des Abfragespeichers werden beim Erstellen der Datenbank in der PRIMÄREN Dateigruppe erstellt. Diese Konfiguration kann später nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ef959-205">Query Store internal tables are created in the PRIMARY filegroup during database creation and that configuration cannot be changed later.</span></span> <span data-ttu-id="ef959-206">Wenn nicht mehr genügend Speicherplatz vorhanden ist, sollten Sie mithilfe der folgenden Anweisung ältere Daten aus dem Abfragespeicher löschen.</span><span class="sxs-lookup"><span data-stu-id="ef959-206">If you are running out of space you might want to clear older Query Store data by using the following statement.</span></span>

```
ALTER DATABASE <db_name> SET QUERY_STORE CLEAR;
```

 <span data-ttu-id="ef959-207">Sie können auch nur Ad-hoc-Abfragedaten löschen, da diese evtl. für die Abfrageoptimierung und Plananalyse weniger wichtig sind, aber trotzdem viel Platz einnehmen.</span><span class="sxs-lookup"><span data-stu-id="ef959-207">Alternatively, you might want to clear up only ad-hoc query data, since it is less relevant for query optimizations and plan analysis but takes up just as much space.</span></span>

 <span data-ttu-id="ef959-208">**Löschen von Ad-hoc-Abfragen** : Hiermit löschen Sie Abfragen, die nur einmal ausgeführt wurden und mehr als 24 Stunden alt sind.</span><span class="sxs-lookup"><span data-stu-id="ef959-208">**Delete ad-hoc queries** This deletes the queries that were only executed only once and that are more than 24 hours old.</span></span>

```
DECLARE @id int
DECLARE adhoc_queries_cursor CURSOR 
FOR 
SELECT q.query_id
FROM sys.query_store_query_text AS qt
JOIN sys.query_store_query AS q 
    ON q.query_text_id = qt.query_text_id
JOIN sys.query_store_plan AS p 
    ON p.query_id = q.query_id
JOIN sys.query_store_runtime_stats AS rs 
    ON rs.plan_id = p.plan_id
GROUP BY q.query_id
HAVING SUM(rs.count_executions) < 2 
AND MAX(rs.last_execution_time) < DATEADD (hour, -24, GETUTCDATE())
ORDER BY q.query_id ;

OPEN adhoc_queries_cursor ;
FETCH NEXT FROM adhoc_queries_cursor INTO @id;
WHILE @@fetch_status = 0
    BEGIN 
        PRINT @id
        EXEC sp_query_store_remove_query @id
        FETCH NEXT FROM adhoc_queries_cursor INTO @id
    END 
CLOSE adhoc_queries_cursor ;
DEALLOCATE adhoc_queries_cursor;
```

 <span data-ttu-id="ef959-209">Sie können eine eigene Prozedur mit abweichender Logik für das Bereinigen der Daten, die für Sie nicht mehr wichtig sind, definieren.</span><span class="sxs-lookup"><span data-stu-id="ef959-209">You can define your own procedure with different logic for clearing up the data that is no longer important for you.</span></span>

 <span data-ttu-id="ef959-210">Im Beispiel oben wird die erweiterte gespeicherte Prozedur `sp_query_store_remove_query` verwendet, um nicht benötigte Daten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ef959-210">The example above uses the `sp_query_store_remove_query` extended stored procedure for removing unnecessary data.</span></span> <span data-ttu-id="ef959-211">Sie können auch zwei andere Prozeduren verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef959-211">You can also use two other procedures.</span></span>

-   <span data-ttu-id="ef959-212">`sp_query_store_reset_exec_stats`-Löschen Sie die Lauf Zeit Statistiken für einen angegebenen Plan.</span><span class="sxs-lookup"><span data-stu-id="ef959-212">`sp_query_store_reset_exec_stats` - clear runtime statistics for a given plan.</span></span>

-   <span data-ttu-id="ef959-213">`sp_query_store_remove_plan`-entfernt einen einzelnen Plan.</span><span class="sxs-lookup"><span data-stu-id="ef959-213">`sp_query_store_remove_plan` - removes a single plan.</span></span>



###  <a name="performance-auditing-and-troubleshooting"></a><a name="Peformance"></a> <span data-ttu-id="ef959-214">Leistungsüberwachung und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="ef959-214">Performance Auditing and Troubleshooting</span></span>
 <span data-ttu-id="ef959-215">Da der Abfragespeicher den Verlauf von Kompilierungs- und Laufzeitmetriken der Abfrageausführungen speichert, können Sie eine Vielzahl von verschiedenen Fragen im Hinblick auf Ihre Workload sehr einfach beantworten.</span><span class="sxs-lookup"><span data-stu-id="ef959-215">Because Query Store keeps history of compilation and runtime metrics throughout query executions there are many different questions you can easily answer with regards to your workload.</span></span>

 <span data-ttu-id="ef959-216">**Die letzten *n* Abfragen, die für die Datenbank ausgeführt wurden.**</span><span class="sxs-lookup"><span data-stu-id="ef959-216">**Last *n* queries executed on the database.**</span></span>

```
SELECT TOP 10 qt.query_sql_text, q.query_id, 
    qt.query_text_id, p.plan_id, rs.last_execution_time
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
ORDER BY rs.last_execution_time DESC;
```

 <span data-ttu-id="ef959-217">**Anzahl der Ausführungen für jede Abfrage.**</span><span class="sxs-lookup"><span data-stu-id="ef959-217">**Number of executions for each query.**</span></span>

```
SELECT q.query_id, qt.query_text_id, qt.query_sql_text, 
    SUM(rs.count_executions) AS total_execution_count
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
GROUP BY q.query_id, qt.query_text_id, qt.query_sql_text
ORDER BY total_execution_count DESC;
```

 <span data-ttu-id="ef959-218">**Die Anzahl der Abfragen mit der längsten durchschnittlichen Ausführungszeit innerhalb der letzten Stunde.**</span><span class="sxs-lookup"><span data-stu-id="ef959-218">**The number of queries with the longest average execution time within last hour.**</span></span>

```
SELECT TOP 10 rs.avg_duration, qt.query_sql_text, q.query_id,
    qt.query_text_id, p.plan_id, GETUTCDATE() AS CurrentUTCTime, 
    rs.last_execution_time 
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
WHERE rs.last_execution_time > DATEADD(hour, -1, GETUTCDATE())
ORDER BY rs.avg_duration DESC;
```

 <span data-ttu-id="ef959-219">**Die Anzahl der Abfragen mit den größten durchschnittlichen physischen e/a-Lesevorgängen in den letzten 24 Stunden mit entsprechender durchschnittlicher Zeilen Anzahl und Ausführungs Anzahl.**</span><span class="sxs-lookup"><span data-stu-id="ef959-219">**The number of queries that had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count.**</span></span>

```
SELECT TOP 10 rs.avg_physical_io_reads, qt.query_sql_text, 
    q.query_id, qt.query_text_id, p.plan_id, rs.runtime_stats_id, 
    rsi.start_time, rsi.end_time, rs.avg_rowcount, rs.count_executions
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi 
    ON rsi.runtime_stats_interval_id = rs.runtime_stats_interval_id
WHERE rsi.start_time >= DATEADD(hour, -24, GETUTCDATE()) 
ORDER BY rs.avg_physical_io_reads DESC;
```

 <span data-ttu-id="ef959-220">**Abfragen mit mehreren Plänen.**</span><span class="sxs-lookup"><span data-stu-id="ef959-220">**Queries with multiple plans.**</span></span> <span data-ttu-id="ef959-221">Diese Abfragen sind besonders interessant, da sie bei Änderungen der Planauswahl zu einer Regression führen können.</span><span class="sxs-lookup"><span data-stu-id="ef959-221">These queries are especially interesting because they are candidates for regressions due to plan choice change.</span></span> <span data-ttu-id="ef959-222">Die folgende Abfrage erkennt diese Abfragen sowie alle Pläne:</span><span class="sxs-lookup"><span data-stu-id="ef959-222">The following query identifies these queries along with all plans:</span></span>

```
WITH Query_MultPlans
AS
(
    SELECT COUNT(*) AS cnt, q.query_id 
    FROM sys.query_store_query_text AS qt
    JOIN sys.query_store_query AS q
        ON qt.query_text_id = q.query_text_id
    JOIN sys.query_store_plan AS p
        ON p.query_id = q.query_id
    GROUP BY q.query_id
    HAVING COUNT(distinct plan_id) > 1
)

SELECT q.query_id, object_name(object_id) AS ContainingObject, query_sql_text,
plan_id, p.query_plan AS plan_xml,
p.last_compile_start_time, p.last_execution_time
FROM Query_MultPlans AS qm
JOIN sys.query_store_query AS q
    ON qm.query_id = q.query_id
JOIN sys.query_store_plan AS p
    ON q.query_id = p.query_id
JOIN sys.query_store_query_text qt 
    ON qt.query_text_id = q.query_text_id
ORDER BY query_id, plan_id;
```

 <span data-ttu-id="ef959-223">**Abfragen, die vor kurzem in die Leistung zurückgegangen sind (Vergleichen von einem anderen Zeitpunkt).**</span><span class="sxs-lookup"><span data-stu-id="ef959-223">**Queries that recently regressed in performance (comparing different point in time).**</span></span> <span data-ttu-id="ef959-224">Das folgende Abfragebeispiel gibt alle Abfragen zurück, für die sich die Ausführungszeit in den letzten 48 Stunden aufgrund einer Änderung der Planauswahl verdoppelt hat.</span><span class="sxs-lookup"><span data-stu-id="ef959-224">The following query example returns all queries for which execution time doubled in last 48 hours due to a plan choice change.</span></span> <span data-ttu-id="ef959-225">Die Abfrage vergleicht alle Intervalle der Laufzeitstatistiken miteinander.</span><span class="sxs-lookup"><span data-stu-id="ef959-225">Query compares all runtime stat intervals side by side.</span></span>

```
SELECT 
    qt.query_sql_text, 
    q.query_id, 
    qt.query_text_id, 
    rs1.runtime_stats_id AS runtime_stats_id_1,
    rsi1.start_time AS interval_1, 
    p1.plan_id AS plan_1, 
    rs1.avg_duration AS avg_duration_1, 
    rs2.avg_duration AS avg_duration_2,
    p2.plan_id AS plan_2, 
    rsi2.start_time AS interval_2, 
    rs2.runtime_stats_id AS runtime_stats_id_2
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p1 
    ON q.query_id = p1.query_id 
JOIN sys.query_store_runtime_stats AS rs1 
    ON p1.plan_id = rs1.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi1 
    ON rsi1.runtime_stats_interval_id = rs1.runtime_stats_interval_id 
JOIN sys.query_store_plan AS p2 
    ON q.query_id = p2.query_id 
JOIN sys.query_store_runtime_stats AS rs2 
    ON p2.plan_id = rs2.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi2 
    ON rsi2.runtime_stats_interval_id = rs2.runtime_stats_interval_id
WHERE rsi1.start_time > DATEADD(hour, -48, GETUTCDATE()) 
    AND rsi2.start_time > rsi1.start_time 
    AND p1.plan_id <> p2.plan_id
    AND rs2.avg_duration > 2*rs1.avg_duration
ORDER BY q.query_id, rsi1.start_time, rsi2.start_time;
```

 <span data-ttu-id="ef959-226">Wenn Sie alle Leistungsregressionen (nicht nur die im Zusammenhang mit einer Änderung der Planauswahl) anzeigen möchten, entfernen Sie einfach die Bedingung `AND p1.plan_id <> p2.plan_id` aus der vorherigen Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ef959-226">If you want to see performance all regressions (not only those related to plan choice change) than just remove condition `AND p1.plan_id <> p2.plan_id` from the previous query.</span></span>

 <span data-ttu-id="ef959-227">**Abfragen, die vor kurzem in die Leistung zurückgegangen sind (Vergleich der aktuellen und Verlaufs Ausführung).**</span><span class="sxs-lookup"><span data-stu-id="ef959-227">**Queries that recently regressed in performance (comparing recent vs. history execution).**</span></span> <span data-ttu-id="ef959-228">Die nächste Abfrage vergleicht die Abfrageausführung basierend auf den Zeiträumen der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ef959-228">The next query compares query execution based periods of execution.</span></span> <span data-ttu-id="ef959-229">In diesem speziellen Beispiel vergleicht die Abfrage die Ausführung in jüngster Zeit (1 Stunde) mit einem älteren Zeitraum (letzter Tag) und identifiziert Ausführungen, die zu additional_duration_workload geführt haben.</span><span class="sxs-lookup"><span data-stu-id="ef959-229">In this particular example the query compares execution in recent period (1 hour) vs. history period (last day) and identifies those that introduced additional_duration_workload.</span></span> <span data-ttu-id="ef959-230">Diese Metrik wird als Differenz zwischen aktueller durchschnittlicher Ausführung und älterer durchschnittlicher Ausführung multipliziert mit der Anzahl der letzten Ausführungen berechnet.</span><span class="sxs-lookup"><span data-stu-id="ef959-230">This metrics is calculated as a difference between recent average execution and history average execution multiplied by the number of recent executions.</span></span> <span data-ttu-id="ef959-231">Sie stellt damit tatsächlich dar, wie viel zusätzliche Zeit die letzten Ausführungen im Vergleich zu älteren benötigt haben:</span><span class="sxs-lookup"><span data-stu-id="ef959-231">It actually represents how much of additional duration recent executions introduced compared to history:</span></span>

```
--- "Recent" workload - last 1 hour
DECLARE @recent_start_time datetimeoffset;
DECLARE @recent_end_time datetimeoffset;
SET @recent_start_time = DATEADD(hour, -1, SYSUTCDATETIME());
SET @recent_end_time = SYSUTCDATETIME();

--- "History" workload
DECLARE @history_start_time datetimeoffset;
DECLARE @history_end_time datetimeoffset;
SET @history_start_time = DATEADD(hour, -24, SYSUTCDATETIME());
SET @history_end_time = SYSUTCDATETIME();

WITH
hist AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
     FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @history_start_time AND rs.last_execution_time < @history_end_time)
        OR (rs.first_execution_time <= @history_start_time AND rs.last_execution_time > @history_start_time)
        OR (rs.first_execution_time <= @history_end_time AND rs.last_execution_time > @history_end_time)
    GROUP BY p.query_id
),
recent AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
    FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @recent_start_time AND rs.last_execution_time < @recent_end_time)
        OR (rs.first_execution_time <= @recent_start_time AND rs.last_execution_time > @recent_start_time)
        OR (rs.first_execution_time <= @recent_end_time AND rs.last_execution_time > @recent_end_time)
    GROUP BY p.query_id
)
SELECT 
    results.query_id query_id,
    results.query_text query_text,
    results.additional_duration_workload additional_duration_workload,
    results.total_duration_recent total_duration_recent,
    results.total_duration_hist total_duration_hist,
    ISNULL(results.count_executions_recent, 0) count_executions_recent,
    ISNULL(results.count_executions_hist, 0) count_executions_hist 
FROM
(
    SELECT
        hist.query_id query_id,
        qt.query_sql_text query_text,
        ROUND(CONVERT(float, recent.total_duration/recent.count_executions-hist.total_duration/hist.count_executions)*(recent.count_executions), 2) AS additional_duration_workload,
        ROUND(recent.total_duration, 2) total_duration_recent, 
        ROUND(hist.total_duration, 2) total_duration_hist,
        recent.count_executions count_executions_recent,
        hist.count_executions count_executions_hist   
    FROM hist 
        JOIN recent 
            ON hist.query_id = recent.query_id 
        JOIN sys.query_store_query AS q 
            ON q.query_id = hist.query_id
        JOIN sys.query_store_query_text AS qt 
            ON q.query_text_id = qt.query_text_id    
) AS results
WHERE additional_duration_workload > 0
ORDER BY additional_duration_workload DESC
OPTION (MERGE JOIN);
```



###  <a name="maintaining-query-performance-stability"></a><a name="Stability"></a><span data-ttu-id="ef959-232">Aufrechterhalten der Stabilität der Abfrageleistung</span><span class="sxs-lookup"><span data-stu-id="ef959-232">Maintaining Query Performance Stability</span></span>
 <span data-ttu-id="ef959-233">Für mehrfach ausgeführte Abfragen werden Sie möglicherweise feststellen, dass [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verschiedene Pläne verwendet hat, die eine unterschiedliche Ressourcenverwendung und Dauer nach sich ziehen.</span><span class="sxs-lookup"><span data-stu-id="ef959-233">For queries that are executed multiple times you may notice that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] used different plans which resulted in different resource utilization and duration.</span></span> <span data-ttu-id="ef959-234">Mit dem Abfragespeicher können Sie sehr einfach erkennen, wenn die Abfrageleistung abfällt, und den optimalen Plan innerhalb des gewünschten Zeitraums bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ef959-234">With Query Store you can easily detect when the query performance regressed and determine the optimal plan within a period of interest.</span></span> <span data-ttu-id="ef959-235">Anschließend können Sie diesen optimalen Plan für zukünftige Abfrageausführungen erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ef959-235">Then you can force that optimal plan for future query execution.</span></span>

 <span data-ttu-id="ef959-236">Sie können auch abweichende Abfrageleistungen für eine Abfrage mit Parametern ermitteln (entweder automatisch oder manuell parametrisiert).</span><span class="sxs-lookup"><span data-stu-id="ef959-236">You can also identify inconsistent query performance for a query with parameters (either auto- parameterized or manually parameterized).</span></span> <span data-ttu-id="ef959-237">Sie können unter den verschiedenen Plänen den Plan identifizieren, der schnell und ausreichend geeignet für alle oder die meisten Parameterwerte ist, und diesen dann erzwingen. So erhalten Sie eine vorhersagbare Leistung für eine größere Anzahl von Benutzerszenarios.</span><span class="sxs-lookup"><span data-stu-id="ef959-237">Among different plans you can identify plan which is fast and optimal enough for all or most of the parameter values and force that plan; keeping predictable performance for the wider set of user scenarios.</span></span>

 <span data-ttu-id="ef959-238">**Erzwingen eines Plans für eine Abfrage (Anwenden einer Durchsetzungsrichtlinie).**</span><span class="sxs-lookup"><span data-stu-id="ef959-238">**Force or a plan for a query (apply forcing policy).**</span></span> <span data-ttu-id="ef959-239">Wenn ein Plan für eine bestimmte Abfrage erzwungen wird, erfolgen sämtliche Ausführungen dieser Abfrage mit dem erzwungenen Plan.</span><span class="sxs-lookup"><span data-stu-id="ef959-239">When a plan is forced for a certain query, every time a query comes to execution it will be executed with the plan that is forced.</span></span>

```
EXEC sp_query_store_force_plan @query_id = 48, @plan_id = 49;
```

 <span data-ttu-id="ef959-240">Durch die Verwendung von `sp_query_store_force_plan` können Sie ausschließlich solche Pläne erzwingen, die vom Abfragespeicher als Plan für diese Abfrage aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="ef959-240">When using `sp_query_store_force_plan` you can only force plans that were recorded by Query Store as a plan for that query.</span></span> <span data-ttu-id="ef959-241">Es stehen für eine Abfrage also nur Pläne zur Verfügung, die bereits zum Ausführen der Abfrage verwendet wurden, während der Abfragespeicher aktiv war.</span><span class="sxs-lookup"><span data-stu-id="ef959-241">In other words, the only plans available for a query are those that were already used to execute Q1 while Query Store was active.</span></span>

 <span data-ttu-id="ef959-242">**Entfernen Sie die Plan Erzwingung für eine Abfrage.**</span><span class="sxs-lookup"><span data-stu-id="ef959-242">**Remove plan forcing for a query.**</span></span> <span data-ttu-id="ef959-243">Wenn Sie den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Abfrageoptimierer wieder verwenden möchten, um den optimalen Abfrageplan zu berechnen, verwenden `sp_query_store_unforce_plan` Sie, um den für die Abfrage ausgewählten Plan zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ef959-243">To rely again on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] query optimizer to calculate the optimal query plan, use `sp_query_store_unforce_plan` to unforce the plan that was selected for the query.</span></span>

```
EXEC sp_query_store_unforce_plan @query_id = 48, @plan_id = 49;
```



## <a name="see-also"></a><span data-ttu-id="ef959-244">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef959-244">See Also</span></span>
 <span data-ttu-id="ef959-245">Überwachung [und Optimierung für die Leistungs](../performance/monitor-and-tune-for-performance.md) [Überwachung und Optimierungs Tools](../performance/performance-monitoring-and-tuning-tools.md) &#40;Aktivitätsmonitor "Aktivitäts Überwachung" [SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Aktivitätsmonitor](../performance-monitor/activity-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="ef959-245">[Monitor and Tune for Performance](../performance/monitor-and-tune-for-performance.md) [Performance Monitoring and Tuning Tools](../performance/performance-monitoring-and-tuning-tools.md) [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Activity Monitor](../performance-monitor/activity-monitor.md)</span></span>


