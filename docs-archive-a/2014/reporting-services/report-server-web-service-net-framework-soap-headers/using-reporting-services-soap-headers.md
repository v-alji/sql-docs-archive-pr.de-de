---
title: Verwenden von Reporting Services SOAP-Headern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- SOAP headers [Reporting Services]
- SOAP [Reporting Services], headers
- XML Web service [Reporting Services], SOAP
ms.assetid: 306d2c06-a25a-40f8-8a35-13dd32e8841e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f48be183398d4d441b5781c9f9467178c3011e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717371"
---
# <a name="using-reporting-services-soap-headers"></a><span data-ttu-id="11392-102">Verwenden von Reporting Services SOAP-Headern</span><span class="sxs-lookup"><span data-stu-id="11392-102">Using Reporting Services SOAP Headers</span></span>
  <span data-ttu-id="11392-103">Die Kommunikation mit einer Webdienstmethode über SOAP erfolgt nach einem Standardformat.</span><span class="sxs-lookup"><span data-stu-id="11392-103">Communication with a Web service method using SOAP follows a standard format.</span></span> <span data-ttu-id="11392-104">Teil dieses Formats bilden die Daten, die in einem XML-Dokument verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="11392-104">Part of this format is the data that is encoded in an XML document.</span></span> <span data-ttu-id="11392-105">Das XML-Dokument besteht aus einem **Envelope**-Stammelement, das sich wiederum aus einem erforderlichen **Textkörper**-Element und einem optionalen **Header**-Element zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="11392-105">The XML document consists of a root **Envelope** element, which in turn consists of a required **Body** element and an optional **Header** element.</span></span> <span data-ttu-id="11392-106">Das **Textelement** enthält die für die Meldung spezifischen Daten.</span><span class="sxs-lookup"><span data-stu-id="11392-106">The **Body** element contains the data specific to the message.</span></span> <span data-ttu-id="11392-107">Das optionale **Header**-Element kann zusätzliche Informationen umfassen, die sich nicht direkt auf die spezifische Meldung beziehen.</span><span class="sxs-lookup"><span data-stu-id="11392-107">The optional **Header** element can contain additional information not directly related to the particular message.</span></span> <span data-ttu-id="11392-108">Die untergeordneten Elemente des **Header**-Elements werden SOAP-Header genannt.</span><span class="sxs-lookup"><span data-stu-id="11392-108">Each child element of the **Header** element is called a SOAP header.</span></span>  
  
 <span data-ttu-id="11392-109">Obwohl die SOAP-Header Daten enthalten können, die sich auf die Meldung beziehen, beinhalten sie in der Regel von der Infrastruktur des Webservers verarbeitete Informationen.</span><span class="sxs-lookup"><span data-stu-id="11392-109">Although the SOAP headers can contain data related to the message, they typically contain information processed by the Web server infrastructure.</span></span>  
  
 <span data-ttu-id="11392-110">Die Berichtsserver-Webdienste definieren mehrere Klassen für die Verwendung im SOAP-Header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader> und <xref:ReportExecution2005.ExecutionHeader>.</span><span class="sxs-lookup"><span data-stu-id="11392-110">The Report Server Web services define several classes for use in the SOAP header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader>, and <xref:ReportExecution2005.ExecutionHeader>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11392-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="11392-111">In This Section</span></span>  
  
|<span data-ttu-id="11392-112">Thema</span><span class="sxs-lookup"><span data-stu-id="11392-112">Topic</span></span>|<span data-ttu-id="11392-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11392-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="11392-114">Methoden der Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="11392-114">Batching Methods</span></span>](batching-methods.md)|<span data-ttu-id="11392-115">Beschreibt, wie mehrere Vorgänge mithilfe von <xref:ReportService2005.BatchHeader> in einer Batchtransaktion verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="11392-115">Describes how to batch multiple operations into a single transaction using <xref:ReportService2005.BatchHeader>.</span></span>|  
|[<span data-ttu-id="11392-116">Identifizieren des Ausführungsstatus</span><span class="sxs-lookup"><span data-stu-id="11392-116">Identifying Execution State</span></span>](identifying-execution-state.md)|<span data-ttu-id="11392-117">Beschreibt, wie der Sitzungsstatus in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] mit **SessionHeader** (Sitzungsheader) verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="11392-117">Describes how to manage session state in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] using **SessionHeader**.</span></span>|  
|[<span data-ttu-id="11392-118">Festlegen des Elementnamespaces für die GetProperties-Methode</span><span class="sxs-lookup"><span data-stu-id="11392-118">Setting the Item Namespace for the GetProperties Method</span></span>](setting-the-item-namespace-for-the-getproperties-method.md)|<span data-ttu-id="11392-119">Beschreibt, wie Eigenschaften anhand des Pfads oder der ID des Elements mit der <xref:ReportService2010.ReportingService2010.GetProperties%2A>-Methode und dem <xref:ReportService2010.ItemNamespaceHeader>-SOAP-Header abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="11392-119">Describes how to retrieve properties based on either the path or the ID of an item by using the <xref:ReportService2010.ReportingService2010.GetProperties%2A> method and the <xref:ReportService2010.ItemNamespaceHeader> SOAP header.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11392-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11392-120">See Also</span></span>  
 <span data-ttu-id="11392-121">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="11392-121">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="11392-122">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="11392-122">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
