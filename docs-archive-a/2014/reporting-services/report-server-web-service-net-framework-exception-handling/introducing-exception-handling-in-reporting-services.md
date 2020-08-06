---
title: Einführung der Ausnahmebehandlung in Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 091b1f40d293515617e369b750a5f18dfe12951b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699320"
---
# <a name="introducing-exception-handling-in-reporting-services"></a><span data-ttu-id="35224-102">Einführung in die Ausnahmebehandlung in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="35224-102">Introducing Exception Handling in Reporting Services</span></span>
  <span data-ttu-id="35224-103">Wenn die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Anwendung die Anforderung an den Berichtsserver-Webdienst sendet, dass der Dienst die Verarbeitung nicht durchführen kann, gibt der Dienst eine SOAP-Ausnahme an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="35224-103">If your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application sends a request to the Report Server Web service that the service is unable to process, the service returns a SOAP exception to the client.</span></span> <span data-ttu-id="35224-104">Die Behandlung von Ausnahmen, die vom Berichtsserver-Webdienst ausgelöst werden, stellt einen wichtigen Teil der Anwendungen dar, die Sie entwickeln, da Sie damit sinnvolle Informationen an die Benutzer zurückgeben können, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="35224-104">Handling exceptions thrown by the Report Server Web service is an important part of the applications that you develop because you can return useful information to users when errors occur.</span></span>  
  
 <span data-ttu-id="35224-105">Dieser Abschnitt enthält spezielle Informationen zur Ausnahmebehandlung, damit ungültige Benutzereingaben verhindert und sinnvolle Fehlermeldungen an die Benutzer ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="35224-105">This section contains specific information about handling exceptions, preventing user input that is not valid, and returning meaningful error information to users.</span></span> <span data-ttu-id="35224-106">Allgemeine Informationen zur Ausnahmebehandlung finden Sie unter "behandeln und Auslösen von Ausnahmen" in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="35224-106">For general information about exception handling, see "Handling and Throwing Exceptions" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35224-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="35224-107">In This Section</span></span>  
  
|<span data-ttu-id="35224-108">Thema</span><span class="sxs-lookup"><span data-stu-id="35224-108">Topic</span></span>|<span data-ttu-id="35224-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="35224-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="35224-110">Behandeln von Ausnahmen in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="35224-110">Handling Exceptions in Reporting Services</span></span>](handling-exceptions-in-reporting-services.md)|<span data-ttu-id="35224-111">Bietet eine Übersicht der Ausnahmen in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] und die Rolle von SOAP, wenn Fehler von einem Webdienst zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="35224-111">Provides an overview of exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and the role of SOAP in returning errors from a Web service.</span></span>|  
|[<span data-ttu-id="35224-112">Bewährte Methoden für die Ausnahmebehandlung in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="35224-112">Best Practices for Reporting Services Exception Handling</span></span>](best-practices/best-practices-for-reporting-services-exception-handling.md)|<span data-ttu-id="35224-113">Gibt Empfehlungen darüber, wie Ausnahmen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] behandelt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="35224-113">Provides recommendations on how to handle exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="35224-114">Reporting Services-SoapException-Klasse</span><span class="sxs-lookup"><span data-stu-id="35224-114">Reporting Services SoapException Class</span></span>](soapexception-class/reporting-services-soapexception-class.md)|<span data-ttu-id="35224-115">Beschreibt die **SoapException**-Klasse in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35224-115">Describes the **SoapException** class in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35224-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35224-116">See Also</span></span>  
 [<span data-ttu-id="35224-117">Erstellen von Anwendungen mit dem Webdienst und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="35224-117">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
