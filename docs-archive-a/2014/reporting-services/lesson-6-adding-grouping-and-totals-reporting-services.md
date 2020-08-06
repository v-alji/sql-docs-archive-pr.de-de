---
title: 'Lektion 6: Hinzufügen von Gruppierungen und Gesamtergebnissen (Reporting Services) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e3d61228-2aa4-42cc-955e-602dbf3406a7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b98798005a984edf00aff469d4c1b09aa2e34d98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621871"
---
# <a name="lesson-6-adding-grouping-and-totals-reporting-services"></a><span data-ttu-id="45ca0-102">Lektion 6: Hinzufügen von Gruppierungen und Gesamtwerten (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="45ca0-102">Lesson 6: Adding Grouping and Totals (Reporting Services)</span></span>
  <span data-ttu-id="45ca0-103">Fügen Sie dem Bericht Gruppierungen und Gesamtwerte hinzu, um Daten zu gruppieren und zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-103">Add grouping and totals to your report to organize and summarize your data.</span></span>  
  
 <span data-ttu-id="45ca0-104">Weitere Informationen zum Hinzufügen von laufenden Summen zu Berichten finden Sie unter [Hinzufügen von Summen zu Reporting Services Berichten (SSRS)](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span><span class="sxs-lookup"><span data-stu-id="45ca0-104">For information about adding running totals to reports, see: [Adding totals to Reporting Services (SSRS) reports](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span></span>  
  
 <span data-ttu-id="45ca0-105">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="45ca0-105">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="45ca0-106">So gruppieren Sie Daten in einem Bericht</span><span class="sxs-lookup"><span data-stu-id="45ca0-106">To group data in a report</span></span>](#bkmk_groupdata)  
  
-   [<span data-ttu-id="45ca0-107">So fügen Sie einem Bericht Summen hinzu</span><span class="sxs-lookup"><span data-stu-id="45ca0-107">To add totals to a report</span></span>](#bkmk_addtotals)  
  
-   [<span data-ttu-id="45ca0-108">So fügen Sie einem Bericht ein Tagesergebnis hinzu</span><span class="sxs-lookup"><span data-stu-id="45ca0-108">To add a daily total to a report</span></span>](#bkmk_adddailytotal)  
  
-   [<span data-ttu-id="45ca0-109">So fügen Sie einem Bericht ein Gesamtergebnis hinzu</span><span class="sxs-lookup"><span data-stu-id="45ca0-109">To add a grand total to a report</span></span>](#bkmk_addgrandtotal)  
  
-   [<span data-ttu-id="45ca0-110">So veröffentlichen Sie den Bericht auf dem Berichts Server (optional)</span><span class="sxs-lookup"><span data-stu-id="45ca0-110">To Publish the Report to the Report Server (Optional)</span></span>](#bkmk_publishreport)  
  
##  <a name="to-group-data-in-a-report"></a><a name="bkmk_groupdata"></a><span data-ttu-id="45ca0-111">So gruppieren Sie Daten in einem Bericht</span><span class="sxs-lookup"><span data-stu-id="45ca0-111">To group data in a report</span></span>  
  
1.  <span data-ttu-id="45ca0-112">Klicken Sie auf die Registerkarte **Entwurf** .</span><span class="sxs-lookup"><span data-stu-id="45ca0-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="45ca0-113">Wenn Sie den Bereich **Zeilengruppen** nicht sehen, klicken Sie mit der rechten Maustaste auf die Entwurfsoberfläche. Klicken Sie auf **Sicht** und dann auf **Gruppierung**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-113">If you do not see the **Row Groups** pane , right-click the design surface and click **view** and then click **Grouping**.</span></span>  
  
3.  <span data-ttu-id="45ca0-114">Ziehen Sie im **Berichtsdatenbereich** das Feld `Date` in den Bereich **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-114">From the **Report Data** pane, drag the `Date` field to the **Row Groups** pane.</span></span> <span data-ttu-id="45ca0-115">Platzieren Sie das Feld über der Zeile **(Details)**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-115">Place it above the row called **(Details)**.</span></span>  
  
     <span data-ttu-id="45ca0-116">Beachten Sie, dass das Zeilenhandle nun Klammern zum Anzeigen einer Gruppe aufweist.</span><span class="sxs-lookup"><span data-stu-id="45ca0-116">Note that the row handle now has a bracket in it, to show a group.</span></span> <span data-ttu-id="45ca0-117">Außerdem verfügt die Tabelle nun auf jeder Seite der vertikalen gepunkteten Linie einmal über die Spalte Date.</span><span class="sxs-lookup"><span data-stu-id="45ca0-117">The table now also has two Date columns -- one on either side of a vertical dotted line.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablegroups1design.gif "rs_BasicTableGroups1Design")  
  
4.  <span data-ttu-id="45ca0-118">Ziehen Sie im **Berichtsdatenbereich** das Feld `Order` in den Bereich **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-118">From the **Report Data** pane, drag the `Order` field to the **Row Groups** pane.</span></span> <span data-ttu-id="45ca0-119">Platzieren das Feld unter Date und über **Details**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-119">Place it below Date and above **(Details)**.</span></span>  
  
     <span data-ttu-id="45ca0-120">Beachten Sie, dass das Zeilenhandle nun zweimal Klammern zum Anzeigen von zwei Gruppen aufweist.</span><span class="sxs-lookup"><span data-stu-id="45ca0-120">Note that the row handle now has two brackets in it, to show two groups.</span></span> <span data-ttu-id="45ca0-121">Die Tabelle verfügt nun auch über zwei `Order` Spalten.</span><span class="sxs-lookup"><span data-stu-id="45ca0-121">The table now has two `Order` columns, too.</span></span>  
  
5.  <span data-ttu-id="45ca0-122">Löschen Sie die ursprünglichen Spalten Date und Order**rechts** der doppelten Linie.</span><span class="sxs-lookup"><span data-stu-id="45ca0-122">Delete the original Date and Order columns to the **right** of the double line.</span></span> <span data-ttu-id="45ca0-123">Dadurch werden die einzelnen Datensatzwerte entfernt, und nur der Gruppenwert wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45ca0-123">This removes this individual record values so that only the group value is displayed.</span></span> <span data-ttu-id="45ca0-124">Wählen Sie die Spaltenhandles für die beiden Spalten aus, klicken Sie mit der rechten Maustaste und wählen Sie **Spalten löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="45ca0-124">Select the column handles for the two columns, right-click and click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="45ca0-125">![Auswählen der zu löschenden Spalten](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Auswählen der zu löschenden Spalten")</span><span class="sxs-lookup"><span data-stu-id="45ca0-125">![Select columns to delete](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Select columns to delete")</span></span>  
  
     <span data-ttu-id="45ca0-126">Die Spaltenkopfzeilen und der Datumswert können erneut formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="45ca0-126">You can format the column headers and date again.</span></span>  
  
6.  <span data-ttu-id="45ca0-127">Wechseln Sie zur Registerkarte **Vorschau** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-127">Switch to the **Preview** tab to preview the report.</span></span> <span data-ttu-id="45ca0-128">Die Vorschau sollte ähnlich der folgenden Abbildung aussehen:</span><span class="sxs-lookup"><span data-stu-id="45ca0-128">It should look similar to the following illustration:</span></span>  
  
     <span data-ttu-id="45ca0-129">![Tabelle gruppiert nach „Date“ und dann „Order“](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Tabelle gruppiert nach „Date“ und dann „Order“")</span><span class="sxs-lookup"><span data-stu-id="45ca0-129">![Table grouped by date and then order](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table grouped by date and then order")</span></span>  
  
##  <a name="to-add-totals-to-a-report"></a><a name="bkmk_addtotals"></a><span data-ttu-id="45ca0-130">So fügen Sie einem Bericht Summen hinzu</span><span class="sxs-lookup"><span data-stu-id="45ca0-130">To add totals to a report</span></span>  
  
1.  <span data-ttu-id="45ca0-131">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="45ca0-131">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="45ca0-132">Klicken Sie mit der rechten Maustaste auf die Datenbereichszelle mit dem Feld `[LineTotal]`und anschließend auf **Gesamtergebnis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-132">Right-click the data region cell that contains the field `[LineTotal]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="45ca0-133">Dadurch wird eine Zeile mit dem Gesamtwert für die einzelnen Bestellungen in Dollar hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="45ca0-133">This adds a row with a sum of the dollar amount for each order.</span></span>  
  
3.  <span data-ttu-id="45ca0-134">Klicken Sie mit der rechten Maustaste auf die Zelle mit dem Feld `[Qty]`und anschließend auf **Gesamtergebnis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-134">Right-click the cell that contains the field `[Qty]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="45ca0-135">Dadurch wird der Ergebniszeile eine Gesamtmenge für die einzelnen Bestellungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="45ca0-135">This adds a sum of the quantity for each order to the totals row.</span></span>  
  
4.  <span data-ttu-id="45ca0-136">Geben Sie in die leere Zelle links von `Sum[Qty]`die Bezeichnung**Order Total**ein.</span><span class="sxs-lookup"><span data-stu-id="45ca0-136">In the empty cell to the left of `Sum[Qty]`, type the label "**Order Total"**.</span></span>  
  
5.  <span data-ttu-id="45ca0-137">Sie können der Ergebniszeile eine Hintergrundfarbe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-137">You can add a background color to the totals row.</span></span> <span data-ttu-id="45ca0-138">Wählen Sie die beiden Gesamtergebniszellen und die Bezeichnungszelle aus.</span><span class="sxs-lookup"><span data-stu-id="45ca0-138">Select the two sum cells and the label cell.</span></span>  
  
6.  <span data-ttu-id="45ca0-139">Klicken Sie im Menü **Format** auf **Hintergrundfarbe**, klicken Sie auf **Hellgrau**und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-139">On the **Format** menu, click **Background Color**, click **Light Gray**, and click **OK**.</span></span>  
  
     <span data-ttu-id="45ca0-140">![Entwurfsansicht: Einfache Tabelle mit Gesamtergebnis der Bestellungen](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Entwurfsansicht: Einfache Tabelle mit Gesamtergebnis der Bestellungen")</span><span class="sxs-lookup"><span data-stu-id="45ca0-140">![Design view: Basic table with order total](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Design view: Basic table with order total")</span></span>  
  
##  <a name="to-add-a-daily-total-to-a-report"></a><a name="bkmk_adddailytotal"></a><span data-ttu-id="45ca0-141">So fügen Sie einem Bericht ein Tagesergebnis hinzu</span><span class="sxs-lookup"><span data-stu-id="45ca0-141">To add a daily total to a report</span></span>  
  
1.  <span data-ttu-id="45ca0-142">Klicken Sie mit der rechten Maustaste auf die Zelle Order , zeigen Sie auf **Gesamtergebnis hinzufügen**, und klicken Sie auf **Danach**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-142">Right-click the Order cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="45ca0-143">Dadurch wird eine neue Zeile mit Summen der Menge und Dollarbetrag für jeden Tag und der Bezeichnung "**Total**" in der Spalte Order hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="45ca0-143">This adds a new row containing sums of the quantity and dollar amount for each day, and the label "**Total**" in the Order column.</span></span>  
  
2.  <span data-ttu-id="45ca0-144">Geben Sie in der gleichen Zelle zuerst das Wort **Daily** und anschließend das Wort **Total** ein, um **Daily Total**zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="45ca0-144">Type the word **Daily** before the word **Total** in the same cell, so it reads **Daily Total**.</span></span>  
  
3.  <span data-ttu-id="45ca0-145">Wählen Sie die Zelle **Daily Total** aus, und markieren Sie die beiden Zellen für **Sum** sowie die leere Zelle dazwischen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-145">Select the **Daily Total** cell, the two **Sum** cells and the empty cell between them.</span></span>  
  
4.  <span data-ttu-id="45ca0-146">Klicken Sie im Menü **Format** auf **Hintergrundfarbe**, klicken Sie auf **Orange**und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-146">On the **Format** menu, click **Background Color**, click **Orange**, and click **OK**.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablesumdaytotaldesign.gif "rs_BasicTableSumDayTotalDesign")  
  
##  <a name="to-add-a-grand-total-to-a-report"></a><a name="bkmk_addgrandtotal"></a><span data-ttu-id="45ca0-147">So fügen Sie einem Bericht ein Gesamtergebnis hinzu</span><span class="sxs-lookup"><span data-stu-id="45ca0-147">To add a grand total to a report</span></span>  
  
1.  <span data-ttu-id="45ca0-148">Klicken Sie mit der rechten Maustaste auf die Zelle Date, zeigen Sie auf **Gesamtergebnis hinzufügen**, und klicken Sie auf **Danach**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-148">Right-click the Date cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="45ca0-149">Dadurch wird eine neue Zeile mit Summen der Menge und dem Dollarbetrag für den gesamten Bericht und die **Gesamt** Bezeichnung in der Spalte hinzugefügt `Date` .</span><span class="sxs-lookup"><span data-stu-id="45ca0-149">This adds a new row containing sums of the quantity and dollar amount for the entire report, and the **Total** label in the `Date` column.</span></span>  
  
2.  <span data-ttu-id="45ca0-150">Geben Sie in der gleichen Zelle zuerst das Wort **Grand** und anschließend das Wort **Total** ein, um **Grand Total**zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="45ca0-150">Type the word **Grand** before the word **Total** in the same cell, so it reads **Grand Total**.</span></span>  
  
3.  <span data-ttu-id="45ca0-151">Wählen Sie die Zelle **Grand Total** aus, und markieren Sie die beiden Zellen für **Sum** sowie die leeren Zellen dazwischen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-151">Select the **Grand Total** cell, the two **Sum** cells and the empty cells between them.</span></span>  
  
4.  <span data-ttu-id="45ca0-152">Klicken Sie im Menü **Format** auf **Hintergrundfarbe**, klicken Sie auf **Hellblau**und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-152">On the **Format** menu, click **Background Color**, click **Light Blue**, and click **OK**.</span></span>  
  
     <span data-ttu-id="45ca0-153">![Entwurfsansicht: Gesamtergebnis in einfacher Tabelle](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Entwurfsansicht: Gesamtergebnis in einfacher Tabelle")</span><span class="sxs-lookup"><span data-stu-id="45ca0-153">![Design view: Grand total in basic table](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Design view: Grand total in basic table")</span></span>  
  
5.  <span data-ttu-id="45ca0-154">Klicken Sie auf "Vorschau".</span><span class="sxs-lookup"><span data-stu-id="45ca0-154">Click Preview.</span></span>  
  
     <span data-ttu-id="45ca0-155">Die letzte Seite sollte etwa folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="45ca0-155">The last page should look something like this:</span></span>  
  
     <span data-ttu-id="45ca0-156">![Vorschau: Einfache Tabelle mit Gesamtergebnis](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Vorschau: Einfache Tabelle mit Gesamtergebnis")</span><span class="sxs-lookup"><span data-stu-id="45ca0-156">![Preview: Basic table with grand total](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Preview: Basic table with grand total")</span></span>  
  
##  <a name="to-publish-the-report-to-the-report-server-optional"></a><a name="bkmk_publishreport"></a><span data-ttu-id="45ca0-157">So veröffentlichen Sie den Bericht auf dem Berichts Server (optional)</span><span class="sxs-lookup"><span data-stu-id="45ca0-157">To Publish the Report to the Report Server (Optional)</span></span>  
  
1.  <span data-ttu-id="45ca0-158">Ein optionaler Schritt besteht darin, den vervollständigten Bericht auf dem Berichtsserver im einheitlichen Modus zu veröffentlichen, damit Sie den Bericht im Berichts-Manager anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="45ca0-158">An optional step is to publish the completed report to the native mode report server so you can view the report from Report Manager.</span></span>  
  
2.  <span data-ttu-id="45ca0-159">Klicken Sie auf der Symbolleiste auf **Projekt** , und klicken Sie dann auf auf die Option für die **Eigenschaften des Lernprogramms**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-159">On the toolbar click **Project** and then click **tutorial Properties...**</span></span>  
  
3.  <span data-ttu-id="45ca0-160">Geben Sie in **TargetServerURL** den Namen des Berichts Servers ein, z. b. **http:// \<servername> /ReportServer**</span><span class="sxs-lookup"><span data-stu-id="45ca0-160">In the **TargetServerURL** type the name of the name of your report server, for example **http://\<servername>/reportserver**</span></span>  
  
4.  <span data-ttu-id="45ca0-161">Klicken Sie auf **OK**</span><span class="sxs-lookup"><span data-stu-id="45ca0-161">Click **OK**</span></span>  
  
5.  <span data-ttu-id="45ca0-162">Klicken Sie auf der Symbolleiste auf **Erstellen** , und klicken Sie dann auf **Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="45ca0-162">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>  
  
     <span data-ttu-id="45ca0-163">Wenn Sie im Ausgabefenster eine Meldung wie die Folgende sehen, war die Bereitstellung erfolgreich:</span><span class="sxs-lookup"><span data-stu-id="45ca0-163">If you see a message similar to the following in the output window, it indicates a successful deployment.</span></span>  
  
    > <span data-ttu-id="45ca0-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span><span class="sxs-lookup"><span data-stu-id="45ca0-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span></span> <span data-ttu-id="45ca0-165">Das Element ist auf dem neuesten Stand. Build abgeschlossen--0 Fehler, 0 Warnungen------Bereitstellung gestartet: Projekt: Tutorial, Konfiguration: Debuggen------Bereitstellung für http:// \<server name> /reportserverDeploying Bericht "/Tutorial/Sales Orders". Bereitstellung abgeschlossen--0 Fehler, 0 Warnungen = = = = = = = = = = Build: 1 erfolgreich oder aktuell, 0 fehlgeschlagen, 0 übersprungen = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =</span><span class="sxs-lookup"><span data-stu-id="45ca0-165">Item is up to date.Build complete -- 0 errors, 0 warnings------ Deploy started: Project: tutorial, Configuration: Debug ------Deploying to http://\<server name>/reportserverDeploying report '/tutorial/Sales Orders'.Deploy complete -- 0 errors, 0 warnings========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==================== Deploy: 1 succeeded, 0 failed, 0 skipped ==========</span></span>  
  
     <span data-ttu-id="45ca0-166">Wenn Sie eine Fehlermeldung wie die Folgende sehen, überprüfen Sie, ob Sie über Berechtigungen für den Berichtsserver verfügen und ob Sie [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] mit Administratorrechten gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="45ca0-166">If you see an error message similar to the following, verify you have permissions on the report server and you have started [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] with administrator privileges.</span></span>  
  
    > <span data-ttu-id="45ca0-167">"Die dem Benutzer ' xxxxxxxx \\<Ihrem Benutzernamen ' gewährten Berechtigungen \> reichen zum Ausführen dieses Vorgangs nicht aus."</span><span class="sxs-lookup"><span data-stu-id="45ca0-167">"The permissions granted to user 'XXXXXXXX\\<your user name\>' are insufficient for performing this operation"</span></span>  
  
6.  <span data-ttu-id="45ca0-168">Starten Sie Berichts-Manager mit Administratorrechten, indem Sie z. B. mit der rechten Maustaste auf das Symbol für Internet Explorer und dann auf **Als Administrator ausführen**klicken.</span><span class="sxs-lookup"><span data-stu-id="45ca0-168">Start Report Manager with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>  
  
     <span data-ttu-id="45ca0-169">Wechseln Sie zur Berichts-Manager-URL z. B.: `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="45ca0-169">Browse to the Report Manager URL, for example: `http://<server name>/reports`.</span></span>  
  
7.  <span data-ttu-id="45ca0-170">Wechseln Sie zum Ordner, der den Bericht enthält, und klicken Sie auf den Namen des Berichts `Sales Orders`, um den gerenderten Bericht im Browser anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-170">Browse to the folder that contains the report and click the name of the report `Sales Orders` to view the rendered report in the browser.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="45ca0-171">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="45ca0-171">Next Steps</span></span>  
 <span data-ttu-id="45ca0-172">Sie haben nun das Lernprogramm zum Erstellen eines grundlegenden Tabellenberichts erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="45ca0-172">You have successfully completed the Creating a Basic Table Report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ca0-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45ca0-173">See Also</span></span>  
 [<span data-ttu-id="45ca0-174">Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="45ca0-174">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
