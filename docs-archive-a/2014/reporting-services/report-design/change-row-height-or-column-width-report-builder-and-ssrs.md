---
title: Ändern der Zeilenhöhe oder der Spaltenbreite (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5d75a8101d07d7d6e81c624d08cd951277936eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620214"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a><span data-ttu-id="f3d34-102">Ändern der Zeilenhöhe oder der Spaltenbreite (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="f3d34-102">Change Row Height or Column Width (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f3d34-103">Wenn Sie eine Zeilenhöhe festlegen, legen Sie damit die maximale Höhe der Zeile im gerenderten Bericht fest.</span><span class="sxs-lookup"><span data-stu-id="f3d34-103">When you set a row height, you are specifying the maximum height for the row in the rendered report.</span></span> <span data-ttu-id="f3d34-104">Textfelder in einer Zeile passen sich jedoch zur Laufzeit automatisch vertikal an die darin enthaltenen Daten an. Dies kann dazu führen, dass eine Zeile über die festgelegte Höhe hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="f3d34-104">However, by default, text boxes in the row are set to grow vertically to accommodate their data at run-time, and this can cause a row to expand beyond the height that you specify.</span></span> <span data-ttu-id="f3d34-105">Wenn Sie eine feste Zeilenhöhe definieren möchten, müssen Sie die Textfeldeigenschaften so ändern, dass sich die Zeile nicht automatisch ausdehnt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-105">To set a fixed row height, you must change the text box properties so they do not automatically expand.</span></span>  
  
 <span data-ttu-id="f3d34-106">Wenn Sie eine Spaltenbreite festlegen, legen Sie damit die maximale Breite der Spalte im gerenderten Bericht fest.</span><span class="sxs-lookup"><span data-stu-id="f3d34-106">When you set a column width, you are specifying the maximum width for the column in the rendered report.</span></span> <span data-ttu-id="f3d34-107">Spalten passen sich nicht automatisch horizontal an den darin enthaltenen Text an.</span><span class="sxs-lookup"><span data-stu-id="f3d34-107">Columns do not automatically adjust horizontally to accommodate text.</span></span>  
  
 <span data-ttu-id="f3d34-108">Falls eine Zelle in einer Zeile oder Spalte ein Rechteck oder einen Datenbereich enthält, werden die Mindesthöhe und -breite der Zelle durch die Höhe und Breite des darin enthaltenen Elements bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-108">If a cell in a row or column contains a rectangle or data region, the minimum height and width of the cell is determined by the height and width of the contained item.</span></span> <span data-ttu-id="f3d34-109">Weitere Informationen finden Sie unter [Renderingverhalten &#40;Berichts-Generator und SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f3d34-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a><span data-ttu-id="f3d34-110">So ändern Sie die Zeilenhöhe durch das Bewegen von Zeilenhandles</span><span class="sxs-lookup"><span data-stu-id="f3d34-110">To change row height by moving row handles</span></span>  
  
1.  <span data-ttu-id="f3d34-111">Klicken Sie in der Entwurfsansicht auf eine Stelle im Tablix-Datenbereich, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f3d34-111">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="f3d34-112">Graue Zeilenziehpunkte werden am Außenrand des Tablix-Datenbereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-112">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="f3d34-113">Zeigen Sie mit der Maus auf die Ziehpunktkante der Zeile, die Sie erweitern möchten.</span><span class="sxs-lookup"><span data-stu-id="f3d34-113">Hover over the row handle edge that you want to expand.</span></span> <span data-ttu-id="f3d34-114">Es wird ein Pfeil mit zwei Spitzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-114">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="f3d34-115">Klicken Sie mit der Maus, und ziehen Sie die Kante der Zeile nach oben oder unten, um die Zeilenhöhe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f3d34-115">Click to grab the edge of the row and move it higher or lower to adjust the row height.</span></span>  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a><span data-ttu-id="f3d34-116">So ändern Sie die Zeilenhöhe durch das Festlegen von Zelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="f3d34-116">To change row height by setting cell properties</span></span>  
  
1.  <span data-ttu-id="f3d34-117">Klicken Sie in der Ansicht Entwurf auf eine Zelle in der Tabellenzeile.</span><span class="sxs-lookup"><span data-stu-id="f3d34-117">In Design view, click a cell in the table row.</span></span>  
  
     <span data-ttu-id="f3d34-118">![Ausgewählte Zelle in einer Tabelle](../media/table-selectcell.png "Ausgewählte Zelle in einer Tabelle")</span><span class="sxs-lookup"><span data-stu-id="f3d34-118">![Selected Cell in a Table](../media/table-selectcell.png "Selected Cell in a Table")</span></span>  
  
2.  <span data-ttu-id="f3d34-119">Ändern Sie im angezeigten Bereich **Eigenschaften** die Eigenschaft **Höhe** , und klicken Sie anschließend auf eine beliebige Stelle außerhalb des Bereichs **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="f3d34-119">In the **Properties** pane that displays, modify the **Height** property, and then click anywhere outside the **Properties** pane.</span></span>  
  
     <span data-ttu-id="f3d34-120">![Eigenschaftenbereich für ausgewählte Tabellenzelle](../media/cell-propertiespane.png "Eigenschaftenbereich für ausgewählte Tabellenzelle")</span><span class="sxs-lookup"><span data-stu-id="f3d34-120">![Properties Pane for selected table cell](../media/cell-propertiespane.png "Properties Pane for selected table cell")</span></span>  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a><span data-ttu-id="f3d34-121">So deaktivieren Sie die automatische Ausdehnung einer Zeile</span><span class="sxs-lookup"><span data-stu-id="f3d34-121">To prevent a row from automatically expanding vertically</span></span>  
  
1.  <span data-ttu-id="f3d34-122">Klicken Sie in der Entwurfsansicht auf eine Stelle im Tablix-Datenbereich, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f3d34-122">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="f3d34-123">Graue Zeilenziehpunkte werden am Außenrand des Tablix-Datenbereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-123">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="f3d34-124">Klicken Sie auf den Zeilenziehpunkt, um die Zeile auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f3d34-124">Click the row handle to select the row.</span></span>  
  
3.  <span data-ttu-id="f3d34-125">Legen Sie im Eigenschaftenbereich CanGrow auf **FALSE**fest.</span><span class="sxs-lookup"><span data-stu-id="f3d34-125">In the Properties pane, set CanGrow to **False**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f3d34-126">Falls der Eigenschaftenbereich noch nicht angezeigt wird, klicken Sie im Menü **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f3d34-126">If you cannot see the Properties pane, from the **View** menu, click **Properties**.</span></span>  
  
### <a name="to-change-column-width"></a><span data-ttu-id="f3d34-127">So ändern Sie die Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="f3d34-127">To change column width</span></span>  
  
1.  <span data-ttu-id="f3d34-128">Klicken Sie in der Entwurfsansicht auf eine Stelle im Tablix-Datenbereich, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f3d34-128">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="f3d34-129">Graue Spaltenziehpunkte werden am Außenrand des Tablix-Datenbereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-129">Gray column handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="f3d34-130">Zeigen Sie mit der Maus auf die Ziehpunktkante der Spalte, die Sie erweitern möchten.</span><span class="sxs-lookup"><span data-stu-id="f3d34-130">Hover over the column handle edge that you want to expand.</span></span> <span data-ttu-id="f3d34-131">Es wird ein Pfeil mit zwei Spitzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3d34-131">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="f3d34-132">Klicken Sie mit der Maus, und ziehen Sie die Kante der Spalte nach links oder rechts, um die Spaltenbreite zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f3d34-132">Click to grab the edge of the column and move it left or right to adjust the column width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d34-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3d34-133">See Also</span></span>  
 <span data-ttu-id="f3d34-134">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f3d34-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f3d34-135">[Zellen, Zeilen und Spalten des Tablix-Datenbereichs &#40;Berichts-Generator&#41; und SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f3d34-135">[Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f3d34-136">[Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f3d34-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f3d34-137">[Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f3d34-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f3d34-138">[Listet &#40;Berichts-Generator und SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f3d34-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f3d34-139">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d34-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
