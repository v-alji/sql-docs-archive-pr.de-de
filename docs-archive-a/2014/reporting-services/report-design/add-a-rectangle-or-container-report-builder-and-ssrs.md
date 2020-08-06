---
title: Hinzufügen eines Rechtecks oder Containers (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10061"
- sql12.rtp.rptdesigner.rectangleproperties.general.f1
ms.assetid: f905c35f-754d-4d02-80f3-85e29ddda826
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fddda2f02b9f370d9742ae6add5bae444f8f55f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608293"
---
# <a name="add-a-rectangle-or-container-report-builder-and-ssrs"></a><span data-ttu-id="ce19d-102">Hinzufügen eines Rechtecks oder Containers (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ce19d-102">Add a Rectangle or Container (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ce19d-103">Fügen Sie dem Bericht ein Rechteck hinzu, wenn Sie durch ein grafisches Element Bereiche des Berichts trennen oder hervorheben oder einen Hintergrund für ein oder mehrere Berichtselemente bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ce19d-103">Add a rectangle to your report when you want a graphical element to separate areas of the report, emphasize areas of a report, or provide a background for one or more report items.</span></span> <span data-ttu-id="ce19d-104">Rechtecke werden auch als Container verwendet, mit denen das Rendering von Datenbereichen in einem Bericht gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ce19d-104">Rectangles are also used as containers to help control the way data regions render in a report.</span></span> <span data-ttu-id="ce19d-105">Sie können die Darstellung eines Rechtecks anpassen, indem Sie die Rechteckeigenschaften bearbeiten, z. B. den Hintergrund und die Rahmenfarben.</span><span class="sxs-lookup"><span data-stu-id="ce19d-105">You can customize the appearance of a rectangle by editing rectangle properties such as the background and border colors.</span></span> <span data-ttu-id="ce19d-106">Weitere Informationen zum Verwenden eines Rechtecks als Container finden Sie unter [Rechtecke und Linien (Berichts-Generator und SSRS)](rectangles-and-lines-report-builder-and-ssrs.md) und [Anzeigen derselben Daten in einer Matrix und einem Diagramm (Berichts-Generator)](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ce19d-106">For more information about using a rectangle as a container, see [Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-rectangle"></a><span data-ttu-id="ce19d-107">So fügen Sie ein Rechteck hinzu</span><span class="sxs-lookup"><span data-stu-id="ce19d-107">To add a rectangle</span></span>  
  
1.  <span data-ttu-id="ce19d-108">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Berichtselemente** auf **Rechteck**.</span><span class="sxs-lookup"><span data-stu-id="ce19d-108">On the **Insert** tab, in the **Report Items** group, click **Rectangle.**</span></span>  
  
2.  <span data-ttu-id="ce19d-109">Klicken Sie auf der Entwurfsoberfläche auf die Stelle, an der die obere linke Ecke des Rechtecks positioniert werden soll, und ziehen Sie den Mauszeiger an die Stelle, an der die untere rechte Ecke des Rechtecks positioniert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce19d-109">On the design surface, click the location where you want the upper left corner of the rectangle, and drag to where you want the lower-right corner.</span></span>  
  
     <span data-ttu-id="ce19d-110">Während Sie den Cursor bewegen, werden "Ausrichtungslinien" angezeigt, wenn der Cursor mit anderen Objekten auf der Entwurfsoberfläche ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ce19d-110">Note that as you move the cursor, "snap lines" appear as the cursor lines up with other objects on the design surface.</span></span> <span data-ttu-id="ce19d-111">Mit diesen Ausrichtungslinien können Sie die Objekte besser ausrichten.</span><span class="sxs-lookup"><span data-stu-id="ce19d-111">These help you if you want objects to be aligned.</span></span>  
  
### <a name="to-create-a-container"></a><span data-ttu-id="ce19d-112">So erstellen Sie einen Container</span><span class="sxs-lookup"><span data-stu-id="ce19d-112">To create a container</span></span>  
  
1.  <span data-ttu-id="ce19d-113">Fügen Sie dem Bericht ein Rechteckberichtsobjekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="ce19d-113">Add a rectangle report item to the report.</span></span>  
  
2.  <span data-ttu-id="ce19d-114">Ziehen Sie andere Berichtselemente in das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="ce19d-114">Drag other report items into the rectangle.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce19d-115">Ein Rechteck ist lediglich ein Container für Elemente, die Sie im Rechteck erstellen oder in das Rechteck ziehen.</span><span class="sxs-lookup"><span data-stu-id="ce19d-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="ce19d-116">Wenn Sie ein Rechteck um ein Element zeichnen, das bereits auf der Entwurfsoberfläche vorhanden ist, fungiert das Rechteck nicht als Container.</span><span class="sxs-lookup"><span data-stu-id="ce19d-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span>  
  
### <a name="to-change-rectangle-properties-such-as-color-style-or-weight"></a><span data-ttu-id="ce19d-117">So ändern Sie Rechteckeigenschaften, z. B. Farbe, Format oder Gewichtung</span><span class="sxs-lookup"><span data-stu-id="ce19d-117">To change rectangle properties such as color, style, or weight</span></span>  
  
1.  <span data-ttu-id="ce19d-118">Wählen Sie das Rechteck aus, und klicken Sie auf die Optionen für Linienfarbe, Format oder Gewichtung im Abschnitt **Rahmen** der Registerkarte Home.</span><span class="sxs-lookup"><span data-stu-id="ce19d-118">Select the rectangle, and then click the line color, style, or weight options in the **Border** section of the Home tab.</span></span>  
  
2.  <span data-ttu-id="ce19d-119">Klicken Sie auf den Pfeil neben der Schaltfläche **Rahmen** , um zu bestimmen, welche Seiten des Rechtecks geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ce19d-119">Click the arrow next to the **Border** button to determine which sides of the rectangle to change.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce19d-120">Wenn Sie die Linienart auf **Double** festlegen und die Linienstärke 1 1/2 pt oder schmaler ist, wird die Linie möglicherweise nicht doppelt angezeigt, wenn Sie den Bericht in Berichts-Generator, Berichts-Designer oder Berichts-Manager ausführen.</span><span class="sxs-lookup"><span data-stu-id="ce19d-120">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="ce19d-121">Sie wird doppelt angezeigt, wenn Sie den Bericht in andere Formate wie Microsoft Word oder Acrobat PDF exportieren.</span><span class="sxs-lookup"><span data-stu-id="ce19d-121">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce19d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce19d-122">See Also</span></span>  
 <span data-ttu-id="ce19d-123">[Rechtecke und Linien &#40;Berichts-Generator und SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ce19d-123">[Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ce19d-124">Renderingverhalten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ce19d-124">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
