---
title: Berichtsserver-Webdienstendpunkte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70281c5171eb37d9888d663542a7850820c81bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717359"
---
# <a name="report-server-web-service-endpoints"></a><span data-ttu-id="1a8cf-102">Report Server-Webdienst-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="1a8cf-102">Report Server Web Service Endpoints</span></span>
  <span data-ttu-id="1a8cf-103">Der Report Server-Webdienst stellt mehrere Endpunkte für die Verwaltung eines Berichtsservers sowie für das Ausführen von Berichten und die Berichtsnavigation bereit.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-103">The Report Server Web service provides several endpoints for managing a report server as well as executing and navigating reports.</span></span>  
  
## <a name="the-management-endpoints"></a><span data-ttu-id="1a8cf-104">Die Verwaltungsendpunkte</span><span class="sxs-lookup"><span data-stu-id="1a8cf-104">The Management Endpoints</span></span>  
 <span data-ttu-id="1a8cf-105">Drei Endpunkte sind für das Verwalten von Objekten auf einem Berichtsserver verfügbar: <xref:ReportService2005>, <xref:ReportService2006> und <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-105">There are three endpoints available for managing objects on a report server, <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010>.</span></span> <span data-ttu-id="1a8cf-106">Der <xref:ReportService2005>-Endpunkt wird zum Verwalten von Objekten auf einem Berichtsserver verwendet, der für den einheitlichen Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-106">The <xref:ReportService2005> endpoint is used for managing objects on a report server that is configured for native mode.</span></span> <span data-ttu-id="1a8cf-107">Der <xref:ReportService2006>-Endpunkt wird zum Verwalten von Objekten auf einem Berichtsserver verwendet, der für den integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-107">The <xref:ReportService2006> endpoint is used for managing objects on a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="1a8cf-108">Der <xref:ReportService2010>-Endpunkt führt die Funktionen von <xref:ReportService2005> und <xref:ReportService2006> zusammen und kann Objekte auf einem Berichtsserver verwalten, die entweder für den einheitlichen oder integrierten SharePoint-Modus konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-108">The <xref:ReportService2010> endpoint merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage objects on a report server that are configured for either native or SharePoint integrated mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1a8cf-109">Wenn ein Berichtsserver für den integrierten SharePoint-Modus konfiguriert ist, geben die <xref:ReportService2005>-APIs einen `rsOperationNotSupportedSharePointMode`-Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-109">When a report server is configured for SharePoint integrated mode, the <xref:ReportService2005> APIs will return an `rsOperationNotSupportedSharePointMode` error.</span></span> <span data-ttu-id="1a8cf-110">Wenn der Berichtsserver für den einheitlichen Modus konfiguriert ist, geben die <xref:ReportService2006>-APIs einen `rsOperationNotSupportedNativeMode`-Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-110">If the report server is configured for native mode, the <xref:ReportService2006> APIs will return an `rsOperationNotSupportedNativeMode` error.</span></span> <span data-ttu-id="1a8cf-111">Auch wenn modusspezifische APIs in <xref:ReportService2010> in einem nicht beabsichtigten Modus verwendet werden, geben die APIs die entsprechenden Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-111">Similarly, when mode-specific APIs in <xref:ReportService2010> are used on unintended modes, the APIs will return the respective errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a8cf-112">Der <xref:ReportService2005>-Endpunkt und der <xref:ReportService2006>-Endpunkt sind in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-112">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="1a8cf-113">Der <xref:ReportService2010>-Endpunkt schließt die Funktionen beider Endpunkte ein und beinhaltet zusätzliche Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-113">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="1a8cf-114">Wenn der Berichtsserver für den einheitlichen Modus oder den integrierten SharePoint-Modus konfiguriert ist, kann über eine der folgenden URLs auf die WSDL für den Verwaltungsendpunkt zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="1a8cf-114">If the report server is configured for native mode or SharePoint integrate mode, the WSDL for the management endpoint can be accessed using one of the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="1a8cf-115">Weitere Informationen finden Sie unter [Accessing the SOAP API (Zugriff auf die SOAP-API)](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="1a8cf-115">For more information, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="the-execution-endpoint"></a><span data-ttu-id="1a8cf-116">Der Ausführungsendpunkt</span><span class="sxs-lookup"><span data-stu-id="1a8cf-116">The Execution Endpoint</span></span>  
 <span data-ttu-id="1a8cf-117">Der <xref:ReportExecution2005>-Endpunkt ermöglicht es den Entwicklern, die Berichtsverarbeitung sowie das Rendern von einem Berichtsserver sowohl im einheitlichen als auch im integrierten SharePoint-Modus problemlos anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-117">The <xref:ReportExecution2005> endpoint makes it easy for developers to customize report processing and rendering from a report server in both native and SharePoint integrated modes.</span></span> <span data-ttu-id="1a8cf-118">Der Endpunkt enthält Klassen und Methoden aus den Vorgängerversionen des Report Server-Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-118">The endpoint includes classes and methods that existed in earlier versions of the Report Server Web service.</span></span> <span data-ttu-id="1a8cf-119">Darüber hinaus wurden dem Report Server-Webdienst viele neue Klassen und Methoden hinzugefügt, die über den Ausführungsendpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-119">In addition, many new classes and methods have been added to the Report Server Web service that are exposed through the execution endpoint.</span></span>  
  
 <span data-ttu-id="1a8cf-120">Auf die WSDL-Datei für den Verwaltungsendpunkt kann über die folgende URL zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="1a8cf-120">The WSDL for the management endpoint can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="1a8cf-121">Wenn der Berichtsserver für den integrierten SharePoint-Modus konfiguriert ist, kann über die folgende URL auf die WSDL-Datei zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="1a8cf-121">If the report server is configured for SharePoint integrate mode, the WSDL can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="1a8cf-122">Weitere Informationen finden Sie unter [Accessing the SOAP API (Zugriff auf die SOAP-API)](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="1a8cf-122">For more information, please see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="sharepoint-proxy-endpoints"></a><span data-ttu-id="1a8cf-123">SharePoint-Proxyendpunkte</span><span class="sxs-lookup"><span data-stu-id="1a8cf-123">SharePoint Proxy Endpoints</span></span>  
 <span data-ttu-id="1a8cf-124">Wenn ein Berichtsserver für den integrierten SharePoint-Modus konfiguriert und das [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Add-In installiert ist, wird ein Satz von Proxyendpunkten auf dem SharePoint-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-124">When a report server is configured for SharePoint integrated mode and the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in has been installed, a set of proxy endpoints are installed on the SharePoint server.</span></span> <span data-ttu-id="1a8cf-125">Bei den Proxyendpunkten handelt es sich um die primäre API für das Entwickeln von Berichtslösungen, wenn ein Berichtsserver für den integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-125">The proxy endpoints are the primary API for developing report solutions when a report server is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="1a8cf-126">Wenn Sie für die Proxyendpunkte entwickeln, verwaltet das [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Add-In den Austausch der Anmeldeinformationen zwischen dem SharePoint-Server und dem Berichtsserver im Authentifizierungsmodus Vertrauenswürdiges Konto.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-126">When developing against the proxy endpoints, the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in manages the exchange of credentials between the SharePoint server and the report server in Trusted account authentication mode.</span></span> <span data-ttu-id="1a8cf-127">Wenn Sie für die Berichtsserverendpunkte entwickeln, muss die aufrufende Anwendung den Austausch der Anmeldeinformationen im Authentifizierungsmodus Vertrauenswürdiges Konto behandeln.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-127">When developing against the report server endpoints, the calling application will have to manage the credential exchange in Trusted account authentication mode.</span></span> <span data-ttu-id="1a8cf-128">In der folgenden Tabelle sind die Endpunkte aufgeführt, die mit dem [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Add-In installiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-128">The following table lists the endpoints that are installed with the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
|<span data-ttu-id="1a8cf-129">Proxyendpunkt</span><span class="sxs-lookup"><span data-stu-id="1a8cf-129">Proxy Endpoint</span></span>|<span data-ttu-id="1a8cf-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8cf-130">Description</span></span>|  
|--------------------|-----------------|  
|<xref:ReportService2006>|<span data-ttu-id="1a8cf-131">Stellt die APIs für das Verwalten eines Berichtsservers bereit, der für den integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-131">Provides the APIs for managing a report server that is configured for SharePoint integrate mode.</span></span> <span data-ttu-id="1a8cf-132">**Hinweis:**  Dieser Endpunkt ist in veraltet [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a8cf-132">**Note:**  This endpoint is deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span>|  
|<xref:ReportService2010>|<span data-ttu-id="1a8cf-133">Stellt die APIs für das Verwalten eines Berichtsservers bereit, der entweder für den einheitlichen Modus oder für den integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-133">Provides the APIs for managing a report server that is configured for either native or SharePoint integrated mode.</span></span>|  
|<xref:ReportExecution2005>|<span data-ttu-id="1a8cf-134">Stellt die APIs für die Ausführung von Berichten und die Berichtsnavigation bereit.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-134">Provides the APIs for running and navigating reports.</span></span>|  
|<xref:ReportServiceAuthentication>|<span data-ttu-id="1a8cf-135">Stellt die APIs zum Authentifizieren von Benutzern für einen Berichtsserver bereit, wenn die SharePoint-Webanwendung für die Formularauthentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-135">Provides the APIs for authenticating users against a report server when the SharePoint Web application is configured for Forms Authentication.</span></span>|  
  
 <span data-ttu-id="1a8cf-136">Nachfolgend finden Sie Beispiel-URLs für Verweise auf die Proxyendpunkte auf einer SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="1a8cf-136">The following are example URLs for referencing the proxy endpoints on a SharePoint site.</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a8cf-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a8cf-137">See Also</span></span>  
 [<span data-ttu-id="1a8cf-138">Erstellen von Anwendungen mit dem Webdienst und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a8cf-138">Building Applications Using the Web Service and the .NET Framework</span></span>](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
