---
title: 'ListIPAddresses-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListIPAddresses method
ms.assetid: 7e7cf182-fba0-4604-a474-098461e23e9d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 845f7ba7db02a0b860f966184463580733af0faf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616910"
---
# <a name="listipaddresses-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="95261-102">ListIPAddresses-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="95261-102">ListIPAddresses Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="95261-103">Listet die IP-Adressen für den Berichtsservercomputer auf.</span><span class="sxs-lookup"><span data-stu-id="95261-103">Lists the IP addresses for the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95261-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95261-104">Syntax</span></span>  
  
```vb  
Public Sub ListIPAddresses (ByRef IPAddress() as String, _  
    ByRef IPVersion()as String, ByRef IsDhcpEnabled () as Boolean, _   
    ByRef Length as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListIPAddresses (out string[] IPAddress,   
    out string[] IPVersion, out bool[] isDhcpEnabled, out int length,   
    out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95261-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95261-105">Parameters</span></span>  
 <span data-ttu-id="95261-106">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="95261-106">*IPAddress[]*</span></span>  
 <span data-ttu-id="95261-107">[out] Die Liste der IP-Adressen für den Computer</span><span class="sxs-lookup"><span data-stu-id="95261-107">[out] The list of IP address for the computer.</span></span>  
  
 <span data-ttu-id="95261-108">*IPVersion[]*</span><span class="sxs-lookup"><span data-stu-id="95261-108">*IPVersion[]*</span></span>  
 <span data-ttu-id="95261-109">[out] Die Version für die IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="95261-109">[out] The version for the IP addresses.</span></span>  
  
 <span data-ttu-id="95261-110">*IsDhcpEnabled[]*</span><span class="sxs-lookup"><span data-stu-id="95261-110">*IsDhcpEnabled[]*</span></span>  
 <span data-ttu-id="95261-111">[out] Gibt an, ob die IP-Adressen DHCP-aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="95261-111">[out] Indicates whether the IP addresses are DHCP enabled.</span></span>  
  
 <span data-ttu-id="95261-112">*Länge*</span><span class="sxs-lookup"><span data-stu-id="95261-112">*Length*</span></span>  
 <span data-ttu-id="95261-113">[out] Die Länge des von der Methode zurückgegebenen Arrays</span><span class="sxs-lookup"><span data-stu-id="95261-113">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="95261-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="95261-114">*HRESULT*</span></span>  
 <span data-ttu-id="95261-115">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="95261-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95261-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95261-116">Return Value</span></span>  
 <span data-ttu-id="95261-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="95261-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="95261-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="95261-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95261-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="95261-119">Remarks</span></span>  
 <span data-ttu-id="95261-120">*IPVersion* -Zeichenfolgen sind V4 und V6.</span><span class="sxs-lookup"><span data-stu-id="95261-120">*IPVersion* strings are V4, V6.</span></span>  
  
 <span data-ttu-id="95261-121">Wenn *isdhcpabled* ist `True` , ist die *IPAddress* dynamisch.</span><span class="sxs-lookup"><span data-stu-id="95261-121">If *IsDhcpEnabled* is `True`, the *IPAddress* is dynamic.</span></span> <span data-ttu-id="95261-122">Eine Verwendung für SSL-Bindungen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="95261-122">It should not be used for SSL bindings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95261-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95261-123">Requirements</span></span>  
 <span data-ttu-id="95261-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95261-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95261-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95261-125">See Also</span></span>  
 [<span data-ttu-id="95261-126">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="95261-126">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
