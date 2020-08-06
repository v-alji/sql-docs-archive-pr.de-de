---
title: 'Tutorial: Hinzufügen einer KPI zu einem Bericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1bf77859-0b33-4f40-abaf-ebeeb6ebb1f8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 405978721068583597adf5c4257978a222121078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720941"
---
# <a name="tutorial-adding-a-kpi-to-your-report-report-builder"></a><span data-ttu-id="ff00d-102">Lernprogramm: Hinzufügen eines KPIs zu einem Bericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="ff00d-102">Tutorial: Adding a KPI to Your Report (Report Builder)</span></span>
  <span data-ttu-id="ff00d-103">Ein Key Performance Indicator (KPI) ist ein messbarer Wert mit einer Aussagekraft für das Geschäft.</span><span class="sxs-lookup"><span data-stu-id="ff00d-103">A key performance indicator (KPI) is a measurable value that has business significance.</span></span> <span data-ttu-id="ff00d-104">In diesem Lernprogramm erfahren Sie, wie ein (KPI) in einen Bericht eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-104">This tutorial teaches you how to include a (KPI) in a report.</span></span> <span data-ttu-id="ff00d-105">In diesem Szenario ist die Verkaufszusammenfassung nach Produktunterkategorien der KPI.</span><span class="sxs-lookup"><span data-stu-id="ff00d-105">In this scenario, the sales summary by product subcategories is the KPI.</span></span> <span data-ttu-id="ff00d-106">Der aktuelle Status des KPI wird mit Farben, Messgeräten und Indikatoren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-106">The current state of the KPI is shown by using colors, gauges, and indicators.</span></span>  
  
 <span data-ttu-id="ff00d-107">Die folgende Abbildung zeigt den Bericht, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-107">The following illustration shows the report that you will create.</span></span>  
  
 <span data-ttu-id="ff00d-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span><span class="sxs-lookup"><span data-stu-id="ff00d-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="ff00d-109">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="ff00d-109">What You Will Learn</span></span>  
 <span data-ttu-id="ff00d-110">In diesem Lernprogramm erfahren Sie, wie ein KPI hinzugefügt wird, indem Sie die Hintergrundfarbe von Tabellenzellen basierend auf dem Zellenwert festlegen und ein Messgerät und einen Indikator hinzufügen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ff00d-110">In this tutorial, you will learn to add a KPI by setting the background color of table cells based on cell value and add and configure a gauge and an indicator.</span></span> <span data-ttu-id="ff00d-111">Sie erfahren auch, wie der Ausdruck zum Festlegen der Hintergrundfarbe der Tabellenzellen geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-111">You also learn to write the expression that sets the background color of the table cells.</span></span>  
  
 <span data-ttu-id="ff00d-112">Dieses Lernprogramm enthält die folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="ff00d-112">This tutorial contains the following procedures:</span></span>  
  
1.  [<span data-ttu-id="ff00d-113">Erstellen eines Tabellenberichts und eines Datasets mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="ff00d-113">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Table)  
  
2.  [<span data-ttu-id="ff00d-114">Organisieren von Daten und Auswählen des Layouts und Formats mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="ff00d-114">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="ff00d-115">Anzeigen eines KPI mithilfe von Hintergrundfarben</span><span class="sxs-lookup"><span data-stu-id="ff00d-115">Use Background Colors to Display a KPI</span></span>](#BackgroundColors)  
  
4.  [<span data-ttu-id="ff00d-116">Anzeigen eines KPI mit einem Messgerät</span><span class="sxs-lookup"><span data-stu-id="ff00d-116">Display a KPI by Using a Gauge</span></span>](#Gauge)  
  
5.  [<span data-ttu-id="ff00d-117">Anzeigen eines KPI mit einem Indikator</span><span class="sxs-lookup"><span data-stu-id="ff00d-117">Display a KPI by Using an Indicator</span></span>](#Indicator)  
  
6.  [<span data-ttu-id="ff00d-118">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="ff00d-118">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="ff00d-119">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="ff00d-119">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="ff00d-120">In diesem Lernprogramm werden die Schritte für den Assistenten in zwei Verfahren zusammengefasst: ein Verfahren zum Erstellen des Datasets und ein Verfahren zum Erstellen einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ff00d-120">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="ff00d-121">Im ersten Tutorial dieser Reihe erhalten Sie ausführliche Anweisungen zum Navigieren zu einem Berichtsserver, Auswählen einer Datenquelle, Erstellen eines Datasets und Ausführen des Assistenten: [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-121">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="ff00d-122">Geschätzte Zeit zum Bearbeiten dieses Tutorials: 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="ff00d-122">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff00d-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff00d-123">Requirements</span></span>  
 <span data-ttu-id="ff00d-124">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Table"></a><span data-ttu-id="ff00d-125">1. Erstellen eines Tabellen Berichts und eines Datasets mit dem Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="ff00d-125">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="ff00d-126">Wählen Sie im Dialogfeld " **Getting Started** " eine freigegebene Datenquelle aus, erstellen Sie ein eingebettetes DataSet, und zeigen Sie die Daten in einer Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="ff00d-126">From the **Getting Started** dialog box, choose a shared data source, create an embedded dataset, and display the data in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff00d-127">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-127">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="ff00d-128">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="ff00d-128">This makes the query quite long.</span></span> <span data-ttu-id="ff00d-129">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff00d-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="ff00d-130">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="ff00d-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-table"></a><span data-ttu-id="ff00d-131">So erstellen Sie eine neue Tabelle</span><span class="sxs-lookup"><span data-stu-id="ff00d-131">To create a new table</span></span>  
  
1.  <span data-ttu-id="ff00d-132">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="ff00d-133">Das Dialogfeld " **Getting Started** " wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-133">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff00d-134">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche "Berichts-Generator" auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-134">If the **Getting Started** dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="ff00d-135">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ff00d-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="ff00d-136">Klicken Sie im rechten Bereich auf **Tabellen- oder Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="ff00d-137">Klicken Sie auf der Seite Dataset auswählen auf **Dataset erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-137">On the Choose a dataset page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="ff00d-138">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ff00d-139">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichtsserver, und wählen Sie eine Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="ff00d-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source.</span></span> <span data-ttu-id="ff00d-140">Falls dort keine Datenquelle verfügbar ist oder Sie keinen Zugriff auf einen Berichtsserver haben, können Sie stattdessen eine eingebettete Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff00d-140">If there no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="ff00d-141">Weitere Informationen finden Sie unter [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-141">For more information, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="ff00d-142">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="ff00d-143">Klicken Sie auf der Seite **Abfrage entwerfen** auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="ff00d-144">Kopieren Sie die folgende Abfrage, und fügen Sie sie in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="ff00d-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
10. <span data-ttu-id="ff00d-145">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="ff00d-146">2. Organisieren von Daten, auswählen von Layout und Stil im Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="ff00d-146">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="ff00d-147">Stellen Sie mithilfe des Assistenten einen Startentwurf für die Anzeige von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="ff00d-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="ff00d-148">Im Vorschaufenster des Assistenten können Sie das Ergebnis der Datengruppierung visualisieren, bevor Sie den Tabellen- oder Matrixentwurf abschließen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-choose-a-layout-and-a-style"></a><span data-ttu-id="ff00d-149">Wählen Sie ein Layout und einen Stil aus, um Daten in Gruppen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="ff00d-149">To organize data into groups, choose a layout and a style</span></span>  
  
1.  <span data-ttu-id="ff00d-150">Ziehen Sie auf der Seite „Felder anordnen“ das Feld „Product“ in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-150">On the Arrange fields page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="ff00d-151">Ziehen Sie „Quantity“ in **Werte** , und platzieren Sie es unter „Product“.</span><span class="sxs-lookup"><span data-stu-id="ff00d-151">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="ff00d-152">Die Menge wird mit der Sum-Funktion zusammengefasst, der Standardfunktion zum Summieren numerischer Felder.</span><span class="sxs-lookup"><span data-stu-id="ff00d-152">Quantity is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
3.  <span data-ttu-id="ff00d-153">Ziehen Sie „Sales“ in **Werte** , und fügen Sie dieses Feld unter „Quantity“ ein.</span><span class="sxs-lookup"><span data-stu-id="ff00d-153">Drag Sales to **Values** and place below Quantity.</span></span>  
  
     <span data-ttu-id="ff00d-154">In Schritt 1, 2 und 3 werden die Daten angegeben, die in der Tabelle angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-154">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="ff00d-155">Ziehen Sie „SalesDate“ in **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-155">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="ff00d-156">Ziehen Sie „Subcategory“ in **Zeilengruppen** , und fügen Sie dieses Feld unter „SalesDate“ ein.</span><span class="sxs-lookup"><span data-stu-id="ff00d-156">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="ff00d-157">Durch die Schritte 4 und 5 werden die Werte für die Felder zuerst nach Datum und dann nach allen Umsätzen für dieses Datum angeordnet.</span><span class="sxs-lookup"><span data-stu-id="ff00d-157">Steps 4 and 5 organize the values for the fields first by date, and then by all sales for that date.</span></span>  
  
6.  <span data-ttu-id="ff00d-158">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-158">Click **Next**.</span></span>  
  
     <span data-ttu-id="ff00d-159">Bei der Ausführung des Berichts werden in der Tabelle jedes Datum, alle Aufträge für jedes Datum sowie alle Produkte, Mengen und Umsatzsummen für jeden Auftrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-159">When you run the report, the table displays each date, all orders for each date, and all products, quantities, and sales totals for each order.</span></span>  
  
7.  <span data-ttu-id="ff00d-160">Vergewissern Sie sich auf der Seite „Layout auswählen“, dass unter **Optionen**die Option **Teil- und Gesamtergebnisse anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ff00d-160">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
8.  <span data-ttu-id="ff00d-161">Überprüfen Sie, ob **Als Block, Teilergebnis unterhalb** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ff00d-161">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
9. <span data-ttu-id="ff00d-162">Deaktivieren Sie die Option **Gruppen erweitern/reduzieren**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-162">Clear the option **Expand/collapse groups**.</span></span>  
  
     <span data-ttu-id="ff00d-163">In diesem Lernprogramm enthält der erstellte Bericht keine Drilldownfunktion, mit der ein Benutzer eine übergeordnete Gruppenhierarchie einblenden kann, um untergeordnete Gruppenzeilen und Detailzeilen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-163">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
10. <span data-ttu-id="ff00d-164">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-164">Click **Next**.</span></span>  
  
11. <span data-ttu-id="ff00d-165">Wählen Sie auf der Seite "Format auswählen" im Bereich "Formate" ein Format aus.</span><span class="sxs-lookup"><span data-stu-id="ff00d-165">On the Choose a Style page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="ff00d-166">Die Abbildung des fertig gestellten Berichts zeigt den Bericht im Format "Ozean".</span><span class="sxs-lookup"><span data-stu-id="ff00d-166">The illustration of the completed report shows the report using the Ocean style.</span></span>  
  
12. <span data-ttu-id="ff00d-167">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-167">Click **Finish**.</span></span>  
  
     <span data-ttu-id="ff00d-168">Die Tabelle wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-168">The table is added to the design surface.</span></span> <span data-ttu-id="ff00d-169">Die Tabelle enthält fünf Spalten und fünf Zeilen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-169">The table has five columns and five rows.</span></span> <span data-ttu-id="ff00d-170">Im Bereich "Zeilengruppen" werden drei Zeilengruppen angezeigt: "SalesDate", "Subcategory" und "Details".</span><span class="sxs-lookup"><span data-stu-id="ff00d-170">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="ff00d-171">Detaildaten sind alle Daten, die von der Datasetabfrage abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ff00d-171">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
13. <span data-ttu-id="ff00d-172">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-172">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="ff00d-173">Für jedes an einem bestimmten Datum verkaufte Produkt werden in der Tabelle der Produktname, die verkaufte Menge und der Gesamtumsatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-173">For each product that is sold on a specific date, the table displays the product name, the quantity sold, and the sales total.</span></span> <span data-ttu-id="ff00d-174">Die Daten sind zuerst nach Verkaufsdatum und dann nach Unterkategorie organisiert.</span><span class="sxs-lookup"><span data-stu-id="ff00d-174">The data is organized first by sales date and then by subcategory.</span></span>  
  
##  <a name="3-use-background-colors-to-display-a-kpi"></a><a name="BackgroundColors"></a><span data-ttu-id="ff00d-175">3. Verwenden von Hintergrundfarben zum Anzeigen eines KPIs</span><span class="sxs-lookup"><span data-stu-id="ff00d-175">3. Use Background Colors to Display a KPI</span></span>  
 <span data-ttu-id="ff00d-176">Hintergrundfarben können für einen Ausdruck festgelegt werden, der beim Ausführen des Berichts ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-176">Background colors can be set to an expression that is evaluated when you run the report.</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-by-using-background-colors"></a><span data-ttu-id="ff00d-177">So zeigen Sie den aktuellen Status eines KPI mit Hintergrundfarben an</span><span class="sxs-lookup"><span data-stu-id="ff00d-177">To display the present state of a KPI by using background colors</span></span>  
  
1.  <span data-ttu-id="ff00d-178">Klicken Sie in der Tabelle mit der rechten Maustaste auf aus der `[Sum(Sales)]` Zelle (in der Teil Ergebniszeile mit dem Umsatz für eine Unterkategorie), und klicken Sie dann auf **Text Feldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-178">In the table, right-click two cells down from the `[Sum(Sales)]` cell (the subtotal row that displays the sales for a subcategory), and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="ff00d-179">Klicken Sie unter **Ausfüllen**auf die Schaltfläche **FX** neben der Option **Füllfarbe** , und geben Sie den folgenden Ausdruck in das Feld **Ausdruck festlegen für: Background Color** ein:</span><span class="sxs-lookup"><span data-stu-id="ff00d-179">In **Fill**, click the **fx** button next to the **Fill color** option and enter the following expression in the **Set expression for: BackgroundColor** field:</span></span>  
  
 `=IIF(Sum(Fields!Sales.Value) >= 5000 ,"Lime", IIF(Sum(Fields!Sales.Value) < 2500, "Red","Yellow"))`  
  
 <span data-ttu-id="ff00d-180">Dadurch wird die Hintergrundfarbe für jede Zelle, die eine kombinierte Summe für `[Sum(Sales)]` enthält, die größer oder gleich 5.000 ist, mithilfe des Grüntons "Limonengrün" in Grün geändert.</span><span class="sxs-lookup"><span data-stu-id="ff00d-180">This changes the background color to green, using the shade of green named "Lime", for each cell that contains an aggregated sum for `[Sum(Sales)]` that is greater than or equal to 5000.</span></span> <span data-ttu-id="ff00d-181">Werte von `[Sum(Sales)]` zwischen 2.500 und 5.000 werden gelb eingefärbt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-181">Values of `[Sum(Sales)]` between 2500 and 5000 are colored yellow.</span></span> <span data-ttu-id="ff00d-182">Werte kleiner als 2.500 werden rot eingefärbt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-182">Values less than 2500 are colored red.</span></span>  
  
1.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="ff00d-183">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-183">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="ff00d-184">In der Teilergebniszeile, die den Umsatz für eine Unterkategorie anzeigt, ist die Hintergrundfarbe der Zelle abhängig vom Wert der Umsatzsumme rot, gelb oder grün.</span><span class="sxs-lookup"><span data-stu-id="ff00d-184">In the subtotal row that displays the sales for a subcategory, the background color of the cell is red, yellow, or green depending on value of the sales sum.</span></span>  
  
##  <a name="4-display-a-kpi-by-using-a-gauge"></a><a name="Gauge"></a><span data-ttu-id="ff00d-185">4. Anzeigen eines KPI mit einem Messgerät</span><span class="sxs-lookup"><span data-stu-id="ff00d-185">4. Display a KPI by Using a Gauge</span></span>  
 <span data-ttu-id="ff00d-186">Ein Messgerät stellt einen einzelnen Wert in einem Dataset dar.</span><span class="sxs-lookup"><span data-stu-id="ff00d-186">A gauge depicts a single value in a dataset.</span></span> <span data-ttu-id="ff00d-187">In diesem Lernprogramm wird ein horizontales lineares Messgerät verwendet, da es aufgrund seiner Form und Einfachheit auch dann leicht zu lesen ist, wenn es klein ist und innerhalb einer Tabellenzelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-187">This tutorial uses a horizontal linear gauge because its shape and simplicity makes it easy to read, even in when it is a small size and used within a table cell.</span></span> <span data-ttu-id="ff00d-188">Weitere Informationen finden Sie unter [Messgeräte &#40;Berichts-Generator und SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-188">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-a-gauge"></a><span data-ttu-id="ff00d-189">So zeigen Sie den aktuellen Status eines KPI mit einem Messgerät an</span><span class="sxs-lookup"><span data-stu-id="ff00d-189">To display the present state of a KPI using a gauge</span></span>  
  
1.  <span data-ttu-id="ff00d-190">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="ff00d-190">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="ff00d-191">Klicken Sie in der Tabelle mit der rechten Maustaste auf den Spalten Handler für die Zelle, die Sie im vorherigen Verfahren geändert haben, zeigen Sie auf **Spalte einfügen**, und klicken Sie dann auf **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-191">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="ff00d-192">Eine neue Spalte wird der Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-192">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="ff00d-193">Geben Sie in der Spaltenüberschrift **KPI** ein.</span><span class="sxs-lookup"><span data-stu-id="ff00d-193">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="ff00d-194">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** auf **Messgerät**, und klicken Sie dann außerhalb der Tabelle auf die Entwurfs Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="ff00d-194">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click the design surface outside the table.</span></span> <span data-ttu-id="ff00d-195">Das Dialogfeld **Messgerättyp auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-195">The **Select Gauge Type** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="ff00d-196">Klicken Sie auf **linear**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-196">Click **Linear**.</span></span> <span data-ttu-id="ff00d-197">Der erste lineare Mess Messtyp ( **Horizontal**) ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-197">The first linear gauge type, **Horizontal**, is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="ff00d-198">Der Entwurfsoberfläche wird ein Messgerät hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-198">A gauge is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="ff00d-199">Ziehen Sie "Sales" aus dem Berichtsdatenbereich in das Messgerät.</span><span class="sxs-lookup"><span data-stu-id="ff00d-199">From the Report Data pane, drag Sales to the gauge.</span></span> <span data-ttu-id="ff00d-200">Wenn Sie "Sales" über das Messgerät ziehen, wird der Bereich "Messgerätdaten" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ff00d-200">When you drag Sales across the gauge, the Gauge Data pane opens.</span></span>  
  
8.  <span data-ttu-id="ff00d-201">Drop Sales in der **Werte** Liste.</span><span class="sxs-lookup"><span data-stu-id="ff00d-201">Drop Sales in the **Values** list.</span></span>  
  
     <span data-ttu-id="ff00d-202">Wenn Sie das Feld auf dem Messgerät ablegen, wird das Feld anhand der integrierten Sum-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="ff00d-202">When you drop the field onto the gauge, the field is aggregated by using the built-in Sum function.</span></span>  
  
9. <span data-ttu-id="ff00d-203">Klicken Sie mit der rechten Maustaste auf den Zeiger im Messgerät, und klicken Sie auf **Zeiger Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-203">Right-click the pointer in the gauge and click **Pointer Properties**.</span></span>  
  
10. <span data-ttu-id="ff00d-204">Wählen Sie unter **Zeigertyp**die Option **Leiste**aus.</span><span class="sxs-lookup"><span data-stu-id="ff00d-204">In **Pointer Type**, select **Bar**.</span></span> <span data-ttu-id="ff00d-205">Dadurch ändert sich der Zeiger von einem Marker in einen Balken, der besser zu sehen ist, wenn das Messgerät der Tabelle hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-205">This changes the pointer from a marker to a bar that will be more visible when the gauge is added to the table.</span></span>  
  
11. <span data-ttu-id="ff00d-206">Klicken Sie auf **Zeiger Füllung**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-206">Click **Pointer Fill**.</span></span> <span data-ttu-id="ff00d-207">Wählen Sie in **Sekundärfarbe** **Gelb**aus.</span><span class="sxs-lookup"><span data-stu-id="ff00d-207">In **Secondary Color,** pick **Yellow**.</span></span> <span data-ttu-id="ff00d-208">Das Farbverlaufsmuster verwandelt sich von Weiß in Gelb.</span><span class="sxs-lookup"><span data-stu-id="ff00d-208">The gradient fill pattern will change from white to yellow.</span></span>  
  
12. <span data-ttu-id="ff00d-209">Klicken Sie mit der rechten Maustaste auf die Skala im Messgerät, und klicken Sie auf **Skalierungseigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-209">Right-click the scale in the gauge and click **Scale Properties**.</span></span>  
  
13. <span data-ttu-id="ff00d-210">Legen Sie die Option **Maximum** auf 25000 fest.</span><span class="sxs-lookup"><span data-stu-id="ff00d-210">Set the **Maximum** option to 25000.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff00d-211">Anstelle einer Konstante wie 25.000 können Sie den Wert der Option **Maximum** auch mithilfe eines Ausdrucks dynamisch berechnen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-211">Instead of a constant such as 25000, you can use an expression to dynamically calculate the value of the **Maximum** option.</span></span> <span data-ttu-id="ff00d-212">Der Ausdruck würde das Aggregat der Aggregatfunktion verwenden und dem Ausdruck `=Max(Sum(Fields!Sales.value), "Tablix1")`ähneln.</span><span class="sxs-lookup"><span data-stu-id="ff00d-212">The expression would use the aggregate of aggregate feature and look similar to the expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span></span>  
  
14. <span data-ttu-id="ff00d-213">Ziehen Sie das Messgerät in der Tabelle in die dritte Zelle in der Teilergebniszeile, in der die Umsätze für eine Unterkategorie der von Ihnen eingefügten Spalte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff00d-213">Drag the gauge inside the table into the third cell in the subtotal row that displays the sales for a subcategory of the column that you inserted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff00d-214">Möglicherweise müssen Sie die Größe der Spalte ändern, damit das horizontale lineare Messgerät in die Zelle passt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-214">You might have to resize the column so that the horizontal linear gauge fits into the cell.</span></span> <span data-ttu-id="ff00d-215">Klicken Sie dazu auf eine Spaltenkopfzeile, und passen Sie Höhe und Breite der Zellen mithilfe der entsprechenden Ziehpunkte an.</span><span class="sxs-lookup"><span data-stu-id="ff00d-215">To resize the column, click a column header and use the handles to resize the cells horizontally and vertically.</span></span>  
  
15. <span data-ttu-id="ff00d-216">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-216">Click **Run** to preview the report.</span></span>  
  
     <span data-ttu-id="ff00d-217">Die horizontale Länge der Leiste im Messgerät ändert sich je nach Wert des KPIs.</span><span class="sxs-lookup"><span data-stu-id="ff00d-217">The horizontal length of the bar in the gauge changes depending on the value of the KPI.</span></span>  
  
16. <span data-ttu-id="ff00d-218">(Optional) Fügen Sie einen maximalen Stift zur Behandlung des Überlaufs hinzu, damit Werte, die das Skalenmaximum überschreiten, stets auf den maximalen Stift verweisen:</span><span class="sxs-lookup"><span data-stu-id="ff00d-218">(Optional) Add a maximum pin to handle overflow so that any value over the scale maximum always points to the maximum pin:</span></span>  
  
    1.  <span data-ttu-id="ff00d-219">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ff00d-219">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="ff00d-220">Klicken Sie auf die Skala.</span><span class="sxs-lookup"><span data-stu-id="ff00d-220">Click the scale.</span></span> <span data-ttu-id="ff00d-221">Die Eigenschaften für die lineare Skala werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-221">The properties for the linear scale are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="ff00d-222">Erweitern Sie in der Kategorie **Skalieren der Pins** den Knoten **MaximumPin** .</span><span class="sxs-lookup"><span data-stu-id="ff00d-222">In the **Scale Pins** category, expand the **MaximumPin** node.</span></span>  
  
    4.  <span data-ttu-id="ff00d-223">Legen Sie die Eigenschaft **aktivieren** auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="ff00d-223">Set the **Enable** property to `True`.</span></span> <span data-ttu-id="ff00d-224">Ein Stift wird nach dem maximalen Wert auf der Skala angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-224">A pin appears after the maximum value on the scale.</span></span>  
  
    5.  <span data-ttu-id="ff00d-225">Legen Sie **BorderColor** auf fest `Lime` .</span><span class="sxs-lookup"><span data-stu-id="ff00d-225">Set **BorderColor** to `Lime`.</span></span>  
  
17. <span data-ttu-id="ff00d-226">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-display-a-kpi-by-using-an-indicator"></a><a name="Indicator"></a><span data-ttu-id="ff00d-227">5. Anzeigen eines KPIs mithilfe eines Indikators</span><span class="sxs-lookup"><span data-stu-id="ff00d-227">5. Display a KPI by Using an Indicator</span></span>  
 <span data-ttu-id="ff00d-228">Indikatoren sind kleine einfache Messgeräte, die Datenwerte auf einen Blick darstellen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-228">Indicators are small simple gauges that communicate data values at a glance.</span></span> <span data-ttu-id="ff00d-229">Aufgrund ihrer Größe und Einfachheit werden Indikatoren oft in Tabellen und Matrizen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff00d-229">Because of their size and simplicity, indicators are often used in tables and matrices.</span></span> <span data-ttu-id="ff00d-230">Weitere Informationen finden Sie unter [Indikatoren (Berichts-Generator und SSRS)](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-230">For more information, see [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-an-indicator"></a><span data-ttu-id="ff00d-231">So zeigen Sie den aktuellen Status eines KPI mit einem Indikator an</span><span class="sxs-lookup"><span data-stu-id="ff00d-231">To display the present state of a KPI using an indicator</span></span>  
  
1.  <span data-ttu-id="ff00d-232">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="ff00d-232">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="ff00d-233">Klicken Sie in der Tabelle mit der rechten Maustaste auf den Spalten Handler für die Zelle, die Sie im vorherigen Verfahren geändert haben, zeigen Sie auf **Spalte einfügen**, und klicken Sie dann auf **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-233">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="ff00d-234">Eine neue Spalte wird der Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-234">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="ff00d-235">Geben Sie in der Spaltenüberschrift **KPI** ein.</span><span class="sxs-lookup"><span data-stu-id="ff00d-235">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="ff00d-236">Klicken Sie auf die Zelle für das Teilergebnis der Unterkategorie.</span><span class="sxs-lookup"><span data-stu-id="ff00d-236">Click the cell for the subcategory subtotal.</span></span>  
  
5.  <span data-ttu-id="ff00d-237">Doppelklicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** auf **Indikator.**</span><span class="sxs-lookup"><span data-stu-id="ff00d-237">On the **Insert** tab, in the **Data Regions** group, double-click **Indicator.**</span></span>  
  
     <span data-ttu-id="ff00d-238">Das Dialogfeld **Indikatortyp auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ff00d-238">The **Select Indicator Type** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="ff00d-239">Klicken Sie auf **Shapes**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-239">Click **Shapes**.</span></span> <span data-ttu-id="ff00d-240">Der erste Formtyp, **3 Ampeln (unrimmed),** wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-240">The first shape type, **3 Traffic Lights (Unrimmed),** is selected.</span></span>  
  
     <span data-ttu-id="ff00d-241">In diesem Lernprogramm verwenden Sie diesen Indikator.</span><span class="sxs-lookup"><span data-stu-id="ff00d-241">You will use this indicator in the tutorial.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="ff00d-242">Der Indikator wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-242">The indicator is added to the design surface.</span></span>  
  
8.  <span data-ttu-id="ff00d-243">Klicken Sie mit der rechten Maustaste auf den Indikator, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-243">Right-click the indicator and click **Indicator Properties**.</span></span>  
  
9. <span data-ttu-id="ff00d-244">Klicken Sie auf **Werte und Zustände**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-244">Click **Values and States**.</span></span>  
  
10. <span data-ttu-id="ff00d-245">Wählen Sie in der Dropdown Liste Wert den Wert **[Sum (Sales)]** aus, ändern Sie jedoch keine weiteren Optionen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-245">In the Value drop-down list, select **[Sum(Sales)]**, but do not change any other options.</span></span>  
  
     <span data-ttu-id="ff00d-246">Standardmäßig findet eine Datensynchronisierung im Datenbereich statt, und der Wert **Tablix1**, der Name des Tabellendatenbereichs im Bericht, wird im Feld **Synchronisierungsbereich** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-246">By default, data synchronization occurs across the data region and you see the value **Tablix1**, the name of the table data region in the report, in the **Synchronization scope** box.</span></span>  
  
     <span data-ttu-id="ff00d-247">In diesem Bericht können Sie auch den Bereich eines Indikators ändern, der in der Zelle für das Teilergebnis der Unterkategorie eingefügt wurde, um das Feld "SalesDate" zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="ff00d-247">In this report, you can also change the scope of an indicator placed in the cell of the subcategory subtotal to synchronize across the SalesDate field.</span></span>  
  
11. <span data-ttu-id="ff00d-248">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-248">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="ff00d-249">6. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="ff00d-249">6. Add a Report Title</span></span>  
 <span data-ttu-id="ff00d-250">Ein Berichtstitel wird oben im Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-250">A report title appears at the top of the report.</span></span> <span data-ttu-id="ff00d-251">Sie können den Berichtstitel in eine Berichtskopfzeile einfügen oder, wenn der Bericht keine Kopfzeile enthält, in einem Textfeld am oberen Rand des Berichtshauptteils.</span><span class="sxs-lookup"><span data-stu-id="ff00d-251">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="ff00d-252">Sie verwenden das Textfeld, das automatisch am oberen Rand des Berichtshauptteils platziert wird.</span><span class="sxs-lookup"><span data-stu-id="ff00d-252">You will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="ff00d-253">Die Darstellung des Texts kann weiter verbessert werden, indem andere Schriftschnitte, Größen und Farben für Ausdrücke und einzelne Zeichen des Texts angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff00d-253">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="ff00d-254">Weitere Informationen finden Sie unter [Formatieren von Text in einem Textfeld (Berichts-Generator und SSRS)](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-254">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="ff00d-255">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="ff00d-255">To add a report title</span></span>  
  
1.  <span data-ttu-id="ff00d-256">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-256">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="ff00d-257">Geben Sie **Product Sales KPI**ein, und klicken Sie dann außerhalb des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="ff00d-257">Type **Product Sales KPI**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="ff00d-258">Klicken Sie optional mit der rechten Maustaste auf das Textfeld mit dem **Product Sales-KPI**, klicken Sie auf **Text Feldeigenschaften**, und wählen Sie dann auf der Registerkarte Schriftart die verschiedenen Schriftarten, Größen und Farben aus.</span><span class="sxs-lookup"><span data-stu-id="ff00d-258">Optionally, right-click the text box that contains **Product Sales KPI**, click **Text Box Properties**, and then on the Font tab select the different font styles, sizes and colors.</span></span>  
  
4.  <span data-ttu-id="ff00d-259">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-259">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="ff00d-260">7. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="ff00d-260">7. Save the Report</span></span>  
 <span data-ttu-id="ff00d-261">Speichern Sie den Bericht auf einem Berichtsserver oder auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="ff00d-261">Save the report to a report server or your computer.</span></span> <span data-ttu-id="ff00d-262">Wenn Sie den Bericht nicht auf dem Berichtsserver speichern, ist eine Reihe von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen nicht verfügbar, z. B. Berichtsteile und Unterberichte.</span><span class="sxs-lookup"><span data-stu-id="ff00d-262">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="ff00d-263">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="ff00d-263">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="ff00d-264">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-264">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="ff00d-265">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-265">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="ff00d-266">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="ff00d-266">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="ff00d-267">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-267">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="ff00d-268">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="ff00d-268">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="ff00d-269">Ersetzen Sie im Feld **Name**den Standardnamen durch **Produktumsatz-KPI**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-269">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
5.  <span data-ttu-id="ff00d-270">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-270">Click **Save**.</span></span>  
  
 <span data-ttu-id="ff00d-271">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ff00d-271">The report is saved to the report server.</span></span> <span data-ttu-id="ff00d-272">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff00d-272">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="ff00d-273">So speichern Sie den Bericht auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="ff00d-273">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="ff00d-274">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-274">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="ff00d-275">Klicken Sie auf **Desktop**, **Eigene Dokumente**oder **Computer**, und navigieren Sie zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ff00d-275">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff00d-276">Wenn Sie keinen Zugriff auf einen Berichtsserver haben, klicken Sie auf **Desktop**&gt; **Eigene Dokumente**oder **Arbeitsplatz** , und speichern Sie den Bericht auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ff00d-276">If you do not have access to a report server, click **Desktop**, **My Documents**, or **My computer** and save the report to your computer.</span></span>  
  
1.  <span data-ttu-id="ff00d-277">Ersetzen Sie im Feld **Name**den Standardnamen durch **Produktumsatz-KPI**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-277">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
2.  <span data-ttu-id="ff00d-278">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff00d-278">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ff00d-279">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ff00d-279">Next Steps</span></span>  
 <span data-ttu-id="ff00d-280">Sie haben das Lernprogramm "Hinzufügen eines KPI zu einem Bericht" erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ff00d-280">You have successfully completed the Adding a KPI to Your Report tutorial.</span></span> <span data-ttu-id="ff00d-281">Weitere Informationen finden Sie unter Messgeräte Indikatoren (Berichts-Generator) [&#40;Berichts-Generator und SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff00d-281">For more information, see Gauges (Report Builder) [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff00d-282">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff00d-282">See Also</span></span>  
 <span data-ttu-id="ff00d-283">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="ff00d-283">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="ff00d-284">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ff00d-284">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
