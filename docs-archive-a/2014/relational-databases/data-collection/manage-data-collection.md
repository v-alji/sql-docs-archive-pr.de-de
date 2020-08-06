---
title: Verwalten der Datensammlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- data collector [SQL Server], Transact-SQL
- data collector [SQL Server], SQL Server Management Studio
ms.assetid: bc137daa-9f37-4c01-9766-8b7350c75af8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a7d88923bc41939541bedeed2d40908e454e9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616104"
---
# <a name="manage-data-collection"></a><span data-ttu-id="40b0e-102">Verwalten von Datensammlungen</span><span class="sxs-lookup"><span data-stu-id="40b0e-102">Manage Data Collection</span></span>
  <span data-ttu-id="40b0e-103">Sie können gespeicherten Prozeduren und Funktionen von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)] verwenden, um unterschiedliche Aspekte der Datensammlung zu verwalten, beispielsweise das Aktivieren oder Deaktivieren der Datensammlung, das Ändern einer Sammlungssatzkonfiguration oder das Anzeigen von Daten im Verwaltungs-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="40b0e-103">You can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and functions to manage different aspects of data collection, such as enabling or disabling data collection, changing a collection set configuration, or viewing data in the management data warehouse.</span></span>  
  
## <a name="manage-data-collection-by-using-sql-server-management-studio"></a><span data-ttu-id="40b0e-104">Verwalten der Datensammlung mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40b0e-104">Manage Data Collection by Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="40b0e-105">Sie können die folgenden datensammlerbezogenen Tasks ausführen, indem Sie den Objekt-Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="40b0e-105">You can perform the following data collector-related tasks by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]:</span></span>  
  
-   [<span data-ttu-id="40b0e-106">Konfigurieren des Verwaltungs-Data Warehouses &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-106">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="40b0e-107">Konfigurieren der Eigenschaften eines Datensammlers</span><span class="sxs-lookup"><span data-stu-id="40b0e-107">Configure Properties of a Data Collector</span></span>](configure-properties-of-a-data-collector.md)  
  
-   [<span data-ttu-id="40b0e-108">Aktivieren oder Deaktivieren der Datensammlung</span><span class="sxs-lookup"><span data-stu-id="40b0e-108">Enable or Disable Data Collection</span></span>](data-collection.md)  
  
-   [<span data-ttu-id="40b0e-109">Starten oder Beenden eines Sammlungssatzes</span><span class="sxs-lookup"><span data-stu-id="40b0e-109">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
-   [<span data-ttu-id="40b0e-110">Verwenden von SQL Server Profiler zum Erstellen eines Sammlungssatzes für die SQL-Ablaufverfolgung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-110">Use SQL Server Profiler to Create a SQL Trace Collection Set &#40;SQL Server Management Studio&#41;</span></span>](use-sql-server-profiler-to-create-a-sql-trace-collection-set.md)  
  
-   [<span data-ttu-id="40b0e-111">Anzeigen von Sammlungssatzprotokollen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-111">View Collection Set Logs &#40;SQL Server Management Studio&#41;</span></span>](view-collection-set-logs-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="40b0e-112">Anzeigen oder Ändern von Sammlungssatz-Zeitplänen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-112">View or Change Collection Set Schedules &#40;SQL Server Management Studio&#41;</span></span>](view-or-change-collection-set-schedules-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="40b0e-113">Anzeigen eines Sammlungssatzberichts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-113">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
## <a name="manage-data-collection-by-using-transact-sql"></a><span data-ttu-id="40b0e-114">Verwalten der Datensammlung mithilfe von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40b0e-114">Manage Data Collection by Using Transact-SQL</span></span>  
 <span data-ttu-id="40b0e-115">Der Datensammler stellt eine umfassende Sammlung von gespeicherten Prozeduren bereit, die Sie verwenden können, um beliebige datensammlerbezogene Tasks auszuführen.</span><span class="sxs-lookup"><span data-stu-id="40b0e-115">The data collector provides an extensive collection of stored procedures that you can use to perform any data-collector related task.</span></span> <span data-ttu-id="40b0e-116">Sie können mit [!INCLUDE[tsql](../../includes/tsql-md.md)]beispielsweise die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="40b0e-116">For example, by using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="40b0e-117">Konfigurieren von Parametern für die Datensammlung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-117">Configure Data Collection Parameters &#40;Transact-SQL&#41;</span></span>](configure-data-collection-parameters-transact-sql.md)  
  
-   [<span data-ttu-id="40b0e-118">Aktivieren oder Deaktivieren der Datensammlung</span><span class="sxs-lookup"><span data-stu-id="40b0e-118">Enable or Disable Data Collection</span></span>](data-collection.md)  
  
-   [<span data-ttu-id="40b0e-119">Starten oder Beenden eines Sammlungssatzes</span><span class="sxs-lookup"><span data-stu-id="40b0e-119">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
-   [<span data-ttu-id="40b0e-120">Erstellen eines benutzerdefinierten Sammlungssatzes, der einen generischen T-SQL-Abfragesammlertyp verwendet &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-120">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;</span></span>](create-custom-collection-set-generic-t-sql-query-collector-type.md)  
  
-   [<span data-ttu-id="40b0e-121">Hinzufügen eines Sammelelements zu einem Sammlungssatz &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-121">Add a Collection Item to a Collection Set &#40;Transact-SQL&#41;</span></span>](add-a-collection-item-to-a-collection-set-transact-sql.md)  
  
 <span data-ttu-id="40b0e-122">Außerdem gibt es Funktionen und Sichten, mit denen Konfigurationsdaten für die msdb- und Verwaltungs-Data Warehouse-Datenbanken, Ausführungsprotokolldaten und im Verwaltungs-Data Warehouse gespeicherte Daten abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-122">In addition, there are functions and views that you can use to get configuration data for the msdb and management data warehouse databases, execution log data, and data that is stored in the management data warehouse.</span></span>  
  
 <span data-ttu-id="40b0e-123">Sie können die bereitgestellten gespeicherten Prozeduren, Funktionen und Sichten verwenden, um eigene End-to-End-Datensammlungszenarios zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="40b0e-123">You can use the stored procedures, functions, and views that are provided to create your own end-to-end data collection scenarios.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="40b0e-124">Im Gegensatz zu regulären gespeicherten Prozeduren verwenden die gespeicherten Prozeduren des Datensammlers genau eingegebene Parameter und unterstützen die automatische Datentypkonvertierung nicht.</span><span class="sxs-lookup"><span data-stu-id="40b0e-124">Unlike regular stored procedures, the data collector stored procedures use strictly typed parameters and do not support automatic data type conversion.</span></span> <span data-ttu-id="40b0e-125">Wenn diese Parameter nicht mit den richtigen Datentypen für Eingabeparameter aufgerufen werden, wie in der Argumentbeschreibung angegeben, gibt die gespeicherte Prozedur einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="40b0e-125">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
 <span data-ttu-id="40b0e-126">Sie können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verwenden, um die bereitgestellten Codebeispiele zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="40b0e-126">You can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create and execute the provided code samples.</span></span> <span data-ttu-id="40b0e-127">Weitere Informationen finden Sie unter [Objekt-Explorer](../../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="40b0e-127">For more information, see [Object Explorer](../../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="40b0e-128">Alternativ können Sie die Abfrage in einem Editor erstellen und in einer Textdatei mit der Dateinamenerweiterung ".sql" speichern.</span><span class="sxs-lookup"><span data-stu-id="40b0e-128">As an alternative you can create the query in any editor and save it in a text file that has a .sql file name extension.</span></span> <span data-ttu-id="40b0e-129">Sie können die Abfrage mithilfe des Hilfsprogramms `sqlcmd` von der Windows-Eingabeaufforderung aus ausführen.</span><span class="sxs-lookup"><span data-stu-id="40b0e-129">You can execute the query from the Windows command prompt using the `sqlcmd` utility.</span></span> <span data-ttu-id="40b0e-130">Weitere Informationen finden Sie unter [Verwenden des Hilfsprogramms sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="40b0e-130">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
### <a name="stored-procedures-and-views"></a><span data-ttu-id="40b0e-131">Gespeicherte Prozeduren und Sichten</span><span class="sxs-lookup"><span data-stu-id="40b0e-131">Stored Procedures and Views</span></span>  
 <span data-ttu-id="40b0e-132">**Arbeiten mit dem Datensammler**</span><span class="sxs-lookup"><span data-stu-id="40b0e-132">**Working with the data collector**</span></span>  
  
 <span data-ttu-id="40b0e-133">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit dem Datensammler verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-133">The following table describes the stored procedures that you can use to work with the data collector.</span></span>  
  
|<span data-ttu-id="40b0e-134">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-134">Procedure name</span></span>|<span data-ttu-id="40b0e-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-135">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-136">sp_syscollector_enable_collector</span><span class="sxs-lookup"><span data-stu-id="40b0e-136">sp_syscollector_enable_collector</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql)|<span data-ttu-id="40b0e-137">Aktiviert den Datensammler.</span><span class="sxs-lookup"><span data-stu-id="40b0e-137">Enable the data collector.</span></span>|  
|[<span data-ttu-id="40b0e-138">sp_syscollector_disable_collector</span><span class="sxs-lookup"><span data-stu-id="40b0e-138">sp_syscollector_disable_collector</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql)|<span data-ttu-id="40b0e-139">Deaktiviert den Datensammler.</span><span class="sxs-lookup"><span data-stu-id="40b0e-139">Disable the data collector.</span></span>|  
  
 <span data-ttu-id="40b0e-140">**Arbeiten mit Sammlungssätzen**</span><span class="sxs-lookup"><span data-stu-id="40b0e-140">**Working with collection sets**</span></span>  
  
 <span data-ttu-id="40b0e-141">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit Sammlungssätzen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-141">The following table describes the stored procedures that you can use to work with collection sets.</span></span>  
  
|<span data-ttu-id="40b0e-142">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-142">Procedure name</span></span>|<span data-ttu-id="40b0e-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-143">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-144">sp_syscollector_run_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-144">sp_syscollector_run_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-run-collection-set-transact-sql)|<span data-ttu-id="40b0e-145">Führt bei Bedarf einen Sammlungssatz aus.</span><span class="sxs-lookup"><span data-stu-id="40b0e-145">Run a collection set on demand.</span></span>|  
|[<span data-ttu-id="40b0e-146">sp_syscollector_start_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-146">sp_syscollector_start_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql)|<span data-ttu-id="40b0e-147">Startet einen Sammlungssatz.</span><span class="sxs-lookup"><span data-stu-id="40b0e-147">Start a collection set.</span></span>|  
|[<span data-ttu-id="40b0e-148">sp_syscollector_stop_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-148">sp_syscollector_stop_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql)|<span data-ttu-id="40b0e-149">Beendet einen Sammlungssatz.</span><span class="sxs-lookup"><span data-stu-id="40b0e-149">Stop a collection set.</span></span>|  
|[<span data-ttu-id="40b0e-150">sp_syscollector_create_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-150">sp_syscollector_create_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-create-collection-set-transact-sql)|<span data-ttu-id="40b0e-151">Erstellt einen Sammlungssatz.</span><span class="sxs-lookup"><span data-stu-id="40b0e-151">Create a collection set.</span></span>|  
|[<span data-ttu-id="40b0e-152">sp_syscollector_delete_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-152">sp_syscollector_delete_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-collection-set-transact-sql)|<span data-ttu-id="40b0e-153">Löscht einen Sammlungssatz.</span><span class="sxs-lookup"><span data-stu-id="40b0e-153">Delete a collection set.</span></span>|  
|[<span data-ttu-id="40b0e-154">sp_syscollector_update_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-154">sp_syscollector_update_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-update-collection-set-transact-sql)|<span data-ttu-id="40b0e-155">Ändert die Konfiguration eines Sammlungssatzes.</span><span class="sxs-lookup"><span data-stu-id="40b0e-155">Change a collection set configuration.</span></span>|  
|[<span data-ttu-id="40b0e-156">sp_syscollector_upload_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-156">sp_syscollector_upload_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-upload-collection-set-transact-sql)|<span data-ttu-id="40b0e-157">Lädt Sammlungssatzdaten in das Management Data Warehouse hoch.</span><span class="sxs-lookup"><span data-stu-id="40b0e-157">Upload collection set data to the management data warehouse.</span></span> <span data-ttu-id="40b0e-158">Dies ist im Prinzip ein bedarfsgesteuerter Upload.</span><span class="sxs-lookup"><span data-stu-id="40b0e-158">This is effectively an on-demand upload.</span></span>|  
  
 <span data-ttu-id="40b0e-159">**Arbeiten mit Sammelelementen**</span><span class="sxs-lookup"><span data-stu-id="40b0e-159">**Working with collection items**</span></span>  
  
 <span data-ttu-id="40b0e-160">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit Sammelelementen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-160">The following table describes the stored procedures that you can use to work with collection items.</span></span>  
  
|<span data-ttu-id="40b0e-161">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-161">Procedure name</span></span>|<span data-ttu-id="40b0e-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-162">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-163">sp_syscollector_create_collection_item &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-163">sp_syscollector_create_collection_item &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-create-collection-item-transact-sql)|<span data-ttu-id="40b0e-164">Erstellt ein Auflistelement.</span><span class="sxs-lookup"><span data-stu-id="40b0e-164">Create a collection item.</span></span>|  
|[<span data-ttu-id="40b0e-165">sp_syscollector_delete_collection_item &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-165">sp_syscollector_delete_collection_item &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-collection-item-transact-sql)|<span data-ttu-id="40b0e-166">Löscht ein Sammelelement.</span><span class="sxs-lookup"><span data-stu-id="40b0e-166">Delete a collection item.</span></span>|  
|[<span data-ttu-id="40b0e-167">sp_syscollector_update_collection_item &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-167">sp_syscollector_update_collection_item &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-update-collection-item-transact-sql)|<span data-ttu-id="40b0e-168">Aktualisiert ein Sammelelement.</span><span class="sxs-lookup"><span data-stu-id="40b0e-168">Update a collection item.</span></span>|  
  
 <span data-ttu-id="40b0e-169">**Arbeiten mit Sammlertypen**</span><span class="sxs-lookup"><span data-stu-id="40b0e-169">**Working with collector types**</span></span>  
  
 <span data-ttu-id="40b0e-170">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit Sammlertypen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-170">The following table describes the stored procedures that you can use to work with collector types.</span></span>  
  
|<span data-ttu-id="40b0e-171">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-171">Procedure name</span></span>|<span data-ttu-id="40b0e-172">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-172">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-173">sp_syscollector_create_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-173">sp_syscollector_create_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-create-collector-type-transact-sql)|<span data-ttu-id="40b0e-174">Erstellt einen Sammlertyp.</span><span class="sxs-lookup"><span data-stu-id="40b0e-174">Create a collector type.</span></span>|  
|[<span data-ttu-id="40b0e-175">sp_syscollector_update_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-175">sp_syscollector_update_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-update-collector-type-transact-sql)|<span data-ttu-id="40b0e-176">Aktualisiert einen Sammlertyp.</span><span class="sxs-lookup"><span data-stu-id="40b0e-176">Update a collector type.</span></span>|  
|[<span data-ttu-id="40b0e-177">sp_syscollector_delete_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-177">sp_syscollector_delete_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-collector-type-transact-sql)|<span data-ttu-id="40b0e-178">Löscht einen Sammlertyp.</span><span class="sxs-lookup"><span data-stu-id="40b0e-178">Delete a collector type.</span></span>|  
  
 <span data-ttu-id="40b0e-179">**Abrufen von Konfigurationsinformationen**</span><span class="sxs-lookup"><span data-stu-id="40b0e-179">**Getting configuration information**</span></span>  
  
 <span data-ttu-id="40b0e-180">In der folgenden Tabelle werden die Sichten beschrieben, die Sie zum Abrufen von Konfigurationsinformationen und Ausführungsprotokolldaten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-180">The following table describes the views that you can use for getting configuration information and execution log data.</span></span>  
  
|<span data-ttu-id="40b0e-181">Name der Ansicht</span><span class="sxs-lookup"><span data-stu-id="40b0e-181">View name</span></span>|<span data-ttu-id="40b0e-182">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-182">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="40b0e-183">syscollector_config_store &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-183">syscollector_config_store &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-config-store-transact-sql)|<span data-ttu-id="40b0e-184">Ruft die Datensammlerkonfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-184">Get data collector configuration.</span></span>|  
|[<span data-ttu-id="40b0e-185">syscollector_collection_items &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-185">syscollector_collection_items &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-collection-items-transact-sql)|<span data-ttu-id="40b0e-186">Ruft Informationen zum Sammelelement ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-186">Get collection item information.</span></span>|  
|[<span data-ttu-id="40b0e-187">syscollector_collection_sets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-187">syscollector_collection_sets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql)|<span data-ttu-id="40b0e-188">Ruft Informationen zum Sammlungssatz ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-188">Get collection set information.</span></span>|  
|[<span data-ttu-id="40b0e-189">syscollector_collector_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-189">syscollector_collector_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-collector-types-transact-sql)|<span data-ttu-id="40b0e-190">Ruft Informationen zum Sammlertyp ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-190">Get collector type information.</span></span>|  
|[<span data-ttu-id="40b0e-191">syscollector_execution_log &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-191">syscollector_execution_log &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-execution-log-transact-sql)|<span data-ttu-id="40b0e-192">Ruft Informationen über den Sammlungssatz und die Paketausführung ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-192">Get information about collection set and package execution.</span></span>|  
|[<span data-ttu-id="40b0e-193">syscollector_execution_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-193">syscollector_execution_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-execution-stats-transact-sql)|<span data-ttu-id="40b0e-194">Ruft Informationen über die Taskausführung ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-194">Get information about task execution.</span></span>|  
|[<span data-ttu-id="40b0e-195">syscollector_execution_log_full &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-195">syscollector_execution_log_full &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-execution-log-full-transact-sql)|<span data-ttu-id="40b0e-196">Ruft Informationen ab, wenn das Ausführungsprotokoll voll ist.</span><span class="sxs-lookup"><span data-stu-id="40b0e-196">Get information when the execution log is full.</span></span>|  
  
 <span data-ttu-id="40b0e-197">**Konfigurieren des Zugriffs auf das Management Date Warehouse**</span><span class="sxs-lookup"><span data-stu-id="40b0e-197">**Configuring access to the management data warehouse**</span></span>  
  
 <span data-ttu-id="40b0e-198">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Konfigurieren des Zugriffs auf das Management Data Warehouse verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-198">The following table describes the stored procedures that you can use to configure access to the management data warehouse.</span></span>  
  
|<span data-ttu-id="40b0e-199">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-199">Procedure name</span></span>|<span data-ttu-id="40b0e-200">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-200">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-201">sp_syscollector_set_warehouse_database_name &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-201">sp_syscollector_set_warehouse_database_name &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-warehouse-database-name-transact-sql)|<span data-ttu-id="40b0e-202">Gibt den in der Verbindungszeichenfolge für das Management Data Warehouse definierten Datenbanknamen an.</span><span class="sxs-lookup"><span data-stu-id="40b0e-202">Specify the database name defined in the connection string for the management data warehouse.</span></span>|  
|[<span data-ttu-id="40b0e-203">sp_syscollector_set_warehouse_instance_name &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-203">sp_syscollector_set_warehouse_instance_name &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-warehouse-instance-name-transact-sql)|<span data-ttu-id="40b0e-204">Gibt die in der Verbindungszeichenfolge für das Management Data Warehouse definierte Instanz an.</span><span class="sxs-lookup"><span data-stu-id="40b0e-204">Specify the instance defined in the connection string for the management data warehouse.</span></span>|  
  
 <span data-ttu-id="40b0e-205">**Konfigurieren des Management Date Warehouse**</span><span class="sxs-lookup"><span data-stu-id="40b0e-205">**Configuring the management data warehouse**</span></span>  
  
 <span data-ttu-id="40b0e-206">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit der Konfiguration des Management Data Warehouse verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-206">The following table describes the stored procedures that you can use to work with the management data warehouse configuration.</span></span>  
  
|<span data-ttu-id="40b0e-207">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-207">Procedure name</span></span>|<span data-ttu-id="40b0e-208">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-208">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-209">core.sp_create_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-209">core.sp_create_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-create-snapshot-transact-sql)|<span data-ttu-id="40b0e-210">Erstellt einen Auflistungssnapshot im Management Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="40b0e-210">Create a collection snapshot in the management data warehouse.</span></span>|  
|[<span data-ttu-id="40b0e-211">core.sp_update_data_source &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-211">core.sp_update_data_source &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-update-data-source-transact-sql)|<span data-ttu-id="40b0e-212">Aktualisiert die Datenquelle für die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="40b0e-212">Update the data source for data collection.</span></span>|  
|[<span data-ttu-id="40b0e-213">core.sp_add_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-213">core.sp_add_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-add-collector-type-transact-sql)|<span data-ttu-id="40b0e-214">Fügt dem Management Data Warehouse einen Sammlertyp hinzu.</span><span class="sxs-lookup"><span data-stu-id="40b0e-214">Add a collector type to the management data warehouse.</span></span>|  
|[<span data-ttu-id="40b0e-215">core.sp_remove_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-215">core.sp_remove_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-remove-collector-type-transact-sql)|<span data-ttu-id="40b0e-216">Entfernt einen Sammlertyp aus dem Management Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="40b0e-216">Remove a collector type from the management data warehouse.</span></span>|  
|[<span data-ttu-id="40b0e-217">core.sp_purge_data &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-217">core.sp_purge_data &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-purge-data-transact-sql)|<span data-ttu-id="40b0e-218">Löscht Daten aus dem Management Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="40b0e-218">Delete data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="40b0e-219">**Arbeiten mit Uploadpaketen**</span><span class="sxs-lookup"><span data-stu-id="40b0e-219">**Working with upload packages**</span></span>  
  
 <span data-ttu-id="40b0e-220">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit Uploadpaketen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-220">The following table describes the stored procedures that you can use to work with upload packages.</span></span>  
  
|<span data-ttu-id="40b0e-221">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-221">Procedure name</span></span>|<span data-ttu-id="40b0e-222">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-222">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-223">sp_syscollector_set_cache_window &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-223">sp_syscollector_set_cache_window &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-cache-window-transact-sql)|<span data-ttu-id="40b0e-224">Konfiguriert die Anzahl von Wiederholungen für Datenuploads.</span><span class="sxs-lookup"><span data-stu-id="40b0e-224">Configure the number of data upload retries.</span></span>|  
|[<span data-ttu-id="40b0e-225">sp_syscollector_set_cache_directory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-225">sp_syscollector_set_cache_directory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-cache-directory-transact-sql)|<span data-ttu-id="40b0e-226">Gibt eine temporäre Speicherung für Daten zwischen Uploadwiederholungen an.</span><span class="sxs-lookup"><span data-stu-id="40b0e-226">Specify temporary storage for data between upload retries.</span></span>|  
  
 <span data-ttu-id="40b0e-227">**Arbeiten mit dem Ausführungsprotokoll der Datensammlung**</span><span class="sxs-lookup"><span data-stu-id="40b0e-227">**Working with the data collection execution log**</span></span>  
  
 <span data-ttu-id="40b0e-228">In der folgenden Tabelle werden die gespeicherten Prozeduren beschrieben, die Sie zum Arbeiten mit dem Ausführungsprotokoll der Datensammlung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-228">The following table describes the stored procedures that you can use to work with the data collection execution log.</span></span>  
  
|<span data-ttu-id="40b0e-229">Name der Prozedur</span><span class="sxs-lookup"><span data-stu-id="40b0e-229">Procedure name</span></span>|<span data-ttu-id="40b0e-230">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-230">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="40b0e-231">sp_syscollector_delete_execution_log_tree &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-231">sp_syscollector_delete_execution_log_tree &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-execution-log-tree-transact-sql)|<span data-ttu-id="40b0e-232">Löscht Einträge des Sammlungssatzes aus dem Ausführungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="40b0e-232">Delete collection set entries from the execution log.</span></span>|  
  
### <a name="functions"></a><span data-ttu-id="40b0e-233">Functions</span><span class="sxs-lookup"><span data-stu-id="40b0e-233">Functions</span></span>  
 <span data-ttu-id="40b0e-234">In der folgenden Tabelle werden die Funktionen beschrieben, die Sie zum Abrufen von Ausführungs- und Überwachungsinformationen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40b0e-234">The following table describes the functions that you can use to obtain execution and trace information.</span></span>  
  
|<span data-ttu-id="40b0e-235">Funktionsname</span><span class="sxs-lookup"><span data-stu-id="40b0e-235">Function name</span></span>|<span data-ttu-id="40b0e-236">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40b0e-236">Description</span></span>|  
|-------------------|-----------------|  
|[<span data-ttu-id="40b0e-237">fn_syscollector_get_execution_details &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-237">fn_syscollector_get_execution_details &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/fn-syscollector-get-execution-details-transact-sql)|<span data-ttu-id="40b0e-238">Ruft [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Ausführungsprotokolldaten für ein bestimmtes Paket ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-238">Get [!INCLUDE[ssIS](../../includes/ssis-md.md)] execution log data for a specific package.</span></span>|  
|[<span data-ttu-id="40b0e-239">fn_syscollector_get_execution_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-239">fn_syscollector_get_execution_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/fn-syscollector-get-execution-stats-transact-sql)|<span data-ttu-id="40b0e-240">Ruft Ausführungsstatistiken für einen Sammlungssatz oder ein Paket ab.</span><span class="sxs-lookup"><span data-stu-id="40b0e-240">Get execution statistics for a collection set or package.</span></span> <span data-ttu-id="40b0e-241">Diese Informationen umfassen Fehler, die protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="40b0e-241">This information includes errors that are logged.</span></span>|  
|[<span data-ttu-id="40b0e-242">snapshots.fn_trace_getdata &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40b0e-242">snapshots.fn_trace_getdata &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/snapshots-fn-trace-getdata-transact-sql)|<span data-ttu-id="40b0e-243">Ruft die Ereignisse ab, die protokolliert werden, wenn der generische SQL-Ablaufverfolgungs-Sammlertyp für das Sammeln von Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40b0e-243">Get the events that are logged when the Generic SQL Trace collector type is used to collect data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40b0e-244">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40b0e-244">See Also</span></span>  
 <span data-ttu-id="40b0e-245">[Ausführen einer gespeicherten Prozedur](../stored-procedures/execute-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="40b0e-245">[Execute a Stored Procedure](../stored-procedures/execute-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="40b0e-246">[SQL Server Management Studio verwenden](../../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="40b0e-246">[Use SQL Server Management Studio](../../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="40b0e-247">Datensammlung</span><span class="sxs-lookup"><span data-stu-id="40b0e-247">Data Collection</span></span>](data-collection.md)  
  
  