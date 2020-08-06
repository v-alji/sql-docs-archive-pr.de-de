---
title: Definieren von Farben in einem Diagramm mit einer Palette (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7db137ed87b0c84e43577dcf2936a6287abd8e36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617742"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a><span data-ttu-id="be0d3-102">Definieren von Farben in einem Diagramm mit einer Palette (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="be0d3-102">Define Colors on a Chart Using a Palette (Report Builder and SSRS)</span></span>
  <span data-ttu-id="be0d3-103">Sie können die Farbpalette für ein Diagramm durch Auswählen einer vordefinierten Palette oder durch Definieren einer benutzerdefinierten Palette ändern.</span><span class="sxs-lookup"><span data-stu-id="be0d3-103">You can change the color palette for a chart by selecting a pre-defined palette or defining a custom palette.</span></span> <span data-ttu-id="be0d3-104">Benutzerdefinierte Paletten sind berichtsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="be0d3-104">Custom palettes are report-specific.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a><span data-ttu-id="be0d3-105">So ändern Sie die Farben im Diagramm mit einer integrierten Farbpalette</span><span class="sxs-lookup"><span data-stu-id="be0d3-105">To change the colors on the chart using a built-in color palette</span></span>  
  
1.  <span data-ttu-id="be0d3-106">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="be0d3-106">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="be0d3-107">Klicken Sie auf der Entwurfsoberfläche auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="be0d3-107">On the design surface, click the chart.</span></span> <span data-ttu-id="be0d3-108">Die Eigenschaften für das Diagrammobjekt werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be0d3-108">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
     <span data-ttu-id="be0d3-109">Der Objektname (standardmäßig**Chart1** ) wird in der Dropdownliste oben im Bereich „Eigenschaften“ aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="be0d3-109">The object name (**Chart1** by default) appears in the drop-down list at the top of the Properties pane.</span></span>  
  
3.  <span data-ttu-id="be0d3-110">Wählen Sie im Abschnitt **Diagramm** für die „Palette“-Eigenschaft eine neue Palette aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="be0d3-110">In the **Chart** section, for the Palette property, select a new palette from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="be0d3-111">Sie können die Farben oder die Reihenfolge in einer vordefinierten Palette nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="be0d3-111">You cannot change the colors or order in a pre-defined palette.</span></span>  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a><span data-ttu-id="be0d3-112">So definieren Sie eigene Farben im Diagramm mit einer benutzerdefinierten Farbpalette</span><span class="sxs-lookup"><span data-stu-id="be0d3-112">To define your own colors on the chart using a custom color palette</span></span>  
  
1.  <span data-ttu-id="be0d3-113">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="be0d3-113">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="be0d3-114">Klicken Sie auf der Entwurfsoberfläche auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="be0d3-114">On the design surface, click the chart.</span></span> <span data-ttu-id="be0d3-115">Die Eigenschaften für das Diagrammobjekt werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be0d3-115">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="be0d3-116">Wählen Sie im Abschnitt **Diagramm** für die-Eigenschaft die Option `Palette` **Benutzer**definiert aus.</span><span class="sxs-lookup"><span data-stu-id="be0d3-116">In the **Chart** section, for the `Palette` property, select **Custom**.</span></span>  
  
4.  <span data-ttu-id="be0d3-117">Klicken Sie in der CustomPaletteColors-Eigenschaft auf die Schaltfläche zum Bearbeiten der Collection ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="be0d3-117">In the CustomPaletteColors property, click the Edit Collection (**...**) button.</span></span> <span data-ttu-id="be0d3-118">Das Dialogfeld **ReportColorExpression-Auflistungs-Editor** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="be0d3-118">The **ReportColorExpression Collection Editor** opens.</span></span>  
  
5.  <span data-ttu-id="be0d3-119">Klicken Sie auf **Hinzufügen** , um eine Farbe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="be0d3-119">Click **Add** to add a color.</span></span> <span data-ttu-id="be0d3-120">Wählen Sie in der Dropdownliste eine Farbe aus, oder wählen Sie Ausdruck, und geben Sie einen hexadezimalen Wert für eine bestimmte Farbe an, z. B. ff6600 für "Orange".</span><span class="sxs-lookup"><span data-stu-id="be0d3-120">Select a color from the drop-down list or select Expression and specify a hex value for a specific color, such as ff6600 for "Orange".</span></span>  
  
     <span data-ttu-id="be0d3-121">Weitere Informationen zu Hexadezimalwerten finden Sie unter [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="be0d3-121">For more information about hex values, see [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) on MSDN.</span></span>  
  
6.  <span data-ttu-id="be0d3-122">Klicken Sie auf **Hinzufügen** , um der Palette weitere Farben hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="be0d3-122">Click **Add** to add more colors to the palette.</span></span>  
  
7.  <span data-ttu-id="be0d3-123">Abschließend klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="be0d3-123">When you are done, click **OK**.</span></span>  
  
 <span data-ttu-id="be0d3-124">Wenn Sie eine benutzerdefinierte Palette verwenden, können Sie die Reihenfolge der Farben ändern, um die Farbe verschiedener Reihen im Diagramm zu ändern.</span><span class="sxs-lookup"><span data-stu-id="be0d3-124">If you are using a custom palette, you can change the order of the colors to change the color of different series in the chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0d3-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be0d3-125">See Also</span></span>  
 <span data-ttu-id="be0d3-126">[Formatieren von Reihenfarben in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be0d3-126">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="be0d3-127">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be0d3-127">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="be0d3-128">Angeben von Farben, die für mehrere Formdiagramme konsistent sind &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="be0d3-128">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
