---
title: Festlegen eines Mindestwerts oder eines Höchstwerts auf einem Messgerät (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 344122dbff647a8c35b838ecce637602f202864b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609640"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="e26d3-102">Festlegen eines Mindestwerts oder eines Höchstwerts auf einem Messgerät (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e26d3-102">Set a Minimum or Maximum on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e26d3-103">Im Gegensatz zu Diagrammen mit mehreren Gruppen zeigen Messgeräte nur einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="e26d3-103">Unlike the chart, where multiple groups are defined, the gauge only shows one value.</span></span> <span data-ttu-id="e26d3-104">Da Berichts-Generator und Berichts-Designer nicht in der Lage sind, den Kontext oder die relative Bedeutung des einen Werts, der auf dem Messgerät angezeigt werden soll, zu ermitteln, müssen Sie den niedrigsten und den höchsten Wert der Skala festlegen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-104">Since Report Builder and Report Designer determine the context or relative significance of the one value that you are trying to show on the gauge, you must define the minimum and maximum of the scale.</span></span> <span data-ttu-id="e26d3-105">Wenn die Datenwerte zum Beispiel zwischen 0 und 10 liegen, sollten Sie den Mindestwert 0 und den Höchstwert 10 festlegen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-105">For example, if your data values are rankings between 0 and 10, you will want to set the minimum to 0 and maximum to 10.</span></span> <span data-ttu-id="e26d3-106">Die Intervalle werden automatisch basierend auf dem festgelegten Mindest- und Höchstwert berechnet.</span><span class="sxs-lookup"><span data-stu-id="e26d3-106">The interval numbers are calculated automatically based on the values specified for the minimum and maximum.</span></span> <span data-ttu-id="e26d3-107">Standardmäßig wird der Mindestwert 0 und der Höchstwert 100 festgelegt. Dies sind jedoch willkürliche Werte, die geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="e26d3-107">By default, the minimum and maximum are set to 0 and 100, but this is an arbitrary value that you should change.</span></span> <span data-ttu-id="e26d3-108">Der Wert wird nicht als Prozentwert berechnet.</span><span class="sxs-lookup"><span data-stu-id="e26d3-108">The application does not calculate your value as a percentage.</span></span>  
  
 <span data-ttu-id="e26d3-109">Falls Sie mit einem großen Wertebereich arbeiten, wie etwa von 0 bis 10000, können Sie ggf. einen Multiplikator verwenden, um die Anzahl der Nullen auf dem Messgerät zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e26d3-109">If the range of your values is large, for example from 0 to 10000, consider using a multiplier to reduce the number of zeroes on the gauge.</span></span> <span data-ttu-id="e26d3-110">Der Multiplikator reduziert lediglich die Skalierung der Zahlen auf dem Messgerät, nicht den Wert selbst.</span><span class="sxs-lookup"><span data-stu-id="e26d3-110">The multiplier will only reduce the scale of the numbers on the gauge, not the value itself.</span></span>  
  
 <span data-ttu-id="e26d3-111">Sie können die Werte der Optionen **Minimum** und **Maximum** mithilfe von Ausdrücken festlegen.</span><span class="sxs-lookup"><span data-stu-id="e26d3-111">You can use expressions to set the values of the **Minimum** and **Maximum** options.</span></span> <span data-ttu-id="e26d3-112">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e26d3-112">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a><span data-ttu-id="e26d3-113">So legen Sie den Mindestwert und den Höchstwert auf dem Messgerät fest</span><span class="sxs-lookup"><span data-stu-id="e26d3-113">To set the minimum and maximum on the gauge</span></span>  
  
1.  <span data-ttu-id="e26d3-114">Klicken Sie mit der rechten Maustaste auf die Skalierung, und wählen Sie **Skalierungseigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e26d3-114">Right-click on the scale and select **Scale Properties**.</span></span> <span data-ttu-id="e26d3-115">Das Dialogfeld **Skalierungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e26d3-115">The **Scale Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="e26d3-116">Geben Sie im Abschnitt **Allgemein**einen Wert für **Minimum**an.</span><span class="sxs-lookup"><span data-stu-id="e26d3-116">In **General**, specify a value for **Minimum**.</span></span> <span data-ttu-id="e26d3-117">Dieser Wert ist standardmäßig 0.</span><span class="sxs-lookup"><span data-stu-id="e26d3-117">By default, this value is 0.</span></span> <span data-ttu-id="e26d3-118">Klicken Sie optional auf die **Ausdrucksschaltfläche** (*fx*), um den Ausdruck zu bearbeiten, der den Wert der Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="e26d3-118">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
3.  <span data-ttu-id="e26d3-119">Geben Sie einen Wert für **Maximum**an.</span><span class="sxs-lookup"><span data-stu-id="e26d3-119">Specify a value for **Maximum**.</span></span> <span data-ttu-id="e26d3-120">Der Standardwert ist 100.</span><span class="sxs-lookup"><span data-stu-id="e26d3-120">By default, this value is 100.</span></span> <span data-ttu-id="e26d3-121">Klicken Sie optional auf die **Ausdrucksschaltfläche** (*fx*), um den Ausdruck zu bearbeiten, der den Wert der Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="e26d3-121">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="e26d3-122">(Optional) Falls die angegebenen Werte sehr groß sind, legen Sie einen Wert für **Skalabezeichnungen multiplizieren mit** fest.</span><span class="sxs-lookup"><span data-stu-id="e26d3-122">(Optional) If the values for your minimum and maximum are large, specify a value for the **Multiply scale labels by** option.</span></span> <span data-ttu-id="e26d3-123">Um einen Multiplikator festzulegen, durch den die Skalierung reduziert wird, verwenden Sie eine Dezimalzahl.</span><span class="sxs-lookup"><span data-stu-id="e26d3-123">To specify a multiplier that reduces your scale, use a decimal number.</span></span> <span data-ttu-id="e26d3-124">Wenn Sie zum Beispiel eine Skalierung von 0 bis 1000 verwenden, können Sie den Multiplikatorwert 0,01 festlegen, sodass die Skalierung als 0 bis 10 angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e26d3-124">For example, if you have a scale from 0 to 1000, you can specify a multiplier value of 0.01 to reduce the scale to read 0 to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26d3-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e26d3-125">See Also</span></span>  
 <span data-ttu-id="e26d3-126">[Formatieren von Skalen auf einem Messgerät &#40;Berichts-Generator und SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e26d3-126">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e26d3-127">[Formatieren von Zeigern auf einem Messgerät (Berichts-Generator und SSRS)](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e26d3-127">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e26d3-128">Messgeräte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e26d3-128">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
