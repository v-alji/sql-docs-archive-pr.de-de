---
title: Zusammenführen von Zellen in einem Datenbereich (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 43551300-89b2-4f4e-af09-69084324afaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c69ce8182bda3e0b644893e97b69280a003f5732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719552"
---
# <a name="merge-cells-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="10754-102">Zusammenführen von Zellen in einem Datenbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="10754-102">Merge Cells in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="10754-103">Sie können Zellen in einem Datenbereich zusammenführen, um Zellen zu kombinieren, die Darstellung des Datenbereichs zu verbessern oder umfassende Bezeichnungen für Spaltengruppen und Zeilengruppen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="10754-103">You can merge cells in a data region to combine cells, improve data region appearance, or provide spanning labels for column groups and row groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10754-104">Zellen können nur innerhalb der folgenden Bereiche eines Datenbereichs zusammengeführt werden: Ecke, Spaltenkopfzeilen, Gruppendefinition (oder Zeilenköpfe) und Textkörper.</span><span class="sxs-lookup"><span data-stu-id="10754-104">Cells can only be merged within each area of a data region: corner, column headers, group definition (or row headers), and body.</span></span> <span data-ttu-id="10754-105">Sie können keine Zellen zusammenführen, die über Bereichsgrenzen hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="10754-105">You cannot merge cells that cross area boundaries.</span></span> <span data-ttu-id="10754-106">Sie können beispielsweise eine Zelle im Eckbereich des Datenbereichs nicht mit einer Zelle im Zeilengruppenbereich zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="10754-106">For example, you cannot merge a cell in the data region corner area with a cell in the row group area.</span></span> <span data-ttu-id="10754-107">Weitere Informationen zu Tablix--Bereichen finden Sie unter [Listen &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="10754-107">For more information about tablix areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-merge-cells-in-a-data-region"></a><span data-ttu-id="10754-108">So führen Sie Zellen in einem Datenbereich zusammen</span><span class="sxs-lookup"><span data-stu-id="10754-108">To merge cells in a data region</span></span>  
  
1.  <span data-ttu-id="10754-109">Klicken Sie im Datenbereich auf der Berichtsentwurfsoberfläche auf die erste Zelle, die zusammengeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10754-109">In the data region on the report design surface, click the first cell to merge.</span></span> <span data-ttu-id="10754-110">Drücken Sie die linke Maustaste, und ziehen Sie den Mauszeiger vertikal oder horizontal, um angrenzende Zellen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="10754-110">Holding the left mouse button down, drag vertically or horizontally to select adjacent cells.</span></span> <span data-ttu-id="10754-111">Die ausgewählten Zellen werden markiert.</span><span class="sxs-lookup"><span data-stu-id="10754-111">The selected cells are highlighted.</span></span>  
  
2.  <span data-ttu-id="10754-112">Klicken Sie mit der rechten Maustaste auf die ausgewählten Zellen, und wählen Sie **Zellen zusammenführen**aus.</span><span class="sxs-lookup"><span data-stu-id="10754-112">Right-click the selected cells and select **Merge Cells**.</span></span> <span data-ttu-id="10754-113">Die ausgewählten Zellen werden zu einer einzigen Zelle kombiniert.</span><span class="sxs-lookup"><span data-stu-id="10754-113">The selected cells are combined into a single cell.</span></span>  
  
3.  <span data-ttu-id="10754-114">Wiederholen Sie die Schritte 1 und 2, um andere angrenzende Zellen in einem Datenbereich zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="10754-114">Repeat steps 1 and 2 to merge other adjacent cells in a data region.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10754-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10754-115">See Also</span></span>  
 <span data-ttu-id="10754-116">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10754-116">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10754-117">[Tabellen (Berichts-Generator und SSRS)](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10754-117">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10754-118">[Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10754-118">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10754-119">[Listet &#40;Berichts-Generator und SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10754-119">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="10754-120">Listen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="10754-120">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
