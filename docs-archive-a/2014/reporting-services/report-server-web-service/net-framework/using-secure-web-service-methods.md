---
title: Verwenden von sicheren Webdienstmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], secure connections
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: 87329299-c2ea-4517-9148-d855726768a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e88a164602f9bbe6ad42c3897285a484cac94466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723374"
---
# <a name="using-secure-web-service-methods"></a><span data-ttu-id="21fb5-102">Verwenden von sicheren Webdienstmethoden</span><span class="sxs-lookup"><span data-stu-id="21fb5-102">Using Secure Web Service Methods</span></span>
  <span data-ttu-id="21fb5-103">Es kann sein, dass für bestimmte Berichtsserver-Webdienstmethoden eine sichere Verbindung erforderlich ist, wenn Sie diese aufrufen.</span><span class="sxs-lookup"><span data-stu-id="21fb5-103">Certain Report Server Web service methods may require a secure connection when you invoke them.</span></span> <span data-ttu-id="21fb5-104">Die Methoden, die eine sichere Verbindung benötigen, werden von der Einstellung `SecureConnectionLevel` in der Datei RSReportServer.config bestimmt.</span><span class="sxs-lookup"><span data-stu-id="21fb5-104">The methods that require a secure connection are determined by the `SecureConnectionLevel` setting in the RSReportServer.config file.</span></span> <span data-ttu-id="21fb5-105">Der Wert der Einstellung ist ein ganzzahliger Wert im gültigen Bereich von 0 und höher.</span><span class="sxs-lookup"><span data-stu-id="21fb5-105">The value of the setting is an integer value with a valid range of 0 and higher.</span></span> <span data-ttu-id="21fb5-106">In der folgenden Tabelle werden diese Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21fb5-106">The following table describes these values.</span></span>  
  
|<span data-ttu-id="21fb5-107">Ebene</span><span class="sxs-lookup"><span data-stu-id="21fb5-107">Level</span></span>|<span data-ttu-id="21fb5-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21fb5-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="21fb5-109">**0**</span><span class="sxs-lookup"><span data-stu-id="21fb5-109">**0**</span></span>|<span data-ttu-id="21fb5-110">Nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="21fb5-110">Not secure.</span></span> <span data-ttu-id="21fb5-111">Aufrufe an die Reporting Services-SOAP-API benötigen keine sichere Verbindung.</span><span class="sxs-lookup"><span data-stu-id="21fb5-111">Calls made to the Reporting Services SOAP API do not require a secure connection.</span></span>|  
|<span data-ttu-id="21fb5-112">Größer als **0**</span><span class="sxs-lookup"><span data-stu-id="21fb5-112">Greater than **0**</span></span>|<span data-ttu-id="21fb5-113">Sicher.</span><span class="sxs-lookup"><span data-stu-id="21fb5-113">Secure.</span></span> <span data-ttu-id="21fb5-114">Alle Aufrufe an die Reporting Services-SOAP-API benötigen eine sichere Verbindung.</span><span class="sxs-lookup"><span data-stu-id="21fb5-114">All calls made to the Reporting Services SOAP API require a secure connection.</span></span>|  
  
 <span data-ttu-id="21fb5-115">Sie können mithilfe der <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>-Methode des Webdiensts eine Liste der Webdienstmethoden zurückgeben, die entsprechend der aktuellen Konfiguration des Berichtsservers eine sichere Verbindung benötigen.</span><span class="sxs-lookup"><span data-stu-id="21fb5-115">You can use the <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> method of the Web service to return a list of Web service methods that require a secure connection according to the current configuration of the report server.</span></span> <span data-ttu-id="21fb5-116">In einem SSL-Szenario sollten Sie die Liste der von <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> zurückgegebenen Methoden überprüfen und den Schema-Namen der Webdienst-URI entsprechend der aufgerufenen Methode in "https" oder "http" ändern.</span><span class="sxs-lookup"><span data-stu-id="21fb5-116">In an SSL scenario, you should evaluate the list of methods that are returned by <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> and change the scheme name of the Web service URI to "https" or "http" depending on the method being called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fb5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21fb5-117">See Also</span></span>  
 <span data-ttu-id="21fb5-118">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="21fb5-118">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="21fb5-119">Report Server Web Service (Report Server-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="21fb5-119">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
