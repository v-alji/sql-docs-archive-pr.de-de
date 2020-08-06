---
title: Renderingverhalten (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8f873ef9-27a3-40e5-b58b-6774f8027a58
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d6a6aa91c547f4739b172f9303ac9e61bde5771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721145"
---
# <a name="rendering-behaviors-report-builder--and-ssrs"></a><span data-ttu-id="76344-102">Renderingverhalten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="76344-102">Rendering Behaviors (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="76344-103">Abhängig vom ausgewählten Renderer werden beim Rendern eines Berichts bestimmte Regeln auf den Hauptteil des Berichts und seinen Inhalt angewendet.</span><span class="sxs-lookup"><span data-stu-id="76344-103">Depending on the renderer you select, certain rules are applied to the report body and its contents when rendering a report.</span></span> <span data-ttu-id="76344-104">Wie sich Berichtselemente auf einer Seite zusammenfügen, wird durch die Kombination folgender Faktoren bestimmt:</span><span class="sxs-lookup"><span data-stu-id="76344-104">How report items fit together on a page is determined by the combination of these factors:</span></span>  
  
-   <span data-ttu-id="76344-105">Renderingregeln.</span><span class="sxs-lookup"><span data-stu-id="76344-105">Rendering rules.</span></span>  
  
-   <span data-ttu-id="76344-106">Die Breite und die Höhe von Berichtselementen.</span><span class="sxs-lookup"><span data-stu-id="76344-106">The width and height of report items.</span></span>  
  
-   <span data-ttu-id="76344-107">Die Größe des Berichtshauptteils.</span><span class="sxs-lookup"><span data-stu-id="76344-107">The size of the report body.</span></span>  
  
-   <span data-ttu-id="76344-108">Die Breite und die Höhe der Seite.</span><span class="sxs-lookup"><span data-stu-id="76344-108">The width and height of the page.</span></span>  
  
-   <span data-ttu-id="76344-109">Rendererspezifische Unterstützung für Auslagerungen.</span><span class="sxs-lookup"><span data-stu-id="76344-109">Renderer-specific support for paging.</span></span>  
  
 <span data-ttu-id="76344-110">Die allgemeinen Regeln, die von Reporting Services angewendet werden, werden in diesem Thema erläutert.</span><span class="sxs-lookup"><span data-stu-id="76344-110">This topic discusses the general rules that are applied by Reporting Services.</span></span> <span data-ttu-id="76344-111">Weitere Informationen finden Sie unter [Rendern von Berichtselementen (Berichts-Generator und SSRS)](rendering-report-items-report-builder-and-ssrs.md), [Rendern von Datenbereichen (Berichts-Generator und SSRS)](rendering-data-regions-report-builder-and-ssrs.md) und [Rendern von Daten (Berichts-Generator und SSRS)](rendering-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="76344-111">For more information, see [Rendering Report Items &#40;Report Builder and SSRS&#41;](rendering-report-items-report-builder-and-ssrs.md), [Rendering Data Regions &#40;Report Builder and SSRS&#41;](rendering-data-regions-report-builder-and-ssrs.md), and [Rendering Data &#40;Report Builder and SSRS&#41;](rendering-data-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="general-behaviors-for-html-mhtml-word-and-excel-soft-page-break-renderers"></a><span data-ttu-id="76344-112">Allgemeine Verhaltensweisen für HTML, MHTML, Word und Excel (Renderer mit weichem Seitenumbruch)</span><span class="sxs-lookup"><span data-stu-id="76344-112">General Behaviors for HTML, MHTML, Word, and Excel (Soft Page-Break Renderers)</span></span>  
 <span data-ttu-id="76344-113">Im HTML- und MHTML-Format exportierte Berichte sind für die Anzeige am Computerbildschirm optimiert, bei der Seiten unterschiedlich lang sein können.</span><span class="sxs-lookup"><span data-stu-id="76344-113">Reports exported using HTML and MHTML formats are optimized for a computer screen-based experience where pages can be various lengths.</span></span> <span data-ttu-id="76344-114">Seitenumbrüche werden vertikal nur an ungefähren Positionen im Berichtshauptteil eingefügt.</span><span class="sxs-lookup"><span data-stu-id="76344-114">Page breaks are inserted vertically only at approximate locations within the report body.</span></span> <span data-ttu-id="76344-115">Diese ungefähren Positionen werden durch die interaktive Höheneinstellung im Bereich Eigenschaften bestimmt.</span><span class="sxs-lookup"><span data-stu-id="76344-115">These approximate locations are determined by the interactive height setting in the Properties pane.</span></span> <span data-ttu-id="76344-116">Angenommen, die interaktive Höhe ist auf 5 Zoll festgelegt.</span><span class="sxs-lookup"><span data-stu-id="76344-116">For example, suppose the interactive height is set to 5 inches.</span></span> <span data-ttu-id="76344-117">Wenn der Bericht gerendert wird, beträgt die Seitenhöhe etwa 5 Zoll.</span><span class="sxs-lookup"><span data-stu-id="76344-117">When the report is rendered, the page height is approximately 5 inches in length.</span></span> <span data-ttu-id="76344-118">Word und Excel paginieren auf Grundlage logischer Seitenumbrüche und ignorieren die interaktive Höheneinstellung.</span><span class="sxs-lookup"><span data-stu-id="76344-118">Word and Excel paginate based on logical page breaks and ignore the interactive height setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76344-119">Um zu bestimmen, wie ein Bericht in einem Renderer mit weichem Seitenumbruch angezeigt wird, verwenden Sie die Berichtsvorschau.</span><span class="sxs-lookup"><span data-stu-id="76344-119">To determine how a report will appear in a soft page-break renderer, use Report Preview.</span></span> <span data-ttu-id="76344-120">Der Bericht wird so angezeigt, wie dies im HTML-, MHTML-, Word- bzw. Excel-Format der Fall wäre.</span><span class="sxs-lookup"><span data-stu-id="76344-120">The report appears as it would in a HTML, MHTML, Word, or Excel format.</span></span>  
  
 <span data-ttu-id="76344-121">Wenn Sie einen Bericht in HTML, MHTML, Word oder Excel exportieren, werden folgende allgemeine Regeln befolgt:</span><span class="sxs-lookup"><span data-stu-id="76344-121">When exporting a report to HTML, MHTML, Word, or Excel, the following general rules are followed:</span></span>  
  
-   <span data-ttu-id="76344-122">Logische Seitenumbrüche, die Seitenumbrüche, die Sie explizit einfügen, werden für Berichtselemente übernommen.</span><span class="sxs-lookup"><span data-stu-id="76344-122">Logical page breaks, the page breaks that you explicitly insert, are applied to report items.</span></span> <span data-ttu-id="76344-123">Wenn Sie beispielsweise zwischen den einzelnen Gruppen jeweils einen Seitenumbruch einfügen, werden sie beim Rendern des Berichts angewendet.</span><span class="sxs-lookup"><span data-stu-id="76344-123">For example, if you insert a page break between each group, they are applied when the report is rendered.</span></span>  
  
-   <span data-ttu-id="76344-124">Es wird ein ungefähres Layout erstellt, und zwar anhand der Seitenhöhe und der Anzahl der Vorkommnisse des Berichtselements.</span><span class="sxs-lookup"><span data-stu-id="76344-124">An approximate layout is created using the page height and the number of times that the report item appears.</span></span> <span data-ttu-id="76344-125">Wenn beispielsweise ein Textfeld eine Höhe von 0,5 Zoll aufweist und fünfmal in dem Bericht vorkommt, werden 2,5 Zoll reserviert.</span><span class="sxs-lookup"><span data-stu-id="76344-125">For example, if a text box is .5 inches in height and repeats five times in the report, 2.5 inches are reserved.</span></span>  
  
-   <span data-ttu-id="76344-126">Mehrere weiche Seitenumbrüche werden auf Grundlage der interaktiven Höheneinstellung eingefügt.</span><span class="sxs-lookup"><span data-stu-id="76344-126">Multiple soft page breaks are inserted based on the interactive height setting.</span></span> <span data-ttu-id="76344-127">Wenn die Unterdrückung in HTML und den ReportViewer-Steuerelementen erfolgen und die Paginierung lediglich mit expliziten Seitenumbrüchen gesteuert werden soll, stellen Sie den Wert für die **interactive height** auf 0 oder eine extrem hohe Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="76344-127">To suppress in HTML and the ReportViewer controls, and control pagination only with explicit page breaks, set the **interactive height** value to 0 or an extremely large number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76344-128">Die interaktive Breiteneinstellung wird in den Renderern mit weichem Seitenumbruch nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76344-128">The interactive width setting is not used in the soft page break renderers.</span></span>  
  
-   <span data-ttu-id="76344-129">Berichtsseiten können größer werden, um allein stehende Absatzzeilen, Waisen und Berichtselemente aufzunehmen, die zusammenbleiben müssen.</span><span class="sxs-lookup"><span data-stu-id="76344-129">Report pages can grow to accommodate widows, orphans and report items that need to be kept together.</span></span> <span data-ttu-id="76344-130">Der Bericht kann also über die Bildschirmbreite hinaus erweitert werden; zur Anzeige werden dann Schieberegler verwendet.</span><span class="sxs-lookup"><span data-stu-id="76344-130">This means that the report can extend beyond the screen width and can be viewed by using slider bars.</span></span>  
  
-   <span data-ttu-id="76344-131">Die Paginierung wird nur vertikal für Berichte übernommen.</span><span class="sxs-lookup"><span data-stu-id="76344-131">Pagination is applied to reports vertically only.</span></span>  
  
-   <span data-ttu-id="76344-132">Seitenränder werden nicht übernommen.</span><span class="sxs-lookup"><span data-stu-id="76344-132">Page margins are not applied.</span></span>  
  
## <a name="general-behaviors-for-pdf-image-and-print-hard-page-break-renderers"></a><span data-ttu-id="76344-133">Allgemeine Verhaltensweisen für PDF, Bild und Drucken (Renderer mit hartem Seitenumbruch)</span><span class="sxs-lookup"><span data-stu-id="76344-133">General Behaviors for PDF, Image, and Print (Hard Page-Break Renderers)</span></span>  
 <span data-ttu-id="76344-134">Berichte, die im PDF- und Bild-Format exportiert werden, sind für den buch- oder dokumentationsähnlichen Druck optimiert, bei dem Seiten eine konsistente Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="76344-134">Reports exported using PDF and Image are optimized for a book-like or printed experience where pages are a consistent size.</span></span> <span data-ttu-id="76344-135">Seitenumbrüche werden vertikal und horizontal an bestimmten Positionen im Berichtshauptteil eingefügt.</span><span class="sxs-lookup"><span data-stu-id="76344-135">Page breaks are inserted vertically and horizontally at specific locations within the report body.</span></span> <span data-ttu-id="76344-136">Diese bestimmten Positionen werden durch die Einstellungen für Seitenbreite und -höhe bestimmt.</span><span class="sxs-lookup"><span data-stu-id="76344-136">These specific locations are determined by the page width and page height settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76344-137">Um zu bestimmen, wie ein Bericht in einem Renderer mit hartem Seitenumbruch angezeigt wird, verwenden Sie die Seitenansicht.</span><span class="sxs-lookup"><span data-stu-id="76344-137">To determine how a report will appear in a hard page-break renderer, use Print Preview.</span></span> <span data-ttu-id="76344-138">Der Bericht wird so angezeigt, wie dies im PDF- oder Bild-Format der Fall wäre.</span><span class="sxs-lookup"><span data-stu-id="76344-138">The report appears as it would in a PDF or Image format.</span></span>  
  
-   <span data-ttu-id="76344-139">Seiten werden sequenziell von links nach rechts nummeriert, dann von oben nach unten.</span><span class="sxs-lookup"><span data-stu-id="76344-139">Pages are numbered sequentially from left to right, then top to bottom.</span></span>  
  
-   <span data-ttu-id="76344-140">Logische Seitenumbrüche, die Seitenumbrüche, die Sie explizit einfügen, werden für Berichtselemente übernommen.</span><span class="sxs-lookup"><span data-stu-id="76344-140">Logical page breaks, the page breaks that you explicitly insert, are applied to report items.</span></span> <span data-ttu-id="76344-141">Diese Seitenumbrüche können bewirken, dass Berichtselemente andere Elemente auf die nächste Seite schieben.</span><span class="sxs-lookup"><span data-stu-id="76344-141">These page breaks can cause report items to push other items to the next page.</span></span>  
  
-   <span data-ttu-id="76344-142">Wenn ein physischer Seitenumbruch Berichtselemente trennt, die zusammenbleiben müssen, werden die Elemente, die zusammenbleiben müssen, auf die nächste Seite verschoben.</span><span class="sxs-lookup"><span data-stu-id="76344-142">If a physical page break occurs through report items that must be kept together, the items that must be kept together are moved to the next page.</span></span>  
  
-   <span data-ttu-id="76344-143">Aufgrund der Seitengrößenbeschränkungen ist es unter Umständen nicht möglich, dass alle Elemente zusammenbleiben bzw. dass Elemente wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="76344-143">Because of page size constraints, it may not be possible to keep all the items together or to repeat items.</span></span> <span data-ttu-id="76344-144">In diesem Fall ignoriert der Renderer bei einem anderen Element möglicherweise bestimmte Wiederholungsregeln, damit das Berichtselement auf die Seite passt.</span><span class="sxs-lookup"><span data-stu-id="76344-144">If that occurs, the renderer might ignore certain rules for repeating with another item in order to allow the report item to fit on the page.</span></span>  
  
-   <span data-ttu-id="76344-145">Wenn ein Element nicht zusammenbleiben kann, beispielsweise ein Textfeld, das zu groß für den vertikalen nutzbaren Seitenbereich wird, wird das Element an der physischen Seitengrenze abgeschnitten und auf der nächsten Seite fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="76344-145">If an item cannot be kept together, for example a text box that grows too large to fit within the vertical usable page area, then the item will be clipped at the physical page boundary and will continue on the next page.</span></span>  
  
-   <span data-ttu-id="76344-146">Die Paginierung wird vertikal und horizontal für Berichte übernommen.</span><span class="sxs-lookup"><span data-stu-id="76344-146">Pagination is applied to reports vertically and horizontally.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76344-147">Die interaktive Breiteneinstellung wird in den Renderern mit hartem Seitenumbruch nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76344-147">The interactive width setting is not used in the hard page break renderers.</span></span>  
  
## <a name="minimum-spacing-between-report-items"></a><span data-ttu-id="76344-148">Minimaler Abstand zwischen Berichtselementen</span><span class="sxs-lookup"><span data-stu-id="76344-148">Minimum Spacing Between Report Items</span></span>  
 <span data-ttu-id="76344-149">Berichtselemente wachsen innerhalb des Hauptteils des Berichts, um ihren Inhalt aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="76344-149">Report items grow within the report body to accommodate their contents.</span></span> <span data-ttu-id="76344-150">So wird beispielsweise ein Matrixdatenbereich beim Rendern des Berichts normalerweise zur Seite und nach unten erweitert, und die Höhe eines Textfelds ändert sich abhängig von den Daten, die von einem Ausdruck zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="76344-150">For example, a matrix data region typically expands across and down the page when the report is rendered, and the height of a text box adjusts depending on the data returned from an expression.</span></span>  
  
 <span data-ttu-id="76344-151">Renderer behalten den minimalen Abstand zwischen Berichtselementen bei, die Sie im Berichtslayout definieren.</span><span class="sxs-lookup"><span data-stu-id="76344-151">Renderers maintain the minimum space between report items that you define in the report layout.</span></span> <span data-ttu-id="76344-152">Wenn Sie ein Berichtselement im Berichtslayout neben einem anderen platzieren, wird der Abstand zwischen den Berichtselementen zum Mindestabstand, der bei der horizontalen bzw. vertikalen Erweiterung des Berichts beibehalten werden muss.</span><span class="sxs-lookup"><span data-stu-id="76344-152">When you place a report item adjacent to another on the report layout, the distance between the report items becomes the minimum distance that must be maintained as the report grows horizontally or vertically.</span></span> <span data-ttu-id="76344-153">Wenn Sie beispielsweise einen Matrixdatenbereich einem Bericht hinzufügen und dann ein Rechteck 0,25 Zoll rechts von der Matrix hinzufügen, wird dieser Abstand beibehalten, wenn die Matrix größer wird.</span><span class="sxs-lookup"><span data-stu-id="76344-153">For example, if you add a matrix data region to a report and then add a rectangle .25 inches to the right of the matrix, that space is maintained as the matrix grows.</span></span> <span data-ttu-id="76344-154">Jedes Element wird nach rechts verschoben, um den Mindestabstand zu Elementen beizubehalten, die links von ihm enden.</span><span class="sxs-lookup"><span data-stu-id="76344-154">Each item moves to the right to maintain the minimum distance from items that end to the left of it.</span></span>  
  
## <a name="page-headers-and-footers"></a><span data-ttu-id="76344-155">Seitenkopfzeilen und -fußzeilen</span><span class="sxs-lookup"><span data-stu-id="76344-155">Page Headers and Footers</span></span>  
 <span data-ttu-id="76344-156">Seitenkopf- und -fußzeilen werden am oberen und unteren Rand der einzelnen gerenderten Seiten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76344-156">Page headers and footers appear at the top and bottom of each rendered page.</span></span> <span data-ttu-id="76344-157">Sie können für den Seitenkopf und die Seitenfußzeile eine Rahmenfarbe, Rahmenart und Rahmenbreite formatieren.</span><span class="sxs-lookup"><span data-stu-id="76344-157">You can format the page header and footer so that there is a border color, border style, and border width.</span></span> <span data-ttu-id="76344-158">Sie können auch eine Hintergrundfarbe oder ein Hintergrundbild hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="76344-158">You can also add a background color or background image.</span></span> <span data-ttu-id="76344-159">Diese Formatierungsoptionen werden alle gerendert, abhängig von dem Format, das Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="76344-159">These formatting options are all rendered, depending on the format that you choose.</span></span>  
  
 <span data-ttu-id="76344-160">Folgende Regeln gelten für Seitenköpfe und -füße, die im HTML- oder MHTML-Rendering-Format gerendert werden:</span><span class="sxs-lookup"><span data-stu-id="76344-160">The following rules apply to page headers and footers when rendered in the HTML or MHTML rendering format:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76344-161">Informationen zum Rendern von Kopf- und Fußzeilen in Excel finden Sie unter [Exportieren nach Microsoft Excel (Berichts-Generator und SSRS)](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="76344-161">For information about how Excel renders headers and footers, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="76344-162">Informationen zum Rendern von Kopf- und Fußzeilen in Word finden Sie unter [Exportieren nach Microsoft Word (Berichts-Generator und SSRS)](../report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="76344-162">For information about how Word renders headers and footers, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="76344-163">Sind Kopf- und Fußzeilen vorhanden, werden sie am oberen und unteren Rand der einzelnen Seiten innerhalb des nutzbaren Seitenbereichs gerendert.</span><span class="sxs-lookup"><span data-stu-id="76344-163">When present, the header and footer is rendered at the top and bottom of every page within the usable page area.</span></span>  
  
-   <span data-ttu-id="76344-164">Auf Seiten, auf denen die Kopf- bzw. Fußzeile ausgeblendet ist, bleibt die Höhe der Kopf- bzw. Fußzeile im nutzbaren Seitenbereich weiterhin reserviert, obwohl die Kopf- bzw. Fußzeile nicht gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="76344-164">On pages where the header or footer is hidden, the height of the header or footer is still reserved within the usable page area, even though the header or footer is not rendered.</span></span>  
  
-   <span data-ttu-id="76344-165">Wenn der Inhalt des Headers bzw. der Fußzeile über die Grenzen der Kopf- bzw. Fußzeile hinausgeht, wird die Größe der Kopf- bzw. Fußzeile angepasst, um den Inhalt aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="76344-165">If the contents of the header or footer grows beyond the boundaries of the header or footer, the header or footer increases in size to accommodate the contents.</span></span>  
  
 <span data-ttu-id="76344-166">Folgende Regeln gelten für Seitenköpfe und -füße, die im PDF- oder Bild-Rendering-Format gerendert werden:</span><span class="sxs-lookup"><span data-stu-id="76344-166">The following rules apply to page headers and footers when rendered in the PDF or Image rendering format:</span></span>  
  
-   <span data-ttu-id="76344-167">Die Kopf- bzw. Fußzeile wird am oberen und unteren Rand der einzelnen Seiten innerhalb des nutzbaren Seitenbereichs gerendert.</span><span class="sxs-lookup"><span data-stu-id="76344-167">The header or footer is rendered at the top and bottom of every page within the usable page area.</span></span>  
  
-   <span data-ttu-id="76344-168">Auf Seiten, auf denen die Kopf- bzw. Fußzeile ausgeblendet ist, bleibt die Höhe der Kopf- bzw. Fußzeile im nutzbaren Seitenbereich weiterhin reserviert, obwohl die Kopf- bzw. Fußzeile nicht gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="76344-168">On pages where the header or footer is hidden, the height of the header or footer is still reserved within the usable page area, even though the header or footer is not rendered.</span></span>  
  
-   <span data-ttu-id="76344-169">Der Header und die Fußzeile werden weder größer noch kleiner.</span><span class="sxs-lookup"><span data-stu-id="76344-169">The header and footer do not grow or shrink.</span></span> <span data-ttu-id="76344-170">Sie werden auf jeder Seite in der Höhe gerendert, die bei der Erstellung der Kopf- bzw. Fußzeile angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="76344-170">They are rendered on every page at the height specified when you created the header or footer.</span></span>  
  
-   <span data-ttu-id="76344-171">Ungeachtet der Anzahl an Spalten im Bericht gibt es nur eine Kopf- und eine Fußzeile pro Seite.</span><span class="sxs-lookup"><span data-stu-id="76344-171">Regardless of the number of columns within the report, there is only one header and footer per page.</span></span>  
  
-   <span data-ttu-id="76344-172">Wenn der Inhalt der Kopf- bzw. Fußzeile über die Grenzen der Kopf- bzw. Fußzeile hinausgeht, wird der Inhalt abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="76344-172">If the contents of the header or footer grow beyond the boundaries of the header or footer, the contents are clipped.</span></span>  
  
-   <span data-ttu-id="76344-173">Kopf- und Fußzeilen, die in der ursprünglichen RDL-Datei definiert wurden, werden nicht gerendert, wenn der Bericht als Unterbericht gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="76344-173">Headers and footers that are defined in the original RDL file are not rendered when the report is rendered as a subreport.</span></span>  
  
## <a name="logical-page-breaks"></a><span data-ttu-id="76344-174">Logische Seitenumbrüche</span><span class="sxs-lookup"><span data-stu-id="76344-174">Logical Page Breaks</span></span>  
 <span data-ttu-id="76344-175">Logische Seitenumbrüche sind Seitenumbrüche, die vor oder nach Berichtselementen oder -gruppen eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="76344-175">Logical page breaks are page breaks that you insert before or after report items or groups.</span></span> <span data-ttu-id="76344-176">Mithilfe von Seitenumbrüchen können Sie festlegen, wie beim Rendern oder Exportieren des Berichts Inhalt für die optimale Anzeige auf einer Berichtsseite angeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="76344-176">Page breaks help to determine how the content is fitted to a report page for optimal viewing when rendering or exporting the report.</span></span>  
  
 <span data-ttu-id="76344-177">Folgende Regeln gelten beim Rendern logischer Seitenumbrüche:</span><span class="sxs-lookup"><span data-stu-id="76344-177">The following rules apply when rendering logical page breaks:</span></span>  
  
-   <span data-ttu-id="76344-178">Logische Seitenumbrüche werden bei Berichtselementen ignoriert, die dauerhaft ausgeblendet sind, und bei Berichtselementen, deren Sichtbarkeit durch Klicken auf ein anderes Berichtselement gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="76344-178">Logical page breaks are ignored for report items that are constantly hidden and for report items where the visibility is controlled by clicking another report item.</span></span>  
  
-   <span data-ttu-id="76344-179">Logische Seitenumbrüche werden auf bedingt sichtbare Elemente angewendet, wenn Sie zum Renderzeitpunkt des Berichts sichtbar waren.</span><span class="sxs-lookup"><span data-stu-id="76344-179">Logical page breaks are applied on conditionally visible items if they are currently visible at the time the report is rendered.</span></span>  
  
-   <span data-ttu-id="76344-180">Der Abstand zwischen dem Berichtselement mit dem logischen Seitenumbruch und seinen Peer-Berichtselementen wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="76344-180">Space is preserved between the report item with the logical page break and its peer report items.</span></span>  
  
-   <span data-ttu-id="76344-181">Logische Seitenumbrüche, die vor einem Berichtselement eingefügt werden, bewirken, dass das Berichtselement auf die nächste Seite verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="76344-181">Logical page breaks that are inserted before a report item push the report item down to the next page.</span></span> <span data-ttu-id="76344-182">Das Berichtselement wird am Anfang der nächsten Seite gerendert.</span><span class="sxs-lookup"><span data-stu-id="76344-182">The report item is rendered at the top of the next page.</span></span>  
  
-   <span data-ttu-id="76344-183">Logische Seitenumbrüche, die für Elemente in einer Tabellen- oder Matrixzelle definiert wurden, werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="76344-183">Logical page breaks defined on items in table or matrix cells are not kept.</span></span> <span data-ttu-id="76344-184">Dies gilt nicht für Listenelemente.</span><span class="sxs-lookup"><span data-stu-id="76344-184">This does not apply to items in lists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76344-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76344-185">See Also</span></span>  
 <span data-ttu-id="76344-186">[Interaktive Funktionalität für verschiedene Berichtsrenderingerweiterungen &#40;Berichts-Generator und SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="76344-186">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="76344-187">[Rendern in HTML (Berichts-Generator und SSRS)](../report-builder/rendering-to-html-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76344-187">[Rendering to HTML &#40;Report Builder and SSRS&#41;](../report-builder/rendering-to-html-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="76344-188">Seitenlayout und Rendering &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="76344-188">Page Layout and Rendering &#40;Report Builder and SSRS&#41;</span></span>](page-layout-and-rendering-report-builder-and-ssrs.md)  
  
  