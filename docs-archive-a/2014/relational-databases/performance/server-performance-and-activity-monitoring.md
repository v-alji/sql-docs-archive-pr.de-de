---
title: Überwachen der Serverleistung und -aktivität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- activity monitoring [SQL Server]
- traces [SQL Server], how-to topics
- monitoring server performance [SQL Server], activity monitoring
- stored procedures [SQL Server], traces
- performance [SQL Server], servers
- servers [SQL Server], performance
- SQL Server Profiler, how-to topics
- SQL Server Management Studio [SQL Server], monitoring system
- Profiler [SQL Server Profiler], how-to topics
ms.assetid: f9abe48d-d6e9-4c38-a355-fc5eb5a95a25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0fa7902d68c587a7733f07ceb8daccd3a6a98fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622606"
---
# <a name="server-performance-and-activity-monitoring"></a><span data-ttu-id="17a4b-102">Überwachen der Serverleistung und -aktivität</span><span class="sxs-lookup"><span data-stu-id="17a4b-102">Server Performance and Activity Monitoring</span></span>
  <span data-ttu-id="17a4b-103">Ziel der Überwachung von Datenbanken ist es, die Leistung eines Servers zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="17a4b-103">The goal of monitoring databases is to assess how a server is performing.</span></span> <span data-ttu-id="17a4b-104">Eine effektive Überwachung umfasst die regelmäßige Erstellung von Momentaufnahmen der aktuellen Leistung, um problematische Prozesse zu isolieren, und die kontinuierliche Sammlung von Daten, um Leistungstrends über längere Zeit zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="17a4b-104">Effective monitoring involves taking periodic snapshots of current performance to isolate processes that are causing problems, and gathering data continuously over time to track performance trends.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="17a4b-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Betriebssystem stellen Hilfsprogramme bereit, mit denen Sie den aktuellen Zustand der Datenbank anzeigen und die Leistung bei Änderung der Bedingungen nachverfolgen können.</span><span class="sxs-lookup"><span data-stu-id="17a4b-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows operating system provide utilities that let you view the current condition of the database and to track performance as conditions change.</span></span>  
  
 <span data-ttu-id="17a4b-106">Der folgende Abschnitt enthält Themen zum Verwenden der Leistungs- und Aktivitätsüberwachungstools von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und Windows.</span><span class="sxs-lookup"><span data-stu-id="17a4b-106">The following section contains topics that describe how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows performance and activity monitoring tools.</span></span> <span data-ttu-id="17a4b-107">Die Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="17a4b-107">It contains the following topics:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17a4b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="17a4b-108">In This Section</span></span>  
 <span data-ttu-id="17a4b-109">**So führen Sie Überwachungsaufgaben mithilfe von Windows-Tools aus**</span><span class="sxs-lookup"><span data-stu-id="17a4b-109">**To perform monitoring tasks with Windows tools**</span></span>  
  
-   [<span data-ttu-id="17a4b-110">Starten des Systemmonitors &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-110">Start System Monitor &#40;Windows&#41;</span></span>](start-system-monitor-windows.md)  
  
-   [<span data-ttu-id="17a4b-111">Anzeigen des Anwendungsprotokolls von Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-111">View the Windows Application Log &#40;Windows&#41;</span></span>](view-the-windows-application-log-windows-10.md)  
  
 <span data-ttu-id="17a4b-112">**So erstellen Sie SQL Server-Datenbankwarnungen mithilfe von Windows-Tools**</span><span class="sxs-lookup"><span data-stu-id="17a4b-112">**To create SQL Server database alerts with Windows tools**</span></span>  
  
-   [<span data-ttu-id="17a4b-113">Einrichten einer SQL Server-Datenbankwarnung &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-113">Set Up a SQL Server Database Alert &#40;Windows&#41;</span></span>](set-up-a-sql-server-database-alert-windows.md)  
  
 <span data-ttu-id="17a4b-114">**So führen Sie Überwachungsaufgaben mithilfe von SQL Server Management Studio aus**</span><span class="sxs-lookup"><span data-stu-id="17a4b-114">**To perform monitoring tasks with SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="17a4b-115">Anzeigen des SQL Server-Fehlerprotokolls &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-115">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="17a4b-116">Öffnen des Aktivitätsmonitors &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-116">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)  
  
 <span data-ttu-id="17a4b-117">**So führen Sie Überwachungsaufgaben mithilfe der SQL-Ablaufverfolgung unter Verwendung gespeicherter Transact-SQL-Prozeduren aus**</span><span class="sxs-lookup"><span data-stu-id="17a4b-117">**To perform monitoring tasks with SQL Trace by using Transact-SQL stored procedures**</span></span>  
  
-   [<span data-ttu-id="17a4b-118">Erstellen einer Ablaufverfolgung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-118">Create a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
-   [<span data-ttu-id="17a4b-119">Festlegen eines Ablaufverfolgungsfilters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-119">Set a Trace Filter &#40;Transact-SQL&#41;</span></span>](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md)  
  
-   [<span data-ttu-id="17a4b-120">Ändern einer vorhandenen Ablaufverfolgung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-120">Modify an Existing Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/modify-an-existing-trace-transact-sql.md)  
  
-   [<span data-ttu-id="17a4b-121">Anzeigen einer gespeicherten Ablaufverfolgung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-121">View a Saved Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-a-saved-trace-transact-sql.md)  
  
-   [<span data-ttu-id="17a4b-122">Anzeigen von Filterinformationen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-122">View Filter Information &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-filter-information-transact-sql.md)  
  
-   [<span data-ttu-id="17a4b-123">Löschen einer Ablaufverfolgung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-123">Delete a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/delete-a-trace-transact-sql.md)  
  
 <span data-ttu-id="17a4b-124">**So erstellen und ändern Sie Ablaufverfolgungen mithilfe von SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="17a4b-124">**To create and modify traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="17a4b-125">Erstellen einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-125">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-126">Festlegen globaler Ablaufverfolgungsoptionen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-126">Set Global Trace Options &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-127">Angeben von Ereignissen und Datenspalten für eine Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-127">Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-128">Erstellen eines Transact-SQL-Skripts zum Ausführen einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-128">Create a Transact-SQL Script for Running a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-transact-sql-script-for-running-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-129">Speichern von Ablaufverfolgungsergebnissen in einer Datei &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-129">Save Trace Results to a File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-130">Festlegen einer maximalen Dateigröße für eine Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-130">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-131">Speichern von Ablaufverfolgungsergebnissen in einer Tabelle &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-131">Save Trace Results to a Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-132">Festlegen der maximalen Tabellengröße für eine Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-132">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-133">Filtern von Ereignissen in einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-133">Filter Events in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-134">Anzeigen von Filterinformationen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-134">View Filter Information &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-135">Ändern eines Filters &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-135">Modify a Filter &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-136">Filtern von Ereignissen nach Ereignisstartzeit &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-136">Filter Events Based on the Event Start Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-start-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-137">Filtern von Ereignissen anhand der Ereignisendzeit &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-137">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-138">Filtern von Server-Prozess-IDs &#40;SPIDs&#41; in einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-138">Filter Server Process IDs &#40;SPIDs&#41; in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-server-process-ids-spids-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-139">Organisieren von in einer Ablaufverfolgung angezeigten Spalten &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-139">Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="17a4b-140">**So können Sie Ablaufverfolgungen mithilfe von SQL Server Profiler starten, anhalten und beenden**</span><span class="sxs-lookup"><span data-stu-id="17a4b-140">**To start, pause, and stop traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="17a4b-141">Automatisches Starten einer Ablaufverfolgung nach dem Herstellen einer Verbindung mit einem Server &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-141">Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-142">Anhalten einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-142">Pause a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-143">Beenden einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-143">Stop a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-144">Ausführen einer Ablaufverfolgung, nachdem sie angehalten oder beendet wurde &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-144">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
 <span data-ttu-id="17a4b-145">**So können Sie mithilfe von SQL Server Profiler Ablaufverfolgungen öffnen und ihre Anzeige konfigurieren**</span><span class="sxs-lookup"><span data-stu-id="17a4b-145">**To open traces and configure how traces are displayed by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="17a4b-146">Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-146">Open a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-147">Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-147">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-148">Löschen des Inhalts eines Ablaufverfolgungsfensters &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-148">Clear a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-149">Schließen eines Ablaufverfolgungsfensters &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-149">Close a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/close-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-150">Festlegen der Standardeinstellungen für Ablaufverfolgungsdefinitionen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-150">Set Trace Definition Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-definition-defaults-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-151">Festlegen der Standardeinstellungen für die Ablaufverfolgungsanzeige &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-151">Set Trace Display Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="17a4b-152">**So geben Sie Ablaufverfolgungen mithilfe von SQL Server Profiler wieder**</span><span class="sxs-lookup"><span data-stu-id="17a4b-152">**To replay traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="17a4b-153">Wiedergeben einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-153">Replay a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-154">Wiedergeben einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-154">Replay a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-155">Wiedergeben von jeweils einem einzelnen Ereignis &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-155">Replay a Single Event at a Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-single-event-at-a-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-156">Wiedergeben bis zu einem Breakpoint &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-156">Replay to a Breakpoint &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-breakpoint-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-157">Wiedergeben bis zu einer Cursorposition &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-157">Replay to a Cursor &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-158">Wiedergeben eines Transact-SQL-Skripts &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-158">Replay a Transact-SQL Script &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-transact-sql-script-sql-server-profiler.md)  
  
 <span data-ttu-id="17a4b-159">**So erstellen, ändern und verwenden Sie Ablaufverfolgungsvorlagen mithilfe von SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="17a4b-159">**To create, modify, and use trace templates by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="17a4b-160">Erstellen einer Ablaufverfolgungsvorlage &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-160">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-161">Ändern einer Ablaufverfolgungsvorlage &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-161">Modify a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-162">Ableiten einer Vorlage von einer zurzeit ausgeführten Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-162">Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-163">Ableiten einer Vorlage von einer Ablaufverfolgungsdatei oder Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-163">Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-164">Exportieren einer Ablaufverfolgungsvorlage &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-164">Export a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/export-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-165">Importieren einer Ablaufverfolgungsvorlage &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-165">Import a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/import-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="17a4b-166">**So verwenden Sie SQL Server Profiler-Ablaufverfolgungen zum Auflisten und Überwachen der Serverleistung**</span><span class="sxs-lookup"><span data-stu-id="17a4b-166">**To use SQL Server Profiler traces to collect and monitor server performance**</span></span>  
  
-   [<span data-ttu-id="17a4b-167">Suchen eines Wertes oder einer Datenspalte während der Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-167">Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-168">Speichern von Deadlockdiagrammen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-168">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-169">Separates Speichern von Showplan XML-Ereignissen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-169">Save Showplan XML Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-170">Separates Speichern eines Showplan XML Statistics Profile-Ereignisses &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-170">Save Showplan XML Statistics Profile Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-statistics-profile-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-171">Extrahieren eines Skripts aus einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-171">Extract a Script from a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/extract-a-script-from-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="17a4b-172">Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="17a4b-172">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
