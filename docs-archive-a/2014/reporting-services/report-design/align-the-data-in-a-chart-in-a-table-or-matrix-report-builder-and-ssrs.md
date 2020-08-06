---
title: Ausrichten von Daten in einem Diagramm, in einer Tabelle oder einer Matrix (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 75137575-d1bf-46d6-8527-5afc85eea5e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3e4278cd9f0dd5526770b43d2c6d94a8b87158cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621381"
---
# <a name="align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs"></a><span data-ttu-id="502a2-102">Ausrichten von Diagrammdaten in einer Tabelle oder einer Matrix (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="502a2-102">Align the Data in a Chart in a Table or Matrix (Report Builder and SSRS)</span></span>
  <span data-ttu-id="502a2-103">Sparklines und Datenbalken sind kleine, einfache Diagramme, die viel Information mit wenig relevanten Details vermitteln.</span><span class="sxs-lookup"><span data-stu-id="502a2-103">Sparklines and data bars are small, simple charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="502a2-104">Wenn Sie diese Option aktivieren, werden die Werte in den Sparklines und Datenbalken in den verschiedenen Zellen in der Tabelle oder Matrix ausgerichtet, auch wenn Sie nicht über alle Werte für die Daten verfügen, auf denen sie basieren.</span><span class="sxs-lookup"><span data-stu-id="502a2-104">When you check this option, the values in your sparklines and data bars will align across the different cells in the table or matrix, even if there are missing values in the data they are based on.</span></span>  
  
 <span data-ttu-id="502a2-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span><span class="sxs-lookup"><span data-stu-id="502a2-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span></span>  
  
 <span data-ttu-id="502a2-106">In diesem Bild wird das Säulendiagramm für die täglichen Verkäufe jedes Mitarbeiters dargestellt.</span><span class="sxs-lookup"><span data-stu-id="502a2-106">In this image, the column chart shows daily sales for each employee.</span></span> <span data-ttu-id="502a2-107">Beachten Sie, dass Tage, an denen ein Mitarbeiter keine Verkäufe getätigt hat, leer gelassen werden und die nachfolgenden Tage horizontal ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="502a2-107">Note that for days that an employee has no sales, the chart leaves a blank and aligns subsequent days horizontally.</span></span> <span data-ttu-id="502a2-108">Die Diagramme werden auch vertikal ausgerichtet, indem die Größen der unterschiedlichen Diagramme relativ zu einander festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="502a2-108">It also aligns the charts vertically by making the sizes of the different charts relative to each other.</span></span> <span data-ttu-id="502a2-109">Weitere Informationen finden Sie unter [Sparklines und Datenbalken &#40;Berichts-Generator und SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="502a2-109">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="align-the-data-in-a-sparkline-or-data-bar"></a><span data-ttu-id="502a2-110">Ausrichten der Daten in einer Sparkline oder einem Datenbalken</span><span class="sxs-lookup"><span data-stu-id="502a2-110">Align the data in a sparkline or data bar</span></span>  
  
1.  <span data-ttu-id="502a2-111">Klicken Sie in die Sparkline oder den Datenbalken, und klicken Sie dann auf **Eigenschaften für Horizontale Achsen** oder **Eigenschaften für vertikale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="502a2-111">Click in the sparkline or data bar, and then click **Horizontal Axis Properties** or **Vertical Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="502a2-112">Aktivieren Sie auf der Registerkarte **Achsenoptionen** das Kontrollkästchen **Achsen ausrichten in** , und wählen Sie dann im Dropdownfeld die Gruppe aus, in der die Achse ausgerichtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="502a2-112">On the **Axis Options** tab, check the **Align axes in** box, and then in the dropdown box, select the group on which to align the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="502a2-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="502a2-113">See Also</span></span>  
 <span data-ttu-id="502a2-114">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="502a2-114">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="502a2-115">Hinzufügen von Sparklines und Datenbalken &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="502a2-115">Add Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](add-sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
