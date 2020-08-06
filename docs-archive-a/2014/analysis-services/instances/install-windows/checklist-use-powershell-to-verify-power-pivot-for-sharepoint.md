---
title: 'Prüfliste: Verwenden von PowerShell zum Überprüfen von PowerPivot für SharePoint | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 07/20/2020
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 73a13f05-3450-411f-95f9-4b6167cc7607
author: minewiskan
ms.author: owend
ms.openlocfilehash: 001b3fae82851b9ec08b0383bb3db9e6d011ae32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697318"
---
# <a name="checklist-use-powershell-to-verify-powerpivot-for-sharepoint"></a><span data-ttu-id="dd28a-102">Prüfliste: Überprüfen von PowerPivot für SharePoint mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd28a-102">CheckList: Use PowerShell to Verify PowerPivot for SharePoint</span></span>
  <span data-ttu-id="dd28a-103">[!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] -Installations- oder -Wiederherstellungsvorgänge sind erst abgeschlossen, nachdem ein solider Überprüfungstestlauf ausgeführt wurde, durch den die Einsatzbereitschaft der Dienste und Daten bestätigt wird.</span><span class="sxs-lookup"><span data-stu-id="dd28a-103">No [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] installation or recovery operation is complete without a solid verification test pass that confirms your services and data are operational.</span></span> <span data-ttu-id="dd28a-104">In diesem Artikel erfahren Sie, wie Sie diese Schritte mit Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="dd28a-104">In this article, we show you how to perform these steps using Windows PowerShell.</span></span> <span data-ttu-id="dd28a-105">Jeder Schritt wird in einem eigenen Abschnitt behandelt, sodass Sie direkt zu einer bestimmten Aufgabe wechseln können.</span><span class="sxs-lookup"><span data-stu-id="dd28a-105">We put each step into its own section so that you can go straight to specific tasks.</span></span> <span data-ttu-id="dd28a-106">Führen Sie z. B. das Skript im Abschnitt [Datenbanken](#bkmk_databases) dieses Themas aus, um die Namen von Dienstanwendung und Inhaltsdatenbanken zu überprüfen, wenn Sie Wartungen oder Sicherungen für sie planen möchten.</span><span class="sxs-lookup"><span data-stu-id="dd28a-106">For example, run the script in the [Databases](#bkmk_databases) section of this topic to verify the name of the service application and content databases if you want to schedule them for maintenance or backup.</span></span>

|||
|-|-|
|<span data-ttu-id="dd28a-107">![PowerShell-Inhalt](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell-Inhalt")</span><span class="sxs-lookup"><span data-stu-id="dd28a-107">![PowerShell related content](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell related content")</span></span>|<span data-ttu-id="dd28a-108">Ein vollständiges PowerShell-Skript finden Sie am Ende des Themas.</span><span class="sxs-lookup"><span data-stu-id="dd28a-108">A full PowerShell script is included at the bottom of the topic.</span></span> <span data-ttu-id="dd28a-109">Verwenden Sie das vollständige Skript als Ausgangspunkt für die Erstellung eines benutzerdefinierten Skripts, das zur Überwachung der gesamten [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] -Bereitstellung eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="dd28a-109">Use the full script as a starting point to build a custom script for auditing your full [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] deployment.</span></span>|

||
|-|
|<span data-ttu-id="dd28a-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="dd28a-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="dd28a-111">**In diesem Thema**: Die mit Buchstaben gekennzeichneten Elemente im folgenden Inhaltsverzeichnis beziehen sich auf die Bereiche des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="dd28a-111">**In this topic**: The lettered items in the following the TOC correspond to areas of the diagram.</span></span> <span data-ttu-id="dd28a-112">Das Diagramm veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="dd28a-112">The diagram illustrates the</span></span>

|||
|-|-|
|[<span data-ttu-id="dd28a-113">Vorbereitung der PowerShell-Umgebung</span><span class="sxs-lookup"><span data-stu-id="dd28a-113">Prepare your PowerShell environment</span></span>](#bkmk_prerequisites)<br /><br /> [<span data-ttu-id="dd28a-114">Symptome und empfohlene Aktionen</span><span class="sxs-lookup"><span data-stu-id="dd28a-114">Symptoms and Recommended Actions</span></span>](#bkmk_symptoms)<br /><br /> <span data-ttu-id="dd28a-115">**(A)** [Windows-Dienst von Analysis Services](#bkmk_windows_service)</span><span class="sxs-lookup"><span data-stu-id="dd28a-115">**(A)** [Analysis Services Windows Service](#bkmk_windows_service)</span></span><br /><br /> <span data-ttu-id="dd28a-116">**(B)** [powerpivotsystemservice und powerpivotengineservice](#bkmk_engine_and_system_service)</span><span class="sxs-lookup"><span data-stu-id="dd28a-116">**(B)** [PowerPivotSystemService and PowerPivotEngineService](#bkmk_engine_and_system_service)</span></span><br /><br /> <span data-ttu-id="dd28a-117">**(C)** [PowerPivot-Dienstanwendung(en) und -Proxys](#bkmk_powerpivot_service_application)</span><span class="sxs-lookup"><span data-stu-id="dd28a-117">**(C)** [PowerPivot Service Application(s) and proxies](#bkmk_powerpivot_service_application)</span></span><br /><br /> <span data-ttu-id="dd28a-118">**(D)** [Datenbanken](#bkmk_databases)</span><span class="sxs-lookup"><span data-stu-id="dd28a-118">**(D)** [Databases](#bkmk_databases)</span></span><br /><br /> [<span data-ttu-id="dd28a-119">SharePoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="dd28a-119">SharePoint Features</span></span>](#bkmk_features)<br /><br /> [<span data-ttu-id="dd28a-120">Zeitgeberaufträge</span><span class="sxs-lookup"><span data-stu-id="dd28a-120">Timer Jobs</span></span>](#bkmk_timer_jobs)<br /><br /> [<span data-ttu-id="dd28a-121">Integritätsregeln</span><span class="sxs-lookup"><span data-stu-id="dd28a-121">Health Rules</span></span>](#bkmk_health_rules)<br /><br /> <span data-ttu-id="dd28a-122">**(E)** [Windows- und ULS-Protokolle](#bkmk_logs)</span><span class="sxs-lookup"><span data-stu-id="dd28a-122">**(E)** [Windows and ULS Logs](#bkmk_logs)</span></span><br /><br /> [<span data-ttu-id="dd28a-123">MSOLAP-Anbieter</span><span class="sxs-lookup"><span data-stu-id="dd28a-123">MSOLAP Provider</span></span>](#bkmk_msolap)<br /><br /> [<span data-ttu-id="dd28a-124">ADOMD.NET-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="dd28a-124">ADOMD.Net client Library</span></span>](#bkmk_adomd)<br /><br /> [<span data-ttu-id="dd28a-125">Regeln zur Sammlung von Integritätsdaten</span><span class="sxs-lookup"><span data-stu-id="dd28a-125">Health Data Collection Rules</span></span>](#bkmk_health_collection)<br /><br /> [<span data-ttu-id="dd28a-126">Lösungen</span><span class="sxs-lookup"><span data-stu-id="dd28a-126">Solutions</span></span>](#bkmk_solutions)<br /><br /> [<span data-ttu-id="dd28a-127">Manuelle Überprüfungsschritte</span><span class="sxs-lookup"><span data-stu-id="dd28a-127">Manual Verification Steps</span></span>](#bkmk_manual)<br /><br /> [<span data-ttu-id="dd28a-128">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="dd28a-128">More Resources</span></span>](#bkmk_more_resources)<br /><br /> [<span data-ttu-id="dd28a-129">Vollständiges PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="dd28a-129">Full PowerShell Script</span></span>](#bkmk_full_script)|<span data-ttu-id="dd28a-130">![PowerShell-Überprüfung von PowerPivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "PowerShell-Überprüfung von PowerPivot")</span><span class="sxs-lookup"><span data-stu-id="dd28a-130">![powershell verification of powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "powershell verification of powerpivot")</span></span>|

##  <a name="prepare-your-powershell-environment"></a><a name="bkmk_prerequisites"></a><span data-ttu-id="dd28a-131">Vorbereiten der PowerShell-Umgebung</span><span class="sxs-lookup"><span data-stu-id="dd28a-131">Prepare your PowerShell environment</span></span>
 <span data-ttu-id="dd28a-132">Mithilfe der Schritte in diesem Abschnitt bereiten Sie die PowerShell-Umgebung vor.</span><span class="sxs-lookup"><span data-stu-id="dd28a-132">The steps in this section prepare your PowerShell environment.</span></span> <span data-ttu-id="dd28a-133">Je nach Konfiguration der Skriptumgebung sind die Schritte u. U. nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd28a-133">The steps may not be required, depending on how your scripting environment is currently configured.</span></span>

 <span data-ttu-id="dd28a-134">**PowerShell-Berechtigungen**</span><span class="sxs-lookup"><span data-stu-id="dd28a-134">**PowerShell Permissions**</span></span>

 <span data-ttu-id="dd28a-135">Öffnen Sie ein PowerShell-Fenster oder PowerShell ISE (integrierte Skriptumgebung) mit **Administratorrechten**.</span><span class="sxs-lookup"><span data-stu-id="dd28a-135">Open a Powershell window or the PowerShell ISE (Integrated Scripting Environment) with **administrative privileges**.</span></span> <span data-ttu-id="dd28a-136">Wenn Sie Befehle ohne Administratorrechte ausführen, wird eine Fehlermeldung ähnlich der folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd28a-136">If you do not have administrative privileges when you run commands, you will see an error message similar to the following:</span></span>

 <span data-ttu-id="dd28a-137">Get-SPLogEvent: Sie müssen **Administratorrechte** für den Computer besitzen, um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dd28a-137">Get-SPLogEvent : You need to have Machine **administrator privileges** to run this cmdlet.</span></span>

 <span data-ttu-id="dd28a-138">**SharePoint und [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]**-Modul</span><span class="sxs-lookup"><span data-stu-id="dd28a-138">**SharePoint and [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]** Module</span></span>

 <span data-ttu-id="dd28a-139">Wenn beim Ausführen der zugehörigen SharePoint-Cmdlets eine Fehlermeldung ähnlich der folgenden angezeigt wird, führen Sie den Add-PSSnapin-Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dd28a-139">If you see an error message similar to the following when you run SharePoint related cmdlets, run the Add-PSSnapin command:</span></span>

 <span data-ttu-id="dd28a-140">Die Benennung „Get-PowerPivotSystemService“ **wurde nicht als Name eines Cmdlets**, einer Funktion, einer Skriptdatei oder eines ausführbaren Programms erkannt.</span><span class="sxs-lookup"><span data-stu-id="dd28a-140">The term 'Get-PowerPivotSystemService' **is not recognized as the name of a cmdlet**, function, script file, or operable program.</span></span> <span data-ttu-id="dd28a-141">Prüfen Sie die Schreibweise des Namens bzw. stellen Sie sicher, dass der Pfad korrekt angegeben wurde, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="dd28a-141">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>

```
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0
```

 <span data-ttu-id="dd28a-142">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dd28a-142">**Windows PowerShell**</span></span>

 <span data-ttu-id="dd28a-143">Weitere Informationen zu PowerShell ISE finden Sie unter [Einführung in Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) und [Verwenden von Windows PowerShell zur Verwaltung von SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="dd28a-143">For more information on the PowerShell ISE, see [Introducing the Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) and [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span></span>

|||
|-|-|
|<span data-ttu-id="dd28a-144">![Allgemeine Anwendungseinstellungen für PowerPivot in SharePoint](../../../sql-server/install/media/ssas-powerpivot-logo.png "Allgemeine Anwendungseinstellungen für PowerPivot in SharePoint")</span><span class="sxs-lookup"><span data-stu-id="dd28a-144">![powerpivot in sharepoint general application set](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot in sharepoint general application set")</span></span>|<span data-ttu-id="dd28a-145">Die meisten Komponenten in der Zentraladministration können mithilfe des [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Management-Dashboards optional überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="dd28a-145">You can optionally verify a majority of the components in Central Administration, using the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] management dashboard.</span></span> <span data-ttu-id="dd28a-146">Um das Dashboard in der Zentraladministration zu öffnen, klicken Sie auf **Allgemeine Anwendungseinstellungen**und dann in **PowerPivot** auf **Management-Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="dd28a-146">To open the dashboard in Central Administration, click **General Application Settings**, and then click **Management Dashboard** in the **PowerPivot**.</span></span> <span data-ttu-id="dd28a-147">Weitere Informationen zum Dashboard finden Sie unter [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-147">For more information on the dashboard, see [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span></span>|

##  <a name="symptoms-and-recommended-actions"></a><a name="bkmk_symptoms"></a><span data-ttu-id="dd28a-148">Symptome und empfohlene Aktionen</span><span class="sxs-lookup"><span data-stu-id="dd28a-148">Symptoms and Recommended Actions</span></span>
 <span data-ttu-id="dd28a-149">Die folgende Tabelle enthält eine Liste der Symptome oder Probleme und den jeweiligen Abschnitt, in dem Sie Unterstützung für die Problemlösung finden.</span><span class="sxs-lookup"><span data-stu-id="dd28a-149">The following table is a list of symptoms or issues and the suggested section of this topic to consult to help you resolve the issue.</span></span>

|<span data-ttu-id="dd28a-150">Symptom</span><span class="sxs-lookup"><span data-stu-id="dd28a-150">Symptom</span></span>|<span data-ttu-id="dd28a-151">Siehe Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dd28a-151">See section</span></span>|
|-------------|-----------------|
|<span data-ttu-id="dd28a-152">Datenaktualisierung wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="dd28a-152">Data refresh is not running</span></span>|<span data-ttu-id="dd28a-153">Lesen Sie den Abschnitt [Timer Jobs](#bkmk_timer_jobs) , und stellen Sie sicher, dass der **Zeitgeberauftrag für die PowerPivot-Onlinedatenaktualisierung** online ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-153">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Online PowerPivot Data Refresh Timer Job** is online.</span></span>|
|<span data-ttu-id="dd28a-154">Die Daten im Management-Dashboard sind veraltet</span><span class="sxs-lookup"><span data-stu-id="dd28a-154">Management dashboard data is old</span></span>|<span data-ttu-id="dd28a-155">Lesen Sie den Abschnitt [Zeitgeberaufträge](#bkmk_timer_jobs) , und stellen Sie sicher, dass der **Zeitgeberauftrag für die Verarbeitung des Management-Dashboards** online ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-155">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Management Dashboard Processing Timer Job** is online.</span></span>|
|<span data-ttu-id="dd28a-156">Einige Bereiche des Management-Dashboards</span><span class="sxs-lookup"><span data-stu-id="dd28a-156">Some portions of the Management Dashboard</span></span>|<span data-ttu-id="dd28a-157">Wenn Sie PowerPivot für SharePoint in einer Farm installieren, die die Topologie der Zentraladministration ohne Excel Services oder PowerPivot für SharePoint aufweist, müssen Sie die Microsoft ADOMD.NET-Clientbibliothek herunterladen und installieren, wenn Sie Vollzugriff auf die integrierten Berichte im PowerPivot-Management-Dashboard erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="dd28a-157">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, you must download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="dd28a-158">Einige Berichte im Dashboard verwenden ADOMD.NET für den Zugriff auf interne Daten, die Berichtsdaten zur PowerPivot-Abfrageverarbeitung und zum Serverzustand in der Farm liefern.</span><span class="sxs-lookup"><span data-stu-id="dd28a-158">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span> <span data-ttu-id="dd28a-159">Siehe den Abschnitt [ADOMD.Net-Clientbibliothek](#bkmk_adomd) und das Thema [Installieren von ADOMD.NET auf Web-Front-End-Servern, auf denen die Zentraladministration ausgeführt wird](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-159">See the section [ADOMD.Net client Library](#bkmk_adomd) and the topic [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>|
|\<future content>||

##  <a name="analysis-services-windows-service"></a><a name="bkmk_windows_service"></a><span data-ttu-id="dd28a-160">Analysis Services-Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="dd28a-160">Analysis Services Windows Service</span></span>
 <span data-ttu-id="dd28a-161">Durch das Skript in diesem Abschnitt wird die [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Instanz im SharePoint-Modus überprüft.</span><span class="sxs-lookup"><span data-stu-id="dd28a-161">The script in this section verifies the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="dd28a-162">Überprüfen Sie, ob der Dienst **ausgeführt**wird.</span><span class="sxs-lookup"><span data-stu-id="dd28a-162">Verify the service is **running**.</span></span>

```powershell
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name              DisplayName                                Status
----              -----------                                ------
MSOLAP$POWERPIVOT SQL Server Analysis Services (POWERPIVOT) Running
```

##  <a name="powerpivotsystemservice-and-powerpivotengineservice"></a><a name="bkmk_engine_and_system_service"></a><span data-ttu-id="dd28a-163">Powerpivotsystemservice und powerpivotengineservice</span><span class="sxs-lookup"><span data-stu-id="dd28a-163">PowerPivotSystemService and PowerPivotEngineService</span></span>
 <span data-ttu-id="dd28a-164">Durch die Skripts in diesem Abschnitt werden die [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] -Systemdienste überprüft.</span><span class="sxs-lookup"><span data-stu-id="dd28a-164">The scripts in this section verify the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] system services.</span></span> <span data-ttu-id="dd28a-165">Es gibt einen Systemdienst für eine SharePoint 2013-Bereitstellung und zwei Dienste für eine SharePoint 2010-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="dd28a-165">There is one system service for a SharePoint 2013 deployment and two services for a SharePoint 2010 deployment.</span></span>

 <span data-ttu-id="dd28a-166">**PowerPivotSystemService**</span><span class="sxs-lookup"><span data-stu-id="dd28a-166">**PowerPivotSystemService**</span></span>

 <span data-ttu-id="dd28a-167">Überprüfen Sie, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-167">Verify the Status is **Online**.</span></span>

```powershell
Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                  Status Applications                             Farm
--------                                  ------ ------------                             ----
SQL Server PowerPivot Service Application Online {Default PowerPivot Service Application} SPFarm Name=SharePoint_Config_77d8ab0744a34e8aa27c806a2b8c760c
```

 <span data-ttu-id="dd28a-168">**PowerPivotEngineService**</span><span class="sxs-lookup"><span data-stu-id="dd28a-168">**PowerPivotEngineService**</span></span>

> [!NOTE]
>  <span data-ttu-id="dd28a-169">Wenn Sie SharePoint 2013 verwenden,**überspringen Sie dieses Skript** .</span><span class="sxs-lookup"><span data-stu-id="dd28a-169">**Skip this script if** you are using SharePoint 2013.</span></span> <span data-ttu-id="dd28a-170">Der PowerPivotEngineService ist nicht Teil einer SharePoint 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="dd28a-170">The PowerPivotEngineService is not part of a SharePoint 2013 deployment.</span></span> <span data-ttu-id="dd28a-171">Wenn Sie das Get-PowerPivot**Engine**Service-Cmdlet für SharePoint 2013 ausführen, wird eine Fehlermeldung ähnlich der folgenden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd28a-171">If you run the Get-PowerPivot**Engine**Service cmdlet on SharePoint 2013, you will see an error message similar to the following.</span></span> <span data-ttu-id="dd28a-172">Diese Fehlermeldung wird selbst dann zurückgegeben, wenn Sie den Add-PSSnapin-Befehl ausgeführt haben, der im Abschnitt zu den Voraussetzungen in diesem Thema erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="dd28a-172">This error message is returned even if you have run the Add-PSSnapin command described in the prerequisites section of this topic.</span></span>
> 
>  <span data-ttu-id="dd28a-173">Die Benennung "Get-PowerPivotEngineService" wird nicht als Name eines Cmdlets erkannt</span><span class="sxs-lookup"><span data-stu-id="dd28a-173">The term 'Get-PowerPivotEngineService' is not recognized as the name of a cmdlet</span></span>

 <span data-ttu-id="dd28a-174">Überprüfen Sie in einer SharePoint 2010-Bereitstellung, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-174">In a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName  : SQL Server Analysis Services
Status    : Online
Name      : MSOLAP$POWERPIVOT
Instances : {POWERPIVOT}
Farm      : SPFarm Name=SharePoint_Config
```

##  <a name="powerpivot-service-applications-and-proxies"></a><a name="bkmk_powerpivot_service_application"></a><span data-ttu-id="dd28a-175">Power Pivot-Dienst Anwendung (en) und Proxys</span><span class="sxs-lookup"><span data-stu-id="dd28a-175">PowerPivot Service Application(s) and proxies</span></span>
 <span data-ttu-id="dd28a-176">Überprüfen Sie, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-176">Verify the status is **Online**.</span></span> <span data-ttu-id="dd28a-177">Die Excel Services-Anwendung verwendet keine Dienstanwendungs-Datenbank. Folglich gibt das Cmdlet keinen Datenbanknamen zurück.</span><span class="sxs-lookup"><span data-stu-id="dd28a-177">The Excel Services Application does not use a service application database and therefore the cmdlet does not return a database name.</span></span> <span data-ttu-id="dd28a-178">Merken Sie sich die von der [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Dienstanwendung verwendete Datenbank, damit sie im weiter unten beschriebenen Abschnitt zu Datenbanken überprüfen können, ob die Datenbank online ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-178">Note the database used by the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] service application so you can verify the database is online in the database section later in this topic.</span></span>

 <span data-ttu-id="dd28a-179">**PowerPivot und Excel-Dienstanwendung(en)**</span><span class="sxs-lookup"><span data-stu-id="dd28a-179">**PowerPivot and Excel Service Application(s)**</span></span>

 <span data-ttu-id="dd28a-180">Überprüfen Sie in einer SharePoint 2010-Bereitstellung, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-180">For a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename, DisplayName, status
```

```Output
TypeName          : PowerPivot Service Application
Name              : PowerPivotServiceApplication1
Status            : Online
UnattendedAccount : PowerPivotUnattendedAccount
ApplicationPool   : SPIisWebServiceApplicationPool Name=sqlbi_serviceapp
Farm              : SPFarm Name=SharePoint_Config
Database          : GeminiServiceDatabase Name=PowerPivotServiceApplication1_19648f3f2c944e27acdc6c20aab8487a

TypeName    : Excel Services Application Web Service Application
DisplayName : Excel Services Application
Status      : Online
```

 <span data-ttu-id="dd28a-181">**Dienst Anwendungs Pool**</span><span class="sxs-lookup"><span data-stu-id="dd28a-181">**Service Application Pool**</span></span>

> [!NOTE]
>  <span data-ttu-id="dd28a-182">Im folgenden Codebeispiel wird zuerst die applicationpool-Eigenschaft der standardmäßigen [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] -Dienstanwendung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dd28a-182">The following code sample first returns the applicationpool property of the default [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] service application.</span></span> <span data-ttu-id="dd28a-183">Der Name wird in der Zeichenfolge analysiert und verwendet, um den Status des Anwendungspoolobjekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="dd28a-183">The name is parsed from the string and used to get the status of the application pool object.</span></span>
> 
>  <span data-ttu-id="dd28a-184">Überprüfen Sie, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-184">Verify the Status is **Online**.</span></span> <span data-ttu-id="dd28a-185">Wenn der Status nicht online ist oder beim Durchsuchen der Website "http-Fehler" angezeigt wird [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] , überprüfen Sie, ob die Identitäts Anmelde Informationen in den IIS-Anwendungs Pools weiterhin korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="dd28a-185">If the status is not Online or you see "http error" when you browse the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verify the identity credentials in the IIS application pools are still correct.</span></span> <span data-ttu-id="dd28a-186">Der IIS-Poolname entspricht dem Wert der ID-Eigenschaft, die vom Get-SPServiceApplicationPool-Befehl zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dd28a-186">The IIS pool name will is the value of the ID property returned by the Get-SPServiceApplicationPool command.</span></span>

```powershell
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)

Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                           Status ProcessAccountName Id
----                           ------ ------------------ ------- 
SharePoint Web Services System Online DOMAIN\account     89b50ec3-49e3-4de7-881a-2cec4b8b73ea
```

 ![Hinweis](../../../reporting-services/media/rs-fyinote.png "Hinweis:") Der Anwendungs Pool kann auch auf der Seite "zentral Administration" auf der Seite " **Dienst Anwendungen verwalten**" überprüft werden. <span data-ttu-id="dd28a-188">Klicken Sie auf den Namen der Dienstanwendung und dann im Menüband auf **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="dd28a-188">Click the name of the service application and then click **properties** in the ribbon.</span></span>

 <span data-ttu-id="dd28a-189">**PowerPivot und Excel Services-Anwendungsproxys**</span><span class="sxs-lookup"><span data-stu-id="dd28a-189">**PowerPivot and Excel Service Application proxies**</span></span>

 <span data-ttu-id="dd28a-190">Überprüfen Sie, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-190">Verify the Status is **Online**.</span></span>

```powershell
Get-SPServiceApplicationProxy | Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -Like "*powerpivot*" -Or $_.TypeName -Like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                                 Status UnattendedAccount           DisplayName
--------                                                 ------ -----------------           -----------
PowerPivot Service Application Proxy                     Online PowerPivotUnattendedAccount PowerPivotServiceApplication1
Excel Services Application Web Service Application Proxy Online                             Excel Services Application
```

##  <a name="databases"></a><a name="bkmk_databases"></a> <span data-ttu-id="dd28a-191">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="dd28a-191">Databases</span></span>
 <span data-ttu-id="dd28a-192">Das folgende Skript gibt den Status der Dienstanwendungs-Datenbanken und aller Inhaltsdatenbanken zurück.</span><span class="sxs-lookup"><span data-stu-id="dd28a-192">The following script returns the status of the service application databases and all content databases.</span></span> <span data-ttu-id="dd28a-193">Überprüfen Sie, ob der Status **Online**ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-193">Verify the status is **Online**.</span></span>

```powershell
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -Or $_.TypeName -Like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                                                                       Status Server                  TypeName 
----                                                                       ------ ------                  -------- 
DefaultPowerPivotServiceApplicationDB-38422181-2b68-4ab2-b2bb-9c00c39e5a5e Online SPServer Name=TESTSERVER Microsoft.AnalysisServices.SPAddin.GeminiServiceDatabase
DefaultWebApplicationDB-f0db1a8e-4c22-408c-b9b9-153bd74b0312               Online TESTSERVER\POWERPIVOT    Content Database 
SharePoint_Admin_3cadf0b098bf49e0bb15abd487f5c684                          Online TESTSERVER\POWERPIVOT    Content Database
```

##  <a name="sharepoint-features"></a><a name="bkmk_features"></a><span data-ttu-id="dd28a-194">SharePoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="dd28a-194">SharePoint Features</span></span>
 <span data-ttu-id="dd28a-195">Überprüfen Sie, ob die Website-, Web- und Farmfunktionen online sind.</span><span class="sxs-lookup"><span data-stu-id="dd28a-195">Verify the site, web, and farm features are online.</span></span>

```powershell
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
DisplayName     Status Scope Farm                         
-----------     ------ ----- ----                         
PowerPivotSite  Online  Site SPFarm Name=SharePoint_Config
PowerPivotAdmin Online   Web SPFarm Name=SharePoint_Config
PowerPivot      Online  Farm SPFarm Name=SharePoint_Config
```

##  <a name="timer-jobs"></a><a name="bkmk_timer_jobs"></a><span data-ttu-id="dd28a-196">Zeit Geber Aufträge</span><span class="sxs-lookup"><span data-stu-id="dd28a-196">Timer Jobs</span></span>
 <span data-ttu-id="dd28a-197">Überprüfen Sie, ob die Zeitgeberaufträge **Online**sind.</span><span class="sxs-lookup"><span data-stu-id="dd28a-197">Verify the Time Jobs are **Online**.</span></span> <span data-ttu-id="dd28a-198">[!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService wird unter SharePoint 2013 nicht installiert. Folglich werden EngineService-Zeitgeberaufträge in einer SharePoint 2013-Bereitstellung vom Skript nicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="dd28a-198">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService is not installed on SharePoint 2013, therefore the script will not list EngineService timer jobs in a SharePoint 2013 deployment.</span></span>

```powershell
Get-SPTimerJob | Where {$_.service -Like "*power*" -Or $_.service -Like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default
```

```Output
      Status DisplayName                                                                          LastRunTime          Service                             
------ -----------                                                                          -----------          -------                             
Online Health Analysis Job (Daily, SQL Server Analysis Services, All Servers)               4/9/2014 12:00:01 AM EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Hourly, SQL Server Analysis Services, All Servers)              4/9/2014 1:00:01 PM  EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Weekly, SQL Server Analysis Services, All Servers)              4/6/2014 12:00:10 AM EngineService Name=MSOLAP$POWERPIVOT
Online PowerPivot Management Dashboard Processing Timer Job                                 4/8/2014 3:45:38 AM  MidTierService
Online PowerPivot Health Statistics Collector Timer Job                                     4/9/2014 1:00:12 PM  MidTierService
Online PowerPivot Data Refresh Timer Job                                                    4/9/2014 1:09:36 PM  MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, All Servers)  4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, Any Server)   4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, All Servers) 4/6/2014 12:00:03 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, Any Server)  4/6/2014 12:00:03 AM MidTierService
Online PowerPivot Setup Extension Timer Job                                                 4/1/2014 1:40:31 AM  MidTierService
```

##  <a name="health-rules"></a><a name="bkmk_health_rules"></a><span data-ttu-id="dd28a-199">Integritäts Regeln</span><span class="sxs-lookup"><span data-stu-id="dd28a-199">Health Rules</span></span>
 <span data-ttu-id="dd28a-200">Eine SharePoint 2013-Bereitstellung verfügt über weniger Regeln.</span><span class="sxs-lookup"><span data-stu-id="dd28a-200">There are fewer rules in a SharePoint 2013 deployment.</span></span> <span data-ttu-id="dd28a-201">Eine vollständige Liste der Regeln für jede SharePoint-Umgebung und eine Erläuterung zur Verwendung der Regeln finden Sie unter [Power Pivot-Integritäts Regeln-konfigurieren](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-201">For a full list of rules for each SharePoint environment and an explanation of how to use the rules, see [PowerPivot Health Rules - Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span></span>

```powershell
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                          Enabled Summary
----                          ------- -------         
SecondaryLogonHealthRule         True PowerPivot:  Secondary Logon service (seclogon) is disabled
DataRefreshTimerJobHealthRule    True PowerPivot: The PowerPivot Data Refresh timer job is disabled.
ASUsageLoadHealthRule            True PowerPivot: The ratio of load events to connections is too high.
ASMiniDumpHealthRule             True PowerPivot: One or more minidump files were found in the Logs directory, indicating a program crash
ASUsageCubeRule                  True PowerPivot: Usage data is not getting updated at the expected frequency.
ASADOMDNETHealthRule             True PowerPivot: ADOMD.NET is not installed on a standalone WFE that is configured for central admin
MidTierAcctReadPermissionRule    True PowerPivot: MidTier process account should have 'Full Read' permission on all associated SPWebApplications.
```

##  <a name="windows-and-uls-logs"></a><a name="bkmk_logs"></a><span data-ttu-id="dd28a-202">Windows-und ULS-Protokolle</span><span class="sxs-lookup"><span data-stu-id="dd28a-202">Windows and ULS Logs</span></span>
 <span data-ttu-id="dd28a-203">**Windows-Ereignisprotokoll**</span><span class="sxs-lookup"><span data-stu-id="dd28a-203">**Windows event log**</span></span>

 <span data-ttu-id="dd28a-204">Mit dem folgenden Befehl wird das Windows-Ereignisprotokoll nach Ereignissen durchsucht, die sich auf die [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Instanz im SharePoint-Modus beziehen.</span><span class="sxs-lookup"><span data-stu-id="dd28a-204">The following command will search the windows event log for events related to the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="dd28a-205">Weitere Informationen zum Deaktivieren von Ereignissen oder Ändern der Ereignis Ebene finden Sie unter [Konfigurieren und Anzeigen von SharePoint-Protokolldateien und Diagnoseprotokollierung &#40;PowerPivot für SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-205">For information on disabling events or changing the event level, see [Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span></span>

 <span data-ttu-id="dd28a-206">**Dienstname:** MSOLAP$POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="dd28a-206">**Service Name:** MSOLAP$POWERPIVOT</span></span>

 <span data-ttu-id="dd28a-207">**Anzeigename in Windows-Diensten:** SQL Server Analysis Services (POWERPIVOT)</span><span class="sxs-lookup"><span data-stu-id="dd28a-207">**Display name in Windows Services:** SQL Server Analysis Services (POWERPIVOT)</span></span>

```powershell
Get-EventLog "application" | Where-Object {$_.source -Like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -property * -AutoSize | Out-Default
```

```Output
TimeGenerated           EntryType Source            Message
-------------           --------- ------            -------
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Service started. Microsoft SQL Server Analysis Services 64 Bit Evaluation (x64) RTM 12.0.1997.5.
4/16/2014 1:45:18 PM  Information MSOLAP$POWERPIVOT The flight recorder was started.
4/14/2014 6:45:37 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
```

 <span data-ttu-id="dd28a-208">**SharePoint-ULS-Protokoll der letzten 48 Stunden**</span><span class="sxs-lookup"><span data-stu-id="dd28a-208">**SharePoint ULS Log, last 48 hours**</span></span>

 <span data-ttu-id="dd28a-209">Der folgende Befehl gibt [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Meldungen aus dem ULS-Protokoll zurück, die in den letzten 48 Stunden erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="dd28a-209">The following command will return [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] messages from the ULS log that were created in the last 48 hours.</span></span> <span data-ttu-id="dd28a-210">Passen Sie den addhours-Parameter gemäß Ihren Anforderungen an.</span><span class="sxs-lookup"><span data-stu-id="dd28a-210">Adjust the addhours parameter for your need.</span></span>

```powershell
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid,level, message | Format-Table -Property * -AutoSize | Out-Default
```

 <span data-ttu-id="dd28a-211">Die folgende Abwandlung des Befehls gibt nur Protokollereignisse für die Kategorie **Datenaktualisierung** zurück.</span><span class="sxs-lookup"><span data-stu-id="dd28a-211">The following variation of the command only returns log events for the **data refresh** category.</span></span>

```powershell
Get-SPLogEvent -starttime(Get-Date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message
```

```Output
Timestamp   : 4/14/2014 7:15:01 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 43
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : The following error occurred when working with the service application, Default PowerPivot Service Application. Skipping the service application..

Timestamp   : 4/14/2014 7:15:02 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 99
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : EXCEPTION: System.TimeoutException: The request channel timed out while waiting for a reply after 00:00:47.0625313. Increase the timeout value passed to 
              the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout. 
              ---> System.TimeoutException: The HTTP request to 'http://localhost:32843/SecurityTokenServiceApplication/securitytoken.svc/actas' has exceeded the 
              allotted timeout of 00:00:54.5930000. The time allotted to this operation may have been a portion of a longer timeout. ---> System.Net.WebException: The 
              operation has timed out     at System.Net.HttpWebRequest.GetResponse()     at 
              System.ServiceModel.Channels.HttpChannelFactory`1.HttpRequestChannel.HttpChannelRequest.WaitForReply(TimeSpan timeout...
```

##  <a name="msolap-provider"></a><a name="bkmk_msolap"></a><span data-ttu-id="dd28a-212">MSOLAP-Anbieter</span><span class="sxs-lookup"><span data-stu-id="dd28a-212">MSOLAP Provider</span></span>
 <span data-ttu-id="dd28a-213">Überprüfen Sie den MSOLAP-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="dd28a-213">Verify the provider MSOLAP provider.</span></span> [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]<span data-ttu-id="dd28a-214">und [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] erfordern MSOLAP. 5.</span><span class="sxs-lookup"><span data-stu-id="dd28a-214">and [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] require MSOLAP.5.</span></span>

```powershell
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default
```

```Output
ProviderId ProviderType Description
---------- ------------ -----------
MSOLAP     Oledb        Microsoft OLE DB Provider for OLAP Services     
MSOLAP.3   Oledb        Microsoft OLE DB Provider for OLAP Services 9.0 
MSOLAP.4   Oledb        Microsoft OLE DB Provider for OLAP Services 10.0
MSOLAP.5   Oledb        Microsoft OLE DB Provider for OLAP Services 11.0
```

 <span data-ttu-id="dd28a-215">Weitere Informationen finden Sie unter [Installieren des OLE DB-Anbieters für Analysis Services auf SharePoint-Servern](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) und [Hinzufügen von MSOLAP.5 als vertrauenswürdigen Datenanbieter in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span><span class="sxs-lookup"><span data-stu-id="dd28a-215">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) and [Add MSOLAP.5 as a Trusted Data Provider in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span></span>

##  <a name="adomdnet-client-library"></a><a name="bkmk_adomd"></a><span data-ttu-id="dd28a-216">ADOMD.NET-Client Bibliothek</span><span class="sxs-lookup"><span data-stu-id="dd28a-216">ADOMD.Net client Library</span></span>

```powershell
Get-WMIObject -Class win32_product | Where-Object {$_.name -Like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | out-default
```

```Output
name                                                  version      vendor
----                                                  -------      ------
Microsoft SQL Server 2008 Analysis Services ADOMD.NET 10.1.2531.0  Microsoft Corporation
Microsoft SQL Server 2005 Analysis Services ADOMD.NET 9.00.1399.06 Microsoft Corporation
```

 <span data-ttu-id="dd28a-217">Weitere Informationen finden Sie unter [Installieren von ADOMD.NET auf Web-Front-End-Servern, auf denen die Zentraladministration ausgeführt wird](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-217">For more information, see [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>

##  <a name="health-data-collection-rules"></a><a name="bkmk_health_collection"></a><span data-ttu-id="dd28a-218">Regeln zur Sammlung von Integritäts Daten</span><span class="sxs-lookup"><span data-stu-id="dd28a-218">Health Data Collection Rules</span></span>
 <span data-ttu-id="dd28a-219">Überprüfen Sie, ob der **Status** auf Online und **Enabled** auf True festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dd28a-219">Verify the **Status** is Online and **Enabled** is True.</span></span>

```powershell
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -Like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                         Status Enabled TableName                   DaysToKeepDetailedData
----                         ------ ------- ---------                   ----------------------
PowerPivot Connections       OnlineTrue AnalysisServicesConnections  14
PowerPivot Load Data Usage   Online    True AnalysisServicesLoads                           14
PowerPivot Query Usage       Online    True AnalysisServicesRequests                        14
PowerPivot Unload Data Usage Online    True AnalysisServicesUnloads                         14
```

 <span data-ttu-id="dd28a-220">Weitere Informationen finden Sie unter [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-220">For more information, see [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span></span>

##  <a name="solutions"></a><a name="bkmk_solutions"></a><span data-ttu-id="dd28a-221">Lösungen</span><span class="sxs-lookup"><span data-stu-id="dd28a-221">Solutions</span></span>
 <span data-ttu-id="dd28a-222">Wenn die anderen Komponenten online sind, können Sie die Überprüfung der Lösungen überspringen.</span><span class="sxs-lookup"><span data-stu-id="dd28a-222">If the other components are online then you can skip verifying the solutions.</span></span> <span data-ttu-id="dd28a-223">Wenn die Integritätsregeln jedoch fehlen, überprüfen Sie, ob die beiden Lösungen vorhanden sind und angezeigt werden. Überprüfen Sie, ob die beiden PowerPivot-Lösungen den Status **Online** und **Deployed**haben.</span><span class="sxs-lookup"><span data-stu-id="dd28a-223">If however the Health rules are missing, verify the two solutions exist and showed Verify the two PowerPivot solutions are **Online** and **Deployed**.</span></span>

```powershell
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

<span data-ttu-id="dd28a-224">2013 SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="dd28a-224">SharePoint 2013:</span></span>

```Output
Name                                 Status Deployed        DeploymentState DeployedServers
----                                 ------ --------        --------------- ---------------
powerpivotfarm14solution.wsp         Online     True         GlobalDeployed {UETESTA00}
powerpivotfarmsolution.wsp           Online     True         GlobalDeployed {UETESTA00}
powerpivotwebapplicationsolution.wsp Online     True WebApplicationDeployed {UETESTA00}
```

<span data-ttu-id="dd28a-225">SharePoint 2010:</span><span class="sxs-lookup"><span data-stu-id="dd28a-225">SharePoint 2010:</span></span>

```Output
Name                 Status Deployed        DeploymentState DeployedServers 
----                 ------ --------        --------------- --------------- 
powerpivotfarm.wsp   Online     True         GlobalDeployed {uesql11spoint2}
powerpivotwebapp.wsp Online     True WebApplicationDeployed {uesql11spoint2}
```

 <span data-ttu-id="dd28a-226">Weitere Informationen zur Bereitstellung von SharePoint-Lösungen finden Sie unter [Bereitstellen von Lösungspaketen (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span><span class="sxs-lookup"><span data-stu-id="dd28a-226">For more information on how to deploy SharePoint solutions, see [Deploy solution packages (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span></span>

##  <a name="manual-verification-steps"></a><a name="bkmk_manual"></a><span data-ttu-id="dd28a-227">Manuelle Überprüfungs Schritte</span><span class="sxs-lookup"><span data-stu-id="dd28a-227">Manual Verification Steps</span></span>
 <span data-ttu-id="dd28a-228">In diesem Abschnitt werden die Überprüfungsschritte beschrieben, die nicht mithilfe von PowerShell-Cmdlets ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="dd28a-228">This section describes verification steps that cannot be completed with PowerShell cmdlets.</span></span>

 <span data-ttu-id="dd28a-229">**Geplante Datenaktualisierung:** Konfigurieren Sie den Aktualisierungszeitplan einer Arbeitsmappe mit der Option **Außerdem so bald wie möglich aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="dd28a-229">**Scheduled Data Refresh:** Configure the refresh schedule a workbook to **Also refresh as soon as possible**.</span></span>  <span data-ttu-id="dd28a-230">Weitere Informationen finden Sie im Abschnitt "Überprüfen der Datenaktualisierung" unter [Planen der Datenaktualisierung und Datenquellen, die die Windows-Authentifizierung nicht unterstützen &#40;PowerPivot für SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="dd28a-230">For more information, see the "Verify Data Refresh" section of [Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span></span>

##  <a name="more-resources"></a><a name="bkmk_more_resources"></a><span data-ttu-id="dd28a-231">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="dd28a-231">More Resources</span></span>
 <span data-ttu-id="dd28a-232">[Web Server (IIS)-Verwaltungscmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span><span class="sxs-lookup"><span data-stu-id="dd28a-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span></span>

 <span data-ttu-id="dd28a-233">[PowerShell zur Überprüfung von Diensten, IIS-Websites und Anwendungspoolstatus in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span><span class="sxs-lookup"><span data-stu-id="dd28a-233">[PowerShell to check services, IIS sites and Application Pool status in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span></span>

 <span data-ttu-id="dd28a-234">[Referenz zu Windows PowerShell für SharePoint 2013](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dd28a-234">[Windows PowerShell for SharePoint 2013 reference](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span></span>

 <span data-ttu-id="dd28a-235">[Referenz zu Windows PowerShell für SharePoint Foundation 2010](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dd28a-235">[Windows PowerShell for SharePoint Foundation 2010 reference](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span></span>

 <span data-ttu-id="dd28a-236">[Verwalten von Excel Services mit Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dd28a-236">[Manage Excel Services with Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span></span>

 [<span data-ttu-id="dd28a-237">Lesen und Anzeigen der Setupprotokolldateien von SQL Server</span><span class="sxs-lookup"><span data-stu-id="dd28a-237">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)

 [<span data-ttu-id="dd28a-238">Verwenden des Get-EvenLog-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="dd28a-238">Use the Get-EvenLog cmdlet</span></span>](https://technet.microsoft.com/library/ee176846.aspx)

##  <a name="full-powershell-script"></a><a name="bkmk_full_script"></a><span data-ttu-id="dd28a-239">Vollständiges PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="dd28a-239">Full PowerShell Script</span></span>
 <span data-ttu-id="dd28a-240">Das folgende Skript enthält alle in den vorherigen Abschnitten beschriebenen Befehle.</span><span class="sxs-lookup"><span data-stu-id="dd28a-240">The Following script contains all of the commands from the previous sections.</span></span> <span data-ttu-id="dd28a-241">Von dem Skript werden die Befehle in derselben Reihenfolge ausgeführt, in der sie in diesem Thema dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="dd28a-241">The script runs the commands in the same order as they are presented in this topic.</span></span> <span data-ttu-id="dd28a-242">Das Skript enthält einige optionale Varianten der in diesem Thema behandelten Befehle. Diese können verwendet werden, wenn Sie zusätzliche Filter benötigen.</span><span class="sxs-lookup"><span data-stu-id="dd28a-242">The script contains some optional variations of the commands noted in this topic in case you need additional filtering.</span></span> <span data-ttu-id="dd28a-243">Die Varianten sind durch ein Kommentarzeichen (#) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dd28a-243">The variations are disabled with a comment character (#).</span></span> <span data-ttu-id="dd28a-244">Das Skript enthält außerdem einige Anweisungen zur Überprüfung von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] im SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="dd28a-244">The script also includes some statements for verifying [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="dd28a-245">Die [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Anweisungen sind durch ein Kommentarzeichen (#) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dd28a-245">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] statements are disabled with a comment character (#).</span></span>

```powershell
# This script audits services related to PowerPivot for SharePoint
$starttime = Get-Date
write-host -foregroundcolor DarkGray StartTime $starttime

Write-Host  "Import the SharePoint PowerShell snappin"
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0

Write-Host -ForegroundColor Green "Analysis Services Windows Service"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "PowerPivotEngineService and PowerPivotSystemService"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"

Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotSystemService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotEngineService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

#Write-Host -ForegroundColor Green "Service Instances - optional if you want to associate services with the server"
#Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
#Get-SPServiceInstance | select typename, status, server, service, instance | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel*" -or $_.TypeName -like "*Analysis Services*"} | format-table -property * -autosize | out-default
#Get-PowerPivotEngineServiceInstance  | select typename, ASServername, status, server, service, instance
#Get-PowerPivotSystemServiceInstance  | select typename, ASSServerName, status, server, service, instance

Write-Host -ForegroundColor Green "PowerPivot And Excel Service Applications"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename,  DisplayName, status

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot Service Application pool"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
# the following assumes there is only 1 PowerPivot Service Application, and returns that application's pool name.  if you have more than one, use the 2nd version
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)
Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot and Excel Service Application Proxy"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPServiceApplicationProxy |  Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPServiceApplicationProxy |  select typename, status, unattendedaccount, displayname | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*Reporting Services*" -or $_.TypeName -like "*excel services*"} | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "DATABASES"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPDatabase | select name, status, server, typename | where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*" -or $_.TypeName -like "*ReportingServices*"}

Write-Host -ForegroundColor Green "features"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPFeature | select displayname, status, scope, farm | where {$_.displayName -like "*powerpivot*" -or $_.displayName -like "*ReportServer*"}  | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "Timer Jobs (Job Definitions) -- list is the same as seen in the 'Review timer job definitions' section of the management dashboard"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPTimerJob | Where {$_.service -like "*power*" -or $_.service -like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "health rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "Windows Event Log data MSSQL$POWERPIVOT and "
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -Property * -autosize | Out-Default
#The following is the same command but with the Inforamtion events filtered out.
#Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*" -and ($_.entrytype -match "error" -or $_.entrytype -match "critical" -or $_.entrytype -match "warning")}  |select timegenerated, entrytype , source, message | format-table -property * -autosize | out-default

#Write-Host ""
Write-Host -ForegroundColor Green "ULS Log data"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message | Format-Table -Property * -AutoSize | Out-Default
#the following example filters for the category 'data refresh'
#Get-SPLogEvent -starttime(get-date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | select timestamp, area, category, eventid, level, correlation, message

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "MSOLAP data provider for Excel Servivces, service application"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "ADOMD.net client library"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-WMIObject -Class win32_product | Where-Object {$_.name -like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Usage Data Rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Solutions"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time
```
