---
title: Erstellen von abgestuften Berichten (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5933c4f0-c713-4ecb-b521-ff46c9c63fff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d845993ac1462cef2d39638101e5c7b9fc314b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616422"
---
# <a name="create-a-stepped-report-report-builder-and-ssrs"></a><span data-ttu-id="ee1df-102">Erstellen von abgestuften Berichten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ee1df-102">Create a Stepped Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ee1df-103">Ein abgestufter Bericht zeigt Detailzeilen oder Untergruppen wie im folgenden Beispiel unter einer übergeordneten Gruppe eingerückt in der gleichen Spalte an.</span><span class="sxs-lookup"><span data-stu-id="ee1df-103">A stepped report shows detail rows or child groups indented under a parent group in the same column, as shown in the example below:</span></span>  
  
 <span data-ttu-id="ee1df-104">![Gerenderter abgestufter Bericht](../media/steppedreportrendered.gif "Gerenderter abgestufter Bericht")</span><span class="sxs-lookup"><span data-stu-id="ee1df-104">![Rendered stepped report](../media/steppedreportrendered.gif "Rendered stepped report")</span></span>  
  
 <span data-ttu-id="ee1df-105">Bei herkömmlichen Tabellenberichten wird die übergeordnete Gruppe in einer angrenzenden Spalte im Bericht platziert.</span><span class="sxs-lookup"><span data-stu-id="ee1df-105">Traditional table reports place the parent group in an adjacent column on the report.</span></span> <span data-ttu-id="ee1df-106">Der neue Tablix-Datenbereich ermöglicht es Ihnen, eine Gruppe und Detailzeilen bzw. Untergruppen zur gleichen Spalte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee1df-106">The new tablix data region enables you to add a group and detail rows or child groups to the same column.</span></span> <span data-ttu-id="ee1df-107">Um die Gruppenzeilen von den Detailzeilen oder Zeilen untergeordneter Gruppen zu unterscheiden, können Sie entweder eine Formatierung wie eine Schriftfarbe anwenden oder die Detailzeilen mit einem Einzug versehen.</span><span class="sxs-lookup"><span data-stu-id="ee1df-107">To differentiate the group rows from the detail or child group rows, you can apply formatting such as font color, or you can indent the detail rows.</span></span>  
  
 <span data-ttu-id="ee1df-108">Die Verfahren in diesem Thema veranschaulichen das manuelle Erstellen eines abgestuften Berichts. Sie können jedoch auch den Assistenten zum Erstellen neuer Tabellen und Matrizen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee1df-108">The procedures in this topic show you how to manually create a stepped report, but you can also use the New Table and Matrix Wizard.</span></span> <span data-ttu-id="ee1df-109">Der Assistent stellt das Layout für abgestufte Berichte bereit und erleichtert die Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="ee1df-109">It provides the layout for stepped reports, making it easy to create them.</span></span> <span data-ttu-id="ee1df-110">Nachdem Sie den Assistenten abgeschlossen haben, können Sie den Bericht optimieren.</span><span class="sxs-lookup"><span data-stu-id="ee1df-110">After you complete the wizard, you can further enhance the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee1df-111">Der Assistent ist nur in Berichts-Generator verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ee1df-111">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-stepped-report"></a><span data-ttu-id="ee1df-112">So erstellen Sie einen abgestuften Bericht</span><span class="sxs-lookup"><span data-stu-id="ee1df-112">To create a stepped report</span></span>  
  
1.  <span data-ttu-id="ee1df-113">Erstellen Sie einen Tabellenbericht.</span><span class="sxs-lookup"><span data-stu-id="ee1df-113">Create a table report.</span></span> <span data-ttu-id="ee1df-114">Fügen Sie z. B. einen Tablix-Datenbereich ein, und fügen Sie der Datenzeile Felder hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee1df-114">For example, insert a tablix data region and add fields to the Data row.</span></span>  
  
2.  <span data-ttu-id="ee1df-115">Fügen Sie dem Bericht eine übergeordnete Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee1df-115">Add a parent group to your report.</span></span>  
  
    1.  <span data-ttu-id="ee1df-116">Klicken Sie in der Tabelle an einer beliebigen Stelle, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ee1df-116">Click anywhere in the table to select it.</span></span> <span data-ttu-id="ee1df-117">Im Gruppierungsbereich wird die Gruppe Details im Bereich Zeilengruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee1df-117">The Grouping pane displays the Details group in the Row Groups pane.</span></span>  
  
    2.  <span data-ttu-id="ee1df-118">Klicken Sie im Gruppierungsbereich mit der rechten Maustaste auf die Gruppe „Details“, zeigen Sie auf **Gruppe hinzufügen**, und klicken Sie dann auf **Übergeordnete Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="ee1df-118">In the Grouping Pane, right-click the Details Group, point to **Add Group**, and then click **Parent Group**.</span></span>  
  
    3.  <span data-ttu-id="ee1df-119">Geben Sie im Dialogfeld **Tablix-Gruppe** einen Namen für die Gruppe an, und wählen Sie in der Dropdownliste einen Gruppierungsausdruck aus, bzw. geben Sie manuell einen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="ee1df-119">In the **Tablix Group** dialog box, provide a name for the group and type or select a group expression from the drop-down list.</span></span> <span data-ttu-id="ee1df-120">Die Dropdownliste zeigt die einfachen Feldausdrücke an, die im Berichtsdatenbereich verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ee1df-120">The drop-down list displays the simple field expressions that are available in the Report Data pane.</span></span> <span data-ttu-id="ee1df-121">Zum Beispiel ist [PLZ] ein einfacher Feldausdruck für das Feld PLZ in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="ee1df-121">For example, [PostalCode] is a simple field expression for the PostalCode field in a dataset.</span></span>  
  
    4.  <span data-ttu-id="ee1df-122">Wählen Sie **Gruppenkopf hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ee1df-122">Select **Add group header**.</span></span> <span data-ttu-id="ee1df-123">Hierdurch wird eine statische Zeile für Gruppenbezeichnung und Gruppengesamtwerte über der Gruppe eingefügt.</span><span class="sxs-lookup"><span data-stu-id="ee1df-123">This option adds a static row above the group for the group label and group totals.</span></span> <span data-ttu-id="ee1df-124">Ebenso können Sie **Gruppenfuß hinzufügen** auswählen, um unter der Gruppe eine statische Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee1df-124">Likewise, you can select **Add group footer** to add a static row below the group.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="ee1df-125">Sie haben jetzt einen grundlegenden Tabellenbericht.</span><span class="sxs-lookup"><span data-stu-id="ee1df-125">You now have a basic tabular report.</span></span> <span data-ttu-id="ee1df-126">Beim Rendern werden eine Spalte mit dem Gruppeninstanzwert und eine oder mehrere weitere Spalten mit gruppierten Detaildaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee1df-126">When it is rendered, you see one column with the group instance value, and one or more columns with grouped detail data.</span></span> <span data-ttu-id="ee1df-127">Die folgende Abbildung zeigt, wie der Datenbereich auf der Entwurfsoberfläche aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="ee1df-127">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="ee1df-128">![Tabellendatenbereich mit Gruppe](../media/tabledataregionwithgroup.gif "Tabellendatenbereich mit Gruppe")</span><span class="sxs-lookup"><span data-stu-id="ee1df-128">![Table data region with group](../media/tabledataregionwithgroup.gif "Table data region with group")</span></span>  
  
     <span data-ttu-id="ee1df-129">Die folgende Abbildung zeigt, wie der gerenderte Datenbereich beim Anzeigen des Berichts aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="ee1df-129">The following figure shows how the rendered data region might look when you view the report.</span></span>  
  
     <span data-ttu-id="ee1df-130">![Gerenderter gruppierter Bericht](../media/tablereportrendered.gif "Gerenderter gruppierter Bericht")</span><span class="sxs-lookup"><span data-stu-id="ee1df-130">![Rendered grouped report](../media/tablereportrendered.gif "Rendered grouped report")</span></span>  
  
3.  <span data-ttu-id="ee1df-131">Für einen abgestuften Bericht benötigen Sie die erste Spalte, die die Gruppeninstanz enthält, nicht.</span><span class="sxs-lookup"><span data-stu-id="ee1df-131">For a stepped report, you do not need the first column that shows the group instance.</span></span> <span data-ttu-id="ee1df-132">Kopieren Sie stattdessen den Wert in der Gruppenkopfzelle, löschen Sie die Gruppenspalte, und fügen Sie den Wert in das erste Textfeld in der Gruppenkopfzeile ein.</span><span class="sxs-lookup"><span data-stu-id="ee1df-132">Instead, copy the value in the group header cell, delete the group column, and paste in the first text box in the group header row.</span></span> <span data-ttu-id="ee1df-133">Um die Gruppenspalte zu entfernen, klicken Sie mit der rechten Maustaste auf die Gruppenspalte oder die Zelle, und klicken Sie auf **Spalten löschen**.</span><span class="sxs-lookup"><span data-stu-id="ee1df-133">To remove the group column, right-click the group column or cell, and click **Delete Columns**.</span></span> <span data-ttu-id="ee1df-134">Die folgende Abbildung zeigt, wie der Datenbereich auf der Entwurfsoberfläche aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="ee1df-134">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="ee1df-135">![Datenbereich mit Gruppenkopfzeile](../media/tabledataregiongroupheader.gif "Datenbereich mit Gruppenkopfzeile")</span><span class="sxs-lookup"><span data-stu-id="ee1df-135">![Data region with group header row](../media/tabledataregiongroupheader.gif "Data region with group header row")</span></span>  
  
4.  <span data-ttu-id="ee1df-136">Ändern Sie die Auffüllung der Detaildatenzelle, um die Detailzeilen unter der Gruppenkopfzeile in der gleichen Spalte einzurücken.</span><span class="sxs-lookup"><span data-stu-id="ee1df-136">To indent the detail rows under the group header row in the same column, change the padding of the detail data cell.</span></span>  
  
    1.  <span data-ttu-id="ee1df-137">Wählen Sie die Zelle mit dem Detailfeld aus, das Sie einrücken möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1df-137">Select the cell with the detail field that you want to indent.</span></span> <span data-ttu-id="ee1df-138">Die Eigenschaften für das Textfeld dieser Zelle werden im Eigenschaftenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee1df-138">The text box properties for that cell appear in the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="ee1df-139">Erweitern Sie im Eigenschaftenbereich unter **Ausrichtung**die Eigenschaften für **Auffüllung**.</span><span class="sxs-lookup"><span data-stu-id="ee1df-139">In the Properties pane, under **Alignment**, expand the properties for **Padding**.</span></span>  
  
    3.  <span data-ttu-id="ee1df-140">Geben Sie für **Links**einen neuen Auffüll Wert ein, z `.5in` . b..</span><span class="sxs-lookup"><span data-stu-id="ee1df-140">For **Left**, type a new padding value, such as `.5in`.</span></span> <span data-ttu-id="ee1df-141">Durch die Auffüllung wird der Text in der Zelle um den angegebenen Wert eingerückt.</span><span class="sxs-lookup"><span data-stu-id="ee1df-141">Padding indents the text in the cell by the value you specify.</span></span> <span data-ttu-id="ee1df-142">Die Standardauffüllung ist 2 Punkt.</span><span class="sxs-lookup"><span data-stu-id="ee1df-142">The default padding is 2 points.</span></span> <span data-ttu-id="ee1df-143">Gültige Werte für die Auffüllungseigenschaften sind Zahlen über null (0) gefolgt von einem Größenkennzeichner.</span><span class="sxs-lookup"><span data-stu-id="ee1df-143">Valid values for the Padding properties are zero or a positive number, followed by a size designator.</span></span>  
  
         <span data-ttu-id="ee1df-144">Die folgenden Größenkennzeichner sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ee1df-144">Size designators are:</span></span>  
  
        |||  
        |-|-|  
        |`in`|<span data-ttu-id="ee1df-145">Zoll (1 Zoll = 2,54 Zentimeter)</span><span class="sxs-lookup"><span data-stu-id="ee1df-145">Inches (1 inch = 2.54 centimeters)</span></span>|  
        |`cm`|<span data-ttu-id="ee1df-146">Zentimeter</span><span class="sxs-lookup"><span data-stu-id="ee1df-146">Centimeters</span></span>|  
        |`mm`|<span data-ttu-id="ee1df-147">Millimeter</span><span class="sxs-lookup"><span data-stu-id="ee1df-147">Millimeters</span></span>|  
        |`pt`|<span data-ttu-id="ee1df-148">Punkte (1 Punkt = 1/72 Zoll)</span><span class="sxs-lookup"><span data-stu-id="ee1df-148">Points (1 point = 1/72 inch)</span></span>|  
        |`pc`|<span data-ttu-id="ee1df-149">Picas (1 Pica = 12 Punkte)</span><span class="sxs-lookup"><span data-stu-id="ee1df-149">Picas (1 pica = 12 points)</span></span>|  
  
     <span data-ttu-id="ee1df-150">Ihr Datenbereich sollte dem folgenden Beispiel ähneln.</span><span class="sxs-lookup"><span data-stu-id="ee1df-150">Your data region will look similar to the following example.</span></span>  
  
     <span data-ttu-id="ee1df-151">![Datenbereich für abgestuften Bericht](../media/steppedreportdataregion.gif "Datenbereich für abgestuften Bericht")</span><span class="sxs-lookup"><span data-stu-id="ee1df-151">![Data region for stepped report](../media/steppedreportdataregion.gif "Data region for stepped report")</span></span>  
  
     <span data-ttu-id="ee1df-152">**Datenbereich für abgestuftes Berichtslayout**</span><span class="sxs-lookup"><span data-stu-id="ee1df-152">**Data Region for Stepped Report Layout**</span></span>  
  
     <span data-ttu-id="ee1df-153">Klicken Sie auf der Registerkarte **Home** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ee1df-153">On the **Home** tab Click **Run**.</span></span> <span data-ttu-id="ee1df-154">Der Bericht zeigt die Gruppe mit eingezogenen Ebenen für die Untergruppenwerte an.</span><span class="sxs-lookup"><span data-stu-id="ee1df-154">The report displays the group with indented levels for the child group values.</span></span>  
  
### <a name="to-create-a-stepped-report-with-multiple-groups"></a><span data-ttu-id="ee1df-155">So erstellen Sie einen abgestuften Bericht mit mehreren Gruppen</span><span class="sxs-lookup"><span data-stu-id="ee1df-155">To create a stepped report with multiple groups</span></span>  
  
1.  <span data-ttu-id="ee1df-156">Erstellen Sie einen Bericht wie in der vorherigen Vorgehensweise beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ee1df-156">Create a report as described in the previous procedure.</span></span>  
  
2.  <span data-ttu-id="ee1df-157">Fügen Sie zusätzliche Gruppen zum Bericht hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee1df-157">Add additional groups to your report.</span></span>  
  
    1.  <span data-ttu-id="ee1df-158">Klicken Sie im Bereich Zeilengruppen mit der rechten Maustaste auf die Gruppe, klicken Sie auf **Gruppe hinzufügen**, und wählen Sie dann den Gruppentyp aus, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1df-158">In the Row Groups pane, right-click the group, click **Add Group**, and then choose the type of group you want to add.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ee1df-159">Es gibt mehrere Möglichkeiten, einem Datenbereich Gruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee1df-159">There are several ways to add groups to a data region.</span></span> <span data-ttu-id="ee1df-160">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen einer Gruppe in einem Datenbereich &#40;Berichts-Generator und SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ee1df-160">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
    2.  <span data-ttu-id="ee1df-161">Geben Sie im Dialogfeld **Tablix-Gruppe** einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="ee1df-161">In the **Tablix Group** dialog box, type a name.</span></span>  
  
    3.  <span data-ttu-id="ee1df-162">Geben Sie in **Gruppierungsausdruck**einen Ausdruck ein, oder wählen Sie ein Datasetfeld aus, nach dem gruppiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee1df-162">In **Group expression**, type an expression or select a dataset field to group on.</span></span> <span data-ttu-id="ee1df-163">Zum Erstellen eines Ausdrucks klicken Sie auf die Ausdrucksschaltfläche (**fx**), um das Dialogfeld **Ausdruck** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ee1df-163">To create an expression, click the expression (**fx**) button to open the **Expression** dialog box.</span></span>  
  
    4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="ee1df-164">Ändern Sie die Auffüllung für die Zelle, die die Gruppendaten enthält.</span><span class="sxs-lookup"><span data-stu-id="ee1df-164">Change the padding for the cell that displays the group data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1df-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee1df-165">See Also</span></span>  
 <span data-ttu-id="ee1df-166">[Seiten Kopfzeilen und-Fußzeilen &#40;Berichts-Generator und SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee1df-166">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee1df-167">[Formatieren von Berichts Elementen &#40;Berichts-Generator und SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee1df-167">[Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee1df-168">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee1df-168">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee1df-169">[Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee1df-169">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee1df-170">[Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee1df-170">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ee1df-171">[Listet &#40;Berichts-Generator und SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ee1df-171">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ee1df-172">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee1df-172">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
