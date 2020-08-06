---
title: 'DatabaseLogonTimeout-Eigenschaft (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonTimeout property
ms.assetid: 4a65162c-33de-485e-8fd3-2bd6bff8bf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4920f5ef2282478f4d12a19b0806cf6ff9632cac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722341"
---
# <a name="databaselogontimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4f22c-102">DatabaseLogonTimeout-Eigenschaft (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="4f22c-102">DatabaseLogonTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4f22c-103">Gibt die Anzahl von Sekunden an, die gewartet wird, ehe ein Anmeldeversuch bei der Berichtsserver-Datenbank fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4f22c-103">Specifies the number of seconds to wait before an attempt to log on to the report server database fails.</span></span> <span data-ttu-id="4f22c-104">Der Wert **0** gibt einen unbegrenzten Wartezeitraum an.</span><span class="sxs-lookup"><span data-stu-id="4f22c-104">A value of **0** indicates an infinite wait time.</span></span> <span data-ttu-id="4f22c-105">Schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="4f22c-105">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f22c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f22c-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonTimeout As Int32  
```  
  
```csharp  
public Int32 DatabaseLogonTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="4f22c-107">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="4f22c-107">Property Values</span></span>  
 <span data-ttu-id="4f22c-108">Ein 32-Bit-Ganzzahlobjekt mit Vorzeichen, das die Anzahl der Sekunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="4f22c-108">A 32-bit signed integer object that represents the number of seconds.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="4f22c-109">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="4f22c-109">Example Code</span></span>  
 [<span data-ttu-id="4f22c-110">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="4f22c-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="4f22c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4f22c-111">Requirements</span></span>  
 <span data-ttu-id="4f22c-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f22c-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f22c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f22c-113">See Also</span></span>  
 [<span data-ttu-id="4f22c-114">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="4f22c-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
