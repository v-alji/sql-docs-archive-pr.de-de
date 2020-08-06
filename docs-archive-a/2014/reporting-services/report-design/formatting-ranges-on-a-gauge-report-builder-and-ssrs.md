---
title: Formatieren von Bereichen auf einem Messgerät (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ffdec8ca-3e95-41cd-850b-9e8c83be4b49
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29574c58eef6f18d685b48dd8d695a5fc42c3e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695366"
---
# <a name="formatting-ranges-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="d09fc-102">Formatieren von Bereichen auf einem Messgerät (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d09fc-102">Formatting Ranges on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d09fc-103">Ein Messbereich ist eine Zone oder ein Bereich auf der Messgerätskala, die oder der einen wichtigen Unterabschnitt von Werten auf dem Messgerät angibt.</span><span class="sxs-lookup"><span data-stu-id="d09fc-103">A gauge range is a zone or area on the gauge scale that indicates an important subsection of values on the gauge.</span></span> <span data-ttu-id="d09fc-104">Mit einem Messbereich können Sie grafisch angeben, wann der Zeigerwert in eine bestimmte Wertespanne eintritt.</span><span class="sxs-lookup"><span data-stu-id="d09fc-104">Using a gauge range, you can visually indicate when the pointer value has gone into a certain span of values.</span></span> <span data-ttu-id="d09fc-105">Messbereiche sind durch einen Startwert und einen Endwert definiert.</span><span class="sxs-lookup"><span data-stu-id="d09fc-105">Ranges are defined by a start value and an end value.</span></span>  
  
 <span data-ttu-id="d09fc-106">Mithilfe von Messbereichen können Sie auch unterschiedliche Abschnitte eines Messgeräts definieren.</span><span class="sxs-lookup"><span data-stu-id="d09fc-106">You can also use ranges to define different sections of a gauge.</span></span> <span data-ttu-id="d09fc-107">Auf einem Messgerät mit Werten von 0 bis 10 können Sie beispielsweise einen roten Messbereich mit Werten von 0 bis 3, einen gelben Messbereich mit Werten von 4 bis 7 und einen grünen Messbereich mit Werten von 8 bis 10 definieren.</span><span class="sxs-lookup"><span data-stu-id="d09fc-107">For example, on a gauge with values from 0 to 10, you can define a red range that has a value from 0 to 3, a yellow range that has a value from 4 to 7 and a green range that has a value from 8 to 10.</span></span> <span data-ttu-id="d09fc-108">Wenn der von Ihnen angegebene Startwert größer als der angegebene Endwert ist, werden die Werte ausgetauscht, sodass der Startwert als Endwert und der Endwert als Startwert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d09fc-108">If the start value that you specified is greater than the end value that you specified, the values are swapped so that the start value is the end value and the end value is the start value.</span></span>  
  
 <span data-ttu-id="d09fc-109">Sie können den Messbereich auf dieselbe Weise wie Zeiger auf einer Skala positionieren.</span><span class="sxs-lookup"><span data-stu-id="d09fc-109">You can position the range in the same way that you position pointers on a scale.</span></span> <span data-ttu-id="d09fc-110">Die Position des Messbereichs wird von den Eigenschaften **Position** und **Abstand von Skala** bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d09fc-110">The **Position** and **Distance from scale** properties determine the position of the range.</span></span> <span data-ttu-id="d09fc-111">Weitere Informationen finden Sie unter [Messgeräte &#40;Berichts-Generator und SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d09fc-111">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d09fc-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d09fc-112">See Also</span></span>  
 <span data-ttu-id="d09fc-113">[Formatieren von Skalen auf einem Messgerät &#40;Berichts-Generator und SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d09fc-113">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d09fc-114">[Formatieren von Zeigern auf einem Messgerät (Berichts-Generator und SSRS)](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d09fc-114">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d09fc-115">[Festlegen eines Mindestwerts oder eines Höchstwerts auf einem Messgerät (Berichts-Generator und SSRS)](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d09fc-115">[Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d09fc-116">[Tutorial: Hinzufügen eines KPI zu einem Bericht (Berichts-Generator)](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d09fc-116">[Tutorial: Adding a KPI to Your Report &#40;Report Builder&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="d09fc-117">Messgeräte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d09fc-117">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
