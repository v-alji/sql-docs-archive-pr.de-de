---
title: Veröffentlichen einer freigegebenen Datenquelle in einer SharePoint-Bibliothek | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], publishing to a SharePoint library
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 966ed425-3ce2-4e76-8237-3c1c977954ae
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77ee25535ccb98638ae02ca64e3bcbfc88291c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696402"
---
# <a name="publish-a-shared-data-source-to-a-sharepoint-library"></a><span data-ttu-id="27922-102">Veröffentlichen einer freigegebenen Datenquelle in einer SharePoint-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="27922-102">Publish a Shared Data Source to a SharePoint Library</span></span>
  <span data-ttu-id="27922-103">Wenn Sie eine freigegebene Datenquelle auf einem Berichtsserver veröffentlichen möchten, der im integrierten SharePoint-Modus ausgeführt wird, müssen Sie die Berichtsprojekteigenschaften im Berichts-Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="27922-103">To publish a shared data source to a report server that is running in SharePoint integrated mode, you must set the report project properties in Report Designer.</span></span> <span data-ttu-id="27922-104">In den Projekteigenschaften müssen alle Verweise auf Server, Berichte und freigegebene Datenquellen vollqualifizierte URLs sein.</span><span class="sxs-lookup"><span data-stu-id="27922-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span>  
  
 <span data-ttu-id="27922-105">Sie müssen für die SharePoint-Website über eine Berechtigung als **Mitglied** oder **Besitzer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="27922-105">You must have **Member** or **Owner** permission on the SharePoint site.</span></span> <span data-ttu-id="27922-106">Weitere Informationen finden Sie unter [Beispiele für URLs von veröffentlichten Berichtselementen auf einem Berichtsserver im SharePoint-Modus &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="27922-106">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-shared-data-source-to-a-sharepoint-site"></a><span data-ttu-id="27922-107">So veröffentlichen Sie eine freigegebene Datenquelle auf einer SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="27922-107">To publish a shared data source to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="27922-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das vorhandene bzw. ein neues Berichtsserverprojekt.</span><span class="sxs-lookup"><span data-stu-id="27922-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open your existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="27922-109">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="27922-109">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="27922-110">Das _\<project>_ Dialogfeld **Eigenschaften Seiten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="27922-110">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="27922-111">Wählen Sie die **Konfiguration** aus, die Sie zum Veröffentlichen auf einer SharePoint-Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="27922-111">Choose the **Configuration** you use to publish to a SharePoint site.</span></span>  
  
4.  <span data-ttu-id="27922-112">Wenn Sie die freigegebenen Datenquellen in Ihrem Projekt veröffentlichen und bereits veröffentlichte freigegebene Datenquellen überschreiben möchten, legen Sie **OverwriteDataSources** auf **True**fest.</span><span class="sxs-lookup"><span data-stu-id="27922-112">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="27922-113">(Optional) Geben Sie für **TargetDataSourceFolder**eine URL zu einer SharePoint-Bibliothek oder zu einem Bibliotheksordner ein.</span><span class="sxs-lookup"><span data-stu-id="27922-113">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder.</span></span> <span data-ttu-id="27922-114">Beispiel: *http://TestServer/TestSite/Documents/DataSources*</span><span class="sxs-lookup"><span data-stu-id="27922-114">For example, *http://TestServer/TestSite/Documents/DataSources*.</span></span>  
  
     <span data-ttu-id="27922-115">Wenn Sie keinen Wert angeben, wird der Wert **TargetReportFolder** verwendet.</span><span class="sxs-lookup"><span data-stu-id="27922-115">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="27922-116">Geben Sie für **TargetReportFolder**eine URL zu einer Bibliothek oder einem Bibliotheksordner ein.</span><span class="sxs-lookup"><span data-stu-id="27922-116">For **TargetReportFolder**, type a URL to a library or library folder.</span></span> <span data-ttu-id="27922-117">Beispiel: http:*//TestServer/TestSite/Documents/Reports*.</span><span class="sxs-lookup"><span data-stu-id="27922-117">For example, http:*//TestServer/TestSite/Documents/Reports*.</span></span>  
  
7.  <span data-ttu-id="27922-118">Geben Sie für **TargetServerURL**eine URL zu einer SharePoint-Website auf oberster Ebene oder zu einer Unterwebsite ein.</span><span class="sxs-lookup"><span data-stu-id="27922-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="27922-119">Wenn Sie keine Website angeben, wird die standardmäßige Stammwebsite verwendet.</span><span class="sxs-lookup"><span data-stu-id="27922-119">If you do not specify a site, the default top-level site is used.</span></span> <span data-ttu-id="27922-120">Beispielsweise http://*Servername*, http://*Servername*/*Website*oder http://*servername*/*Website*/*Unterseite*.</span><span class="sxs-lookup"><span data-stu-id="27922-120">For example, http://*servername*, http://*servername*/*site*, or http://*servername*/*site*/*subsite*.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="27922-121">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die zu veröffentlichende freigegebene Datenquelle, und klicken Sie anschließend auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="27922-121">In Solution Explorer, right-click the shared data source you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="27922-122">Die Datenquelle wird an dem in **TargetDataSourceFolder**angegebenen Speicherort veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="27922-122">The data source is published to the location specified in **TargetDataSourceFolder**.</span></span> <span data-ttu-id="27922-123">Im Ausgabefenster werden Bereitstellungsfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27922-123">Deployment errors appear in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27922-124">Nachdem Sie eine freigegebene Datenquelle auf einer SharePoint-Website veröffentlicht haben, wird die Dateinamenerweiterung in RSDS geändert.</span><span class="sxs-lookup"><span data-stu-id="27922-124">After you publish a shared data source to a SharePoint site, the file name extension is changed to .rsds.</span></span> <span data-ttu-id="27922-125">Sie können eine freigegebene Datenquelle direkt auf der SharePoint-Website bearbeiten und verwalten.</span><span class="sxs-lookup"><span data-stu-id="27922-125">You can edit and manage a shared data source directly on the SharePoint site.</span></span> <span data-ttu-id="27922-126">Weitere Informationen finden Sie unter [Erstellen und Verwalten von freigegebenen Datenquellen (Reporting Services im integrierten SharePoint-Modus)](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="27922-126">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27922-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27922-127">See Also</span></span>  
 <span data-ttu-id="27922-128">[Veröffentlichen eines Berichts in einer SharePoint-Bibliothek](publish-a-report-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="27922-128">[Publish a Report to a SharePoint Library](publish-a-report-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="27922-129">[URL-Beispiele für veröffentlichte Berichts Elemente auf einem Berichts Server im SharePoint-Modus &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="27922-129">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="27922-130">[Eigenschaften Seiten für Projekt (Dialog Feld)](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="27922-130">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="27922-131">[Festlegen der Bereitstellungs Eigenschaften &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="27922-131">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="27922-132">[Veröffentlichen von Berichten auf einem Berichts Server](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="27922-132">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 [<span data-ttu-id="27922-133">Verwenden einer Office Data Connection &#40;.odc&#41; für Berichte &#40;Reporting Services im integrierten SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="27922-133">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
