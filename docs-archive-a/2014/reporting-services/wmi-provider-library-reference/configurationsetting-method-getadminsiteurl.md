---
title: GetAdminSiteUrl-Methode (WMI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetAdminSiteUrl method
ms.assetid: fbc5bf3c-120c-4aec-a4f2-f5391bd415f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cae1a6f7e363ddce8c47c00eb5ef25fc832e59c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616914"
---
# <a name="getadminsiteurl-method-wmi"></a><span data-ttu-id="c3ac6-102">GetAdminSiteUrl-Methode (WMI)</span><span class="sxs-lookup"><span data-stu-id="c3ac6-102">GetAdminSiteUrl Method (WMI)</span></span>
  <span data-ttu-id="c3ac6-103">Ruft die absolute URL für die Zentraladministrationswebsite für die Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)]-, [!INCLUDE[offSPServ](../../includes/offspserv-md.md)]-, [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]- oder [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] -Farm ab, in die der Berichtsserver integriert ist</span><span class="sxs-lookup"><span data-stu-id="c3ac6-103">Gets the absolute URL for the Central Administration Web site for the Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] farm that the report server is integrated with.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ac6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3ac6-104">Syntax</span></span>  
  
```vb  
Public Sub GetAdminSiteUrl(ByRef AdminSiteUrl as String, _  
ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GetAdminSiteUrl(out string AdminSiteUrl, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ac6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3ac6-105">Parameters</span></span>  
 <span data-ttu-id="c3ac6-106">*AdminSiteUrl*</span><span class="sxs-lookup"><span data-stu-id="c3ac6-106">*AdminSiteUrl*</span></span>  
 <span data-ttu-id="c3ac6-107">[out] Eine Zeichenfolge, die die absolute URL für die Zentraladministrationswebsite für die SharePoint-Farm enthält, in die der Berichtsserver integriert ist.</span><span class="sxs-lookup"><span data-stu-id="c3ac6-107">[out] A string that contains the absolute URL for the Central Administration Web site for the SharePoint farm that the report server is integrated with.</span></span>  
  
 <span data-ttu-id="c3ac6-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c3ac6-108">*HRESULT*</span></span>  
 <span data-ttu-id="c3ac6-109">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="c3ac6-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3ac6-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c3ac6-110">Return Value</span></span>  
 <span data-ttu-id="c3ac6-111">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c3ac6-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="c3ac6-112">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c3ac6-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="c3ac6-113">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c3ac6-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ac6-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3ac6-114">Requirements</span></span>  
 <span data-ttu-id="c3ac6-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ac6-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ac6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3ac6-116">See Also</span></span>  
 [<span data-ttu-id="c3ac6-117">MSReportServer_ConfigurationSetting Methods (MSReportServer_ConfigurationSetting-Methoden)</span><span class="sxs-lookup"><span data-stu-id="c3ac6-117">MSReportServer_ConfigurationSetting Methods</span></span>](msreportserver-configurationsetting-methods.md)  
  
  
