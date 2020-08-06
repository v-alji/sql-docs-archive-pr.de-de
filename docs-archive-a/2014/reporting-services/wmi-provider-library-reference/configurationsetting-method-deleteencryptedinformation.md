---
title: 'DeleteEncryptedInformation-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptedInformation method
ms.assetid: c14ed187-bdd9-4304-88e3-72072f03c21b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d00dc3e90816cd04c84f124cdc3d25a9ac122bba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616927"
---
# <a name="deleteencryptedinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="13d9b-102">DeleteEncryptedInformation-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="13d9b-102">DeleteEncryptedInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="13d9b-103">Löscht die verschlüsselten Informationen aus der Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="13d9b-103">Deletes the encrypted information from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13d9b-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptedInformation(ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptedInformation(out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13d9b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13d9b-105">Parameters</span></span>  
 <span data-ttu-id="13d9b-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="13d9b-106">*HRESULT*</span></span>  
 <span data-ttu-id="13d9b-107">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="13d9b-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="13d9b-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="13d9b-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="13d9b-109">[out] Ein Zeichenfolgenarray, das zusätzliche Fehler enthält, die durch den Aufruf zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="13d9b-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13d9b-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="13d9b-110">Return Value</span></span>  
 <span data-ttu-id="13d9b-111">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="13d9b-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="13d9b-112">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="13d9b-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="13d9b-113">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="13d9b-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13d9b-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="13d9b-114">Remarks</span></span>  
 <span data-ttu-id="13d9b-115">Wenn diese Methode aufgerufen wird, werden die folgenden Daten gelöscht:</span><span class="sxs-lookup"><span data-stu-id="13d9b-115">When this method is invoked, the following data is deleted:</span></span>  
  
-   <span data-ttu-id="13d9b-116">Datenquellinformationen, die verschlüsselt werden, einschließlich des Benutzernamens und des Kennworts</span><span class="sxs-lookup"><span data-stu-id="13d9b-116">Data source information that is encrypted, including user name and password.</span></span>  
  
-   <span data-ttu-id="13d9b-117">Abonnementdaten, die mithilfe der Schnittstellen der Übermittlungserweiterung verschlüsselt werden</span><span class="sxs-lookup"><span data-stu-id="13d9b-117">Subscription data that is encrypted using the delivery extension interfaces.</span></span>  
  
-   <span data-ttu-id="13d9b-118">Alle Informationen aus der Schlüsseltabelle der Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="13d9b-118">All the information from the keys table in the report server database.</span></span>  
  
 <span data-ttu-id="13d9b-119">Nach dem Aufruf dieser Methode muss der Benutzer jeden Computer initialisieren, auf dem die Berichtsserver-Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13d9b-119">After this method is invoked, the user must initialize each computer that uses the report server database.</span></span>  
  
 <span data-ttu-id="13d9b-120">Der Aufruf der „DeleteEncryptedInformation“-Methode hat keinen Einfluss auf die Berichtsserver-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="13d9b-120">Calling the DeleteEncryptedInformation method does not affect the report server configuration file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d9b-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13d9b-121">Requirements</span></span>  
 <span data-ttu-id="13d9b-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d9b-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d9b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13d9b-123">See Also</span></span>  
 [<span data-ttu-id="13d9b-124">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="13d9b-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
