---
title: Hervorheben von Diagrammdaten durch Hinzufügen von Bereichsstreifen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: addd6137-4b6e-4e88-a7e8-9600fcd1ccce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01b0bb41a71daf9ac558ce8d8bb84480426870c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609641"
---
# <a name="highlight-chart-data-by-adding-strip-lines-report-builder-and-ssrs"></a><span data-ttu-id="0e8e6-102">Hervorheben von Diagrammdaten durch Hinzufügen von Bereichsstreifen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0e8e6-102">Highlight Chart Data by Adding Strip Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0e8e6-103">Bereichsstreifen oder Streifen sind horizontale oder vertikale Bereiche, die den Hintergrund des Diagramms in regelmäßigen oder benutzerdefinierten Abständen schattieren.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-103">Strip lines, or strips, are horizontal or vertical ranges that shade the background of the chart in regular or custom intervals.</span></span> <span data-ttu-id="0e8e6-104">Mithilfe von Bereichsstreifen können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="0e8e6-104">You can use strip lines to:</span></span>  
  
-   <span data-ttu-id="0e8e6-105">Die Lesbarkeit für das Suchen nach einzelnen Werten im Diagramm verbessern.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-105">Improve readability for looking up individual values on the chart.</span></span> <span data-ttu-id="0e8e6-106">Geben Sie in regelmäßigen Abständen Bereichsstreifen an, damit die verschiedenen Datenpunkte beim Lesen des Diagramms leichter erkennbar sind.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-106">Specify strip lines at regular intervals to help separate data points when reading the chart.</span></span>  
  
-   <span data-ttu-id="0e8e6-107">Termine hervorheben, die in regelmäßigen Abständen auftreten.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-107">Highlight dates that occur at regular intervals.</span></span> <span data-ttu-id="0e8e6-108">Beispielsweise können Sie in einem Verkaufsbericht Bereichsstreifen verwenden, um Wochenenddatenpunkte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-108">For example, in a sales report you might use strip lines to identify weekend data points.</span></span>  
  
-   <span data-ttu-id="0e8e6-109">Einen bestimmten Schlüsselbereich hervorheben.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-109">Highlight a specific key range.</span></span> <span data-ttu-id="0e8e6-110">Unter Verwendung des vorherigen Beispiels können Sie z. B. mithilfe eines Bereichsstreifens den höchsten Verkaufszahlenbereich hervorheben (80-100 €).</span><span class="sxs-lookup"><span data-stu-id="0e8e6-110">Using the previous example, you can use one strip line to highlight the highest range of sales that is between $80-100.</span></span>  
  
 <span data-ttu-id="0e8e6-111">Bereichsstreifen können auf die Diagrammtypen Form oder Polar nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-111">Strip lines are not applicable to Shape or Polar chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-interlaced-strip-lines-at-regular-intervals-on-a-chart"></a><span data-ttu-id="0e8e6-112">So zeigen Sie in einem Diagramm in regelmäßigen Abständen Zeilensprungstreifen an</span><span class="sxs-lookup"><span data-stu-id="0e8e6-112">To display interlaced strip lines at regular intervals on a chart</span></span>  
  
1.  <span data-ttu-id="0e8e6-113">Klicken Sie zum Anzeigen horizontaler Bereichsstreifen mit der rechten Maustaste auf die vertikale Diagrammachse, und klicken Sie auf **Eigenschaften für vertikale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-113">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="0e8e6-114">Klicken Sie zum Anzeigen vertikaler Bereichsstreifen mit der rechten Maustaste auf die horizontale Diagrammachse, und klicken Sie auf **Eigenschaften für horizontale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-114">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="0e8e6-115">Wählen Sie die Option **Zeilensprung verwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-115">Select the **Use interlacing** option.</span></span> <span data-ttu-id="0e8e6-116">Auf dem Diagramm werden graue Bereichsstreifen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-116">Grey strip lines will appear on your chart.</span></span>  
  
3.  <span data-ttu-id="0e8e6-117">(Optional) Geben Sie über die nebenstehende Dropdownliste **Farbe** eine Farbe für die Bereichsstreifen an.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-117">(Optional) Specify a color for the strip lines using the adjacent **Color** drop-down list.</span></span>  
  
### <a name="to-display-interlaced-strip-lines-at-custom-intervals-on-a-chart"></a><span data-ttu-id="0e8e6-118">So zeigen Sie in einem Diagramm in benutzerdefinierten Abständen Zeilensprungstreifen an</span><span class="sxs-lookup"><span data-stu-id="0e8e6-118">To display interlaced strip lines at custom intervals on a chart</span></span>  
  
1.  <span data-ttu-id="0e8e6-119">Klicken Sie zum Anzeigen horizontaler Bereichsstreifen mit der rechten Maustaste auf die vertikale Diagrammachse, und klicken Sie auf **Eigenschaften für vertikale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-119">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="0e8e6-120">Klicken Sie zum Anzeigen vertikaler Bereichsstreifen mit der rechten Maustaste auf die horizontale Diagrammachse, und klicken Sie auf **Eigenschaften für horizontale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-120">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
     <span data-ttu-id="0e8e6-121">Die Achseneigenschaften werden im Fenster "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-121">The axis properties are displayed in the Properties window.</span></span>  
  
2.  <span data-ttu-id="0e8e6-122">Klicken Sie im Abschnitt **Darstellung** des Eigenschaftenbereichs für die Eigenschaft StripLines auf die Schaltfläche „Edit Collection(...)“ (Sammlung bearbeiten), um den **ChartStripLine-Auflistungs-Editor** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-122">In the **Appearance** section of the Properties pane, for the StripLines property, click the Edit Collection (...) button to open the **ChartStripLine Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="0e8e6-123">Klicken Sie auf **Hinzufügen** , um der Auflistung einen neuen Bereichsstreifen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-123">Click **Add** to add a new strip line to the collection.</span></span>  
  
4.  <span data-ttu-id="0e8e6-124">Klicken Sie auf StripWidth, um die Breite des Bereichsstreifens anzugeben, der im Bericht in Zoll ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-124">Click StripWidth to specify the width of the strip line, measured in inches on the report.</span></span> <span data-ttu-id="0e8e6-125">Wenn Sie Datumsangaben oder Uhrzeiten hervorheben, klicken Sie auf StripWidthType, und wählen Sie ein Zeitintervall aus.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-125">If you are highlighting dates or times, click StripWidthType and select a time interval.</span></span>  
  
5.  <span data-ttu-id="0e8e6-126">Geben Sie einen Wert oder einen Ausdruck für das Intervall ein, um anzugeben, wie oft der Bereichsstreifen wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-126">Type a value or expression for the Interval to specify how often the strip line will repeat.</span></span>  <span data-ttu-id="0e8e6-127">Wenn Sie beispielsweise als Intervall 10 angeben und der Bereichsstreifen eine Stärke von 5 aufweist, werden bei den Werten 0 bis 5, 15 bis 20, 30 bis 35 usw. Bereichsstreifen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-127">For example, if you specify an interval of 10, and your strip line width is 5, strip lines will display at values of 0 to 5, 15 to 20, 30 to 35, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e8e6-128">Standardmäßig wird die Eigenschaft „Interval“ auf „Auto“ festgelegt. Das bedeutet, dass das Diagramm kein Intervall für benutzerdefinierte Bereichsstreifen berechnet.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-128">By default, Interval is set to Auto, which means the chart will not calculate an interval for custom strip lines.</span></span> <span data-ttu-id="0e8e6-129">Das Diagramm berechnet nur Intervalle für Bereichsstreifen, wenn ein Intervallwert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0e8e6-129">The chart only calculates intervals for strip lines if an interval value is set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8e6-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e8e6-130">See Also</span></span>  
 <span data-ttu-id="0e8e6-131">[Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0e8e6-131">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0e8e6-132">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0e8e6-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0e8e6-133">Hinzufügen eines gleitenden Durchschnitts zu einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e8e6-133">Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md)  
  
  
