---
title: Webdienstmethoden aufrufen – Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 87f1485b4e3c0ed064e42bb3b411fece96eba8d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697502"
---
# <a name="calling-web-service-methods"></a><span data-ttu-id="70172-102">Aufrufen von Webdienstmethoden</span><span class="sxs-lookup"><span data-stu-id="70172-102">Calling Web Service Methods</span></span>
  <span data-ttu-id="70172-103">Wenn Sie eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Proxy Klasse verwenden, um Webdienst Vorgänge aufzurufen, verwenden Sie die Methoden dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="70172-103">When you use a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class to call Web service operations, you do so by using the methods of that class.</span></span> <span data-ttu-id="70172-104">Diese Methoden verhalten sich wie jede andere Methode einer Klasse in der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="70172-104">These methods respond like any other method of a class in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="70172-105">Alle Webdienstmethoden verfügen über öffentlichen Zugriff, und es ist erforderlich, dass Sie die geeignete Anzahl von Argumenten und Argumenttypen angeben.</span><span class="sxs-lookup"><span data-stu-id="70172-105">All Web service methods have public access and require you to supply the appropriate number of arguments and argument types.</span></span> <span data-ttu-id="70172-106">Nachdem Sie eine Instanz der Proxyklasse im Projekt erstellt haben, können Sie die Methoden zum Ausführen von Berichterstellungsvorgängen über den Berichtsserver aufrufen.</span><span class="sxs-lookup"><span data-stu-id="70172-106">After you have created an instance of the proxy class in your project, you can call the methods to perform reporting operations via the report server.</span></span> <span data-ttu-id="70172-107">Im folgenden C#-Code wird die Verwendung der <xref:ReportService2010.ReportingService2010.ListChildren%2A>-Methode der <xref:ReportService2010.ReportingService2010>-Proxyklasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="70172-107">The following C# code illustrates the use of the <xref:ReportService2010.ReportingService2010.ListChildren%2A> method of the <xref:ReportService2010.ReportingService2010> proxy class.</span></span> <span data-ttu-id="70172-108">Der Code wird dazu verwendet, einen rekursiven Aufruf an den Webdienst auszuführen, der ein Array von <xref:ReportService2010.CatalogItem>-Objekten zurückgibt, das eine Liste aller Elemente in der Berichtsserver-Datenbank enthält:</span><span class="sxs-lookup"><span data-stu-id="70172-108">The code is used to make a recursive call to the Web service that returns an array of <xref:ReportService2010.CatalogItem> objects that contains a list of all items in the report server database:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a><span data-ttu-id="70172-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70172-109">See Also</span></span>  
 <span data-ttu-id="70172-110">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="70172-110">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="70172-111">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="70172-111">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="70172-112">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="70172-112">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
