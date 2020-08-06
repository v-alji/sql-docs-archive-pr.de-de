---
title: Rswindowsextendecodschutzscenario-Eigenschaft (WMI-MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ac7ab80-9adf-4f65-abfa-fedf53b082b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84e14d056cc0352b0d1d85bc12c9c873a1b89ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719408"
---
# <a name="rswindowsextendedprotectionscenario-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="45db0-102">RSWindowsExtendedProtectionScenario-Eigenschaft (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="45db0-102">RSWindowsExtendedProtectionScenario Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="45db0-103">Gibt einen Zeichenfolgenwert zurück, der das erweiterte Schutzszenario angibt, für das der Berichtsserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="45db0-103">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45db0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45db0-104">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionScenario As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionScenario;  
```  
  
## <a name="remarks"></a><span data-ttu-id="45db0-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45db0-105">Remarks</span></span>  
 <span data-ttu-id="45db0-106">Gibt einen Zeichenfolgenwert zurück, der das erweiterte Schutzszenario angibt, für das der Berichtsserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="45db0-106">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span> <span data-ttu-id="45db0-107">Wenn der Berichtsserver, mit dem der WMI-Anbieter verbunden wird, keinen erweiterten Schutz unterstützt, wird "" (leere Zeichenfolge) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="45db0-107">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span>  
  
 <span data-ttu-id="45db0-108">In der folgenden Liste werden gültige Werte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="45db0-108">The following list shows valid values:</span></span>  
  
 `"Any | Proxy | Direct"`  
  
## <a name="example-code"></a><span data-ttu-id="45db0-109">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="45db0-109">Example Code</span></span>  
 [<span data-ttu-id="45db0-110">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="45db0-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="45db0-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45db0-111">See Also</span></span>  
 <span data-ttu-id="45db0-112">[RSWindowsExtendedProtectionLevel-Eigenschaft &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="45db0-112">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="45db0-113">[SetExtendedProtectionSettings-Methode (WMI MSReportServer_ConfigurationSetting)](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="45db0-113">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="45db0-114">[Erweiterter Schutz für die Authentifizierung mit Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="45db0-114">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="45db0-115">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="45db0-115">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
