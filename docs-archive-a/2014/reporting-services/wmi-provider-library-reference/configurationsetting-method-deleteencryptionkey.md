---
title: 'DeleteEncryptionKey-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptionKey method
ms.assetid: ed2f25b6-6a63-468d-9279-a577ca01b096
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e302659615bd620b3b0ed802b83aafc4e9506d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616920"
---
# <a name="deleteencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d0ca3-102">DeleteEncryptionKey-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d0ca3-102">DeleteEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d0ca3-103">Löscht die Verschlüsselungsschlüssel aus der Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="d0ca3-103">Deletes the encryption keys from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ca3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0ca3-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptionKeys(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptionKeys(string InstallationID, out Int32 HRESULT,   
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0ca3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0ca3-105">Parameters</span></span>  
 <span data-ttu-id="d0ca3-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="d0ca3-106">*InstallationID*</span></span>  
 <span data-ttu-id="d0ca3-107">Die Installations-ID eines Berichtsservers, die sich in der Schlüsseltabelle der Berichtsserver-Datenbank befindet</span><span class="sxs-lookup"><span data-stu-id="d0ca3-107">The installation ID of a report server that is in the keys table of the report server database.</span></span>  
  
 <span data-ttu-id="d0ca3-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d0ca3-108">*HRESULT*</span></span>  
 <span data-ttu-id="d0ca3-109">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="d0ca3-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="d0ca3-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="d0ca3-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="d0ca3-111">[out] Ein Zeichenfolgenarray, das zusätzliche Fehler enthält, die durch den Aufruf zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="d0ca3-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0ca3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0ca3-112">Return Value</span></span>  
 <span data-ttu-id="d0ca3-113">Gibt HRESULT zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d0ca3-113">Returns an HRESULT indicating success or failure of the method call.</span></span> <span data-ttu-id="d0ca3-114">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d0ca3-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d0ca3-115">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d0ca3-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0ca3-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d0ca3-116">Remarks</span></span>  
 <span data-ttu-id="d0ca3-117">Durch die *DeleteEncryptionKey* -Methode werden für alle Berichtsserver mit Zugriff auf die sicheren Informationen in der Berichtsserver-Datenbank Einträge aus der Schlüsseltabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d0ca3-117">The *DeleteEncryptionKey* method deletes entries from the keys table for any report servers that have access to the secure information in the report server database.</span></span> <span data-ttu-id="d0ca3-118">Wenn der angegebene *InstallationID* -Parameter keiner Installations-ID in der Datenbank entspricht, gibt die Methode einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="d0ca3-118">If the *InstallationID* parameter specified does not correspond to an installation ID in the database, the method returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ca3-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d0ca3-119">Requirements</span></span>  
 <span data-ttu-id="d0ca3-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ca3-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ca3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0ca3-121">See Also</span></span>  
 [<span data-ttu-id="d0ca3-122">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="d0ca3-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
