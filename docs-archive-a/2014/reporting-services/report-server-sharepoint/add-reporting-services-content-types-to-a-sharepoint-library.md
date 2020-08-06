---
title: Hinzufügen des Berichts-Viewer-Webparts zu einer Webseite (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
ms.assetid: cac75345-2380-467d-a394-0a2140908a5a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d9b933fad8bc566b3cb0ef04303a85c5f034e620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721103"
---
# <a name="add-the-report-viewer-web-part-to-a-web-page-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="acf20-102">Hinzufügen des Berichts-Viewer-Webparts zu einer Webseite (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="acf20-102">Add the Report Viewer Web Part to a Web Page (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="acf20-103">Mithilfe des Berichts-Viewer-Webparts können Sie Berichte anzeigen, die auf einem Berichtsserver ausgeführt werden, der für die Ausführung im integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="acf20-103">You can use the Report Viewer Web Part to view reports that run on report server that is configured to run in SharePoint integrated mode.</span></span> <span data-ttu-id="acf20-104">Mithilfe des Webparts können im Berichts-Generator oder Berichts-Designer erstellte und in eine Bibliothek hochgeladene Berichtsdefinitionsdateien (RDL) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="acf20-104">You can use the Web Part to display report definition (.rdl) files that you created in Report Builder or Report Designer and uploaded to a library.</span></span>  
  
 <span data-ttu-id="acf20-105">Sie können das Berichts-Viewer-Webpart einer Webseite hinzufügen, wenn Sie einen Bericht in diese Seite einbetten möchten.</span><span class="sxs-lookup"><span data-stu-id="acf20-105">You can add the Report Viewer Web Part to a Web page if you want to embed a report on that page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="acf20-106">Obwohl ihre Namen identisch sind, unterscheidet sich das über das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Add-In installierte Berichts-Viewer-Webpart von dem in der Datei RSWebParts.cab enthaltenen Berichts-Viewer-Webpart.</span><span class="sxs-lookup"><span data-stu-id="acf20-106">Although they have identical names, the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in is different from the Report Viewer Web Part that is included in the RSWebParts.cab file.</span></span> <span data-ttu-id="acf20-107">Die Anleitungen in diesem Thema sind speziell für den Berichts-Viewer-Webpart gedacht, der durch das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Add-In installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="acf20-107">The instructions in this topic are specifically for the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
 <span data-ttu-id="acf20-108">Sie müssen über die Berechtigung zum Hinzufügen und Anpassen von Seiten auf Websiteebene verfügen, um einer Webseite ein Webpart hinzufügen zu können.</span><span class="sxs-lookup"><span data-stu-id="acf20-108">To add a Web Part to a Web page, you must have the Add and Customize Pages permission at the site level.</span></span> <span data-ttu-id="acf20-109">Wenn Sie Standardsicherheitseinstellungen verwenden, wird diese Berechtigung Mitgliedern der Gruppe **Besitzer** erteilt, die über Berechtigungen für den Vollzugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="acf20-109">If you are using default security settings, this permission is granted to members of the **Owners** group who have the Full Control level of permission.</span></span>  
  
### <a name="to-embed-a-report-in-a-web-page"></a><span data-ttu-id="acf20-110">So betten Sie einen Bericht in eine Webseite ein</span><span class="sxs-lookup"><span data-stu-id="acf20-110">To embed a report in a Web page</span></span>  
  
1.  <span data-ttu-id="acf20-111">Öffnen oder erstellen Sie eine Webpartseite oder ein Dashboard.</span><span class="sxs-lookup"><span data-stu-id="acf20-111">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="acf20-112">Klicken Sie unter **Websiteaktionen**auf **Seite bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="acf20-112">On **Site Actions**, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="acf20-113">Klicken Sie auf **Webpart hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="acf20-113">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="acf20-114">Wählen Sie in der Liste der Webpartkategorien die Kategorie **Sonstiges** aus, und wählen Sie dann **Berichts-Viewer für SQL Server Reporting Services**aus.</span><span class="sxs-lookup"><span data-stu-id="acf20-114">In the list of web part categories, select the **Miscellaneous** category, and then select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="acf20-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="acf20-115">Click **Add**.</span></span> <span data-ttu-id="acf20-116">Der Webpart wird oben in der Zone hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="acf20-116">The Web Part is added at the top of the zone.</span></span> <span data-ttu-id="acf20-117">Sie können ihn an eine andere Stelle in der Zone ziehen.</span><span class="sxs-lookup"><span data-stu-id="acf20-117">You can drag it to a different location in the zone.</span></span>  
  
6.  <span data-ttu-id="acf20-118">Klicken Sie innerhalb des Viewers auf **Hier klicken, um den Toolbereich zu öffnen**.</span><span class="sxs-lookup"><span data-stu-id="acf20-118">Within the viewer, click **Click here to open the tool pane**.</span></span>  
  
7.  <span data-ttu-id="acf20-119">Wählen Sie einen Bericht aus einer Bibliothek in der aktuellen Websitesammlung aus, indem Sie auf die Schaltfläche zum Durchsuchen (**...**) klicken.</span><span class="sxs-lookup"><span data-stu-id="acf20-119">Select a report from any library in the current site collection by clicking the browse (**...**) button.</span></span> <span data-ttu-id="acf20-120">Sie können auch die Berichts-URL eingeben.</span><span class="sxs-lookup"><span data-stu-id="acf20-120">You can also type the report URL.</span></span> <span data-ttu-id="acf20-121">Wenn Sie die URL für einen Bericht bestimmen möchten, klicken Sie mit der rechten Maustaste auf den Bericht, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="acf20-121">To determine the URL for any report, right-click the report and select **Properties**.</span></span> <span data-ttu-id="acf20-122">Klicken Sie nicht auf den Pfeil nach unten neben dem Bericht. Die Berichts-URL wird auf der Seite Eigenschaften anzeigen des Elements nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acf20-122">Do not click the down arrow next to the report; the report URL is not indicated in the View Properties page of the item.</span></span> <span data-ttu-id="acf20-123">Wenn Sie die URL aus dem Dialogfeld **Eigenschaften** kopieren und einfügen, müssen Sie die URL-Codierung "%20" durch ein Leerzeichen ersetzen ("Company%20Sales" sollte z. B. "Company Sales" lauten).</span><span class="sxs-lookup"><span data-stu-id="acf20-123">If you copy and paste the URL from the **Properties** dialog box, replace the "%20" URL encoding with a space (for example, "Company%20Sales" should be "Company Sales").</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acf20-124">In jedem Berichts-Viewer-Webpart ist ein einzelner Bericht enthalten.</span><span class="sxs-lookup"><span data-stu-id="acf20-124">Each Report Viewer Web Part contains a single report.</span></span> <span data-ttu-id="acf20-125">Die URL muss der vollqualifizierte Pfad zu einem Bericht sein, der sich auf der aktuellen SharePoint-Website oder auf einer Website innerhalb derselben Webanwendung oder Webfarm befindet.</span><span class="sxs-lookup"><span data-stu-id="acf20-125">The URL must be the fully qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="acf20-126">Die URL muss in eine Dokumentbibliothek oder in einen Ordner innerhalb einer Dokumentbibliothek mit dem Bericht aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="acf20-126">The URL must resolve to a document library or to a folder within a document library that contains the report.</span></span> <span data-ttu-id="acf20-127">Die Berichts-URL muss die Dateierweiterung RDL enthalten.</span><span class="sxs-lookup"><span data-stu-id="acf20-127">The report URL must include the .rdl file extension.</span></span> <span data-ttu-id="acf20-128">Wenn der Bericht von einem Modell oder freigegebenen Datenquellendateien abhängt, müssen Sie diese Dateien nicht in der URL angeben.</span><span class="sxs-lookup"><span data-stu-id="acf20-128">If the report depends on a model or shared data source files, you do not need to specify those files in the URL.</span></span> <span data-ttu-id="acf20-129">Der Bericht enthält Verweise auf die erforderlichen Dateien.</span><span class="sxs-lookup"><span data-stu-id="acf20-129">The report contains references to the files it needs.</span></span>  
  
8.  <span data-ttu-id="acf20-130">Während der Toolbereich geöffnet ist, können Sie Eigenschaften festlegen, um die Standarddarstellung und das Layout zu ändern.</span><span class="sxs-lookup"><span data-stu-id="acf20-130">While the tool pane is open, you can set properties to modify the default appearance and layout.</span></span>  
  
9. <span data-ttu-id="acf20-131">Klicken Sie unten im Toolbereich auf **Anwenden** , und klicken Sie anschließend auf **OK** , um den Bereich zu schließen.</span><span class="sxs-lookup"><span data-stu-id="acf20-131">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf20-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="acf20-132">See Also</span></span>  
 <span data-ttu-id="acf20-133">[Berichts-Viewer-Webpart auf einer SharePoint-Website](../report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="acf20-133">[Report Viewer Web Part on a SharePoint Site](../report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 <span data-ttu-id="acf20-134">[Anpassen des Berichts-Viewer-Webparts](../customize-the-report-viewer-web-part.md) </span><span class="sxs-lookup"><span data-stu-id="acf20-134">[Customize the Report Viewer Web Part](../customize-the-report-viewer-web-part.md) </span></span>  
 <span data-ttu-id="acf20-135">[Erteilen von Berechtigungen für Berichts Server Elemente auf einer SharePoint-Website](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="acf20-135">[Granting Permissions on Report Server Items on a SharePoint Site](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="acf20-136">Installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="acf20-136">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](../install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
