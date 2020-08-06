---
title: 'RemoveURL-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveURL method
ms.assetid: 3d98bd97-e152-48ce-ab1c-bd2c4f8b7fe9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a32989e8ce8986b785e829d8cc7fcf58fbbf240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619009"
---
# <a name="removeurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ba223-102">RemoveURL-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ba223-102">RemoveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ba223-103">Entfernt eine für den Berichtsserver reservierte URL</span><span class="sxs-lookup"><span data-stu-id="ba223-103">Removes a URL reserved for the report server.</span></span> <span data-ttu-id="ba223-104">Wenn mehrere URLs entfernt werden müssen, muss dies einzeln durch mehrfache Aufrufe dieser API erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ba223-104">If there are multiple URLs that need to be removed, this must be done one by one calling this API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba223-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba223-105">Syntax</span></span>  
  
```vb  
Public Sub RemoveURL(ByVal Application As String, _  
    ByVal UrlString As String, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveURL(string Application, string UrlString, int Lcid,   
    out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba223-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba223-106">Parameters</span></span>  
 <span data-ttu-id="ba223-107">*Anwendung*</span><span class="sxs-lookup"><span data-stu-id="ba223-107">*Application*</span></span>  
 <span data-ttu-id="ba223-108">Der Name der Anwendung, für die die Reservierung entfernt werden soll</span><span class="sxs-lookup"><span data-stu-id="ba223-108">The name of application for which to remove the reservation.</span></span>  
  
 <span data-ttu-id="ba223-109">*URLString*</span><span class="sxs-lookup"><span data-stu-id="ba223-109">*URLString*</span></span>  
 <span data-ttu-id="ba223-110">Die URL für die Reservierung</span><span class="sxs-lookup"><span data-stu-id="ba223-110">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="ba223-111">*lcid*</span><span class="sxs-lookup"><span data-stu-id="ba223-111">*lcid*</span></span>  
 <span data-ttu-id="ba223-112">Das Gebietsschema, das für die zurückgegebenen Fehlermeldungen verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="ba223-112">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="ba223-113">*Fehler*</span><span class="sxs-lookup"><span data-stu-id="ba223-113">*Error*</span></span>  
 <span data-ttu-id="ba223-114">[out] Die Beschreibung des Fehlers, der aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="ba223-114">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="ba223-115">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ba223-115">*HRESULT*</span></span>  
 <span data-ttu-id="ba223-116">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="ba223-116">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba223-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba223-117">Return Value</span></span>  
 <span data-ttu-id="ba223-118">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba223-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ba223-119">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="ba223-119">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba223-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ba223-120">Remarks</span></span>  
 <span data-ttu-id="ba223-121">*UrlString* beinhaltet nicht den Namen des virtuellen Verzeichnisses – die Methode [SetVirtualDirectory-Methode &#40;WMI: MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) ist für diesen Zweck vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ba223-121">*UrlString* does not include the Virtual Directory name - the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="ba223-122">Vor einem Aufruf der [ReserveURL](configurationsetting-method-reserveurl.md) -Methode müssen Sie einen Wert für die VirtualDirectory-Konfigurationseigenschaft des *Anwendungsparameters* angeben.</span><span class="sxs-lookup"><span data-stu-id="ba223-122">Before calling the [ReserveURL](configurationsetting-method-reserveurl.md) method, you must supply a value for the VirtualDirectory configuration property for the *Application* parameter.</span></span> <span data-ttu-id="ba223-123">Verwenden Sie die Methode [SetVirtualDirectory-Methode (WMI: MSReportServer_ConfigurationSetting)](configurationsetting-method-setvirtualdirectory.md), um die VirtualDirectory-Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ba223-123">Use the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method to set the VirtualDirectory property.</span></span>  
  
 <span data-ttu-id="ba223-124">Wenn durch [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ein SSL-Zertifikat bereitgestellt wurde und keine anderen URLs dieses benötigen, wird es entfernt.</span><span class="sxs-lookup"><span data-stu-id="ba223-124">If an SSL Certificate was provisioned by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and no other URLs need it, it is removed.</span></span>  
  
 <span data-ttu-id="ba223-125">Diese Methode verursacht einen "harten" Wiederverwendungsvorgang und ein Beenden aller Nichtkonfigurationsdomänen für Anwendungen. Die Anwendungsdomänen werden nach dem Abschluss des Vorgangs neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="ba223-125">This method causes all non-configuration app domains to hard recycle and stop during this operation; app domains are restarted after this operation complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba223-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ba223-126">Requirements</span></span>  
 <span data-ttu-id="ba223-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba223-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba223-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba223-128">See Also</span></span>  
 [<span data-ttu-id="ba223-129">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="ba223-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
