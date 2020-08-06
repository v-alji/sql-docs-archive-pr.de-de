---
title: ListInstalledSharePointVersions-Methode (WMI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListInstalledSharePointVersions method
ms.assetid: 8f0a5e9f-23f1-41e5-9a90-dfec19ef1df7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ceee23876461cf31cbd265ea39ae015ddcbc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616912"
---
# <a name="listinstalledsharepointversions-method-wmi"></a><span data-ttu-id="3ad5f-102">ListInstalledSharePointVersions-Methode (WMI)</span><span class="sxs-lookup"><span data-stu-id="3ad5f-102">ListInstalledSharePointVersions Method (WMI)</span></span>
  <span data-ttu-id="3ad5f-103">Gibt einen Satz von Token zurück, die die Versionen von Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]oder [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] darstellen, die auf dem gleichen Computer wie der Berichtsserver installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-103">Returns a set of tokens that represent the versions of Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] that are installed on the same computer as the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ad5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ad5f-104">Syntax</span></span>  
  
```vb  
Public Sub ListInstalledSharePointVersions(ByRef VersionTokens() _  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] VersionTokens,   
    out Int32 Length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ad5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ad5f-105">Parameters</span></span>  
 <span data-ttu-id="3ad5f-106">*VersionTokens[]*</span><span class="sxs-lookup"><span data-stu-id="3ad5f-106">*VersionTokens[]*</span></span>  
 <span data-ttu-id="3ad5f-107">[out] Ein Array, das die Token enthält, welche die Version eines SharePoint-Produkts oder der SharePoint-Technologie darstellen, die mit dem installierten Berichtsserver kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="3ad5f-107">[out] An array that contains the tokens that represent the version of a SharePoint product or technology that is compatible with the installed report server.</span></span>  
  
 <span data-ttu-id="3ad5f-108">*Länge*</span><span class="sxs-lookup"><span data-stu-id="3ad5f-108">*Length*</span></span>  
 <span data-ttu-id="3ad5f-109">[out] Die Länge des Arrays von Versionstoken</span><span class="sxs-lookup"><span data-stu-id="3ad5f-109">[out] The length of the version tokens array.</span></span>  
  
 <span data-ttu-id="3ad5f-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="3ad5f-110">*HRESULT*</span></span>  
 <span data-ttu-id="3ad5f-111">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ad5f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ad5f-112">Return Value</span></span>  
 <span data-ttu-id="3ad5f-113">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="3ad5f-114">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="3ad5f-115">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ad5f-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3ad5f-116">Remarks</span></span>  
 <span data-ttu-id="3ad5f-117">Jedes Token, das zurückgegeben wird, stellt eine Version von [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] oder [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] dar, die mit dem derzeit installierten Berichtsserver kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-117">Each token that is returned represents a version of [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] or [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] that is compatible with the currently installed report server.</span></span> <span data-ttu-id="3ad5f-118">Wenn eine bestimmte Version von SharePoint kompatibel mit früheren Versionen von SharePoint ist, werden Token für jede kompatible Version von SharePoint zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-118">If a particular version of SharePoint is compatible with previous SharePoint versions, tokens for each compatible SharePoint version are returned.</span></span>  
  
 <span data-ttu-id="3ad5f-119">Die folgende Tabelle enthält die SharePoint-Token, die zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-119">The following is a table of the SharePoint tokens that are returned.</span></span>  
  
|<span data-ttu-id="3ad5f-120">**Versionstoken**</span><span class="sxs-lookup"><span data-stu-id="3ad5f-120">**Version Tokens**</span></span>|<span data-ttu-id="3ad5f-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3ad5f-121">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="3ad5f-122">WSS_V2_Compatible</span><span class="sxs-lookup"><span data-stu-id="3ad5f-122">WSS_V2_Compatible</span></span>|<span data-ttu-id="3ad5f-123">Es ist eine [!INCLUDE[winSPServ](../../includes/winspserv-md.md)]-, [!INCLUDE[winSPServ](../../includes/winspserv-md.md)]-, [!INCLUDE[offSPServ](../../includes/offspserv-md.md)]-, [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]- oder [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] -Installation vorhanden, die mit [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-123">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span></span>|  
|<span data-ttu-id="3ad5f-124">WSS_V3_Compatible</span><span class="sxs-lookup"><span data-stu-id="3ad5f-124">WSS_V3_Compatible</span></span>|<span data-ttu-id="3ad5f-125">Es ist eine [!INCLUDE[winSPServ](../../includes/winspserv-md.md)]-, [!INCLUDE[winSPServ](../../includes/winspserv-md.md)]-, [!INCLUDE[offSPServ](../../includes/offspserv-md.md)]-, [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]- oder [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] -Installation vorhanden, die mit [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-125">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span></span>|  
|<span data-ttu-id="3ad5f-126">WSS_V4_Compatible</span><span class="sxs-lookup"><span data-stu-id="3ad5f-126">WSS_V4_Compatible</span></span>|<span data-ttu-id="3ad5f-127">Es ist eine [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] - oder [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] -Installation vorhanden, die mit Office 14 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="3ad5f-127">A [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with Office 14.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ad5f-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ad5f-128">Requirements</span></span>  
 <span data-ttu-id="3ad5f-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ad5f-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad5f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ad5f-130">See Also</span></span>  
 [<span data-ttu-id="3ad5f-131">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="3ad5f-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
