---
title: Beginnen der Kreisdiagrammwerte an der Kreisoberseite (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0e6fb59-ca4e-4d70-97cb-0ad183da21d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed010eeaf3e4d581cce2f7242144c4f73ec2895b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608263"
---
# <a name="start-pie-chart-values-at-the-top-of-the-pie-report-builder-and-ssrs"></a><span data-ttu-id="dbb25-102">Beginnen der Kreisdiagrammwerte an der Kreisoberseite (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="dbb25-102">Start Pie Chart Values at the Top of the Pie (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dbb25-103">Standardmäßig beginnt bei Kreisdiagrammen der erste Wert im Dataset bei 90 Grad zur Oberseite des Kreises versetzt.</span><span class="sxs-lookup"><span data-stu-id="dbb25-103">By default in pie charts, the first value in the dataset starts at 90 degrees from the top of the pie.</span></span> <span data-ttu-id="dbb25-104">Möglicherweise ziehen Sie es vor, dass der erste Wert oben beginnt.</span><span class="sxs-lookup"><span data-stu-id="dbb25-104">You may prefer that the first value start from the top.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-start-the-pie-chart-at-the-top-of-the-pie"></a><span data-ttu-id="dbb25-105">So beginnen Sie das Kreisdiagramm an der Kreisoberseite</span><span class="sxs-lookup"><span data-stu-id="dbb25-105">To Start the Pie Chart at the Top of the Pie</span></span>  
  
1.  <span data-ttu-id="dbb25-106">Klicken Sie auf den Kreis selbst.</span><span class="sxs-lookup"><span data-stu-id="dbb25-106">Click the pie itself.</span></span>  
  
2.  <span data-ttu-id="dbb25-107">Zum Anzeigen des Bereichs **Eigenschaften** klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dbb25-107">If the **Properties** pane is not open, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="dbb25-108">Ändern Sie im Bereich **Eigenschaften** unter **benutzerdefinierte Attribute**den Wert für **PieStartAngle** von **0** in **270**.</span><span class="sxs-lookup"><span data-stu-id="dbb25-108">In the **Properties** pane, under **Custom Attributes**, change **PieStartAngle** from **0** to **270**.</span></span>  
  
4.  <span data-ttu-id="dbb25-109">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dbb25-109">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="dbb25-110">Der erste Wert beginnt jetzt an der Kreisdiagrammoberseite.</span><span class="sxs-lookup"><span data-stu-id="dbb25-110">The first value now starts at the top of the pie chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb25-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbb25-111">See Also</span></span>  
 <span data-ttu-id="dbb25-112">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dbb25-112">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dbb25-113">Kreisdiagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dbb25-113">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
