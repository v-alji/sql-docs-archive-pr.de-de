---
title: RemoveUnattendedExecutionAccount-Methode (WMI-MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveUnattendedExecutionAccount method
ms.assetid: 77e371c1-7c26-44f9-9119-7c8dc838db32
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efe0523c9aa13315399c043367ef05a63da46e91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719414"
---
# <a name="removeunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="11467-102">RemoveUnattendedExecutionAccount-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="11467-102">RemoveUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="11467-103">Löscht den Eintrag für das Konto für die unbeaufsichtigte Ausführung aus der Berichtsserver-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="11467-103">Deletes the unattended execution account entry from the report server configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11467-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11467-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveUnattendedExecutionAccount(ByRef HRESULT as Int32)  
```  
  
```csharp  
public void RemoveUnattendedExecutionAccount (out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11467-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11467-105">Parameters</span></span>  
 <span data-ttu-id="11467-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="11467-106">*HRESULT*</span></span>  
 <span data-ttu-id="11467-107">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="11467-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11467-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="11467-108">Return Value</span></span>  
 <span data-ttu-id="11467-109">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="11467-109">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="11467-110">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="11467-110">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="11467-111">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="11467-111">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11467-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="11467-112">Requirements</span></span>  
 <span data-ttu-id="11467-113">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11467-113">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11467-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11467-114">See Also</span></span>  
 [<span data-ttu-id="11467-115">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="11467-115">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
