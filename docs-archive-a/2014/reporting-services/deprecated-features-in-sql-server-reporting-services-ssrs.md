---
title: Als veraltet markierte Features in SQL Server Reporting Services in SQL Server 2014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- deprecated features [Reporting Services]
- HTML OWC rendering extension [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: 3876c01e-f81d-4cce-9104-5106a8c369e6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af858ae94bf5ea3d9f0cfe0b99759442dabd6629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618538"
---
# <a name="deprecated-features-in-sql-server-reporting-services-in-sql-server-2014"></a><span data-ttu-id="7a816-102">Als veraltet markierte Funktionen in SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7a816-102">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>
  <span data-ttu-id="7a816-103">In diesem Thema werden die veralteten [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a816-103">This topic describes the deprecated [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="7a816-104">Die Funktionen sind immer noch in der Version verfügbar, in der sie veraltet sind. Es ist jedoch geplant, die Funktionen in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7a816-104">The features are still available in the release in which they are deprecated; however the features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a816-105">Als veraltet markierte Funktionen sollten in neuen Anwendungen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a816-105">Deprecated features should not be used in new applications.</span></span>  
  
 <span data-ttu-id="7a816-106">Inhalte dieses Themas:</span><span class="sxs-lookup"><span data-stu-id="7a816-106">In this topic:</span></span>  
  
-   [<span data-ttu-id="7a816-107">Als veraltet markierte Funktionen in SQL Server 2014 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7a816-107">SQL Server 2014 Reporting Services Deprecated Features</span></span>](#bkmk_2014)  
  
-   [<span data-ttu-id="7a816-108">Als veraltet markierte Funktionen in SQL Server 2012 SP1 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7a816-108">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>](#bkmk_2012sp1)  
  
-   [<span data-ttu-id="7a816-109">Als veraltet markierte Funktionen in SQL Server 2012 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7a816-109">SQL Server 2012 Reporting Services Deprecated Features</span></span>](#bkmk_2012)  
  
-   [<span data-ttu-id="7a816-110">Als veraltet markierte Funktionen in SQL Server 2008 R2 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7a816-110">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>](#bkmk_kj)  
  
##  <a name="sql-server-2014-reporting-services-deprecated-features"></a><a name="bkmk_2014"></a><span data-ttu-id="7a816-111">SQL Server 2014 Reporting Services als veraltet markierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a816-111">SQL Server 2014 Reporting Services Deprecated Features</span></span>  
  
### <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="7a816-112">Funktionen, die in der nächsten Version von SQL Server nicht unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="7a816-112">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="7a816-113">Die folgenden [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Funktionen werden in der **nächsten** Version von nicht mehr unterstützt [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a816-113">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features will not be supported in the **next** version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a816-114">Verwenden Sie diese Funktionen nicht zum Entwickeln neuer Anwendungen, und ändern Sie so bald wie möglich die Anwendungen, in denen diese Funktionen zurzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a816-114">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
#### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="7a816-115">HTML-Renderingerweiterung für Geräteinformationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7a816-115">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="7a816-116">Die Geräteinformationseinstellungen für die HTML-Renderingerweiterung sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-116">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="7a816-117">ActionScript</span><span class="sxs-lookup"><span data-stu-id="7a816-117">ActionScript</span></span>  
  
-   <span data-ttu-id="7a816-118">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="7a816-118">ActiveXControls</span></span>  
  
-   <span data-ttu-id="7a816-119">GetImage</span><span class="sxs-lookup"><span data-stu-id="7a816-119">GetImage</span></span>  
  
-   <span data-ttu-id="7a816-120">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="7a816-120">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="7a816-121">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="7a816-121">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="7a816-122">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="7a816-122">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="7a816-123">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="7a816-123">StreamRoot</span></span>  
  
-   <span data-ttu-id="7a816-124">UsePx</span><span class="sxs-lookup"><span data-stu-id="7a816-124">UsePx</span></span>  
  
-   <span data-ttu-id="7a816-125">Zoom</span><span class="sxs-lookup"><span data-stu-id="7a816-125">Zoom</span></span>  
  
 <span data-ttu-id="7a816-126">Weitere Informationen über die HTML-Renderingerweiterung finden Sie unter [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7a816-126">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
#### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="7a816-127">Rendern von Microsoft Word und Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="7a816-127">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="7a816-128">Die[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -BIFF8-Renderingerweiterungen von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] senden Berichte im binären Austauschdateiformat von [!INCLUDE[msCoName](../includes/msconame-md.md)] Word und [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="7a816-128">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7a816-129">schließt Erweiterungen ein, die im [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML-Format Rendering.</span><span class="sxs-lookup"><span data-stu-id="7a816-129">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
#### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="7a816-130">Berichtsdefinitionssprache (RDL) 2005 und früher</span><span class="sxs-lookup"><span data-stu-id="7a816-130">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="7a816-131">Report Definition Language (RDL) 2005 und früher ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-131">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="7a816-132">Weitere Informationen zu RDL finden Sie unter [Berichts Definitions Sprache &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7a816-132">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="7a816-133">Weitere Informationen zum Aktualisieren von Berichten von Sie unter [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7a816-133">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
#### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="7a816-134">SQL Server 2005 und frühere benutzerdefinierte Berichtselemente</span><span class="sxs-lookup"><span data-stu-id="7a816-134">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="7a816-135">Benutzerdefinierte Berichts Elemente (CRI), [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] die für 2005 und früher kompiliert wurden, sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-135">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="7a816-136">Reporting Services Snapshots 2005 und früher</span><span class="sxs-lookup"><span data-stu-id="7a816-136">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7a816-137">mit 2005 und früher gerenderte Momentaufnahmen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-137">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="report-models"></a><span data-ttu-id="7a816-138">Berichtsmodelle</span><span class="sxs-lookup"><span data-stu-id="7a816-138">Report Models</span></span>  
 <span data-ttu-id="7a816-139">Semantische Modellierungssprachberichtsmodelle (SMDL) sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-139">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="7a816-140">Obwohl Sie weiterhin vorhandene Berichts Modelle als Datenquellen in Berichten verwenden können [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , sollten Sie Ihre Berichte aktualisieren, um ihre Abhängigkeit von Berichts Modellen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7a816-140">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7a816-141">enthält [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] keine Tools zum Erstellen oder Aktualisieren von Berichts Modellen.</span><span class="sxs-lookup"><span data-stu-id="7a816-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="7a816-142">Weitere Informationen finden Sie unter [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="7a816-142">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
#### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="7a816-143">Veraltete Methoden im Webdienstendpunkt</span><span class="sxs-lookup"><span data-stu-id="7a816-143">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="7a816-144">Die folgenden Vorgänge sind im <xref:ReportService2010.ReportingService2010>-Webdienstendpunkt als veraltet markiert:</span><span class="sxs-lookup"><span data-stu-id="7a816-144">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
#### <a name="sharepoint-web-parts"></a><span data-ttu-id="7a816-145">SharePoint-Webparts</span><span class="sxs-lookup"><span data-stu-id="7a816-145">SharePoint Web Parts</span></span>  
 <span data-ttu-id="7a816-146">Die für die Installation erforderliche CAB-Datei **RSWebParts.cab** und die SharePoint-Webparts, die aus der CAB-Datei extrahiert werden können, sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-146">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="7a816-147">Die veralteten Webparts sind Berichts-Explorer (**SPExplorer.dwp**) und Berichts-Viewer (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="7a816-147">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="7a816-148">Weitere Informationen zu den veralteten Webparts finden Sie unter [Anzeigen und Durchsuchen von Berichten im einheitlichen Modus mithilfe von SharePoint-Webparts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="7a816-148">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
### <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="7a816-149">Funktionen, die in einer zukünftigen Version von SQL Server nicht unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="7a816-149">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="7a816-150">Die folgenden Funktionen von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] werden in der nächsten Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]noch unterstützt, aber in zukünftigen Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7a816-150">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="7a816-151">Die betreffende Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] wurde noch nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7a816-151">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
 <span data-ttu-id="7a816-152">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] wurden keine [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]-Funktionen als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7a816-152">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features were deprecated in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="sql-server-2012-sp1-reporting-services-deprecated-features"></a><a name="bkmk_2012sp1"></a><span data-ttu-id="7a816-153">SQL Server 2012 SP1 Reporting Services als veraltet markierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a816-153">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="7a816-154">In diesem Abschnitt werden als veraltet markierte [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a816-154">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span></span> <span data-ttu-id="7a816-155">Die folgenden Funktionen von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] werden in der nächsten Version von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]noch unterstützt, aber in zukünftigen Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7a816-155">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="7a816-156">Die betreffende Version von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] wurde noch nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7a816-156">The specific version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] has not been determined.</span></span>  
  
### <a name="sharepoint-web-parts"></a><span data-ttu-id="7a816-157">SharePoint-Webparts</span><span class="sxs-lookup"><span data-stu-id="7a816-157">SharePoint Web Parts</span></span>  
 <span data-ttu-id="7a816-158">Die für die Installation erforderliche CAB-Datei **RSWebParts.cab** und die SharePoint-Webparts, die aus der CAB-Datei extrahiert werden können, sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-158">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="7a816-159">Die veralteten Webparts sind Berichts-Explorer (**SPExplorer.dwp**) und Berichts-Viewer (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="7a816-159">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="7a816-160">Weitere Informationen zu den veralteten Webparts finden Sie unter [Anzeigen und Durchsuchen von Berichten im einheitlichen Modus mithilfe von SharePoint-Webparts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="7a816-160">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
##  <a name="sql-server-2012-reporting-services-deprecated-features"></a><a name="bkmk_2012"></a><span data-ttu-id="7a816-161">SQL Server 2012 Reporting Services als veraltet markierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a816-161">SQL Server 2012 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="7a816-162">In diesem Abschnitt werden als veraltet markierte [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a816-162">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="7a816-163">HTML-Renderingerweiterung für Geräteinformationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7a816-163">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="7a816-164">Die Geräteinformationseinstellungen für die HTML-Renderingerweiterung sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-164">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="7a816-165">ActionScript</span><span class="sxs-lookup"><span data-stu-id="7a816-165">ActionScript</span></span>  
  
-   <span data-ttu-id="7a816-166">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="7a816-166">ActiveXControls</span></span>  
  
-   <span data-ttu-id="7a816-167">GetImage</span><span class="sxs-lookup"><span data-stu-id="7a816-167">GetImage</span></span>  
  
-   <span data-ttu-id="7a816-168">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="7a816-168">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="7a816-169">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="7a816-169">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="7a816-170">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="7a816-170">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="7a816-171">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="7a816-171">StreamRoot</span></span>  
  
-   <span data-ttu-id="7a816-172">UsePx</span><span class="sxs-lookup"><span data-stu-id="7a816-172">UsePx</span></span>  
  
-   <span data-ttu-id="7a816-173">Zoom</span><span class="sxs-lookup"><span data-stu-id="7a816-173">Zoom</span></span>  
  
 <span data-ttu-id="7a816-174">Weitere Informationen über die HTML-Renderingerweiterung finden Sie unter [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7a816-174">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="7a816-175">Rendern von Microsoft Word und Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="7a816-175">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="7a816-176">Die[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -BIFF8-Renderingerweiterungen von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] senden Berichte im binären Austauschdateiformat von [!INCLUDE[msCoName](../includes/msconame-md.md)] Word und [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="7a816-176">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7a816-177">schließt Erweiterungen ein, die im [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML-Format Rendering.</span><span class="sxs-lookup"><span data-stu-id="7a816-177">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="7a816-178">Berichtsdefinitionssprache (RDL) 2005 und früher</span><span class="sxs-lookup"><span data-stu-id="7a816-178">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="7a816-179">Report Definition Language (RDL) 2005 und früher ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-179">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="7a816-180">Weitere Informationen zu RDL finden Sie unter [Berichts Definitions Sprache &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7a816-180">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="7a816-181">Weitere Informationen zum Aktualisieren von Berichten von Sie unter [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7a816-181">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="7a816-182">SQL Server 2005 und frühere benutzerdefinierte Berichtselemente</span><span class="sxs-lookup"><span data-stu-id="7a816-182">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="7a816-183">Benutzerdefinierte Berichts Elemente (CRI), [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] die für 2005 und früher kompiliert wurden, sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-183">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="7a816-184">Reporting Services Snapshots 2005 und früher</span><span class="sxs-lookup"><span data-stu-id="7a816-184">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="7a816-185">mit 2005 und früher gerenderte Momentaufnahmen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-185">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="report-models"></a><span data-ttu-id="7a816-186">Berichtsmodelle</span><span class="sxs-lookup"><span data-stu-id="7a816-186">Report Models</span></span>  
 <span data-ttu-id="7a816-187">Semantische Modellierungssprachberichtsmodelle (SMDL) sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="7a816-187">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="7a816-188">Obwohl Sie weiterhin vorhandene Berichts Modelle als Datenquellen in Berichten verwenden können [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , sollten Sie Ihre Berichte aktualisieren, um ihre Abhängigkeit von Berichts Modellen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7a816-188">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="7a816-189">enthält [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] keine Tools zum Erstellen oder Aktualisieren von Berichts Modellen.</span><span class="sxs-lookup"><span data-stu-id="7a816-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="7a816-190">Weitere Informationen finden Sie unter [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="7a816-190">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="7a816-191">Veraltete Methoden im Webdienstendpunkt</span><span class="sxs-lookup"><span data-stu-id="7a816-191">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="7a816-192">Die folgenden Vorgänge sind im <xref:ReportService2010.ReportingService2010>-Webdienstendpunkt als veraltet markiert:</span><span class="sxs-lookup"><span data-stu-id="7a816-192">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
##  <a name="sql-server-2008-r2-reporting-services-deprecated-features"></a><a name="bkmk_kj"></a><span data-ttu-id="7a816-193">SQL Server 2008 R2 Reporting Services als veraltet markierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a816-193">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a816-194">Da SQL Server 2008 R2 ein kleineres Versionsupgrade von SQL Server 2008 darstellt, wird empfohlen, auch den Inhalt im Abschnitt zu SQL Server 2008 zu lesen.</span><span class="sxs-lookup"><span data-stu-id="7a816-194">Because SQL Server 2008 R2 is a minor version upgrade of SQL Server 2008, we recommend that you also review the content in the SQL Server 2008 section.</span></span>  
  
### <a name="report-server-web-service-endpoints"></a><span data-ttu-id="7a816-195">Report Server-Webdienst-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="7a816-195">Report Server Web Service Endpoints</span></span>  
 <span data-ttu-id="7a816-196">Die Webdienste <xref:ReportService2005.ReportingService2005> und <xref:ReportService2006.ReportingService2006> wurden in dieser Version als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7a816-196">The Web services <xref:ReportService2005.ReportingService2005> and <xref:ReportService2006.ReportingService2006> have been deprecated in this release.</span></span> <span data-ttu-id="7a816-197">Diese Endpunkte wurden durch einen neuen Endpunkt ersetzt: <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="7a816-197">These endpoints have been replaced by a new endpoint: <xref:ReportService2010.ReportingService2010>.</span></span>  
  
 <span data-ttu-id="7a816-198">Der neue Endpunkt enthält die gesamte Funktionalität der veralteten Endpunkte und die neuen Funktionen, die in SQL Server 2008 R2 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="7a816-198">The new endpoint includes all the functionality available in the deprecated endpoints and the new features introduced in SQL Server 2008 R2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a816-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a816-199">See Also</span></span>  
 <span data-ttu-id="7a816-200">[Neues &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7a816-200">[What's New &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span></span>  
 <span data-ttu-id="7a816-201">[Abwärtskompatibilität](../getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="7a816-201">[Backward Compatibility](../getting-started/backward-compatibility.md) </span></span>  
 <span data-ttu-id="7a816-202">[Verhaltensänderungen in SQL Server Reporting Services in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="7a816-202">[Behavior Changes to SQL Server Reporting Services  in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span></span>  
 [<span data-ttu-id="7a816-203">Nicht mehr unterstützte Funktionen in SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7a816-203">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  
  
  
