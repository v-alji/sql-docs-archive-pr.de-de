---
title: Ausblenden von Legendenelementen im Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92256240-0cd5-4be4-8904-d1e3b93cb6b3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20444432f580ffaf1c5f4de1320b06319f973a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621358"
---
# <a name="hide-legend-items-on-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="6aec3-102">Ausblenden von Legendenelementen im Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6aec3-102">Hide Legend Items on the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6aec3-103">Standardmäßig werden alle einem Nicht-Formdiagramm hinzugefügten Reihen in der Legende als Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6aec3-103">By default, any series added to a non-Shape chart will be added as an item in the legend.</span></span> <span data-ttu-id="6aec3-104">Für Kreis-, Ring-, Trichter- und Pyramidendiagramme werden für alle dem Diagramm hinzugefügten Reihen der Legende einzelne Datenpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6aec3-104">For pie, doughnut, funnel, and pyramid charts, any series added to the chart will add individual data points in the legend.</span></span>  
  
 <span data-ttu-id="6aec3-105">Sie können in der Legende beliebige Elemente ausblenden.</span><span class="sxs-lookup"><span data-stu-id="6aec3-105">You can hide any item on the legend.</span></span> <span data-ttu-id="6aec3-106">Wenn Sie ein Legendenelement ausblenden, wird dieses immer noch im Diagramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6aec3-106">When you hide a legend item, it will still appear in the chart.</span></span> <span data-ttu-id="6aec3-107">Dies ist hilfreich in Situationen, in denen für eine dem Diagramm hinzugefügte Reihe keine weiteren Informationen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6aec3-107">This is useful in situations where you do not want to show more information for a series that is added to the chart.</span></span> <span data-ttu-id="6aec3-108">Wenn Sie dem Diagramm beispielsweise eine berechnete Reihe (z. B. einen gleitenden Durchschnitt) hinzugefügt haben, empfiehlt es sich u. U., diesen Eintrag in der Legende auszublenden, sodass nur für die ursprüngliche Reihe weitere Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6aec3-108">For example, if you have added a calculated series like a moving average to the chart, you may want to hide this entry in the legend so that more information is only shown for the original series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-an-item-from-display-in-the-legend"></a><span data-ttu-id="6aec3-109">So blenden Sie ein in der Legende angezeigtes Element aus</span><span class="sxs-lookup"><span data-stu-id="6aec3-109">To hide an item from display in the legend</span></span>  
  
1.  <span data-ttu-id="6aec3-110">Klicken Sie mit der rechten Maustaste auf die auszublendende Reihe, und wählen Sie die Option **Reiheneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="6aec3-110">Right-click on the series you want to hide and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="6aec3-111">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="6aec3-111">Click **Legend**.</span></span> <span data-ttu-id="6aec3-112">Aktivieren Sie die Option **Diese Reihe in Legende nicht anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="6aec3-112">Select the **Do not show this series in a legend** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6aec3-113">Eine Reihe kann nicht für eine Gruppe ausgeblendet und für andere angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6aec3-113">You cannot hide a series for one group and not for the others.</span></span> <span data-ttu-id="6aec3-114">Wenn Sie dem Bereich **Reihengruppen** ein Feld hinzugefügt haben, werden alle zu dieser Gruppe gehörenden Reihen ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="6aec3-114">If you have added a field to the **Series Groups** area, all series belonging to this group will be hidden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aec3-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6aec3-115">See Also</span></span>  
 <span data-ttu-id="6aec3-116">[Formatieren der Legende in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6aec3-116">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="6aec3-117">[Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6aec3-117">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6aec3-118">[Ändern des Texts eines Legendenelements (Berichts-Generator und SSRS)](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6aec3-118">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="6aec3-119">[Hinzufügen eines gleitenden Durchschnitts zu einem Diagramm (Berichts-Generator und SSRS)](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6aec3-119">[Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6aec3-120">Legendeneigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6aec3-120">Legend Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../legend-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
