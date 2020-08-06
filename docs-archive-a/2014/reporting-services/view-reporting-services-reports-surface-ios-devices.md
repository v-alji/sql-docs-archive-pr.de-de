---
title: Anzeigen von Reporting Services-Berichten auf Microsoft Surface-Geräten und Apple IOS-Geräten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- iPad
- Safari
- SSRS
- Report Viewer [Reporting Services]
- iOS
ms.assetid: 2124bcf5-d60a-475f-a4ae-de6df44d2860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db52ed500559969ae52eb9477caa6b410889c1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620204"
---
# <a name="view-reporting-services-reports-on-microsoft-surface-devices-and--apple-ios-devices"></a><span data-ttu-id="85da6-102">Anzeigen von Reporting Services-Berichten auf Microsoft Surface-Geräten und Apple iOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="85da6-102">View Reporting Services Reports on Microsoft Surface Devices and  Apple iOS Devices</span></span>
  <span data-ttu-id="85da6-103">In diesem Artikel werden die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen und -Workflows beschrieben, die für Microsoft Surface-Geräte sowie für Geräte mit Apple iOS 6 und Apple Safari (z. B. iPad) unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="85da6-103">This article describes the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features and workflows supported for Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari such as the iPad.</span></span>

## <a name="view-and-interact-with-reports"></a><span data-ttu-id="85da6-104">Anzeigen und Interagieren mit Berichten</span><span class="sxs-lookup"><span data-stu-id="85da6-104">View and Interact With Reports</span></span>
 <span data-ttu-id="85da6-105">Ab [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]unterstützt [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] die Anzeige und grundlegende interaktive Berichtsfunktionen auf Microsoft Surface-Geräten sowie Geräten mit Apple iOS 6 und dem Apple Safari-Browser (z. B. iPad).</span><span class="sxs-lookup"><span data-stu-id="85da6-105">Starting with [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supports viewing and basic interactivity with reports on Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari browser such as the iPad.</span></span> <span data-ttu-id="85da6-106">Sie können Berichte auch mit Microsoft Surface-Geräten veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="85da6-106">You can also publish reports using Microsoft Surface devices.</span></span>

 <span data-ttu-id="85da6-107">![IPad-Desktop](media/videothumbnail.jpg "IPad-Desktop") Sehen Sie sich eine Demonstration der Anzeige von Berichten auf einem iPad an.</span><span class="sxs-lookup"><span data-stu-id="85da6-107">![IPad Desktop](media/videothumbnail.jpg "IPad Desktop") Watch a demonstration of viewing reports on an iPad.</span></span>

 <span data-ttu-id="85da6-108">Sie können [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichte auch auf einem Windows Phone 8-Gerät anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85da6-108">You can also view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports on a Windows Phone 8 device.</span></span>

 <span data-ttu-id="85da6-109">Um die in diesem Thema beschriebenen Funktionen zu nutzen, installieren Sie eine der folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="85da6-109">To utilize the features described in this topic, install one of the following:</span></span>

-   <span data-ttu-id="85da6-110">Berichtsserver im einheitlichen Modus: Installieren Sie [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] oder höher.</span><span class="sxs-lookup"><span data-stu-id="85da6-110">For a native mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later.</span></span>

     [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]<span data-ttu-id="85da6-111">steht im [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575)zum Download zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85da6-111">is available for download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575).</span></span>

-   <span data-ttu-id="85da6-112">Berichtsserver im SharePoint-Modus: Installieren Sie [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] oder höher aus dem [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In für SharePoint-Produkte.</span><span class="sxs-lookup"><span data-stu-id="85da6-112">For a SharePoint mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>

 <span data-ttu-id="85da6-113">**So können Sie einen Bericht auf einem iPad oder Microsoft Surface-Gerät anzeigen und damit interagieren**</span><span class="sxs-lookup"><span data-stu-id="85da6-113">**To view and interact with a report on an iPad device or Microsoft Surface device**</span></span>

1.  <span data-ttu-id="85da6-114">Stellen Sie sicher, dass Sie mit dem Berichtsserver oder der SharePoint-Website, auf dem bzw. der sich der Bericht befindet, eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="85da6-114">Make sure that you can connect to the report server or SharePoint site where the report resides.</span></span>

2.  <span data-ttu-id="85da6-115">Öffnen Sie den Bericht, indem Sie einen der folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="85da6-115">Open the report by doing one of the following.</span></span>

    -   <span data-ttu-id="85da6-116">**Starten von einer E-Mail aus:** Tippen Sie in einer E-Mail, die von einem [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Abonnement erstellt wurde, auf die URL des Berichts.</span><span class="sxs-lookup"><span data-stu-id="85da6-116">**Start from e-mail:** From an e-mail that is created by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] subscription, tap the URL of the report.</span></span> <span data-ttu-id="85da6-117">Der Bericht wird im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="85da6-117">The report will open in the browser.</span></span>

    -   <span data-ttu-id="85da6-118">**Starten vom Berichtsserver:** Durchsuchen Sie das Verzeichnis auf dem [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver, und tippen Sie auf den Berichtsnamen, um den Bericht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="85da6-118">**Start from Report Server:** Browse the directory on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server, and then tap the report name to open the report.</span></span>

    -   <span data-ttu-id="85da6-119">**Starten von einer SharePoint-Dokumentbibliothek:** Navigieren Sie zu einer SharePoint-Dokumentbibliothek, die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichte enthält, und tippen Sie dann auf den Berichtsnamen.</span><span class="sxs-lookup"><span data-stu-id="85da6-119">**Start from a SharePoint document library:** Browse to a SharePoint document library that contains [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports, and then tap the report name.</span></span> <span data-ttu-id="85da6-120">Sie können den Bericht anzeigen und damit interagieren.</span><span class="sxs-lookup"><span data-stu-id="85da6-120">You can view and interact with the report.</span></span>

        > [!IMPORTANT]
        >  <span data-ttu-id="85da6-121">Achten Sie bei einem iPad darauf, dass die Eigenschaft **Privates Surfen** für Safari deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="85da6-121">For the iPad, ensure that the **Private Browsing** property for Safari is turned off.</span></span>

    -   <span data-ttu-id="85da6-122">**SharePoint-Webpart:** Wenn das Webpart einer SharePoint-Seite hinzugefügt wurde, können Sie [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85da6-122">**SharePoint web part:** If the web part has been added to a SharePoint page, you can view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports.</span></span>

3.  <span data-ttu-id="85da6-123">Auf Ihrem Microsoft Surface-Gerät können Sie den Bericht auch mithilfe des Berichts-Managers öffnen.</span><span class="sxs-lookup"><span data-stu-id="85da6-123">On your Microsoft Surface device, you can also open the report by using Report Manager.</span></span> <span data-ttu-id="85da6-124">Durchsuchen Sie das Verzeichnis im [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichts-Manager, und tippen Sie auf den Berichtsnamen, um den Bericht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="85da6-124">Browse the directory in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager, and then tap the report name to open the report.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="85da6-125">Das Anzeigen von Berichten im Berichts-Manager wird auf iPads nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85da6-125">Viewing reports in Report Manager is not supported on an iPad.</span></span>

4.  <span data-ttu-id="85da6-126">Zum Durchführen eines Bildlaufs und Zoomen verfahren Sie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85da6-126">Scroll and zoom by doing the following.</span></span>

    -   <span data-ttu-id="85da6-127">Um einen Bildlauf im Bericht durchzuführen, fahren Sie mit dem Finger (nach oben, unten, links oder rechts) über den Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="85da6-127">To scroll the report, drag your finger across the screen (up, down, left or right).</span></span> <span data-ttu-id="85da6-128">Diese Bewegung wird als "Streifen" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="85da6-128">This is the swipe gesture.</span></span>

    -   <span data-ttu-id="85da6-129">Zum Vergrößern positionieren Sie zwei Finger auf dem Bildschirm und bewegen die Finger voneinander weg.</span><span class="sxs-lookup"><span data-stu-id="85da6-129">To zoom in, place two fingers on the screen and separate the fingers.</span></span> <span data-ttu-id="85da6-130">Zum Verkleinern, positionieren Sie zwei Finger auf dem Bildschirm und bewegen die Finger aufeinander zu.</span><span class="sxs-lookup"><span data-stu-id="85da6-130">To zoom out, place two fingers on the screen and move the fingers together.</span></span> <span data-ttu-id="85da6-131">Diese Bewegung wird als "Zusammendrücken" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="85da6-131">This is the pinch gesture.</span></span>

5.  <span data-ttu-id="85da6-132">Um im Bericht zu navigieren und damit zu interagieren, verfahren Sie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85da6-132">Navigate and interact with the report by doing the following.</span></span>

    -   <span data-ttu-id="85da6-133">Um Berichtselemente sowie Zeilen und Spalten, die Gruppen zugeordnet sind, zu reduzieren und zu erweitern, tippen Sie zum Reduzieren auf das Pluszeichen (+) und zum Erweitern auf das Minuszeichen (-).</span><span class="sxs-lookup"><span data-stu-id="85da6-133">Collapse and expand report items, and rows and columns that are associated with groups, by taping the plus (+) sign to collapse and the minus (-) sign to expand.</span></span>

    -   <span data-ttu-id="85da6-134">Um Zeilen in einer Tabelle oder Zeilen und Spalten in einer Matrix aufsteigend oder absteigend zu sortieren, tippen Sie auf die Sortierschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="85da6-134">Toggle between ascending and descending order for rows in a table or for rows and columns in a matrix, by tapping the sort button.</span></span> <span data-ttu-id="85da6-135">Die Sortierschaltfläche befindet sich normalerweise in der Spaltenüberschrift.</span><span class="sxs-lookup"><span data-stu-id="85da6-135">The sort button is usually located in the column header.</span></span>

    -   <span data-ttu-id="85da6-136">Um den Parameterbereich zu erweitern und zu reduzieren, tippen Sie auf die Pfeilschaltfläche am oberen Rand des Berichts.</span><span class="sxs-lookup"><span data-stu-id="85da6-136">Expand and collapse the parameter pane, by tapping the arrow button near the top of the report.</span></span>

    -   <span data-ttu-id="85da6-137">Wählen Sie einen Parameterwert aus, indem Sie auf das Feld oder Steuerelement neben dem Parameter tippen.</span><span class="sxs-lookup"><span data-stu-id="85da6-137">Select a parameter value by tapping the box or control next to the parameter.</span></span> <span data-ttu-id="85da6-138">Tippen Sie auf **Bericht anzeigen** , um den Parameterwert auf den Bericht anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="85da6-138">Tap **View Report** to apply the parameter value to the report.</span></span>

    -   <span data-ttu-id="85da6-139">Um den Berichtsinhalt zu durchsuchen, tippen Sie auf das Feld neben **Suchen**, geben einen Suchbegriff ein und tippen dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="85da6-139">Search the report content by taping the box next to **Find**, typing a search term, and then taping **Find**.</span></span>

    -   <span data-ttu-id="85da6-140">Um durch die Berichtsseiten zu blättern, tippen Sie auf die Navigationsschaltflächen. Alternativ können Sie auf das Textfeld neben den Schaltflächen tippen und die Seitenzahl eingeben.</span><span class="sxs-lookup"><span data-stu-id="85da6-140">Navigate the report pages by tapping the navigation buttons, or tapping the text box next to the buttons and typing the page number.</span></span>

    -   <span data-ttu-id="85da6-141">Um zu URLs zu navigieren, tippen Sie auf die Hyperlinks, die Berichtselementen, z. B. Textfeldern, Bildern, Diagrammen und Messgeräten, hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="85da6-141">Navigate to URLs by taping hyperlinks that have been added to report items such as text boxes, images, charts, and gauges.</span></span>

    -   <span data-ttu-id="85da6-142">Exportieren Sie den Bericht, indem Sie auf das Symbol für das **Dropdownmenü "Exportieren"** und dann auf ein Dateiformat tippen.</span><span class="sxs-lookup"><span data-stu-id="85da6-142">Export the report by tapping the icon for the **Export drop down menu** and then tapping a file format.</span></span>

        -   <span data-ttu-id="85da6-143">Wenn Sie den Bericht auf einem Microsoft Surface-Gerät anzeigen, können Sie den Bericht in eines der folgenden Formate exportieren.</span><span class="sxs-lookup"><span data-stu-id="85da6-143">If you're viewing the report on a Microsoft Surface device, you can export the report to one of the following formats.</span></span>

            -   <span data-ttu-id="85da6-144">XML-Datei mit Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="85da6-144">XML file with report data</span></span>

            -   <span data-ttu-id="85da6-145">CSV (durch Trennzeichen getrennt)</span><span class="sxs-lookup"><span data-stu-id="85da6-145">CSV (comma delimited)</span></span>

            -   <span data-ttu-id="85da6-146">PDF</span><span class="sxs-lookup"><span data-stu-id="85da6-146">PDF</span></span>

            -   <span data-ttu-id="85da6-147">MHTML (Webarchiv)</span><span class="sxs-lookup"><span data-stu-id="85da6-147">MHTML (web archive)</span></span>

            -   <span data-ttu-id="85da6-148">Excel</span><span class="sxs-lookup"><span data-stu-id="85da6-148">Excel</span></span>

            -   <span data-ttu-id="85da6-149">TIFF</span><span class="sxs-lookup"><span data-stu-id="85da6-149">TIFF</span></span>

            -   <span data-ttu-id="85da6-150">Word</span><span class="sxs-lookup"><span data-stu-id="85da6-150">Word</span></span>

        -   <span data-ttu-id="85da6-151">Wenn Sie den Bericht auf einem iPad anzeigen, können Sie den Bericht als TIFF-oder PDF-Datei exportieren.</span><span class="sxs-lookup"><span data-stu-id="85da6-151">If you're viewing the report on an iPad, you can export the report as a TIFF or PDF file.</span></span>

## <a name="authentication"></a><span data-ttu-id="85da6-152">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="85da6-152">Authentication</span></span>
 <span data-ttu-id="85da6-153">Die RSWindowsNTLM-Authentifizierung und die RSWindowsBasic-Authentifizierung können mit [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] im einheitlichen Modus auf dem iPad verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85da6-153">RSWindowsNTLM authentication and RSWindowsBasic authentication work with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode and the iPad.</span></span>

 <span data-ttu-id="85da6-154">Im Allgemeinen wird davon abgeraten, RSWindowsBasic in Nicht-HTTPS-Umgebungen zu verwenden, da dieser Authentifizierungstyp keine Vertrauenswürdigkeit für übermittelte Anmeldeinformationen bietet.</span><span class="sxs-lookup"><span data-stu-id="85da6-154">In general, it is recommended that RSWindowsBasic is not used in non-https environments because this type of authentication provides no confidentiality for the transmitted credentials.</span></span>

 <span data-ttu-id="85da6-155">Weitere Informationen zur RSWindowsNTLM- und RSWindowsBasic-Authentifizierung finden Sie unter [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="85da6-155">For more information about RSWindowsNTLM and RSWindowsBasic authentication, see [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span></span>

## <a name="uploading-reports"></a><span data-ttu-id="85da6-156">Hochladen von Berichten</span><span class="sxs-lookup"><span data-stu-id="85da6-156">Uploading Reports</span></span>
 <span data-ttu-id="85da6-157">Mit den entsprechenden Berechtigungen können Sie Berichte mithilfe der folgenden Methoden über ein Microsoft Surface-Gerät veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="85da6-157">You can publish reports from a Microsoft Surface device using one of the following methods, if you have the appropriate permissions.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="85da6-158">Auf dem iPad werden diese Methoden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85da6-158">These methods are not supported on the iPad.</span></span>

-   <span data-ttu-id="85da6-159">Hochladen einer Berichtsdefinitionsdatei (RDL) in eine SharePoint-Dokumentbibliothek, indem Sie die Bibliothek öffnen und auf **Dokument hochladen**tippen.</span><span class="sxs-lookup"><span data-stu-id="85da6-159">Upload a report definition file (.rdl) to a SharePoint document library by opening the library and tapping **Upload Document**.</span></span>

-   <span data-ttu-id="85da6-160">Hochladen einer Berichtsdefinitionsdatei in die Berichtsserver-Datenbank, indem Sie den Berichts-Manager öffnen und auf **Datei hochladen**tippen.</span><span class="sxs-lookup"><span data-stu-id="85da6-160">Upload a report definition file to the report server database by opening Report Manager and tapping **Upload File**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="85da6-161">Zusätzliche Informationen</span><span class="sxs-lookup"><span data-stu-id="85da6-161">Additional Information</span></span>
 <span data-ttu-id="85da6-162">Weitere Informationen zu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] und unterstützten Browsern finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="85da6-162">For more information on [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and supported browsers, see:</span></span>

-   [<span data-ttu-id="85da6-163">Planen der Reporting Services-und Power View Browser Unterstützung &#40;Reporting Services 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="85da6-163">Planning for Reporting Services and Power View Browser Support &#40;Reporting Services 2014&#41;</span></span>](../../2014/reporting-services/browser-support-for-reporting-services-and-power-view.md)

 <span data-ttu-id="85da6-164">Weitere Informationen zu Microsoft Business Intelligence und mobilen Geräten finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="85da6-164">For more information on Microsoft Business Intelligence and Mobile devices, see the following:</span></span>

-   <span data-ttu-id="85da6-165">[Übersicht über mobile Geräte und SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161351(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="85da6-165">[Overview of mobile devices and SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161351(v=office.15).aspx).</span></span>

-   <span data-ttu-id="85da6-166">[Unterstützte Browser für mobile Geräte in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161353(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="85da6-166">[Supported mobile device browsers in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161353(v=office.15).aspx).</span></span>

-   <span data-ttu-id="85da6-167">[Anzeigen von Berichten und Scorecards auf Apple iPad-Geräten (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) ( https://technet.microsoft.com/library/hh697482.aspx) .</span><span class="sxs-lookup"><span data-stu-id="85da6-167">[Viewing reports and scorecards on Apple iPad devices (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) (https://technet.microsoft.com/library/hh697482.aspx).</span></span>

-   <span data-ttu-id="85da6-168">[Anzeigen Reporting Services Berichte auf einem iPad (Video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) ( https://technet.microsoft.com/sqlserver/jj873792.aspx) .</span><span class="sxs-lookup"><span data-stu-id="85da6-168">[Viewing Reporting Services Reports on an iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) (https://technet.microsoft.com/sqlserver/jj873792.aspx).</span></span>

-   [<span data-ttu-id="85da6-169">Anzeigen von Reporting Services-Berichten auf einem Microsoft Surface RT-Gerät (Video)</span><span class="sxs-lookup"><span data-stu-id="85da6-169">Viewing Reporting Services Reports on a Microsoft Surface RT Device (video)</span></span>](https://technet.microsoft.com/sqlserver/dn146017)


