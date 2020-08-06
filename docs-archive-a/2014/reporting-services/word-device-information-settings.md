---
title: Geräteinformationseinstellungen für Word | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Word [Reporting Services]
- device information settings [Reporting Services], Word
ms.assetid: 28146498-fae7-4b13-b47f-6ec05aa8e057
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ddd145c5073003a8dc189e3ed9b1bbb25dc11d09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608258"
---
# <a name="word-device-information-settings"></a><span data-ttu-id="a4bd3-102">Geräteinformationseinstellungen für Word</span><span class="sxs-lookup"><span data-stu-id="a4bd3-102">Word Device Information Settings</span></span>
  <span data-ttu-id="a4bd3-103">In der folgenden Tabelle werden die Geräteinformationseinstellungen zum Rendern in das Format [!INCLUDE[ofprword](../includes/ofprword-md.md)] aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprword](../includes/ofprword-md.md)] format.</span></span>  
  
|<span data-ttu-id="a4bd3-104">Einstellung</span><span class="sxs-lookup"><span data-stu-id="a4bd3-104">Setting</span></span>|<span data-ttu-id="a4bd3-105">value</span><span class="sxs-lookup"><span data-stu-id="a4bd3-105">Value</span></span>|  
|-------------|-----------|  
|`AutoFit`|<span data-ttu-id="a4bd3-106">`False`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-106">`False`.</span></span> <span data-ttu-id="a4bd3-107">AutoAnpassen wird in jeder Word-Tabelle auf `false` eingestellt.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-107">AutoFit is set to `false` set on any Word table.</span></span><br /><br /> <span data-ttu-id="a4bd3-108">`True`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-108">`True`.</span></span> <span data-ttu-id="a4bd3-109">AutoFit ist für jede Word-Tabelle auf festgelegt `true` .</span><span class="sxs-lookup"><span data-stu-id="a4bd3-109">AutoFit is set to `true` on every Word table.</span></span><br /><br /> <span data-ttu-id="a4bd3-110">`Never`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-110">`Never`.</span></span> <span data-ttu-id="a4bd3-111">Die Werte für AutoAnpassen sind in keiner Word-Tabelle festgelegt, und der Word-Standardwert wird wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-111">AutoFit values are not set on any Word table and behavior reverts to the Word default.</span></span><br /><br /> <span data-ttu-id="a4bd3-112">`Default`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-112">`Default`.</span></span> <span data-ttu-id="a4bd3-113">AutoAnpassen wird in den Tabellen eingestellt, die enger als der physische Zeichenbereich (physische Seitenbreite ohne Ränder) pro logischer Seite sind.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-113">AutoFit is set on tables that are narrower than the physical drawing area (physical page width excluding margins) per logical page.</span></span>|  
|`ExpandToggles`|<span data-ttu-id="a4bd3-114">Gibt an, ob alle Elemente, die aus- und eingeschaltet werden können, in ihrem voll erweiterten Status gerendert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-114">Indicates whether all items that can be toggled should render in their fully-expanded state.</span></span> <span data-ttu-id="a4bd3-115">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-115">The default value is `false`.</span></span>|  
|`FixedPageWidth`|<span data-ttu-id="a4bd3-116">Gibt an, ob die in die DOC-Datei geschriebene Seitenbreite erhöht wird, damit die Breite der größten Seite im Hauptteil des Berichts hineinpasst.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-116">Indicates whether the Page Width written to the DOC file will grow to accommodate the width of the largest page in the Report Body.</span></span> <span data-ttu-id="a4bd3-117">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-117">The default value is `false`.</span></span>|  
|<span data-ttu-id="a4bd3-118">**OmitHyperlinks**</span><span class="sxs-lookup"><span data-stu-id="a4bd3-118">**OmitHyperlinks**</span></span>|<span data-ttu-id="a4bd3-119">Gibt an, ob die Linkaktion auf allen Elementen weggelassen werden soll, wo sie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-119">Indicates whether to omit the Hyperlink action on all items where it is set.</span></span> <span data-ttu-id="a4bd3-120">Der Standardwert ist `false`</span><span class="sxs-lookup"><span data-stu-id="a4bd3-120">The default value is `false`</span></span>|  
|`OmitDrillthroughs`|<span data-ttu-id="a4bd3-121">Gibt an, ob die Drillthrough-Aktion auf allen Elementen weggelassen werden soll, wo sie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a4bd3-121">Indicates whether to omit the Drillthrough action on all items where it is set.</span></span> <span data-ttu-id="a4bd3-122">Der Standardwert ist `false`</span><span class="sxs-lookup"><span data-stu-id="a4bd3-122">The default value is `false`</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4bd3-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4bd3-123">See Also</span></span>  
 <span data-ttu-id="a4bd3-124">[Übergeben von Geräte Informationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a4bd3-124">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="a4bd3-125">[Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="a4bd3-125">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="a4bd3-126">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="a4bd3-126">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
