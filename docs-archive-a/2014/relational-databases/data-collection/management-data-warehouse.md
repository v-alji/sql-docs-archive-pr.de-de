---
title: Verwaltungs-Data Warehouse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], management data warehouse
- data warehouse
- management data warehouse
ms.assetid: 9874a8b2-7ccd-494a-944c-ad33b30b5499
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 96eb26c3e273832aead4aa0421304df17dc5b8ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616102"
---
# <a name="management-data-warehouse"></a><span data-ttu-id="af3a6-102">Verwaltungs-Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="af3a6-102">Management Data Warehouse</span></span>
  <span data-ttu-id="af3a6-103">Das Verwaltungs-Data Warehouse ist eine relationale Datenbank, die alle Daten enthält, die von einem Server gesammelt werden, der das Datensammlungsziel ist.</span><span class="sxs-lookup"><span data-stu-id="af3a6-103">The management data warehouse is a relational database that contains the data that is collected from a server that is a data collection target.</span></span> <span data-ttu-id="af3a6-104">Diese Daten werden dazu verwendet, die Berichte für die Systemdaten-Sammlungssätze zu generieren. Sie können auch für benutzerdefinierte Berichte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-104">This data is used to generate the reports for the System Data collection sets, and can also be used to create custom reports.</span></span>  
  
 <span data-ttu-id="af3a6-105">Die Datensammlerinfrastruktur definiert die Aufträge und Wartungspläne, die für die Implementierung der vom Datenbankadministrator definierten Beibehaltungsrichtlinien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="af3a6-105">The data collector infrastructure defines the jobs and maintenance plans that are needed to implement the retention policies defined by the database administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af3a6-106">Für diese Version des Datensammlers wird das Verwaltungs-Data Warehouse mithilfe des einfachen Wiederherstellungsmodells erstellt, um die Protokollierung zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="af3a6-106">For this release of the data collector, the management data warehouse is created using the Simple recovery model, to minimize logging.</span></span> <span data-ttu-id="af3a6-107">Sie sollten das entsprechende Wiederherstellungsmodell für Ihre Organisation implementieren.</span><span class="sxs-lookup"><span data-stu-id="af3a6-107">You should implement the appropriate recovery model for your organization.</span></span>  
  
## <a name="deploying-and-using-the-data-warehouse"></a><span data-ttu-id="af3a6-108">Bereitstellen und Verwenden des Data Warehouses</span><span class="sxs-lookup"><span data-stu-id="af3a6-108">Deploying and Using the Data Warehouse</span></span>  
 <span data-ttu-id="af3a6-109">Sie können dieses Verwaltungs-Data Warehouse auf derselben Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installieren, die den Datensammler ausführt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-109">You can install the management data warehouse on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that runs the data collector.</span></span> <span data-ttu-id="af3a6-110">Wenn die Serverressourcen oder die Leistung auf dem überwachten Server ein Problem darstellen, können Sie das Verwaltungs-Data Warehouse auf einem anderen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="af3a6-110">However, if server resources or performance is an issue on the server being monitored, you can install the management data warehouse on a different computer.</span></span>  
  
 <span data-ttu-id="af3a6-111">Die erforderlichen Schemas sowie die Objekte für die vordefinierten Systemdaten-Sammlungssätze werden erstellt, sobald Sie das Verwaltungs-Data Warehouse erstellen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-111">The required schemas and their objects for the predefined system collection sets are created when you create the management data warehouse.</span></span> <span data-ttu-id="af3a6-112">Bei den Schemas, die erstellt werden, handelt es sich um „core“ und „snapshots“. Ein drittes Schema, „custom_snapshots“, wird bei der Erstellung von benutzerdefinierten Sammlungssätzen mit Sammlungselementen erstellt, die den generischen T-SQL-Abfragesammlertyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-112">The schemas that are created are core and snapshots.A third schema, custom_snapshots, is created when user-defined collection sets are created that include collection items that use the Generic T-SQL Query collector type.</span></span>  
  
###### <a name="core-schema"></a><span data-ttu-id="af3a6-113">Core-Schema</span><span class="sxs-lookup"><span data-stu-id="af3a6-113">Core schema</span></span>  
 <span data-ttu-id="af3a6-114">Das core-Schema beschreibt die Tabellen, gespeicherten Prozeduren und Sichten, die zum Organisieren und Identifizieren gesammelter Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-114">The core schema describes the tables, stored procedures, and views that are used to organize and to identify collected data.</span></span> <span data-ttu-id="af3a6-115">Diese Tabellen werden für alle Datentabellen, die für einzelne Sammlertypen erstellt werden, freigegeben.</span><span class="sxs-lookup"><span data-stu-id="af3a6-115">These tables are shared among all the data tables created for individual collector types.</span></span> <span data-ttu-id="af3a6-116">Dieses Schema ist gesperrt und kann nur vom Besitzer der Datenbank des Verwaltungs-Data Warehouse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-116">This schema is locked and can only be modified by the owner of the management data warehouse database.</span></span> <span data-ttu-id="af3a6-117">Den Namen der Tabellen in diesem Schema wird das Präfix "core" vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-117">The names of the tables in this schema are prefixed by "core".</span></span>  
  
 <span data-ttu-id="af3a6-118">In der folgenden Tabelle werden die Datenbanktabellen im core-Schema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af3a6-118">The following table describes the database tables in the core schema.</span></span> <span data-ttu-id="af3a6-119">Mithilfe dieser Datenbanktabellen kann der Datensammler nachverfolgen, woher die Daten kamen, wer sie eingefügt hat und wann sie in das Data Warehouse hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-119">These database tables enable the data collector to track where the data came from, who inserted it, and when it was uploaded to the data warehouse.</span></span>  
  
|<span data-ttu-id="af3a6-120">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="af3a6-120">Table name</span></span>|<span data-ttu-id="af3a6-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af3a6-121">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="af3a6-122">core.performance_counter_report_group_items</span><span class="sxs-lookup"><span data-stu-id="af3a6-122">core.performance_counter_report_group_items</span></span>|<span data-ttu-id="af3a6-123">Speichert Informationen darüber, wie die Leistungsindikatoren in den Berichten des Verwaltungs-Data Warehouse gruppiert und aggregiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-123">Stores information about how the management data warehouse reports should group and aggregate performance counters.</span></span>|  
|<span data-ttu-id="af3a6-124">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-124">core.snapshots_internal</span></span>|<span data-ttu-id="af3a6-125">Identifiziert jede neue Momentaufnahme.</span><span class="sxs-lookup"><span data-stu-id="af3a6-125">Identifies each new snapshot.</span></span> <span data-ttu-id="af3a6-126">Immer dann, wenn ein neues Uploadpaket beginnt, einen neuen Datenbatch in ein Data Warehouse hochzuladen, wird in diese Tabelle eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-126">A new row is inserted into this table whenever an upload package starts uploading a new batch of data.</span></span>|  
|<span data-ttu-id="af3a6-127">core.snapshot_timetable_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-127">core.snapshot_timetable_internal</span></span>|<span data-ttu-id="af3a6-128">Speichert Informationen über die Momentaufnahmezeiten.</span><span class="sxs-lookup"><span data-stu-id="af3a6-128">Stores information about the snapshot times.</span></span> <span data-ttu-id="af3a6-129">Die Momentaufnahmezeit wird in einer separaten Tabelle gespeichert, da viele Momentaufnahmen zur nahezu gleichen Zeit auftreten können.</span><span class="sxs-lookup"><span data-stu-id="af3a6-129">The snapshot time is stored in a separate table because many snapshots can happen at nearly the same time.</span></span>|  
|<span data-ttu-id="af3a6-130">core.source.info_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-130">core.source.info_internal</span></span>|<span data-ttu-id="af3a6-131">In dieser Tabelle werden Informationen über die Datenquelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="af3a6-131">This table stores information about the data source.</span></span> <span data-ttu-id="af3a6-132">Diese Tabelle wird immer dann aktualisiert, wenn ein neuer Sammlungssatz beginnt, Daten in das Data Warehouse hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-132">This table is updated whenever a new collection set starts uploading data to the data warehouse.</span></span>|  
|<span data-ttu-id="af3a6-133">core.supported_collector_types_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-133">core.supported_collector_types_internal</span></span>|<span data-ttu-id="af3a6-134">Enthält die IDs von registrierten Sammlertypen, die Daten in das Verwaltungs-Data Warehouse hochladen können.</span><span class="sxs-lookup"><span data-stu-id="af3a6-134">Contains the IDs of registered collector types that can upload data to the management data warehouse.</span></span> <span data-ttu-id="af3a6-135">Diese Tabelle wird nur dann aktualisiert, wenn das Schema des Warehouse so aktualisiert wird, sodass ein neuer Sammlertyp unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="af3a6-135">This table is only updated when the schema of the warehouse is updated to support a new collector type.</span></span> <span data-ttu-id="af3a6-136">Wenn das Verwaltungs-Data Warehouse erstellt wird, wird diese Tabelle mit den IDs der vom Datensammler bereitgestellten Sammlertypen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-136">When the management data warehouse is created, this table is populated with the IDs of the collector types provided by the data collector.</span></span>|  
|<span data-ttu-id="af3a6-137">core.wait_categories</span><span class="sxs-lookup"><span data-stu-id="af3a6-137">core.wait_categories</span></span>|<span data-ttu-id="af3a6-138">Enthält die Kategorien, die verwendet werden, um Wartetypen entsprechend ihrem wait_type-Merkmal zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="af3a6-138">Contains the categories used to group wait types according to wait_type characteristic.</span></span>|  
|<span data-ttu-id="af3a6-139">core.wait_types</span><span class="sxs-lookup"><span data-stu-id="af3a6-139">core.wait_types</span></span>|<span data-ttu-id="af3a6-140">Enthält die vom Datensammler erkannten Wartetypen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-140">Contains the wait types recognized by the data collector.</span></span>|  
|<span data-ttu-id="af3a6-141">core.purge_info_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-141">core.purge_info_internal</span></span>|<span data-ttu-id="af3a6-142">Gibt an, dass eine Anforderung gestellt wurde, das Entfernen von Daten aus dem Verwaltungs-Data Warehouse zu beenden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-142">Indicates that a request has been made to stop the removal of data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="af3a6-143">Die vorgenannten Tabellen werden zusammen mit den Tabellen des Sammlertyps verwendet, um Informationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="af3a6-143">The preceding tables are used with collector type tables to store information.</span></span> <span data-ttu-id="af3a6-144">Zum Beispiel verwendet der generische SQL-Ablaufverfolgungs-Sammlertyp die folgenden Tabellen, um die Ablaufverfolgungsdaten zu speichern:</span><span class="sxs-lookup"><span data-stu-id="af3a6-144">For example, the Generic SQL Trace collector type uses the following tables to store trace data:</span></span>  
  
-   <span data-ttu-id="af3a6-145">core.source_info_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-145">core.source_info_internal</span></span>  
  
-   <span data-ttu-id="af3a6-146">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="af3a6-146">core.snapshots_internal</span></span>  
  
-   <span data-ttu-id="af3a6-147">snapshots.trace_info</span><span class="sxs-lookup"><span data-stu-id="af3a6-147">snapshots.trace_info</span></span>  
  
-   <span data-ttu-id="af3a6-148">snapshots.trace_data</span><span class="sxs-lookup"><span data-stu-id="af3a6-148">snapshots.trace_data</span></span>  
  
###### <a name="snapshots-schema"></a><span data-ttu-id="af3a6-149">Momentaufnahme-Schema</span><span class="sxs-lookup"><span data-stu-id="af3a6-149">Snapshots schema</span></span>  
 <span data-ttu-id="af3a6-150">Das Momentaufnahme-Schema beschreibt die Objekte, die zum Speichern und Verwalten der von den bereitgestellten Sammlertypen gesammelten Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="af3a6-150">The snapshots schema describes the objects needed to store and maintain the data collected by the collector types that are provided.</span></span> <span data-ttu-id="af3a6-151">Die Tabellen in diesem Schema sind fest und müssen während des Lebenszyklus des Sammlertyps nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-151">The tables in this schema are fixed and do not need to be changed during the lifetime of the collector type.</span></span> <span data-ttu-id="af3a6-152">Wenn Änderungen erforderlich sind, kann das Schema nur von Mitgliedern der mdw_admin-Rolle geändert werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-152">If changes are needed, the schema can only be changed by members of the mdw_admin role.</span></span> <span data-ttu-id="af3a6-153">Diese Tabellen werden erstellt, um die von den Systemdaten-Sammlungssätzen gesammelten Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="af3a6-153">These tables are created to store the data collected by the System Data collection sets.</span></span>  
  
 <span data-ttu-id="af3a6-154">Die folgenden Tabellen zeigen einen Teil des Verwaltungs-Data Warehouse-Schemas, das für die Serveraktivitäts- und Abfragestatistik-Sammlungssätze erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="af3a6-154">The following tables illustrate a portion of the management data warehouse schema that is required for the Server Activity and Query Statistics collection sets.</span></span>  
  
-   <span data-ttu-id="af3a6-155">Ressourcentabellen auf Systemebene</span><span class="sxs-lookup"><span data-stu-id="af3a6-155">System-level resource tables</span></span>  
  
    -   <span data-ttu-id="af3a6-156">**snapshots.os_wait_stats**</span><span class="sxs-lookup"><span data-stu-id="af3a6-156">**snapshots.os_wait_stats**</span></span>  
  
    -   <span data-ttu-id="af3a6-157">**snapshots.os_latch_stats**</span><span class="sxs-lookup"><span data-stu-id="af3a6-157">**snapshots.os_latch_stats**</span></span>  
  
    -   <span data-ttu-id="af3a6-158">**snapshots.os_schedulers**</span><span class="sxs-lookup"><span data-stu-id="af3a6-158">**snapshots.os_schedulers**</span></span>  
  
    -   `snapshots.os_memory_clerks`  
  
    -   <span data-ttu-id="af3a6-159">**snapshots.os_memory_nodes**</span><span class="sxs-lookup"><span data-stu-id="af3a6-159">**snapshots.os_memory_nodes**</span></span>  
  
    -   <span data-ttu-id="af3a6-160">snapshots.sql_process_and_system_memory</span><span class="sxs-lookup"><span data-stu-id="af3a6-160">snapshots.sql_process_and_system_memory</span></span>  
  
-   <span data-ttu-id="af3a6-161">Systemaktivität</span><span class="sxs-lookup"><span data-stu-id="af3a6-161">System activity</span></span>  
  
    -   <span data-ttu-id="af3a6-162">snapshots.active_sessions_and_requests</span><span class="sxs-lookup"><span data-stu-id="af3a6-162">snapshots.active_sessions_and_requests</span></span>  
  
-   <span data-ttu-id="af3a6-163">Abfragestatistik</span><span class="sxs-lookup"><span data-stu-id="af3a6-163">Query statistics</span></span>  
  
    -   <span data-ttu-id="af3a6-164">snapshots.query_stats</span><span class="sxs-lookup"><span data-stu-id="af3a6-164">snapshots.query_stats</span></span>  
  
-   <span data-ttu-id="af3a6-165">E/A-Statistik</span><span class="sxs-lookup"><span data-stu-id="af3a6-165">I/O statistics</span></span>  
  
    -   `snapshots.io_virtual_file_stats`  
  
-   <span data-ttu-id="af3a6-166">Abfragetext und -plan</span><span class="sxs-lookup"><span data-stu-id="af3a6-166">Query text and plan</span></span>  
  
    -   <span data-ttu-id="af3a6-167">snapshots.notable_query_text</span><span class="sxs-lookup"><span data-stu-id="af3a6-167">snapshots.notable_query_text</span></span>  
  
    -   <span data-ttu-id="af3a6-168">snapshots.notable_query_plan</span><span class="sxs-lookup"><span data-stu-id="af3a6-168">snapshots.notable_query_plan</span></span>  
  
-   <span data-ttu-id="af3a6-169">Normalisierte Abfragestatistik</span><span class="sxs-lookup"><span data-stu-id="af3a6-169">Normalized query statistics</span></span>  
  
    -   <span data-ttu-id="af3a6-170">snapshots.distinct_queries</span><span class="sxs-lookup"><span data-stu-id="af3a6-170">snapshots.distinct_queries</span></span>  
  
    -   <span data-ttu-id="af3a6-171">snapshots.distinct_query_to_handle</span><span class="sxs-lookup"><span data-stu-id="af3a6-171">snapshots.distinct_query_to_handle</span></span>  
  
 <span data-ttu-id="af3a6-172">**Custom_snapshots-Schema**</span><span class="sxs-lookup"><span data-stu-id="af3a6-172">**Custom_snapshots schema**</span></span>  
  
 <span data-ttu-id="af3a6-173">Das custom_snapshots-Schema beschreibt die neuen Tabellen und Sichten, die erstellt werden, wenn mithilfe von Standard- oder Sammlertypen von Drittanbietern benutzerdefinierte Sammlungssätze erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-173">The custom_snapshots schema describes new tables and views that are created when standard or third-party collector types are used to create user-defined collection sets.</span></span> <span data-ttu-id="af3a6-174">Jeder Sammlertyp, für den eine neue Datentabelle für ein Sammelelement erforderlich ist, kann diese Tabelle in diesem Schema erstellen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-174">Any collector type that requires a new data table for a collection item can create that table in this schema.</span></span> <span data-ttu-id="af3a6-175">Neue Tabellen können in diesem Schema von Mitgliedern der mdw_writer-Rolle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-175">New tables can be added in this schema by members of the mdw_writer role.</span></span> <span data-ttu-id="af3a6-176">Alle anderen Änderungen am Schema können nur von Mitgliedern der mdw_admin-Rolle vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-176">Any other changes to the schema can only be made by members of the mdw_admin role.</span></span>  
  
 <span data-ttu-id="af3a6-177">Detaillierte Informationen zu Datentyp und Inhalt für die Datenbanktabellenspalten erhalten Sie, indem Sie die Dokumentation für die entsprechende gespeicherte Prozedur des Datensammlers für die einzelnen Tabellen lesen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-177">You can get detailed data type and content information for the database table columns by reading the documentation for the appropriate data collector stored procedure for each of the tables.</span></span>  
  
### <a name="best-practices"></a><span data-ttu-id="af3a6-178">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="af3a6-178">Best Practices</span></span>  
 <span data-ttu-id="af3a6-179">Für die Arbeit mit dem Verwaltungs-Data Warehouse werden die folgenden bewährten Methoden empfohlen:</span><span class="sxs-lookup"><span data-stu-id="af3a6-179">When working with the management data warehouse, we recommend following these best practices:</span></span>  
  
-   <span data-ttu-id="af3a6-180">Ändern Sie die Metadaten der Tabellen im Verwaltungs-Data Warehouse nicht, außer Sie fügen einen neuen Sammlertyp hinzu.</span><span class="sxs-lookup"><span data-stu-id="af3a6-180">Do not modify the metadata of management data warehouse tables unless you are adding a new collector type.</span></span>  
  
-   <span data-ttu-id="af3a6-181">Ändern Sie die Daten nicht direkt im Verwaltungs-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="af3a6-181">Do not directly modify the data in the management data warehouse.</span></span> <span data-ttu-id="af3a6-182">Durch Ändern der gesammelten Daten werden die gesammelten Daten ungültig.</span><span class="sxs-lookup"><span data-stu-id="af3a6-182">Changing the data that you have collected invalidates the legitimacy of the collected data.</span></span>  
  
-   <span data-ttu-id="af3a6-183">Statt direkt auf die Tabellen zuzugreifen, sollten Sie zum Zugriff auf Instanz- und Anwendungsdaten die dokumentierten gespeicherten Prozeduren und Funktionen verwenden, die vom Datensammler bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="af3a6-183">Instead of directly using the tables, use the documented stored procedures and functions that are provided with the data collector to access instance and application data.</span></span> <span data-ttu-id="af3a6-184">Die Tabellennamen und -definitionen können sich ändern. Sie ändern sich mit Sicherheit, wenn Sie die Anwendung aktualisieren. Darüber hinaus kann es auch in künftigen Versionen zu geänderten Tabellennamen und -definitionen kommen.</span><span class="sxs-lookup"><span data-stu-id="af3a6-184">The table names and definitions can change, do change when you update the application, and might change in future releases.</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="af3a6-185">Änderungsverlauf</span><span class="sxs-lookup"><span data-stu-id="af3a6-185">Change History</span></span>  
  
|<span data-ttu-id="af3a6-186">Aktualisierter Inhalt</span><span class="sxs-lookup"><span data-stu-id="af3a6-186">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="af3a6-187">Die Tabelle core.performance_counter_report_group_items wurde dem Abschnitt „Core-Schema“ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-187">Added the core.performance_counter_report_group_items table to the "Core schema" section.</span></span>|  
|<span data-ttu-id="af3a6-188">Die Liste von Tabellen im Abschnitt "Momentaufnahme-Schema" wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="af3a6-188">Updated the list of tables in the "Snapshots schema" section.</span></span> <span data-ttu-id="af3a6-189">snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory und snapshots.io_virtual_file_stats wurden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-189">Added snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory, and snapshots.io_virtual_file_stats.</span></span> <span data-ttu-id="af3a6-190">snapshots.os_process_memory und snapshots.distinct_query_stats wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="af3a6-190">Removedsnapshots.os_process_memory and snapshots.distinct_query_stats.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af3a6-191">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af3a6-191">See Also</span></span>  
 <span data-ttu-id="af3a6-192">[Gespeicherte Prozeduren für das Verwaltungs-Data Warehouse &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af3a6-192">[Management Data Warehouse Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="af3a6-193">[Gespeicherte Prozeduren für den Datensammler &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af3a6-193">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="af3a6-194">[Datensammlung](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="af3a6-194">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="af3a6-195">Anzeigen eines Sammlungssatzberichts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="af3a6-195">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
  
