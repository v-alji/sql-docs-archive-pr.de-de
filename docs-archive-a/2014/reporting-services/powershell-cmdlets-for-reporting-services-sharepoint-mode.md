---
title: PowerShell-Cmdlets für Reporting Services SharePoint-Modus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7835bc97-2827-4215-b0dd-52f692ce5e02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b20ad870fd8a9cd7f220eebb2b954d7a88a10c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726577"
---
# <a name="powershell-cmdlets-for-reporting-services-sharepoint-mode"></a><span data-ttu-id="ea586-102">PowerShell-Cmdlets für SharePoint-Modus von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ea586-102">PowerShell cmdlets for Reporting Services SharePoint Mode</span></span>
  <span data-ttu-id="ea586-103">Wenn Sie [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] den SharePoint-Modus installieren, werden die PowerShell-Cmdlets installiert, um Berichts Server im SharePoint-Modus zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ea586-103">When you install [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode, PowerShell cmdlets are installed to support report Servers in SharePoint mode.</span></span> <span data-ttu-id="ea586-104">Die Cmdlets decken drei Funktionalitätskategorien ab.</span><span class="sxs-lookup"><span data-stu-id="ea586-104">The cmdlets cover three categories of functionality.</span></span>  
  
-   <span data-ttu-id="ea586-105">Installation des gemeinsamen SharePoint-Diensts und -Proxys von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea586-105">Installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service and proxy.</span></span>  
  
-   <span data-ttu-id="ea586-106">Bereitstellung und Verwaltung von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungen und zugeordneten Proxys.</span><span class="sxs-lookup"><span data-stu-id="ea586-106">Provisioning and management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and associated proxies.</span></span>  
  
-   <span data-ttu-id="ea586-107">Verwaltung von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen, z. B. Erweiterungen und Verschlüsselungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="ea586-107">Management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features, for example extensions and encryption keys.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../includes/applies-md.md)]<span data-ttu-id="ea586-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="ea586-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>|  
  
 <span data-ttu-id="ea586-109">**Dieses Thema enthält Folgendes:**</span><span class="sxs-lookup"><span data-stu-id="ea586-109">**This topic contains the following:**</span></span>  
  
-   [<span data-ttu-id="ea586-110">Cmdlet-Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="ea586-110">Cmdlet Summary</span></span>](#bkmk_cmdlet_sum)  
  
-   [<span data-ttu-id="ea586-111">Shared Service-und Proxy-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ea586-111">Shared Service and Proxy Cmdlets</span></span>](#bkmk_sharedservice_cmdlets)  
  
-   [<span data-ttu-id="ea586-112">Dienst Anwendung und Proxy-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ea586-112">Service Application and Proxy Cmdlets</span></span>](#bkmk_serviceapp_cmdlets)  
  
-   [<span data-ttu-id="ea586-113">Cmdlets für die Reporting Services von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="ea586-113">Reporting Services Custom Functionality Cmdlets</span></span>](#bkmk_ssrsfeatures_cmdlets)  
  
-   [<span data-ttu-id="ea586-114">Basisbeispiele</span><span class="sxs-lookup"><span data-stu-id="ea586-114">Basic Samples</span></span>](#bkmk_basic_samples)  
  
-   [<span data-ttu-id="ea586-115">Ausführliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="ea586-115">Detailed Samples</span></span>](#bkmk_detailedsamples)  
  
    -   [<span data-ttu-id="ea586-116">Erstellen einer Reporting Services-Dienst Anwendung und eines Proxys</span><span class="sxs-lookup"><span data-stu-id="ea586-116">Create a Reporting Services service application and proxy</span></span>](#bkmk_example_create_service_application)  
  
    -   [<span data-ttu-id="ea586-117">Überprüfen und Aktualisieren einer Reporting Services-Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="ea586-117">Review and update a Reporting Services delivery extension</span></span>](#bkmk_example_delivery_extension)  
  
    -   [<span data-ttu-id="ea586-118">Abrufen und Festlegen von Eigenschaften der Reporting Services-Anwendungsdatenbank, z. B. Timeout der Datenbank</span><span class="sxs-lookup"><span data-stu-id="ea586-118">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>](#bkmk_example_db_properties)  
  
    -   [<span data-ttu-id="ea586-119">Auflisten von Reporting Services-Daten Erweiterungen: SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="ea586-119">List reporting services data extensions - SharePoint mode</span></span>](#bkmk_example_list_data_extensions)  
  
    -   [<span data-ttu-id="ea586-120">Ändern und Aufführen von Abonnementbesitzern</span><span class="sxs-lookup"><span data-stu-id="ea586-120">Change and list subscription owners</span></span>](#bkmk_change_subscription_owner)  
  
##  <a name="cmdlet-summary"></a><a name="bkmk_cmdlet_sum"></a><span data-ttu-id="ea586-121">Cmdlet-Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="ea586-121">Cmdlet Summary</span></span>  

 <span data-ttu-id="ea586-122">Um die Cmdlets auszuführen, müssen Sie die SharePoint-Verwaltungsshell öffnen.</span><span class="sxs-lookup"><span data-stu-id="ea586-122">To run the cmdlets you need to open the SharePoint Management Shell.</span></span> <span data-ttu-id="ea586-123">Sie können auch den Editor für grafische Benutzeroberflächen **Windows PowerShell Integrated Scripting Environment (ISE)** verwenden, der in Microsoft Windows enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-123">You can also use the graphical user interface editor that is included with Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span></span> <span data-ttu-id="ea586-124">Weitere Informationen finden Sie unter [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell)verwenden, der in Microsoft Windows enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-124">For more information, see [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span></span> <span data-ttu-id="ea586-125">In den folgenden Cmdlet-Zusammenfassungen verweisen die Verweise auf die Dienst Anwendung "Datenbanken" auf alle Datenbanken, die von einer-Dienst Anwendung erstellt und verwendet werden [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea586-125">In the following cmdlet summaries, the references to service application 'databases', refer to all of the databases created and used by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="ea586-126">Dies schließt die Konfigurations- und Warnungsdatenbanken sowie temporären Datenbanken ein.</span><span class="sxs-lookup"><span data-stu-id="ea586-126">This includes the configuration, alerting, and temp databases.</span></span>  

  
 <span data-ttu-id="ea586-127">Wenn Sie bei der Eingabe der PowerShell-Beispiele eine Fehlermeldung mit etwa folgendem Wortlaut sehen:</span><span class="sxs-lookup"><span data-stu-id="ea586-127">If you see an error message similar to the following when you type the PowerShell examples:</span></span>  
  
-   <span data-ttu-id="ea586-128">Install-SPRSService: Die Benennung 'Install-SPRSService' wurde nicht als</span><span class="sxs-lookup"><span data-stu-id="ea586-128">Install-SPRSService : The term 'Install-SPRSService' is not recognized as the</span></span>  
    <span data-ttu-id="ea586-129">Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines ausführbaren Programms erkannt.</span><span class="sxs-lookup"><span data-stu-id="ea586-129">name of a cmdlet, function, script file, or operable program.</span></span> <span data-ttu-id="ea586-130">Prüfen Sie die Schreibweise des Namens bzw. stellen Sie sicher, dass der Pfad korrekt angegeben wurde, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="ea586-130">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>  
  
 <span data-ttu-id="ea586-131">Eines der folgenden Probleme tritt auf:</span><span class="sxs-lookup"><span data-stu-id="ea586-131">One of the following issues is occurring:</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="ea586-132">im SharePoint-Modus ist nicht installiert, und folglich sind auch keine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Cmdlets installiert.</span><span class="sxs-lookup"><span data-stu-id="ea586-132">SharePoint mode is not installed and therefore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets are not installed.</span></span>  
  
-   <span data-ttu-id="ea586-133">Sie haben den PowerShell-Befehl in Windows PowerShell oder Windows PowerShell ISE statt in der SharePoint-Verwaltungsshell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea586-133">You ran the PowerShell command in Windows PowerShell or Windows PowerShell ISE instead of the SharePoint Management Shell.</span></span> <span data-ttu-id="ea586-134">Verwenden Sie die SharePoint-Verwaltungsshell, oder fügen Sie dem Windows PowerShell-Fenster mithilfe des folgenden Befehls das SharePoint-Snap-In hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea586-134">Use the SharePoint Management shell or add the SharePoint Snap-in to the Windows PowerShell window with the following command:</span></span>  
  
    ```powershell
    Add-PSSnapin Microsoft.SharePoint.PowerShell  
    ```  
  
 <span data-ttu-id="ea586-135">Weitere Informationen finden [Sie unter Verwenden von Windows PowerShell zum Verwalten von SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) ( https://technet.microsoft.com/library/ee806878.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ea586-135">For more information see [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) (https://technet.microsoft.com/library/ee806878.aspx).</span></span>  
  
#### <a name="to-open-the-sharepoint-management-shell-and-run-cmdlets"></a><span data-ttu-id="ea586-136">So öffnen Sie die SharePoint-Verwaltungsshell und führen Cmdlets aus</span><span class="sxs-lookup"><span data-stu-id="ea586-136">To Open the SharePoint Management Shell and run cmdlets</span></span>  
  
1.  <span data-ttu-id="ea586-137">Klicken Sie auf die Schaltfläche **Start** .</span><span class="sxs-lookup"><span data-stu-id="ea586-137">Click the **Start** button</span></span>  
  
2.  <span data-ttu-id="ea586-138">Klicken Sie auf die Gruppe **Microsoft SharePoint-Produkte** .</span><span class="sxs-lookup"><span data-stu-id="ea586-138">Click the **Microsoft SharePoint Products** group.</span></span>  
  
3.  <span data-ttu-id="ea586-139">Klicken Sie auf **SharePoint-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ea586-139">Click the **SharePoint Management Shell**.</span></span>  
  
 <span data-ttu-id="ea586-140">Um die Befehlszeilenhilfe für ein Cmdlet anzuzeigen, verwenden Sie in der PowerShell-Eingabeaufforderung den PowerShell-Befehl „Get-Help“.</span><span class="sxs-lookup"><span data-stu-id="ea586-140">To view command line help for a cmdlet use the PowerShell 'Get-Help' command at the PowerShell command prompt.</span></span> <span data-ttu-id="ea586-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea586-141">For example:</span></span>  
  
 `Get-Help Get-SPRSServiceApplicationServers`  
  
###  <a name="shared-service-and-proxy-cmdlets"></a><a name="bkmk_sharedservice_cmdlets"></a> <span data-ttu-id="ea586-142">Shared Service- und Proxy-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ea586-142">Shared Service and Proxy Cmdlets</span></span>  
 <span data-ttu-id="ea586-143">Die folgende Tabelle enthält die PowerShell-Cmdlets für den gemeinsamen SharePoint-Dienst für [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea586-143">The following table contains the PowerShell cmdlets for the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service.</span></span>  
  
|<span data-ttu-id="ea586-144">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea586-144">Cmdlet</span></span>|<span data-ttu-id="ea586-145">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea586-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ea586-146">Install-SPRSService</span><span class="sxs-lookup"><span data-stu-id="ea586-146">Install-SPRSService</span></span>|<span data-ttu-id="ea586-147">Installiert und registriert bzw. deinstalliert den gemeinsamen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="ea586-147">Installs and registers, or uninstalls, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="ea586-148">Dies kann nur auf dem Computer erfolgen, auf dem SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] im SharePoint-Modus installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-148">This can be done only on the machine that has an installation of SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="ea586-149">Für die Installation sind zwei Vorgänge möglich:</span><span class="sxs-lookup"><span data-stu-id="ea586-149">For installation, two operations occur:</span></span><br /><br /> <span data-ttu-id="ea586-150">1) der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Dienst wird in der Farm installiert.</span><span class="sxs-lookup"><span data-stu-id="ea586-150">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is installed in the farm.</span></span><br /><br /> <span data-ttu-id="ea586-151">2) die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Dienst Instanz wird auf dem aktuellen Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ea586-151">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service instance is installed to the current machine.</span></span><br /><br /> <span data-ttu-id="ea586-152">Für die Deinstallation sind zwei Vorgänge möglich:</span><span class="sxs-lookup"><span data-stu-id="ea586-152">For Uninstallation, two operations occur:</span></span><br /><span data-ttu-id="ea586-153">1) der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Dienst wird auf dem aktuellen Computer deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="ea586-153">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the current machine.</span></span><br /><span data-ttu-id="ea586-154">2) der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Dienst wird aus der Farm deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="ea586-154">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the farm.</span></span><br /><br /> <br /><br /> <span data-ttu-id="ea586-155">HINWEIS: Sind weitere Computer in der Farm vorhanden, auf denen der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienst installiert ist, oder werden nach wie vor [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungen in der Farm ausgeführt, wird eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea586-155">NOTE: If there are any other machines in the farm that have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service installed, or if there are still [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications running in the farm, a warning message is displayed.</span></span>|  
|<span data-ttu-id="ea586-156">Install-SPRSServiceProxy</span><span class="sxs-lookup"><span data-stu-id="ea586-156">Install-SPRSServiceProxy</span></span>|<span data-ttu-id="ea586-157">Installiert und registriert bzw. deinstalliert den Reporting Services-Dienstproxy in der SharePoint-Farm.</span><span class="sxs-lookup"><span data-stu-id="ea586-157">Installs and registers, or uninstalls, the Reporting Services service proxy in the SharePoint farm.</span></span>|  
|<span data-ttu-id="ea586-158">Get-SPRSProxyUrl</span><span class="sxs-lookup"><span data-stu-id="ea586-158">Get-SPRSProxyUrl</span></span>|<span data-ttu-id="ea586-159">Ruft die URL(s) für den Zugriff auf den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienst ab.</span><span class="sxs-lookup"><span data-stu-id="ea586-159">Gets the URL(s) for accessing the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="ea586-160">Get-SPRSServiceApplicationServers</span><span class="sxs-lookup"><span data-stu-id="ea586-160">Get-SPRSServiceApplicationServers</span></span>|<span data-ttu-id="ea586-161">Ruft alle Server in der lokalen SharePoint-Farm ab, die eine Installation des gemeinsamen Diensts für [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea586-161">Gets all servers in the local SharePoint farm that contain an installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="ea586-162">Dieses Cmdlet ist hilfreich für [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Upgrades, um die Server zu ermitteln, auf denen der freigegebene Dienst ausgeführt wird und die folglich aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ea586-162">This cmdlet is useful for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] upgrades, to determine which servers run the shared service and therefore need to be upgraded.</span></span>|  
  
###  <a name="service-application-and-proxy-cmdlets"></a><a name="bkmk_serviceapp_cmdlets"></a> <span data-ttu-id="ea586-163">Dienstanwendungs- und Proxy-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ea586-163">Service Application and Proxy Cmdlets</span></span>  
 <span data-ttu-id="ea586-164">Die folgende Tabelle enthält die PowerShell-Cmdlets für [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungen und ihre zugeordneten Proxys.</span><span class="sxs-lookup"><span data-stu-id="ea586-164">The following table contains the PowerShell cmdlets for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and their associated proxies.</span></span>  
  
|<span data-ttu-id="ea586-165">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea586-165">cmdlet</span></span>|<span data-ttu-id="ea586-166">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea586-166">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ea586-167">Get-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="ea586-167">Get-SPRSServiceApplication</span></span>|<span data-ttu-id="ea586-168">Ruft mindestens ein [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungsobjekt ab.</span><span class="sxs-lookup"><span data-stu-id="ea586-168">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application objects.</span></span>|  
|<span data-ttu-id="ea586-169">New-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="ea586-169">New-SPRSServiceApplication</span></span>|<span data-ttu-id="ea586-170">Erstellen Sie eine neue Reporting Services-Dienstanwendung und zugeordnete Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ea586-170">Create a new Reporting Services service application and associated databases.</span></span><br /><br /> <span data-ttu-id="ea586-171">LogonType-Parameter: Gibt an, ob der Berichtsserver das SSRS-Anwendungspoolkonto oder einen SQL Server-Anmeldenamen für den Zugriff auf die Berichtsserver-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea586-171">LogonType Parameter: Specifies if the report server uses the SSRS Application Pool account or a SQL Server login to access the report server database.</span></span> <span data-ttu-id="ea586-172">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="ea586-172">It can be one of the following:</span></span><br /><br /> <span data-ttu-id="ea586-173">0 Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ea586-173">0 Windows Authentication</span></span><br /><br /> <span data-ttu-id="ea586-174">1 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea586-174">1 SQL Server</span></span><br /><br /> <span data-ttu-id="ea586-175">2 Anwendungspoolkonto (Standard)</span><span class="sxs-lookup"><span data-stu-id="ea586-175">2 Application Pool Account (default)</span></span>|  
|<span data-ttu-id="ea586-176">Remove-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="ea586-176">Remove-SPRSServiceApplication</span></span>|<span data-ttu-id="ea586-177">Entfernt die angegebene Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-177">Removes the specified Reporting Services service application.</span></span> <span data-ttu-id="ea586-178">Dadurch werden auch die zugeordneten Datenbanken entfernt.</span><span class="sxs-lookup"><span data-stu-id="ea586-178">This will also remove the associated databases.</span></span>|  
|<span data-ttu-id="ea586-179">Set-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="ea586-179">Set-SPRSServiceApplication</span></span>|<span data-ttu-id="ea586-180">Bearbeitet die Eigenschaften einer vorhandenen Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-180">Edits the properties of an existing Reporting Services service application.</span></span>|  
|<span data-ttu-id="ea586-181">New-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="ea586-181">New-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="ea586-182">Erstellt einen neuen Proxy für die Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-182">Creates a new Reporting Services service application proxy.</span></span>|  
|<span data-ttu-id="ea586-183">Get-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="ea586-183">Get-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="ea586-184">Ruft mindestens einen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungsproxy ab.</span><span class="sxs-lookup"><span data-stu-id="ea586-184">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application proxies.</span></span>|  
|<span data-ttu-id="ea586-185">Dismount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="ea586-185">Dismount-SPRSDatabase</span></span>|<span data-ttu-id="ea586-186">Hebt die Einbindung der Dienstanwendungsdatenbank für eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung auf.</span><span class="sxs-lookup"><span data-stu-id="ea586-186">Dismounts the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="ea586-187">Remove-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="ea586-187">Remove-SPRSDatabase</span></span>|<span data-ttu-id="ea586-188">Entfernen Sie die Dienstanwendungsdatenbanken für eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-188">Remove the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="ea586-189">Set-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="ea586-189">Set-SPRSDatabase</span></span>|<span data-ttu-id="ea586-190">Legt die Eigenschaften der einer [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung zugeordneten Datenbanken fest.</span><span class="sxs-lookup"><span data-stu-id="ea586-190">Sets the properties of the databases associated to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="ea586-191">Mount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="ea586-191">Mount-SPRSDatabase</span></span>|<span data-ttu-id="ea586-192">Bindet Datenbanken für eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="ea586-192">Mounts databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="ea586-193">New-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="ea586-193">New-SPRSDatabase</span></span>|<span data-ttu-id="ea586-194">Erstellen Sie neue Dienstanwendungsdatenbanken für die angegebene [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-194">Create new service application databases for the specified [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="ea586-195">Get-SPRSDatabaseCreationScript</span><span class="sxs-lookup"><span data-stu-id="ea586-195">Get-SPRSDatabaseCreationScript</span></span>|<span data-ttu-id="ea586-196">Gibt für eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung das Datenbankerstellungsskript auf dem Bildschirm aus.</span><span class="sxs-lookup"><span data-stu-id="ea586-196">Outputs the database creation script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="ea586-197">Sie können dann das Skript in SQL Server Management Studio ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea586-197">You can then run the script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="ea586-198">Get-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="ea586-198">Get-SPRSDatabase</span></span>|<span data-ttu-id="ea586-199">Ruft mindestens eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungsdatenbank ab.</span><span class="sxs-lookup"><span data-stu-id="ea586-199">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases.</span></span> <span data-ttu-id="ea586-200">Rufen Sie über den Befehl die ID der Dienstanwendungsdatenbank ab, damit Sie anhand des Set-SPRSDatabase-Cmdlets Eigenschaften ändern können, beispielsweise das `querytimeout`.</span><span class="sxs-lookup"><span data-stu-id="ea586-200">Use the command to get the ID of service application database so you can use the Set-SPRSDatabase comdlet to modify properties, for example the `querytimeout`.</span></span> <span data-ttu-id="ea586-201">Sehen Sie sich das Beispiel unter dem Thema [Abrufen und Festlegen von Eigenschaften der Reporting Services-Anwendungsdatenbank, z. B. Timeout der Datenbank](#bkmk_example_db_properties).</span><span class="sxs-lookup"><span data-stu-id="ea586-201">See the example in this topic, [Get and set properties of the Reporting Servicea application database, for example database timeout](#bkmk_example_db_properties).</span></span>|  
|<span data-ttu-id="ea586-202">Get-SPRSDatabaseRightsScript</span><span class="sxs-lookup"><span data-stu-id="ea586-202">Get-SPRSDatabaseRightsScript</span></span>|<span data-ttu-id="ea586-203">Gibt für eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung das Skript für Datenbankrechte auf dem Bildschirm aus.</span><span class="sxs-lookup"><span data-stu-id="ea586-203">Outputs the database rights script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="ea586-204">Es fordert die Eingabe des gewünschten Benutzers und der Datenbank und gibt dann Transact-SQL zurück, das zum Ändern von Berechtigungen ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea586-204">It will prompt for desired user and database then returns transact SQL you can run to modify permissions.</span></span> <span data-ttu-id="ea586-205">Sie können dann dieses Skript in SQL Server Management Studio ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea586-205">You can then run this script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="ea586-206">Get-SPRSDatabaseUpgradeScript</span><span class="sxs-lookup"><span data-stu-id="ea586-206">Get-SPRSDatabaseUpgradeScript</span></span>|<span data-ttu-id="ea586-207">Gibt ein Datenbankupgradeskript auf dem Bildschirm aus.</span><span class="sxs-lookup"><span data-stu-id="ea586-207">Outputs a database upgrade script to the screen.</span></span> <span data-ttu-id="ea586-208">Das Skript führt ein Upgrade der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungsdatenbanken auf die Datenbankversion der aktuellen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Installation durch.</span><span class="sxs-lookup"><span data-stu-id="ea586-208">The script will upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases to the database version of the current [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installation.</span></span>|  
  
###  <a name="reporting-services-custom-functionality-cmdlets"></a><a name="bkmk_ssrsfeatures_cmdlets"></a><span data-ttu-id="ea586-209">Cmdlets für die Reporting Services von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="ea586-209">Reporting Services Custom Functionality Cmdlets</span></span>  
  
|<span data-ttu-id="ea586-210">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea586-210">Cmdlet</span></span>|<span data-ttu-id="ea586-211">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea586-211">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ea586-212">Update-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="ea586-212">Update-SPRSEncryptionKey</span></span>|<span data-ttu-id="ea586-213">Aktualisiert den Verschlüsselungsschlüssel für die angegebene Reporting Services-Dienstanwendung und verschlüsselt die Daten erneut.</span><span class="sxs-lookup"><span data-stu-id="ea586-213">Updates the encryption key for the specified Reporting Services service application and re-encrypts its data.</span></span>|  
|<span data-ttu-id="ea586-214">Restore-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="ea586-214">Restore-SPRSEncryptionKey</span></span>|<span data-ttu-id="ea586-215">Stellt einen zuvor gesicherten Verschlüsselungsschlüssel für eine Reporting Services-Dienstanwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ea586-215">Restores a previously backed up encryption key for a Reporting Services service application.</span></span>|  
|<span data-ttu-id="ea586-216">Remove-SPRSEncryptedData</span><span class="sxs-lookup"><span data-stu-id="ea586-216">Remove-SPRSEncryptedData</span></span>|<span data-ttu-id="ea586-217">Löscht die verschlüsselten Daten für die angegebene Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-217">Delete the encrypted data for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="ea586-218">Backup-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="ea586-218">Backup-SPRSEncryptionKey</span></span>|<span data-ttu-id="ea586-219">Sichert den Verschlüsselungsschlüssel für die angegebene Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-219">Backs up the encryption key for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="ea586-220">New-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="ea586-220">New-SPRSExtension</span></span>|<span data-ttu-id="ea586-221">Registriert eine neue Erweiterung bei einer Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-221">Registers a new extension with a Reporting Services service application.</span></span>|  
|<span data-ttu-id="ea586-222">Set-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="ea586-222">Set-SPRSExtension</span></span>|<span data-ttu-id="ea586-223">Legt die Eigenschaften einer vorhandenen Reporting Services-Erweiterung fest.</span><span class="sxs-lookup"><span data-stu-id="ea586-223">Sets the properties of an existing Reporting Services extension.</span></span>|  
|<span data-ttu-id="ea586-224">Remove-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="ea586-224">Remove-SPRSExtension</span></span>|<span data-ttu-id="ea586-225">Entfernt eine Erweiterung aus einer Reporting Services-Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="ea586-225">Removes an extension from a Reporting Services service application.</span></span>|  
|<span data-ttu-id="ea586-226">Get-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="ea586-226">Get-SPRSExtension</span></span>|<span data-ttu-id="ea586-227">Ruft mindestens eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Erweiterung für eine [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung ab.</span><span class="sxs-lookup"><span data-stu-id="ea586-227">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensions for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span><br /><br /> <span data-ttu-id="ea586-228">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ea586-228">Valid values are:</span></span><br /><br /> <span data-ttu-id="ea586-229">**Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="ea586-229">**Delivery**</span></span><br /><br /> <span data-ttu-id="ea586-230">**DeliveryUI**</span><span class="sxs-lookup"><span data-stu-id="ea586-230">**DeliveryUI**</span></span><br /><br /> <span data-ttu-id="ea586-231">**Rendern**</span><span class="sxs-lookup"><span data-stu-id="ea586-231">**Render**</span></span><br /><br /> <span data-ttu-id="ea586-232">**Daten**</span><span class="sxs-lookup"><span data-stu-id="ea586-232">**Data**</span></span><br /><br /> <span data-ttu-id="ea586-233">**Security**</span><span class="sxs-lookup"><span data-stu-id="ea586-233">**Security**</span></span><br /><br /> <span data-ttu-id="ea586-234">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="ea586-234">**Authentication**</span></span><br /><br /> <span data-ttu-id="ea586-235">**EventProcessing**</span><span class="sxs-lookup"><span data-stu-id="ea586-235">**EventProcessing**</span></span><br /><br /> <span data-ttu-id="ea586-236">**Berichtselemente**</span><span class="sxs-lookup"><span data-stu-id="ea586-236">**ReportItems**</span></span><br /><br /> <span data-ttu-id="ea586-237">**Designer**</span><span class="sxs-lookup"><span data-stu-id="ea586-237">**Designer**</span></span><br /><br /> <span data-ttu-id="ea586-238">**ReportItemDesigner**</span><span class="sxs-lookup"><span data-stu-id="ea586-238">**ReportItemDesigner**</span></span><br /><br /> <span data-ttu-id="ea586-239">**ReportItemConverter**</span><span class="sxs-lookup"><span data-stu-id="ea586-239">**ReportItemConverter**</span></span><br /><br /> <span data-ttu-id="ea586-240">**ReportDefinitionCustomization**</span><span class="sxs-lookup"><span data-stu-id="ea586-240">**ReportDefinitionCustomization**</span></span>|  
|<span data-ttu-id="ea586-241">Get-SPRSSite</span><span class="sxs-lookup"><span data-stu-id="ea586-241">Get-SPRSSite</span></span>|<span data-ttu-id="ea586-242">Ruft die SharePoint-Websites abhängig davon ab, ob die Funktion "ReportingService" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-242">Gets the SharePoint sites based on whether the "ReportingService" feature is enabled.</span></span> <span data-ttu-id="ea586-243">Standardmäßig werden Websites zurückgegeben, für die die Funktion "ReportingService" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-243">By default, sites that enable the "ReportingService" feature are returned.</span></span>|  
  
##  <a name="basic-samples"></a><a name="bkmk_basic_samples"></a><span data-ttu-id="ea586-244">Grundlegende Beispiele</span><span class="sxs-lookup"><span data-stu-id="ea586-244">Basic Samples</span></span>  
 <span data-ttu-id="ea586-245">Gibt eine Liste von Cmdlets zurück, die „SPRS“ im Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea586-245">Return a list of cmdlets that contain 'SPRS' in the name.</span></span> <span data-ttu-id="ea586-246">Dies entspricht der vollständigen Liste mit [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ea586-246">This will be the full list of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets.</span></span>  
  
```powershell
Get-command -noun *SPRS*  
```  
  
 <span data-ttu-id="ea586-247">Alternativ erfolgt die Weiterleitung an eine Textdatei namens "commandlist.txt" mit genaueren Details.</span><span class="sxs-lookup"><span data-stu-id="ea586-247">Or with a little more detail, piped to a text file named commandlist.txt</span></span>  
  
```powershell
Get-Command -Noun *SPRS* | Select name, definition | Format-List | Out-File c:\commandlist.txt  
```  
  
 <span data-ttu-id="ea586-248">Installieren Sie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint-Dienst und -Dienstproxy.</span><span class="sxs-lookup"><span data-stu-id="ea586-248">Install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint service and service proxy.</span></span>  
  
```powershell
Install-SPRSService  
```  
  
```powershell
Install-SPRSServiceProxy  
```  
  
 <span data-ttu-id="ea586-249">Starten Sie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="ea586-249">Start the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service</span></span>  
  
```powershell
Get-SPServiceInstance -all | where {$_.TypeName -like "SQL Server Reporting*"} | Start-SPServiceInstance  
```  
  
 <span data-ttu-id="ea586-250">Geben Sie den folgenden Befehl in der SharePoint-Verwaltungsshell ein, um eine gefilterte Zeilenliste aus der Protokolldatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ea586-250">Type the following command from the SharePoint Management Shell to return a filtered list of rows from the a log file.</span></span> <span data-ttu-id="ea586-251">Durch den Befehl werden Zeilen herausgefiltert, die „ssrscustomactionerror“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea586-251">The command will filter for lines that contain "ssrscustomactionerror".</span></span> <span data-ttu-id="ea586-252">Dieses Beispiel bezieht sich auf die Protokolldatei, die bei der Installation von "rssharepoint.msi" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ea586-252">This example is looking at the log file created when the rssharepoint.msi was installed.</span></span>  
  
```powershell
Get-Content -Path C:\Users\testuser\AppData\Local\Temp\rs_sp_0.log | Select-String "ssrscustomactionerror"  
```  
  
##  <a name="detailed-samples"></a><a name="bkmk_detailedsamples"></a><span data-ttu-id="ea586-253">Ausführliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="ea586-253">Detailed Samples</span></span>  
 <span data-ttu-id="ea586-254">Zusätzlich zu den folgenden Beispielen finden Sie weitere Informationen im Abschnitt "Windows PowerShell-Skript" im Thema [Windows PowerShell-Skript für die Schritte 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span><span class="sxs-lookup"><span data-stu-id="ea586-254">In addition to the following samples, see the section "Windows PowerShell Script" in the topic [Windows PowerShell script for Steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span></span>  
  
###  <a name="create-a-reporting-services-service-application-and-proxy"></a><a name="bkmk_example_create_service_application"></a><span data-ttu-id="ea586-255">Erstellen einer Reporting Services-Dienst Anwendung und eines Proxys</span><span class="sxs-lookup"><span data-stu-id="ea586-255">Create a Reporting Services service application and proxy</span></span>  
 <span data-ttu-id="ea586-256">Dieses Beispielskript führt die folgenden Tasks aus:</span><span class="sxs-lookup"><span data-stu-id="ea586-256">This sample script completes the following tasks:</span></span>  
  
1.  <span data-ttu-id="ea586-257">Erstellt eine Reporting Services-Dienstanwendung und einen entsprechenden Proxy.</span><span class="sxs-lookup"><span data-stu-id="ea586-257">Create a Reporting Services service application and proxy.</span></span> <span data-ttu-id="ea586-258">Das Skript geht davon aus, dass der Anwendungspool „Mein Anwendungspool“ bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-258">The script assumes the application pool "My App Pool" already exists.</span></span>  
  
2.  <span data-ttu-id="ea586-259">Hinzufügen des Proxys zur Standardproxygruppe</span><span class="sxs-lookup"><span data-stu-id="ea586-259">Add the proxy to the default proxy group</span></span>  
  
3.  <span data-ttu-id="ea586-260">Gewähren Sie der Dienstanwendung Zugriff auf die Inhaltsdatenbank der Webanwendung (Port 80).</span><span class="sxs-lookup"><span data-stu-id="ea586-260">Grant the service app access to the port 80 web app's content database.</span></span> <span data-ttu-id="ea586-261">Das Skript setzt voraus, dass die Website " http://sitename " bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ea586-261">The script assumes site "http://sitename" already exists.</span></span>  
  
```powershell
# Create service application and service application proxy  
$appPool = Get-SPServiceApplicationPool "My App Pool"  
$serviceApp = New-SPRSServiceApplication "My RS Service App" -ApplicationPool $appPool  
$serviceAppProxy = New-SPRSServiceApplicationProxy -Name "My RS Service App Proxy" -ServiceApplication $serviceApp  
  
# Add service application proxy to default proxy group.  Any web application that uses the default proxy group will now be able to use this service application.  
Get-SPServiceApplicationProxyGroup -default | Add-SPServiceApplicationProxyGroupMember -Member $serviceAppProxy  
  
# Grant application pool account access to the port 80 web application's content database.  
$webApp = Get-SPWebApplication "http://sitename"  
$appPoolAccountName = $appPool.ProcessAccount.LookupName()  
$webApp.GrantAccessToProcessIdentity($appPoolAccountName)
```  
  
###  <a name="review-and-update-a-reporting-services-delivery-extension"></a><a name="bkmk_example_delivery_extension"></a><span data-ttu-id="ea586-262">Überprüfen und Aktualisieren einer Reporting Services Übermittlungs Erweiterung</span><span class="sxs-lookup"><span data-stu-id="ea586-262">Review and update a Reporting Services delivery extension</span></span>  
 <span data-ttu-id="ea586-263">Das folgende PowerShell-Skript-Beispiel aktualisiert die Konfiguration der Berichtsserver-E-Mail-Übermittlungserweiterung für die Dienstanwendung mit dem Namen `My RS Service App`.</span><span class="sxs-lookup"><span data-stu-id="ea586-263">The following PowerShell script example, updates the configuration for the report server e-mail delivery extension for the service application named `My RS Service App`.</span></span> <span data-ttu-id="ea586-264">Aktualisieren Sie die Werte für den SMTP-Server (`<email server name>`) und für den E-Mail-Absenderalias „FROM“ (`<your FROM email address>`).</span><span class="sxs-lookup"><span data-stu-id="ea586-264">Update the values for the SMTP server (`<email server name>`) and the FROM email alias (`<your FROM email address>`).</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication -Name "My RS Service App"  
$emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
$emailXml = [xml]$emailCfg
$emailXml.SelectSingleNode("//SMTPServer").InnerText = "<email server name>"  
$emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
$emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
$emailXml.SelectSingleNode("//From").InnerText = '<your FROM email address>'  
Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
```  
  
 <span data-ttu-id="ea586-265">Wenn Sie im oben genannten Beispiel den genauen Namen der Dienstanwendung nicht kennen, besteht die Möglichkeit, die erste Anweisung umzuschreiben, um die Dienstanwendung auf Grundlage einer Suche nach dem Teilnamen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ea586-265">In the above example if you did not know the exact name of the service application, you could rewrite the first statement to get the service application based on a search of the partial name.</span></span> <span data-ttu-id="ea586-266">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea586-266">For example:</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication | Where {$_.name -like " ssrs_testapp *"}  
```  
  
 <span data-ttu-id="ea586-267">Das folgende Skript gibt die aktuellen Konfigurationswerte für die Berichtsserver-E-Mail-Übermittlungserweiterung der Dienstanwendung namens „Reporting Services-Anwendung“ zurück.</span><span class="sxs-lookup"><span data-stu-id="ea586-267">The following script will return the current configuration values for the report server e-mail delivery extension for the service application named "Reporting Services Application".</span></span> <span data-ttu-id="ea586-268">Im ersten Schritt wird der Wert der Variablen $app auf das Objekt der Dienstanwendung mit dem Namen "Meine RS-Dienstanwendung" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ea586-268">The first step sets the value of the variable $app to the object of the service application that has a name of " My RS Service App "</span></span>  
  
 <span data-ttu-id="ea586-269">Die zweite Anweisung ruft die Übermittlungserweiterung „Berichtsserver-E-Mail“ für das Dienstanwendungsobjekt in der Variablen $app ab und wählt configurationXML aus.</span><span class="sxs-lookup"><span data-stu-id="ea586-269">The second statement will Get the 'Report Server Email' delivery extension for the service application object in variable $app, and select the configurationXML</span></span>  
  
```powershell
$app = Get-SPRSServiceapplication -Name "Reporting Services Application"  
Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
 <span data-ttu-id="ea586-270">Sie können die beiden oben stehenden Anweisungen auch in einer Anweisung zusammenfassen:</span><span class="sxs-lookup"><span data-stu-id="ea586-270">You can also rewrite the above two statements as one:</span></span>  
  
```powershell
Get-SPRSServiceApplication -Name "Reporting Services Application" | Get-SPRSExtension -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
###  <a name="get-and-set-properties-of-the-reporting-servicea-application-database-for-example-database-timeout"></a><a name="bkmk_example_db_properties"></a><span data-ttu-id="ea586-271">Eigenschaften der Reporting ServiceA-Anwendungsdatenbank, z. b. Timeout der Datenbank, erhalten und festlegen</span><span class="sxs-lookup"><span data-stu-id="ea586-271">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>  
 <span data-ttu-id="ea586-272">Mit dem folgenden Beispiel wird eine Liste von Datenbanken und Eigenschaften zurückgegeben, sodass Sie die Datenbank-GUID (ID) bestimmen können, die Sie anschließend zum Festlegen des Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="ea586-272">The following example first returns a list of the databases and properties so you can determine the database guid (ID) that you then supply to the set command.</span></span> <span data-ttu-id="ea586-273">Eine vollständige Liste der Eigenschaften erhalten Sie anhand von `Get-SPRSDatabase | format-list`.</span><span class="sxs-lookup"><span data-stu-id="ea586-273">For a full list of the properties, use `Get-SPRSDatabase | format-list`.</span></span>  
  
```powershell
Get-SPRSDatabase | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance
```  
  
 <span data-ttu-id="ea586-274">Unten ist ein Beispiel für die Ausgabe angegeben.</span><span class="sxs-lookup"><span data-stu-id="ea586-274">The following is an example of the output.</span></span> <span data-ttu-id="ea586-275">Bestimmen Sie die ID für die zu ändernde Datenbank und verwenden Sie die ID im SET-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea586-275">Determine the ID for the database you want to modify and use the ID in the SET cmdlet.</span></span>  
  
-   `Id                : 56f8d1bc-cb04-44cf-bd41-a873643c5a14`  
  
     `QueryTimeout      : 120`  
  
     `ConnectionTimeout : 15`  
  
     `Status            : Online`  
  
     `Server            : SPServer Name=uetestb01`  
  
     `ServiceInstance   : SPDatabaseServiceInstance`  
  
```powershell
Set-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 -QueryTimeout 300  
```  
  
 <span data-ttu-id="ea586-276">Um zu überprüfen, ob der Wert festgelegt ist, führen Sie das GET-Cmdlet erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ea586-276">To verify the value is set, run the GET cmdlet again.</span></span>  
  
```powershell
Get-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance  
```  
  
###  <a name="list-reporting-services-data-extensions---sharepoint-mode"></a><a name="bkmk_example_list_data_extensions"></a><span data-ttu-id="ea586-277">Auflisten von Reporting Services-Daten Erweiterungen: SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="ea586-277">List reporting services data extensions - SharePoint mode</span></span>  
 <span data-ttu-id="ea586-278">Das folgende Beispiel durchläuft alle [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungen und listet aktuelle Datenerweiterungen für diese auf.</span><span class="sxs-lookup"><span data-stu-id="ea586-278">The following example loops through each [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application and lists the current data extensions for each.</span></span>  
  
```powershell
$apps = Get-SPRSServiceApplication  
foreach ($app in $apps)
{  
Write-host -ForegroundColor "yellow" Service App Name $app.Name  
Get-SPRSExtension -identity $app -ExtensionType "Data" | select name, extensiontype | Format-Table -AutoSize  
}  
```  
  
 <span data-ttu-id="ea586-279">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="ea586-279">**Example output:**</span></span>  
  
-   `Name           ExtensionType`  
  
     `----           -------------`  
  
     `SQL                     Data`  
  
     `SQLAZURE                Data`  
  
     `SQLPDW                  Data`  
  
     `OLEDB                   Data`  
  
     `OLEDB-MD                Data`  
  
     `ORACLE                  Data`  
  
     `ODBC                    Data`  
  
     `XML                     Data`  
  
     `SHAREPOINTLIST          Data`  
  
###  <a name="change-and-list-subscription-owners"></a><a name="bkmk_change_subscription_owner"></a><span data-ttu-id="ea586-280">Ändern und Auflisten von Abonnement Besitzern</span><span class="sxs-lookup"><span data-stu-id="ea586-280">Change and list subscription owners</span></span>  
 <span data-ttu-id="ea586-281">Siehe [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ea586-281">See [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea586-282">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea586-282">See Also</span></span>  
 <span data-ttu-id="ea586-283">[Verwenden von PowerShell zum Ändern und auflisten Reporting Services Abonnement Besitzern und Ausführen eines Abonnements](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="ea586-283">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span></span>  
 <span data-ttu-id="ea586-284">[Prüfliste: Verwenden von PowerShell zum Überprüfen PowerPivot für SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span><span class="sxs-lookup"><span data-stu-id="ea586-284">[CheckList: Use PowerShell to Verify PowerPivot for SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span></span>  
 [<span data-ttu-id="ea586-285">CodePlex-SharePoint-Verwaltungs-PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="ea586-285">CodePlex SharePoint Management PowerShell scripts</span></span>](https://sharepointpsscripts.codeplex.com/)   
