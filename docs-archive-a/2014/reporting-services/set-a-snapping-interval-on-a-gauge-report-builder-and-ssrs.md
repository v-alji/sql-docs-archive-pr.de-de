---
title: Festlegen eines Richtungs Intervalls auf einem Messgerät (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdc2a621c4406791838d97e93f47cd32fa9d5f94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719459"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="f9702-102">Festlegen eines Ausrichtungsintervalls auf einem Messgerät (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f9702-102">Set a Snapping Interval on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f9702-103">Durch das Ausrichtungsintervall wird das Vielfache festgelegt, auf das Werte gerundet werden.</span><span class="sxs-lookup"><span data-stu-id="f9702-103">A snapping interval defines the multiple to which values are rounded.</span></span> <span data-ttu-id="f9702-104">Standardmäßig zeigt das Messgerät auf den exakten Wert des Felds, das Sie im Datenbereich angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f9702-104">By default, the gauge will point to the exact value of the field you have specified in the data pane.</span></span> <span data-ttu-id="f9702-105">Eventuell möchten Sie jedoch, dass der exakte Wert nach oben oder unten gerundet wird, sodass der Zeiger an einem vordefinierten Intervall ausgerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="f9702-105">However, you may want to round the exact value up or down so that the pointer will snap to a preset interval.</span></span> <span data-ttu-id="f9702-106">Beispiel: Wenn der Wert auf dem Messgerät 34,2 beträgt und Sie ein Ausrichtungsintervall von 5 festlegen, zeigt der Messgerätzeiger auf 35.</span><span class="sxs-lookup"><span data-stu-id="f9702-106">For example, if the value on your gauge is 34.2 and you specify a snapping interval of 5, the gauge pointer will point to 35.</span></span> <span data-ttu-id="f9702-107">Wenn der Wert auf dem Messgerät 31,2 beträgt und Sie ein Ausrichtungsintervall von 5 festlegen, zeigt der Messgerätzeiger auf 30.</span><span class="sxs-lookup"><span data-stu-id="f9702-107">If the value on your gauge is 31.2 and you specify a snapping interval of 5, the gauge pointer will point to 30.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a><span data-ttu-id="f9702-108">So legen Sie ein Ausrichtungsintervall auf einem Messgerät fest</span><span class="sxs-lookup"><span data-stu-id="f9702-108">To set a snapping interval on a gauge</span></span>  
  
1.  <span data-ttu-id="f9702-109">Klicken Sie auf eine der Nummern des Messgeräts, um die Skala auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f9702-109">Click anywhere on the numbers of the gauge to highlight the scale.</span></span>  
  
2.  <span data-ttu-id="f9702-110">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f9702-110">Open the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f9702-111">Wenn der Bereich Eigenschaften nicht angezeigt wird, klicken Sie auf die Registerkarte **Ansicht** , und aktivieren Sie dann das Kontrollkästchen **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="f9702-111">If you do not see the Properties pane, click the **View** tab and then select the **Properties** checkbox.</span></span>  
  
3.  <span data-ttu-id="f9702-112">Klicken Sie in der Eigenschaft **Zeiger** auf die Schaltfläche (...).</span><span class="sxs-lookup"><span data-stu-id="f9702-112">In the **Pointers** property, click the (...) button.</span></span> <span data-ttu-id="f9702-113">Der Zeigerauflistungs-Editor wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f9702-113">The Pointer Collection Editor opens.</span></span>  
  
4.  <span data-ttu-id="f9702-114">Legen Sie die Eigenschaft **SnappingEnabled** auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="f9702-114">Set the **SnappingEnabled** property to `True`.</span></span>  
  
5.  <span data-ttu-id="f9702-115">Legen Sie das **SnappingInterval** auf einen Wert fest, der das Richtungs Intervall darstellt.</span><span class="sxs-lookup"><span data-stu-id="f9702-115">Set the **SnappingInterval** to a value that represents the snapping interval.</span></span> <span data-ttu-id="f9702-116">Der Zeiger wird am nächsten Rundungsvielfachen des angegebenen Werts ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="f9702-116">The pointer will be snapped to the nearest round multiple of the value that you have specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9702-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9702-117">See Also</span></span>  
 <span data-ttu-id="f9702-118">[Formatieren von Skalen auf einem Messgerät &#40;Berichts-Generator und SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f9702-118">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f9702-119">[Formatieren von Zeigern auf einem Messgerät &#40;Berichts-Generator und SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f9702-119">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f9702-120">Messgeräte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f9702-120">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
