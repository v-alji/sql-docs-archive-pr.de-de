---
title: Integrieren von Reporting Services mit SOAP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, application integration
- SOAP [Reporting Services]
- SOAP [Reporting Services], about report integration
- integrating reports [Reporting Services]
- Web service [Reporting Services], application integration
ms.assetid: 6bc17af5-883c-4bfa-87d9-48cd7056d145
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7b6fffd65b22900d7c505c4b50ec290b95fe9ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608411"
---
# <a name="integrating-reporting-services-using-soap"></a><span data-ttu-id="cbe57-102">Integrieren von Reporting Services mit SOAP</span><span class="sxs-lookup"><span data-stu-id="cbe57-102">Integrating Reporting Services Using SOAP</span></span>
  <span data-ttu-id="cbe57-103">Die [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP-API verfügt über mehrere Webdienst-Endpunkte zum Entwickeln von benutzerdefinierten Berichtslösungen.</span><span class="sxs-lookup"><span data-stu-id="cbe57-103">The [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API provides several Web service endpoints for developing custom reporting solutions.</span></span> <span data-ttu-id="cbe57-104">Die Endpunkte lassen sich derzeit in zwei Kategorien unterteilen: Verwaltung und Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cbe57-104">The endpoints currently fall into two categories: management and execution.</span></span> <span data-ttu-id="cbe57-105">Die Verwaltungsfunktionen werden durch die Endpunkte <xref:ReportService2005>, <xref:ReportService2006> und <xref:ReportService2010> verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="cbe57-105">The management functionality is exposed through the <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010> endpoints.</span></span> <span data-ttu-id="cbe57-106">Mit dem <xref:ReportService2005>-Endpunkt wird ein Berichtsserver verwaltet, der im einheitlichen Modus konfiguriert ist, und mit dem <xref:ReportService2006>-Endpunkt wird ein Berichtsserver verwaltet, der für den integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cbe57-106">The <xref:ReportService2005> endpoint is used for managing a report server that is configured in native mode and the <xref:ReportService2006> endpoint is used for managing a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="cbe57-107">Der <xref:ReportService2010>-Endpunkt führt die Funktionen von <xref:ReportService2005> und <xref:ReportService2006> zusammen und kann einen Berichtsserver verwalten, der entweder für den einheitlichen Modus oder integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cbe57-107">The <xref:ReportService2010> merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage a report server that is configured for either native or SharePoint integrated mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbe57-108">Der <xref:ReportService2005>-Endpunkt und der <xref:ReportService2006>-Endpunkt sind in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="cbe57-108">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="cbe57-109">Der <xref:ReportService2010>-Endpunkt schließt die Funktionen beider Endpunkte ein und beinhaltet zusätzliche Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="cbe57-109">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="cbe57-110">Die Ausführungsfunktion wird durch den <xref:ReportExecution2005>-Endpunkt verfügbar gemacht und wird verwendet, wenn der Berichtsserver im einheitlichen Modus oder im integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cbe57-110">The execution functionality is exposed through the <xref:ReportExecution2005> endpoint and it is used when the report server is configured in native or SharePoint integrated mode.</span></span> <span data-ttu-id="cbe57-111">Folgende Themen zeigen, wie diese Endpunkte für die Entwicklung von Berichtslösungen in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-, SharePoint- und Webanwendungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="cbe57-111">The following topics show how these endpoints can be used for developing reporting solutions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint, and Web applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbe57-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cbe57-112">In This Section</span></span>  
 [<span data-ttu-id="cbe57-113">Verwenden der SOAP-API in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="cbe57-113">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
 <span data-ttu-id="cbe57-114">Beschreibt, wie Sie die SOAP-API verwenden, um [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in eine Windows-Umgebung zu integrieren</span><span class="sxs-lookup"><span data-stu-id="cbe57-114">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Windows environment.</span></span>  
  
 [<span data-ttu-id="cbe57-115">Verwenden der SOAP-API in einer Webanwendung</span><span class="sxs-lookup"><span data-stu-id="cbe57-115">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
 <span data-ttu-id="cbe57-116">Beschreibt, wie Sie die SOAP-API verwenden, um [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in eine Webumgebung zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="cbe57-116">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe57-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbe57-117">See Also</span></span>  
 <span data-ttu-id="cbe57-118">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cbe57-118">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="cbe57-119">[Berichtsserver-Webdienst](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cbe57-119">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 [<span data-ttu-id="cbe57-120">Erstellen von Anwendungen mit dem Webdienst und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cbe57-120">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
