---
title: 'SetServiceState-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722365"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="cf7d5-102">SetServiceState-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="cf7d5-102">SetServiceState Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="cf7d5-103">Aktiviert und deaktiviert den Berichtsserver-Windows-Dienst und den Berichtsserver-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-103">Turns the Report Server Windows and Web services on and off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf7d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf7d5-104">Syntax</span></span>  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf7d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf7d5-105">Parameters</span></span>  
 <span data-ttu-id="cf7d5-106">*EnableWindowsService*</span><span class="sxs-lookup"><span data-stu-id="cf7d5-106">*EnableWindowsService*</span></span>  
 <span data-ttu-id="cf7d5-107">Ein `Boolean`-Wert, der den Status des Windows-Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-107">A `Boolean` value indicating the state of the Windows service.</span></span> <span data-ttu-id="cf7d5-108">Bei dem Wert `true` wird der Windows-Dienst des Berichtsservers gestartet. Bei dem Wert `false` wird der Windows-Dienst beendet.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-108">A value of `true` starts the Report Server Windows service; a value of `false` stops the Windows service.</span></span>  
  
 <span data-ttu-id="cf7d5-109">*EnableWebService*</span><span class="sxs-lookup"><span data-stu-id="cf7d5-109">*EnableWebService*</span></span>  
 <span data-ttu-id="cf7d5-110">Ein `Boolean`-Wert, der den Status des [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Webdiensts angibt.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-110">A `Boolean` value indicating the state of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web service.</span></span> <span data-ttu-id="cf7d5-111">Bei dem Wert `true` wird der Webdienst des Berichtsservers gestartet. Bei dem Wert `false` wird der Webdienst beendet.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-111">A value of `true` starts the Report Server Web service; a value of `false` stops the Web service</span></span>  
  
 <span data-ttu-id="cf7d5-112">*EnableReportManager*</span><span class="sxs-lookup"><span data-stu-id="cf7d5-112">*EnableReportManager*</span></span>  
 <span data-ttu-id="cf7d5-113">Ein `Boolean`-Wert, der den gewünschten Status des Berichts-Managers angibt.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-113">A `Boolean` value indicating the desired state of the Report manager.</span></span>  
  
 <span data-ttu-id="cf7d5-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="cf7d5-114">*HRESULT*</span></span>  
 <span data-ttu-id="cf7d5-115">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf7d5-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cf7d5-116">Return Value</span></span>  
 <span data-ttu-id="cf7d5-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="cf7d5-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="cf7d5-119">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cf7d5-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf7d5-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cf7d5-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf7d5-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cf7d5-121">Requirements</span></span>  
 <span data-ttu-id="cf7d5-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf7d5-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7d5-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf7d5-123">See Also</span></span>  
 [<span data-ttu-id="cf7d5-124">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="cf7d5-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
