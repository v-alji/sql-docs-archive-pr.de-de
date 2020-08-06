---
title: 'ReserveURL-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722394"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="5df13-102">ReserveURL-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="5df13-102">ReserveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="5df13-103">Fügt eine URL-Reservierung für eine gegebene Anwendung hinzu</span><span class="sxs-lookup"><span data-stu-id="5df13-103">Adds a URL reservation for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5df13-104">Syntax</span></span>  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5df13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5df13-105">Parameters</span></span>  
 <span data-ttu-id="5df13-106">*Anwendung*</span><span class="sxs-lookup"><span data-stu-id="5df13-106">*Application*</span></span>  
 <span data-ttu-id="5df13-107">Der Name der Anwendung, für die die URL reserviert werden soll</span><span class="sxs-lookup"><span data-stu-id="5df13-107">The name of application to reserve the URL for.</span></span>  
  
 <span data-ttu-id="5df13-108">*URLString*</span><span class="sxs-lookup"><span data-stu-id="5df13-108">*URLString*</span></span>  
 <span data-ttu-id="5df13-109">Die URL für die Reservierung</span><span class="sxs-lookup"><span data-stu-id="5df13-109">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="5df13-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="5df13-110">*lcid*</span></span>  
 <span data-ttu-id="5df13-111">Das Gebietsschema, das für die zurückgegebenen Fehlermeldungen verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="5df13-111">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="5df13-112">*Fehler*</span><span class="sxs-lookup"><span data-stu-id="5df13-112">*Error*</span></span>  
 <span data-ttu-id="5df13-113">[out] Die Beschreibung des Fehlers, der aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="5df13-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="5df13-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="5df13-114">*HRESULT*</span></span>  
 <span data-ttu-id="5df13-115">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="5df13-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5df13-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5df13-116">Return Value</span></span>  
 <span data-ttu-id="5df13-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5df13-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="5df13-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="5df13-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5df13-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5df13-119">Remarks</span></span>  
 <span data-ttu-id="5df13-120">*UrlString* beinhaltet nicht den Namen des virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="5df13-120">*UrlString* does not include the virtual directory name.</span></span> <span data-ttu-id="5df13-121">Dazu wird die [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) -Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5df13-121">The [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="5df13-122">URL-Reservierungen werden für das aktuelle Windows-Dienstkonto erstellt.</span><span class="sxs-lookup"><span data-stu-id="5df13-122">URL reservations are created for the current windows service account.</span></span> <span data-ttu-id="5df13-123">Eine Änderung des Windows-Dienstkontos erfordert das manuelle Aktualisieren der URL-Reservierungen.</span><span class="sxs-lookup"><span data-stu-id="5df13-123">Changing the windows service account requires updating all the URL reservations manually.</span></span>  
  
 <span data-ttu-id="5df13-124">Diese Methode verursacht einen "harten" Wiederverwendungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="5df13-124">This method causes all application domains to hard recycle.</span></span> <span data-ttu-id="5df13-125">Anwendungsdomänen werden neu gestartet, nachdem dieser Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5df13-125">Application domains are restarted after this operation is complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5df13-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5df13-126">Requirements</span></span>  
 <span data-ttu-id="5df13-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5df13-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df13-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5df13-128">See Also</span></span>  
 [<span data-ttu-id="5df13-129">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="5df13-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
