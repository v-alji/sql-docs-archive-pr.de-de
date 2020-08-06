---
title: Integrieren von Reporting Services mit URL-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- URL access [Reporting Services], about URL access
- integrating reports [Reporting Services]
ms.assetid: f1014f7d-fafa-4aa8-8bd2-5bdba835d9b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fedf4ce3011d9caae9d673acf354265537115057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719723"
---
# <a name="integrating-reporting-services-using-url-access"></a><span data-ttu-id="aa14f-102">Integrieren von Reporting Services mit URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="aa14f-102">Integrating Reporting Services Using URL Access</span></span>
  <span data-ttu-id="aa14f-103">Mit URL-Zugriff können Sie über eine Berichtsserver-URL auf Berichte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aa14f-103">With URL access, you access reports through a report server URL.</span></span> <span data-ttu-id="aa14f-104">Eine URL-Anforderung ermöglicht Ihnen, auf einen spezifischen Berichtsserver und die Berichte, Ressourcen und anderen Elemente in der Berichtsserver-Datenbank zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="aa14f-104">A URL request enables you to access a specific report server as well as the reports, resources, and other items in the report server database.</span></span> <span data-ttu-id="aa14f-105">Sie können auch die Art und Weise anpassen, wie Benutzer Berichte anzeigen und in ihnen navigieren können.</span><span class="sxs-lookup"><span data-stu-id="aa14f-105">You can also customize the report viewing and navigation experience for your users.</span></span> <span data-ttu-id="aa14f-106">Die Abfragezeichenfolge der URL enthält Geräteinformationseinstellungen sowie Berichtsparameter, die den Bericht und die gewählte Renderingausgabe als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="aa14f-106">The query string of the URL contains device information settings, as well as report parameters targeted at your report and the chosen rendering output.</span></span> <span data-ttu-id="aa14f-107">Wie URL-Anforderungen vom Berichtsserver behandelt werden, hängt von den Parametern, den Parameterpräfixen sowie dem Elementtyp ab, auf den Sie über die URL zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aa14f-107">The way the report server handles URL requests depends on the parameters, parameter prefixes, and type of item that you are accessing through the URL.</span></span>  
  
 <span data-ttu-id="aa14f-108">Unabhängig davon, ob Sie in einer Windows- oder einer Webumgebung arbeiten, können Sie den URL-Zugriff verwenden, um Links in Berichte und andere Berichtsserverelemente in die von Ihnen entwickelten Anwendungen einzubetten.</span><span class="sxs-lookup"><span data-stu-id="aa14f-108">You can use URL access to embed hyperlinks to reports and other report server items in the applications that you develop, whether in a Windows or Web environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa14f-109">Die Themen in diesem Abschnitt enthalten grundlegende Informationen zur Integration.</span><span class="sxs-lookup"><span data-stu-id="aa14f-109">The topics in the section provide you with some basic ideas for integration.</span></span> <span data-ttu-id="aa14f-110">Diese Informationen sind hilfreich, wenn Sie beginnen, eigene [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Integrationsszenarien zu entwerfen und zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="aa14f-110">You can use the information to begin to design and develop your own [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integration scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa14f-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aa14f-111">In This Section</span></span>  
 [<span data-ttu-id="aa14f-112">Verwenden des URL-Zugriffs in einer Webanwendung</span><span class="sxs-lookup"><span data-stu-id="aa14f-112">Using URL Access in a Web Application</span></span>](integrating-reporting-services-using-url-access-web-application.md)  
 <span data-ttu-id="aa14f-113">Beschreibt, wie Sie den URL-Zugriff verwenden, um [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in eine Webumgebung zu integrieren</span><span class="sxs-lookup"><span data-stu-id="aa14f-113">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
 [<span data-ttu-id="aa14f-114">Verwenden des URL-Zugriffs in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="aa14f-114">Using URL Access in a Windows Application</span></span>](integrating-reporting-services-using-url-access-windows-application.md)  
 <span data-ttu-id="aa14f-115">Beschreibt, wie Sie den URL-Zugriff verwenden, um [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32-Umgebung zu integrieren</span><span class="sxs-lookup"><span data-stu-id="aa14f-115">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa14f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa14f-116">See Also</span></span>  
 <span data-ttu-id="aa14f-117">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="aa14f-117">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="aa14f-118">URL-Zugriff &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa14f-118">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
