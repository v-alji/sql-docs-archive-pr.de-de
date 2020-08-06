---
title: GetDatabaseVersionDisplayName-Methode (WMI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetDatabaseVersionDisplayName method
ms.assetid: e1286424-7043-4f12-a7ad-1cf69e81baa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b39ce39a4f26964c148631c903869b0234e2b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616913"
---
# <a name="getdatabaseversiondisplayname-method-wmi"></a><span data-ttu-id="aef9a-102">GetDatabaseVersionDisplayName-Methode (WMI)</span><span class="sxs-lookup"><span data-stu-id="aef9a-102">GetDatabaseVersionDisplayName Method (WMI)</span></span>
  <span data-ttu-id="aef9a-103">Ruft den Anzeigenamen für eine gegebene Versionszeichenfolge in der Berichtsserver-Datenbank ab</span><span class="sxs-lookup"><span data-stu-id="aef9a-103">Gets the display name for a given report server database version string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aef9a-104">Syntax</span></span>  
  
```vb  
Public Sub GetDatabaseVersionDisplayName(Version As String, DisplayName As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetDatabaseVersionDisplayName(string Version, string DisplayName, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aef9a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aef9a-105">Parameters</span></span>  
 <span data-ttu-id="aef9a-106">*Version*</span><span class="sxs-lookup"><span data-stu-id="aef9a-106">*Version*</span></span>  
 <span data-ttu-id="aef9a-107">Eine Zeichenfolge, die die Versionszeichenfolge für eine Berichtsserver-Datenbank enthält</span><span class="sxs-lookup"><span data-stu-id="aef9a-107">A string that contains the version string for a report server database.</span></span>  
  
 <span data-ttu-id="aef9a-108">*DisplayName*</span><span class="sxs-lookup"><span data-stu-id="aef9a-108">*DisplayName*</span></span>  
 <span data-ttu-id="aef9a-109">[out] Eine Zeichenfolge, die den Anzeigenamen enthält, welcher der angegebenen Version entspricht</span><span class="sxs-lookup"><span data-stu-id="aef9a-109">[out] A string that contains the display name that corresponds to the version supplied.</span></span>  
  
 <span data-ttu-id="aef9a-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="aef9a-110">*HRESULT*</span></span>  
 <span data-ttu-id="aef9a-111">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="aef9a-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aef9a-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="aef9a-112">Remarks</span></span>  
 <span data-ttu-id="aef9a-113">In der folgenden Tabelle ist die Zuordnung der Datenbankversion zur Anzeigezeichenfolge dargestellt.</span><span class="sxs-lookup"><span data-stu-id="aef9a-113">The following table shows the mapping from database version to display string.</span></span>  
  
|<span data-ttu-id="aef9a-114">**Release**</span><span class="sxs-lookup"><span data-stu-id="aef9a-114">**Release**</span></span>|`Version`|<span data-ttu-id="aef9a-115">**Anzeige Name**</span><span class="sxs-lookup"><span data-stu-id="aef9a-115">**Display Name**</span></span>|  
|-----------------|-----------------|----------------------|  
|<span data-ttu-id="aef9a-116">RS 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="aef9a-116">RS 2005 SP2</span></span>|<span data-ttu-id="aef9a-117">@DBVersion = 'C.0.8.54'</span><span class="sxs-lookup"><span data-stu-id="aef9a-117">@DBVersion = 'C.0.8.54'</span></span>|<span data-ttu-id="aef9a-118">SQL Server 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="aef9a-118">SQL Server 2005 SP2</span></span>|  
|<span data-ttu-id="aef9a-119">RS 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="aef9a-119">RS 2005 SP1</span></span>|<span data-ttu-id="aef9a-120">@DBVersion = 'C.0.8.43'</span><span class="sxs-lookup"><span data-stu-id="aef9a-120">@DBVersion = 'C.0.8.43'</span></span>|<span data-ttu-id="aef9a-121">SQL Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="aef9a-121">SQL Server 2005 SP1</span></span>|  
|<span data-ttu-id="aef9a-122">RS 2005 RTM</span><span class="sxs-lookup"><span data-stu-id="aef9a-122">RS 2005 RTM</span></span>|<span data-ttu-id="aef9a-123">@DBVersion = 'C.0.8.40'</span><span class="sxs-lookup"><span data-stu-id="aef9a-123">@DBVersion = 'C.0.8.40'</span></span>|<span data-ttu-id="aef9a-124">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="aef9a-124">SQL Server 2005</span></span>|  
|<span data-ttu-id="aef9a-125">RS 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="aef9a-125">RS 2000 SP2</span></span>|<span data-ttu-id="aef9a-126">@DBVersion = 'C.0.6.54'</span><span class="sxs-lookup"><span data-stu-id="aef9a-126">@DBVersion = 'C.0.6.54'</span></span>|<span data-ttu-id="aef9a-127">SQL Server 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="aef9a-127">SQL Server 2000 SP2</span></span>|  
|<span data-ttu-id="aef9a-128">RS 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="aef9a-128">RS 2000 SP1</span></span>|<span data-ttu-id="aef9a-129">@DBVersion = 'C.0.6.51'</span><span class="sxs-lookup"><span data-stu-id="aef9a-129">@DBVersion = 'C.0.6.51'</span></span>|<span data-ttu-id="aef9a-130">SQL Server 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="aef9a-130">SQL Server 2000 SP1</span></span>|  
|<span data-ttu-id="aef9a-131">RS 2000 RTM</span><span class="sxs-lookup"><span data-stu-id="aef9a-131">RS 2000 RTM</span></span>|<span data-ttu-id="aef9a-132">@DBVersion = 'C.0.6.43'</span><span class="sxs-lookup"><span data-stu-id="aef9a-132">@DBVersion = 'C.0.6.43'</span></span>|<span data-ttu-id="aef9a-133">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="aef9a-133">SQL Server 2000</span></span>|  
|<span data-ttu-id="aef9a-134">Hotfix</span><span class="sxs-lookup"><span data-stu-id="aef9a-134">Hotfix</span></span>||<span data-ttu-id="aef9a-135">Nächste geeignete Version</span><span class="sxs-lookup"><span data-stu-id="aef9a-135">Closest applicable version</span></span>|  
  
 <span data-ttu-id="aef9a-136">Für eine *Version* vor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 wird HRESULT = ACT_E_BAD_VERSION zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aef9a-136">For a *Version* prior to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 an HRESULT of ACT_E_BAD_VERSION is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aef9a-137">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aef9a-137">Return Value</span></span>  
 <span data-ttu-id="aef9a-138">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aef9a-138">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="aef9a-139">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="aef9a-139">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="aef9a-140">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="aef9a-140">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef9a-141">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aef9a-141">Requirements</span></span>  
 <span data-ttu-id="aef9a-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aef9a-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef9a-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aef9a-143">See Also</span></span>  
 [<span data-ttu-id="aef9a-144">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="aef9a-144">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
