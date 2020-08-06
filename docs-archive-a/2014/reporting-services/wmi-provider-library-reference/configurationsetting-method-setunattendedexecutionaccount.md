---
title: 'SetUnattendedExecutionAccount-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetUnattendedExecutionAccount method
ms.assetid: 1ba6be6f-b05c-4ea0-af98-cd0780290b70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 73cf4c633c51de1e3e6b878c66d73ee710e98df6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722369"
---
# <a name="setunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="61201-102">SetUnattendedExecutionAccount-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="61201-102">SetUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="61201-103">Gibt das Konto an, das verwendet wird, um Berichte unbeaufsichtigt auszuführen</span><span class="sxs-lookup"><span data-stu-id="61201-103">Specifies the account used to execute reports unattended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61201-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61201-104">Syntax</span></span>  
  
```vb  
Public Sub SetUnattendedExecutionAccount(UserName as String, _  
    Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetUnattendedExecutionAccount (string UserName,   
    string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61201-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61201-105">Parameters</span></span>  
 <span data-ttu-id="61201-106">*UserName*</span><span class="sxs-lookup"><span data-stu-id="61201-106">*UserName*</span></span>  
 <span data-ttu-id="61201-107">Ein Windows-Konto, das für die unbeaufsichtigte Ausführung verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="61201-107">A Windows account to be used for unattended executions.</span></span>  
  
 <span data-ttu-id="61201-108">*Kennwort*</span><span class="sxs-lookup"><span data-stu-id="61201-108">*Password*</span></span>  
 <span data-ttu-id="61201-109">Das Kennwort für das angegebene Konto</span><span class="sxs-lookup"><span data-stu-id="61201-109">The password for the specified account.</span></span>  
  
 <span data-ttu-id="61201-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="61201-110">*HRESULT*</span></span>  
 <span data-ttu-id="61201-111">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="61201-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61201-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61201-112">Return Value</span></span>  
 <span data-ttu-id="61201-113">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="61201-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="61201-114">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="61201-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="61201-115">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="61201-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61201-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="61201-116">Remarks</span></span>  
 <span data-ttu-id="61201-117">Die Methode „SetUnattendedExecutionAccount“ überprüft nicht, ob sich der Berichtsserver als der angegebene Benutzer anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="61201-117">The SetUnattendedExecutionAccount method does not verify whether the report server can log in as the specified user.</span></span>  
  
 <span data-ttu-id="61201-118">Die Methode „SetUnattendedExecutionAccount“ kann nicht für die unbeaufsichtigte Ausführung im Kontext des Report Server-Windows-Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61201-118">It is not possible to use the SetUnattendedExecutionAccount method to run unattended executions in the context of the report server Windows service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61201-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61201-119">Requirements</span></span>  
 <span data-ttu-id="61201-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61201-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61201-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61201-121">See Also</span></span>  
 [<span data-ttu-id="61201-122">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="61201-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
