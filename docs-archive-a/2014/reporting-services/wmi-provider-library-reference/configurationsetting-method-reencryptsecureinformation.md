---
title: 'ReencryptSecureInformation-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620200"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d2bed-102">ReencryptSecureInformation-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d2bed-102">ReencryptSecureInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d2bed-103">Generiert einen neuen Verschlüsselungsschlüssel und verschlüsselt alle sicheren Informationen im Katalog erneut mit diesem neuen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d2bed-103">Generates a new encryption key and re-encrypts all secure information in the catalog using this new key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2bed-104">Syntax</span></span>  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2bed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2bed-105">Parameters</span></span>  
 <span data-ttu-id="d2bed-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d2bed-106">*HRESULT*</span></span>  
 <span data-ttu-id="d2bed-107">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="d2bed-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="d2bed-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="d2bed-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="d2bed-109">[out] Ein Zeichenfolgenarray, das zusätzliche Fehler enthält, die durch den Aufruf zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="d2bed-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2bed-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2bed-110">Return Value</span></span>  
 <span data-ttu-id="d2bed-111">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d2bed-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d2bed-112">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d2bed-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d2bed-113">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d2bed-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2bed-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d2bed-114">Remarks</span></span>  
 <span data-ttu-id="d2bed-115">Die ReencryptSecureInformation-Methode ermöglicht es dem Administrator, den vorhandenen Verschlüsselungsschlüssel durch einen neuen Schlüssel zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d2bed-115">The ReencryptSecureInformation method allows the administrator to replace the existing encryption key with a new key.</span></span>  
  
 <span data-ttu-id="d2bed-116">Bei einem Aufruf dieser Methode generiert der Berichtsserver einen neuen Verschlüsselungsschlüssel und durchläuft den gesamten verschlüsselten Inhalt, um ihn erneut mit diesem neuen Verschlüsselungsschlüssel zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d2bed-116">When this method is invoked, the report server generates a new encryption key and iterates through all encrypted content to re-encrypt it with the new encryption key.</span></span>  
  
 <span data-ttu-id="d2bed-117">Übermittlungserweiterungen können gesicherte Informationen in den Strukturen ihrer Übermittlungseinstellungen speichern.</span><span class="sxs-lookup"><span data-stu-id="d2bed-117">Delivery extensions can store secured information in their delivery settings structures.</span></span> <span data-ttu-id="d2bed-118">Beim Aufruf von ReencryptSecureInformation lädt der Berichtsserver jedes Abonnement und die entsprechende Übermittlungserweiterung, um die in den zugehörigen Einstellungen gespeicherten Informationen erneut zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d2bed-118">When ReencryptSecureInformation is called, the report server loads each subscription and the corresponding delivery extension to re-encrypt information stored in the associated settings.</span></span>  
  
 <span data-ttu-id="d2bed-119">Wenn diese Methode auf einem Computer in einer Bereitstellung für horizontales Skalieren ausgeführt wird, muss jeder Computer in der Bereitstellung für horizontales Skalieren neu initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2bed-119">If this method is run on a computer in a scale-out deployment, each computer in the scale-out deployment will need to be initialized again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2bed-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d2bed-120">Requirements</span></span>  
 <span data-ttu-id="d2bed-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2bed-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bed-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2bed-122">See Also</span></span>  
 [<span data-ttu-id="d2bed-123">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="d2bed-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
