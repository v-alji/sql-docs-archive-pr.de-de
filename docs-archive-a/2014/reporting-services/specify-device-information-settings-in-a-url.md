---
title: Angeben von Geräteinformationseinstellungen in einer URL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], URLs
- URL access [Reporting Services], device information settings
ms.assetid: cb7f7577-c6a8-4e6f-8e60-5ec0760f29c3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00cd1fdc3b5fbe129ae4d51b220a11bc48b4744c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719444"
---
# <a name="specify-device-information-settings-in-a-url"></a><span data-ttu-id="67841-102">Angeben von Geräteinformationseinstellungen in einer URL</span><span class="sxs-lookup"><span data-stu-id="67841-102">Specify Device Information Settings in a URL</span></span>
  <span data-ttu-id="67841-103">Geräteinformationseinstellungen sind Parameter, die an eine Renderingerweiterung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="67841-103">Device information settings are parameters that are passed to a rendering extension.</span></span> <span data-ttu-id="67841-104">Wenn Sie einen Bericht mit den Methoden des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Berichtsserver-Webdiensts rendern, wird ein `DeviceInfo`-XML-Element als ein Eingabeparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="67841-104">If you use the methods of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service to render a report, a `DeviceInfo` XML element is passed as an input parameter.</span></span> <span data-ttu-id="67841-105">Untergeordnete Elemente des `DeviceInfo`-Elements sind für die Geräteinformationseinstellungen anderer Renderingerweiterungen spezifisch.</span><span class="sxs-lookup"><span data-stu-id="67841-105">Child elements of the `DeviceInfo` element are specific to the device information settings of different rendering extensions.</span></span> <span data-ttu-id="67841-106">Sie können die Geräteinformationseinstellungen in einer URL angeben, indem Sie die *rc:tag=value* -Parameterzeichenfolge verwenden, wobei *tag* der Name des Elements für die Geräteinformationseinstellungen ist.</span><span class="sxs-lookup"><span data-stu-id="67841-106">You can include device information settings in a URL by using the *rc:tag=value* parameter string, where *tag* is the name of the device information settings element being accessed.</span></span> <span data-ttu-id="67841-107">Weitere Informationen zu den Geräteinformationseinstellungen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] finden Sie im Artikel [Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="67841-107">For more information about device information settings in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67841-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67841-108">Example</span></span>  
 <span data-ttu-id="67841-109">Im folgenden Beispiel wird das Format des angegebenen Berichts auf JPEG eingestellt, indem die Geräteinformationseinstellung *OutputFormat* der Bild-Renderingerweiterung verwendet wird (die Zeilenumbrüche wurden aus Gründen der Lesbarkeit eingefügt):</span><span class="sxs-lookup"><span data-stu-id="67841-109">The following example sets the format of the specified report to JPEG by using the *OutputFormat* device information setting of the image rendering extension (the line breaks have been added for legibility):</span></span>  
  
```  
http://servername/reportserver?/SampleReports  
/Employee Sales Summary&EmployeeID=38&rs:  
Command=Render&rs:Format=IMAGE&rc:OutputFormat=JPEG  
```  
  
## <a name="see-also"></a><span data-ttu-id="67841-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67841-110">See Also</span></span>  
 <span data-ttu-id="67841-111">[URL-Zugriff &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="67841-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="67841-112">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="67841-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
