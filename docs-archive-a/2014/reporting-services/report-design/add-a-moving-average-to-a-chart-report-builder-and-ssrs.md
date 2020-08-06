---
title: Hinzufügen eines gleitenden Durchschnitts zu einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bc16d0cb45a3240148f931009a836c231b442b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608298"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="3e530-102">Hinzufügen eines gleitenden Durchschnitts zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="3e530-102">Add a Moving Average to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3e530-103">Ein gleitender Durchschnitt ist ein Mittelwert der Daten in der Reihe, die im Verlauf eines definierten Zeitraums berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="3e530-103">A moving average is an average of the data in your series, calculated over a defined period of time.</span></span> <span data-ttu-id="3e530-104">Der gleitende Durchschnitt kann im Diagramm angezeigt werden, um bedeutende Trends zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3e530-104">The moving average can be shown on the chart to identify significant trends.</span></span>  
  
 <span data-ttu-id="3e530-105">Die Formel für den gleitenden Durchschnitt ist der gängigste in technischen Analysen verwendete Preisindikator.</span><span class="sxs-lookup"><span data-stu-id="3e530-105">The Moving Average formula is the most popular price indicator used in technical analyses.</span></span> <span data-ttu-id="3e530-106">Viele andere Formeln, einschließlich Mittel, Median und Standardabweichung, können auch von einer Reihe des Diagramms abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3e530-106">Many other formulas, including mean, median and standard deviation, can also be derived from a series on the chart.</span></span> <span data-ttu-id="3e530-107">Wenn ein gleitender Durchschnitt angegeben wird, verfügt jede Formel möglicherweise über einen oder mehrere Parameter, die ebenfalls angegeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3e530-107">When specifying a moving average, each formula may have one or more parameters that must be specified.</span></span>  
  
 <span data-ttu-id="3e530-108">Wenn eine Formel für den gleitenden Durchschnitt im Entwurfsmodus hinzugefügt wird, ist die hinzugefügte Linienreihe nur ein visueller Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="3e530-108">When a moving average formula is added in Design mode, the line series that is added is only a visual placeholder.</span></span> <span data-ttu-id="3e530-109">Das Diagramm berechnet die Datenpunkte jeder Formel bei der Berichtsverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="3e530-109">The chart will calculate the data points of each formula during report processing.</span></span>  
  
 <span data-ttu-id="3e530-110">Integrierte Unterstützung für Trendlinien ist in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3e530-110">Built-in support for trend lines is not available in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a><span data-ttu-id="3e530-111">So fügen Sie einen berechneten gleitenden Durchschnitt einer Reihe des Diagramms hinzu</span><span class="sxs-lookup"><span data-stu-id="3e530-111">To add a calculated moving average to a series on the chart</span></span>  
  
1.  <span data-ttu-id="3e530-112">Klicken Sie mit der rechten Maustaste auf ein Feld im Bereich **Werte** , und klicken Sie auf **Berechnete Reihe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3e530-112">Right-click on a field in the **Values** area and click **Add Calculated Series**.</span></span> <span data-ttu-id="3e530-113">Das Dialogfeld **Eigenschaften von berechneten Reihen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3e530-113">The **Calculated Series Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3e530-114">Wählen Sie in der Dropdownliste **Formel** die Option **Gleitender Durchschnitt** aus.</span><span class="sxs-lookup"><span data-stu-id="3e530-114">Select the **Moving average** option from the **Formula** drop-down list.</span></span>  
  
3.  <span data-ttu-id="3e530-115">Geben Sie einen ganzzahligen Wert für den **Zeitraum** an, über den der gleitende Durchschnitt ermittelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e530-115">Specify an integer value for the **Period** that represents the period of the moving average.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e530-116">Der Zeitraum entspricht der Anzahl von Tagen, die verwendet wird, um einen gleitenden Durchschnitt zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="3e530-116">The period is the number of days used to calculate a moving average.</span></span> <span data-ttu-id="3e530-117">Wenn auf der X-Achse keine Datum/Uhrzeit-Werte angegeben sind, wird der Zeitraum durch die Anzahl der Datenpunkte dargestellt, die zur Berechnung eines gleitenden Durchschnitts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e530-117">If date/time values are not specified on the x-axis, the period is represented by the number of data points used to calculate a moving average.</span></span> <span data-ttu-id="3e530-118">Wenn es nur einen Datenpunkt gibt, wird die Formel für den gleitenden Durchschnitt nicht berechnet.</span><span class="sxs-lookup"><span data-stu-id="3e530-118">If there is only one data point, the moving average formula does not calculate.</span></span> <span data-ttu-id="3e530-119">Der gleitende Durchschnitt wird am zweiten Punkt beginnend berechnet.</span><span class="sxs-lookup"><span data-stu-id="3e530-119">The moving average is calculated starting at the second point.</span></span> <span data-ttu-id="3e530-120">Wenn Sie die Option **Bei erstem Punkt beginnen** angeben, startet das Diagramm den gleitenden Durchschnitt am ersten Punkt.</span><span class="sxs-lookup"><span data-stu-id="3e530-120">If you specify the **Start from first point** option, the chart will start the moving average at the first point.</span></span> <span data-ttu-id="3e530-121">Wenn nur ein Datenpunkt vorhanden ist, entspricht der Punkt im berechneten gleitenden Durchschnitt dem ersten Punkt Ihrer ursprünglichen Reihe.</span><span class="sxs-lookup"><span data-stu-id="3e530-121">If there is only one data point, the point in the calculated moving average will be identical to the first point in your original series.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e530-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e530-122">See Also</span></span>  
 <span data-ttu-id="3e530-123">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3e530-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3e530-124">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3e530-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3e530-125">Fügen Sie dem Diagramm &#40;Berichts-Generator und SSRS leere Punkte hinzu&#41;</span><span class="sxs-lookup"><span data-stu-id="3e530-125">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
