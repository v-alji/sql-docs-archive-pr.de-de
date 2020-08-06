---
title: 'SetVirtualDirectory-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SetVirtualDirectory method
ms.assetid: 1a25cb1d-38d5-401a-970b-87b642a780e4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7f45181f3f6a791f5cb64a7519285b6d2a87dd36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722361"
---
# <a name="setvirtualdirectory-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="11544-102">SetVirtualDirectory-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="11544-102">SetVirtualDirectory Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="11544-103">Legt den Namen des virtuellen Verzeichnisses für eine angegebene Anwendung fest.</span><span class="sxs-lookup"><span data-stu-id="11544-103">Sets the name of the virtual directory for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11544-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11544-104">Syntax</span></span>  
  
```vb  
Public Sub SetVirtualDirectory(ByVal Application As String, _  
    ByVal VirtualDirectory As String, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetVirtualDirectory(string Application, string VirtualDirectory,   
       int Lcid,out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11544-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11544-105">Parameters</span></span>  
 <span data-ttu-id="11544-106">*Anwendung*</span><span class="sxs-lookup"><span data-stu-id="11544-106">*Application*</span></span>  
 <span data-ttu-id="11544-107">Der für das virtuelle Verzeichnis festzulegende Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11544-107">The name of application for which to set the virtual directory.</span></span>  
  
 <span data-ttu-id="11544-108">*VirtualDirectory*</span><span class="sxs-lookup"><span data-stu-id="11544-108">*VirtualDirectory*</span></span>  
 <span data-ttu-id="11544-109">Der Name des virtuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="11544-109">The name of the virtual directory.</span></span>  
  
 <span data-ttu-id="11544-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="11544-110">*lcid*</span></span>  
 <span data-ttu-id="11544-111">Die Gebietsschema-ID für das virtuelle Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="11544-111">The locale id for the virtual directory.</span></span>  
  
 <span data-ttu-id="11544-112">*Fehler*</span><span class="sxs-lookup"><span data-stu-id="11544-112">*Error*</span></span>  
 <span data-ttu-id="11544-113">[out] Die Beschreibung des Fehlers, der aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="11544-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="11544-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="11544-114">*HRESULT*</span></span>  
 <span data-ttu-id="11544-115">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="11544-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11544-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="11544-116">Return Value</span></span>  
 <span data-ttu-id="11544-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="11544-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="11544-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="11544-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11544-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="11544-119">Remarks</span></span>  
 <span data-ttu-id="11544-120">Eine Anwendung kann nur einen Namen für ein virtuelles Verzeichnis für alle URL-Reservierungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="11544-120">An application can have only one virtual directory name for all URL reservations.</span></span>  
  
 <span data-ttu-id="11544-121">VirtualDirectory muss den Namenskonventionen für virtuelle Verzeichnisse entsprechen.</span><span class="sxs-lookup"><span data-stu-id="11544-121">VirtualDirectory must conform to naming conventions for virtual directories.</span></span> <span data-ttu-id="11544-122">VirtualDirectory darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="11544-122">VirtualDirectory must not be empty string or blank.</span></span>  
  
 <span data-ttu-id="11544-123">Aktualisiert den Wert des \Configuration\URLReservations\Application\VirtualDirectory-Elements.</span><span class="sxs-lookup"><span data-stu-id="11544-123">Updates the value of the \Configuration\URLReservations\Application\VirtualDirectory element.</span></span> <span data-ttu-id="11544-124">Ist erfolgreich, auch wenn noch keine URL-Reservierungen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="11544-124">Succeeds even if no URL reservations have been created yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11544-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="11544-125">Requirements</span></span>  
 <span data-ttu-id="11544-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11544-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11544-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11544-127">See Also</span></span>  
 [<span data-ttu-id="11544-128">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="11544-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
