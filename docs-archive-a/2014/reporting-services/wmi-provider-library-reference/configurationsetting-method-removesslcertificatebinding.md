---
title: 'RemoveSSLCertificateBindings-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveSSLCertificateBindings method
ms.assetid: b8b484c9-04c4-4ae9-980e-67bbe5aa8481
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d42d17d9c92f2e100a7800e607536ff6c7eab891
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720938"
---
# <a name="removesslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="cd446-102">RemoveSSLCertificateBindings-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="cd446-102">RemoveSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="cd446-103">Entfernt eine SSL-Zertifikatsbindung</span><span class="sxs-lookup"><span data-stu-id="cd446-103">Removes an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd446-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd446-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveSSLCertificateBindings(string Application,  
    string CertificateHash, string IPAddress, Int32 Port, Int32 Lcid,  
    out string Error, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd446-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd446-105">Parameters</span></span>  
 <span data-ttu-id="cd446-106">*Anwendung*</span><span class="sxs-lookup"><span data-stu-id="cd446-106">*Application*</span></span>  
 <span data-ttu-id="cd446-107">Der Name der Anwendung, für den die Zertifikatsbindung entfernt werden soll</span><span class="sxs-lookup"><span data-stu-id="cd446-107">The name of application for which the certificate binding should be removed.</span></span>  
  
 <span data-ttu-id="cd446-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="cd446-108">*CertificateHash*</span></span>  
 <span data-ttu-id="cd446-109">Der Hash für das Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cd446-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="cd446-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="cd446-110">*IPAddress*</span></span>  
 <span data-ttu-id="cd446-111">Die IP-Adresse für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="cd446-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="cd446-112">*Port*</span><span class="sxs-lookup"><span data-stu-id="cd446-112">*Port*</span></span>  
 <span data-ttu-id="cd446-113">Der SSL-Port, der der Bindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cd446-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="cd446-114">*lcid*</span><span class="sxs-lookup"><span data-stu-id="cd446-114">*lcid*</span></span>  
 <span data-ttu-id="cd446-115">Das Gebietsschema, das für die zurückgegebenen Fehlermeldungen verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="cd446-115">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="cd446-116">*Fehler*</span><span class="sxs-lookup"><span data-stu-id="cd446-116">*Error*</span></span>  
 <span data-ttu-id="cd446-117">[out] Die Beschreibung des Fehlers, der aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="cd446-117">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="cd446-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="cd446-118">*HRESULT*</span></span>  
 <span data-ttu-id="cd446-119">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="cd446-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd446-120">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd446-120">Return Value</span></span>  
 <span data-ttu-id="cd446-121">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd446-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="cd446-122">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="cd446-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd446-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cd446-123">Remarks</span></span>  
 <span data-ttu-id="cd446-124">Diese Methode entfernt die spezifische Bindung aus der Datei rsreportserver.config und optional aus HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="cd446-124">This method removes the specific binding from the rsreportserver.config file and optionally HTTP.SYS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd446-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cd446-125">Requirements</span></span>  
 <span data-ttu-id="cd446-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd446-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd446-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd446-127">See Also</span></span>  
 [<span data-ttu-id="cd446-128">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="cd446-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
