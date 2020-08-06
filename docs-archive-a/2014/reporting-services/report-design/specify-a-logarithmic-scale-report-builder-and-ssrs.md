---
title: Angeben einer logarithmischen Skalierung (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cc422a6f95a420445dc604d08a23e8f8e65c95d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608271"
---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a><span data-ttu-id="d8417-102">Angeben einer logarithmischen Skalierung (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d8417-102">Specify a Logarithmic Scale (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d8417-103">Bei logarithmisch proportionalen Daten wäre es möglicherweise sinnvoll, eine logarithmische Skalierung für das Diagramm zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8417-103">If you have data that is logarithmically proportional, you may want to consider using a logarithmic scale on the chart.</span></span> <span data-ttu-id="d8417-104">So werden die Daten überschaubarer und die Darstellung des Diagramms wird verbessert.</span><span class="sxs-lookup"><span data-stu-id="d8417-104">This helps improve the appearance of the chart by making your data more manageable.</span></span> <span data-ttu-id="d8417-105">Die meisten logarithmischen Skalierungen verwenden die Basis 10.</span><span class="sxs-lookup"><span data-stu-id="d8417-105">Most logarithmic scales use a base of 10.</span></span>  
  
 <span data-ttu-id="d8417-106">Diese Funktion ist nur auf der Wertachse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8417-106">This feature is only available on the value axis.</span></span> <span data-ttu-id="d8417-107">Die Wertachse ist normalerweise die vertikale Achse bzw. y-Achse.</span><span class="sxs-lookup"><span data-stu-id="d8417-107">The value axis is usually the vertical, or y-axis.</span></span> <span data-ttu-id="d8417-108">Bei Balkendiagrammen ist jedoch die horizontale Achse bzw. x-Achse die Wertachse.</span><span class="sxs-lookup"><span data-stu-id="d8417-108">On bar charts, however, it is the horizontal, or x-axis.</span></span>  
  
 <span data-ttu-id="d8417-109">Wenn die Achse logarithmisch ist, werden alle anderen Eigenschaften, die sich auf die Achse beziehen, logarithmisch skaliert.</span><span class="sxs-lookup"><span data-stu-id="d8417-109">If your axis is logarithmic, all other properties relating to the axis will be scaled logarithmically.</span></span> <span data-ttu-id="d8417-110">Wenn Sie beispielsweise eine logarithmische Skalierung zur Basis 10 auf der Achse angeben, werden durch Festlegen eines Achsenintervalls von 2 Intervalle in der Größenordnung von 10 hoch 2 bzw. 100 generiert.</span><span class="sxs-lookup"><span data-stu-id="d8417-110">For example, if you specify a base-10 logarithmic scale on your axis, setting an axis interval of 2 will generate intervals in magnitudes of 10 to the power of 2, or 100.</span></span> <span data-ttu-id="d8417-111">Dies bedeutet, dass die Achsenwerte 1, 100, 10000 und nicht wie standardmäßig 1, 10, 100, 1000, 10000 lauten.</span><span class="sxs-lookup"><span data-stu-id="d8417-111">This means your axis values will read 1, 100, 10000, instead of the default result of 1, 10, 100, 1000, 10000.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-logarithmic-scale"></a><span data-ttu-id="d8417-112">So geben Sie eine logarithmische Skalierung an</span><span class="sxs-lookup"><span data-stu-id="d8417-112">To specify a logarithmic scale</span></span>  
  
1.  <span data-ttu-id="d8417-113">Klicken Sie mit der rechten Maustaste auf die y-Achse des Diagramms, und klicken Sie auf **Eigenschaften für vertikale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="d8417-113">Right-click the y-axis of your chart, and click **VerticalAxis Properties**.</span></span> <span data-ttu-id="d8417-114">Das Dialogfeld **Eigenschaften für vertikale Achsen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8417-114">The **VerticalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d8417-115">Aktivieren Sie unter **Achsenoptionen**die Option **Logarithmische Skalierung verwenden**.</span><span class="sxs-lookup"><span data-stu-id="d8417-115">In **Axis Options**, select **Uselogarithmic scale**.</span></span>  
  
3.  <span data-ttu-id="d8417-116">Geben Sie im Textfeld **Logarithmische Basis** einen positiven Wert für die logarithmische Basis ein.</span><span class="sxs-lookup"><span data-stu-id="d8417-116">In the **Logbase** text box, type a positive value for the logarithmic base.</span></span> <span data-ttu-id="d8417-117">Wird kein Wert angegeben, wird als Standardwert 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8417-117">If no value is specified, the logarithmic base defaults to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8417-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8417-118">See Also</span></span>  
 <span data-ttu-id="d8417-119">[Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8417-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8417-120">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8417-120">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8417-121">[Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung (Berichts-Generator und SSRS)](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8417-121">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d8417-122">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d8417-122">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
