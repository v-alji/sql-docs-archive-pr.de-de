---
title: Bereitstellen von Argumenten für Webdienstmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, methods
- Web service [Reporting Services], methods
- methods [Reporting Services], arguments
- XML Web service [Reporting Services], methods
ms.assetid: f7b9ca05-fc4c-4b30-8e5d-172dd0f4a832
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ef5188934628589751fe92d1839da0efb265766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723370"
---
# <a name="supplying-web-service-method-arguments"></a><span data-ttu-id="45f76-102">Bereitstellen von Argumenten für Webdienstmethoden</span><span class="sxs-lookup"><span data-stu-id="45f76-102">Supplying Web Service Method Arguments</span></span>
  <span data-ttu-id="45f76-103">Eine Report Server-Webdienstmethode sendet eine Anforderung an den Dienst unter einer bestimmten URL, wobei SOAP über HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="45f76-103">A Report Server Web service method sends a request to the service at a given URL using SOAP over HTTP.</span></span> <span data-ttu-id="45f76-104">Der Dienst empfängt die Anforderung, verarbeitet sie und gibt dann eine Antwort zurück.</span><span class="sxs-lookup"><span data-stu-id="45f76-104">The service receives the request, processes it, and then returns a response.</span></span> <span data-ttu-id="45f76-105">Diese Anforderungen und Antworten haben die Form von XML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="45f76-105">These requests and responses are in the form of XML documents.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="45f76-106">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="45f76-106">Optional Parameters</span></span>  
 <span data-ttu-id="45f76-107">In manchen Fällen kann eine Webdienstmethode optionale Eingabeparameter haben.</span><span class="sxs-lookup"><span data-stu-id="45f76-107">In some cases, a Web service method can have optional input parameters.</span></span> <span data-ttu-id="45f76-108">Selbst wenn ein Eingabeparameter für eine Webdienstmethode optional ist, müssen Sie ihn trotzdem aufnehmen und den Parameterwert auf `null` festlegen (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="45f76-108">Even if an input parameter for a Web service method is optional, you must still include it and set the parameter value to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="45f76-109">Wenn Sie einen Parameterwert auf `null` festlegen, wird der Elementwert für diesen Parameter in der SOAP-Anforderung auf `null` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="45f76-109">Setting a parameter value to `null` sets the element value for that parameter in the SOAP request to `null`.</span></span>  
  
 <span data-ttu-id="45f76-110">Im folgenden Beispiel wird die <xref:ReportService2010.ReportingService2010.CreateFolder%2A>-Methode zum Erstellen eines neuen Ordners mit dem Namen Product Sales im Ordner Sales verwendet.</span><span class="sxs-lookup"><span data-stu-id="45f76-110">The following example uses the <xref:ReportService2010.ReportingService2010.CreateFolder%2A> method to create a new folder named Product Sales in the Sales folder.</span></span> <span data-ttu-id="45f76-111">Wenn der Wert `null` für die Ordnereigenschaften verwendet wird, werden für den Ordner keine benutzerspezifischen Eigenschaften angegeben:</span><span class="sxs-lookup"><span data-stu-id="45f76-111">By supplying a `null` value for the folder properties, no user-specific properties are supplied for the folder:</span></span>  
  
```  
// C#  
rs.CreateFolder("Product Sales", "/Sales", null);  
```  
  
## <a name="complex-data-types"></a><span data-ttu-id="45f76-112">Komplexe Datentypen</span><span class="sxs-lookup"><span data-stu-id="45f76-112">Complex Data Types</span></span>  
 <span data-ttu-id="45f76-113">Die Kernklasse des Report Server-Webdiensts ist <xref:ReportService2010.ReportingService2010>. Sie wird verwendet, um die SOAP-Vorgänge oder Webmethoden der Proxyklasse aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="45f76-113">The core class of the Report Server Web service is <xref:ReportService2010.ReportingService2010>, which you use to invoke the SOAP operations or Web methods of the proxy class.</span></span> <span data-ttu-id="45f76-114">Damit diese Klasse und ihre Methoden unterstützt werden, enthält [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] benutzerdefinierte, komplexe Datentypen, die für die Eingabe- und Ausgabeparameter der Webdienstmethoden spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="45f76-114">To support this class and its methods, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes user-defined, complex data types that are specific to the input and output parameters of the Web service methods.</span></span> <span data-ttu-id="45f76-115">Diese komplexen Datentypen sind Teil der generierten Proxy Klasse, die Sie bei der Entwicklung in der Umgebung verwenden können [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45f76-115">These complex data types are part of the generated proxy class, which you can use when developing in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environment.</span></span>  
  
 <span data-ttu-id="45f76-116">Wenn Sie eine Proxyklasse erzeugen, werden die in der WSDL-Datei definierten komplexen Datentypen durch die Klassen des Proxys dargestellt, die Eigenschaften enthalten, welche den verschiedenen SOAP-Elementen der komplexen Datentypen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="45f76-116">When you generate a proxy class, the complex data types that are defined in the WSDL file are represented by the classes of the proxy, which include properties that correspond to the various SOAP elements of the complex data types.</span></span> <span data-ttu-id="45f76-117">Sequenzen dieser Datentypen werden zu Objektarrays, die Sie im Code durchlaufen können.</span><span class="sxs-lookup"><span data-stu-id="45f76-117">Sequences of these data types become arrays of objects that you can enumerate through in your code.</span></span> <span data-ttu-id="45f76-118">Dadurch ist es nicht notwendig, direkt mit den in SOAP-Nachrichten gesendeten XML-Strukturen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="45f76-118">This eliminates the need to work directly with the XML structures sent in SOAP messages.</span></span> <span data-ttu-id="45f76-119">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] behandelt diese Übersetzung für Sie.</span><span class="sxs-lookup"><span data-stu-id="45f76-119">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] handles that translation for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f76-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45f76-120">See Also</span></span>  
 <span data-ttu-id="45f76-121">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="45f76-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="45f76-122">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="45f76-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="45f76-123">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="45f76-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
