---
title: Sichtbarhalten von Kopfzeilen beim Scrollen durch einen Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6d9192a4-fd5c-41ad-b9ef-f88f9496afed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d37fcd38a402dc0f88ac002c679c1046d5b0b583
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723417"
---
# <a name="keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs"></a><span data-ttu-id="d3883-102">Sichtbarhalten von Kopfzeilen beim Durchführen eines Bildlaufs durch einen Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3883-102">Keep Headers Visible When Scrolling Through a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d3883-103">Damit Zeilen- und Spaltenbezeichnungen nach dem Rendern des Berichts bei einem Bildlauf nicht aus der Sicht verschwinden, können Sie die Zeilen- oder Spaltenüberschriften fixieren.</span><span class="sxs-lookup"><span data-stu-id="d3883-103">To prevent row and column labels from scrolling out of view after rendering a report, you can freeze the row or column headings.</span></span>  
  
 <span data-ttu-id="d3883-104">Wie Sie die Zeilen und Spalten steuern, hängt davon ab, ob Sie eine Tabelle oder eine Matrix verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3883-104">How you control the rows and columns depends on whether you have a table or a matrix.</span></span> <span data-ttu-id="d3883-105">Bei einer Tabelle konfigurieren Sie statische Elemente (Zeilen- und Spaltenüberschriften) so, dass diese sichtbar bleiben.</span><span class="sxs-lookup"><span data-stu-id="d3883-105">If you have a table, you configure static members (row and column headings) to remain visible.</span></span> <span data-ttu-id="d3883-106">Bei einer Matrix konfigurieren Sie die Kopfzeilen von Zeilen- und Spaltengruppen so, dass diese sichtbar bleiben.</span><span class="sxs-lookup"><span data-stu-id="d3883-106">If you have a matrix, you configure row and column group headers to remain visible.</span></span>  
  
 <span data-ttu-id="d3883-107">Wenn Sie den Bericht in Excel exportieren, wird der Header nicht automatisch fixiert.</span><span class="sxs-lookup"><span data-stu-id="d3883-107">If you export the report to Excel, the header will not be frozen automatically.</span></span> <span data-ttu-id="d3883-108">Sie können den Bereich in Excel fixieren.</span><span class="sxs-lookup"><span data-stu-id="d3883-108">You can freeze the pane in Excel.</span></span> <span data-ttu-id="d3883-109">Weitere Informationen finden Sie im Abschnitt **Seitenkopfzeilen und -fußzeilen** unter [Exportieren nach Microsoft Excel (Berichts-Generator und SSRS)](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d3883-109">For more information see the **Page Headers and Footers** section of [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3883-110">Selbst wenn eine Tabelle Zeilen- und Spaltengruppen enthält, ist es nicht möglich festzulegen, dass die Kopfzeilen dieser Gruppen beim Durchführen eines Bildlaufs immer sichtbar bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="d3883-110">Even if a table has row and column groups, you cannot keep those group headers visible while scrolling</span></span>  
  
 <span data-ttu-id="d3883-111">Die folgende Abbildung zeigt eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d3883-111">The following image shows a table.</span></span>  
  
 <span data-ttu-id="d3883-112">![Table](../media/table.png "Tabelle")</span><span class="sxs-lookup"><span data-stu-id="d3883-112">![Table](../media/table.png "Table")</span></span>  
  
 <span data-ttu-id="d3883-113">Die folgende Abbildung zeigt eine Matrix.</span><span class="sxs-lookup"><span data-stu-id="d3883-113">The following image shows a matrix.</span></span>  
  
 <span data-ttu-id="d3883-114">![Matrix](../media/matrix.png "Matrix")</span><span class="sxs-lookup"><span data-stu-id="d3883-114">![Matrix](../media/matrix.png "Matrix")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-keep-matrix-group-headers-visible-while-scrolling"></a><span data-ttu-id="d3883-115">So halten Sie die Gruppenkopfzeilen einer Matrix beim Bildlauf sichtbar</span><span class="sxs-lookup"><span data-stu-id="d3883-115">To keep matrix group headers visible while scrolling</span></span>  
  
1.  <span data-ttu-id="d3883-116">Klicken Sie im Tablix-Datenbereich mit der rechten Maustaste auf den Zeilen-, Spalten- oder Eckziehpunkt, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d3883-116">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="d3883-117">Wählen Sie auf der Registerkarte **Allgemein** unter **Zeilenköpfe** oder **Spaltenüberschriften**die Option **Die Kopfzeile sollte beim Ausführen eines Bildlaufs sichtbar bleiben**aus.</span><span class="sxs-lookup"><span data-stu-id="d3883-117">On the **General** tab, under **Row Headers** or **Column Headers**, select **Header should remain visible while scrolling**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-keep-a-static-tablix-member-row-or-column-visible-while-scrolling"></a><span data-ttu-id="d3883-118">So halten Sie ein statisches Tablix-Element (Zeile oder Spalte) bei einem Bildlauf sichtbar</span><span class="sxs-lookup"><span data-stu-id="d3883-118">To keep a static tablix member (row or column) visible while scrolling</span></span>  
  
1.  <span data-ttu-id="d3883-119">Klicken Sie auf der Entwurfsoberfläche auf eine beliebige Stelle in der Tabelle, um statische Elemente sowie Gruppen im Gruppierungsbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3883-119">On the design surface, click anywhere in the table to display static members, as well as groups, in the grouping pane.</span></span>  
  
     <span data-ttu-id="d3883-120">![Gruppierungsbereich](../media/grouppane-updated.png "Gruppierungsbereich")</span><span class="sxs-lookup"><span data-stu-id="d3883-120">![Grouping pane](../media/grouppane-updated.png "Grouping pane")</span></span>  
  
     <span data-ttu-id="d3883-121">In den Bereichen Zeilengruppen und Spaltengruppen werden die hierarchischen statischen und dynamischen Elemente für die Zeilengruppenhierarchie bzw. Spaltengruppenhierarchie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3883-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy, and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
2.  <span data-ttu-id="d3883-122">Klicken Sie auf der rechten Seite des Gruppierungsbereichs auf den nach unten weisenden Pfeil und anschließend auf **Erweiterter Modus**.</span><span class="sxs-lookup"><span data-stu-id="d3883-122">On the right side of the grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span>  
  
3.  <span data-ttu-id="d3883-123">Klicken Sie auf das statische Element (Zeile oder Spalte), das bei einem Bildlauf sichtbar bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="d3883-123">Click the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="d3883-124">Im Eigenschaftenbereich werden die Eigenschaften für das **Tablix-Element** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3883-124">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="d3883-125">![Tablix-Element-Eigenschaften](../media/grouppane-tablixmember-updated.png "Tablix-Element-Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="d3883-125">![Tablix Member properties](../media/grouppane-tablixmember-updated.png "Tablix Member properties")</span></span>  
  
4.  <span data-ttu-id="d3883-126">Legen Sie im Eigenschaften Bereich **FixedData** auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="d3883-126">In the Properties pane, set **FixedData** to `True`.</span></span>  
  
5.  <span data-ttu-id="d3883-127">Wiederholen Sie diesen Schritt für die angrenzenden Elemente, die bei einem Bildlauf sichtbar bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="d3883-127">Repeat this for as many adjacent members as you want to keep visible while scrolling.</span></span>  
  
6.  <span data-ttu-id="d3883-128">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="d3883-128">Preview the report.</span></span>  
  
 <span data-ttu-id="d3883-129">Während Sie durch den Bericht blättern, bleiben die statischen Tablix-Elemente sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d3883-129">As you page down or across the report, the static tablix members remain in view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3883-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3883-130">See Also</span></span>  
 <span data-ttu-id="d3883-131">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d3883-131">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d3883-132">[Suchen, Anzeigen und Verwalten von Berichten (Berichts-Generator und SSRS)](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d3883-132">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d3883-133">[Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d3883-133">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d3883-134">[Anzeigen von Kopf- und Fußzeilen einer Gruppe (Berichts-Generator und SSRS)](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d3883-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d3883-135">[Anzeigen von Zeilen- und Spaltenüberschriften auf mehreren Seiten (Berichts-Generator und SSRS)](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d3883-135">[Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d3883-136">Gruppierungsbereich (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="d3883-136">Grouping Pane &#40;Report Builder&#41;</span></span>](grouping-pane-report-builder.md)  
  
  
