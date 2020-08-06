---
title: 'IsSharePointIntegrated-Eigenschaft (WMI: MSReportServer_Instance) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: e21d00ad-5d9a-4290-8d74-7eeeda39e1ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0c92ebe586d37053b47f90ca98c31b3068a7b91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616894"
---
# <a name="issharepointintegrated-property-wmi-msreportserver_instance"></a><span data-ttu-id="a0bcb-102">IsSharePointIntegrated-Eigenschaft (WMI: MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="a0bcb-102">IsSharePointIntegrated Property (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="a0bcb-103">Gibt an, ob sich der Berichtsserver im integrierten SharePoint-Modus befindet</span><span class="sxs-lookup"><span data-stu-id="a0bcb-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="a0bcb-104">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] gibt diese Eigenschaft immer `False` zurück, da [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Instanzen im SharePoint-Modus freigegebene Dienste darstellen und nicht von WMI-Anbietern kontrolliert werden.</span><span class="sxs-lookup"><span data-stu-id="a0bcb-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0bcb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0bcb-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="a0bcb-106">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="a0bcb-106">Property Values</span></span>  
 <span data-ttu-id="a0bcb-107">Ein `Boolean`-Wert, der angibt, ob sich der Berichtsserver im integrierten SharePoint-Modus befindet</span><span class="sxs-lookup"><span data-stu-id="a0bcb-107">A `Boolean` value that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0bcb-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0bcb-108">Requirements</span></span>  
 <span data-ttu-id="a0bcb-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0bcb-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bcb-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0bcb-110">See Also</span></span>  
 <span data-ttu-id="a0bcb-111">[MSReportServer_Instance-Member](msreportserver-instance-members.md) </span><span class="sxs-lookup"><span data-stu-id="a0bcb-111">[MSReportServer_Instance Members](msreportserver-instance-members.md) </span></span>  
 [<span data-ttu-id="a0bcb-112">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="a0bcb-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
  
