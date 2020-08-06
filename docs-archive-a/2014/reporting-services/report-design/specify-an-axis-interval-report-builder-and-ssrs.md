---
title: Angeben eines Achsenintervalls (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46712d-a5bf-44c0-9929-e30ccc1e7e33
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b64b824933753a8482360f193ca4ccf71e8d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608270"
---
# <a name="specify-an-axis-interval-report-builder-and-ssrs"></a><span data-ttu-id="f2180-102">Angeben eines Achsenintervalls (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f2180-102">Specify an Axis Interval (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f2180-103">Das Achsenintervall definiert die Anzahl von Bezeichnungen und zugehörigen Teilstrichen auf einer Achse.</span><span class="sxs-lookup"><span data-stu-id="f2180-103">The axis interval defines the number of labels and accompanying tick marks on an axis.</span></span> <span data-ttu-id="f2180-104">Auf der Wertachse stellen die Achsenintervalle ein konsistentes Maß für die Datenpunkte im Diagramm bereit.</span><span class="sxs-lookup"><span data-stu-id="f2180-104">On the value axis, axis intervals provide a consistent measure of the data points on the chart.</span></span> <span data-ttu-id="f2180-105">Auf der Kategorieachse kann diese Funktion jedoch bewirken, dass Kategorien ohne Achsenbezeichnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f2180-105">However, on the category axis, this functionality can cause categories to appear without axis labels.</span></span> <span data-ttu-id="f2180-106">Sie können die Anzahl der Intervalle in der Interval-Eigenschaft der Achse festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2180-106">You can specify the number of intervals you want in the axis Interval property.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="f2180-107">berechnet die Anzahl der Intervalle zur Laufzeit basierend auf den Daten im Resultset.</span><span class="sxs-lookup"><span data-stu-id="f2180-107">calculates the number of intervals at run time, based on the data in the result set.</span></span> <span data-ttu-id="f2180-108">Weitere Informationen zum Berechnen von Achsenintervallen finden Sie unter [Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f2180-108">For more information about how axis intervals are calculated, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f2180-109">Dieses Thema gilt nicht für Datums- oder Zeitwerte auf der Kategorieachse.</span><span class="sxs-lookup"><span data-stu-id="f2180-109">This topic is not applicable for date or time values on the category axis.</span></span> <span data-ttu-id="f2180-110">Standardmäßig werden `DateTime`-Werte als Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2180-110">Be default, `DateTime` values appear as days.</span></span> <span data-ttu-id="f2180-111">Wenn Sie ein anderes Datums- oder Zeitintervall angeben möchten, z. B. ein Monats- oder Zeitintervall, müssen Sie die Achsenbezeichnungen formatieren und die Achse auf die Anzeige von Instanzen von `DateTime`-Typen statt von `String`-Typen festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2180-111">To specify a different date or time interval, such as a month or time interval, you must format the axis labels and set the axis to display instances of `DateTime` types instead of `String` types.</span></span> <span data-ttu-id="f2180-112">Darüber hinaus müssen Sie die Interval-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2180-112">In addition, you must set the Interval property.</span></span> <span data-ttu-id="f2180-113">Weitere Informationen finden Sie unter [Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung &#40;Berichts-Generator und SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f2180-113">For more information, see [Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f2180-114">Dieses Thema gilt nicht für Kreis-, Ring-, Trichter- oder Pyramidendiagramme, die keine Achsen haben.</span><span class="sxs-lookup"><span data-stu-id="f2180-114">This topic does not apply to pie, doughnut, funnel or pyramid charts, which do not have axes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2180-115">Die Kategorieachse ist normalerweise die horizontale Achse oder x-Achse.</span><span class="sxs-lookup"><span data-stu-id="f2180-115">The category axis is usually the horizontal or x-axis.</span></span> <span data-ttu-id="f2180-116">Bei Balkendiagrammen ist die Kategorieachse jedoch die vertikale Achse oder y-Achse.</span><span class="sxs-lookup"><span data-stu-id="f2180-116">However, for bar charts, the category axis is the vertical or y-axis.</span></span>  
  
 <span data-ttu-id="f2180-117">Ein Beispiel für ein Diagramm, in dem andere Achsenintervalle angegeben werden, ist als Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2180-117">An example of a chart specifying different axis intervals is available as a sample report.</span></span> <span data-ttu-id="f2180-118">Weitere Informationen zum Herunterladen des Beispielberichts und anderer Berichte finden Sie unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Beispielberichte zu Berichts-Generator und Berichts-Designer](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="f2180-118">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-show-all-category-labels-on-the-x-axis"></a><span data-ttu-id="f2180-119">So zeigen Sie alle Kategoriebezeichnungen auf der X-Achse an</span><span class="sxs-lookup"><span data-stu-id="f2180-119">To show all category labels on the x-axis</span></span>  
  
1.  <span data-ttu-id="f2180-120">Klicken Sie mit der rechten Maustaste auf die Kategorieachse, und klicken Sie auf **Achseneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f2180-120">Right-click the category axis and click **Axis Properties**.</span></span> <span data-ttu-id="f2180-121">Das Dialogfeld **Achseneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2180-121">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f2180-122">Legen Sie unter **Achsen Optionen** `Interval` auf **1**fest.</span><span class="sxs-lookup"><span data-stu-id="f2180-122">In **Axis Options**, set `Interval` to **1**.</span></span> <span data-ttu-id="f2180-123">Jede Kategoriegruppenbezeichnung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2180-123">Every category group label is displayed.</span></span> <span data-ttu-id="f2180-124">Wenn Sie jede zweite Kategoriegruppenbezeichnung auf der X-Achse anzeigen möchten, geben Sie **2**ein.</span><span class="sxs-lookup"><span data-stu-id="f2180-124">If you want to show every other category group label on the x-axis, type **2**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2180-125">Wenn ein Achsenintervall festgelegt wird, wird die automatische Kennzeichnung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2180-125">When an axis interval is set, all automatic labeling is disabled.</span></span> <span data-ttu-id="f2180-126">Wenn Sie einen Wert für das Achsenintervall angeben, kann es je nach Anzahl der Kategorien auf der Kategorieachse zu unerwartetem Kennzeichnungsverhalten kommen.</span><span class="sxs-lookup"><span data-stu-id="f2180-126">If you specify a value for the axis interval, you may experience unpredictable labeling behavior depending on how many categories are on the category axis.</span></span>  
  
### <a name="to-enable-a-variable-interval-calculation-on-an-axis"></a><span data-ttu-id="f2180-127">So aktivieren Sie eine variable Intervallberechnung auf einer Achse</span><span class="sxs-lookup"><span data-stu-id="f2180-127">To enable a variable interval calculation on an axis</span></span>  
  
1.  <span data-ttu-id="f2180-128">Klicken Sie mit der rechten Maustaste auf die Diagrammachse, die Sie ändern möchten, und klicken Sie dann auf **Achseneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f2180-128">Right-click the chart axis that you want to change, and then click **Axis Properties**.</span></span> <span data-ttu-id="f2180-129">Das Dialogfeld **Achseneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2180-129">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f2180-130">Legen Sie unter **Achsen Optionen die Option** `Interval` auf **automatisch**fest. Im Diagramm wird die optimale Anzahl von Kategoriebezeichnungen angezeigt, die auf die Achse passen.</span><span class="sxs-lookup"><span data-stu-id="f2180-130">In **Axis Options**, set `Interval` to **Auto**. The chart will display the optimal number of category labels that can fit along the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2180-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2180-131">See Also</span></span>  
 <span data-ttu-id="f2180-132">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2180-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2180-133">[Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2180-133">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2180-134">[Sortieren von Daten in einem Datenbereich &#40;Berichts-Generator und SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2180-134">[Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2180-135">[Achsen Eigenschaften (Dialog Feld), Achsen Optionen &#40;Berichts-Generator und SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2180-135">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2180-136">[Geben Sie eine logarithmische Skalierung &#40;Berichts-Generator und SSRS an&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2180-136">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f2180-137">Zeichnen von Daten auf einer sekundären Achse (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f2180-137">Plot Data on a Secondary Axis &#40;Report Builder and SSRS&#41;</span></span>](plot-data-on-a-secondary-axis-report-builder-and-ssrs.md)  
  
  
