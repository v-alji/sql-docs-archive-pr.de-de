---
title: Geräteinformationseinstellungen für Excel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719612"
---
# <a name="excel-device-information-settings"></a><span data-ttu-id="a3b58-102">Geräteinformationseinstellungen für Excel</span><span class="sxs-lookup"><span data-stu-id="a3b58-102">Excel Device Information Settings</span></span>
  <span data-ttu-id="a3b58-103">In der folgenden Tabelle werden die Geräteinformationseinstellungen zum Rendern in das Format [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3b58-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] format.</span></span>  
  
|<span data-ttu-id="a3b58-104">Einstellung</span><span class="sxs-lookup"><span data-stu-id="a3b58-104">Setting</span></span>|<span data-ttu-id="a3b58-105">value</span><span class="sxs-lookup"><span data-stu-id="a3b58-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="a3b58-106">**OmitDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="a3b58-106">**OmitDocumentMap**</span></span>|<span data-ttu-id="a3b58-107">Gibt an, ob die Dokumentstruktur für Berichte weggelassen werden soll, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a3b58-107">Indicates whether to omit the document map for reports that support it.</span></span> <span data-ttu-id="a3b58-108">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="a3b58-108">The default value is `false`.</span></span>|  
|<span data-ttu-id="a3b58-109">**OmitFormulas**</span><span class="sxs-lookup"><span data-stu-id="a3b58-109">**OmitFormulas**</span></span>|<span data-ttu-id="a3b58-110">Gibt an, ob Formeln aus dem gerenderten Bericht weggelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a3b58-110">Indicates whether to omit formulas from the rendered report.</span></span> <span data-ttu-id="a3b58-111">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="a3b58-111">The default value is `false`.</span></span>|  
|<span data-ttu-id="a3b58-112">`SimplePageHeade`rs</span><span class="sxs-lookup"><span data-stu-id="a3b58-112">`SimplePageHeade`rs</span></span>|<span data-ttu-id="a3b58-113">Gibt an, ob der Seitenkopf des Berichts in den Excel-Seitenkopf gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="a3b58-113">Indicates whether the page header of the report is rendered to the Excel page header.</span></span> <span data-ttu-id="a3b58-114">Der Wert `false` gibt an, dass der Seitenkopf in die erste Zeile des Arbeitsblatts gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="a3b58-114">A value of `false` indicates that the page header is rendered to the first row of the worksheet.</span></span> <span data-ttu-id="a3b58-115">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="a3b58-115">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3b58-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3b58-116">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="a3b58-117">[Übergeben von Geräte Informationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a3b58-117">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="a3b58-118">[Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="a3b58-118">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="a3b58-119">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="a3b58-119">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
