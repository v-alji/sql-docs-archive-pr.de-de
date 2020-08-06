---
title: Die Rolle von SOAP in Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- SOAP [Reporting Services], role in Reporting Services
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: f229c3ef-f2ca-448f-98f1-b8df350b9992
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05445eb1c95c5761595944867b6d0c20a6f1a412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700814"
---
# <a name="the-role-of-soap-in-reporting-services"></a><span data-ttu-id="a0a18-102">Die Rolle von SOAP in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a0a18-102">The Role of SOAP in Reporting Services</span></span>
  <span data-ttu-id="a0a18-103">Der Berichtsserver-Webdienst verwendet SOAP-Messaging (Simple Object Access Protocol), um textbasierte Befehle über ein Netzwerk zu senden.</span><span class="sxs-lookup"><span data-stu-id="a0a18-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) messaging to send text-based commands over a network.</span></span> <span data-ttu-id="a0a18-104">Bei diesen Befehlen handelt es sich um XML-Text, der mit HTTP über das World Wide Web gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0a18-104">These commands take the form of XML text that is sent over the World Wide Web using HTTP.</span></span> <span data-ttu-id="a0a18-105">Wenn SOAP als Kommunikationsprotokoll verwendet wird, erlaubt der Report Server-Webdienst Anwendungen und Komponenten den Datenaustausch mit dem Berichtsserver über eine offene und weit verbreitete Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="a0a18-105">By using SOAP as its communication protocol, the Report Server Web service allows applications and components to exchange data with the report server using an open and widely accepted infrastructure.</span></span> <span data-ttu-id="a0a18-106">Der SOAP-Standard wird unter www.w3.org/TR/SOAP definiert.</span><span class="sxs-lookup"><span data-stu-id="a0a18-106">The SOAP standard is defined at www.w3.org/TR/SOAP.</span></span>  
  
 <span data-ttu-id="a0a18-107">Jede Clientanwendung kann als SOAP-Client dienen, wenn sie SOAP erkennt und SOAP-Anforderungen senden kann.</span><span class="sxs-lookup"><span data-stu-id="a0a18-107">Any client application can act as a SOAP client as long as it is SOAP-aware and can send SOAP requests.</span></span> <span data-ttu-id="a0a18-108">Der Berichts-Manager ist ein solcher SOAP-Client.</span><span class="sxs-lookup"><span data-stu-id="a0a18-108">Report Manager is one such SOAP client.</span></span> <span data-ttu-id="a0a18-109">Er bietet eine Schnittstelle zur Berichtsserver-Datenbank, in der alle Berichte und alle mit dem Bericht verbundenen Inhalte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a0a18-109">It provides an interface to the report server database in which all reports and report-related content is stored.</span></span> <span data-ttu-id="a0a18-110">Endbenutzer können mit der Anwendung Berichte und Ordner im Berichtsserver-Namespace durchsuchen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="a0a18-110">End users can use the application to browse through and manage reports and folders in the report server namespace.</span></span> <span data-ttu-id="a0a18-111">Der Berichts-Manager basiert auf der Infrastruktur des Report Server-Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="a0a18-111">Report Manager is built on the Report Server Web service infrastructure.</span></span>  
  
 <span data-ttu-id="a0a18-112">Ein Berichtsserver fungiert als ein SOAP-Server, ein Dienst, der SOAP erkennt und Anforderungen von SOAP-Clients akzeptieren sowie entsprechende Antworten zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="a0a18-112">A report server acts as a SOAP server, a SOAP-aware service that can accept requests from SOAP clients and create appropriate responses.</span></span> <span data-ttu-id="a0a18-113">Der Server behandelt die Anforderungen und sendet codierte Antworten an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="a0a18-113">The server handles the requests and sends encoded responses back to the client.</span></span>  
  
 <span data-ttu-id="a0a18-114">SOAP-Nachrichten in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] können verschiedene Formate haben. Dies hängt von der Art der Anforderung ab, die vom Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0a18-114">SOAP messages in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] take many different forms, depending on the type of request made by the client.</span></span> <span data-ttu-id="a0a18-115">Das folgende Beispiel zeigt eine einfache Anforderung vom SOAP-Client, ein Element aus der Berichtsserver-Datenbank zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a0a18-115">The following example represents a simple SOAP client request to remove an item from the report server database.</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItem xmlns="https://www.microsoft.com/sql/ReportingServer">  
            <item>/Samples/Report1</item>  
        </DeleteItem>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="a0a18-116">SOAP selbst erfordert, dass Nachrichten in ein `Envelope`-Element gestellt werden, wobei sich der Großteil der Nachricht in einem `Body`-Element befindet.</span><span class="sxs-lookup"><span data-stu-id="a0a18-116">The SOAP itself requires that messages be put into an `Envelope` element, with the bulk of the message inside a `Body` element.</span></span> <span data-ttu-id="a0a18-117">In diesem Beispiel enthält der Nachrichtentext einen Aufruf an die <xref:ReportService2010.ReportingService2010.DeleteItem%2A>-Methode, die einen Zeichenfolgenparameter akzeptiert, welcher den Pfad des zu löschenden Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0a18-117">In this example, the body contains a call to the <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method, which takes a string parameter representing the path of the item to delete.</span></span> <span data-ttu-id="a0a18-118">Sie können eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Client Proxy Klasse erstellen, die alle SOAP-Vorgänge in Methoden kapselt.</span><span class="sxs-lookup"><span data-stu-id="a0a18-118">You can create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] client proxy class that encapsulates all SOAP operations into methods.</span></span> <span data-ttu-id="a0a18-119">Die folgende [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] Methode stellt das zuvor angegebene SOAP-Beispiel dar.</span><span class="sxs-lookup"><span data-stu-id="a0a18-119">The following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] method represents the SOAP example given earlier.</span></span>  
  
```  
public void DeleteItem(string item);  
```  
  
 <span data-ttu-id="a0a18-120">Die Antwort vom Server könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="a0a18-120">The response from the server might look like the following:</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItemResponse xmlns="https://www.microsoft.com/sql/ReportingServer" />  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="a0a18-121">Da die <xref:ReportService2010.ReportingService2010.DeleteItem%2A>-Methode über keinen Rückgabewert verfügt, wird eine leere Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0a18-121">The <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method has no return value, so an empty response is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a18-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0a18-122">See Also</span></span>  
 <span data-ttu-id="a0a18-123">[Zugreifen auf die SOAP-API](accessing-the-soap-api.md) </span><span class="sxs-lookup"><span data-stu-id="a0a18-123">[Accessing the SOAP API](accessing-the-soap-api.md) </span></span>  
 <span data-ttu-id="a0a18-124">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a0a18-124">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="a0a18-125">[Reporting Services Berichts Server](../reporting-services-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0a18-125">[Reporting Services Report Server](../reporting-services-report-server.md) </span></span>  
 [<span data-ttu-id="a0a18-126">Report Server Web Service (Report Server-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="a0a18-126">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
