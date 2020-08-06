---
title: 'RestoreEncryptionKey-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RestoreEncryptionKey method
ms.assetid: 37e949f5-15af-4858-848a-f482ee94fcd9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e67478541bab615a6d441ae273ed3385a8654203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722393"
---
# <a name="restoreencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b5121-102">RestoreEncryptionKey-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b5121-102">RestoreEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b5121-103">Wendet den angegebenen Verschlüsselungsschlüssel erneut auf die Berichtsserver-Datenbank an</span><span class="sxs-lookup"><span data-stu-id="b5121-103">Reapplies the specified encryption key to the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5121-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5121-104">Syntax</span></span>  
  
```vb  
Public Sub RestoreEncryptionKey(ByRef KeyFile() As Integer, _  
    ByRef Length As Int32, ByVal Password As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void RestoreEncryptionKey(out Byte[] KeyFile, out Int32 Length,   
            string Password, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5121-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5121-105">Parameters</span></span>  
 <span data-ttu-id="b5121-106">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="b5121-106">*KeyFile[]*</span></span>  
 <span data-ttu-id="b5121-107">[out] Ein Array, das den verschlüsselten Verschlüsselungsschlüssel enthält</span><span class="sxs-lookup"><span data-stu-id="b5121-107">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="b5121-108">*Länge*</span><span class="sxs-lookup"><span data-stu-id="b5121-108">*Length*</span></span>  
 <span data-ttu-id="b5121-109">[out] Die Länge des von der Methode zurückgegebenen Arrays</span><span class="sxs-lookup"><span data-stu-id="b5121-109">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="b5121-110">*Kennwort*</span><span class="sxs-lookup"><span data-stu-id="b5121-110">*Password*</span></span>  
 <span data-ttu-id="b5121-111">Eine Zeichenfolge, die zum Verschlüsseln des Verschlüsselungsschlüssels verwendet wird</span><span class="sxs-lookup"><span data-stu-id="b5121-111">A string used to encrypt the encryption key.</span></span>  
  
 <span data-ttu-id="b5121-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="b5121-112">*HRESULT*</span></span>  
 <span data-ttu-id="b5121-113">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="b5121-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="b5121-114">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="b5121-114">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="b5121-115">[out] Ein Zeichenfolgenarray, das zusätzliche Fehler enthält, die durch den Aufruf zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="b5121-115">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5121-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b5121-116">Return Value</span></span>  
 <span data-ttu-id="b5121-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5121-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="b5121-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b5121-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="b5121-119">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b5121-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5121-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b5121-120">Remarks</span></span>  
 <span data-ttu-id="b5121-121">Wenn bereits ein Eintrag für den Berichtsserver in der Berichtsserver-Datenbank vorhanden ist, wird dieser gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b5121-121">If an entry already exists for the report server in the report server database, it is deleted.</span></span> <span data-ttu-id="b5121-122">Der neue Eintrag wird dann mit dem angegebenen Verschlüsselungsschlüssel und dem öffentlichen Schlüssel des Berichtsservers erstellt.</span><span class="sxs-lookup"><span data-stu-id="b5121-122">The new entry is then created using the specified encryption key and the report server's public key.</span></span>  
  
 <span data-ttu-id="b5121-123">Diese Methode ist am effektivsten, wenn sie nach der [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) -Methode aufgerufen wird, die die Liste der Verschlüsselungsschlüssel löscht.</span><span class="sxs-lookup"><span data-stu-id="b5121-123">The method is most effective when called after the [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) method, which clears the list of encryption keys.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5121-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b5121-124">Requirements</span></span>  
 <span data-ttu-id="b5121-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5121-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5121-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5121-126">See Also</span></span>  
 [<span data-ttu-id="b5121-127">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="b5121-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
