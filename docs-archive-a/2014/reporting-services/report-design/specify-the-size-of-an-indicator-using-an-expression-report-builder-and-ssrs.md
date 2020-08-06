---
title: Angeben der Größe eines Indikators mithilfe eines Ausdrucks (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab0b86f1-4882-4258-a2b6-c612faecfa4b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b450abb957329b8dbaa4f7f0e4c963c5f63f06b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608264"
---
# <a name="specify-the-size-of-an-indicator-using-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="0fe06-102">Angeben der Größe eines Indikators mithilfe eines Ausdrucks (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0fe06-102">Specify the Size of an Indicator Using an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0fe06-103">Zusätzlich zu Farbe, Richtung und Form können Sie die Größe anpassen und damit die visuelle Wirkung von Indikatoren maximieren.</span><span class="sxs-lookup"><span data-stu-id="0fe06-103">In addition to color, direction, and shape, you can use size to maximize the visual impact of indicators.</span></span>  
  
 <span data-ttu-id="0fe06-104">Ein Indikator verfügt über eine Auflistung von Indikatorstatus mit der Bezeichnung IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="0fe06-104">An indicator has a collection of indicator states named IndicatorStates.</span></span> <span data-ttu-id="0fe06-105">Die IndicatorStates-Auflistung verfügt in der Regel über mehrere Status.</span><span class="sxs-lookup"><span data-stu-id="0fe06-105">The IndicatorStates collection typically have multiple states.</span></span> <span data-ttu-id="0fe06-106">Jeder Status ist ein Element der Auflistung und wird durch ein Symbol dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0fe06-106">Each state is a member of the collection and is represented by an icon.</span></span> <span data-ttu-id="0fe06-107">Zusammen bilden die Status die IndicatorsStates-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fe06-107">Together the states constitute the IndicatorsStates collection.</span></span>  
  
 <span data-ttu-id="0fe06-108">Um die Größen von Symbolen dynamisch zu konfigurieren, legen Sie die Eigenschaften der Elemente der IndicatorsStates-Auflistung im Eigenschaftenbereich des Berichts-Generators fest.</span><span class="sxs-lookup"><span data-stu-id="0fe06-108">To dynamically configure the sizes of icons, you set properties of members of the IndicatorsStates collection in the Properties pane of Report Builder.</span></span> <span data-ttu-id="0fe06-109">Zum Anzeigen des Bereichs **Eigenschaften** klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0fe06-109">If the **Properties** pane is not visible, click the **View** tab and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0fe06-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]verwenden Sie das **Eigenschaftenfenster** , um die Elementeigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0fe06-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you use the **Properties** window to set the member properties.</span></span> <span data-ttu-id="0fe06-111">Wenn das **Eigenschaftenfenster** nicht geöffnet ist, drücken Sie die F4-TASTE.</span><span class="sxs-lookup"><span data-stu-id="0fe06-111">If the **Properties** window is not open, press the F4 key.</span></span>  
  
 <span data-ttu-id="0fe06-112">Der Bereich **Eigenschaften** bietet Zugriff auf die Eigenschaften der IndicatorStates-Auflistung eines Indikators.</span><span class="sxs-lookup"><span data-stu-id="0fe06-112">The **Properties** pane provides access to the properties of the IndicatorStates collection of an indicator.</span></span> <span data-ttu-id="0fe06-113">Sie konfigurieren die Größe der Symbole, indem Sie die ScaleFactor-Eigenschaft der IndicatorStates-Auflistungselemente mit einem Ausdruck festlegen.</span><span class="sxs-lookup"><span data-stu-id="0fe06-113">You configure the icons to be different sizes by setting the ScaleFactor property of the IndicatorStates collection members using an expression.</span></span> <span data-ttu-id="0fe06-114">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0fe06-114">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="0fe06-115">Der in dieser Prozedur verwendete Ausdruck wurde ebenfalls verwendet, um den Bericht mit Indikatoren verschiedener Größe zu erstellen, wie in [Indikatoren &#40;Berichts-Generator und SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0fe06-115">The expression used in this procedure was also used to generate the report with different sizes of indicators, shown in [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-the-indicator-icon-size-using-an-expression"></a><span data-ttu-id="0fe06-116">So geben Sie die Symbolgröße für Indikatoren mit einem Ausdruck an</span><span class="sxs-lookup"><span data-stu-id="0fe06-116">To specify the indicator icon size using an expression</span></span>  
  
1.  <span data-ttu-id="0fe06-117">Klicken Sie auf den Indikator, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0fe06-117">Click the indicator you want to change.</span></span>  
  
2.  <span data-ttu-id="0fe06-118">Suchen Sie im Eigenschaftenbereich die IndicatorStates-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0fe06-118">In the Properties pane, locate the IndicatorStates property.</span></span>  
  
     <span data-ttu-id="0fe06-119">Wenn der Eigenschaftenbereich nach Kategorie organisiert ist, finden Sie IndicatorStates unter der Kategorie **Status** .</span><span class="sxs-lookup"><span data-stu-id="0fe06-119">If the Properties pane is organized by category, you will find IndicatorStates in the **States** category.</span></span>  
  
3.  <span data-ttu-id="0fe06-120">Klicken Sie neben IndicatorStates auf die Schaltfläche mit den Auslassungszeichen **(...)** .</span><span class="sxs-lookup"><span data-stu-id="0fe06-120">Click the ellipsis **(...)** button next to IndicatorStates.</span></span> <span data-ttu-id="0fe06-121">Das Dialogfeld **IndicatorState-Auflistungs-Editor** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0fe06-121">The **IndicatorState Collection Editor** dialog box opens.</span></span>  
  
     <span data-ttu-id="0fe06-122">Wählen Sie alle Elemente der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="0fe06-122">Select all members of the collection.</span></span>  
  
4.  <span data-ttu-id="0fe06-123">Klicken Sie in der Liste mit den **Mehrfachauswahleigenschaften** auf den Abwärtspfeil neben ScaleFactor, und klicken Sie dann auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="0fe06-123">In the **Multi-Select Properties** list, click the down arrow next to ScaleFactor and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="0fe06-124">Schreiben Sie im Dialogfeld **Ausdruck** den Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0fe06-124">In the **Expression** dialog box write the expression.</span></span>  
  
     <span data-ttu-id="0fe06-125">Der folgende Beispielausdruck ändert die Größe des Symbols basierend auf dem Wert des **SalesYTD** -Felds.</span><span class="sxs-lookup"><span data-stu-id="0fe06-125">The following sample expression makes the icon a different size based on the value of the **SalesYTD** field.</span></span>  
  
     `=IIF(Fields!SalesYTD.value = 0,0,Fields!SalesYTD.value/Max(Fields!SalesYTD.value,"Indicator"))`  
  
     <span data-ttu-id="0fe06-126">Weitere Informationen finden Sie unter [Beispiele für Ausdrücke (Berichts-Generator und SSRS)](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0fe06-126">For more information, see [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0fe06-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fe06-127">See Also</span></span>  
 [<span data-ttu-id="0fe06-128">Indikatoren &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0fe06-128">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
