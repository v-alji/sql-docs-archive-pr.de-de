---
title: Aktivieren von Remotefehlern (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- remote data source [Reporting Services]
- EnableRemoteError server property
ms.assetid: 5f05022b-d557-43e0-b50a-f5e2a1846b83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d2a7e7e0b38b38bf563dfc2a8cff65c897c5293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619576"
---
# <a name="enable-remote-errors-reporting-services"></a><span data-ttu-id="e5170-102">Aktivieren von Remotefehlern (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="e5170-102">Enable Remote Errors (Reporting Services)</span></span>
  <span data-ttu-id="e5170-103">Sie können Servereigenschaften auf einem [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] festlegen, um zusätzliche Informationen zu auf Remoteservern aufgetretenen Fehlerbedingungen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5170-103">You can set server properties on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="e5170-104">Wenn in einer Fehlermeldung der Text "Um weitere Informationen zu diesem Fehler zu erhalten, navigieren Sie zum Berichtsserver auf dem lokalen Servercomputer, oder aktivieren Sie Remotefehler." angezeigt wird, können Sie die `EnableRemoteErrors`-Eigenschaft festlegen, um zusätzliche Informationen zum Behandeln des Problems zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e5170-104">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", you can set the `EnableRemoteErrors` property to access additional information that can help you troubleshoot the problem.</span></span> <span data-ttu-id="e5170-105">Weitere Informationen finden Sie unter [Berichtsserver-Systemeigenschaften](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5170-105">For more information, see [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="e5170-106">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="e5170-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="e5170-107">Aktivieren von Remotefehlern für den SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="e5170-107">Enable Remote Errors for SharePoint Mode</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="e5170-108">Aktivieren von Remotefehlern durch SQL Server Management Studio (Einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="e5170-108">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>](#bkmk_mgtStudio)  
  
-   [<span data-ttu-id="e5170-109">Aktivieren von Remotefehlern per Skript (Einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="e5170-109">Enable remote errors through script (Native Mode)</span></span>](#bkmk_script)  
  
-   [<span data-ttu-id="e5170-110">Ändern der ConfigurationInfo-Tabelle (Einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="e5170-110">Modifying the ConfigurationInfo table (Native Mode)</span></span>](#bkmk_ConfigurationInfo)  
  
##  <a name="enable-remote-errors-for-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="e5170-111">Aktivieren von Remotefehlern für den SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="e5170-111">Enable Remote Errors for SharePoint Mode</span></span>  
 <span data-ttu-id="e5170-112">Es gibt zwei verschiedene Prozeduren zum Aktivieren von Remotefehlern für den SharePoint-Modus von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5170-112">There are two different procedures for enabling remote errors for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="e5170-113">Die Prozedur ist für die beiden verschiedenen Berichtsserverarchitekturen unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="e5170-113">The procedure is different for the two different report server architectures.</span></span> <span data-ttu-id="e5170-114">Die neuere, auf dem SharePoint-Dienst basierende Architektur, die in der [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] -Version eingeführt wurde, verwendet eine Einstellung, die für jede [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5170-114">The newer SharePoint service based architecture that was introduced in the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, utilizes a setting that can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="e5170-115">Die ältere Architektur verwendet eine einzelne Einstellung auf Websiteebene.</span><span class="sxs-lookup"><span data-stu-id="e5170-115">The older architecture utilizes a single site level setting.</span></span>  
  
#### <a name="enable-remote-errors-for-a-reporting-services-service-application"></a><span data-ttu-id="e5170-116">Aktivieren von Remotefehlern für eine Reporting Services-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="e5170-116">Enable Remote errors for a Reporting Services Service Application</span></span>  
  
1.  <span data-ttu-id="e5170-117">Aktivieren Sie für einen Berichtsserver im SharePoint-Modus, der mit [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] oder einer neueren Version von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]installiert wurde, die Dienstanwendungseinstellung **Remotefehler aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e5170-117">For a SharePoint mode report server installed with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] or a newer version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], enable the service application setting **Enable remote errors**.</span></span> <span data-ttu-id="e5170-118">Die Einstellung kann für jede [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e5170-118">The setting can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="e5170-119">Klicken Sie in der SharePoint-Zentraladministration in der Gruppe **Anwendungsverwaltung** auf **Dienstanwendungen verwalten** .</span><span class="sxs-lookup"><span data-stu-id="e5170-119">In SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
3.  <span data-ttu-id="e5170-120">Suchen Sie Ihre [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung, und klicken Sie auf den Namen der Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="e5170-120">Find your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and click the name of your service application.</span></span>  
  
4.  <span data-ttu-id="e5170-121">Klicken Sie auf **Systemeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e5170-121">Click **System Settings**.</span></span>  
  
5.  <span data-ttu-id="e5170-122">Klicken Sie im Abschnitt **Sicherheit** auf **Remotefehler aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="e5170-122">Click **Enable Remote Errors** in the **Security** section.</span></span>  
  
6.  <span data-ttu-id="e5170-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5170-123">Click **OK**.</span></span>  
  
#### <a name="enable-remote-errors-for-a-sharepoint-site"></a><span data-ttu-id="e5170-124">Aktivieren von Remotefehlern für eine SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="e5170-124">Enable Remote Errors for a SharePoint Site</span></span>  
  
1.  <span data-ttu-id="e5170-125">Aktivieren Sie für einen Berichtsserver im SharePoint-Modus, der mit einer Version von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] vor [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installiert ist, die Websiteeinstellung **Remotefehler im lokalen Modus aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e5170-125">For a SharePoint mode report server installed with a version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prior to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], enable the site setting **Enable remote errors in local mode**.</span></span>  
  
2.  <span data-ttu-id="e5170-126">Klicken Sie unter **Websiteaktionen** auf **Siteeinstellungen** für die zu ändernde Website.</span><span class="sxs-lookup"><span data-stu-id="e5170-126">In **Site Actions** click **Site Settings** for the site you want to modify.</span></span>  
  
3.  <span data-ttu-id="e5170-127">Klicken Sie in der Gruppe **Reporting Services** auf **Einstellungen für Reporting Services-Websites** .</span><span class="sxs-lookup"><span data-stu-id="e5170-127">Click **Reporting Services Site Settings** in the **Reporting Services** group.</span></span>  
  
4.  <span data-ttu-id="e5170-128">Klicken Sie auf **Remotefehler im lokalen Modus aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e5170-128">Click **Enable remote errors in local mode**.</span></span>  
  
5.  <span data-ttu-id="e5170-129">Klicken Sie auf **OK**</span><span class="sxs-lookup"><span data-stu-id="e5170-129">Click **OK**</span></span>  
  
##  <a name="enable-remote-errors-through-sql-server-management-studio-native-mode"></a><a name="bkmk_mgtStudio"></a> <span data-ttu-id="e5170-130">Aktivieren von Remotefehlern durch SQL Server Management Studio (Einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="e5170-130">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>  
  
1.  <span data-ttu-id="e5170-131">Starten Sie Management Studio, und stellen Sie eine Verbindung mit einer Berichtsserverinstanz her.</span><span class="sxs-lookup"><span data-stu-id="e5170-131">Start Management Studio and connect to a report server instance.</span></span> <span data-ttu-id="e5170-132">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einem Berichtsserver in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5170-132">For more information, see [Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="e5170-133">Klicken Sie mit der rechten Maustaste auf den Berichtsserverknoten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e5170-133">Right-click the report server node, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="e5170-134">Klicken Sie auf **Erweitert** , um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5170-134">Click **Advanced** to open the properties page.</span></span> <span data-ttu-id="e5170-135">Weitere Informationen finden Sie unter [Servereigenschaften (Seite „Erweitert“) – Reporting Services](../tools/server-properties-advanced-page-reporting-services.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5170-135">For more information, see [Server Properties &#40;Advanced Page&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md)in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="e5170-136">`EnableRemoteErrors`Wählen Sie in aus `True` .</span><span class="sxs-lookup"><span data-stu-id="e5170-136">In `EnableRemoteErrors`, select `True`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="enable-remote-errors-through-script-native-mode"></a><a name="bkmk_script"></a> <span data-ttu-id="e5170-137">Aktivieren von Remotefehlern per Skript (Einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="e5170-137">Enable remote errors through script (Native Mode)</span></span>  
  
1.  <span data-ttu-id="e5170-138">Erstellen Sie eine Textdatei, und kopieren Sie das folgende Skript in die Datei.</span><span class="sxs-lookup"><span data-stu-id="e5170-138">Create a text file and copy the following script into the file.</span></span>  
  
    ```  
    Public Sub Main()  
      Dim P As New [Property]()  
      P.Name = "EnableRemoteErrors"  
      P.Value = True  
      Dim Properties(0) As [Property]  
      Properties(0) = P  
      Try  
        rs.SetSystemProperties(Properties)  
        Console.WriteLine("Remote errors enabled.")  
      Catch SE As SoapException  
        Console.WriteLine(SE.Detail.OuterXml)  
      End Try  
    End Sub  
    ```  
  
2.  <span data-ttu-id="e5170-139">Speichern Sie die Datei unter dem Namen EnableRemoteErrors.rss.</span><span class="sxs-lookup"><span data-stu-id="e5170-139">Save the file as EnableRemoteErrors.rss.</span></span>  
  
3.  <span data-ttu-id="e5170-140">Klicken Sie auf **Start**, zeigen Sie auf **Ausführen**, geben Sie **cmd**ein, und klicken Sie auf **OK** , um eine Eingabeaufforderung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5170-140">Click **Start**, point to **Run**, type **cmd**, and click **OK** to open a command prompt window.</span></span>  
  
4.  <span data-ttu-id="e5170-141">Wechseln Sie in das Verzeichnis, das die zuvor von Ihnen erstellte RSS-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="e5170-141">Navigate to the directory that contains the .rss file you just created.</span></span>  
  
5.  <span data-ttu-id="e5170-142">Geben Sie die folgenden Befehlszeile ein. Ersetzen Sie dabei *servername* durch den Namen Ihres aktuellen Servers:</span><span class="sxs-lookup"><span data-stu-id="e5170-142">Type the following command line, replacing *servername* with the actual name of your server:</span></span>  
  
    ```  
    rs -i EnableRemoteErrors.rss -s http://servername/ReportServer  
    ```  
  
6.  <span data-ttu-id="e5170-143">Weitere Informationen finden Sie unter [Hilfsprogramm RS.exe &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e5170-143">For more information, see [RS.exe Utility &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span></span>  
  
##  <a name="modifying-the-configurationinfo-table-native-mode"></a><a name="bkmk_ConfigurationInfo"></a> <span data-ttu-id="e5170-144">Ändern der ConfigurationInfo-Tabelle (Einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="e5170-144">Modifying the ConfigurationInfo table (Native Mode)</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="e5170-145">Sie können die **configurationinfo** -Tabelle in der Berichts Server-Datenbank so bearbeiten, dass Sie auf festgelegt wird `EnableRemoteErrors` `True` . wenn der Berichts Server jedoch aktiv verwendet wird, sollten Sie die Einstellungen mit SQL Server Management Studio oder einem Skript ändern.</span><span class="sxs-lookup"><span data-stu-id="e5170-145">You can edit the **ConfigurationInfo** table in the report server database to set `EnableRemoteErrors` to `True`, but if the report server is actively used, you should use SQL Server Management Studio or script to modify the settings.</span></span> <span data-ttu-id="e5170-146">Wenn Sie die Einstellung in der Datenbank ändern, müssen Sie den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienst neu starten, bevor die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="e5170-146">If you modify the setting in the database, you need to restart the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service before the changes take effect.</span></span>  
  
  
