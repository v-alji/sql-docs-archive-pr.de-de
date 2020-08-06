---
title: Integration von Reporting Services in Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- integrating reports [Reporting Services]
- custom applications [SSRS]
- Reporting Services, application integration
- application integration [Reporting Services]
- reports [Reporting Services], integrating
ms.assetid: 49eb539c-d89b-4291-839a-0ec1a65cd270
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ab92008c5beb4d931e8e781857d766bb56a1efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608417"
---
# <a name="integrating-reporting-services-into-applications"></a><span data-ttu-id="18dc8-102">Integration von Reporting Services in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="18dc8-102">Integrating Reporting Services into Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="18dc8-103">stellt eine offene und erweiterbare Berichtsplattform dar, die Entwicklern eine umfangreiche Reihe von APIs zur Entwicklung von Lösungen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="18dc8-103">is an open and extensible reporting platform designed to provide developers with a comprehensive set of APIs for developing solutions.</span></span>  
  
 <span data-ttu-id="18dc8-104">Es gibt drei Optionen für [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] die Integration in benutzerdefinierte Anwendungen: den Report Server-Webdienst, auch als [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP-API bezeichnet, die Report Viewer-Steuerelemente für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] und den URL-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="18dc8-104">There are three options for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: the Report Server Web service, also known as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API, the ReportViewer controls for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], and URL access.</span></span> <span data-ttu-id="18dc8-105">Jede Option hat einen anderen Ansatz zur Integration von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in die Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="18dc8-105">Each option provides a different approach for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span>  
  
## <a name="report-server-web-service"></a><span data-ttu-id="18dc8-106">Report Server-Webdienst</span><span class="sxs-lookup"><span data-stu-id="18dc8-106">Report Server Web Service</span></span>  
 <span data-ttu-id="18dc8-107">Der Berichtsserver-Webdienst stellt die primäre Schnittstelle zum Entwickeln für [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dar.</span><span class="sxs-lookup"><span data-stu-id="18dc8-107">The Report Server Web service is the primary interface for developing against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="18dc8-108">Unabhängig davon, ob Sie Code zur Verwaltung Ihres Berichtskatalogs oder Code zum Rendern von Berichten in einem unterstützten Format entwickeln, verfügt der Webdienst über alle notwendigen Methoden, um [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in Ihre Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="18dc8-108">Whether you are developing code to manage your report catalog or developing code to render reports to a supported format, the Web service exposes all the necessary methods to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span> <span data-ttu-id="18dc8-109">Ein Beispiel für eine solche Anwendung ist der Berichts-Manager, der in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enthalten ist. Er verwaltet die Berichtsserver-Datenbank mithilfe des Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="18dc8-109">An example of one such application is Report Manager, which is included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; it uses the Web service to manage the report server database.</span></span>  
  
## <a name="reportviewer-controls-for-visual-studio"></a><span data-ttu-id="18dc8-110">ReportViewer-Steuerelemente für Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18dc8-110">ReportViewer Controls for Visual Studio</span></span>  
 <span data-ttu-id="18dc8-111">Mit den in [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] enthaltenen ReportViewer-Steuerelementen können Berichtsanzeigen in Ihre Anwendungen integriert werden.</span><span class="sxs-lookup"><span data-stu-id="18dc8-111">The ReportViewer controls included with [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] are used for integrating report viewing into your applications.</span></span> <span data-ttu-id="18dc8-112">Es gibt zwei Steuerelemente: eines für Windows Forms-Anwendungen und eines für WebForms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="18dc8-112">There are two controls: one for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="18dc8-113">Jedes Steuerelement verfügt über die Möglichkeit zur Anzeige von Berichten, die auf einem Berichtsserver bereitgestellt wurden, sowie zum Rendern von Berichten, die in einer Umgebung vorliegen, in der kein Berichtsserver installiert ist.</span><span class="sxs-lookup"><span data-stu-id="18dc8-113">Each control provides the capability for viewing reports that have been deployed to a report server as well as the ability to render reports that exist in an environment where a report server has not been installed.</span></span>  
  
## <a name="url-access"></a><span data-ttu-id="18dc8-114">URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="18dc8-114">URL Access</span></span>  
 <span data-ttu-id="18dc8-115">Der URL-Zugriff ist eine weitere Option für die Integration der Berichtsanzeige in Ihren Anwendungen, wenn die ReportViewer-Steuerelemente nicht zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="18dc8-115">URL access is another option for integrating report viewing into your applications if the ReportViewer controls are not an option.</span></span> <span data-ttu-id="18dc8-116">Darüber hinaus ist der URL-Zugriff hilfreich, wenn Links zu Berichten per E-Mail an Benutzer gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18dc8-116">In addition, URL access is useful for sending links to reports to users via e-mail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18dc8-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="18dc8-117">In This Section</span></span>  
 [<span data-ttu-id="18dc8-118">Integrieren von Reporting Services mit SOAP</span><span class="sxs-lookup"><span data-stu-id="18dc8-118">Integrating Reporting Services Using SOAP</span></span>](../application-integration/integrating-reporting-services-using-soap.md)  
 <span data-ttu-id="18dc8-119">Beschreibt, wie Sie die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Berichtsnavigation und -verwaltung mithilfe des Berichtsserver-Webdiensts in Ihre vorhandenen Geschäftsanwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="18dc8-119">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management into your existing business applications using the Report Server Web service.</span></span>  
  
 [<span data-ttu-id="18dc8-120">Integrieren von Reporting Services mit den ReportViewer-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="18dc8-120">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
 <span data-ttu-id="18dc8-121">Beschreibt, wie Sie die Berichtsanzeige mithilfe der ReportViewer-Steuerelemente in Ihre vorhandenen Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="18dc8-121">Describes how to integrate report viewing into your existing applications using the ReportViewer controls.</span></span>  
  
 [<span data-ttu-id="18dc8-122">Integrieren von Reporting Services mit URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="18dc8-122">Integrating Reporting Services Using URL Access</span></span>](../application-integration/integrating-reporting-services-using-url-access.md)  
 <span data-ttu-id="18dc8-123">Beschreibt, wie Sie die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Berichtsnavigation mithilfe des URL-Zugriffs in Ihre vorhandenen Geschäftsanwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="18dc8-123">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation into your existing business applications using URL access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18dc8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18dc8-124">See Also</span></span>  
 <span data-ttu-id="18dc8-125">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="18dc8-125">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="18dc8-126">[Auswählen zwischen URL-Zugriff und SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span><span class="sxs-lookup"><span data-stu-id="18dc8-126">[Choosing Between URL Access and SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span></span>  
 <span data-ttu-id="18dc8-127">[Technische Referenz &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18dc8-127">[Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="18dc8-128">Report Server Web Service (Report Server-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="18dc8-128">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
