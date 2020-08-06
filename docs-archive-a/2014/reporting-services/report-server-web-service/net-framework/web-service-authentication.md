---
title: Webdienstauthentifizierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0c7836d6eba8c6ab3f0a8e705ebb79c7ed73eb17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723365"
---
# <a name="web-service-authentication"></a><span data-ttu-id="81b84-102">Webdienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="81b84-102">Web Service Authentication</span></span>
  <span data-ttu-id="81b84-103">Sie können entweder die Windows-Authentifizierung oder die Standardauthentifizierung verwenden, um an den Berichtsserver-Webdienst gerichtete Aufrufe zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="81b84-103">You can use either Windows Authentication or Basic authentication to authenticate the calls made to the Report Server Web service.</span></span> <span data-ttu-id="81b84-104">Jeder Client, der SOAP-Anforderungen an den Berichtsserver richtet, muss den Clientteil eines der unterstützten Authentifizierungsprotokolle implementieren.</span><span class="sxs-lookup"><span data-stu-id="81b84-104">Any client that makes SOAP requests to the report server must implement the client portion of one of the supported authentication protocols.</span></span> <span data-ttu-id="81b84-105">Wenn Sie verwenden [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , können Sie die HTTP-Klassen für verwalteten Code verwenden, um die Authentifizierung zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="81b84-105">If you are using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], you can use the managed code HTTP classes to implement authentication.</span></span> <span data-ttu-id="81b84-106">Mithilfe von APIs können Sie die Authentifizierungsdaten problemlos zusammen mit den SOAP-Anforderungen senden.</span><span class="sxs-lookup"><span data-stu-id="81b84-106">Using these APIs makes it easy to send authentication information along with the SOAP requests.</span></span>  
  
 <span data-ttu-id="81b84-107">Wenn Sie die entsprechenden Anmeldeinformationen nicht haben, bevor Sie einen Aufruf an den Berichtsserver-Webdienst richten, schlägt der Aufruf fehl.</span><span class="sxs-lookup"><span data-stu-id="81b84-107">If you do not have appropriate credentials before you make a call to the Report Server Web service, the call fails.</span></span> <span data-ttu-id="81b84-108">Sie können die Anmeldeinformationen zur Laufzeit an den Webdienst übergeben, indem Sie die **Credentials**-Eigenschaft des clientseitigen Objekts festlegen, das den XML-Webdienst darstellt, bevor Sie seine Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="81b84-108">At run time, you can pass credentials to the Web service by setting the **Credentials** property of the client-side object that represents the Web service before you call its methods.</span></span>  
  
 <span data-ttu-id="81b84-109">Die folgenden Abschnitte enthalten Beispielcode, der die Anmeldeinformationen mithilfe von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] sendet.</span><span class="sxs-lookup"><span data-stu-id="81b84-109">The following sections contain example code that sends credentials using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="81b84-110">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="81b84-110">Windows Authentication</span></span>  
 <span data-ttu-id="81b84-111">Folgender Code übergibt die Windows-Anmeldeinformationen an den Webdienst.</span><span class="sxs-lookup"><span data-stu-id="81b84-111">The following code passes Windows credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a><span data-ttu-id="81b84-112">Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="81b84-112">Basic Authentication</span></span>  
 <span data-ttu-id="81b84-113">Folgender Code übergibt die Standardanmeldeinformationen an den Webdienst.</span><span class="sxs-lookup"><span data-stu-id="81b84-113">The following code passes Basic credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 <span data-ttu-id="81b84-114">Die Anmeldeinformationen müssen jedoch festgelegt sein, bevor Sie eine der Methoden des Berichtsserver-Webdiensts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="81b84-114">The credentials must be set before you call any of the methods of the Report Server Web service.</span></span> <span data-ttu-id="81b84-115">Wenn Sie die Anmeldeinformationen nicht festlegen, erhalten Sie den Fehlercode „Fehler HTTP 401 (Zugriff verweigert)“.</span><span class="sxs-lookup"><span data-stu-id="81b84-115">If you do not set the credentials, you receive the error code an HTTP 401 Error: Access Denied.</span></span> <span data-ttu-id="81b84-116">Sie müssen den Dienst vor der Verwendung authentifizieren, aber wenn Sie die Anmeldeinformationen festgelegt haben, müssen Sie diese nicht nochmals festlegen, solange Sie weiterhin dieselbe Dienstvariable verwenden (z. B. *rs*).</span><span class="sxs-lookup"><span data-stu-id="81b84-116">You must authenticate the service before you use it, but after you have set the credentials, you do not need to set them again as long as you continue to use the same service variable (such as *rs*).</span></span>  
  
## <a name="custom-authentication"></a><span data-ttu-id="81b84-117">Benutzerdefinierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="81b84-117">Custom Authentication</span></span>  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="81b84-118">enthält eine Programmierungs-API, mit denen Entwickler benutzerdefinierte Authentifizierungserweiterungen, so genannte Sicherheitserweiterungen, entwerfen und entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="81b84-118">includes a programming API that provides developers with the opportunity to design and develop custom authentication extensions, known as security extensions.</span></span> <span data-ttu-id="81b84-119">Weitere Informationen finden Sie unter [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="81b84-119">For more information, see [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b84-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81b84-120">See Also</span></span>  
 <span data-ttu-id="81b84-121">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="81b84-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="81b84-122">Report Server Web Service (Report Server-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="81b84-122">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
