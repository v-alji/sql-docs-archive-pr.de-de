---
title: 'InitializeReportServer-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- InitializeReportServer (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- InitializeReportServer method
ms.assetid: 0304acc2-1fd7-437b-94d9-1c1073dd3ca4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6a8e44a98320ca2c9add6a1b6eef9362eef7731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616916"
---
# <a name="initializereportserver-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="bac38-102">InitializeReportServer-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="bac38-102">InitializeReportServer Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="bac38-103">Initialisiert die angegebene Berichtsdienstinstanz</span><span class="sxs-lookup"><span data-stu-id="bac38-103">Initializes the specified report service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bac38-104">Syntax</span></span>  
  
```vb  
Public Sub InitializeReportServer(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void InitializeReportServer(string InstallationID,   
    out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac38-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bac38-105">Parameters</span></span>  
 <span data-ttu-id="bac38-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="bac38-106">*InstallationID*</span></span>  
 <span data-ttu-id="bac38-107">Eine Zeichenfolge, mit der der Verschlüsselungsschlüssel verschlüsselt wird, bevor er zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="bac38-107">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="bac38-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="bac38-108">*HRESULT*</span></span>  
 <span data-ttu-id="bac38-109">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="bac38-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="bac38-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="bac38-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="bac38-111">[out] Ein Zeichenfolgenarray, das zusätzliche Fehler enthält, die durch den Aufruf zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="bac38-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bac38-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bac38-112">Return Value</span></span>  
 <span data-ttu-id="bac38-113">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bac38-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="bac38-114">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bac38-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="bac38-115">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bac38-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bac38-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bac38-116">Remarks</span></span>  
 <span data-ttu-id="bac38-117">Wenn diese Methode aufgerufen wird, wird der Verschlüsselungsschlüssel, der auf die sicheren Informationen der Berichtsserverdatenbank zugreift, mit dem öffentlichen Schlüssel des Berichtsservers verschlüsselt, der von *InstallationID*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bac38-117">When this method is called, the encryption key that accesses the report server database secure information is encrypted using the public key of the report server identified by *InstallationID*.</span></span>  
  
 <span data-ttu-id="bac38-118">Der angegebene öffentliche Schlüssel des Berichtsservers muss zuvor in die Berichtsserver-Datenbank geschrieben worden sein.</span><span class="sxs-lookup"><span data-stu-id="bac38-118">The specified report server's public key must have previously been written into the report server database.</span></span>  
  
 <span data-ttu-id="bac38-119">Die *InitializeReportServer* -Methode muss für einen Berichtsserver aufgerufen werden, der bereits Zugriff auf die sicheren Informationen hat, damit der Verschlüsselungsschlüssel entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bac38-119">The *InitializeReportServer* method must be called against a report server that already has access to the secure information so that it can decrypt the encryption key.</span></span> <span data-ttu-id="bac38-120">Der resultierende verschlüsselte Verschlüsselungsschlüssel wird dann in der Berichtsserver-Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bac38-120">The resulting encrypted encryption key is then stored in the report server database.</span></span>  
  
 <span data-ttu-id="bac38-121">Wenn die [IsInitialized](configurationsetting-property-isinitialized.md) -Eigenschaft des Berichts Servers auf festgelegt ist `true` , wenn die InitializeReportServer-Methode aufgerufen wird, gibt die Methode Erfolg zurück, ohne zu versuchen, den Verschlüsselungsschlüssel zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="bac38-121">If the report server's [IsInitialized](configurationsetting-property-isinitialized.md) property is set to `true` when the InitializeReportServer method is called, the method returns success without trying to encrypt the encryption key.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac38-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bac38-122">Requirements</span></span>  
 <span data-ttu-id="bac38-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac38-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac38-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bac38-124">See Also</span></span>  
 [<span data-ttu-id="bac38-125">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="bac38-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
