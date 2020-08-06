---
title: Lesen und Anzeigen der Setupprotokolldateien von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying log files
- Setup [SQL Server], logs
- installation log files [SQL Server]
- installing SQL Server, logs
- errors [SQL Server], Setup
- logs [SQL Server], Setup
ms.assetid: 9d77af64-9084-4375-908a-d90f99535062
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 70f9bbb9a8ed72503dc6fe90077232748b2c4ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698516"
---
# <a name="view-and-read-sql-server-setup-log-files"></a><span data-ttu-id="bfa94-102">Lesen und Anzeigen der Setupprotokolldateien von SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfa94-102">View and Read SQL Server Setup Log Files</span></span>
  <span data-ttu-id="bfa94-103">Bei jeder Ausführung von Setup werden Protokolldateien mit einem neuen Protokoll Ordner erstellt, der einen Zeitstempel aufweist, und zwar unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-103">Each execution of Setup creates log files are created with a new timestamped log folder at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span> <span data-ttu-id="bfa94-104">Das Namensformat für mit einem Zeitstempel versehene Protokollordner ist JJJJMMTT_hhmmss.</span><span class="sxs-lookup"><span data-stu-id="bfa94-104">The time-stamped log folder name format is YYYYMMDD_hhmmss.</span></span> <span data-ttu-id="bfa94-105">Wenn Setup in einem unbeaufsichtigten Modus ausgeführt wird, werden die Protokolle unter %temp%\sqlsetup\*.log erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfa94-105">When Setup is run in an unattended mode, the logs are created at % temp%\sqlsetup\*.log.</span></span> <span data-ttu-id="bfa94-106">Alle Dateien in den Protokollordnern werden in der Log\*.cab-Datei im jeweiligen Protokollordner archiviert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-106">All files in the logs folder are archived into the Log\*.cab file in their respective log folder.</span></span>  
  
 <span data-ttu-id="bfa94-107">Eine typische Setupanforderung durchläuft drei Ausführungsphasen:</span><span class="sxs-lookup"><span data-stu-id="bfa94-107">A typical Setup request goes through three execution phases:</span></span>  
  
1.  <span data-ttu-id="bfa94-108">Überprüfung der allgemeinen Regeln</span><span class="sxs-lookup"><span data-stu-id="bfa94-108">Global rules text</span></span>  
  
2.  <span data-ttu-id="bfa94-109">Komponentenupdate</span><span class="sxs-lookup"><span data-stu-id="bfa94-109">Component update</span></span>  
  
3.  <span data-ttu-id="bfa94-110">Vom Benutzer angeforderte Aktion</span><span class="sxs-lookup"><span data-stu-id="bfa94-110">User-requested action</span></span>  
  
 <span data-ttu-id="bfa94-111">In jeder dieser Phasen werden Detail- und Zusammenfassungsprotokolle generiert, wobei je nach Bedarf auch noch zusätzliche Protokolldateien generiert werden.</span><span class="sxs-lookup"><span data-stu-id="bfa94-111">In each phase, Setup generates detail and summary logs with additional logs created as appropriate.</span></span> <span data-ttu-id="bfa94-112">Das Setup wird mindestens dreimal pro vom Benutzer angeforderter Setupaktion aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bfa94-112">Setup is called at least three times per user-requested Setup action.</span></span>  
  
 <span data-ttu-id="bfa94-113">Datenspeicherdateien enthalten eine Momentaufnahme vom Zustand aller Konfigurationsobjekte, die vom Setupprozess nachverfolgt werden, und sind bei der Behebung von Konfigurationsfehlern nützlich.</span><span class="sxs-lookup"><span data-stu-id="bfa94-113">Datastore files contain a snapshot of the state of all configuration objects being tracked by the Setup process, and are useful for troubleshooting configuration errors.</span></span> <span data-ttu-id="bfa94-114">Für jede Ausführungsphase werden XML-Dateidumps von Datenspeicherobjekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfa94-114">XML file dumps are created for datastore objects for each execution phase.</span></span> <span data-ttu-id="bfa94-115">Sie werden in einem eigenen Protokollunterordner unter dem mit einem Zeitstempel versehenen Protokollordner wie folgt gespeichert:</span><span class="sxs-lookup"><span data-stu-id="bfa94-115">They are saved in their own log subfolder under the time-stamped log folder, as follows:</span></span>  
  
-   <span data-ttu-id="bfa94-116">Datastore_GlobalRules</span><span class="sxs-lookup"><span data-stu-id="bfa94-116">Datastore_GlobalRules</span></span>  
  
-   <span data-ttu-id="bfa94-117">Datastore_ComponentUpdated</span><span class="sxs-lookup"><span data-stu-id="bfa94-117">Datastore_ComponentUpdated</span></span>  
  
-   <span data-ttu-id="bfa94-118">Datenspeicher</span><span class="sxs-lookup"><span data-stu-id="bfa94-118">Datastore</span></span>  
  
 <span data-ttu-id="bfa94-119">In den folgenden Abschnitten werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setupprotokolldateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bfa94-119">The following sections describe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup log files.</span></span>  
  
## <a name="summary-text"></a><span data-ttu-id="bfa94-120">Zusammenfassungstext</span><span class="sxs-lookup"><span data-stu-id="bfa94-120">Summary Text</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-121">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-121">Overview</span></span>  
 <span data-ttu-id="bfa94-122">In dieser Datei werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Komponenten, die beim Setup entdeckt wurden, die Betriebssystemumgebung, die Parameterwerte für die Befehlszeile, wenn diese angegeben wurden, und der allgemeine Status jeder MSI-/MSP-Datei, die ausgeführt wurde, angegeben.</span><span class="sxs-lookup"><span data-stu-id="bfa94-122">This file shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that were detected during Setup, the operating system environment, command-line parameter values if they are specified, and the overall status of each MSI/MSP that was executed.</span></span>  
  
 <span data-ttu-id="bfa94-123">Das Protokoll ist in folgende Abschnitte unterteilt:</span><span class="sxs-lookup"><span data-stu-id="bfa94-123">The log is organized into the following sections:</span></span>  
  
-   <span data-ttu-id="bfa94-124">Eine allgemeine Zusammenfassung der Ausführung</span><span class="sxs-lookup"><span data-stu-id="bfa94-124">An overall summary of the execution</span></span>  
  
-   <span data-ttu-id="bfa94-125">Eigenschaften und Konfiguration des Computers, auf dem das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setup ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="bfa94-125">Properties and the configuration of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup was run</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bfa94-126">-Produktfeatures</span><span class="sxs-lookup"><span data-stu-id="bfa94-126">product features previously installed on the computer</span></span>  
  
-   <span data-ttu-id="bfa94-127">Die Beschreibung der Installationsversion und der Installationspaketeigenschaften</span><span class="sxs-lookup"><span data-stu-id="bfa94-127">Description of the installation version and installation package properties</span></span>  
  
-   <span data-ttu-id="bfa94-128">Laufzeiteingabeeinstellungen, die während der Installation angegeben werden</span><span class="sxs-lookup"><span data-stu-id="bfa94-128">Runtime input settings that are provided during install</span></span>  
  
-   <span data-ttu-id="bfa94-129">Speicherort der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bfa94-129">Location of the configuration file</span></span>  
  
-   <span data-ttu-id="bfa94-130">Details zu den Ausführungsergebnissen</span><span class="sxs-lookup"><span data-stu-id="bfa94-130">Details of the execution results</span></span>  
  
-   <span data-ttu-id="bfa94-131">Globale Regeln</span><span class="sxs-lookup"><span data-stu-id="bfa94-131">Global rules</span></span>  
  
-   <span data-ttu-id="bfa94-132">Für das Installationsszenario spezifische Regeln</span><span class="sxs-lookup"><span data-stu-id="bfa94-132">Rules specific to the installation scenario</span></span>  
  
-   <span data-ttu-id="bfa94-133">Regeln, bei denen Fehler aufgetreten sind</span><span class="sxs-lookup"><span data-stu-id="bfa94-133">Failed rules</span></span>  
  
-   <span data-ttu-id="bfa94-134">Speicherort der Regelberichtdatei</span><span class="sxs-lookup"><span data-stu-id="bfa94-134">Location of the rules report file</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-135">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-135">Location</span></span>  
 <span data-ttu-id="bfa94-136">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-136">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span>  
  
 <span data-ttu-id="bfa94-137">Um Fehler in der Textdatei zu finden, die die Zusammenfassung enthält, durchsuchen Sie die Datei nach den Schlüsselwörtern "error" oder "failed".</span><span class="sxs-lookup"><span data-stu-id="bfa94-137">To find errors in the summary text file, search the file by using the "error" or "failed" keywords.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmsstxt"></a><span data-ttu-id="bfa94-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span><span class="sxs-lookup"><span data-stu-id="bfa94-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-139">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-139">Overview</span></span>  
 <span data-ttu-id="bfa94-140">Die summary_engine-Basisdatei ähnelt der Zusammenfassungsdatei und wird während des Hauptworkflows generiert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-140">The summary_engine base file is similar to the summary file and is generated during the main workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-141">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-141">Location</span></span>  
 <span data-ttu-id="bfa94-142">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-142">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmss_componentupdatetxt"></a><span data-ttu-id="bfa94-143">Summary_engine-base_JJJJMMTT_HHMMss_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="bfa94-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-144">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-144">Overview</span></span>  
 <span data-ttu-id="bfa94-145">Die Komponentenupdate-Zusammenfassungsprotokolldatei ähnelt der Zusammenfassungsdatei und wird während des Komponentenupdateworkflows generiert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-145">The component update summary log file is similar to the summary file and is generated during the component update workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-146">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-146">Location</span></span>  
 <span data-ttu-id="bfa94-147">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-147">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_versionnumbermmdd_hhmmss_globalrulestxt"></a><span data-ttu-id="bfa94-148">Summary_engine-base_ \<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="bfa94-148">Summary_engine-base_\<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-149">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-149">Overview</span></span>  
 <span data-ttu-id="bfa94-150">Die Zusammenfassungsprotokolldatei für die globalen Regeln ähnelt der Zusammenfassungsdatei und wird während des Workflows für allgemeine Regeln generiert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-150">The global rules summary log file is similar to the summary file generated during the global rules workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-151">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-151">Location</span></span>  
 <span data-ttu-id="bfa94-152">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-152">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detailtxt"></a><span data-ttu-id="bfa94-153">Detail.txt</span><span class="sxs-lookup"><span data-stu-id="bfa94-153">Detail.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-154">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-154">Overview</span></span>  
 <span data-ttu-id="bfa94-155">Die Datei Detail.txt wird für den Hauptworkflow wie Installation oder Upgrade generiert und liefert Einzelheiten zur Ausführung.</span><span class="sxs-lookup"><span data-stu-id="bfa94-155">Detail.txt is generated for the main workflow such as install or upgrade, and provides the details of the execution.</span></span> <span data-ttu-id="bfa94-156">Die Protokolle in der Datei werden basierend auf dem Zeitpunkt generiert, zu dem die Installationsaktionen aufgerufen wurden. Sie zeigen die Reihenfolge, in der die Aktionen ausgeführt wurden, und ihre Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="bfa94-156">The logs in the file are generated based on the time when each action for the installation was invoked, and show the order in which the actions were executed, and their dependencies.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-157">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-157">Location</span></span>  
 <span data-ttu-id="bfa94-158">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup.</span><span class="sxs-lookup"><span data-stu-id="bfa94-158">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup</span></span>  
  
 <span data-ttu-id="bfa94-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="bfa94-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span></span>  
  
 <span data-ttu-id="bfa94-160">Wenn während des Setupvorgangs ein Fehler auftritt, wird die Ausnahme oder der Fehler am Ende dieser Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-160">If an error occurs during the Setup process, the exception or error are logged at the end of this file.</span></span> <span data-ttu-id="bfa94-161">Um die Fehler zu finden, prüfen Sie daher zunächst das Ende der Datei, und suchen Sie dann nach den Schlüsselwörtern "Fehler" oder "Ausnahme".</span><span class="sxs-lookup"><span data-stu-id="bfa94-161">To find the errors in this file, first examine the end of the file followed by a search of the file for the "error" or "exception" keywords.</span></span>  
  
## <a name="detail_componentupdatetxt"></a><span data-ttu-id="bfa94-162">Detail_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="bfa94-162">Detail_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-163">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-163">Overview</span></span>  
 <span data-ttu-id="bfa94-164">Die Datei Detail_ComponentUpdate.txt wird für den Komponentenupdateworkflow generiert und ähnelt der Datei Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="bfa94-164">The Detail_ComponentUpdate.txt file is generated for the component update workflow and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-165">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-165">Location</span></span>  
 <span data-ttu-id="bfa94-166">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-166">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detail_globalrulestxt"></a><span data-ttu-id="bfa94-167">Detail_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="bfa94-167">Detail_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-168">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-168">Overview</span></span>  
 <span data-ttu-id="bfa94-169">Die Datei Detail_GlobalRules.txt wird für die Ausführung der globalen Regeln generiert und ähnelt der Datei Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="bfa94-169">Detail_GlobalRules.txt is generated for the global rules execution and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-170">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-170">Location</span></span>  
 <span data-ttu-id="bfa94-171">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-171">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="msi-log-files"></a><span data-ttu-id="bfa94-172">MSI-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="bfa94-172">MSI log files</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-173">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-173">Overview</span></span>  
 <span data-ttu-id="bfa94-174">Die MSI-Protokolldateien liefern Details zum Installationspaketprozess.</span><span class="sxs-lookup"><span data-stu-id="bfa94-174">The MSI log files provide details of the installation package process.</span></span> <span data-ttu-id="bfa94-175">Sie werden durch MSIEXEC während der Installation des angegebenen Pakets generiert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-175">They are generated by the MSIEXEC during the installation of the specified package.</span></span>  
  
 <span data-ttu-id="bfa94-176">Typen von MSI-Protokolldateien:</span><span class="sxs-lookup"><span data-stu-id="bfa94-176">Types of MSI log files:</span></span>  
  
-   <span data-ttu-id="bfa94-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="bfa94-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="bfa94-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="bfa94-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="bfa94-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span><span class="sxs-lookup"><span data-stu-id="bfa94-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-180">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-180">Location</span></span>  
 <span data-ttu-id="bfa94-181">Die MSI-Protokolldateien befinden sich unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\<Name \> . log.</span><span class="sxs-lookup"><span data-stu-id="bfa94-181">The MSI log files are located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\<Name\>.log.</span></span>  
  
 <span data-ttu-id="bfa94-182">Am Ende der Datei ist eine Zusammenfassung der Ausführung zu finden, die Aufschluss über eventuelle Fehler gibt.</span><span class="sxs-lookup"><span data-stu-id="bfa94-182">At the end of the file is a summary of the execution which includes the success or failure status and properties.</span></span> <span data-ttu-id="bfa94-183">Um die Fehler in der MSI-Datei zu finden, suchen Sie nach "value 3". In der Regel sind die Fehler in der Nähe dieser Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="bfa94-183">To find the error in the MSI file, search for "value 3" and usually the errors can be found close to the string.</span></span>  
  
## <a name="configurationfileini"></a><span data-ttu-id="bfa94-184">ConfigurationFile.ini</span><span class="sxs-lookup"><span data-stu-id="bfa94-184">ConfigurationFile.ini</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-185">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-185">Overview</span></span>  
 <span data-ttu-id="bfa94-186">Die Konfigurationsdatei enthält die Eingabeeinstellungen, die während der Installation angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bfa94-186">The configuration file contains the input settings that are provided during installation.</span></span> <span data-ttu-id="bfa94-187">Sie kann verwendet werden, um eine Installation neu zu starten, ohne die Einstellungen manuell eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="bfa94-187">It can be used to restart the installation without having to enter the settings manually.</span></span> <span data-ttu-id="bfa94-188">Kennwörter für die Konten, die PID und einige Parameter werden jedoch nicht in der Konfigurationsdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bfa94-188">However, passwords for the accounts, PID, and some parameters are not saved in the configuration file.</span></span> <span data-ttu-id="bfa94-189">Diese Einstellungen können der Datei entweder hinzugefügt oder über die Befehlszeile oder die Setupbenutzeroberfläche angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bfa94-189">The settings can be either added to the file or provided by using the command line or the Setup user interface.</span></span> <span data-ttu-id="bfa94-190">Weitere Informationen finden Sie unter [Installieren von SQL Server 2014 mithilfe einer Konfigurationsdatei](install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="bfa94-190">For more information, see [Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md).</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-191">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-191">Location</span></span>  
 <span data-ttu-id="bfa94-192">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-192">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="systemconfigurationcheck_reporthtm"></a><span data-ttu-id="bfa94-193">SystemConfigurationCheck_Report.htm</span><span class="sxs-lookup"><span data-stu-id="bfa94-193">SystemConfigurationCheck_Report.htm</span></span>  
  
### <a name="overview"></a><span data-ttu-id="bfa94-194">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfa94-194">Overview</span></span>  
 <span data-ttu-id="bfa94-195">Im Bericht zur Systemkonfigurationsprüfung sind eine kurze Beschreibung für jede ausgeführte Regel sowie der Ausführungsstatus enthalten.</span><span class="sxs-lookup"><span data-stu-id="bfa94-195">The system configuration check report contains a short description for each executed rule, and the execution status.</span></span>  
  
### <a name="location"></a><span data-ttu-id="bfa94-196">Standort</span><span class="sxs-lookup"><span data-stu-id="bfa94-196">Location</span></span>  
 <span data-ttu-id="bfa94-197">Der Speicherort lautet% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="bfa94-197">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa94-198">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfa94-198">See Also</span></span>  
 <span data-ttu-id="bfa94-199">[Gewusst-wie-Themen zur Installation](../../sql-server/install/installation-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="bfa94-199">[Installation How-to Topics](../../sql-server/install/installation-how-to-topics.md) </span></span>  
 [<span data-ttu-id="bfa94-200">Installieren von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="bfa94-200">Install SQL Server 2014</span></span>](install-sql-server.md)  
  
  
