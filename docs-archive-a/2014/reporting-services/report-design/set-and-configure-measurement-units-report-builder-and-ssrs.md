---
title: Festlegen und Konfigurieren von Maßeinheiten (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c01523dad9a96d2d45b96474d36873bac2484343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608287"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a><span data-ttu-id="ee092-102">Festlegen und Konfigurieren von Maßeinheiten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ee092-102">Set and Configure Measurement Units (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ee092-103">Indikatoren stellen zwei Maßeinheiten bereit: eine prozentuale und eine numerische Maßeinheit.</span><span class="sxs-lookup"><span data-stu-id="ee092-103">Indicators provide two measurement units: percentage and numeric.</span></span> <span data-ttu-id="ee092-104">Standardmäßig sind Indikatoren so konfiguriert, dass Prozentsätze als Maßeinheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee092-104">By default, indicators are configured to use percentages as the measurement unit.</span></span> <span data-ttu-id="ee092-105">Dies bedeutet, dass die Indikatorwerte, die den einzelnen Symbolen im Indikatorsatz zugewiesen sind, von einem Prozentbereich bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="ee092-105">This means that the indicator values assigned to each icon in the indicator set are determined by a percentage range.</span></span> <span data-ttu-id="ee092-106">Die Prozentbereiche werden gleichmäßig auf die Symbole im Indikatorsatz verteilt.</span><span class="sxs-lookup"><span data-stu-id="ee092-106">The percentage ranges are evenly divided across the icons in the indicator set.</span></span> <span data-ttu-id="ee092-107">Jedes Symbol stellt einen Indikatorstatus dar.</span><span class="sxs-lookup"><span data-stu-id="ee092-107">Each icon represents an indicator state.</span></span> <span data-ttu-id="ee092-108">Sie können die Prozentsätze für die einzelnen Symbole im Indikatorsatz ändern, indem Sie andere Prozentsätze für den Start- und Endbereich angeben.</span><span class="sxs-lookup"><span data-stu-id="ee092-108">You can change the percentages for each icon in the indicator set by specifying different start and end percentages.</span></span> <span data-ttu-id="ee092-109">Darüber hinaus wird der Minimal- und Maximalwert in den Daten von Indikatoren automatisch erkannt.</span><span class="sxs-lookup"><span data-stu-id="ee092-109">Indicators also automatically detect the minimum and maximum values in the data.</span></span>  
  
 <span data-ttu-id="ee092-110">Sie können die Maßeinheit in einen numerischen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="ee092-110">You can change the measurement unit to be a numeric value.</span></span> <span data-ttu-id="ee092-111">In diesem Fall geben Sie kein Minimum oder Maximum für die Daten an, sondern legen stattdessen nur den Start- und Endwert für jedes vom Indikator verwendete Symbol fest.</span><span class="sxs-lookup"><span data-stu-id="ee092-111">In this case, you do not specify minimum or maximum for the data; instead, you provide only the start and end values for each icon that the indicator uses.</span></span>  
  
 <span data-ttu-id="ee092-112">Optionen wie Maßeinheiten können mithilfe von Ausdrücken festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ee092-112">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="ee092-113">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ee092-113">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-use-the-numeric-state-measurement-unit"></a><span data-ttu-id="ee092-114">So verwenden Sie die numerische Maßeinheit</span><span class="sxs-lookup"><span data-stu-id="ee092-114">To use the numeric state measurement unit</span></span>  
  
1.  <span data-ttu-id="ee092-115">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ee092-115">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="ee092-116">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="ee092-116">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="ee092-117">Klicken Sie in der Liste **Maßeinheit für Status** auf **Numerisch**.</span><span class="sxs-lookup"><span data-stu-id="ee092-117">In the **States Measurement Unit** list, click **Numeric**.</span></span>  
  
     <span data-ttu-id="ee092-118">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Wert der Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="ee092-118">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="ee092-119">Aktualisieren Sie für jedes Symbol im Indikatorsatz die Werte in den Textfeldern **Start** und **Ende** .</span><span class="sxs-lookup"><span data-stu-id="ee092-119">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="ee092-120">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, mit dem die Werte der Optionen **Start** und **Ende** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ee092-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee092-121">Die Werte in den Textfeldern **Start** und **Ende** müssen numerisch sein.</span><span class="sxs-lookup"><span data-stu-id="ee092-121">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-percentage-measurement-unit"></a><span data-ttu-id="ee092-122">So verwenden Sie die prozentuale Maßeinheit</span><span class="sxs-lookup"><span data-stu-id="ee092-122">To use the percentage measurement unit</span></span>  
  
1.  <span data-ttu-id="ee092-123">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ee092-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="ee092-124">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="ee092-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="ee092-125">Klicken Sie in der Liste **Maßeinheit für Status** auf **Prozent**.</span><span class="sxs-lookup"><span data-stu-id="ee092-125">In the **States Measurement Unit** list, click **Percentage**.</span></span>  
  
     <span data-ttu-id="ee092-126">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Wert der Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="ee092-126">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="ee092-127">Optional können Sie die Optionen **Minimum** und **Maximum** ändern, um bestimmte Werte zu verwenden, statt die vom Indikator verwendeten Minimum- und Maximumwerte der Daten automatisch zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ee092-127">Optionally, change the **Minimum** and **Maximum** options to use specific values instead of automatically detecting the minimum and maximum values of the data that the indicator uses.</span></span> <span data-ttu-id="ee092-128">Der Wert von **Minimum** muss kleiner als der Wert von **Maximum**sein.</span><span class="sxs-lookup"><span data-stu-id="ee092-128">The value of **Minimum** must be smaller than the value of **Maximum**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee092-129">Wenn Sie explizit Minimum- und Maximumwerte festlegen, wird dieser Wertbereich vom Indikator unabhängig von den tatsächlichen Minimum- und Maximumwerten in den Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee092-129">If you explicitly set minimum and maximum values, that value range is used by the indicator regardless of the actual the minimum and maximum values in the data.</span></span> <span data-ttu-id="ee092-130">Das bedeutet, dass die Werte unter dem Minimumwert und über dem Maximumwert von der Auswertung ausgeschlossen wird, über die die im Bericht anzuzeigenden Indikatorsymbole bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="ee092-130">This means that values lower than the minimum and higher than the maximum are excluded from the evaluation that determine what indictor icon to show in the report.</span></span>  
  
     <span data-ttu-id="ee092-131">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der die Werte der Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="ee092-131">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the option.</span></span>  
  
5.  <span data-ttu-id="ee092-132">Aktualisieren Sie für jedes Symbol im Indikatorsatz die Werte in den Textfeldern **Start** und **Ende** .</span><span class="sxs-lookup"><span data-stu-id="ee092-132">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="ee092-133">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, mit dem die Werte der Optionen **Start** und **Ende** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ee092-133">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee092-134">Die Werte in den Textfeldern **Start** und **Ende** müssen numerisch sein.</span><span class="sxs-lookup"><span data-stu-id="ee092-134">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee092-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee092-135">See Also</span></span>  
 [<span data-ttu-id="ee092-136">Indikatoren &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee092-136">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
