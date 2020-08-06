---
title: Berichte im lokalen Modus im Vergleich zu Berichten im verbundenen Modus im Berichts-Viewer (Reporting Services im SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a230a9bb-6046-401f-b5e5-53ff6edf2264
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 805be8722a38252a9a44797b5e59d2136bc83d6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721229"
---
# <a name="local-mode-vs-connected-mode-reports-in-the-report-viewer-reporting-services-in-sharepoint-mode"></a><span data-ttu-id="d65c3-102">Berichte im lokalen Modus im Vergleich mit Berichten im verbundenen Modus im Berichts-Viewer (Reporting Services im SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="d65c3-102">Local Mode vs. Connected Mode Reports in the Report Viewer (Reporting Services in SharePoint Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="d65c3-103">-Berichte können so konfiguriert werden, dass sie entweder im *lokalen Modus* oder im *verbundenen Modus*ausgeführt werden, der einen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver nutzt.</span><span class="sxs-lookup"><span data-stu-id="d65c3-103">reports can be configure to run in either *local mode* or *connected mode*, which leverages a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="d65c3-104">Sie können stattdessen mithilfe des Berichts-Viewers Berichte aus SharePoint direkt rendern, sofern die Datenerweiterung die Berichterstellung im lokalen Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d65c3-104">Instead, you can use the Report Viewer to directly render reports from SharePoint when the data extension supports local mode reporting.</span></span> <span data-ttu-id="d65c3-105">Dieser Ansatz wird als *lokaler Modus*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d65c3-105">This approach is called *local mode*.</span></span> <span data-ttu-id="d65c3-106">In früheren Versionen von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]musste die SharePoint-Farm mit einem im SharePoint-Modus konfigurierten [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver verbunden sein, damit Berichte vom Steuerelement des Berichts-Viewers gerendert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="d65c3-106">In previous versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], the SharePoint farm was required to be connected to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server configured in SharePoint mode so the Report Viewer control could render reports.</span></span> <span data-ttu-id="d65c3-107">Dieser Ansatz wird als *Remotemodus* oder *verbundener Modus*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d65c3-107">This approach is called *remote mode* or *connected mode*.</span></span>  
  
 <span data-ttu-id="d65c3-108">Im *lokalen Modus* gibt es keinen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="d65c3-108">In *local mode* there is no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="d65c3-109">Sie müssen das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In für SharePoint-Produkte installieren, während jedoch kein [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d65c3-109">You must install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products, but no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server is required.</span></span> <span data-ttu-id="d65c3-110">Im lokalen Modus können Benutzer Berichte anzeigen, haben aber keinen Zugriff auf serverseitige Funktionen wie Abonnements und Datenwarnungen.</span><span class="sxs-lookup"><span data-stu-id="d65c3-110">With Local mode, users can view reports but will not have access to server side features such as subscriptions and data alerts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="d65c3-111">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="d65c3-111">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="d65c3-112">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="d65c3-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="d65c3-113">Lokaler Modus im Vergleich zum verbundenen Modus und unterstützte Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="d65c3-113">Local mode vs connected mode and supported extensions</span></span>](#bkmk_local_vs_connected)  
  
-   [<span data-ttu-id="d65c3-114">Konfigurieren des lokalen Modus und Zugreifen auf Dienste mit SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="d65c3-114">Configure Local Mode and Access Services with SharePoint 2013</span></span>](#bkmk_local_mode_sharepoint2013)  
  
-   [<span data-ttu-id="d65c3-115">Konfigurieren der Berichterstellung im lokalen Modus mit SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="d65c3-115">Configure Local Mode Reporting with SharePoint 2010</span></span>](#bkmk_local_mode_sharepoint2010)  
  
##  <a name="local-mode-vs-connected-mode-and-supported-extensions"></a><a name="bkmk_local_vs_connected"></a> <span data-ttu-id="d65c3-116">Lokaler Modus vs. verbundener Modus und unterstützte Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="d65c3-116">Local mode vs connected mode and supported extensions</span></span>  
 <span data-ttu-id="d65c3-117">**Lokaler Modus:** Bei Datenerweiterungen, die den lokalen Modus unterstützen, können Berichte vom Berichts-Viewer direkt aus SharePoint gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="d65c3-117">**Local mode:** When you have a data extension that supports local mode, the Report Viewer directly renders reports from SharePoint.</span></span> <span data-ttu-id="d65c3-118">Im *lokalen Modus* gibt es keinen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="d65c3-118">In *local mode* there is no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="d65c3-119">Sie müssen das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In für SharePoint-Produkte installieren, während jedoch kein [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d65c3-119">You must install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products, but no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server is required.</span></span> <span data-ttu-id="d65c3-120">Im lokalen Modus können Benutzer Berichte anzeigen, haben aber **keinen** Zugriff auf serverseitige Funktionen wie Abonnements und Daten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="d65c3-120">With Local mode, users can view reports but will **not** have access to server side features such as subscriptions and data alerts.</span></span>  
  
 <span data-ttu-id="d65c3-121">Für den**verbundenen Modus**, auch *Remotemodus* genannt, ist ein mit der SharePoint-Farm verbundener [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver im SharePoint-Modus erforderlich, damit Berichte vom Steuerelement des Berichts-Viewers gerendert werden können.</span><span class="sxs-lookup"><span data-stu-id="d65c3-121">**Connected mode**, also called *remote mode* requires a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server in SharePoint mode, connected to the SharePoint farm so the Report Viewer control could render reports..</span></span>  
  
 <span data-ttu-id="d65c3-122">Die folgende Liste enthält die Datenverarbeitungserweiterungen, die lokale Modusberichterstellung unterstützen:</span><span class="sxs-lookup"><span data-stu-id="d65c3-122">The following is a list of the data processing extensions that support local mode reporting:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="d65c3-123">Access 2010-Berichtserweiterung.</span><span class="sxs-lookup"><span data-stu-id="d65c3-123">Access 2010 reporting extension.</span></span> <span data-ttu-id="d65c3-124">Weitere Informationen zu Access Services finden Sie unter [Verwenden von Access Services mit SQL Reporting Services: Installieren des SQL Server 2008 R2 Reporting Services-Add-Ins (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?LinkId=192686).</span><span class="sxs-lookup"><span data-stu-id="d65c3-124">For more information on Access Services, see [Use Access Services with SQL Reporting Services: Installing SQL Server 2008 R2 Reporting Services Add-In (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?LinkId=192686).</span></span>  
  
-   <span data-ttu-id="d65c3-125">Die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -SharePoint-Listendatenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="d65c3-125">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint list data extension.</span></span> <span data-ttu-id="d65c3-126">Weitere Informationen zur SharePoint-Listendatenerweiterung finden Sie unter [Von Reporting Services unterstützte Datenquellen &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md)</span><span class="sxs-lookup"><span data-stu-id="d65c3-126">For more information on the SharePoint List Data Extension, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md)</span></span>  
  
 <span data-ttu-id="d65c3-127">Benutzerdefinierte Datenverarbeitungserweiterungen können auch für den lokalen Modus entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="d65c3-127">Custom data processing extensions can also be developed to support local mode.</span></span> <span data-ttu-id="d65c3-128">Weitere Informationen finden Sie unter [Implementing a Data Processing Extension](extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d65c3-128">For more information, see [Implementing a Data Processing Extension](extensions/data-processing/implementing-a-data-processing-extension.md).</span></span>  
  
 <span data-ttu-id="d65c3-129">Der lokale Modus unterstützt das Rendern von Berichten mit einer eingebetteten oder freigegebenen Datenquelle von einer RSDS-Datei.</span><span class="sxs-lookup"><span data-stu-id="d65c3-129">Local mode supports rendering reports that have an embedded data source or a shared data source from an .rsds file.</span></span> <span data-ttu-id="d65c3-130">Sie können den Bericht oder dessen zugeordnete Datenquelle jedoch nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="d65c3-130">However, you cannot manage the report or its associated data source.</span></span> <span data-ttu-id="d65c3-131">In diesem Fall wird ein Fehler mit dem Hinweis ausgegeben, dass der Vorgang im lokalen Modus nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d65c3-131">If you try to do this, you will receive an error that this is not supported in local mode.</span></span> <span data-ttu-id="d65c3-132">Das Verwalten von Datenquellen auf der SharePoint-Website wird nur im verbundenen Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d65c3-132">Managing data sources in the SharePoint site is supported in only connected mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d65c3-133">Wie in früheren Versionen ist es nicht möglich, Benutzernamen und Kennwörter in die RSDS-Datei einzubetten.</span><span class="sxs-lookup"><span data-stu-id="d65c3-133">As with previous versions, you cannot embed user names and passwords in the .rsds file.</span></span>  
  
##  <a name="configure-local-mode-and-access-services-with-sharepoint-2013"></a><a name="bkmk_local_mode_sharepoint2013"></a><span data-ttu-id="d65c3-134">Konfigurieren des lokalen Modus und Zugreifen auf Dienste mit SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="d65c3-134">Configure Local Mode and Access Services with SharePoint 2013</span></span>  
 <span data-ttu-id="d65c3-135">Sie können die SharePoint 2013-Farm so konfigurieren, dass vorhandene Access 2010-Webdatenbanken und der lokale [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Modus unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d65c3-135">You can configure your SharePoint 2013 farm to support existing Access 2010 web databases and [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] local mode.</span></span> <span data-ttu-id="d65c3-136">Weitere Informationen finden Sie unter [Einrichten und Konfigurieren von Access Services 2010 für Webdatenbanken in SharePoint Server 2013](https://technet.microsoft.com/library/ee748653\(office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d65c3-136">For more information, see [Set up and configure Access Services 2010 for web databases in SharePoint Server 2013](https://technet.microsoft.com/library/ee748653\(office.15\).aspx).</span></span>  
  
 <span data-ttu-id="d65c3-137">Es ist nicht möglich, neue Access-Webdatenbanken für SharePoint 2013 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d65c3-137">It is not possible to create new Access web databases for SharePoint 2013.</span></span> <span data-ttu-id="d65c3-138">Access 2013 verwendet den neuen Datenbanktyp *Access Web App* , den Sie in Access erstellen und dann als SharePoint-App in einem Webbrowser verwenden und mit anderen gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="d65c3-138">Access 2013 uses a new type of database, *Access web app* that you build in Access, then use and share with others as a SharePoint app in a web browser.</span></span>  
  
 <span data-ttu-id="d65c3-139">Weitere Informationen finden Sie unter folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="d65c3-139">For more information, see the following.</span></span>  
  
-   <span data-ttu-id="d65c3-140">[Neues in Access 2013](https://office.microsoft.com/access-help/what-s-new-in-access-2013-HA102809500.aspx) ( https://office.microsoft.com/access-help/what-s-new-in-access-2013-HA102809500.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d65c3-140">[What's new in Access 2013](https://office.microsoft.com/access-help/what-s-new-in-access-2013-HA102809500.aspx) (https://office.microsoft.com/access-help/what-s-new-in-access-2013-HA102809500.aspx).</span></span>  
  
-   <span data-ttu-id="d65c3-141">[Grundlegende Aufgaben für eine Access-App](https://office.microsoft.com/access-help/basic-tasks-for-an-access-app-HA102840210.aspx?CTT=5&origin=HA102809500) ( https://office.microsoft.com/access-help/basic-tasks-for-an-access-app-HA102840210.aspx?CTT=5&origin=HA102809500) .</span><span class="sxs-lookup"><span data-stu-id="d65c3-141">[Basic tasks for an Access app](https://office.microsoft.com/access-help/basic-tasks-for-an-access-app-HA102840210.aspx?CTT=5&origin=HA102809500) (https://office.microsoft.com/access-help/basic-tasks-for-an-access-app-HA102840210.aspx?CTT=5&origin=HA102809500).</span></span>  
  
##  <a name="configure-local-mode-reporting-with-sharepoint-2010"></a><a name="bkmk_local_mode_sharepoint2010"></a><span data-ttu-id="d65c3-142">Konfigurieren der Berichterstellung im lokalen Modus mit SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="d65c3-142">Configure Local Mode Reporting with SharePoint 2010</span></span>  
 <span data-ttu-id="d65c3-143">Der lokale Modus erfordert den ASP.NET-Sitzungsstatus.</span><span class="sxs-lookup"><span data-stu-id="d65c3-143">Local mode requires ASP.NET session state.</span></span> <span data-ttu-id="d65c3-144">Durch die Installation von Access-Diensten wird der ASP.NET-Sitzungstatus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d65c3-144">The installation of Access services will enable ASP.Net sessions state.</span></span> <span data-ttu-id="d65c3-145">Sie können die Aktivierung auch mit PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="d65c3-145">You can also enable using PowerShell.</span></span>  
  
1.  <span data-ttu-id="d65c3-146">Öffnen Sie die SharePoint 2010-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="d65c3-146">Open the SharePoint 2010 Management Shell.</span></span>  
  
2.  <span data-ttu-id="d65c3-147">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="d65c3-147">Type the following command:</span></span>  
  
    ```  
    - Enable-SPSessionStateService  
    ```  
  
3.  <span data-ttu-id="d65c3-148">Geben bei Aufforderung den Namen der Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="d65c3-148">When prompted, type the name of your database.</span></span>  
  
4.  <span data-ttu-id="d65c3-149">Führen Sie eine IIS-Rücksetzung aus.</span><span class="sxs-lookup"><span data-stu-id="d65c3-149">Perform an IIS reset.</span></span>  
  
 <span data-ttu-id="d65c3-150">Weitere Informationen finden Sie unter [Verwenden von Access Services mit SQL Reporting Services: Installieren des SQL Server 2008 R2 Reporting Services-Add-Ins (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?LinkId=192686) und [Enable-SPSessionStateService](https://technet.microsoft.com/library/ff607857\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d65c3-150">For more information, see [Use Access Services with SQL Reporting Services: Installing SQL Server 2008 R2 Reporting Services Add-In (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?LinkId=192686) and [Enable-SPSessionStateService](https://technet.microsoft.com/library/ff607857\(v=office.15\).aspx).</span></span>  
  
## <a name="connected-mode"></a><span data-ttu-id="d65c3-151">Modus „Verbunden“</span><span class="sxs-lookup"><span data-stu-id="d65c3-151">Connected mode</span></span>  
 <span data-ttu-id="d65c3-152">Die neuesten Informationen zur Verwendung der ADS-Erweiterung mit verbundenem Modus in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] finden Sie unter [Access Services-Bericht in SharePoint-Website zeigt einen Fehler in der ADS-Datenerweiterung](https://social.technet.microsoft.com/wiki/contents/articles/25298.access-services-report-in-sharepoint-site-shows-error-in-data-extension-ads.aspx).</span><span class="sxs-lookup"><span data-stu-id="d65c3-152">For the latest information on using ADS extension with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connected mode, see [Access Services Report in SharePoint Site shows error in data extension 'ADS'](https://social.technet.microsoft.com/wiki/contents/articles/25298.access-services-report-in-sharepoint-site-shows-error-in-data-extension-ads.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65c3-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d65c3-153">See Also</span></span>  
 [<span data-ttu-id="d65c3-154">Von Reporting Services unterstützte Datenquellen &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d65c3-154">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](create-deploy-and-manage-mobile-and-paginated-reports.md)  
  