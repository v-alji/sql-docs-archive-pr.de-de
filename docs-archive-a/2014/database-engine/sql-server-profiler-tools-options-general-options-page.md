---
title: Optionen für "SQL Server Profiler-Tools" (Seite "Allgemeine Optionen") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.generaloptions.f1
helpviewer_keywords:
- General Options dialog box
ms.assetid: a888246d-ccfe-415f-bbdc-d6adafac250a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fad4d3529482835367898276a973bd7c8827b553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619984"
---
# <a name="sql-server-profiler---tools-options-general-options-page"></a><span data-ttu-id="73edd-102">Optionen für "SQL Server Profiler-Tools" (Seite "Allgemeine Optionen")</span><span class="sxs-lookup"><span data-stu-id="73edd-102">SQL Server Profiler - Tools-Options (General Options Page)</span></span>
  <span data-ttu-id="73edd-103">Verwenden Sie das Dialogfeld **Allgemeine Optionen** , um die folgenden Optionen anzuzeigen oder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="73edd-103">Use the **General Options** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73edd-104">Optionen</span><span class="sxs-lookup"><span data-stu-id="73edd-104">Options</span></span>  
  
### <a name="display-options"></a><span data-ttu-id="73edd-105">Anzeigeoptionen</span><span class="sxs-lookup"><span data-stu-id="73edd-105">Display Options</span></span>  
 <span data-ttu-id="73edd-106">**Schriftart Name**</span><span class="sxs-lookup"><span data-stu-id="73edd-106">**Font name**</span></span>  
 <span data-ttu-id="73edd-107">Zeigt den Namen der Schriftart an, die im Ergebnisraster der Ablaufverfolgung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="73edd-107">Displays the name of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="73edd-108">**Schriftgrad**</span><span class="sxs-lookup"><span data-stu-id="73edd-108">**Font size**</span></span>  
 <span data-ttu-id="73edd-109">Zeigt die Größe der Schrift an, die im Ergebnisraster der Ablaufverfolgung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="73edd-109">Displays the size of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="73edd-110">**Schriftart auswählen**</span><span class="sxs-lookup"><span data-stu-id="73edd-110">**Choose Font**</span></span>  
 <span data-ttu-id="73edd-111">Öffnet ein Dialogfeld, in dem die Schriftarteinstellungen geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="73edd-111">Opens a dialog to change the font settings.</span></span>  
  
 <span data-ttu-id="73edd-112">**Einstellungen für Land/Region zum Anzeigen von Datums- und Uhrzeitwerten verwenden**</span><span class="sxs-lookup"><span data-stu-id="73edd-112">**Use regional settings to display date and time values**</span></span>  
 <span data-ttu-id="73edd-113">Zeigt Datums- und Uhrzeitwerte entsprechend den Einstellungen für das Land/die Region an, die für Ihren Computer konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="73edd-113">Displays date and time values in regional settings configured for your computer.</span></span> <span data-ttu-id="73edd-114">Wenn Sie diese Option nicht aktivieren, werden die Datums- und Uhrzeitwerte in dem festgelegten Format anzeigt, das von Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verwendet wird und bei dem auch Millisekunden angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="73edd-114">If you do not select this option, the date and time values are displayed in the fixed format used by Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], which includes milliseconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73edd-115">Wenn Sie dieses Kontrollkästchen umschalten, wird das Anzeigeformat der Zeitspalten, z. B. **StartTime** und **EndTime**, geändert.</span><span class="sxs-lookup"><span data-stu-id="73edd-115">Toggling this checkbox changes the time columns display format such as **StartTime** and **EndTime**.</span></span> <span data-ttu-id="73edd-116">Nicht geändert werden jedoch die **DateTime**-Wertparameter in den Sprachereignissen oder den Remoteprozeduraufrufen (Remote Procedure Calls, RPCs).</span><span class="sxs-lookup"><span data-stu-id="73edd-116">However, it does not change the **DateTime** value parameters inside the language events or remote procedure calls (RPCs).</span></span>  
  
 <span data-ttu-id="73edd-117">**Werte in der Spalte 'Dauer' in Mikrosekunden anzeigen**</span><span class="sxs-lookup"><span data-stu-id="73edd-117">**Show values in Duration column in microseconds**</span></span>  
 <span data-ttu-id="73edd-118">Zeigt die Werte in der **Dauer** -Datenspalte bei Ablaufverfolgungen in Mikrosekunden an.</span><span class="sxs-lookup"><span data-stu-id="73edd-118">Displays the values in microseconds in the **Duration** data column of traces.</span></span> <span data-ttu-id="73edd-119">Standardmäßig werden die Werte unter **Dauer** in Millisekunden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73edd-119">By default, the **Duration** column displays values in milliseconds.</span></span>  
  
### <a name="tracing-options"></a><span data-ttu-id="73edd-120">Ablaufverfolgungsoptionen</span><span class="sxs-lookup"><span data-stu-id="73edd-120">Tracing Options</span></span>  
 <span data-ttu-id="73edd-121">**Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**</span><span class="sxs-lookup"><span data-stu-id="73edd-121">**Start tracing immediately after making connection**</span></span>  
 <span data-ttu-id="73edd-122">Startet eine Ablaufverfolgung mithilfe der Standardvorlage, sobald eine Verbindung hergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="73edd-122">Begin a trace using the default template as soon as a connection is made.</span></span>  
  
 <span data-ttu-id="73edd-123">**Ablaufverfolgungsdefinition bei Änderung der Anbieterversion aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="73edd-123">**Update trace definition when provider version changes**</span></span>  
 <span data-ttu-id="73edd-124">Wendet die neueste Ablaufverfolgungsdefinition auf [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] an, wenn der Anbieter aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="73edd-124">Apply the most current trace definition to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when the provider is updated.</span></span> <span data-ttu-id="73edd-125">Diese Option ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73edd-125">This item is not checked by default.</span></span> <span data-ttu-id="73edd-126">Dadurch ist [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] gezwungen, die Ablaufverfolgungsdefinition beim Server abzufragen und, sofern diese vorhanden ist, die Datei auf dem Datenträger neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73edd-126">This forces [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to query the server for the trace definition and re-create, if one exists, the file on disk.</span></span>  
  
### <a name="file-rollover-options"></a><span data-ttu-id="73edd-127">Dateirolloveroptionen</span><span class="sxs-lookup"><span data-stu-id="73edd-127">File Rollover Options</span></span>  
 <span data-ttu-id="73edd-128">**Alle Rolloverdateien nacheinander ohne Eingabeaufforderung laden**</span><span class="sxs-lookup"><span data-stu-id="73edd-128">**Load all rollover files in sequence without prompting**</span></span>  
 <span data-ttu-id="73edd-129">Lädt die Rolloverdateien automatisch, wenn eine Ablaufverfolgungsdatei geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="73edd-129">Load rollover files automatically when a trace file is opened.</span></span> <span data-ttu-id="73edd-130">Wenn mehrere Dateien bei der Ablaufverfolgung erstellt wurden, werden bei Auswahl dieser Option alle Rolloverdateien automatisch geladen.</span><span class="sxs-lookup"><span data-stu-id="73edd-130">If more than one file was created while tracing, selecting this option automatically loads all rollover files.</span></span>  
  
 <span data-ttu-id="73edd-131">**Bestätigung vor dem Laden von Rolloverdateien**</span><span class="sxs-lookup"><span data-stu-id="73edd-131">**Prompt before loading rollover files**</span></span>  
 <span data-ttu-id="73edd-132">Legt fest, dass Sie beim Öffnen einer Ablaufverfolgungsdatei von [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] zur Bestätigung aufgefordert werden, bevor eine Rolloverdatei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="73edd-132">Have [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] prompt you before adding a rollover file when a trace file is opened.</span></span>  
  
 <span data-ttu-id="73edd-133">**Nachfolgende Rolloverdateien niemals laden**</span><span class="sxs-lookup"><span data-stu-id="73edd-133">**Never load subsequent rollover files**</span></span>  
 [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="73edd-134">beim Öffnen einer Ablaufverfolgungsdatei nachfolgende Rolloverdateien lädt.</span><span class="sxs-lookup"><span data-stu-id="73edd-134">never loads subsequent rollover files when a trace file is opened.</span></span>  
  
### <a name="replay-options"></a><span data-ttu-id="73edd-135">Wiedergabeoptionen</span><span class="sxs-lookup"><span data-stu-id="73edd-135">Replay Options</span></span>  
 <span data-ttu-id="73edd-136">**Standardanzahl von Wiedergabethreads**</span><span class="sxs-lookup"><span data-stu-id="73edd-136">**Default number of replay threads**</span></span>  
 <span data-ttu-id="73edd-137">Gibt die Anzahl der Threads an, die gleichzeitig verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="73edd-137">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="73edd-138">Eine größere Anzahl beansprucht mehr Ressourcen bei der Wiedergabe, erhöht aber die Wiedergabeparallelität.</span><span class="sxs-lookup"><span data-stu-id="73edd-138">A higher number consumes more resources during replay, but increases replay concurrency.</span></span>  
  
 <span data-ttu-id="73edd-139">**Standardwartezeit für Systemüberwachung (Sek.)**</span><span class="sxs-lookup"><span data-stu-id="73edd-139">**Default health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="73edd-140">Gibt die Wartezeit für die Wiedergabe in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="73edd-140">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="73edd-141">Der Standardwert ist 3600 Sekunden (1 Stunde).</span><span class="sxs-lookup"><span data-stu-id="73edd-141">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="73edd-142">Die Einstellung bestimmt den Zeitraum, in dem ein Thread ausgeführt werden kann, bevor er von der Systemüberwachung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="73edd-142">This setting affects the amount of time a thread is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="73edd-143">**Standardabrufintervall für Systemüberwachung (Sek.)**</span><span class="sxs-lookup"><span data-stu-id="73edd-143">**Default health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="73edd-144">Gibt das Abrufinterval für die Systemüberwachung während der Wiedergabe in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="73edd-144">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="73edd-145">Der Standardwert ist 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="73edd-145">Default is 60 seconds.</span></span> <span data-ttu-id="73edd-146">Mit diesem Wert kann der Benutzer konfigurieren, wie oft die Systemüberwachung Informationen zu potenziell zu beendenden Vorgängen abruft.</span><span class="sxs-lookup"><span data-stu-id="73edd-146">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73edd-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73edd-147">See Also</span></span>  
 <span data-ttu-id="73edd-148">[Automatisches Starten einer Ablauf Verfolgung nach dem Herstellen einer Verbindung mit einem Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-148">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="73edd-149">[Festlegen der Standardeinstellungen für die Ablauf Verfolgungs Anzeige &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-149">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="73edd-150">[Wiedergeben einer Ablauf Verfolgungs Tabelle &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-150">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="73edd-151">[Wiedergeben einer Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-151">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="73edd-152">[Wiedergabe Ablauf Verfolgungen](../tools/sql-server-profiler/replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-152">[Replay Traces](../tools/sql-server-profiler/replay-traces.md) </span></span>  
 <span data-ttu-id="73edd-153">[Festlegen globaler Ablauf Verfolgungs Optionen &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-153">[Set Global Trace Options &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="73edd-154">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="73edd-154">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="73edd-155">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="73edd-155">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
