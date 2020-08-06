---
title: 'SetDatabaseQueryTimeout-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722378"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b12c5-102">SetDatabaseQueryTimeout-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b12c5-102">SetDatabaseQueryTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b12c5-103">Gibt den Standardtimeoutwert für Berichtsserver-Datenbankabfragen an.</span><span class="sxs-lookup"><span data-stu-id="b12c5-103">Specifies the default time-out value for report server database queries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b12c5-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b12c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b12c5-105">Parameters</span></span>  
 <span data-ttu-id="b12c5-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="b12c5-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="b12c5-107">Der Standardtimeoutwert (in Sekunden) für Berichtsserver-Datenbankabfragen</span><span class="sxs-lookup"><span data-stu-id="b12c5-107">The default timeout value, in seconds, for report server database queries.</span></span>  
  
 <span data-ttu-id="b12c5-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="b12c5-108">*HRESULT*</span></span>  
 <span data-ttu-id="b12c5-109">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="b12c5-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b12c5-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b12c5-110">Return Value</span></span>  
 <span data-ttu-id="b12c5-111">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b12c5-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="b12c5-112">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b12c5-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="b12c5-113">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b12c5-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12c5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b12c5-114">Requirements</span></span>  
 <span data-ttu-id="b12c5-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12c5-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12c5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b12c5-116">See Also</span></span>  
 [<span data-ttu-id="b12c5-117">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="b12c5-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
