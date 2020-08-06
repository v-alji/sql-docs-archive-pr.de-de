---
title: Hinzufügen oder Entfernen von Rändern aus einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d8bad99591964540bcd14fc5609560a3d324515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719594"
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="d8adf-102">Hinzufügen oder Entfernen von Rändern aus einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d8adf-102">Add or Remove Margins from a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d8adf-103">Bei Säulen- und Punktdiagrammen werden an den Enden der x-Achse automatisch Seitenränder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d8adf-103">In Column and Scatter chart types, the chart automatically adds side margins on the ends of the x-axis.</span></span> <span data-ttu-id="d8adf-104">Bei Balkendiagrammen werden an den Enden der x-Achse automatisch Seitenränder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d8adf-104">In Bar chart types, the chart automatically adds side margins on the ends of the y-axis.</span></span> <span data-ttu-id="d8adf-105">Bei allen anderen Diagrammtypen fügt das Diagramm keine Seitenränder hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8adf-105">In all other chart types, the chart does not add side margins.</span></span> <span data-ttu-id="d8adf-106">Die Größe der Seitenränder kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d8adf-106">You cannot change the size of the margin.</span></span>  
  
 <span data-ttu-id="d8adf-107">Dieses Thema gilt nicht für Kreis-, Ring-, Trichter- oder Pyramidendiagramme.</span><span class="sxs-lookup"><span data-stu-id="d8adf-107">This topic does not apply to pie, doughnut, funnel, or pyramid chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-or-disable-side-margins"></a><span data-ttu-id="d8adf-108">So aktivieren oder deaktivieren Sie Seitenränder</span><span class="sxs-lookup"><span data-stu-id="d8adf-108">To enable or disable side margins</span></span>  
  
1.  <span data-ttu-id="d8adf-109">Klicken Sie mit der rechten Maustaste auf die Achse, und wählen Sie **Achseneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="d8adf-109">Right-click the axis and select **Axis Properties**.</span></span> <span data-ttu-id="d8adf-110">Das Dialogfeld **Eigenschaften für vertikale Achsen** oder **Eigenschaften für horizontale Achsen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8adf-110">The **Vertical** or **HorizontalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d8adf-111">Legen Sie auf der Seite **Achsenoptionen** die Eigenschaft **Seitenränder** fest:</span><span class="sxs-lookup"><span data-stu-id="d8adf-111">On the **Axis Options** page, set the **Side margins** property:</span></span>  
  
    -   <span data-ttu-id="d8adf-112">**Automatisch:** Das Diagramm bestimmt basierend auf dem Diagrammtyp, ob ein Seitenrand hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d8adf-112">**Auto** The chart will determine whether to add a side margin based on the chart type.</span></span>  
  
    -   <span data-ttu-id="d8adf-113">**Deaktiviert:** Balken-, Säulen- und Punktdiagramme haben keine Seitenränder.</span><span class="sxs-lookup"><span data-stu-id="d8adf-113">**Disabled** Bar, column, and scatter charts will have no side margins.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8adf-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8adf-114">See Also</span></span>  
 <span data-ttu-id="d8adf-115">[Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8adf-115">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8adf-116">[Achseneigenschaften (Dialogfeld), Achsenoptionen (Berichts-Generator und SSRS)](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8adf-116">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8adf-117">[Angeben eines Achsenintervalls (Berichts-Generator und SSRS)](specify-an-axis-interval-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8adf-117">[Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8adf-118">[Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung (Berichts-Generator und SSRS)](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8adf-118">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d8adf-119">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d8adf-119">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
