---
title: Veröffentlichen eines Berichts in einer SharePoint-Bibliothek | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], reports in SharePoint integrated mode
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23b74ffb04bf1e13523dcf6ec5d774089d80f73b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696406"
---
# <a name="publish-a-report-to-a-sharepoint-library"></a><span data-ttu-id="92e42-102">Veröffentlichen eines Berichts in einer SharePoint-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="92e42-102">Publish a Report to a SharePoint Library</span></span>
  <span data-ttu-id="92e42-103">Wenn Sie einen Bericht auf einer für die SharePoint-Integration konfigurierten SharePoint-Website veröffentlichen möchten, müssen Sie die Berichtsprojekteigenschaften im Berichts-Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="92e42-103">To publish a report to a SharePoint site configured for SharePoint integration, you must set the project properties in Report Designer.</span></span> <span data-ttu-id="92e42-104">In den Projekteigenschaften müssen alle Verweise auf Server, Berichte und freigegebene Datenquellen vollqualifizierte URLs sein.</span><span class="sxs-lookup"><span data-stu-id="92e42-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span> <span data-ttu-id="92e42-105">Zudem muss es sich in einer Berichtsdefinition bei allen Verweisen auf eingebettete Berichte, Drillthroughberichten und Ressourcen (z. B. webbasierte Bilder) um vollqualifizierte URLs handeln.</span><span class="sxs-lookup"><span data-stu-id="92e42-105">In the report definition, all references to subreports, drillthrough reports, and resources such as Web-based images, must be fully qualified URLS.</span></span>  
  
 <span data-ttu-id="92e42-106">Sie müssen für die SharePoint-Website über die Berechtigung als **Mitglied** oder **Besitzer** verfügen, um die Eigenschaften für das Projekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="92e42-106">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span> <span data-ttu-id="92e42-107">Weitere Informationen finden Sie unter [Beispiele für URLs von veröffentlichten Berichtselementen auf einem Berichtsserver im SharePoint-Modus &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="92e42-107">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-report-to-a-sharepoint-site"></a><span data-ttu-id="92e42-108">So veröffentlichen Sie einen Bericht auf einer SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="92e42-108">To publish a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="92e42-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]öffnen Sie ein vorhandenes oder neues Berichtsserverprojekt.</span><span class="sxs-lookup"><span data-stu-id="92e42-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open an existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="92e42-110">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="92e42-110">From the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="92e42-111">Das _\<project>_ Dialogfeld **Eigenschaften Seiten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="92e42-111">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="92e42-112">Wählen Sie in der Liste **Konfiguration** den Namen einer Projektmappenkonfiguration aus, die Sie zum Erstellen und Veröffentlichen Ihres Berichts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="92e42-112">In the **Configuration** list, select the name of a solution build configuration to use to build and publish your report.</span></span> <span data-ttu-id="92e42-113">Die aktuelle Konfiguration wird als **aktiv**( *\<configuration>* ) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="92e42-113">The current configuration is listed as **Active**(*\<configuration>*).</span></span>  
  
4.  <span data-ttu-id="92e42-114">Wenn Sie die freigegebenen Datenquellen in Ihrem Projekt veröffentlichen und bereits veröffentlichte freigegebene Datenquellen überschreiben möchten, legen Sie **OverwriteDataSources** auf **True**fest.</span><span class="sxs-lookup"><span data-stu-id="92e42-114">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="92e42-115">Optionale Geben Sie für **TargetDataSourceFolder**eine URL zu einer SharePoint-Bibliothek oder einem Bibliotheks Ordner ein (z *http://TestServer/TestSite/Documents/DataSources)* . b..</span><span class="sxs-lookup"><span data-stu-id="92e42-115">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder (for example, *http://TestServer/TestSite/Documents/DataSources)*.</span></span>  
  
     <span data-ttu-id="92e42-116">Wenn Sie keinen Wert angeben, wird der Wert **TargetReportFolder** verwendet.</span><span class="sxs-lookup"><span data-stu-id="92e42-116">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="92e42-117">Geben Sie für **TargetReportFolder**eine URL zu einer Bibliothek oder einem Bibliotheks Ordner ein (z *http://TestServer/TestSite/Documents/Reports)* . b..</span><span class="sxs-lookup"><span data-stu-id="92e42-117">For **TargetReportFolder**, type a URL to a library or library folder (for example, *http://TestServer/TestSite/Documents/Reports)*.</span></span>  
  
7.  <span data-ttu-id="92e42-118">Geben Sie für **TargetServerURL**eine URL zu einer SharePoint-Website auf oberster Ebene oder zu einer Unterwebsite ein.</span><span class="sxs-lookup"><span data-stu-id="92e42-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="92e42-119">Wenn Sie keine Website angeben, wird die Standard Website der obersten Ebene verwendet (z. b., *http://servername* *http://servername/site* oder *http://servername/site/subsite* ).</span><span class="sxs-lookup"><span data-stu-id="92e42-119">If you do not specify a site, the default top-level site is used (for example, *http://servername*, *http://servername/site*, or *http://servername/site/subsite*).</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="92e42-120">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Bericht, den Sie veröffentlichen möchten, und klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="92e42-120">In Solution Explorer, right-click the report you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="92e42-121">Der Bericht wird an dem in **TargetReportFolder**angegebenen Speicherort veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="92e42-121">The report is published to the location specified in **TargetReportFolder**.</span></span> <span data-ttu-id="92e42-122">Im Ausgabefenster werden Bereitstellungsfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92e42-122">Deployment errors appear in the Output window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e42-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92e42-123">See Also</span></span>  
 <span data-ttu-id="92e42-124">[Eigenschaften Seiten für Projekt (Dialog Feld)](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="92e42-124">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="92e42-125">[Festlegen der Bereitstellungs Eigenschaften &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="92e42-125">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="92e42-126">[Veröffentlichen von Berichten auf einem Berichts Server](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="92e42-126">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="92e42-127">[URL-Beispiele für veröffentlichte Berichts Elemente auf einem Berichts Server im SharePoint-Modus &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="92e42-127">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 [<span data-ttu-id="92e42-128">Verwenden einer Office Data Connection &#40;.odc&#41; für Berichte &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="92e42-128">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
