---
title: 'ListReservedURLs-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListReservedURLs method
ms.assetid: 32335af1-5eae-4420-a0ef-b1e8a3267166
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7639741adb0c756961c4c6b63a3bffb627c4a89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616907"
---
# <a name="listreservedurls-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a9063-102">ListReservedURLs-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a9063-102">ListReservedURLs Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a9063-103">Listet für alle Anwendungen auf dem Berichtsserver reservierte URLs auf</span><span class="sxs-lookup"><span data-stu-id="a9063-103">Lists URLs reserved for all applications on the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9063-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9063-104">Syntax</span></span>  
  
```vb  
Public Sub ListReservedUrls(ByRef Application() as String, ByRef UrlString() as String, _  
    ByRef Account() as String, ByRef AccountSID() as String, _  
    ByRef length() as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListReservedUrls(out string[] Application, out string[] UrlString,  
        out string[] Account, out string[] AccountSID,  
        out int[] Length, out int[] HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9063-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9063-105">Parameters</span></span>  
 <span data-ttu-id="a9063-106">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="a9063-106">*Application[]*</span></span>  
 <span data-ttu-id="a9063-107">[out] Die Anwendungen, die URL-Reservierungen aufweisen</span><span class="sxs-lookup"><span data-stu-id="a9063-107">[out] The applications that have URL reservations.</span></span>  
  
 <span data-ttu-id="a9063-108">*UrlString[]*</span><span class="sxs-lookup"><span data-stu-id="a9063-108">*UrlString[]*</span></span>  
 <span data-ttu-id="a9063-109">[out] Die URLs, die reserviert sind</span><span class="sxs-lookup"><span data-stu-id="a9063-109">[out] The URLs that are reserved.</span></span>  
  
 <span data-ttu-id="a9063-110">*Account[]*</span><span class="sxs-lookup"><span data-stu-id="a9063-110">*Account[]*</span></span>  
 <span data-ttu-id="a9063-111">[out] Die mit dem Konto für die URL-Reservierungen verknüpften Kontonamen</span><span class="sxs-lookup"><span data-stu-id="a9063-111">[out] The account names associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="a9063-112">*AccountSID[]*</span><span class="sxs-lookup"><span data-stu-id="a9063-112">*AccountSID[]*</span></span>  
 <span data-ttu-id="a9063-113">[out] Die mit dem Konto für die URL-Reservierungen verknüpften Konto-SIDs</span><span class="sxs-lookup"><span data-stu-id="a9063-113">[out] The account SIDs associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="a9063-114">*Länge*</span><span class="sxs-lookup"><span data-stu-id="a9063-114">*Length*</span></span>  
 <span data-ttu-id="a9063-115">[out] Die Länge der von der Methode zurückgegebenen Arrays</span><span class="sxs-lookup"><span data-stu-id="a9063-115">[out] The length of the arrays returned by the method.</span></span>  
  
 <span data-ttu-id="a9063-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="a9063-116">*HRESULT*</span></span>  
 <span data-ttu-id="a9063-117">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="a9063-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9063-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a9063-118">Return Value</span></span>  
 <span data-ttu-id="a9063-119">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9063-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="a9063-120">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a9063-120">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9063-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a9063-121">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9063-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a9063-122">Requirements</span></span>  
 <span data-ttu-id="a9063-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9063-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9063-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9063-124">See Also</span></span>  
 [<span data-ttu-id="a9063-125">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="a9063-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
