---
title: Aktivieren und Deaktivieren von Features von Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, configuration
- security [Reporting Services], strategies
ms.assetid: b69db02a-43a7-4fdc-ad9b-438d817a7f83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f56f9984b5b02431db23b782652e5575af557bdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617620"
---
# <a name="turn-reporting-services-features-on-or-off"></a><span data-ttu-id="1f77b-102">Aktivieren und Deaktivieren der Reporting Services-Funktionen</span><span class="sxs-lookup"><span data-stu-id="1f77b-102">Turn Reporting Services Features On or Off</span></span>
  <span data-ttu-id="1f77b-103">Sie können Berichtsserver-Funktionen, die Sie nicht als Teil einer Sicherheitsstrategie verwenden, deaktivieren, um die Angriffsfläche eines Produktionsberichtsservers zu verkleinern.</span><span class="sxs-lookup"><span data-stu-id="1f77b-103">You can turn off report server features that you do not use as part of a lockdown strategy for reducing the attack surface of a production report server.</span></span> <span data-ttu-id="1f77b-104">In den meisten Fällen sollten Sie die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Features gleichzeitig ausführen, damit Sie alle Funktionen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1f77b-104">In most cases, you will want to run [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features concurrently to use all of the functionality provided in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="1f77b-105">Sie können jedoch je nach Bereitstellungsmodell die Funktionen deaktivieren, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="1f77b-105">However, depending on your deployment model, you can disable the features that you do not require.</span></span> <span data-ttu-id="1f77b-106">Beispielweise können Sie nur die Hintergrundverarbeitung aktivieren, wenn die gesamte Berichtsverarbeitung in Form von geplanten Vorgängen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1f77b-106">For example, you can enable only the background processing if all report processing is configured as scheduled operations.</span></span> <span data-ttu-id="1f77b-107">Entsprechend können Sie nur den Report Server-Webdienst ausführen, wenn Sie ausschließlich interaktive, bedarfsgesteuerte Berichte wünschen.</span><span class="sxs-lookup"><span data-stu-id="1f77b-107">Similarly, you can run just the Report Server Web service if you only want interactive, on-demand reporting.</span></span>  
  
 <span data-ttu-id="1f77b-108">Die Prozeduren in diesem Thema erläutern, wie Sie die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Funktionen des einheitlichen Modus deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f77b-108">The procedures in this topic show you how to turn off native mode [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="1f77b-109">Sie können die Funktionen auf verschiedene Arten konfigurieren, z.B. indem Sie die Datei `RsReportServer.config` direkt bearbeiten oder indem Sie das Facet **Oberflächenkonfiguration für Reporting Services** der richtlinienbasierten Verwaltung in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f77b-109">Features can be configured in different ways, such as by editing the `RsReportServer.config` file directly or by using the **Surface Area Configuration for Reporting Services** facet of Policy-Based Management in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1f77b-110">Verwenden Sie die Links, um auf die Prozeduren zuzugreifen, in denen das Aktivieren und Deaktivieren einer Funktion erläutert wird:</span><span class="sxs-lookup"><span data-stu-id="1f77b-110">Use the links to locate the procedure or procedures that explain how to turn a feature on or off:</span></span>  
  
-   [<span data-ttu-id="1f77b-111">Report Server-Webdienst</span><span class="sxs-lookup"><span data-stu-id="1f77b-111">Report Server Web service</span></span>](#RSWebSvc)  
  
-   [<span data-ttu-id="1f77b-112">Geplante Ereignisse und Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="1f77b-112">Scheduled events and processing</span></span>](#Sched)  
  
-   [<span data-ttu-id="1f77b-113">Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="1f77b-113">Report Manager</span></span>](#ReportManager)  
  
-   [<span data-ttu-id="1f77b-114">Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="1f77b-114">Report Builder</span></span>](#ReportBuilder)  
  
-   [<span data-ttu-id="1f77b-115">Integrierte Sicherheit von Windows für Berichtsdatenquellen</span><span class="sxs-lookup"><span data-stu-id="1f77b-115">Windows Integrated security for report data sources</span></span>](#WinIntSec)  
  
##  <a name="report-server-web-service"></a><a name="RSWebSvc"></a><span data-ttu-id="1f77b-116">Report Server-Webdienst</span><span class="sxs-lookup"><span data-stu-id="1f77b-116">Report Server Web Service</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-editing-configuration"></a><span data-ttu-id="1f77b-117">So aktivieren bzw. deaktivieren Sie den Berichtsserver-Webdienst, indem Sie die Konfiguration bearbeiten</span><span class="sxs-lookup"><span data-stu-id="1f77b-117">To turn on or off the Report Server Web service by editing configuration</span></span>  
  
1.  <span data-ttu-id="1f77b-118">Öffnen Sie die Datei `RsReportServer.config` in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="1f77b-118">Open the `RsReportServer.config` file in a text editor.</span></span> <span data-ttu-id="1f77b-119">Weitere Informationen finden Sie unter [Ändern einer Reporting Services-Konfigurationsdatei (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1f77b-119">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="1f77b-120">Um den Berichtsserver-Webdienst zu aktivieren, setzen Sie `IsWebServiceEnabled` auf `true`:</span><span class="sxs-lookup"><span data-stu-id="1f77b-120">To turn on the Report Server Web service, set `IsWebServiceEnabled` to `true`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>true</IsWebServiceEnabled>  
    ```  
  
3.  <span data-ttu-id="1f77b-121">Um den Berichtsserver-Webdienst zu deaktivieren, setzen Sie `IsWebServiceEnabled` auf `false`:</span><span class="sxs-lookup"><span data-stu-id="1f77b-121">To turn off the Report Server Web service, set `IsWebServiceEnabled` to `false`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>false</IsWebServiceEnabled>  
    ```  
  
4.  <span data-ttu-id="1f77b-122">Speichern Sie die Änderungen, und schließen Sie dann die Datei.</span><span class="sxs-lookup"><span data-stu-id="1f77b-122">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-using-sql-server-management-studio"></a><span data-ttu-id="1f77b-123">So aktivieren bzw. deaktivieren Sie den Berichtsserver-Webdienst mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f77b-123">To turn on or off the Report Server Web service by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f77b-124">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Instanz her, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1f77b-124">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="1f77b-125">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Knoten, zeigen Sie auf **Richtlinien**, und klicken Sie auf **Facets**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-125">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="1f77b-126">Wählen Sie in der Liste **Facet** den Eintrag **Oberflächenkonfiguration für Reporting Services**aus.</span><span class="sxs-lookup"><span data-stu-id="1f77b-126">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="1f77b-127">Führen Sie unter **Facet-Eigenschaften**Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="1f77b-127">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="1f77b-128">Um den Report Server-Webdienst zu aktivieren, legen Sie **WebServiceAndHTTPAccessEnabled** auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="1f77b-128">To turn on the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="1f77b-129">Legen Sie **WebServiceAndHTTPAccessEnabled** auf fest, um den Report Server-Webdienst zu deaktivieren `False` .</span><span class="sxs-lookup"><span data-stu-id="1f77b-129">To turn off the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="scheduled-events-and-delivery"></a><a name="Sched"></a> <span data-ttu-id="1f77b-130">Geplante Ereignisse und Übermittlung</span><span class="sxs-lookup"><span data-stu-id="1f77b-130">Scheduled Events and Delivery</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-editing-configuration"></a><span data-ttu-id="1f77b-131">So aktivieren bzw. deaktivieren Sie geplante Ereignisse und die Übermittlung, indem Sie die Konfiguration bearbeiten</span><span class="sxs-lookup"><span data-stu-id="1f77b-131">To turn on or off scheduled events and delivery by editing configuration</span></span>  
  
1.  <span data-ttu-id="1f77b-132">Öffnen Sie die Datei RSReportServer.config in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="1f77b-132">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="1f77b-133">Weitere Informationen finden Sie unter [Ändern einer Reporting Services-Konfigurationsdatei (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1f77b-133">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="1f77b-134">Um die geplante Berichtsverarbeitung und -übermittlung zu aktivieren, setzen Sie `IsSchedulingService`, `IsNotificationService` und `IsEventService` auf `true`:</span><span class="sxs-lookup"><span data-stu-id="1f77b-134">To turn on scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `true`:</span></span>  
  
    ```  
    <IsSchedulingService>true</IsSchedulingService>  
    <IsNotificationService>true</IsNotificationService>  
    <IsEventService>true</IsEventService>  
    ```  
  
3.  <span data-ttu-id="1f77b-135">Um die geplante Berichtsverarbeitung und -übermittlung zu deaktivieren, setzen Sie `IsSchedulingService`, `IsNotificationService` und `IsEventService` auf `false`:</span><span class="sxs-lookup"><span data-stu-id="1f77b-135">To turn off scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `false`:</span></span>  
  
    ```  
    <IsSchedulingService>false</IsSchedulingService>  
    <IsNotificationService>false</IsNotificationService>  
    <IsEventService>false</IsEventService>  
    ```  
  
4.  <span data-ttu-id="1f77b-136">Speichern Sie die Änderungen, und schließen Sie dann die Datei.</span><span class="sxs-lookup"><span data-stu-id="1f77b-136">Save your changes and then close the file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f77b-137">Die Hintergrundverarbeitung kann nicht vollständig deaktiviert werden, da sie Datenbankverwaltungsfunktionen enthält, die für den Serverbetrieb benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f77b-137">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-using-sql-server-management-studio"></a><span data-ttu-id="1f77b-138">So aktivieren bzw. deaktivieren Sie geplante Ereignisse und die Übermittlung mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f77b-138">To turn on or off scheduled events and delivery by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f77b-139">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Instanz her, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1f77b-139">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="1f77b-140">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Knoten, zeigen Sie auf **Richtlinien**, und klicken Sie auf **Facets**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-140">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="1f77b-141">Wählen Sie in der Liste **Facet** den Eintrag **Oberflächenkonfiguration für Reporting Services**aus.</span><span class="sxs-lookup"><span data-stu-id="1f77b-141">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="1f77b-142">Führen Sie unter **Facet-Eigenschaften**Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="1f77b-142">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="1f77b-143">Um geplante Ereignisse und die Übermittlung zu aktivieren, legen Sie **scheduleeventsandreportdeliveryaktiviauf** fest `True` .</span><span class="sxs-lookup"><span data-stu-id="1f77b-143">To turn on scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="1f77b-144">Um geplante Ereignisse und die Übermittlung zu deaktivieren, legen Sie **scheduleeventsandreportdeliveryaktiviauf** fest `False` .</span><span class="sxs-lookup"><span data-stu-id="1f77b-144">To turn off scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="1f77b-145">Die Hintergrundverarbeitung kann nicht vollständig deaktiviert werden, da sie Datenbankverwaltungsfunktionen enthält, die für den Serverbetrieb benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f77b-145">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
##  <a name="report-manager"></a><a name="ReportManager"></a><span data-ttu-id="1f77b-146">Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="1f77b-146">Report Manager</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-editing-configuration"></a><span data-ttu-id="1f77b-147">So aktivieren bzw. deaktivieren Sie den Berichts-Manager, indem Sie die Konfiguration bearbeiten</span><span class="sxs-lookup"><span data-stu-id="1f77b-147">To turn on or off Report Manager by editing configuration</span></span>  
  
1.  <span data-ttu-id="1f77b-148">Öffnen Sie die Datei RSReportServer.config in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="1f77b-148">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="1f77b-149">Anweisungen finden Sie unter [Ändern einer Reporting Services-Konfigurationsdatei &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1f77b-149">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="1f77b-150">Um den Berichts-Manager zu aktivieren, setzen Sie `IsReportManagerEnabled` auf `true`:</span><span class="sxs-lookup"><span data-stu-id="1f77b-150">To turn on Report Manager, set `IsReportManagerEnabled` to `true`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>true</IsReportManagerEnabled>  
    ```  
  
3.  <span data-ttu-id="1f77b-151">Um den Berichts-Manager zu deaktivieren, setzen Sie `IsReportManagerEnabled` auf `false`:</span><span class="sxs-lookup"><span data-stu-id="1f77b-151">To turn off Report Manager, set `IsReportManagerEnabled` to `false`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>false</IsReportManagerEnabled>  
    ```  
  
4.  <span data-ttu-id="1f77b-152">Speichern Sie die Änderungen, und schließen Sie dann die Datei.</span><span class="sxs-lookup"><span data-stu-id="1f77b-152">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-using-sql-server-management-studio"></a><span data-ttu-id="1f77b-153">So aktivieren bzw. deaktivieren Sie den Berichts-Manager mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f77b-153">To turn on or off Report Manager by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f77b-154">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Instanz her, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1f77b-154">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="1f77b-155">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Knoten, zeigen Sie auf **Richtlinien**, und klicken Sie auf **Facetten**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-155">In **Object Explorer**, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="1f77b-156">Wählen Sie in der Liste **Facet** den Eintrag **Oberflächenkonfiguration für Reporting Services**aus.</span><span class="sxs-lookup"><span data-stu-id="1f77b-156">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="1f77b-157">Führen Sie unter **Facet-Eigenschaften**Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="1f77b-157">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="1f77b-158">Um Berichts-Manager zu aktivieren, legen Sie **reportmanageraktivierte** auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="1f77b-158">To turn on Report Manager, set **ReportManagerEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="1f77b-159">Um Berichts-Manager zu deaktivieren, legen Sie **reportmanageraktivierte** auf fest `False` .</span><span class="sxs-lookup"><span data-stu-id="1f77b-159">To turn off Report Manager, set **ReportManagerEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="report-builder"></a><a name="ReportBuilder"></a> <span data-ttu-id="1f77b-160">Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="1f77b-160">Report Builder</span></span>  
  
#### <a name="to-turn-on-or-off-report-builder-by-using-sql-server-management-studio"></a><span data-ttu-id="1f77b-161">So aktivieren bzw. deaktivieren Sie den Berichts-Generator mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f77b-161">To turn on or off Report Builder by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f77b-162">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Instanz her, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1f77b-162">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="1f77b-163">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Knoten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-163">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1f77b-164">Klicken Sie im Dialogfeld **Servereigenschaften** unter **Seite auswählen**auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-164">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="1f77b-165">Um den Berichts-Generator zu aktivieren, wählen Sie die Option **Ad-hoc-Berichtsausführungen aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="1f77b-165">To turn on Report Builder, select the **Enable ad hoc report executions** option.</span></span>  
  
    -   <span data-ttu-id="1f77b-166">Um den Berichts-Generator zu deaktivieren, heben Sie die Auswahl der Option **Ad-hoc-Berichtsausführungen aktivieren** auf.</span><span class="sxs-lookup"><span data-stu-id="1f77b-166">To turn off Report Builder, unselect the **Enable ad hoc report executions** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="windows-integrated-security"></a><a name="WinIntSec"></a> <span data-ttu-id="1f77b-167">Integrierte Sicherheit von Windows</span><span class="sxs-lookup"><span data-stu-id="1f77b-167">Windows Integrated Security</span></span>  
  
#### <a name="to-turn-on-or-off-windows-integrated-security-by-using-sql-server-management-studio"></a><span data-ttu-id="1f77b-168">So aktivieren bzw. deaktivieren Sie die integrierte Windows-Sicherheit mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f77b-168">To turn on or off Windows Integrated security by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f77b-169">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Instanz her, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1f77b-169">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="1f77b-170">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Knoten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-170">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1f77b-171">Klicken Sie im Dialogfeld **Servereigenschaften** unter **Seite auswählen**auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="1f77b-171">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="1f77b-172">Um die integrierte Sicherheit von Windows zu aktivieren, wählen Sie die Option **Integrierte Sicherheit von Windows für Berichtsdatenquellen aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="1f77b-172">To turn on Windows Integrated security, select the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
    -   <span data-ttu-id="1f77b-173">Um die integrierte Sicherheit von Windows zu deaktivieren, heben Sie die Auswahl der Option **Integrierte Sicherheit von Windows für Berichtsdatenquellen aktivieren** auf.</span><span class="sxs-lookup"><span data-stu-id="1f77b-173">To turn off Windows integrated security, unselect the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f77b-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f77b-174">See Also</span></span>  
 [<span data-ttu-id="1f77b-175">Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="1f77b-175">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
