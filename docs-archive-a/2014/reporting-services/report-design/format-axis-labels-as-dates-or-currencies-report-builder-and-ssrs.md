---
title: Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9a01a74-2f51-4b35-be3a-a6138568f6cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ffe9d903a2271db95d4b1c2ef6201d2b0f3edab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616386"
---
# <a name="format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs"></a><span data-ttu-id="d22b2-102">Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d22b2-102">Format Axis Labels as Dates or Currencies (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d22b2-103">Wenn Sie ordnungsgemäß formatierte DateTime-Werte auf einer Achse anzeigen, zeigt ein Diagramm diese Werte automatisch als Tage an.</span><span class="sxs-lookup"><span data-stu-id="d22b2-103">When you show properly formatted DateTime values on an axis, a chart will automatically display these values as days.</span></span> <span data-ttu-id="d22b2-104">Zum Festlegen eines Datums- oder Zeitintervalls für die x-Achse (z. B. ein Monats- oder Stundenintervall) müssen Sie die Achsenbezeichnungen formatieren und den Achsentyp auf ein gültiges Datums- oder Zeitintervall festlegen.</span><span class="sxs-lookup"><span data-stu-id="d22b2-104">To specify a date/time interval for the x-axis, such as an interval of months or an interval of hours, you must format the axis labels and set the type of axis interval to a valid date or time interval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d22b2-105">In Säulen- und Punktdiagrammen ist die horizontale Achse bzw. x-Achse die Kategorieachse.</span><span class="sxs-lookup"><span data-stu-id="d22b2-105">In column and scatter charts, the horizontal, or x-axis, is the category axis.</span></span> <span data-ttu-id="d22b2-106">In Balkendiagrammen ist die vertikale Achse bzw. y-Achse die Kategorieachse.</span><span class="sxs-lookup"><span data-stu-id="d22b2-106">In bar charts, the vertical, or y-axis, is the category axis.</span></span>  
  
 <span data-ttu-id="d22b2-107">Für die korrekte Formatierung von Zeitintervallen müssen die auf der x-Achse angezeigten Werte einen <xref:System.DateTime> -Datentyp ergeben.</span><span class="sxs-lookup"><span data-stu-id="d22b2-107">In order to format time intervals correctly, the values displayed on the x-axis must evaluate to a <xref:System.DateTime> data type.</span></span> <span data-ttu-id="d22b2-108">Wenn das Feld den Datentyp <xref:System.String>aufweist, berechnet das Diagramm Intervalle nicht als Datumsangaben oder Zeiten.</span><span class="sxs-lookup"><span data-stu-id="d22b2-108">If your field has a data type of <xref:System.String>, the chart will not calculate intervals as dates or times.</span></span> <span data-ttu-id="d22b2-109">Weitere Informationen finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d22b2-109">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d22b2-110">Wenn der y-Achse ein numerischer Wert hinzugefügt wird, wird die Zahl im Diagramm erst formatiert, wenn sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d22b2-110">When a numeric value is added to the y-axis, by default, the chart does not format the number before displaying it.</span></span> <span data-ttu-id="d22b2-111">Wenn das numerische Feld eine Verkaufszahl enthält, sollten Sie die Zahlen als Währungseinheiten formatieren, um so die Lesbarkeit des Diagramms zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d22b2-111">If your numeric field is a sales figure, consider formatting the numbers as currencies to increase the readability of the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-format-x-axis-labels-as-monthly-intervals"></a><span data-ttu-id="d22b2-112">So formatieren Sie x-Achsenbezeichnungen als monatliche Intervalle</span><span class="sxs-lookup"><span data-stu-id="d22b2-112">To format x-axis labels as monthly intervals</span></span>  
  
1.  <span data-ttu-id="d22b2-113">Klicken Sie mit der rechten Maustaste auf die horizontale Achse bzw. x-Achse des Diagramms, und wählen Sie **Eigenschaften für horizontale Achsen**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-113">Right-click the horizontal, or x-axis, of the chart, and select **HorizontalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="d22b2-114">Wählen Sie im Dialogfeld **Eigenschaften für horizontale Achsen** die Option **Zahl**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-114">In the **HorizontalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="d22b2-115">Wählen Sie in der Liste **Kategorie** die Option **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-115">From the **Category** list, select **Date**.</span></span> <span data-ttu-id="d22b2-116">Wählen Sie in der Liste **Typ** das Datumsformat aus, das auf die X-Achsenbezeichnungen angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d22b2-116">From the **Type** list, select a date format to apply to the x-axis labels.</span></span>  
  
4.  <span data-ttu-id="d22b2-117">Wählen Sie **Achsenoptionen**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-117">Select **Axis Options.**</span></span>  
  
5.  <span data-ttu-id="d22b2-118">Geben Sie in **Intervall**den Wert **1**ein.</span><span class="sxs-lookup"><span data-stu-id="d22b2-118">In **Interval**, type **1**.</span></span> <span data-ttu-id="d22b2-119">Wählen Sie unter **Intervalltyp** die Eigenschaft **Monate**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-119">In **Interval type** property, select **Months**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d22b2-120">Wenn Sie keinen Intervalltyp angeben, berechnet das Diagramm Intervalle in Tagen.</span><span class="sxs-lookup"><span data-stu-id="d22b2-120">If you do not specify an interval type, the chart will calculate intervals in terms of days.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-format-y-axis-labels-using-a-currency-format"></a><span data-ttu-id="d22b2-121">So formatieren Sie y-Achsenbezeichnungen mit einem Währungsformat</span><span class="sxs-lookup"><span data-stu-id="d22b2-121">To format y-axis labels using a currency format</span></span>  
  
1.  <span data-ttu-id="d22b2-122">Klicken Sie mit der rechten Maustaste auf die vertikale Achse bzw. y-Achse des Diagramms, und wählen Sie **Eigenschaften für vertikale Achsen**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-122">Right-click the vertical, or y-axis, of the chart, and select **VerticalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="d22b2-123">Wählen Sie im Dialogfeld **Eigenschaften für vertikale Achsen** die Option **Zahl**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-123">In the **VerticalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="d22b2-124">Wählen Sie in der Liste **Kategorie** die Option **Währung**aus.</span><span class="sxs-lookup"><span data-stu-id="d22b2-124">From the **Category** list, select **Currency**.</span></span> <span data-ttu-id="d22b2-125">Wählen Sie in der Liste **Symbol** das Währungsformat aus, das auf die Y-Achsenbezeichnungen angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d22b2-125">From the **Symbol** list, select a currency format to apply to the y-axis labels.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d22b2-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d22b2-126">See Also</span></span>  
 <span data-ttu-id="d22b2-127">[Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d22b2-127">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d22b2-128">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d22b2-128">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d22b2-129">[Angeben einer logarithmischen Skalierung (Berichts-Generator und SSRS)](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d22b2-129">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d22b2-130">Angeben eines Achsenintervalls &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d22b2-130">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
