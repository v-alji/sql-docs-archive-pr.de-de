---
title: Verwenden von PowerShell zum Ändern und auflisten Reporting Services Abonnement Besitzern und Ausführen eines Abonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0fa6cb36-68fc-4fb8-b1dc-ae4f12bf6ff0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b274dc190d8830a2cf7b55110f15267a00c581e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618466"
---
# <a name="use-powershell-to-change-and-list-reporting-services-subscription-owners-and-run-a-subscription"></a><span data-ttu-id="6d854-102">Verwenden von PowerShell, um Reporting Services-Abonnenten zu ändern und aufzulisten sowie ein Abonnement auszuführen</span><span class="sxs-lookup"><span data-stu-id="6d854-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span></span>
  <span data-ttu-id="6d854-103">Beginnend mit [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] können Sie den Besitz eines [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Abonnements programmgesteuert von einem Benutzer auf einen anderen übertragen.</span><span class="sxs-lookup"><span data-stu-id="6d854-103">Starting with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] you can programmatically transfer the ownership of a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription from one user to another.</span></span> <span data-ttu-id="6d854-104">Dieses Thema enthält mehrere Windows PowerShell-Skripts, die Sie verwenden können, um den Besitz von Abonnements zu ändern oder einfach aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="6d854-104">This topic provides several Windows PowerShell scripts you can use to change or simply list subscription ownership.</span></span> <span data-ttu-id="6d854-105">Jedes Beispiel enthält Beispielsyntax sowohl für den einheitlichen als auch den SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="6d854-105">Each sample includes sample syntax for both Native mode and SharePoint mode.</span></span> <span data-ttu-id="6d854-106">Wenn Sie den Abonnementbesitzer ändern, wird das Abonnement dann im Sicherheitskontext des neuen Besitzers ausgeführt, und das User!UserID-Feld des Berichts zeigt den Wert für den neuen Besitzer an.</span><span class="sxs-lookup"><span data-stu-id="6d854-106">After you change the subscription owner, the subscription will then execute in the security context of the new owner, and the User!UserID field in the report will display the value of new owner.</span></span> <span data-ttu-id="6d854-107">Weitere Informationen zum Objektmodell des PowerShell-Beispielaufrufs finden Sie unter <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="6d854-107">For more information on the object model the PowerShell samples call, see <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span>

 <span data-ttu-id="6d854-108">![PowerShell-Inhalt](../media/rs-powershellicon.jpg "PowerShell-Inhalt")</span><span class="sxs-lookup"><span data-stu-id="6d854-108">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

||
|-|
|<span data-ttu-id="6d854-109">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] im einheitlichen Modus &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="6d854-110">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="6d854-110">**In this topic:**</span></span>

-   [<span data-ttu-id="6d854-111">Gewusst wie: Verwenden der Skripts</span><span class="sxs-lookup"><span data-stu-id="6d854-111">How to use the scripts</span></span>](#bkmk_how_to)

-   [<span data-ttu-id="6d854-112">Skript: Auflisten der Besitzer aller Abonnements</span><span class="sxs-lookup"><span data-stu-id="6d854-112">Script: List the ownership of all subscriptions</span></span>](#bkmk_list_ownership_all)

-   [<span data-ttu-id="6d854-113">Skript: Auflisten aller Abonnements im Besitz eines spezifischen Benutzers</span><span class="sxs-lookup"><span data-stu-id="6d854-113">Script: List all subscriptions owned by a specific user</span></span>](#bkmk_list_all_one_user)

-   [<span data-ttu-id="6d854-114">Skript: Ändern des Besitzes aller Abonnements eines spezifischen Benutzers</span><span class="sxs-lookup"><span data-stu-id="6d854-114">Script: Change ownership for all subscriptions owned by a specific user</span></span>](#bkmk_change_all)

-   [<span data-ttu-id="6d854-115">Skript: Auflisten aller Abonnements im Zusammenhang mit einem bestimmten Bericht</span><span class="sxs-lookup"><span data-stu-id="6d854-115">Script: List all subscriptions associated with a specific report</span></span>](#bkmk_list_for_1_report)

-   [<span data-ttu-id="6d854-116">Skript: Ändern des Besitzes eines bestimmten Abonnements</span><span class="sxs-lookup"><span data-stu-id="6d854-116">Script: Change ownership of a specific subscription</span></span>](#bkmk_change_all_1_subscription)

-   [<span data-ttu-id="6d854-117">Skript: Ausführen (Auslösen) eines Einzelabonnements</span><span class="sxs-lookup"><span data-stu-id="6d854-117">Script: Run (fire) a single subscription</span></span>](#bkmk_run_1_subscription)

##  <a name="how-to-use-the-scripts"></a><a name="bkmk_how_to"></a> <span data-ttu-id="6d854-118">Gewusst wie: Verwenden der Skripts</span><span class="sxs-lookup"><span data-stu-id="6d854-118">How to use the scripts</span></span>

### <a name="permissions"></a><span data-ttu-id="6d854-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6d854-119">Permissions</span></span>
 <span data-ttu-id="6d854-120">In diesem Abschnitt werden die erforderlichen Berechtigungsstufen für die Verwendung der Methoden für den einheitlichen und den SharePoint-Modus [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6d854-120">This section summarizes the permission levels required to use each of the methods for both Native and SharePoint mode [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="6d854-121">Die Skripts in diesem Thema verwenden die folgenden [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Methoden:</span><span class="sxs-lookup"><span data-stu-id="6d854-121">The scripts in this topic use the following [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] methods:</span></span>

-   [<span data-ttu-id="6d854-122">ReportingService2010.ListSubscriptions Method</span><span class="sxs-lookup"><span data-stu-id="6d854-122">ReportingService2010.ListSubscriptions Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listsubscriptions.aspx)

-   [<span data-ttu-id="6d854-123">ReportingService2010.ChangeSubscriptionOwner Method</span><span class="sxs-lookup"><span data-stu-id="6d854-123">ReportingService2010.ChangeSubscriptionOwner Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.changesubscriptionowner.aspx)

-   [<span data-ttu-id="6d854-124">ReportingService2010.ListChildren</span><span class="sxs-lookup"><span data-stu-id="6d854-124">ReportingService2010.ListChildren</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listchildren.aspx)

-   <span data-ttu-id="6d854-125">Die Methode [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) wird nur im letzten Skript verwendet, um zu veranlassen, dass ein bestimmtes Abonnement ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d854-125">The method [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) is only used in the last script to trigger a specific subscription to run.</span></span> <span data-ttu-id="6d854-126">Wenn Sie nicht vorhaben, dieses Skript zu verwenden, können Sie die Berechtigungsanforderungen für die FireEvent-Methode ignorieren.</span><span class="sxs-lookup"><span data-stu-id="6d854-126">If you do not plan to use that script you can ignore the permission requirements for the FireEvent method.</span></span>

 <span data-ttu-id="6d854-127">**Einheitlicher Modus :**</span><span class="sxs-lookup"><span data-stu-id="6d854-127">**Native mode:**</span></span>

-   <span data-ttu-id="6d854-128">Auflisten von Abonnements: (Hyperlink "", lesen Sie den https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx Bericht, und der Benutzer ist der Abonnement Besitzer) oder "Read anyabonnement"</span><span class="sxs-lookup"><span data-stu-id="6d854-128">List Subscriptions: ( HYPERLINK "https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx" ReadSubscription on the report AND the user is the subscription owner) OR ReadAnySubscription</span></span>

-   <span data-ttu-id="6d854-129">Abonnements ändern: Der Benutzer muss ein Mitglied der Gruppe "BUILTIN\Administrators" sein.</span><span class="sxs-lookup"><span data-stu-id="6d854-129">Change Subscriptions: The user must be a member of the BUILTIN\Administrators group</span></span>

-   <span data-ttu-id="6d854-130">Untergeordnete Elemente auflisten: ReadProperties für das Element</span><span class="sxs-lookup"><span data-stu-id="6d854-130">List Children: ReadProperties on Item</span></span>

-   <span data-ttu-id="6d854-131">Ereignis auslösen: GenerateEvents (System)</span><span class="sxs-lookup"><span data-stu-id="6d854-131">Fire Event: GenerateEvents (System)</span></span>

 <span data-ttu-id="6d854-132">**SharePoint-Modus:**</span><span class="sxs-lookup"><span data-stu-id="6d854-132">**SharePoint mode:**</span></span>

-   <span data-ttu-id="6d854-133">Auflisten von Abonnements: managealerts oder (Hyperlink " https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx " für den Bericht, und der Benutzer ist der Abonnement Besitzer und das Abonnement ist ein Zeit gesteuerter Abonnement).</span><span class="sxs-lookup"><span data-stu-id="6d854-133">List Subscriptions: ManageAlerts OR ( HYPERLINK "https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx" CreateAlerts on the report AND the user is the subscription owner and the subscription is a timed subscription).</span></span>

-   <span data-ttu-id="6d854-134">Abonnements ändern: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="6d854-134">Change Subscriptions: ManageWeb</span></span>

-   <span data-ttu-id="6d854-135">Untergeordnete Elemente auflisten: ViewListItems</span><span class="sxs-lookup"><span data-stu-id="6d854-135">List Children: ViewListItems</span></span>

-   <span data-ttu-id="6d854-136">Ereignis auslösen: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="6d854-136">Fire Event: ManageWeb</span></span>

 <span data-ttu-id="6d854-137">Weitere Informationen finden Sie unter [Vergleichen der Rollen und Aufgaben in Reporting Services mit SharePoint-Gruppen und -Berechtigungen](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6d854-137">For more information, see [Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span></span>

### <a name="script-usage"></a><span data-ttu-id="6d854-138">Verwenden von Skripts</span><span class="sxs-lookup"><span data-stu-id="6d854-138">Script usage</span></span>
 <span data-ttu-id="6d854-139">**Erstellen von Skriptdateien (.ps1)**</span><span class="sxs-lookup"><span data-stu-id="6d854-139">**Create Script files (.ps1)**</span></span>

1.  <span data-ttu-id="6d854-140">Erstellen Sie einen Ordner mit dem Namen **c:\scripts**.</span><span class="sxs-lookup"><span data-stu-id="6d854-140">Create a folder named **c:\scripts**.</span></span> <span data-ttu-id="6d854-141">Wenn Sie einen anderen Ordner wählen, passen Sie den Ordnernamen in den Befehlszeilensyntax-Anweisungen aus dem Beispiel an.</span><span class="sxs-lookup"><span data-stu-id="6d854-141">If you choose a different folder then modify the folder name used in the example command line syntax statements.</span></span>

2.  <span data-ttu-id="6d854-142">Erstellen Sie eine Textdatei für jedes Skript, und speichern Sie die Dateien im Ordner c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="6d854-142">Create a text file for each script and save the files to the c:\scripts folder.</span></span> <span data-ttu-id="6d854-143">Verwenden Sie den Namen jeder einzelnen Beispiel-Befehlszeilensyntax, wenn Sie die .ps1-Dateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d854-143">When you create the .ps1 files, use the name from each example command line syntax.</span></span>

3.  <span data-ttu-id="6d854-144">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="6d854-144">Open a command prompt with administrative privileges.</span></span>

4.  <span data-ttu-id="6d854-145">Führen Sie jede Skriptdatei aus und verwenden Sie dafür die Befehlszeilensyntax, die in jedem Beispiel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6d854-145">Run each script file, using the sample command line syntax provided with each example.</span></span>

 <span data-ttu-id="6d854-146">**Getestete Umgebungen**</span><span class="sxs-lookup"><span data-stu-id="6d854-146">**Tested environments**</span></span>

 <span data-ttu-id="6d854-147">Die Skripts in diesem Thema wurden mit Version 3 von PowerShell getestet sowie den folgenden Versionen von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6d854-147">The scripts in this topic were tested on PowerShell version 3 and with the following versions of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span></span>

-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]

-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]

-   [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]

##  <a name="script-list-the-ownership-of-all-subscriptions"></a><a name="bkmk_list_ownership_all"></a> <span data-ttu-id="6d854-148">Skript: Auflisten der Besitzer aller Abonnements</span><span class="sxs-lookup"><span data-stu-id="6d854-148">Script: List the ownership of all subscriptions</span></span>
 <span data-ttu-id="6d854-149">Dieses Skript listet alle Abonnements auf einer Site auf.</span><span class="sxs-lookup"><span data-stu-id="6d854-149">This script lists all of the subscriptions on a site.</span></span> <span data-ttu-id="6d854-150">Sie können dieses Skript verwenden, um Ihre Verbindung zu testen oder um den Berichtspfad und die Abonnement-ID für die Verwendung in den anderen Skripts zu verifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d854-150">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="6d854-151">Dieses Skript ist außerdem hilfreich, wenn Sie einfach prüfen möchten, welche Abonnements vorhanden sind und wer diese besitzt.</span><span class="sxs-lookup"><span data-stu-id="6d854-151">This is also a useful script to simply audit what subscriptions exist and who owns them.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="6d854-152">Syntax im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-152">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="6d854-153">Syntax im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-153">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="6d854-154">Skript</span><span class="sxs-lookup"><span data-stu-id="6d854-154">Script</span></span>

```powershell
# Parameters
#    server   - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)

Param(
    [string]$server,
    [string]$site
   )

$rs2010 += New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site); # use "/" for default native mode site

Write-Host " "
Write-Host "----- $server's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted, Status
```

> [!TIP]
>  <span data-ttu-id="6d854-155">Verwenden Sie das SharePoint-Cmdlet **Get-SPSite**, um Website-URLs im SharePoint-Modus zu verifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d854-155">To verify site URLS in SharePoint mode, use the SharePoint cmdlet **Get-SPSite**.</span></span> <span data-ttu-id="6d854-156">Weitere Informationen finden Sie unter [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="6d854-156">For more information, see [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span></span>

##  <a name="script-list-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_list_all_one_user"></a> <span data-ttu-id="6d854-157">Skript: Auflisten aller Abonnements im Besitz eines spezifischen Benutzers</span><span class="sxs-lookup"><span data-stu-id="6d854-157">Script: List all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="6d854-158">Dieses Skript listet alle Abonnements auf, die ein bestimmter Benutzer besitzt.</span><span class="sxs-lookup"><span data-stu-id="6d854-158">This script lists all of the subscriptions owned by a specific user.</span></span> <span data-ttu-id="6d854-159">Sie können dieses Skript verwenden, um Ihre Verbindung zu testen oder um den Berichtspfad und die Abonnement-ID für die Verwendung in den anderen Skripts zu verifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d854-159">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="6d854-160">Dieses Skript ist hilfreich, wenn jemand Ihr Unternehmen verlässt und Sie prüfen möchten, welche Abonnements diese Person besessen hat, sodass Sie den Besitzer ändern oder das Abonnement löschen können.</span><span class="sxs-lookup"><span data-stu-id="6d854-160">This script is useful when someone in your organization leaves and you want to verify what subscriptions they owned so you can change the owner or delete the subscription.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="6d854-161">Syntax im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-161">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]" "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="6d854-162">Syntax im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-162">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]"  "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="6d854-163">Skript</span><span class="sxs-lookup"><span data-stu-id="6d854-163">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
Param(
    [string]$currentOwner,
    [string]$server,
    [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $currentOwner's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.owner -eq $currentOwner}
```

##  <a name="script-change-ownership-for-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_change_all"></a> <span data-ttu-id="6d854-164">Skript: Ändern des Besitzes aller Abonnements eines spezifischen Benutzers</span><span class="sxs-lookup"><span data-stu-id="6d854-164">Script: Change ownership for all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="6d854-165">Dieses Skript ändert den Besitz für alle Abonnements, die ein bestimmter Benutzer besitzt, zum neuen Besitzerparameter.</span><span class="sxs-lookup"><span data-stu-id="6d854-165">This script changes the ownership for all subscriptions owned by a specific user to the new owner parameter.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="6d854-166">Syntax im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-166">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\current owner]" "[Domain]\[new owner]" "[server]/reportserver"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="6d854-167">Syntax im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-167">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\{current owner]" "[Domain]\[new owner]" "[server]/_vti_bin/reportserver"
```

### <a name="script"></a><span data-ttu-id="6d854-168">Skript</span><span class="sxs-lookup"><span data-stu-id="6d854-168">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    newOwner      - DOMAIN\USER that will own the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver, myserver/reportserver_db2, myserver/_vti_bin/reportserver)

Param(
    [string]$currentOwner,
    [string]$newOwner,
    [string]$server
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$items = $rs2010.ListChildren("/", $true);

$subscriptions = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $curRepSubs = $rs2010.ListSubscriptions($item.Path);
        ForEach ($curRepSub in $curRepSubs)
        {
            if ($curRepSub.Owner -eq $currentOwner)
            {
                $subscriptions += $curRepSub;
            }
        }
    }
}

Write-Host " "
Write-Host " "
Write-Host -foregroundcolor "green" "-----  $currentOwner's Subscriptions changing ownership to $newOwner : "
$subscriptions | select SubscriptionID, Owner, Path, Description,  Status  | format-table -AutoSize

ForEach ($sub in $subscriptions)
{
    $rs2010.ChangeSubscriptionOwner($sub.SubscriptionID, $newOwner);
}

$subs2 = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $subs2 += $rs2010.ListSubscriptions($item.Path);
    }
}
```

##  <a name="script-list-all-subscriptions-associated-with-a-specific-report"></a><a name="bkmk_list_for_1_report"></a> <span data-ttu-id="6d854-169">Skript: Auflisten aller Abonnements im Zusammenhang mit einem bestimmten Bericht</span><span class="sxs-lookup"><span data-stu-id="6d854-169">Script: List all subscriptions associated with a specific report</span></span>
 <span data-ttu-id="6d854-170">Dieses Skript listet alle Abonnements auf, die mit einem bestimmten Bericht verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="6d854-170">This script lists all of the subscriptions associated with a specific report.</span></span> <span data-ttu-id="6d854-171">Die Berichtspfadsyntax unterscheidet sich vom SharePoint-Modus, der eine vollständige URL erfordert.</span><span class="sxs-lookup"><span data-stu-id="6d854-171">The report path syntax is different SharePoint mode which requires a full URL.</span></span> <span data-ttu-id="6d854-172">In den Syntaxbeispielen wird der Berichtsname „title only“ verwendet, der ein Leerzeichen enthält und daher einfache Anführungszeichen vor und nach dem Berichtsnamen erfordert.</span><span class="sxs-lookup"><span data-stu-id="6d854-172">In the syntax examples, the report name used is "title only", which contains a space and therefore requires the single quotes around the report name.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="6d854-173">Syntax im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-173">Native mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/reportserver" "'/reports/title only'" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="6d854-174">Syntax im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-174">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/_vti_bin/reportserver"  "'http://[server]/shared documents/title only.rdl'" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="6d854-175">Skript</span><span class="sxs-lookup"><span data-stu-id="6d854-175">Script</span></span>

```powershell
# Parameters:
#    server      - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    reportpath  - path to report in the report server, including report name e.g. /reports/test report >> pass in  "'/reports/title only'"
#    site        - use "/" for default native mode site
Param
(
      [string]$server,
      [string]$reportpath,
      [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $reportpath 's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.path -eq $reportpath}
```

##  <a name="script-change-ownership-of-a-specific-subscription"></a><a name="bkmk_change_all_1_subscription"></a> <span data-ttu-id="6d854-176">Skript: Ändern des Besitzes eines bestimmten Abonnements</span><span class="sxs-lookup"><span data-stu-id="6d854-176">Script: Change ownership of a specific subscription</span></span>
 <span data-ttu-id="6d854-177">Dieses Skript ändert den Besitz eines bestimmten Abonnements.</span><span class="sxs-lookup"><span data-stu-id="6d854-177">This script changes the ownership for a specific subscription.</span></span> <span data-ttu-id="6d854-178">Dieses Abonnement wird durch die SubscriptionID (Abonnement-ID) identifiziert, die Sie in das Skript übernehmen.</span><span class="sxs-lookup"><span data-stu-id="6d854-178">The subscription is identified by the SubscriptionID that you pass into the script.</span></span> <span data-ttu-id="6d854-179">Sie können eines der Skripts zur Auflistung von Abonnements verwenden, um die korrekte SubscriptionID zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6d854-179">You can use one of the list subscription scripts to determine the correct SubscriptionID.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="6d854-180">Syntax im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-180">Native mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/reportserver" "/" "ac5637a1-9982-4d89-9d69-a72a9c3b3150"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="6d854-181">Syntax im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-181">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/_vti_bin/reportserver" "http://[server]" "9660674b-f020-453f-b1e3-d9ba37624519"
```

### <a name="script"></a><span data-ttu-id="6d854-182">Skript</span><span class="sxs-lookup"><span data-stu-id="6d854-182">Script</span></span>

```powershell
# Parameters:
#    newOwner       - DOMAIN\USER that will own the subscriptions you wish to change
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
#    subscriptionID - guid for the single subscription to change

Param(
    [string]$newOwner,
    [string]$server,
    [string]$site,
    [string]$subscriptionid
   )
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;

$subscription += $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid};

Write-Host " "
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status

$rs2010.ChangeSubscriptionOwner($subscription.SubscriptionID, $newOwner)

#refresh the list
$subscription = $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid}; # use "/" for default native mode site
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status
```

##  <a name="script-run-fire-a-single-subscription"></a><a name="bkmk_run_1_subscription"></a> <span data-ttu-id="6d854-183">Skript: Ausführen (Auslösen) eines Einzelabonnements</span><span class="sxs-lookup"><span data-stu-id="6d854-183">Script: Run (fire) a single subscription</span></span>
 <span data-ttu-id="6d854-184">Dieses Skript führt ein bestimmtes Abonnement mit der FireEvent-Methode aus.</span><span class="sxs-lookup"><span data-stu-id="6d854-184">This script will run a specific subscription using the FireEvent method.</span></span> <span data-ttu-id="6d854-185">Das Skript führt das Abonnement sofort aus, unabhängig davon, welcher Zeitplan für das Abonnement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6d854-185">The script will immediately run the subscription regardless of the schedule configured for the subscription.</span></span> <span data-ttu-id="6d854-186">Der EventType (Ereignistyp) wird mit einem bekannten Satz an Ereignissen abgeglichen, die in der Konfigurationsdatei des Berichtsservers **rsreportserver.config** definiert sind. Das Skript verwendet den folgenden Ereignistyp für standardmäßige Abonnements:</span><span class="sxs-lookup"><span data-stu-id="6d854-186">The EventType is matched against the known set of events that are defined in the report server configuration file **rsreportserver.config** The script uses the following event type for standard subscriptions:</span></span>

 `<Event>`

 `<Type>TimedSubscription</Type>`

 `</Event>`

 <span data-ttu-id="6d854-187">Weitere Informationen zur Konfigurationsdatei finden Sie unter [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="6d854-187">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>

 <span data-ttu-id="6d854-188">Das Skript enthält die Verzögerungslogik „`Start-Sleep -s 6`“, sodass nach Auslösen des Ereignisses Zeit bleibt, in der der aktualisierte Status mit der ListSubscription-Methode verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6d854-188">The script includes delay logic "`Start-Sleep -s 6`" so there is time after the event fires, for the updated status to be available with the ListSubscription method.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="6d854-189">Syntax im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-189">Native mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/reportserver" $null "70366e82-2d3c-4edd-a216-b97e51e26de9"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="6d854-190">Syntax im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="6d854-190">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/_vti_bin/reportserver" "http://[server]" "c3425c72-580d-423e-805a-41cf9799fd25"
```

### <a name="script"></a><span data-ttu-id="6d854-191">Skript</span><span class="sxs-lookup"><span data-stu-id="6d854-191">Script</span></span>

```powershell
# Parameters
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site           - use $null for a native mode server
#    subscriptionid - subscription guid

Param(
  [string]$server,
  [string]$site,
  [string]$subscriptionid
  )

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
#event type is case sensative to what is in the rsreportserver.config
$rs2010.FireEvent("TimedSubscription",$subscriptionid,$site)

Write-Host " "
Write-Host "----- Subscription ($subscriptionid) status: "
#get list of subscriptions and filter to the specific ID to see the Status and LastExecuted
Start-Sleep -s 6 # slight delay in processing so ListSubscription returns the updated Status and LastExecuted
$subscriptions = $rs2010.ListSubscriptions($site); 
$subscriptions | select Status, Path, report, Description, Owner, SubscriptionID, EventType, lastexecuted | where {$_.SubscriptionID -eq $subscriptionid}
```

## <a name="see-also"></a><span data-ttu-id="6d854-192">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d854-192">See Also</span></span>
 <span data-ttu-id="6d854-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="6d854-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span> 
 <xref:ReportService2010.ReportingService2010.ListChildren%2A> 
 <xref:ReportService2010.ReportingService2010.FireEvent%2A>
