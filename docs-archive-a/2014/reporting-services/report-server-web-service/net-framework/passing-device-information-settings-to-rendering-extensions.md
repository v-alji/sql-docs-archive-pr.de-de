---
title: Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- device information settings [Reporting Services]
- Render method
- Report Server Web service, device information settings
- Web service [Reporting Services], device information settings
- XML Web service [Reporting Services], device information settings
- passing device information [Reporting Services]
- rendering extensions [Reporting Services], device information settings
- rendering [Reporting Services], settings
- device information settings [Reporting Services], about device information settings
- extensions [Reporting Services], device information settings
ms.assetid: fe718939-7efe-4c7f-87cb-5f5b09caeff4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea50de3955ab152cbd92d5fd50ef8b2281a67eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697490"
---
# <a name="passing-device-information-settings-to-rendering-extensions"></a><span data-ttu-id="26577-102">Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="26577-102">Passing Device Information Settings to Rendering Extensions</span></span>
  <span data-ttu-id="26577-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]werden Geräteinformationseinstellungen zum Übergeben von Renderingparametern an eine Renderingerweiterung verwendet.</span><span class="sxs-lookup"><span data-stu-id="26577-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="26577-104">Einstellungen im Berichtsserver-Webdienst werden als **DeviceInfo** -XML-Element übergeben und vom Berichtsserver verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="26577-104">Settings in the Report Server Web service are passed as a **DeviceInfo** XML element and processed by the report server.</span></span> <span data-ttu-id="26577-105">Da Geräteinformationseinstellungen Standardwerte besitzen, werden sie als optionale Argumente für das Rendern angesehen.</span><span class="sxs-lookup"><span data-stu-id="26577-105">Because device information settings have default values, they are considered optional arguments in the rendering process.</span></span> <span data-ttu-id="26577-106">Sie können jedoch Geräteinformationseinstellungen verwenden, um das Rendern anzupassen und die vom Server angegebenen Standardwerte zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="26577-106">However, you can use device information settings to customize rendering and to override the default values that are supplied by the server.</span></span>  
  
 <span data-ttu-id="26577-107">Die Geräteinformationseinstellungen können auf verschiedene Weisen eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="26577-107">You can specify device information settings in a variety of ways.</span></span> <span data-ttu-id="26577-108">Für eine programmgesteuerte Einstellung können Sie die Render-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="26577-108">Programmatically, you can use the Render method.</span></span> <span data-ttu-id="26577-109">Wenn Sie über die URL eines Berichts auf den Bericht zugreifen, können Sie Geräteinformationen als URL-Parameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="26577-109">If you are accessing a report through its URL, you can specify device information as URL parameters.</span></span> <span data-ttu-id="26577-110">Sie können die Geräteinformationseinstellungen auch in der Konfigurationsdatei von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] bearbeiten, um Renderingparameter global festzulegen.</span><span class="sxs-lookup"><span data-stu-id="26577-110">You can also edit the device information settings in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files to specify rendering parameters globally.</span></span> <span data-ttu-id="26577-111">Weitere Informationen zum globalen Angeben von Renderingparametern finden Sie unter [Anpassen der Parameter für Renderingerweiterungen in der Datei „RSReportServer.config“](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="26577-111">For more information about specifying rendering parameters globally, see [Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span></span>  
  
## <a name="passing-device-information-using-the-render-method"></a><span data-ttu-id="26577-112">Übergeben von Geräteinformationen mit der Render-Methode</span><span class="sxs-lookup"><span data-stu-id="26577-112">Passing Device Information Using the Render Method</span></span>  
 <span data-ttu-id="26577-113">Verwenden Sie die <xref:ReportExecution2005.ReportExecutionService.Render%2A>-Methode, um Geräteinformationen an eine Renderingerweiterung zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="26577-113">To pass device information settings to a rendering extension, use the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="26577-114">Beispiel: Die folgende XML-Zeichenfolge kann an die <xref:ReportExecution2005.ReportExecutionService.Render%2A>-Methode übergeben werden, um beim Rendern in HTML ein HTML-Fragment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="26577-114">For example, the following XML string can be passed to the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method to create an HTML fragment when rendering to HTML.</span></span>  
  
```  
<DeviceInfo>  
   <HTMLFragment>True</HTMLFragment>  
</DeviceInfo>  
```  
  
 <span data-ttu-id="26577-115">Wenn ein Bericht als HTML-Fragment gerendert wird, befindet sich der Inhalt des Berichts in einem TABLE-Element, ohne ein HTML- oder ein BODY-Element zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="26577-115">When a report is rendered as an HTML fragment, the content of the report is contained within a TABLE element without the use of an HTML or BODY element.</span></span> <span data-ttu-id="26577-116">Verwenden Sie das HTML-Fragment, um den Bericht in ein bestehendes HTML-Dokument einzubinden.</span><span class="sxs-lookup"><span data-stu-id="26577-116">You can use the HTML fragment to incorporate the report into an existing HTML document.</span></span> <span data-ttu-id="26577-117">Weitere Informationen zu Geräteinformationseinstellungen für die HTML-Ausgabe finden Sie unter [HTML-Geräteinformationseinstellungen](../../html-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="26577-117">For more information about device information settings for HTML output, see [HTML Device Information Settings](../../html-device-information-settings.md).</span></span>  
  
## <a name="passing-device-information-using-url-access"></a><span data-ttu-id="26577-118">Übergeben von Geräteinformationen mit URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="26577-118">Passing Device Information Using URL Access</span></span>  
 <span data-ttu-id="26577-119">Die Geräteinformationen können auch mithilfe eines URL-Zugriffs übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="26577-119">You can also pass device information settings through URL access.</span></span> <span data-ttu-id="26577-120">Dabei werden Geräteinformationseinstellungen als URL-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="26577-120">Device information settings are passed as URL parameters.</span></span> <span data-ttu-id="26577-121">Die folgende URL-Zugriffszeichenfolge kann an den Berichtsserver übergeben werden, um einen gerenderten Bericht ohne die Symbolleiste des HTML-Viewers zu generieren.</span><span class="sxs-lookup"><span data-stu-id="26577-121">The following URL access string can be passed to the report server to generate a rendered report without the HTML viewer toolbar.</span></span>  
  
```  
http://<Server Name>/reportserver?/SampleReports/Sales Order Detail&rs:Command=Render&rs:Format=HTML4.0&rc:Toolbar=False  
```  
  
 <span data-ttu-id="26577-122">Weitere Informationen finden Sie unter [Angeben von Geräteinformationseinstellungen in einer URL](../../specify-device-information-settings-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="26577-122">For more information, see [Specify Device Information Settings in a URL](../../specify-device-information-settings-in-a-url.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26577-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26577-123">See Also</span></span>  
 <span data-ttu-id="26577-124">[Geräte Informationseinstellungen für Renderingerweiterungen &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="26577-124">[Device Information Settings for Rendering Extensions &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span></span>  
 <span data-ttu-id="26577-125">[Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="26577-125">[Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="26577-126">Erstellen von Anwendungen mit dem Webdienst und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="26577-126">Building Applications Using the Web Service and the .NET Framework</span></span>](building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
