---
title: 'Lektion 4: Hinzufügen einer Tabelle zum Bericht (Reporting Services) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52694168bd60b8e3807db6204f33a89815573093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609719"
---
# <a name="lesson-4-adding-a-table-to-the-report-reporting-services"></a><span data-ttu-id="caeb7-102">Lektion 4: Hinzufügen einer Tabelle zum Bericht (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="caeb7-102">Lesson 4: Adding a Table to the Report (Reporting Services)</span></span>
  <span data-ttu-id="caeb7-103">Nach dem Definieren des Datasets können Sie mit dem Entwerfen des Berichts beginnen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-103">After the dataset is defined, you can start designing the report.</span></span> <span data-ttu-id="caeb7-104">Zum Erstellen eines Berichtslayouts verschieben Sie mit Drag und Drop Datenbereiche, Textfelder, Bilder und andere Elemente auf die Entwurfsoberfläche, die in den Bericht eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-104">You create a report layout by dragging and dropping data regions, text boxes, images, and other items that you want to include in your report to the design surface.</span></span>  
  
 <span data-ttu-id="caeb7-105">Elemente, die wiederholte Zeilen von Daten aus zugrunde liegenden Datasets enthalten, werden als *Datenbereiche*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="caeb7-105">Items that contain repeated rows of data from underlying datasets are called *data regions*.</span></span> <span data-ttu-id="caeb7-106">Ein grundlegender Bericht enthält typischerweise nur einen Datenbereich. Sie können jedoch weitere Datenbereiche hinzufügen, z. B. wenn dem Tabellenbericht ein Diagramm hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="caeb7-106">A basic report will have only one data region, but you can add more, for example, if you want to add a chart to your tabular report.</span></span> <span data-ttu-id="caeb7-107">Nachdem Sie einen Datenbereich hinzugefügt haben, können Sie diesem Felder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-107">After you add a data region, you can add fields to the data region.</span></span>  
  
### <a name="to-add-a-table-data-region-and-fields-to-a-report-layout"></a><span data-ttu-id="caeb7-108">So fügen Sie einem Berichtslayout einen Tabellendatenbereich und Felder hinzu</span><span class="sxs-lookup"><span data-stu-id="caeb7-108">To add a Table data region and fields to a report layout</span></span>  
  
1.  <span data-ttu-id="caeb7-109">Klicken Sie in **Toolbox**auf **Tabelle**, und klicken Sie anschließend auf die Entwurfsoberfläche und ziehen Sie die Maus.</span><span class="sxs-lookup"><span data-stu-id="caeb7-109">In the **Toolbox**, click **Table**, and then click on the design surface and drag the mouse.</span></span> <span data-ttu-id="caeb7-110">Vom Berichts-Designer wird ein Tabellendatenbereich mit drei Spalten in der Mitte der Entwurfsoberfläche gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="caeb7-110">Report Designer draws a table data region with three columns in the center of the design surface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="caeb7-111">Die **Toolbox** kann auf der linken Seite des **Berichtsdatenbereichs** als Registerkarte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="caeb7-111">The **Toolbox** may appear as a tab on the left side of the **Report Data** pane.</span></span> <span data-ttu-id="caeb7-112">Um die **Toolbox**zu öffnen, bewegen Sie den Mauszeiger über die Registerkarte **Toolbox** . Wenn die **Toolbox** nicht sichtbar ist, klicken Sie im Menü **Ansicht** auf **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="caeb7-112">To open the **Toolbox**, move the pointer over the **Toolbox** tab. If the **Toolbox** is not visible, from the **View** menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="caeb7-113">Erweitern Sie im **Berichtsdaten** Bereich das **AdventureWorksDataSet** -DataSet, um die Felder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-113">In the **Report Data** pane, expand the **AdventureWorksDataset** dataset to display the fields.</span></span>  
  
3.  <span data-ttu-id="caeb7-114">Ziehen Sie das Feld Date aus dem **Berichtsdatenbereich** in die erste Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="caeb7-114">Drag the Date field from the **Report Data** pane to the first column in the table.</span></span>  
  
     <span data-ttu-id="caeb7-115">Wenn Sie das Feld in der ersten Spalte ablegen, werden zwei Vorgänge ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="caeb7-115">When you drop the field into the first column, two things happen.</span></span> <span data-ttu-id="caeb7-116">Zunächst wird in der Datenzelle der als *Feldausdruck*bezeichnete Feldname in Klammern: `[Date]`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="caeb7-116">First, the data cell will display the field name, known as the *field expression*, in brackets: `[Date]`.</span></span> <span data-ttu-id="caeb7-117">Dann wird automatisch der Kopfzeile ein Wert für den Spaltenkopf hinzugefügt, und zwar direkt über dem Feldausdruck.</span><span class="sxs-lookup"><span data-stu-id="caeb7-117">Second, a column header value is automatically added to Header row, just above the field expression.</span></span> <span data-ttu-id="caeb7-118">Standardmäßig ist die Spalte der Name des Felds.</span><span class="sxs-lookup"><span data-stu-id="caeb7-118">By default, the column is the name of the field.</span></span> <span data-ttu-id="caeb7-119">Sie können den Kopfzeilentext auswählen und einen neuen Namen eingeben.</span><span class="sxs-lookup"><span data-stu-id="caeb7-119">You can select the Header row text and type a new name.</span></span>  
  
4.  <span data-ttu-id="caeb7-120">Ziehen Sie das Feld Order aus dem **Berichtsdatenbereich** in die zweite Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="caeb7-120">Drag the Order field from the **Report Data** pane to the second column in the table.</span></span>  
  
5.  <span data-ttu-id="caeb7-121">Ziehen Sie das Feld Product aus dem **Berichtsdatenbereich** in die dritte Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="caeb7-121">Drag the Product field from the **Report Data** pane to the third column in the table.</span></span>  
  
6.  <span data-ttu-id="caeb7-122">Ziehen Sie das Feld Qty an den rechten Rand der dritten Spalte, bis Sie einen vertikalen Cursor erhalten und der Mauszeiger ein Pluszeichen [+] aufweist.</span><span class="sxs-lookup"><span data-stu-id="caeb7-122">Drag the Qty field to the right edge of the third column until you get a vertical cursor and the mouse pointer has a plus sign [+].</span></span> <span data-ttu-id="caeb7-123">Wenn Sie die Maustaste loslassen, wird eine vierte Spalte für `[Qty]`erstellt.</span><span class="sxs-lookup"><span data-stu-id="caeb7-123">When you release the mouse button, a fourth column is created for `[Qty]`.</span></span>  
  
7.  <span data-ttu-id="caeb7-124">Fügen Sie das Feld LineTotal auf dieselbe Weise hinzu, wodurch eine fünfte Spalte erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="caeb7-124">Add the LineTotal field in the same way, creating a fifth column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="caeb7-125">Der Spaltenheader lautet "Line Total".</span><span class="sxs-lookup"><span data-stu-id="caeb7-125">The column header is Line Total.</span></span> <span data-ttu-id="caeb7-126">Der Berichts-Designer erstellt für die Spalte automatisch einen besser lesbaren Namen, indem er "LineTotal" in zwei Wörter unterteilt.</span><span class="sxs-lookup"><span data-stu-id="caeb7-126">Report Designer automatically creates a friendly name for the column by splitting LineTotal into two words.</span></span>  
  
     <span data-ttu-id="caeb7-127">Die folgende Abbildung zeigt einen Datenbereich einer Tabelle, der mit folgenden Feldern aufgefüllt wurde: Date, Order, Product, Qty und Line Total.</span><span class="sxs-lookup"><span data-stu-id="caeb7-127">The following diagram shows a table data region that has been populated with these fields: Date, Order, Product, Qty, and Line Total.</span></span>  
  
     <span data-ttu-id="caeb7-128">![Entwurf, Tabelle mit Kopfzeile und Detailzeile](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Entwurf, Tabelle mit Kopfzeile und Detailzeile")</span><span class="sxs-lookup"><span data-stu-id="caeb7-128">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
## <a name="preview-your-report"></a><span data-ttu-id="caeb7-129">Zeigen Sie den Bericht in der Vorschau an.</span><span class="sxs-lookup"><span data-stu-id="caeb7-129">Preview Your Report</span></span>  
 <span data-ttu-id="caeb7-130">Wenn Sie einen Bericht in der Vorschau anzeigen, können Sie den gerenderten Bericht überprüfen, ohne ihn zuvor auf einem Berichtsserver zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-130">Previewing a report enables you to view the rendered report without having to first publish it to a report server.</span></span> <span data-ttu-id="caeb7-131">Es empfiehlt sich beispielsweise, den Bericht zur Entwurfszeit häufig in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-131">You will probably want to preview your report frequently during design time.</span></span> <span data-ttu-id="caeb7-132">Wenn Sie den Bericht in der Vorschau anzuzeigen, wird auch eine Überprüfung des Entwurfs und der Datenverbindungen ausgeführt, damit Sie Fehler und Probleme korrigieren können, bevor Sie den Bericht auf einem Berichtsserver veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="caeb7-132">Previewing the report will also run validation on the design and data connections so you can correct errors and issues before publishing the report to a report server.</span></span>  
  
#### <a name="to-preview-a-report"></a><span data-ttu-id="caeb7-133">So zeigen Sie die Vorschau eines Berichts an</span><span class="sxs-lookup"><span data-stu-id="caeb7-133">To preview a report</span></span>  
  
-   <span data-ttu-id="caeb7-134">Klicken Sie auf die Registerkarte **Vorschau** . Berichts-Designer führt den Bericht aus und zeigt ihn in der Vorschau Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="caeb7-134">Click the **Preview** tab. Report Designer runs the report and displays it in Preview view.</span></span>  
  
     <span data-ttu-id="caeb7-135">In der folgenden Abbildung wird ein Teil des Berichts in der Ansicht Vorschau angezeigt.</span><span class="sxs-lookup"><span data-stu-id="caeb7-135">The following diagram shows part of the report in Preview view.</span></span>  
  
     <span data-ttu-id="caeb7-136">![Vorschau, Detailzeilen der Tabelle mit 5 Spalten](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Vorschau, Detailzeilen der Tabelle mit 5 Spalten")</span><span class="sxs-lookup"><span data-stu-id="caeb7-136">![Preview, Detail rows of table with 5 columns](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Preview, Detail rows of table with 5 columns")</span></span>  
  
     <span data-ttu-id="caeb7-137">Beachten Sie, dass die Währungsangabe (in der Spalte Line Total) sechs Stellen nach dem Dezimaltrennzeichen aufweist und dass das Datum einen Zeitstempel enthält.</span><span class="sxs-lookup"><span data-stu-id="caeb7-137">Notice that the currency (in the Line Total column) has six places after the decimal, and the date has includes a time stamp.</span></span> <span data-ttu-id="caeb7-138">Diese Formatierung wird in der nächsten Lektion korrigiert.</span><span class="sxs-lookup"><span data-stu-id="caeb7-138">You're going to fix that formatting in the next lesson.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="caeb7-139">Klicken Sie im Menü **Datei** auf **Alle Speichern** , um den Bericht zu speichern.</span><span class="sxs-lookup"><span data-stu-id="caeb7-139">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="caeb7-140">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="caeb7-140">Next Steps</span></span>  
 <span data-ttu-id="caeb7-141">Sie haben Ihrem Bericht erfolgreich einen Tabellendatenbereich hinzugefügt, dem Datenbereich Felder hinzugefügt und den Bericht in der Vorschau angezeigt.</span><span class="sxs-lookup"><span data-stu-id="caeb7-141">You have successfully added a Table data region to your report, added fields to the data region, and previewed your report.</span></span> <span data-ttu-id="caeb7-142">Anschließend formatieren Sie Spaltenheader sowie Datums- und Währungswerte.</span><span class="sxs-lookup"><span data-stu-id="caeb7-142">Next, you will format column headers and date and currency values.</span></span> <span data-ttu-id="caeb7-143">Weitere Informationen finden Sie unter [Lektion 5: Formatieren eines Berichts (Reporting Services)](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="caeb7-143">See [Lesson 5: Formatting a Report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caeb7-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="caeb7-144">See Also</span></span>  
 <span data-ttu-id="caeb7-145">[Tabellen &#40;Berichts-Generator und SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="caeb7-145">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="caeb7-146">Datasetfeld-Sammlung &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="caeb7-146">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
  
  
