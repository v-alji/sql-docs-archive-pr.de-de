---
title: Verwenden der SOAP-API in einer Windows-Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- Windows applications [Reporting Services]
- Windows Forms [Reporting Services]
- SOAP [Reporting Services], Windows applications
ms.assetid: e4804792-20cd-4df2-9257-fb958ff447b4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 115ce02da69a8adb2c7a3de4175e528f281eb2b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607558"
---
# <a name="using-the-soap-api-in-a-windows-application"></a><span data-ttu-id="98d01-102">Verwenden der SOAP-API in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="98d01-102">Using the SOAP API in a Windows Application</span></span>
  <span data-ttu-id="98d01-103">Über die Reporting Services-SOAP-API können Sie auf alle Funktionen des Berichtsservers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="98d01-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="98d01-104">Bei der SOAP-API handelt es sich um einen Webdienst, auf den problemlos zugegriffen werden kann, um Funktionen zur Unternehmensberichterstellung für benutzerdefinierte Geschäftsanwendungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="98d01-104">The SOAP API is a Web service and, as such, can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="98d01-105">Sie können in einer Windows-Anwendung auf den Webdienst zugreifen, indem Sie einfach Code schreiben, mit dem der Dienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="98d01-105">You can access the Web service in a Windows application simply by writing code that makes calls to the service.</span></span> <span data-ttu-id="98d01-106">Mithilfe von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] können Sie eine Proxy Klasse generieren, die die Eigenschaften und Methoden des Webdiensts verfügbar macht und es Ihnen ermöglicht, eine vertraute Infrastruktur und Tools zum Erstellen von Geschäftsanwendungen zu verwenden, die auf der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Technologie basieren.</span><span class="sxs-lookup"><span data-stu-id="98d01-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Web service and enables you to use a familiar infrastructure and tools to build business applications built on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
## <a name="integrating-report-management-functionality-using-windows-forms"></a><span data-ttu-id="98d01-107">Integrieren der Berichtsverwaltungsfunktionalität mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98d01-107">Integrating Report Management Functionality Using Windows Forms</span></span>  
 <span data-ttu-id="98d01-108">Anders als beim URL-Zugriff macht die SOAP-API sämtliche Verwaltungsfunktionen verfügbar, die über den Berichtsserver zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="98d01-108">Unlike URL access, the SOAP API exposes the complete set of management functions that are available through the report server.</span></span> <span data-ttu-id="98d01-109">Dies bedeutet, dass Entwicklern über SOAP sämtliche Administratorfunktionen des Berichts-Managers zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="98d01-109">This means that the entire administrative functionality of Report Manager is available to developers through SOAP.</span></span> <span data-ttu-id="98d01-110">Mit Windows Forms können Sie also ein vollständiges Management- und Verwaltungstool entwickeln.</span><span class="sxs-lookup"><span data-stu-id="98d01-110">As such, you can develop a complete management and administration tool using Windows Forms.</span></span> <span data-ttu-id="98d01-111">Sie können beispielsweise Benutzern in der Windows-Anwendung ermöglichen, den Inhalt des Berichtsserver-Namespace abzurufen.</span><span class="sxs-lookup"><span data-stu-id="98d01-111">For example, in your Windows application, you might want to enable your users to retrieve the contents of the report server namespace.</span></span> <span data-ttu-id="98d01-112">Zu diesem Zweck haben Sie die Möglichkeit, mit der <xref:ReportService2010.ReportingService2010.ListChildren%2A>-Methode des Webdiensts alle Elemente in der Berichtsserver-Datenbank aufzulisten und anschließend das Steuerelement Listview, Treeview oder Combobox zu verwenden, um diese Elemente für die Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98d01-112">To do this, you could use the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method to list all the items in the report server database and then use a Listview, Treeview, or Combobox control to display those items to your users.</span></span> <span data-ttu-id="98d01-113">Den folgenden Webdienstcode können Sie verwenden, um die aktuelle Liste der verfügbaren Berichte im Ordner Meine Berichte abzurufen, wenn ein Benutzer auf eine Schaltfläche in einem Formular klickt:</span><span class="sxs-lookup"><span data-stu-id="98d01-113">The following Web service code might be used to retrieve the current list of available reports in a user's My Reports folder when a user clicks a button on a form:</span></span>  
  
```vb  
' Button click event that retrieves a list of reports from  
' the My Reports folder and displays them in a combo box  
Private Sub listReportsButton_Click(sender As Object, e As System.EventArgs)  
   ' Create a new Web service object and set credentials  
   ' to Windows Authentication  
   Dim rs As New ReportingService2010()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return the list of items in My Reports  
   Dim items As CatalogItem() = rs.ListChildren("/Adventureworks 2008 Sample Reports", False)  
  
   Dim ci As CatalogItem  
   For Each ci In  items  
      ' If the item is a report, add it to   
      ' a combo box  
      If ci.TypeName = "Report" Then  
         catalogComboBox.Items.Add(ci.Name)  
      End If  
   Next ci  
End Sub 'listReportsButton_Click  
```  
  
```csharp  
// Button click event that retrieves a list of reports from  
// the My Reports folder and displays them in a combo box  
private void listReportsButton_Click(object sender, System.EventArgs e)  
{  
   // Create a new Web service object and set credentials  
   // to Windows Authentication  
   ReportingService2010 rs = new ReportingService2010();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return the list of items in My Reports  
   CatalogItem[] items = rs.ListChildren("/Adventureworks 2008 Sample Reports", false);  
  
   foreach (CatalogItem ci in items)  
   {  
      // If the item is a report, add it to   
      // a combo box  
      if (ci.TypeName == "Report")  
         catalogComboBox.Items.Add(ci.Name);  
   }  
}  
```  
  
 <span data-ttu-id="98d01-114">Von dort aus können Sie es Benutzern ermöglichen, den Bericht im Kombinationsfeld auszuwählen und dann mithilfe eines Webbrowser-Steuerelements oder eines Bildsteuerelements eine Vorschau des Berichts im Formular anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98d01-114">From there, you might enable users to select the report from the Combo box and preview the report on the form either using a Web browser control or an image control.</span></span>  
  
## <a name="enabling-report-viewing-and-navigation-using-windows-forms"></a><span data-ttu-id="98d01-115">Aktivieren der Anzeige von Berichten und der Berichtsnavigation mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98d01-115">Enabling Report Viewing and Navigation Using Windows Forms</span></span>  
 <span data-ttu-id="98d01-116">Es gibt zwei Methoden zum Integrieren von Berichten in Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="98d01-116">There are two methods available for integrating reports into your Windows Forms applications.</span></span>  
  
 <span data-ttu-id="98d01-117">Sie können die SOAP-API verwenden, um Berichte mithilfe der <xref:ReportExecution2005.ReportExecutionService.Render%2A>-Methode in jedes der unterstützten Renderingformate zu rendern.</span><span class="sxs-lookup"><span data-stu-id="98d01-117">You can use the SOAP API to render reports to any of the supported rendering formats using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="98d01-118">Die Verwendung dieser Methode bringt im Vergleich zur Aktivierung der Anzeige von Berichten und der Berichtsnavigation durch SOAP kleine Nachteile mit sich:</span><span class="sxs-lookup"><span data-stu-id="98d01-118">There are slight disadvantages to enabling report viewing and navigation through SOAP:</span></span>  
  
-   <span data-ttu-id="98d01-119">Sie können die integrierte Funktionalität der Berichtssymbolleiste nicht nutzen, die über URL-Zugriff im HTML-Viewer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="98d01-119">You cannot take advantage of the built-in functionality of the report toolbar that is included with the HTML Viewer through URL access.</span></span>  
  
-   <span data-ttu-id="98d01-120">Wenn Sie in das HTML-Format rendern, müssen Sie mit der <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A>-Methode alle Bilder oder Ressourcen separat als zusätzliche Datenströme rendern.</span><span class="sxs-lookup"><span data-stu-id="98d01-120">If you render to HTML, you must separately render any images or resources as additional streams using the <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> method.</span></span>  
  
-   <span data-ttu-id="98d01-121">Wenn Sie den URL-Zugriff verwenden, gibt es beim Rendern von Berichten einen leichten Leistungsvorteil im Vergleich zur SOAP-API.</span><span class="sxs-lookup"><span data-stu-id="98d01-121">There is a slight performance advantage to rendering reports using URL access over using the SOAP API.</span></span>  
  
 <span data-ttu-id="98d01-122">Sie können die <xref:ReportExecution2005.ReportExecutionService.Render%2A>-Methode der SOAP-API jedoch verwenden, um Berichte zu rendern und sie programmgesteuert in verschiedenen Ausgabeformaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="98d01-122">However, the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the SOAP API can be used to render reports and save them to various output formats programmatically.</span></span> <span data-ttu-id="98d01-123">Dies ist ein Vorteil gegenüber dem URL-Zugriff, der eine Benutzereingabe erfordert.</span><span class="sxs-lookup"><span data-stu-id="98d01-123">This is an advantage over URL access, which requires user interaction.</span></span> <span data-ttu-id="98d01-124">Wenn Sie mit der SOAP-API-<xref:ReportExecution2005.ReportExecutionService.Render%2A>-Methode einen Bericht rendern, können Sie in jedes der unterstützten Ausgabeformate rendern.</span><span class="sxs-lookup"><span data-stu-id="98d01-124">When you render a report using the SOAP API <xref:ReportExecution2005.ReportExecutionService.Render%2A> method, you can render to any of the supported output formats.</span></span>  
  
 <span data-ttu-id="98d01-125">Sie können auch die frei verteilbaren Report Viewer-Steuerelemente verwenden, die in enthalten sind [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98d01-125">You can also use the freely distributable ReportViewer controls that are included with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span> <span data-ttu-id="98d01-126">Durch die ReportViewer-Steuerelemente kann [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Funktionalität problemlos in benutzerdefinierte Anwendungen eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="98d01-126">The ReportViewer controls make it easy to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality into custom applications.</span></span> <span data-ttu-id="98d01-127">Die ReportViewer-Steuerelemente wurden für Entwickler konzipiert, die vorbereitete, vollständig erstellte Berichte als Bestandteil einer Anwendungsfunktionsgruppe bereitstellen möchten, z. B. für eine Anwendung zur Websiteverwaltung mit Berichten, die Analysen von Klickströmen für Unternehmenswebsites enthalten.</span><span class="sxs-lookup"><span data-stu-id="98d01-127">The ReportViewer controls are intended for developers who want to provide predesigned, fully authored reports as part of an application feature set (for example, a Web site management application might include reports that show click-stream analysis on company Web sites).</span></span> <span data-ttu-id="98d01-128">Das Einbetten der Steuerelemente in eine Anwendung stellt eine optimierte Alternative zum Aufnehmen der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Serverkomponenten in der Anwendungsbereitstellung dar.</span><span class="sxs-lookup"><span data-stu-id="98d01-128">Embedding the controls in an application provides a streamlined alternative to including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server components in your application deployment.</span></span> <span data-ttu-id="98d01-129">Die Steuerelemente stellen Berichtsfunktionalität bereit, jedoch ohne die in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] vorhandene zusätzliche Unterstützung für das Erstellen, Veröffentlichen, Verteilen und Übermitteln von Berichten.</span><span class="sxs-lookup"><span data-stu-id="98d01-129">The controls provide report functionality, but without the additional report authoring, publication, or distribution and delivery support that you find in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="98d01-130">Es gibt zwei Versionen von ReportViewer-Steuerelementen: eine für umfassende Windows-Clientanwendungen und eine für [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="98d01-130">There are two versions of the ReportViewer controls, one for rich Windows client applications and one for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications.</span></span> <span data-ttu-id="98d01-131">Die Steuerelemente unterstützen sowohl den lokalen Verarbeitungsmodus als auch den Remoteverarbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="98d01-131">The controls support both local processing and remote processing modes.</span></span> <span data-ttu-id="98d01-132">Beim lokalen Verarbeitungsmodus stellt die Anwendung die Berichtsdefinition und -Datasets bereit und löst die Berichtsverarbeitung aus.</span><span class="sxs-lookup"><span data-stu-id="98d01-132">In local processing mode, your application provides the report definition and datasets and triggers report processing.</span></span> <span data-ttu-id="98d01-133">Beim Remoteverarbeitungsmodus finden Datenabruf und Berichtsverarbeitung auf dem Berichtsserver statt, und die Steuerung wird für die Anzeige und für die Berichtsnavigation verwendet.</span><span class="sxs-lookup"><span data-stu-id="98d01-133">In remote processing mode, data retrieval and report processing happen on the report server and the control is used for display and report navigation.</span></span> <span data-ttu-id="98d01-134">Mit diesem Modell können Sie anspruchsvolle Anwendungen erstellen, die vom Desktop auf das Unternehmen zugeschnitten werden können.</span><span class="sxs-lookup"><span data-stu-id="98d01-134">This model allows you to build rich applications that can be scaled from desktop to the enterprise.</span></span>  
  
 <span data-ttu-id="98d01-135">ReportViewer-Steuerelemente sind in der Onlinehilfe zu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="98d01-135">ReportViewer controls are documented in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] online Help.</span></span> <span data-ttu-id="98d01-136">Weitere Informationen finden Sie in der Produktdokumentation zu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98d01-136">For more information, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] product documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d01-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98d01-137">See Also</span></span>  
 <span data-ttu-id="98d01-138">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="98d01-138">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="98d01-139">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="98d01-139">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="98d01-140">Verwenden der SOAP-API in einer Webanwendung</span><span class="sxs-lookup"><span data-stu-id="98d01-140">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
  
  
