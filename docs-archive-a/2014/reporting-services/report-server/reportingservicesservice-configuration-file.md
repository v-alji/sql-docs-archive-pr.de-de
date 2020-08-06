---
title: ReportingServicesService-Konfigurationsdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- traces [Reporting Services]
- Report Server Windows service, ReportingServicesService configuration file
- ReportingServicesService configuration file
ms.assetid: 40f4a401-cb61-4c42-b1ec-01acdacdacd1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5124631db9635211827dd3b1abbff7116101a61d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618487"
---
# <a name="reportingservicesservice-configuration-file"></a><span data-ttu-id="a664a-102">ReportingServicesService-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a664a-102">ReportingServicesService Configuration File</span></span>
  <span data-ttu-id="a664a-103">Die Datei ReportingServicesService.exe.config enthält Einstellungen zum Konfigurieren der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="a664a-103">The ReportingServicesService.exe.config file includes settings that configure tracing.</span></span>  
  
## <a name="file-location"></a><span data-ttu-id="a664a-104">Dateispeicherort</span><span class="sxs-lookup"><span data-stu-id="a664a-104">File Location</span></span>  
 <span data-ttu-id="a664a-105">Diese Datei ist im Ordner \Reporting Services\Report Server\Bin gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a664a-105">This file is located in the \Reporting Services\Report Server\Bin folder.</span></span>  
  
## <a name="editing-guidelines"></a><span data-ttu-id="a664a-106">Bearbeitungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a664a-106">Editing Guidelines</span></span>  
 <span data-ttu-id="a664a-107">Sie können diese Datei ändern, um die Protokolldatei umzubenennen oder die Ablaufverfolgungsebenen zu erhöhen bzw. zu senken.</span><span class="sxs-lookup"><span data-stu-id="a664a-107">You can modify this file to rename the log file or to increase or decrease trace levels.</span></span> <span data-ttu-id="a664a-108">Ändern Sie ansonsten keine anderen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a664a-108">Do not modify any of the other settings.</span></span> <span data-ttu-id="a664a-109">Weitere Informationen finden Sie unter [Ändern einer Reporting Services-Konfigurationsdatei („RSreportserver.config“)](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="a664a-109">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="a664a-110">Weitere Informationen zu Ablaufverfolgungsprotokollen finden Sie unter [Berichtsserverdienst-Ablaufverfolgungsprotokoll](report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="a664a-110">For more information about trace logs, see [Report Server Service Trace Log](report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="a664a-111">Beispielkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a664a-111">Example Configuration</span></span>  
 <span data-ttu-id="a664a-112">Das folgende Beispiel zeigt die Einstellungen und Standardwerte, die in der Datei ReportingServicesService.exe.config gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="a664a-112">The following example shows the settings and default values found in the ReportingServicesService.exe.config file.</span></span>  
  
```  
<configSections>  
      <section name="RStrace" type="Microsoft.ReportingServices.Diagnostics.RSTraceSectionHandler,Microsoft.ReportingServices.Diagnostics" />  
</configSections>  
<system.diagnostics>  
      <switches>  
          <add name="DefaultTraceSwitch" value="3" />  
      </switches>  
</system.diagnostics>  
<RStrace>  
      <add name="FileName" value="ReportServerService_" />  
      <add name="FileSizeLimitMb" value="32" />  
      <add name="KeepFilesForDays" value="14" />  
      <add name="Prefix" value="tid, time" />  
      <add name="TraceListeners" value="debugwindow, file" />  
      <add name="TraceFileMode" value="unique" />  
      <add name="Components" value="all" />  
</RStrace>  
<runtime>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
             <dependentAssembly>  
                    <assemblyIdentity name="Microsoft.ReportingServices.Interfaces"  
                        publicKeyToken="89845dcd8080cc91"  
                        culture="neutral" />  
                    <bindingRedirect oldVersion="8.0.242.0"  
                                     newVersion="10.0.0.0"/>  
                    <bindingRedirect oldVersion="9.0.242.0"  
                                     newVersion="10.0.0.0"/>  
             </dependentAssembly>  
      </assemblyBinding>  
      <gcServer enabled="true" />  
</runtime>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="a664a-113">Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a664a-113">Configuration Settings</span></span>  
 <span data-ttu-id="a664a-114">Die folgende Tabelle enthält Informationen zu bestimmten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a664a-114">The following table provides information about specific settings.</span></span> <span data-ttu-id="a664a-115">Diese Einstellungen werden in der Reihenfolge aufgeführt, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a664a-115">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="a664a-116">Einstellung</span><span class="sxs-lookup"><span data-stu-id="a664a-116">Setting</span></span>|<span data-ttu-id="a664a-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a664a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a664a-118">**RStrace**</span><span class="sxs-lookup"><span data-stu-id="a664a-118">**RStrace**</span></span>|<span data-ttu-id="a664a-119">Gibt Namespaces an, die für Fehler und für die Ablaufverfolgung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a664a-119">Specifies namespaces used for errors and tracing.</span></span>|  
|<span data-ttu-id="a664a-120">**DefaultTraceSwitch**</span><span class="sxs-lookup"><span data-stu-id="a664a-120">**DefaultTraceSwitch**</span></span>|<span data-ttu-id="a664a-121">Gibt die Ebene der Informationen an, die im Ablaufverfolgungsprotokoll ReportServerService aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a664a-121">Specifies the level of information that is reported to the ReportServerService trace log.</span></span> <span data-ttu-id="a664a-122">Jede Ebene enthält jeweils die Informationen aller niedrigerer Ebenen.</span><span class="sxs-lookup"><span data-stu-id="a664a-122">Each level includes the information reported by all lower-numbered levels.</span></span> <span data-ttu-id="a664a-123">Das Deaktivieren der Ablaufverfolgung wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a664a-123">Disabling tracing is not recommended.</span></span> <span data-ttu-id="a664a-124">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="a664a-124">Valid values include:</span></span><br /><br /> <span data-ttu-id="a664a-125">0= Deaktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="a664a-125">0= Disables tracing</span></span><br /><br /> <span data-ttu-id="a664a-126">1= Ausnahmen und Neustarts</span><span class="sxs-lookup"><span data-stu-id="a664a-126">1= Exceptions and restarts</span></span><br /><br /> <span data-ttu-id="a664a-127">2= Ausnahmen, Neustarts, Warnungen</span><span class="sxs-lookup"><span data-stu-id="a664a-127">2= Exceptions, restarts, warnings</span></span><br /><br /> <span data-ttu-id="a664a-128">3= Ausnahmen, Neustarts, Warnungen, Statusmeldungen (Standard)</span><span class="sxs-lookup"><span data-stu-id="a664a-128">3= Exceptions, restarts, warnings, status messages (default)</span></span><br /><br /> <span data-ttu-id="a664a-129">4= Ausführlicher Modus</span><span class="sxs-lookup"><span data-stu-id="a664a-129">4= Verbose mode</span></span>|  
|<span data-ttu-id="a664a-130">**FileName**</span><span class="sxs-lookup"><span data-stu-id="a664a-130">**FileName**</span></span>|<span data-ttu-id="a664a-131">Gibt den ersten Teil des Protokolldateinamens an.</span><span class="sxs-lookup"><span data-stu-id="a664a-131">Specifies the first portion of the log file name.</span></span> <span data-ttu-id="a664a-132">Der Wert von `Prefix` ergänzt den restlichen Namen.</span><span class="sxs-lookup"><span data-stu-id="a664a-132">The value specified by `Prefix` completes the rest of the name.</span></span> <span data-ttu-id="a664a-133">Standardmäßig lautet der Name ReportServerService_.</span><span class="sxs-lookup"><span data-stu-id="a664a-133">By default, the name is ReportServerService_.</span></span>|  
|<span data-ttu-id="a664a-134">**FileSizeLimitMb**</span><span class="sxs-lookup"><span data-stu-id="a664a-134">**FileSizeLimitMb**</span></span>|<span data-ttu-id="a664a-135">Gibt eine Obergrenze für die Größe des Ablaufverfolgungsprotokolls an.</span><span class="sxs-lookup"><span data-stu-id="a664a-135">Specifies an upper limit on trace log size.</span></span> <span data-ttu-id="a664a-136">Die Datei wird in Megabytes gemessen.</span><span class="sxs-lookup"><span data-stu-id="a664a-136">The file is measured in megabytes.</span></span> <span data-ttu-id="a664a-137">Gültige Werte sind 0 bis zu einer maximalen ganzen Zahl.</span><span class="sxs-lookup"><span data-stu-id="a664a-137">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="a664a-138">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="a664a-138">The default value is 32.</span></span>|  
|<span data-ttu-id="a664a-139">**KeepFilesForDays**</span><span class="sxs-lookup"><span data-stu-id="a664a-139">**KeepFilesForDays**</span></span>|<span data-ttu-id="a664a-140">Gibt die Anzahl von Tagen an, nach der eine Ablaufverfolgungs-Protokolldatei gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="a664a-140">Specifies the number of days after which a trace log file will be deleted.</span></span> <span data-ttu-id="a664a-141">Gültige Werte sind 0 bis zu einer maximalen ganzen Zahl.</span><span class="sxs-lookup"><span data-stu-id="a664a-141">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="a664a-142">Der Standardwert ist 14.</span><span class="sxs-lookup"><span data-stu-id="a664a-142">The default value is 14.</span></span>|  
|`Prefix`|<span data-ttu-id="a664a-143">Gibt einen generierten Wert an, der die Protokollinstanzen voneinander unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="a664a-143">Specifies a generated value that distinguishes one log instance from another.</span></span> <span data-ttu-id="a664a-144">Standardmäßig werden Timestampwerte an die Dateinamen von Ablaufverfolgungsprotokollen angehängt.</span><span class="sxs-lookup"><span data-stu-id="a664a-144">By default, timestamp values are appended to trace log file names.</span></span> <span data-ttu-id="a664a-145">Dieser Wert wird auf "tid, time " festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a664a-145">This value is set to " tid, time ".</span></span> <span data-ttu-id="a664a-146">Ändern Sie diese Einstellung nicht.</span><span class="sxs-lookup"><span data-stu-id="a664a-146">Do not modify this setting.</span></span>|  
|<span data-ttu-id="a664a-147">**TraceListeners**</span><span class="sxs-lookup"><span data-stu-id="a664a-147">**TraceListeners**</span></span>|<span data-ttu-id="a664a-148">Gibt die Zieladresse für die Ausgabe des Inhalts von Ablaufverfolgungsprotokollen an.</span><span class="sxs-lookup"><span data-stu-id="a664a-148">Specifies a target for outputting trace log content.</span></span> <span data-ttu-id="a664a-149">Sie können mehrere durch Trennzeichen getrennte Ziele angeben.</span><span class="sxs-lookup"><span data-stu-id="a664a-149">You can specify multiple targets using a comma to separate each one.</span></span> <span data-ttu-id="a664a-150">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="a664a-150">Valid values include:</span></span><br /><br /> <span data-ttu-id="a664a-151">DebugWindow (Standard)</span><span class="sxs-lookup"><span data-stu-id="a664a-151">DebugWindow (default)</span></span><br /><br /> <span data-ttu-id="a664a-152">File (Standard)</span><span class="sxs-lookup"><span data-stu-id="a664a-152">File (default)</span></span><br /><br /> <span data-ttu-id="a664a-153">StdOut</span><span class="sxs-lookup"><span data-stu-id="a664a-153">StdOut</span></span>|  
|<span data-ttu-id="a664a-154">**TraceFileMode**</span><span class="sxs-lookup"><span data-stu-id="a664a-154">**TraceFileMode**</span></span>|<span data-ttu-id="a664a-155">Gibt an, ob Ablaufverfolgungsprotokolle Daten für einen Zeitraum von 24 Stunden enthalten.</span><span class="sxs-lookup"><span data-stu-id="a664a-155">Specifies whether trace logs contain data for a 24-hour period.</span></span> <span data-ttu-id="a664a-156">Für jede Komponente sollte pro Tag ein eindeutiges Ablaufverfolgungsprotokoll erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a664a-156">You should have one unique trace log for each component on each day.</span></span> <span data-ttu-id="a664a-157">Dieser Wert wird auf "Unique (Standard)" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a664a-157">This value is set to "Unique (default)".</span></span> <span data-ttu-id="a664a-158">Ändern Sie diesen Wert nicht.</span><span class="sxs-lookup"><span data-stu-id="a664a-158">Do not modify this value.</span></span>|  
|<span data-ttu-id="a664a-159">**Komponenten**</span><span class="sxs-lookup"><span data-stu-id="a664a-159">**Components**</span></span>|<span data-ttu-id="a664a-160">Gibt die Komponenten an, für die Ablaufverfolgungsprotokolle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a664a-160">Specifies the components for which trace logs are created.</span></span> <span data-ttu-id="a664a-161">Standardwert: `all`.</span><span class="sxs-lookup"><span data-stu-id="a664a-161">The default value is `all`.</span></span> <span data-ttu-id="a664a-162">Ebenfalls gültige Werte für diese Einstellung sind die Namen interner Komponenten.</span><span class="sxs-lookup"><span data-stu-id="a664a-162">Other valid values for this setting include the names of internal components.</span></span> <span data-ttu-id="a664a-163">Ändern Sie diesen Wert nicht.</span><span class="sxs-lookup"><span data-stu-id="a664a-163">Do not modify this value.</span></span>|  
|<span data-ttu-id="a664a-164">**Runtime**</span><span class="sxs-lookup"><span data-stu-id="a664a-164">**Runtime**</span></span>|<span data-ttu-id="a664a-165">Gibt Konfigurationseinstellungen an, die die Abwärtskompatibilität mit der früheren Version unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a664a-165">Specifies configuration settings that support backward compatibility with the previous version.</span></span> <span data-ttu-id="a664a-166">Mit den Runtime-Einstellungen werden Anforderungen, die an die frühere Version von Microsoft.ReportingServices.Interfaces gerichtet sind, an die neue Version umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a664a-166">Runtime settings are used to redirect requests that target the previous version of Microsoft.ReportingServices.Interfaces to the new version.</span></span><br /><br /> <span data-ttu-id="a664a-167">Alle Konfigurationseinstellungen in diesem Abschnitt sind in der Produktdokumentation zu [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a664a-167">All of the configuration settings in this section are described in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] product documentation.</span></span> <span data-ttu-id="a664a-168">Weitere Informationen finden Sie, indem Sie auf der MSDN-Website oder in der Dokumentation von [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] nach Informationen zum Schema für Laufzeiteinstellungen ("Runtime Schema Settings") suchen.</span><span class="sxs-lookup"><span data-stu-id="a664a-168">For more information, search for "Runtime Schema Settings" on the MSDN Web site or in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a664a-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a664a-169">See Also</span></span>  
 <span data-ttu-id="a664a-170">[Reporting Services-Konfigurationsdateien](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="a664a-170">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="a664a-171">Berichtsserverdienst-Ablaufverfolgungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="a664a-171">Report Server Service Trace Log</span></span>](report-server-service-trace-log.md)  
  
  
