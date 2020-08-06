---
title: IsSharePointIntegrated-Eigenschaft (WMI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a1f3f38c23546ddf4dfb52c2a3af7c122af10cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620199"
---
# <a name="issharepointintegrated-property-wmi"></a><span data-ttu-id="b877f-102">IsSharePointIntegrated-Eigenschaft (WMI)</span><span class="sxs-lookup"><span data-stu-id="b877f-102">IsSharePointIntegrated Property (WMI)</span></span>
  <span data-ttu-id="b877f-103">Gibt an, ob sich der Berichtsserver im integrierten SharePoint-Modus befindet</span><span class="sxs-lookup"><span data-stu-id="b877f-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="b877f-104">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] gibt diese Eigenschaft immer `False` zurück, da [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Instanzen im SharePoint-Modus freigegebene Dienste darstellen und nicht von WMI-Anbietern kontrolliert werden.</span><span class="sxs-lookup"><span data-stu-id="b877f-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b877f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b877f-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="b877f-106">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="b877f-106">Property Values</span></span>  
 <span data-ttu-id="b877f-107">Ein `Boolean`-Objekt, das angibt, ob sich der Berichtsserver im integrierten SharePoint-Modus befindet</span><span class="sxs-lookup"><span data-stu-id="b877f-107">A `Boolean` object that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="b877f-108">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="b877f-108">Example Code</span></span>  
 [<span data-ttu-id="b877f-109">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="b877f-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="b877f-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b877f-110">Requirements</span></span>  
 <span data-ttu-id="b877f-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b877f-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b877f-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b877f-112">See Also</span></span>  
 [<span data-ttu-id="b877f-113">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="b877f-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
