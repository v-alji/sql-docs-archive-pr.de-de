---
title: 'ListReportServersInDatabase-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616909"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="789cc-102">ListReportServersInDatabase-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="789cc-102">ListReportServersInDatabase Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="789cc-103">Gibt die Liste von Berichtsserverinstallationen zurück, die in der Berichtsserver-Datenbank vorhanden sind. Dies geschieht unabhängig davon, ob diese Installationen Zugriff auf sichere Informationen haben.</span><span class="sxs-lookup"><span data-stu-id="789cc-103">Returns the list of report server installations that are present in the report server database, regardless of whether they have access to secure information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="789cc-104">Syntax</span></span>  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="789cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="789cc-105">Parameters</span></span>  
 <span data-ttu-id="789cc-106">*MachineNames[]*</span><span class="sxs-lookup"><span data-stu-id="789cc-106">*MachineNames[]*</span></span>  
 <span data-ttu-id="789cc-107">[out] Ein Array, das die Computernamen für die Berichtsserverinstallationen in der Datenbank enthält</span><span class="sxs-lookup"><span data-stu-id="789cc-107">[out] An array containing the machine names for the report server installations in the database.</span></span>  
  
 <span data-ttu-id="789cc-108">*InstanceNames[]*</span><span class="sxs-lookup"><span data-stu-id="789cc-108">*InstanceNames[]*</span></span>  
 <span data-ttu-id="789cc-109">[aus] Ein Array mit den Instanznamen der einzelnen Berichtsserverinstallationen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="789cc-109">[out] An array containing the instance names of each of the report server installations in the database.</span></span>  
  
 <span data-ttu-id="789cc-110">*InstallationIDs[]*</span><span class="sxs-lookup"><span data-stu-id="789cc-110">*InstallationIDs[]*</span></span>  
 <span data-ttu-id="789cc-111">[out] Ein Array, das die Installations-IDs für jede Berichtsserverinstallation in der Datenbank enthält</span><span class="sxs-lookup"><span data-stu-id="789cc-111">[out] An array containing the installation IDs of each report server installation in the database.</span></span>  
  
 <span data-ttu-id="789cc-112">*IsInitialized[]*</span><span class="sxs-lookup"><span data-stu-id="789cc-112">*IsInitialized[]*</span></span>  
 <span data-ttu-id="789cc-113">[out] Ein Array, das den Initialisierungsstatus für jede Berichtsserverinstallation in der Datenbank enthält</span><span class="sxs-lookup"><span data-stu-id="789cc-113">[out] An array containing initialization status for each report server installation in the database.</span></span>  
  
 <span data-ttu-id="789cc-114">*Länge*</span><span class="sxs-lookup"><span data-stu-id="789cc-114">*Length*</span></span>  
 <span data-ttu-id="789cc-115">[out] Die Länge der von der Methode zurückgegebenen Arrays</span><span class="sxs-lookup"><span data-stu-id="789cc-115">[out] The length of the arrays returned by the method.</span></span> <span data-ttu-id="789cc-116">Alle zurückgegebenen Arrays haben die gleiche Länge.</span><span class="sxs-lookup"><span data-stu-id="789cc-116">All returned arrays have the same length.</span></span>  
  
 <span data-ttu-id="789cc-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="789cc-117">*HRESULT*</span></span>  
 <span data-ttu-id="789cc-118">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="789cc-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="789cc-119">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="789cc-119">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="789cc-120">[out] Ein Zeichenfolgenarray, das zusätzliche Fehler enthält, die durch den Aufruf zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="789cc-120">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="789cc-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="789cc-121">Return Value</span></span>  
 <span data-ttu-id="789cc-122">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="789cc-122">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="789cc-123">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="789cc-123">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="789cc-124">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="789cc-124">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="789cc-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="789cc-125">Remarks</span></span>  
 <span data-ttu-id="789cc-126">ListReportServersInDatabase listet die Berichtsserverinstallationen auf, die in der Berichtsserver-Datenbank vorhanden sind. Dies geschieht unabhängig davon, ob diese Installationen Zugriff auf sichere Informationen haben, und es wird ein übereinstimmender Satz von Arrays mit Informationen zu jeder Installation zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="789cc-126">ListReportServersInDatabase lists the report server installations that are present in the report server database, regardless of whether they have access to secure information, and returns a matched set of arrays containing information about each installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="789cc-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="789cc-127">Requirements</span></span>  
 <span data-ttu-id="789cc-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="789cc-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="789cc-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="789cc-129">See Also</span></span>  
 [<span data-ttu-id="789cc-130">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="789cc-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
