---
title: 'ListSSLCertificates-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificates method
ms.assetid: 88cd0936-b202-4ab8-90f2-d9c3f66d37f4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a5ced8371817adc44bbbc89400dc83e0dfccef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616898"
---
# <a name="listsslcertificates-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="cb832-102">ListSSLCertificates-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="cb832-102">ListSSLCertificates Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="cb832-103">Gibt eine Liste der Zertifikate auf dem Berichtsservercomputer zurück</span><span class="sxs-lookup"><span data-stu-id="cb832-103">Returns a list of certificates on the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb832-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb832-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding (ByRef CertificateHash() as String, _  
    ByRef CertName() as String, ByRef HostName() as String, ByRef Length as Int32, _   
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListSSLCertificates(out string[] CertificateHash,   
    out string[] CertName, out string[] Hostname, out Int32 length,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb832-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb832-105">Parameters</span></span>  
 <span data-ttu-id="cb832-106">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="cb832-106">*CertificateHash[]*</span></span>  
 <span data-ttu-id="cb832-107">[out] Der Hash der Zertifikate</span><span class="sxs-lookup"><span data-stu-id="cb832-107">[out] The certificate hashes.</span></span>  
  
 <span data-ttu-id="cb832-108">*CertName[]*</span><span class="sxs-lookup"><span data-stu-id="cb832-108">*CertName[]*</span></span>  
 <span data-ttu-id="cb832-109">[out] Die Namen des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="cb832-109">[out] Names of the certificate.</span></span>  
  
 <span data-ttu-id="cb832-110">*HostName[]*</span><span class="sxs-lookup"><span data-stu-id="cb832-110">*HostName[]*</span></span>  
 <span data-ttu-id="cb832-111">[out] Die Hostnamen der Zertifikate</span><span class="sxs-lookup"><span data-stu-id="cb832-111">[out] The host names for the certificates.</span></span>  
  
 <span data-ttu-id="cb832-112">*Länge*</span><span class="sxs-lookup"><span data-stu-id="cb832-112">*Length*</span></span>  
 <span data-ttu-id="cb832-113">[out] stellt die Länge der Arrays *CertificateHash*, *CertName* und *HostName* dar.</span><span class="sxs-lookup"><span data-stu-id="cb832-113">[out] Represents the length of the *CertificateHash*, *CertName* and *HostName* arrays.</span></span>  
  
 <span data-ttu-id="cb832-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="cb832-114">*HRESULT*</span></span>  
 <span data-ttu-id="cb832-115">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="cb832-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb832-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cb832-116">Return Value</span></span>  
 <span data-ttu-id="cb832-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cb832-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="cb832-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="cb832-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb832-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cb832-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb832-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cb832-120">Requirements</span></span>  
 <span data-ttu-id="cb832-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb832-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb832-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb832-122">See Also</span></span>  
 [<span data-ttu-id="cb832-123">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="cb832-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
