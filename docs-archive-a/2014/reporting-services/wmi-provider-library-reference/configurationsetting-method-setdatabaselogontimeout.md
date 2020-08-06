---
title: 'SetDatabaseLogonTimeout-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseLogonTimeout method
ms.assetid: b8773596-5b98-4355-a4ab-4412e1317c67
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf93cd9158c3489db611446ac8523701f52831f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722386"
---
# <a name="setdatabaselogontimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4021f-102">SetDatabaseLogonTimeout-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="4021f-102">SetDatabaseLogonTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4021f-103">Gibt den Standardtimeoutwert für Verbindungen mit der Berichtsserver-Datenbank an</span><span class="sxs-lookup"><span data-stu-id="4021f-103">Specifies the default timeout value for report server database connections.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4021f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4021f-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseLogonTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseLogonTimeout(Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4021f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4021f-105">Parameters</span></span>  
 <span data-ttu-id="4021f-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="4021f-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="4021f-107">Der Standardtimeoutwert (in Sekunden) für Verbindungen mit der Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="4021f-107">The default time-out value, in seconds, for report server database connections.</span></span>  
  
 <span data-ttu-id="4021f-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4021f-108">*HRESULT*</span></span>  
 <span data-ttu-id="4021f-109">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="4021f-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4021f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4021f-110">Return Value</span></span>  
 <span data-ttu-id="4021f-111">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4021f-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4021f-112">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4021f-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4021f-113">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4021f-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4021f-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4021f-114">Requirements</span></span>  
 <span data-ttu-id="4021f-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4021f-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4021f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4021f-116">See Also</span></span>  
 [<span data-ttu-id="4021f-117">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="4021f-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
