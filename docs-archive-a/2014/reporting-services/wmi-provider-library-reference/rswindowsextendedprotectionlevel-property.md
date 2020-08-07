---
title: Rswindowsextendecodschutzlevel-Eigenschaft (WMI-MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02ff3bad42ae25adf6cfa563944d89bac2c600e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616893"
---
# <a name="rswindowsextendedprotectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d21e5-102">RSWindowsExtendedProtectionLevel-Eigenschaft (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d21e5-102">RSWindowsExtendedProtectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d21e5-103">Gibt einen Zeichenfolgenwert zurück, der die Schutzebene angibt, für deren Unterstützung der Berichtsserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d21e5-103">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="d21e5-104">Diese Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="d21e5-104">This property is read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d21e5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d21e5-105">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d21e5-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d21e5-106">Remarks</span></span>  
 <span data-ttu-id="d21e5-107">Gibt einen Zeichenfolgenwert zurück, der die Schutzebene angibt, für deren Unterstützung der Berichtsserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d21e5-107">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="d21e5-108">Wenn der Berichtsserver, mit dem der WMI-Anbieter verbunden wird, keinen erweiterten Schutz unterstützt, wird "" (leere Zeichenfolge) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d21e5-108">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span> <span data-ttu-id="d21e5-109">In der folgenden Liste werden gültige Werte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="d21e5-109">The following list shows valid values:</span></span>  
  
 `"Off" | "Allow" | "Require"`  
  
## <a name="example-code"></a><span data-ttu-id="d21e5-110">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="d21e5-110">Example Code</span></span>  
 [<span data-ttu-id="d21e5-111">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="d21e5-111">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="d21e5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d21e5-112">See Also</span></span>  
 <span data-ttu-id="d21e5-113">[RSWindowsExtendedProtectionScenario-Eigenschaft &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="d21e5-113">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="d21e5-114">[SetExtendedProtectionSettings-Methode (WMI MSReportServer_ConfigurationSetting)](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="d21e5-114">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="d21e5-115">[Erweiterter Schutz für die Authentifizierung mit Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="d21e5-115">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="d21e5-116">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="d21e5-116">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
