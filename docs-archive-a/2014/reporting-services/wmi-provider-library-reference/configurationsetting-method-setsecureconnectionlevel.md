---
title: 'SetSecureConnectionLevel-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4361f09eb38b3e5650b68ae6f86b7f2266bbf1a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722374"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f609b-102">SetSecureConnectionLevel-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="f609b-102">SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f609b-103">Legt die sichere Verbindungsebene des Berichtsservers fest</span><span class="sxs-lookup"><span data-stu-id="f609b-103">Sets the secure connection level of the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f609b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f609b-104">Syntax</span></span>  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f609b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f609b-105">Parameters</span></span>  
 <span data-ttu-id="f609b-106">*Level*</span><span class="sxs-lookup"><span data-stu-id="f609b-106">*Level*</span></span>  
 <span data-ttu-id="f609b-107">Ein ganzzahliger Wert, der eine sichere Verbindungsebene darstellt</span><span class="sxs-lookup"><span data-stu-id="f609b-107">An integer value representing a secure connection level.</span></span>  
  
 <span data-ttu-id="f609b-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="f609b-108">*HRESULT*</span></span>  
 <span data-ttu-id="f609b-109">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="f609b-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f609b-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f609b-110">Return Value</span></span>  
 <span data-ttu-id="f609b-111">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f609b-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="f609b-112">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f609b-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="f609b-113">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f609b-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f609b-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f609b-114">Remarks</span></span>  
 <span data-ttu-id="f609b-115">Bei einem Aufruf wird die SecureConnectionLevel-Eigenschaft des Berichtsservers auf den angegebenen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f609b-115">When called, the report server SecureConnectionLevel property is set to the value specified.</span></span> <span data-ttu-id="f609b-116">Der Wert 0 gibt an, dass SSL deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f609b-116">A value of 0 indicates that SSL is turned off.</span></span> <span data-ttu-id="f609b-117">Ein Wert größer oder gleich 1 gibt an, dass SSL aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f609b-117">A value greater than or equal to 1 indicates that SSL is turned on.</span></span>  
  
-   <span data-ttu-id="f609b-118">Wenn der Wert festgelegt ist, wird das SecureConnectionLevel-Element in der Berichts Server-Konfigurationsdatei geändert, und das- `URLRoot` Element in der Konfigurationsdatei wird so festgelegt, dass "https://" verwendet wird, wenn die angegebene *Ebene* größer oder gleich 1 ist, oder "http://", wenn die angegebene *Ebene* gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="f609b-118">When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the `URLRoot` element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.</span></span>  
  
 <span data-ttu-id="f609b-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]wird SecureConnectionLevel zu einer ON-/OFF-Option mit dem Standardwert 0.</span><span class="sxs-lookup"><span data-stu-id="f609b-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0.</span></span> <span data-ttu-id="f609b-120">Bei einem beliebigen Wert größer oder gleich 1, der über eine API der SetSecureConnectionLevel-Methode übergeben wird, wird SSL als aktiviert erachtet und die SecureConnectionLevel-Konfigurationseigenschaft in der Datei „rsreportserver.config“ entsprechend festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f609b-120">For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file.</span></span> <span data-ttu-id="f609b-121">Werte von 2 und 3 werden weiterhin aus Gründen der Abwärtskompatibilität zugelassen.</span><span class="sxs-lookup"><span data-stu-id="f609b-121">Values of 2 and 3 are still allowed for backward compatibility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f609b-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f609b-122">Requirements</span></span>  
 <span data-ttu-id="f609b-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f609b-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f609b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f609b-124">See Also</span></span>  
 [<span data-ttu-id="f609b-125">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="f609b-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
