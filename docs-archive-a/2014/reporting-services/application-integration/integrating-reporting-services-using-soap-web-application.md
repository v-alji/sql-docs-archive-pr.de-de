---
title: Verwenden der SOAP-API in einer Webanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], Web applications
- impersonation [Reporting Services]
- user impersonation [Reporting Services]
- report servers [Reporting Services], SOAP
- Web applications [Reporting Services]
ms.assetid: e8ca4455-0dc3-4741-8872-3636114938ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e228f01915df633f50b23bf93e892446863c28ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696509"
---
# <a name="using-the-soap-api-in-a-web-application"></a><span data-ttu-id="b75f1-102">Verwenden der SOAP-API in einer Webanwendung</span><span class="sxs-lookup"><span data-stu-id="b75f1-102">Using the SOAP API in a Web Application</span></span>
  <span data-ttu-id="b75f1-103">Über die Reporting Services-SOAP-API können Sie auf alle Funktionen des Berichtsservers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b75f1-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="b75f1-104">Da es sich um einen Webdienst handelt, kann problemlos auf die SOAP-API zugegriffen werden, um Funktionen zur Unternehmensberichterstellung für Ihre benutzerdefinierten Geschäftsanwendungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b75f1-104">Because it's a Web service, the SOAP API can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="b75f1-105">Wenn Sie über eine Webanwendung auf den Report Server-Webdienst zugreifen, gehen Sie ganz ähnlich vor, als würden Sie über eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anwendung auf die SOAP-API zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b75f1-105">You access the Report Server Web service from a Web application in much the same way that you access the SOAP API from a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="b75f1-106">Mithilfe von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] können Sie eine Proxy Klasse generieren, die die Eigenschaften und Methoden des Report Server-Webdiensts verfügbar macht und es Ihnen ermöglicht, eine vertraute Infrastruktur und Tools zum Erstellen von Geschäftsanwendungen auf der Technologie zu verwenden [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b75f1-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Report Server Web service and enables you to use a familiar infrastructure and tools to build business applications on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
 <span data-ttu-id="b75f1-107">Von einer Webanwendung aus kann auf die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Funktionen für die Berichterstellung ebenso leicht wie von einer Windows-Anwendung aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b75f1-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report management functionality is just as easily accessed from a Web application as from a Windows application.</span></span> <span data-ttu-id="b75f1-108">Wenn Sie mit einer Webanwendung arbeiten, können Sie unter anderem Elemente zur Berichtsserver-Datenbank hinzufügen oder daraus entfernen, Einstellungen für die Elementsicherheit festlegen, Elemente in der Berichtsserver-Datenbank ändern und die Zeitplanung und Übermittlung verwalten.</span><span class="sxs-lookup"><span data-stu-id="b75f1-108">From a Web application, you can add and remove items from the report server database, set item security, modify report server database items, manage scheduling and delivery, and more.</span></span>  
  
## <a name="enabling-impersonation"></a><span data-ttu-id="b75f1-109">Aktivieren des Identitätswechsels</span><span class="sxs-lookup"><span data-stu-id="b75f1-109">Enabling Impersonation</span></span>  
 <span data-ttu-id="b75f1-110">Der erste Schritt beim Konfigurieren der Webanwendung besteht darin, den Identitätswechsel vom Webdienstclient aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b75f1-110">The first step in configuring your Web application is to enable impersonation from the Web service client.</span></span> <span data-ttu-id="b75f1-111">Mit Identitätswechsel können [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]-Anwendungen mit der Identität des Clients ausgeführt werden, in dessen Namen sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b75f1-111">With impersonation, [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications can execute with the identity of the client on whose behalf they are operating.</span></span> [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="b75f1-112">nutzt [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internetinformationsdienste (Internet Information Services, IIS), um den Benutzer zu authentifizieren und ein authentifiziertes Token an die [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]-Anwendung zu übergeben oder ein nicht authentifiziertes Token zu übergeben, falls der Benutzer nicht authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b75f1-112">relies on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) to authenticate the user and either pass an authenticated token to the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application or, if unable to authenticate the user, pass an unauthenticated token.</span></span> <span data-ttu-id="b75f1-113">In jedem dieser Fälle nimmt die [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]-Anwendung die Identität des jeweils empfangenen Tokens an, wenn der Identitätswechsel aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b75f1-113">In either case, the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application impersonates whichever token is received if impersonation is enabled.</span></span> <span data-ttu-id="b75f1-114">Sie können den Identitätswechsel auf dem Client aktivieren, indem Sie die Datei Web.config der Clientanwendung folgendermaßen ändern:</span><span class="sxs-lookup"><span data-stu-id="b75f1-114">You can enable impersonation on the client, by modifying the Web.config file of the client application as follows:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b75f1-115">Der Identitätswechsel ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b75f1-115">Impersonation is disabled by default.</span></span>  
  
 <span data-ttu-id="b75f1-116">Weitere Informationen zum Identitätswechsel finden Sie in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b75f1-116">For more information about [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] impersonation, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="managing-the-report-server-using-soap-api"></a><span data-ttu-id="b75f1-117">Verwalten des Berichtsservers mit der SOAP-API</span><span class="sxs-lookup"><span data-stu-id="b75f1-117">Managing the Report Server using SOAP API</span></span>  
 <span data-ttu-id="b75f1-118">Sie können die Webanwendung auch verwenden, um einen Berichtsserver und seinen Inhalt zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b75f1-118">You can also use your Web application to manage a report server and its contents.</span></span> <span data-ttu-id="b75f1-119">Der mit [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] gelieferte Berichts-Manager ist ein Beispiel für eine Webanwendung, die komplett mit [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] und der Reporting Services-SOAP-API erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b75f1-119">Report Manager, included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], is an example of a Web application that is completely built using [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] and the Reporting Services SOAP API.</span></span> <span data-ttu-id="b75f1-120">Sie können den benutzerdefinierten Webanwendungen die Berichtsverwaltungsfunktionalität des Berichts-Managers hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b75f1-120">You can add the report management functionality of Report Manager to your custom Web applications.</span></span> <span data-ttu-id="b75f1-121">Beispielsweise können Sie eine Liste der verfügbaren Berichte in der Berichts Server-Datenbank zurückgeben und diese in einem-Steuerelement anzeigen, in dem die [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` Benutzer auswählen können.</span><span class="sxs-lookup"><span data-stu-id="b75f1-121">For example, you might want to return a list of available reports in the report server database and display them in a [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control for your users to choose from.</span></span> <span data-ttu-id="b75f1-122">Der folgende Code stellt eine Verbindung zur Berichtsserver-Datenbank her und gibt eine Liste der Elemente in der Berichtsserver-Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="b75f1-122">The following code connects to the report server database and returns a list of items in the report server database.</span></span> <span data-ttu-id="b75f1-123">Die verfügbaren Berichte werden dann zu einem ListBox-Steuerelement hinzugefügt, das für jeden Bericht eine Pfadangabe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b75f1-123">The available reports are then added to a Listbox control, which displays the path of each report.</span></span>  
  
```vb  
Private Sub Page_Load(sender As Object, e As System.EventArgs)  
   ' Create a Web service proxy object and set credentials  
   Dim rs As New ReportingService2005()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return a list of catalog items in the report server database  
   Dim items As CatalogItem() = rs.ListChildren("/", True)  
  
   ' For each report, display the path of the report in a Listbox  
   Dim ci As CatalogItem  
   For Each ci In  items  
      If ci.Type = ItemTypeEnum.Report Then  
         catalogListBox.Items.Add(ci.Path)  
      End If  
   Next ci  
End Sub ' Page_Load   
```  
  
```csharp  
private void Page_Load(object sender, System.EventArgs e)  
{  
   // Create a Web service proxy object and set credentials  
   ReportingService2005 rs = new ReportingService2005();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return a list of catalog items in the report server database  
   CatalogItem[] items = rs.ListChildren("/", true);  
  
   // For each report, display the path of the report in a Listbox  
   foreach(CatalogItem ci in items)  
   {  
      if (ci.Type == ItemTypeEnum.Report)  
         catalogListBox.Items.Add(ci.Path);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b75f1-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b75f1-124">See Also</span></span>  
 <span data-ttu-id="b75f1-125">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="b75f1-125">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="b75f1-126">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b75f1-126">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="b75f1-127">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="b75f1-127">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="b75f1-128">Verwenden der SOAP-API in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b75f1-128">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
  
  
