---
title: 'SetExtendedProtectionSettings-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d8e7232-42f4-41b6-98eb-c856f6c85d8c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ee937747b74bcf8d53012721b4be5bfca04185df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722381"
---
# <a name="setextendedprotectionsettings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c5b92-102">SetExtendedProtectionSettings-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c5b92-102">SetExtendedProtectionSettings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c5b92-103">Die SetExtendedProtectionSettings-Methode wird verwendet, um die RSWindowsExtendedProtectionLevel- und RSWindowsExtendedProtectionScenario-Eigenschaft in der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationsdatei "RSReportServer.config" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c5b92-103">The SetExtendedProtectionSettings method is used to set the RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration file RSReportServer.config.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5b92-104">Syntax</span></span>  
  
```vb  
Public Sub SetExtendedProtectionSettings( _  
        ByVal ExtendedProtectionLevel As String, _  
        ByVal ExtendedProtectionScenario As String, _  
        ByRef Warnings() As String, _  
        ByRef Length As Int32, _  
        ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetExtendedProtectionSettings(  
            string ExtendedProtectionLevel,  
            string ExtendedProtectionScenario,  
            out string[] Warnings,  
            out Int32 Length,  
            out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5b92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5b92-105">Parameters</span></span>  
 <span data-ttu-id="c5b92-106">*ExtendedProtectionLevel*</span><span class="sxs-lookup"><span data-stu-id="c5b92-106">*ExtendedProtectionLevel*</span></span>  
 <span data-ttu-id="c5b92-107">Legt "RSWindowsExtendedProtectionLevel" in der Datei "RSRreportserver.config" fest.</span><span class="sxs-lookup"><span data-stu-id="c5b92-107">Sets the RSWindowsExtendedProtectionLevel in the RSRreportserver.config file.</span></span> <span data-ttu-id="c5b92-108">Beim erforderlichen Wert wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="c5b92-108">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="c5b92-109">In der folgenden Liste werden gültige Werte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c5b92-109">The following list shows valid values:</span></span>  
  
 `"Off | Allow | Require"`  
  
 <span data-ttu-id="c5b92-110">*ExtendedProtectionScenario*</span><span class="sxs-lookup"><span data-stu-id="c5b92-110">*ExtendedProtectionScenario*</span></span>  
 <span data-ttu-id="c5b92-111">Legt "RSWindowsExtendedProtectionScenario" in der Datei "RSReportserver.config" fest.</span><span class="sxs-lookup"><span data-stu-id="c5b92-111">Sets the RSWindowsExtendedProtectionScenario in the RSReportserver.config file.</span></span> <span data-ttu-id="c5b92-112">Beim erforderlichen Wert wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="c5b92-112">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="c5b92-113">In der folgenden Liste werden gültige Werte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c5b92-113">The following list shows valid values:</span></span>  
  
 `"Any" | "Proxy" | "Direct"`  
  
## <a name="remarks"></a><span data-ttu-id="c5b92-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c5b92-114">Remarks</span></span>  
 <span data-ttu-id="c5b92-115">Die RSWindowsExtendedProtectionLevel-Eigenschaft und die RSWindowsExtendedProtectionScenario-Eigenschaft sind gültig, wenn AuthenticationTypes in der Datei RSReportServer.config RSWindowNTLM, RSWindowsNegotiate oder RSWindowsKerberos einschließt.</span><span class="sxs-lookup"><span data-stu-id="c5b92-115">The RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties apply when the AuthenticationTypes in the RSReportServer.config file include RSWindowNTLM, RSWindowsNegotiate, or RSWindowsKerberos.</span></span> <span data-ttu-id="c5b92-116">Das Festlegen dieser Eigenschaften wirkt sich darauf aus, wie sich Benutzer und Clientsoftware an einem Berichtsserver authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="c5b92-116">Setting these properties affects how users and client software authenticate with a report server.</span></span> <span data-ttu-id="c5b92-117">Es wird empfohlen, dass Sie die Dokumentation für erweiterten Schutz vor dem Festlegen von ExtendedProtectionLevel auf `Allow` oder `Require` lesen.</span><span class="sxs-lookup"><span data-stu-id="c5b92-117">It is recommended that you read the documentation for extended protection before setting ExtendedProtectionLevel to either `Allow` or `Require`.</span></span>  
  
 <span data-ttu-id="c5b92-118">Zum Festlegen von ExtendedProtectionLevel muss der Benutzer Mitglied der Gruppe "BUILTIN\Administrators" auf dem Berichtsserver sein.</span><span class="sxs-lookup"><span data-stu-id="c5b92-118">To set the ExtendedProtectionLevel, the user must be a member of the BUILTIN\Administrators group on the report server.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b92-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c5b92-119">Requirements</span></span>  
 <span data-ttu-id="c5b92-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b92-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b92-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5b92-121">See Also</span></span>  
 <span data-ttu-id="c5b92-122">[RSWindowsExtendedProtectionScenario-Eigenschaft &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="c5b92-122">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="c5b92-123">[RSWindowsExtendedProtectionLevel-Eigenschaft &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="c5b92-123">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="c5b92-124">[Erweiterter Schutz für die Authentifizierung mit Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="c5b92-124">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="c5b92-125">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="c5b92-125">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
