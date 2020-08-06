---
title: Anzeigen von Zeilen- und Spaltenüberschriften auf mehreren Seiten (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e3b38aa0faab267a0cd71feafe600829237b55c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721172"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a><span data-ttu-id="b8732-102">Anzeigen von Zeilen- und Spaltenüberschriften auf mehreren Seiten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b8732-102">Display Row and Column Headers on Multiple Pages (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b8732-103">Sie können festlegen, ob bei einem Tablix-Datenbereich, der mehrere Seiten umfasst, Zeilen- und Spaltenüberschriften auf jeder Seite wiederholt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b8732-103">You can control whether to repeat row and column headers on every page for a tablix data region that spans multiple pages.</span></span> <span data-ttu-id="b8732-104">Ein Tablix-Datenbereich kann eine Tabelle, eine Matrix oder eine Liste sein.</span><span class="sxs-lookup"><span data-stu-id="b8732-104">A tablix data region can be a table, matrix, or list.</span></span>  
  
 <span data-ttu-id="b8732-105">Wie Zeilen und Spalten behandelt werden, hängt davon ab, ob der Tablix-Datenbereich Gruppenkopfzeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="b8732-105">How you control the rows and columns depends on whether the tablix data region has group headers.</span></span> <span data-ttu-id="b8732-106">Wenn Sie auf einen Tablix-Datenbereich klicken, der Gruppenkopfzeilen enthält, wird eine gepunktete Linie in den Tablix-Bereichen angezeigt, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b8732-106">When you click in a tablix data region that has group headers, a dotted line shows the tablix areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="b8732-107">![Zonen des Tablix-Datenbereichs](../media/rs-tablixareas.gif "Zonen des Tablix-Datenbereichs")</span><span class="sxs-lookup"><span data-stu-id="b8732-107">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="b8732-108">Zeilen- und Spaltengruppenkopfzeilen werden automatisch erstellt, wenn Sie Gruppen mit dem Tabellen- oder Matrix-Assistenten bzw. dem Diagramm-Assistenten hinzufügen, indem Felder zu dem Gruppierungsbereich hinzugefügt oder Kontextmenüs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8732-108">Row and column group headers are created automatically when you add groups by using the New Table or Matrix wizard or the New Chart wizard, by adding fields to the Grouping pane, or by using context menus.</span></span> <span data-ttu-id="b8732-109">Wenn der Tablix-Datenbereich nur einen Tablix-Textbereich und keine Gruppenkopfzeilen enthält, sind die Zeilen und Spalten Tablix-Elemente.</span><span class="sxs-lookup"><span data-stu-id="b8732-109">If the tablix data region has only a tablix body area and no group headers, the rows and columns are tablix members.</span></span>  
  
 <span data-ttu-id="b8732-110">Bei statischen Elementen können Sie die obersten angrenzenden Zeilen oder die seitlichen angrenzenden Spalten auf mehreren Seiten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8732-110">For static members, you can display the top adjacent rows or the side adjacent columns on multiple pages.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a><span data-ttu-id="b8732-111">So zeigen Sie Zeilenüberschriften auf mehreren Seiten an</span><span class="sxs-lookup"><span data-stu-id="b8732-111">To display row headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="b8732-112">Klicken Sie im Tablix-Datenbereich mit der rechten Maustaste auf den Zeilen-, Spalten- oder Eckziehpunkt, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b8732-112">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="b8732-113">Wählen Sie unter **Zeilenüberschriften**die Option **Kopfzeile auf jeder Seite wiederholen**aus.</span><span class="sxs-lookup"><span data-stu-id="b8732-113">In **Row Headers**, select **Repeat header rows on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a><span data-ttu-id="b8732-114">So zeigen Sie Spaltenüberschriften auf mehreren Seiten an</span><span class="sxs-lookup"><span data-stu-id="b8732-114">To display column headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="b8732-115">Klicken Sie im Tablix-Datenbereich mit der rechten Maustaste auf den Zeilen-, Spalten- oder Eckziehpunkt, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b8732-115">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="b8732-116">Wählen Sie unter **Spaltenkopfzeilen**die Option **Spaltenüberschrift auf jeder Seite wiederholen**aus.</span><span class="sxs-lookup"><span data-stu-id="b8732-116">In **Column Headers**, select **Repeat header columns on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a><span data-ttu-id="b8732-117">So zeigen Sie ein statisches Tablix-Element (Zeile oder Spalte) auf mehreren Seiten an</span><span class="sxs-lookup"><span data-stu-id="b8732-117">To display a static tablix member (row or column) on multiple pages</span></span>  
  
1.  <span data-ttu-id="b8732-118">Klicken Sie auf der Entwurfsoberfläche auf den Zeilen- oder Spaltenziehpunkt des Tablix-Datenbereichs, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b8732-118">On the design surface, click the row or column handle of the tablix data region to select it.</span></span> <span data-ttu-id="b8732-119">Im Gruppierungsbereich werden die Zeilen- und Spaltengruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8732-119">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="b8732-120">Klicken Sie auf der rechten Seite des Gruppierungsbereichs auf den Pfeil nach unten und anschließend auf **Erweiterter Modus**.</span><span class="sxs-lookup"><span data-stu-id="b8732-120">On the right side of the Grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span> <span data-ttu-id="b8732-121">In den Bereichen Zeilengruppen und Spaltengruppen werden die hierarchischen und statischen Elemente für die Zeilengruppenhierarchie bzw. Spaltengruppenhierarchie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8732-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
3.  <span data-ttu-id="b8732-122">Klicken Sie auf das statische Element, das dem statischen Element (Zeile oder Spalte) entspricht, das beim Bildlauf sichtbar bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="b8732-122">Click the static member that corresponds to the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="b8732-123">Im Eigenschaftenbereich werden die Eigenschaften für das **Tablix-Element** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8732-123">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="b8732-124">Wenn der Eigenschaftenbereich nicht angezeigt wird, klicken Sie am oberen Rand des Fensters Berichts-Generator auf die Registerkarte **Ansicht** und dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b8732-124">If you don't see the Properties pane, click the **View** tab at the top of the Report Builder window and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b8732-125">Legen Sie im Eigenschaftenbereich **RepeatOnNewPage** auf True fest.</span><span class="sxs-lookup"><span data-stu-id="b8732-125">In the Properties pane, set **RepeatOnNewPage** to True.</span></span>  
  
5.  <span data-ttu-id="b8732-126">Legen Sie **KeepWithGroup** auf After fest.</span><span class="sxs-lookup"><span data-stu-id="b8732-126">Set **KeepWithGroup** to After.</span></span>  
  
6.  <span data-ttu-id="b8732-127">Wiederholen Sie diesen Schritt für alle angrenzenden Elemente, die wiederholt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b8732-127">Repeat this for as many adjacent members as you want to repeat.</span></span>  
  
7.  <span data-ttu-id="b8732-128">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="b8732-128">Preview the report.</span></span>  
  
 <span data-ttu-id="b8732-129">Während Sie jede Seite des Berichts anzeigen, über die sich der Tablix-Datenbereich erstreckt, werden die statischen Tablix-Elemente auf jeder Seite wiederholt.</span><span class="sxs-lookup"><span data-stu-id="b8732-129">As you view each page of the report that the tablix data region spans, the static tablix members repeat on each page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8732-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8732-130">See Also</span></span>  
 <span data-ttu-id="b8732-131">[Suchen, Anzeigen und Verwalten von Berichten (Berichts-Generator und SSRS)](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b8732-131">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b8732-132">[Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b8732-132">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b8732-133">[Steuern von Seitenumbrüchen, Überschriften, Spalten und Zeilen &#40;Berichts-Generator und SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b8732-133">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b8732-134">[Anzeigen von Kopf- und Fußzeilen einer Gruppe (Berichts-Generator und SSRS)](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b8732-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b8732-135">Sichtbarhalten von Kopfzeilen beim Durchführen eines Bildlaufs durch einen Bericht &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b8732-135">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  
