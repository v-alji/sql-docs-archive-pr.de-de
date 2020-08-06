---
title: Zugriff auf die SOAP-API | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- XML Web service [Reporting Services], WSDL
- Web service [Reporting Services], SOAP
- calling Web service
- SOAP [Reporting Services], accessing
- Report Server Web service, SOAP
- Web service [Reporting Services], WSDL
- WSDL [Reporting Services]
- XML Web service [Reporting Services], SOAP
- Report Server Web service, WSDL
- referencing WSDL
ms.assetid: 63bb870a-4dbf-46bd-8921-78f8ebe5fd75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e8a0c21bb53deff746cfd916b6ae2c96fa0de19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621333"
---
# <a name="accessing-the-soap-api"></a><span data-ttu-id="11a45-102">Accessing the SOAP API</span><span class="sxs-lookup"><span data-stu-id="11a45-102">Accessing the SOAP API</span></span>
  <span data-ttu-id="11a45-103">Der Berichtsserver-Webdienst verwendet SOAP (Simple Object Access Protocol) über HTTP und agiert als Kommunikationsschnittstelle zwischen den Clientprogrammen und dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="11a45-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="11a45-104">Der Webdienst verfügt über zwei Endpunkte (einen für die Berichtsausführung und einen für die Berichtsverwaltung) und besteht aus Methoden und einer Reihe komplexer Typenobjekte, anhand derer Sie auf die kompletten Funktionen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="11a45-104">The Web service provides two endpoints - one for report execution and one for report management - and consists of methods and a set of complex type objects that you can use to access the complete functionality of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="11a45-105">Um den Dienst aufzurufen, müssen Sie auf die Reporting Services-WSDL (Web Services Description Language) verweisen.</span><span class="sxs-lookup"><span data-stu-id="11a45-105">To call the service, you must reference the Reporting Services Web Services Description Language (WSDL).</span></span>  
  
## <a name="referencing-the-reporting-services-wsdl"></a><span data-ttu-id="11a45-106">Verweisen auf die Reporting Services-WSDL</span><span class="sxs-lookup"><span data-stu-id="11a45-106">Referencing the Reporting Services WSDL</span></span>  
 <span data-ttu-id="11a45-107">Um einen Webdienst erfolgreich aufzurufen, müssen Sie wissen, wie auf den Dienst zugegriffen wird, welche Vorgänge der Dienst unterstützt, welche Parameter der Dienst benötigt und was der Dienst zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="11a45-107">To call a Web service successfully, you must know how to access the service, what operations the service supports, what parameters the service expects, and what the service returns.</span></span> <span data-ttu-id="11a45-108">WSDL stellt diese Informationen in einem XML-Dokument bereit, das von einem Computer gelesen oder verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="11a45-108">WSDL provides this information in an XML document that can be read or processed by a computer.</span></span>  
  
 <span data-ttu-id="11a45-109">Die Berichtsserver-Webdienste werden an drei unterschiedlichen Endpunkten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="11a45-109">The Report Server Web services are exposed in three different endpoints.</span></span> <span data-ttu-id="11a45-110">Der Name der WSDL-Datei ist für jeden Endpunkt anders.</span><span class="sxs-lookup"><span data-stu-id="11a45-110">The name of the WSDL file is different for each endpoint.</span></span> <span data-ttu-id="11a45-111">Der <xref:ReportService2010>-Endpunkt enthält Methoden zum Verwalten von Objekten auf einem Berichtsserver im einheitlichen Modus oder integrierten SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="11a45-111">The <xref:ReportService2010> endpoint contains methods for managing objects in a Report Server in either native or SharePoint integrated mode.</span></span> <span data-ttu-id="11a45-112">Auf die WSDL für diesen Endpunkt wird über `ReportService2010.asmx?wsdl.` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="11a45-112">The WSDL for this endpoint is accessed through `ReportService2010.asmx?wsdl.`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11a45-113">Der <xref:ReportService2005>-Endpunkt und der <xref:ReportService2006>-Endpunkt sind in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="11a45-113">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="11a45-114">Der <xref:ReportService2010>-Endpunkt schließt die Funktionen beider Endpunkte ein und beinhaltet zusätzliche Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="11a45-114">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
-   <span data-ttu-id="11a45-115">Der <xref:ReportExecution2005>-Endpunkt ermöglicht es Entwicklern, Berichte programmgesteuert auf einem Berichtsserver zu verarbeiten und zu rendern.</span><span class="sxs-lookup"><span data-stu-id="11a45-115">The <xref:ReportExecution2005> endpoint allows developers to programmatically process and render reports in a Report Server.</span></span> <span data-ttu-id="11a45-116">Sie können über `ReportExecution2005.asmx?wsdl` auf die WSDL dieses Endpunkts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="11a45-116">The WSDL for this endpoint is accessed through `ReportExecution2005.asmx?wsdl`.</span></span>  
  
 <span data-ttu-id="11a45-117">WSDL kann von Development Kits verwendet werden, die SOAP-und Webdienste unterstützen, z [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] . b. das SDK.</span><span class="sxs-lookup"><span data-stu-id="11a45-117">WSDL can be consumed by development kits that support SOAP and Web services, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="11a45-118">Das folgende Beispiel zeigt das Format der URL zur [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Verwaltungs-WSDL-Datei:</span><span class="sxs-lookup"><span data-stu-id="11a45-118">The following example shows the format of the URL to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] management WSDL file:</span></span>  
  
```  
http://server/reportserver/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="11a45-119">In der folgenden Tabelle werden die einzelnen Elemente in der URL beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11a45-119">The following table describes each element in the URL.</span></span>  
  
|<span data-ttu-id="11a45-120">URL-Element</span><span class="sxs-lookup"><span data-stu-id="11a45-120">URL element</span></span>|<span data-ttu-id="11a45-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11a45-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="11a45-122">*server*</span><span class="sxs-lookup"><span data-stu-id="11a45-122">*server*</span></span>|<span data-ttu-id="11a45-123">Der Name des Servers, auf dem der Berichtsserver eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="11a45-123">The name of the server on which the report server is deployed.</span></span>|  
|<span data-ttu-id="11a45-124">*Report Server*</span><span class="sxs-lookup"><span data-stu-id="11a45-124">*reportserver*</span></span>|<span data-ttu-id="11a45-125">Der Name des Ordners, der den XML-Webdienst enthält.</span><span class="sxs-lookup"><span data-stu-id="11a45-125">The name of the folder that contains the XML Web service.</span></span> <span data-ttu-id="11a45-126">Dieser wird während des Setups konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="11a45-126">This is configured during setup.</span></span>|  
|<span data-ttu-id="11a45-127">*\<endpoint name>. asmx*</span><span class="sxs-lookup"><span data-stu-id="11a45-127">*\<endpoint name>.asmx*</span></span>|<span data-ttu-id="11a45-128">Der Name des Webdienst-Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="11a45-128">The name of the web service endpoint.</span></span>|  
  
 <span data-ttu-id="11a45-129">Weitere Informationen über das WSDL-Format finden Sie in der WSDL-Spezifikation von W3C (World Wide Web Consortium) unter http://www.w3.org/TR/wsdl.</span><span class="sxs-lookup"><span data-stu-id="11a45-129">For more information about the WSDL format, see the World Wide Web Consortium (W3C) WSDL specification at http://www.w3.org/TR/wsdl.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a45-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11a45-130">See Also</span></span>  
 <span data-ttu-id="11a45-131">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="11a45-131">[Building Applications Using the Web Service and the .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="11a45-132">Report Server Web Service (Report Server-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="11a45-132">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
