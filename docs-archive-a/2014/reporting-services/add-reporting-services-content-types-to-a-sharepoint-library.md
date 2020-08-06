---
title: Hinzufügen von Berichts Server-Inhaltstypen zu einer Bibliothek (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ac9136c8-9ef4-484c-8e9d-05008a186db5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e0ee56c235a54920fba5389a61f300eeaa65329
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723633"
---
# <a name="add-report-server-content-types-to-a-library-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="76108-102">Hinzufügen von Berichtsserver-Inhaltstypen zu einer Bibliothek (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="76108-102">Add Report Server Content Types to a Library (Reporting Services in SharePoint Integrated Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="76108-103">Für SharePoint werden vordefinierte Inhaltstypen bereitgestellt, die zum Verwalten freigegebener Datenquellendateien (RSDS), Berichtsmodelldateien (SMDL) und Berichtsgenerator-Berichtsdefinitionsdateien (RDL) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="76108-103">provides predefined SharePoint content types that are used to manage shared data source (.rsds) files, report models (.smdl), and Report Builder report definition (.rdl) files.</span></span> <span data-ttu-id="76108-104">Wenn einer Bibliothek ein Inhaltstyp ( **Berichts-Generator-Bericht**, **Berichtsmodell**und **Berichtsdatenquelle** ) hinzugefügt wird, wird der Befehl **Neu** aktiviert, sodass Sie neue Dokumente des betreffenden Typs erstellen können.</span><span class="sxs-lookup"><span data-stu-id="76108-104">Adding a **Report Builder Report**, **Report Model**, and **Report Data Source** content type to a library enables the **New** command so that you can create new documents of that type.</span></span>  
  
 <span data-ttu-id="76108-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="76108-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>  
  
 <span data-ttu-id="76108-106">Wenn Sie einer Bibliothek Inhaltstypen hinzufügen möchten, müssen Sie Websiteadministrator sein oder über die Berechtigungsstufe "Vollzugriff" verfügen.</span><span class="sxs-lookup"><span data-stu-id="76108-106">To add content types to a library, you must be a site administrator or have Full Control level of permission.</span></span>  
  
 <span data-ttu-id="76108-107">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstypen sowie die Verwaltung dieser Inhaltstypen werden in allen Dokumentbibliotheken für vorhandene Websitesammlungen, die von folgenden **Business Intelligence Center** -Websitevorlagen erstellt wurden, automatisch aktiviert:</span><span class="sxs-lookup"><span data-stu-id="76108-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types and content type management will automatically be enabled in all document libraries for existing site collections created from the following **Business Intelligence Center** site template.</span></span>  
  
 <span data-ttu-id="76108-108">Für Websites, die nach der Integration von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] erstellt wurden, sind die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstypen nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="76108-108">Sites created after the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration will not have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types enabled.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="76108-109">Wenn Sie zuvor **keine** Inhaltstypen für eine Bibliothek konfiguriert haben, aktivieren Sie zunächst die Verwaltung von Inhaltstypen und dann die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstypen.</span><span class="sxs-lookup"><span data-stu-id="76108-109">If you have **not** previously configured content types for a library, first enable management of content types, then enable the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="76108-110">Siehe die Verfahren zum Aktivieren der Inhaltstypverwaltung in einer einzelnen Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="76108-110">See the procedures on enabling content type management in a single document library.</span></span>  
  
 <span data-ttu-id="76108-111">**Kurzvideo:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w) ((SSRS) Aktivieren von Inhaltstypen in SharePoint2010.wmv).</span><span class="sxs-lookup"><span data-stu-id="76108-111">**Short video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span></span>  
  
 <span data-ttu-id="76108-112">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="76108-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="76108-113">Aktivieren von Inhaltstypen in allen Dokumentbibliotheken eines vorhandenen Business Intelligence Centers</span><span class="sxs-lookup"><span data-stu-id="76108-113">Enable content types in all document libraries in an existing BI center</span></span>](#bkmk_enable_all)  
  
-   [<span data-ttu-id="76108-114">So aktivieren Sie die Inhaltstypverwaltung für eine einzelne Dokumentbibliothek (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="76108-114">To enable content type management for a single document library (SharePoint 2013)</span></span>](#bkmk_enable_content_management)  
  
-   [<span data-ttu-id="76108-115">So fügen Sie Reporting Services-Inhaltstypen hinzu (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="76108-115">To add Reporting Services content types (SharePoint 2013)</span></span>](#bkmk_add_single)  
  
-   [<span data-ttu-id="76108-116">So aktivieren Sie die Inhaltstypverwaltung für eine einzelne Dokumentbibliothek (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="76108-116">To enable content type management for a single document library (SharePoint 2010)</span></span>](#bkmk_enable_content_management_2010)  
  
-   [<span data-ttu-id="76108-117">So fügen Sie Berichtsserver-Inhaltstypen hinzu (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="76108-117">To add report server content types (SharePoint 2010)</span></span>](#bkmk_add_single_2010)  
  
-   [<span data-ttu-id="76108-118">So aktivieren Sie Inhaltstypen und die Inhaltsverwaltung für mehrere BI-Websites</span><span class="sxs-lookup"><span data-stu-id="76108-118">To enable Content types and content management for multiple BI sites</span></span>](#bkmk_enable_multiple_sites)  
  
##  <a name="enable-content-types-in-all-document-libraries-in-an-existing-bi-center"></a><a name="bkmk_enable_all"></a><span data-ttu-id="76108-119">Aktivieren von Inhaltstypen in allen Dokument Bibliotheken eines vorhandenen BI Centers</span><span class="sxs-lookup"><span data-stu-id="76108-119">Enable content types in all document libraries in an existing BI center</span></span>  
  
1.  <span data-ttu-id="76108-120">Um Inhaltstypen sowie die Inhaltsverwaltung in allen Dokumentbibliotheken einer vorhandenen **Business Intelligence Center** -Website zu aktivieren, können Sie die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Integrationsfunktion aktivieren/deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="76108-120">To enable the content types and content management in all document libraries in an existing **Business Intelligence Center** site, you can toggle the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration feature.</span></span>  
  
2.  <span data-ttu-id="76108-121">Wechseln Sie zu **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-121">Go to **Site settings**.</span></span>  
  
    -   <span data-ttu-id="76108-122">Klicken Sie in SharePoint 2013 auf das **Einstellungssymbol**.</span><span class="sxs-lookup"><span data-stu-id="76108-122">In SharePoint 2013, click the **Settings** icon.</span></span> <span data-ttu-id="76108-123">![SharePoint-Einstellungen](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint-Einstellungen")</span><span class="sxs-lookup"><span data-stu-id="76108-123">![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings")</span></span>  
  
    -   <span data-ttu-id="76108-124">Klicken Sie in SharePoint 2010 auf **Websiteaktionen**und auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-124">In SharePoint 2010, click **Site Actions**, then click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="76108-125">Klicken Sie auf **Website Sammlungs Features**.</span><span class="sxs-lookup"><span data-stu-id="76108-125">Click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="76108-126">Suchen Sie die **Berichtsserver-Integrationsfunktion** , und klicken Sie auf **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="76108-126">Find the **Report Server Integration Feature** and click **Deactivate**.</span></span>  
  
     <span data-ttu-id="76108-127">![rs_Berichtsserver_Integration_aktiviert](media/rs-reportserver-integration-active.gif "rs_Berichtsserver_Integration_aktiviert")</span><span class="sxs-lookup"><span data-stu-id="76108-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span></span>  
  
5.  <span data-ttu-id="76108-128">Aktualisieren Sie den Browser, und klicken Sie unter **Berichtsserver-Integrationsfunktion** auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="76108-128">Refresh the browser then click **Activate** for the **Report Server Integration Feature**.</span></span>  
  
    <span data-ttu-id="76108-129">![Deaktivieren](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span><span class="sxs-lookup"><span data-stu-id="76108-129">![Deactivate](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2013"></a><a name="bkmk_enable_content_management"></a><span data-ttu-id="76108-130">So aktivieren Sie die Inhaltstyp Verwaltung für eine einzelne Dokumentbibliothek (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="76108-130">To enable content type management for a single document library (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="76108-131">Öffnen Sie die Bibliothek, für die Sie mehrere Inhaltstypen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="76108-131">Open the library for which you want to enable multiple content types.</span></span>  
  
2.  <span data-ttu-id="76108-132">Klicken Sie im Menüband auf **Bibliothek** .</span><span class="sxs-lookup"><span data-stu-id="76108-132">Click **Library** in the ribbon.</span></span>  
  
     <span data-ttu-id="76108-133">![rs_SharePoint2013_MenübandBibliothek](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_MenübandBibliothek")</span><span class="sxs-lookup"><span data-stu-id="76108-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="76108-134">Klicken Sie im Menüband **Bibliothek** auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-134">On the **Library** ribbon, click **Library Settings**.</span></span> <span data-ttu-id="76108-135">Falls **Bibliothekseinstellungen** nicht angezeigt wird oder die Schaltfläche deaktiviert ist, sind Sie nicht berechtigt, Bibliothekseinstellungen sowie Inhaltstypen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76108-135">If you do not see **Library Settings** or the button is disabled, you do not have permission to configure library settings, including content types.</span></span>  
  
     <span data-ttu-id="76108-136">![rs_SharePoint2013_Bibliothekseinstellungen](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_Bibliothekseinstellungen")</span><span class="sxs-lookup"><span data-stu-id="76108-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span></span>  
  
4.  <span data-ttu-id="76108-137">Klicken Sie im Abschnitt **Allgemeine Einstellungen** auf **Erweiterte Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-137">In the **General Settings** section, click **Advanced settings**.</span></span>  
  
     <span data-ttu-id="76108-138">![rs_SharePoint2013_Bibliothekseinstellungen_ErweiterteEinstellungen](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_Bibliothekseinstellungen_ErweiterteEinstellungen")</span><span class="sxs-lookup"><span data-stu-id="76108-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span></span>  
  
5.  <span data-ttu-id="76108-139">Wählen Sie im Abschnitt **Inhaltstypen** die Option **Ja** aus, um die Verwaltung von Inhaltstypen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="76108-139">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="76108-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="76108-140">Click **OK**.</span></span>  
  
##  <a name="to-add-reporting-services-content-types-sharepoint-2013"></a><a name="bkmk_add_single"></a><span data-ttu-id="76108-141">So fügen Sie Reporting Services Inhaltstypen hinzu (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="76108-141">To add Reporting Services content types (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="76108-142">Öffnen Sie die Bibliothek, für die Sie Reporting Services-Inhaltstypen hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="76108-142">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="76108-143">Klicken Sie im Menüband auf **Bibliothek**.</span><span class="sxs-lookup"><span data-stu-id="76108-143">On the ribbon, click **Library**.</span></span>  
  
3.  <span data-ttu-id="76108-144">Klicken Sie auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-144">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="76108-145">Klicken Sie unter **Inhaltstypen**auf **Aus vorhandenen Websiteinhaltstypen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="76108-145">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="76108-146">Wählen Sie unter **Websiteinhaltstypen auswählen aus**die Option **SQL Server Reporting Services-Inhaltstypen**aus.</span><span class="sxs-lookup"><span data-stu-id="76108-146">In **Select site content types from**, select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="76108-147">Klicken Sie in der Liste **Verfügbare Websiteinhaltstypen** auf **Berichts-Generator**, und klicken Sie dann auf **Hinzufügen** , um den ausgewählten Inhaltstyp in die Liste **Hinzuzufügende Inhaltstypen** zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="76108-147">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="76108-148">Wiederholen Sie den vorherigen Schritt, um die Inhaltstypen **Berichtsmodell** und **Berichtsdatenquelle** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76108-148">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="76108-149">Nachdem Sie alle gewünschten Inhaltstypen hinzugefügt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="76108-149">When you finish adding content types, click **OK**.</span></span>  
  
9. > [!NOTE]  
    >  <span data-ttu-id="76108-150"> Die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstypgruppe **SQL Server Reporting Services-Inhaltstypen** wird unter folgenden Bedingungen auf der Seite **Inhaltstypen hinzufügen** nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="76108-150">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content type group **SQL Server Reporting Services Content Types** is not visible on the **Add Content Types** page, one of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="76108-151">Das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Add-In für SharePoint-Produkte wurde nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="76108-151">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products has not been installed.</span></span> <span data-ttu-id="76108-152">Weitere Informationen finden Sie unter [installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="76108-152">For more information, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span> <span data-ttu-id="76108-153">Das Thema enthält Informationen zum Installieren des Add-Ins und es wird Schritt für Schritt erläutert, wie Sie eine Nur-Datei-Installation des Add-Ins ausführen können, um Probleme zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="76108-153">The topic includes information on installing the add-in and stepping through a files only installation of the add-in to work around issues.</span></span>  
  
    -   <span data-ttu-id="76108-154">Das Add-In wird installiert, aber die **Funktion für die Berichtsserverintegration** für die Websitesammlung ist nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="76108-154">The add-in is installed but the site collection feature **Report Server Integration Feature** is not active.</span></span> <span data-ttu-id="76108-155">Prüfen Sie die Websitesammlungsfunktion unter **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-155">Verify the site collection feature in **Site Settings**.</span></span>  
  
    -   <span data-ttu-id="76108-156">Der Bibliothek wurden bereits sämtliche [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstypen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="76108-156">All of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types have already been added to the library.</span></span> <span data-ttu-id="76108-157">Wenn alle Inhaltstypen einer Bibliothek angehören, wird die Gruppe von der Seite **Inhaltstypen hinzufügen** entfernt.</span><span class="sxs-lookup"><span data-stu-id="76108-157">If all the content types are part of a library, then the group is removed from the **Add Content Types** page.</span></span> <span data-ttu-id="76108-158">Nachdem mindestens ein [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Inhaltstyp gelöscht wurde, wird die Gruppe **SQL Server Reporting Services-Inhaltstypen** auf der Seite **Inhaltstypen hinzufügen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76108-158">If you delete one or more of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types, then the group **SQL Server Reporting Services Content Types** will be visible on the **Add Content Types** page.</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2010"></a><a name="bkmk_enable_content_management_2010"></a><span data-ttu-id="76108-159">So aktivieren Sie die Inhaltstyp Verwaltung für eine einzelne Dokumentbibliothek (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="76108-159">To enable content type management for a single document library (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="76108-160">Öffnen Sie die Bibliothek, für die Sie mehrere Inhaltstypen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="76108-160">Open the library for which you want to enable multiple content types.</span></span> <span data-ttu-id="76108-161">Auf der Menüleiste der Bibliothek sollten die folgenden Menüs angezeigt werden: **Neu**, **Upload**, **Aktionen**und **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-161">On the library menu bar, you should see the following menus: **New**, **Upload**, **Actions**, and **Settings**.</span></span> <span data-ttu-id="76108-162">Falls **Einstellungen**nicht angezeigt wird, sind Sie nicht berechtigt, Inhaltstypen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76108-162">If you do not see **Settings**, you do not have permission to add a content type.</span></span>  
  
2.  <span data-ttu-id="76108-163">Klicken Sie im Menüband **Bibliothekstools** auf **Bibliothek**.</span><span class="sxs-lookup"><span data-stu-id="76108-163">On the **Library Tools** ribbon, click **Library**.</span></span>  
  
     <span data-ttu-id="76108-164">![rs_SharePoint2010_MenübandBibliothek](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_MenübandBibliothek")</span><span class="sxs-lookup"><span data-stu-id="76108-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="76108-165">Klicken Sie in der Menübandgruppe **Einstellungen** auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-165">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="76108-166">Klicken Sie unter **Allgemeine Einstellungen**auf **Erweiterte Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-166">Under **General Settings**, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="76108-167">Wählen Sie im Abschnitt **Inhaltstypen** die Option **Ja** aus, um die Verwaltung von Inhaltstypen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="76108-167">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="76108-168">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="76108-168">Click **OK**.</span></span>  
  
##  <a name="to-add-report-server-content-types-sharepoint-2010"></a><a name="bkmk_add_single_2010"></a><span data-ttu-id="76108-169">So fügen Sie Berichts Server-Inhaltstypen hinzu (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="76108-169">To add report server content types (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="76108-170">Öffnen Sie die Bibliothek, für die Sie Reporting Services-Inhaltstypen hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="76108-170">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="76108-171">Klicken Sie auf den Registerkarten des Menübands **Bibliothekstools** auf die Registerkarte **Bibliothek**.</span><span class="sxs-lookup"><span data-stu-id="76108-171">On the **Library Tools** ribbon tabs, click the **Library tab**.</span></span>  
  
3.  <span data-ttu-id="76108-172">Klicken Sie in der Menübandgruppe **Einstellungen** auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-172">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="76108-173">Klicken Sie unter **Inhaltstypen**auf **Aus vorhandenen Websiteinhaltstypen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="76108-173">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="76108-174">Klicken Sie im Abschnitt **Inhaltstypen auswählen** in der Liste **Websiteinhaltstypen auswählen aus**auf den Pfeil, um **SQL Server Reporting Services-Inhaltstypen**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="76108-174">In the **Select Content Types** section, in **Select site content types from**, click the arrow to select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="76108-175">Klicken Sie in der Liste **Verfügbare Websiteinhaltstypen** auf **Berichts-Generator**, und klicken Sie dann auf **Hinzufügen** , um den ausgewählten Inhaltstyp in die Liste **Hinzuzufügende Inhaltstypen** zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="76108-175">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="76108-176">Wiederholen Sie den vorherigen Schritt, um die Inhaltstypen **Berichtsmodell** und **Berichtsdatenquelle** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76108-176">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="76108-177">Nachdem Sie alle gewünschten Inhaltstypen hinzugefügt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="76108-177">When you finish adding content types, click **OK**.</span></span>  
  
##  <a name="to-enable-content-types-and-content-management-for-multiple-bi-sites"></a><a name="bkmk_enable_multiple_sites"></a><span data-ttu-id="76108-178">So aktivieren Sie Inhaltstypen und die Inhalts Verwaltung für mehrere BI-Websites</span><span class="sxs-lookup"><span data-stu-id="76108-178">To enable Content types and content management for multiple BI sites</span></span>  
  
1.  <span data-ttu-id="76108-179">Bei Berichtsservern unter SQL Server Reporting Services 2008 und 2008 R2 können Inhaltstypen sowie die Inhaltsverwaltung für mehrere Business Intelligence Center-Websites aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="76108-179">For SQL Server Reporting Services 2008 and 2008 R2 report servers, you can enable content types and content management for multiple Business Intelligence Center sites:</span></span>  
  
2.  <span data-ttu-id="76108-180">Klicken Sie in der SharePoint-Zentraladministration auf **Allgemeine Anwendungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76108-180">In SharePoint Central Administration, click **General Applications settings**.</span></span> <span data-ttu-id="76108-181">Klicken Sie im Abschnitt **SQL Server Reporting Services (2008 und 2008 R2)** auf **Reporting Services-Integration**.</span><span class="sxs-lookup"><span data-stu-id="76108-181">In the **SQL Server Reporting Services (2008 and 2008 R2)** section, click **Reporting Services Integration**.</span></span>  
  
     <span data-ttu-id="76108-182">![rs_allgemeine_Appeinstellungen](media/rs-general-app-settings.gif "rs_allgemeine_Appeinstellungen")</span><span class="sxs-lookup"><span data-stu-id="76108-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span></span>  
  
3.  <span data-ttu-id="76108-183">Klicken Sie auf **Funktion in allen vorhandenen Websitesammlungen aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="76108-183">Click **Activate feature in all exciting site collections**.</span></span>  
  
     <span data-ttu-id="76108-184">![rs_allgemeine_Appeinstellungen_alte_Integrationen](media/rs-general-app-settings-old-integrations.gif "rs_allgemeine_Appeinstellungen_alte_Integrationen")</span><span class="sxs-lookup"><span data-stu-id="76108-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span></span>  
  
4.  <span data-ttu-id="76108-185">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="76108-185">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76108-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76108-186">See Also</span></span>  
 <span data-ttu-id="76108-187">[Referenz zu SharePoint-Website-und Listen Berechtigungen für Berichts Server Elemente](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="76108-187">[SharePoint Site and List Permission Reference for Report Server Items](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="76108-188">Starten Sie Berichts-Generator &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="76108-188">Start Report Builder &#40;Report Builder&#41;</span></span>](report-builder/start-report-builder.md)  
  
  
