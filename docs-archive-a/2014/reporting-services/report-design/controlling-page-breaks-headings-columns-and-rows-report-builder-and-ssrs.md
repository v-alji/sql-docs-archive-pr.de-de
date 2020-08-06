---
title: Steuern von Seitenumbrüchen, Überschriften, Spalten und Zeilen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b8fa41f-a727-4f23-8efb-fd9bb0d4cd1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7dae06129ee5dc9962538e8d025dca9966325f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620209"
---
# <a name="controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs"></a><span data-ttu-id="c62d2-102">Steuern von Seitenumbrüchen, Überschriften, Spalten und Zeilen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c62d2-102">Controlling Page Breaks, Headings, Columns, and Rows (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c62d2-103">Ein Seitenumbruch unterteilt einen Bericht in getrennte Seiten, damit dieser einfacher angezeigt und gedruckt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c62d2-103">A page break divides a report into separate pages for viewing and printing.</span></span> <span data-ttu-id="c62d2-104">Seitenumbrüche legen fest, wie der Inhalt für die optimale Anzeige bei der Vorschau eines Berichts oder beim Exportieren in ein anderes Dateiformat an eine Berichtsseite angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="c62d2-104">Page breaks determine how the content is fitted to a report page for optimal viewing when you preview a report or export it to a different file format.</span></span>  
  
 <span data-ttu-id="c62d2-105">Das Hinzufügen von Seitenumbrüchen verbessert auch die Leistung großer Berichte bei der Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="c62d2-105">Adding page breaks also improves the performance of large reports when the are processed.</span></span> <span data-ttu-id="c62d2-106">Eine gerenderte Seite wird angezeigt, während die restlichen Seiten im Hintergrund gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="c62d2-106">A rendered page is displayed while the rest of the pages are rendered in the background.</span></span> <span data-ttu-id="c62d2-107">Dadurch können Sie die ersten Seiten des Berichts bereits anzeigen, während weitere Seiten erst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="c62d2-107">This allows you to begin viewing the initial pages of the report while waiting for additional pages to become available.</span></span>  
  
 <span data-ttu-id="c62d2-108">Seitenumbrüche können Berichtselementen hinzugefügt werden, wie Tabellen, Matrizen, Listen, Diagrammen, Messgeräten oder Bildern.</span><span class="sxs-lookup"><span data-stu-id="c62d2-108">Page breaks can be added to report items such as a table, matrix, list, chart, gauge, or image.</span></span> <span data-ttu-id="c62d2-109">Sie können Seitenumbrüche auch Gruppen in einer Tabelle, Matrix oder Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c62d2-109">You can also add page breaks to groups in a table, matrix, or list.</span></span> <span data-ttu-id="c62d2-110">Seitenumbrüche können vor, nach und zwischen Gruppen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c62d2-110">Page breaks can be added before, after, and between groups.</span></span> <span data-ttu-id="c62d2-111">Standardmäßig werden keine Seitenumbrüche zwischen Gruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c62d2-111">Page breaks between groups are not added to the report by default.</span></span>  
  
 <span data-ttu-id="c62d2-112">Weitere Informationen finden Sie unter [Anzeigen von Zeilen- und Spaltenüberschriften auf mehreren Seiten (Berichts-Generator und SSRS)](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) und [Sichtbarhalten von Kopfzeilen beim Scrollen durch einen Bericht (Berichts-Generator und SSRS)](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c62d2-112">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) and [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c62d2-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c62d2-113">See Also</span></span>  
 <span data-ttu-id="c62d2-114">[Listet &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c62d2-114">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c62d2-115">[Steuern der Tablix-Datenbereichsanzeige auf einer Berichtsseite (Berichts-Generator und SSRS)](controlling-the-tablix-data-region-display-on-a-report-page.md) </span><span class="sxs-lookup"><span data-stu-id="c62d2-115">[Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span></span>  
 <span data-ttu-id="c62d2-116">[Gruppierungsbereich (Berichts-Generator)](grouping-pane-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c62d2-116">[Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md) </span></span>  
 [<span data-ttu-id="c62d2-117">Anzeigen von Kopf- und Fußzeilen einer Gruppe &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c62d2-117">Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;</span></span>](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)  
  
  
