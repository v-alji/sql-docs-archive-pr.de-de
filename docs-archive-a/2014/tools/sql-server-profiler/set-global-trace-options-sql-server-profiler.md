---
title: Festlegen globaler Ablauf Verfolgungs Optionen (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f0809ae11776e1bddf42c189b86f48689ff4859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608981"
---
# <a name="set-global-trace-options-sql-server-profiler"></a><span data-ttu-id="89215-102">Festlegen globaler Ablaufverfolgungsoptionen (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="89215-102">Set Global Trace Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="89215-103">In diesem Thema wird beschrieben, wie Sie die Optionen festlegen können, die für alle Ablaufverfolgungen gelten, die mit einer bestimmten Instanz von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="89215-103">This topic describes how to set options that apply to all traces that are created with a specific instance of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-global-trace-options"></a><span data-ttu-id="89215-104">So legen Sie globale Ablaufverfolgungsoptionen fest</span><span class="sxs-lookup"><span data-stu-id="89215-104">To set global trace options</span></span>  
  
1.  <span data-ttu-id="89215-105">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="89215-105">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="89215-106">Klicken Sie im Dialogfeld **Allgemeine Optionen**auf **Schriftart auswählen**, um die Anzeigeoptionen zu ändern, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="89215-106">In the **General Options**dialog box, click **Choose Font**to modify the display options, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="89215-107">Sie können optional auch **Ablaufverfolgung sofort nach Herstellen der Verbindung starten**auswählen.</span><span class="sxs-lookup"><span data-stu-id="89215-107">Optionally, select **Start tracing immediately after making connection**.</span></span>  
  
4.  <span data-ttu-id="89215-108">Sie können optional auch **Ablaufverfolgungsdefinition bei Änderung der Anbieterversion aktualisieren**auswählen.</span><span class="sxs-lookup"><span data-stu-id="89215-108">Optionally, select **Update trace definition when provider version changes**.</span></span> <span data-ttu-id="89215-109">Diese Option wird empfohlen, und sie ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="89215-109">This option is recommended and is selected by default.</span></span> <span data-ttu-id="89215-110">Wenn diese Option aktiviert ist, wird die Ablaufverfolgungsdefinition automatisch auf die aktuelle Version des Servers aktualisiert, auf dem die Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89215-110">When this option is selected, the trace definition is automatically updated to the current version of the server where tracing is performed.</span></span>  
  
5.  <span data-ttu-id="89215-111">Sie können optional angeben, wie der Server mit Rolloverdateien umgehen soll:</span><span class="sxs-lookup"><span data-stu-id="89215-111">Optionally, specify how the server should manage rollover files:</span></span>  
  
    -   <span data-ttu-id="89215-112">Wählen Sie **Alle Rolloverdateien nacheinander ohne Eingabeaufforderung laden** aus, damit Rolloverdateien während der Wiedergabe automatisch geladen werden.</span><span class="sxs-lookup"><span data-stu-id="89215-112">Select **Load all rollover files in sequence without prompting** to automatically load rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="89215-113">Wählen sie **Bestätigung vor dem Laden von Rolloverdateien** aus, um Rolloverdateien während der Wiedergabe steuern zu können.</span><span class="sxs-lookup"><span data-stu-id="89215-113">Select **Prompt before loading rollover files** to control rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="89215-114">Wählen Sie **Nachfolgende Rolloverdateien niemals laden** aus, um jeweils nur eine Datei wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="89215-114">Select **Never load subsequent rollover files** to replay only one file at a time.</span></span>  
  
6.  <span data-ttu-id="89215-115">Optional können Sie die Wiedergabeoptionen festlegen:</span><span class="sxs-lookup"><span data-stu-id="89215-115">Optionally, set replay options:</span></span>  
  
    -   <span data-ttu-id="89215-116">**Standardanzahl von Wiedergabethreads** wird die Anzahl von Prozessorthreads kontrolliert, die während der Wiedergabe verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89215-116">**Default number of replay threads** controls the number of processor threads to use during replay.</span></span> <span data-ttu-id="89215-117">Durch eine höhere Anzahl von Threads wird die Wiedergabe schneller abgeschlossen. Die Serverleistung wird während der Wiedergabe jedoch beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="89215-117">A higher number of threads causes replay to complete faster, but causes server performance to degrade during replay.</span></span> <span data-ttu-id="89215-118">Die empfohlene Einstellung lautet **4**.</span><span class="sxs-lookup"><span data-stu-id="89215-118">The recommended setting is **4**.</span></span> <span data-ttu-id="89215-119">Die folgende Tabelle enthält die verfügbaren Optionen:</span><span class="sxs-lookup"><span data-stu-id="89215-119">The following table lists the available options:</span></span>  
  
        |<span data-ttu-id="89215-120">value</span><span class="sxs-lookup"><span data-stu-id="89215-120">Value</span></span>|<span data-ttu-id="89215-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89215-121">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="89215-122">**2**</span><span class="sxs-lookup"><span data-stu-id="89215-122">**2**</span></span>|<span data-ttu-id="89215-123">Minimalwert.</span><span class="sxs-lookup"><span data-stu-id="89215-123">Minimum value.</span></span> <span data-ttu-id="89215-124">Verwenden von zwei Threads für die Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="89215-124">Use two threads to replay.</span></span>|  
        |<span data-ttu-id="89215-125">**4**</span><span class="sxs-lookup"><span data-stu-id="89215-125">**4**</span></span>|<span data-ttu-id="89215-126">Standardwert.</span><span class="sxs-lookup"><span data-stu-id="89215-126">Default value.</span></span>|  
        |<span data-ttu-id="89215-127">**255**</span><span class="sxs-lookup"><span data-stu-id="89215-127">**255**</span></span>|<span data-ttu-id="89215-128">Maximalwert.</span><span class="sxs-lookup"><span data-stu-id="89215-128">Maximum value.</span></span> <span data-ttu-id="89215-129">Durch Einstellung eines Maximalwerts wird die für andere Prozesse verfügbare Leistung eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="89215-129">Setting a maximum value will impede performance for other processes.</span></span>|  
  
    -   <span data-ttu-id="89215-130">Mit**Standardwartezeit für Systemüberwachung (Sek.)** wird die maximale Zeitspanne in Sekunden angegeben, über die ein Wiedergabethread einen anderen Prozess blockieren kann.</span><span class="sxs-lookup"><span data-stu-id="89215-130">**Default health monitor wait interval (sec)** sets the maximum amount of time that a replay thread can block another process in seconds.</span></span> <span data-ttu-id="89215-131">In der folgenden Tabelle werden die einzelnen Werten näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="89215-131">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="89215-132">value</span><span class="sxs-lookup"><span data-stu-id="89215-132">Value</span></span>|<span data-ttu-id="89215-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89215-133">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="89215-134">**0**</span><span class="sxs-lookup"><span data-stu-id="89215-134">**0**</span></span>|<span data-ttu-id="89215-135">Minimalwert.</span><span class="sxs-lookup"><span data-stu-id="89215-135">Minimum value.</span></span> <span data-ttu-id="89215-136">Die Einstellung **0** bedeutet, dass [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] einen blockierenden Prozess in keinem Fall beendet.</span><span class="sxs-lookup"><span data-stu-id="89215-136">A setting of **0** means that [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will never stop a blocking process.</span></span>|  
        |<span data-ttu-id="89215-137">**3600**</span><span class="sxs-lookup"><span data-stu-id="89215-137">**3600**</span></span>|<span data-ttu-id="89215-138">Standardwert.</span><span class="sxs-lookup"><span data-stu-id="89215-138">Default value.</span></span> <span data-ttu-id="89215-139">Lässt blockierende Prozesse zu, die nicht länger als **3600** Sekunden oder eine Stunde dauern.</span><span class="sxs-lookup"><span data-stu-id="89215-139">Allow blocking processes that do not exceed **3600** seconds, or one hour.</span></span>|  
        |<span data-ttu-id="89215-140">**86400**</span><span class="sxs-lookup"><span data-stu-id="89215-140">**86400**</span></span>|<span data-ttu-id="89215-141">Maximalwert.</span><span class="sxs-lookup"><span data-stu-id="89215-141">Maximum value.</span></span> <span data-ttu-id="89215-142">Lässt blockierende Prozesse zu, die nicht länger als **86400** Sekunden oder einen Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="89215-142">Allow blocking processes that do not exceed **86400** seconds, or one day.</span></span>|  
  
    -   <span data-ttu-id="89215-143">Mit**Standardabrufintervall für Systemüberwachung (Sek.)** wird die Frequenz festgelegt, mit der Wiedergabethreads für blockierende Prozesse abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="89215-143">**Default health monitor poll interval (sec)** sets the frequency to poll replay threads for blocking processes.</span></span> <span data-ttu-id="89215-144">In der folgenden Tabelle werden die einzelnen Werten näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="89215-144">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="89215-145">value</span><span class="sxs-lookup"><span data-stu-id="89215-145">Value</span></span>|<span data-ttu-id="89215-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89215-146">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="89215-147">**1**</span><span class="sxs-lookup"><span data-stu-id="89215-147">**1**</span></span>|<span data-ttu-id="89215-148">Minimalwert.</span><span class="sxs-lookup"><span data-stu-id="89215-148">Minimum value.</span></span> <span data-ttu-id="89215-149">Eine Einstellung von **1** bedeutet, dass [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] blockierende Prozesse einmal pro Sekunde abruft.</span><span class="sxs-lookup"><span data-stu-id="89215-149">A setting of **1** means [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will poll for blocking processes once per second.</span></span>|  
        |<span data-ttu-id="89215-150">**60**</span><span class="sxs-lookup"><span data-stu-id="89215-150">**60**</span></span>|<span data-ttu-id="89215-151">Standardwert.</span><span class="sxs-lookup"><span data-stu-id="89215-151">Default value.</span></span> <span data-ttu-id="89215-152">Abrufen von blockierenden Prozessen einmal pro Minute.</span><span class="sxs-lookup"><span data-stu-id="89215-152">Poll for blocking processes once per minute.</span></span>|  
        |<span data-ttu-id="89215-153">**86400**</span><span class="sxs-lookup"><span data-stu-id="89215-153">**86400**</span></span>|<span data-ttu-id="89215-154">Maximalwert.</span><span class="sxs-lookup"><span data-stu-id="89215-154">Maximum value.</span></span> <span data-ttu-id="89215-155">Abrufen von blockierenden Prozessen einmal pro **86400** Sekunden, oder einmal pro Tag.</span><span class="sxs-lookup"><span data-stu-id="89215-155">Poll for blocking processes once per **86400** seconds, or one day.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89215-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89215-156">See Also</span></span>  
 <span data-ttu-id="89215-157">[Festlegen der Standardeinstellungen für die Ablaufverfolgungsanzeige &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="89215-157">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="89215-158">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="89215-158">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
