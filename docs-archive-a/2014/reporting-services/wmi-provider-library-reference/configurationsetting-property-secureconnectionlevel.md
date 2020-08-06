---
title: 'SecureConnectionLevel-Eigenschaft (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SecureConnectionLevel
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SecureConnectionLevel property
ms.assetid: fd5549e7-b874-41e2-866e-2f58caf6f733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5d1b3bccc8a7fee3899fa21208d83a718a33f5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722317"
---
# <a name="secureconnectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9f04f-102">SecureConnectionLevel-Eigenschaft (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="9f04f-102">SecureConnectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9f04f-103">Gibt die in der Datei RSReportServer.config angegebene sichere Verbindungsebene zurück.</span><span class="sxs-lookup"><span data-stu-id="9f04f-103">Returns the secure connection level specified in the RSReportServer.config file.</span></span> <span data-ttu-id="9f04f-104">Schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="9f04f-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f04f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f04f-105">Syntax</span></span>  
  
```vb  
Public Dim SecureConnectionLevel As Integer  
```  
  
```csharp  
public Integer SecureConnectionLevel;  
```  
  
## <a name="property-values"></a><span data-ttu-id="9f04f-106">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="9f04f-106">Property Values</span></span>  
 <span data-ttu-id="9f04f-107">Ein `Integer`-Wert, der die sichere Verbindungsebene darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f04f-107">An `Integer` value that represents the secure connection level.</span></span> <span data-ttu-id="9f04f-108">Die Rückgabewerte geben an, dass SSL entweder konfiguriert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="9f04f-108">The return values indicate that the SSL is either configured or not.</span></span> <span data-ttu-id="9f04f-109">Ein Wert größer oder gleich 1 gibt an, dass SSL aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f04f-109">A value of greater than or equal to 1 indicates that SSL is turned on.</span></span> <span data-ttu-id="9f04f-110">Der Wert 0 gibt an, dass SSL deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9f04f-110">A value of 0 indicates that SSL is turned off.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="9f04f-111">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="9f04f-111">Example Code</span></span>  
 [<span data-ttu-id="9f04f-112">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="9f04f-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="9f04f-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9f04f-113">Requirements</span></span>  
 <span data-ttu-id="9f04f-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f04f-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f04f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f04f-115">See Also</span></span>  
 [<span data-ttu-id="9f04f-116">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="9f04f-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
