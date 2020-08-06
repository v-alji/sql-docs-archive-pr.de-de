---
title: 'Tutorial: Hinzufügen einer Sparkline zum Bericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 18c90a36-48bf-4805-a960-2d1e8f00c2dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1bf83810b6c743b977e399864ce2edd514f572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720956"
---
# <a name="tutorial-add-a-sparkline-to-your-report-report-builder"></a><span data-ttu-id="c3403-102">Lernprogramm: Hinzufügen einer Sparkline zum Bericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="c3403-102">Tutorial: Add a Sparkline to Your Report (Report Builder)</span></span>
  <span data-ttu-id="c3403-103">In diesem Lernprogramm erstellen Sie auf Grundlage der Beispielumsatzdaten einen einfachen Tabellenbericht und fügen anschließend einer Zelle in der Tabelle ein Sparklinediagramm hinzu.</span><span class="sxs-lookup"><span data-stu-id="c3403-103">In this tutorial, you create a basic table report based on sample sales data, and then add a sparkline chart to a cell in the table.</span></span>  
  
 <span data-ttu-id="c3403-104">Eine erweiterte Version des Berichts, den Sie in diesem Lernprogramm erstellen, ist als [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Berichts-Generator-Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c3403-104">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="c3403-105">Weitere Informationen zum Herunterladen dieses Beispiel Berichts und anderer Informationen finden Sie unter [Berichts-Generator-Beispiel Berichte](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="c3403-105">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span> <span data-ttu-id="c3403-106">Die folgende Abbildung zeigt den Beispielbericht, der dem Bericht ähnelt, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3403-106">The following illustration shows the sample report similar to the one that you will create.</span></span>  
  
 <span data-ttu-id="c3403-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span><span class="sxs-lookup"><span data-stu-id="c3403-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span></span>  
  
 <span data-ttu-id="c3403-108">Das Video Gewusst [wie: Erstellen einer sparkline in einer Tabelle (Berichts-Generator Video)](https://technet.microsoft.com/bi/ff871942.aspx) veranschaulicht, wie ein ähnlicher Bericht mit Sparklines erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c3403-108">The video [How to: Create a Sparkline in a Table (Report Builder Video)](https://technet.microsoft.com/bi/ff871942.aspx) illustrates how to create a similar report with sparklines.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="c3403-109">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="c3403-109">What You Will Learn</span></span>  
 <span data-ttu-id="c3403-110">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c3403-110">In this tutorial, you will learn how to do the following:</span></span>  
  
 1. [<span data-ttu-id="c3403-111">Erstellen eines Berichts mit einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="c3403-111">Create a Report with a Table</span></span>](#CreateTable)  
  
 2. [<span data-ttu-id="c3403-112">Erstellen einer Abfrage im Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="c3403-112">Create a Query in the Table or Matrix Wizard</span></span>](#Query)  
  
 3. [<span data-ttu-id="c3403-113">Hinzufügen einer Sparkline zur Tabelle</span><span class="sxs-lookup"><span data-stu-id="c3403-113">Add a Sparkline to the Table</span></span>](#Sparkline)  
  
 4. [<span data-ttu-id="c3403-114">Vertikales und horizontales Ausrichten der Sparklines</span><span class="sxs-lookup"><span data-stu-id="c3403-114">Align the Sparklines Vertically and Horizontally</span></span>](#AlignSparklines)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="c3403-115">Weitere optionale Schritte</span><span class="sxs-lookup"><span data-stu-id="c3403-115">Other Optional Steps</span></span>  
 5. [<span data-ttu-id="c3403-116">Formatieren von Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="c3403-116">Format Data as Currency</span></span>](#FormatCurrency)  
  
 6. [<span data-ttu-id="c3403-117">Formatieren von Daten als Datumsangaben</span><span class="sxs-lookup"><span data-stu-id="c3403-117">Format Data as Dates</span></span>](#FormatDates)  
  
 7. [<span data-ttu-id="c3403-118">Ändern der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="c3403-118">Change Column Widths</span></span>](#Width)  
  
 8. [<span data-ttu-id="c3403-119">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="c3403-119">Add a Report Title</span></span>](#Title)  
  
 9. [<span data-ttu-id="c3403-120">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="c3403-120">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="c3403-121">Geschätzte Zeit zum Bearbeiten dieses Lernprogramms: 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="c3403-121">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3403-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3403-122">Requirements</span></span>  
 <span data-ttu-id="c3403-123">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="c3403-123">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-report-with-a-table"></a><a name="CreateTable"></a><span data-ttu-id="c3403-124">1. Erstellen eines Berichts mit einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="c3403-124">1. Create a Report with a Table</span></span>  
  
#### <a name="to-create-a-report"></a><span data-ttu-id="c3403-125">So erstellen Sie einen Bericht</span><span class="sxs-lookup"><span data-stu-id="c3403-125">To create a report</span></span>  
  
1.  <span data-ttu-id="c3403-126">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="c3403-126">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="c3403-127">Das Dialogfeld **Erste Schritte** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c3403-127">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3403-128">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche " **Berichts-Generator** " auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="c3403-128">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="c3403-129">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c3403-129">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="c3403-130">Klicken Sie im rechten Bereich auf **Tabellen- oder Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="c3403-130">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="c3403-131">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-131">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="c3403-132">Die Seite **Verbindung mit einer Datenquelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c3403-132">The **Choose a connection to a data source** page opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3403-133">Für dieses Lernprogramm sind keine bestimmten Daten erforderlich; es wird lediglich eine Verbindung mit einer [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] -Datenbank benötigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-133">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="c3403-134">Wenn unter **Datenquellenverbindungen**bereits eine Datenquellenverbindung aufgeführt ist, können Sie sie auswählen und zu Schritt 10 wechseln.</span><span class="sxs-lookup"><span data-stu-id="c3403-134">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to step 10.</span></span> <span data-ttu-id="c3403-135">Weitere Informationen finden Sie unter [Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c3403-135">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  <span data-ttu-id="c3403-136">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="c3403-136">Click **New**.</span></span> <span data-ttu-id="c3403-137">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-137">The **Data Source Properties** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="c3403-138">Geben Sie im Feld **Name**den Namen **Product Sales**für die Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="c3403-138">In **Name**, type **Product Sales**, a name for the data source.</span></span>  
  
7.  <span data-ttu-id="c3403-139">Vergewissern Sie sich, dass unter **Verbindungstyp auswählen**die Option **Microsoft SQL Server** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c3403-139">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
8.  <span data-ttu-id="c3403-140">Geben Sie für **Verbindungszeichenfolge**den folgenden Text ein:</span><span class="sxs-lookup"><span data-stu-id="c3403-140">In **Connection string**, type the following text:</span></span>  
  
     <span data-ttu-id="c3403-141">**Datenquelle =\<servername>**</span><span class="sxs-lookup"><span data-stu-id="c3403-141">**Data Source=\<servername>**</span></span>  
  
     <span data-ttu-id="c3403-142">Der Ausdruck \<servername>, z.B. „Report001“, bezeichnet einen Computer, auf dem eine Instanz der SQL Server-Datenbank-Engine installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c3403-142">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="c3403-143">Da die Berichtsdaten nicht aus einer SQL Server-Datenbank extrahiert werden, muss der Name einer Datenbank nicht eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-143">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="c3403-144">Die Standarddatenbank auf dem angegebenen Server wird verwendet, um die Abfrage zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="c3403-144">The default database on the specified server is used to parse the query.</span></span>  
  
9. <span data-ttu-id="c3403-145">Klicken Sie auf **Anmeldeinformationen**.</span><span class="sxs-lookup"><span data-stu-id="c3403-145">Click **Credentials**.</span></span> <span data-ttu-id="c3403-146">Geben Sie die für den Zugriff auf die externe Datenquelle benötigten Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="c3403-146">Enter the credentials that you need to access the external data source.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c3403-147">Nun wird wieder die Seite **Verbindung mit einer Datenquelle auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-147">You are back on the **Choose a connection to a data source** page.</span></span>  
  
11. <span data-ttu-id="c3403-148">Klicken Sie auf **Verbindung testen**, um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3403-148">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="c3403-149">Die Meldung "Die Verbindung wurde erfolgreich hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-149">The message "Connection created successfully" appears.</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="c3403-150">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-150">Click **Next**.</span></span>  
  
##  <a name="2-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="c3403-151">2. Erstellen einer Abfrage im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="c3403-151">2. Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="c3403-152">In einem Bericht können Sie ein freigegebenes Dataset mit einer vordefinierten Abfrage verwenden oder ein eingebettetes Dataset erstellen, das nur in Ihrem Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3403-152">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="c3403-153">In diesem Lernprogramm erstellen Sie ein eingebettetes Dataset.</span><span class="sxs-lookup"><span data-stu-id="c3403-153">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3403-154">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c3403-154">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="c3403-155">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="c3403-155">This makes the query quite long.</span></span> <span data-ttu-id="c3403-156">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3403-156">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="c3403-157">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="c3403-157">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="c3403-158">So erstellen Sie eine Abfrage</span><span class="sxs-lookup"><span data-stu-id="c3403-158">To create a query</span></span>  
  
1.  <span data-ttu-id="c3403-159">Auf der Seite **Abfrage entwerfen** ist der relationale Abfrage-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c3403-159">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="c3403-160">Für dieses Lernprogramm verwenden Sie den textbasierten Abfrage-Designer.</span><span class="sxs-lookup"><span data-stu-id="c3403-160">For this tutorial, you will use the text-based query designer.</span></span>  
  
2.  <span data-ttu-id="c3403-161">Klicken Sie auf **als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c3403-161">Click **Edit As Text**.</span></span> <span data-ttu-id="c3403-162">Der textbasierte Abfrage-Designer umfasst zwei Bereiche: den Abfragebereich und den Ergebnisbereich.</span><span class="sxs-lookup"><span data-stu-id="c3403-162">The text-based query designer displays a query pane and a results pane.</span></span>  
  
3.  <span data-ttu-id="c3403-163">Fügen Sie die folgende [!INCLUDE[tsql](../includes/tsql-md.md)] -Abfrage in das Feld **Abfrage** ein.</span><span class="sxs-lookup"><span data-stu-id="c3403-163">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Budget Movie-Maker' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Slim Digital' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,'Accessories' as Subcategory,    
       'Budget Movie-Maker' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2010-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Carrying Case' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
4.  <span data-ttu-id="c3403-164">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf „Ausführen“ (**!**).</span><span class="sxs-lookup"><span data-stu-id="c3403-164">On the query designer toolbar, click Run  (**!**).</span></span>  
  
     <span data-ttu-id="c3403-165">Die Abfrage wird ausgeführt, und das Resultset für die Felder **SalesDate**, **Subcategory**, **Product**, **Sales**und **Quantity**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-165">The query runs and displays the result set for the fields **SalesDate**, **Subcategory**, **Product**, **Sales**, and **Quantity**.</span></span>  
  
5.  <span data-ttu-id="c3403-166">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-166">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c3403-167">Ziehen Sie auf der Seite **Felder anordnen** das Feld **Sales** in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="c3403-167">On the **Arrange fields** page, drag **Sales** to **Values**.</span></span>  
  
     <span data-ttu-id="c3403-168">**Sales** wird von der Sum-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="c3403-168">**Sales** is aggregated by the Sum function.</span></span> <span data-ttu-id="c3403-169">Der Wert ist "[Sum(Sales)]".</span><span class="sxs-lookup"><span data-stu-id="c3403-169">The value is [Sum(Sales)].</span></span>  
  
7.  <span data-ttu-id="c3403-170">Ziehen Sie **Product** in **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="c3403-170">Drag **Product** to **Row groups**.</span></span>  
  
8.  <span data-ttu-id="c3403-171">Ziehen Sie **SalesDate** in **Spaltengruppen**.</span><span class="sxs-lookup"><span data-stu-id="c3403-171">Drag **SalesDate** to **Column groups**.</span></span>  
  
9. <span data-ttu-id="c3403-172">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-172">Click **Next**.</span></span>  
  
10. <span data-ttu-id="c3403-173">Vergewissern Sie sich, dass auf der Seite **Layout auswählen** unter **Optionen die Option** **Teil-und Gesamtsummen anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c3403-173">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="c3403-174">Im Vorschaubereich des Assistenten wird eine Tabelle mit drei Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-174">The wizard Preview pane displays a table with three rows.</span></span> <span data-ttu-id="c3403-175">Bei der Ausführung des Berichts wird jede Zeile wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c3403-175">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="c3403-176">Die erste Zeile erscheint einmal, damit Spaltenüberschriften in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-176">The first row will appear once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="c3403-177">Die zweite Zeile wird einmal für jedes Produkt wiederholt. In dieser Zeile werden Produktname, Summe pro Tag und die Zeilensumme angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-177">The second row will repeat once for each product and display the product name, total per day, and line total.</span></span>  
  
    3.  <span data-ttu-id="c3403-178">Die dritte Zeile erscheint einmal, damit Gesamtsummen in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-178">The third row will appear once for the table to display the grand totals.</span></span>  
  
11. <span data-ttu-id="c3403-179">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-179">Click **Next**.</span></span>  
  
12. <span data-ttu-id="c3403-180">Wählen Sie auf der Seite **Format auswählen** im Bereich **Formate** die Option **Schiefer**aus.</span><span class="sxs-lookup"><span data-stu-id="c3403-180">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>  
  
     <span data-ttu-id="c3403-181">Im Vorschaubereich wird ein Beispiel für die Tabelle mit diesem Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-181">The Preview pane displays a sample of the table with that style.</span></span>  
  
13. <span data-ttu-id="c3403-182">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c3403-182">Click **Finish**.</span></span>  
  
14. <span data-ttu-id="c3403-183">Die Tabelle wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c3403-183">The table is added to the design surface.</span></span> <span data-ttu-id="c3403-184">Die Tabelle enthält drei Spalten und drei Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c3403-184">The table has three columns and three rows.</span></span>  
  
     <span data-ttu-id="c3403-185">Betrachten Sie den Gruppierungsbereich.</span><span class="sxs-lookup"><span data-stu-id="c3403-185">Look in the Grouping pane.</span></span> <span data-ttu-id="c3403-186">Wenn der Gruppierungsbereich nicht angezeigt wird, klicken Sie im Menü **Ansicht** auf **Gruppierung**.</span><span class="sxs-lookup"><span data-stu-id="c3403-186">If you can't see the Grouping pane, on the **View** menu, click **Grouping**.</span></span> <span data-ttu-id="c3403-187">Im Zeilengruppenbereich wird eine Zeilengruppe angezeigt: **Product**.</span><span class="sxs-lookup"><span data-stu-id="c3403-187">The Row Groups pane shows one row group: **Product**.</span></span> <span data-ttu-id="c3403-188">Im Spaltengruppenbereich wird eine Spaltengruppe angezeigt: **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="c3403-188">The Column Groups pane shows one column group: **SalesDate**.</span></span> <span data-ttu-id="c3403-189">Detaildaten sind alle Daten, die von der Datasetabfrage abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-189">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
15. <span data-ttu-id="c3403-190">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-190">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-add-a-sparkline"></a><a name="Sparkline"></a><span data-ttu-id="c3403-191">3. Hinzufügen einer sparkline</span><span class="sxs-lookup"><span data-stu-id="c3403-191">3. Add a Sparkline</span></span>  
  
#### <a name="to-add-a-sparkline-chart-to-a-table"></a><span data-ttu-id="c3403-192">So fügen Sie einer Tabelle ein Sparklinediagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="c3403-192">To add a sparkline chart to a table</span></span>  
  
1.  <span data-ttu-id="c3403-193">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="c3403-193">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c3403-194">Wählen Sie die Summenspalte in der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c3403-194">Select the Total column in your table.</span></span>  
  
3.  <span data-ttu-id="c3403-195">Führen Sie einen Rechtsklick aus, zeigen Sie auf **Spalte einfügen**, und klicken Sie anschließend auf **Links**.</span><span class="sxs-lookup"><span data-stu-id="c3403-195">Right-click, point to **Insert Column**, and then click **Left**.</span></span>  
  
4.  <span data-ttu-id="c3403-196">Klicken Sie in der neuen Spalte mit der rechten Maustaste in die Zeile [Product], zeigen Sie auf die Registerkarte des Menübands **Einfügen** , und klicken Sie dann auf **sparkline**.</span><span class="sxs-lookup"><span data-stu-id="c3403-196">In the new column, right-click in the [Product] row, point to the **Insert** ribbon tab, and then click **Sparkline**.</span></span>  
  
5.  <span data-ttu-id="c3403-197">Stellen Sie sicher, dass die erste sparkline in der **Spalten** Zeile ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3403-197">Make sure the first sparkline in the **Column** row is selected and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="c3403-198">Klicken Sie zum Anzeigen des Diagrammdatenbereichs auf die Sparkline.</span><span class="sxs-lookup"><span data-stu-id="c3403-198">Click the sparkline to show the Chart Data pane.</span></span>  
  
7.  <span data-ttu-id="c3403-199">Klicken Sie im Feld Werte auf das Pluszeichen (+), und klicken Sie dann auf **Sales**.</span><span class="sxs-lookup"><span data-stu-id="c3403-199">Click the plus (+) sign in the Values box, and then click **Sales**.</span></span>  
  
     <span data-ttu-id="c3403-200">Die Werte im Feld **Sales** sind nun die Werte für die Sparkline.</span><span class="sxs-lookup"><span data-stu-id="c3403-200">The values in the **Sales** field are now the values for the sparkline.</span></span>  
  
8.  <span data-ttu-id="c3403-201">Klicken Sie im Feld Kategoriegruppen auf das Pluszeichen (+), und klicken Sie dann auf **salesdate**.</span><span class="sxs-lookup"><span data-stu-id="c3403-201">Click the plus (+) sign in the Category Groups box, and then click **SalesDate**.</span></span>  
  
9. <span data-ttu-id="c3403-202">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-202">Click **Run** to preview your report.</span></span>  
  
     <span data-ttu-id="c3403-203">In jeder Zeile der Tabelle sind Sparklinediagramme enthalten, die jedoch nicht korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="c3403-203">Note that there are sparkline charts in each row of the table, but they're not correct.</span></span> <span data-ttu-id="c3403-204">Die Balken in den Diagrammen weisen nicht die gleiche Breite auf.</span><span class="sxs-lookup"><span data-stu-id="c3403-204">The bars in the charts don't line up with each other.</span></span> <span data-ttu-id="c3403-205">In der zweiten Datenzeile befinden sich nur vier Balken, weshalb die Balken breiter als in der ersten Zeile sind, die sechs Balken enthält.</span><span class="sxs-lookup"><span data-stu-id="c3403-205">There are only four bars in the second row of data, so the bars are wider than the bars in the first row, which has six.</span></span> <span data-ttu-id="c3403-206">Werte für die einzelnen Produkte können nicht pro Tag verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-206">You can't compare values for each product per day.</span></span> <span data-ttu-id="c3403-207">Sie müssen die gleiche Breite aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c3403-207">They need to line up with each other.</span></span>  
  
     <span data-ttu-id="c3403-208">Für jede Zeile entspricht die maximale Balkenlänge der jeweiligen Höhe der Zeile.</span><span class="sxs-lookup"><span data-stu-id="c3403-208">Also note that for each row, the tallest bar for that row is the height of the row.</span></span> <span data-ttu-id="c3403-209">Dies ist auch irreführend, da die größten Werte für jede Zeile nicht gleich sind: der größte Wert für "Budget Movie-Maker" ist $10.400, aber der größte Wert für "Slim Digital" ist $26.576-mehr als doppelt so groß.</span><span class="sxs-lookup"><span data-stu-id="c3403-209">This is misleading, too, because the largest values for each row are not equal: the largest value for Budget Movie-Maker is $10,400, but the largest value for Slim Digital is $26,576-more than twice as large.</span></span> <span data-ttu-id="c3403-210">Dennoch sind die größten Balken in diesen zwei Zeilen etwa gleich hoch.</span><span class="sxs-lookup"><span data-stu-id="c3403-210">And yet the largest bars in those two rows are about the same height.</span></span> <span data-ttu-id="c3403-211">Auch das muss an die anderen Sparklines angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-211">That also needs to be made to scale with the other sparklines.</span></span>  
  
     <span data-ttu-id="c3403-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span><span class="sxs-lookup"><span data-stu-id="c3403-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span></span>  
  
##  <a name="4-align-the-sparklines-vertically-and-horizontally"></a><a name="AlignSparklines"></a><span data-ttu-id="c3403-213">4. horizontales und horizontales Ausrichten der Sparklines</span><span class="sxs-lookup"><span data-stu-id="c3403-213">4. Align the Sparklines Vertically and Horizontally</span></span>  
 <span data-ttu-id="c3403-214">Die Sparklines sind schwer zu lesen, wenn Sie nicht alle die gleichen Messungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3403-214">The sparklines are hard to read when they don't all use the same measurements.</span></span> <span data-ttu-id="c3403-215">Sowohl die horizontale als auch die vertikale Achse muss mit dem Rest übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c3403-215">Both the horizontal and vertical axes for each need to match the rest.</span></span>  
  
#### <a name="to-set-alignment-for-the-sparklines-in-the-table"></a><span data-ttu-id="c3403-216">So legen Sie die Ausrichtung für die Sparklines in der Tabelle fest</span><span class="sxs-lookup"><span data-stu-id="c3403-216">To set alignment for the sparklines in the table</span></span>  
  
1.  <span data-ttu-id="c3403-217">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="c3403-217">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c3403-218">Klicken Sie mit der rechten Maustaste auf die Sparkline, und klicken Sie auf **Eigenschaften für vertikale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="c3403-218">Right-click the sparkline and click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="c3403-219">Aktivieren Sie das Kontrollkästchen **Achsen ausrichten in** .</span><span class="sxs-lookup"><span data-stu-id="c3403-219">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="c3403-220">Tablix1 wird in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-220">Tablix1 is showing in the list.</span></span> <span data-ttu-id="c3403-221">Das ist die einzige Option.</span><span class="sxs-lookup"><span data-stu-id="c3403-221">That is the only option.</span></span> <span data-ttu-id="c3403-222">Dadurch wird die Höhe der Balken in jeder Sparkline relativ zu den anderen Balken festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c3403-222">This sets the height of the bars in each sparkline relative to the others.</span></span>  
  
4.  <span data-ttu-id="c3403-223">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3403-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c3403-224">Klicken Sie mit der rechten Maustaste auf die Sparkline, und klicken Sie auf **Eigenschaften für horizontale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="c3403-224">Right-click the sparkline and click **Horizontal Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="c3403-225">Aktivieren Sie das Kontrollkästchen **Achsen ausrichten in** .</span><span class="sxs-lookup"><span data-stu-id="c3403-225">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="c3403-226">Tablix1 wird in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-226">Tablix1 is showing in the list.</span></span> <span data-ttu-id="c3403-227">Das ist die einzige Option.</span><span class="sxs-lookup"><span data-stu-id="c3403-227">That is the only option.</span></span> <span data-ttu-id="c3403-228">Dadurch wird die Breite der Balken in jeder Sparkline relativ zu den anderen Balken festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c3403-228">This sets the width of the bars in each sparkline relative to the others.</span></span> <span data-ttu-id="c3403-229">Wenn in einigen Sparklines weniger Balken enthalten sind, enthalten diese Sparklines Leerräume für die fehlenden Daten.</span><span class="sxs-lookup"><span data-stu-id="c3403-229">If some sparklines have fewer bars than others, then those sparklines will have blank spaces for the missing data.</span></span>  
  
7.  <span data-ttu-id="c3403-230">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3403-230">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="c3403-231">Klicken Sie auf **Ausführen** , um den Bericht erneut in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-231">Click **Run** to preview your report again.</span></span>  
  
 <span data-ttu-id="c3403-232">Die Ausrichtung aller Balken entspricht nun der der Balken in den anderen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c3403-232">Note that all the bars are now aligned with the bars in the other rows.</span></span>  
  
##  <a name="5-optional-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="c3403-233">5. (optional) Formatieren von Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="c3403-233">5. (Optional) Format Data as Currency</span></span>  
 <span data-ttu-id="c3403-234">Standardmäßig wird in den Zusammenfassungs Daten für das Feld **Sales** eine allgemeine Zahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-234">By default, the summary data for the **Sales** field displays a general number.</span></span> <span data-ttu-id="c3403-235">Formatieren Sie das Feld, um die Zahl als Währung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-235">Format it to display the number as currency.</span></span> <span data-ttu-id="c3403-236">Ändern Sie die Einstellung der Option **Platzhalterformate** , um formatierte Textfelder und Platzhaltertext als Beispielwerte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-236">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="c3403-237">So formatieren Sie ein Währungsfeld</span><span class="sxs-lookup"><span data-stu-id="c3403-237">To format a currency field</span></span>  
  
1.  <span data-ttu-id="c3403-238">Klicken Sie auf **Entwurf** , um zur Entwurfs Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="c3403-238">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="c3403-239">Klicken Sie in der Spalte **salesdate** auf die Zelle in der zweiten Zeile (unter der Zeile Spaltenüberschriften), und wählen Sie alle Zellen aus, die enthalten `[Sum(Sales)]` .</span><span class="sxs-lookup"><span data-stu-id="c3403-239">Click the cell in the second row (under the column headings row) in the **SalesDate** column and drag to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="c3403-240">Klicken Sie auf der Registerkarte **Stamm** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="c3403-240">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="c3403-241">Die Zellen ändern sich, um die formatierte Währung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-241">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="c3403-242">Wenn Sie das Gebietsschema „Deutsch (Deutschland)“ verwenden, lautet der Standardbeispieltext [**12,345.00€**].</span><span class="sxs-lookup"><span data-stu-id="c3403-242">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="c3403-243">Wenn kein Beispiel Währungswert angezeigt wird, klicken Sie in der Gruppe **Zahlen** auf **Platzhalter** Formate und dann auf **Beispiel Werte**.</span><span class="sxs-lookup"><span data-stu-id="c3403-243">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="c3403-244">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-244">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="c3403-245">Die Zusammenfassungs Werte für **Sales** werden als Währung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-245">The summary values for **Sales** display as currency.</span></span>  
  
##  <a name="6-optional-format-data-as-dates"></a><a name="FormatDates"></a><span data-ttu-id="c3403-246">6. (optional) Formatieren von Daten als Datumsangaben</span><span class="sxs-lookup"><span data-stu-id="c3403-246">6. (Optional) Format Data as Dates</span></span>  
 <span data-ttu-id="c3403-247">Standardmäßig werden im Feld **salesdate** sowohl Datums-als auch Uhrzeit Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-247">By default, the **SalesDate** field displays both date and time information.</span></span> <span data-ttu-id="c3403-248">Durch entsprechende Formatierung kann auch nur das Datum angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-248">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="c3403-249">So formatieren Sie ein Datumsfeld als Standardformat</span><span class="sxs-lookup"><span data-stu-id="c3403-249">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="c3403-250">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="c3403-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c3403-251">Klicken Sie auf die Zelle, die `[SalesDate]`enthält.</span><span class="sxs-lookup"><span data-stu-id="c3403-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="c3403-252">Wählen Sie im Menüband auf der Registerkarte **Startseite** in der Gruppe **Zahl** in der Dropdown Liste **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="c3403-252">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="c3403-253">In der Zelle wird das Beispieldatum **[31.01.2000]** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-253">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="c3403-254">Falls kein Beispieldatum angezeigt wird, klicken Sie in der Gruppe **Zahlen** auf **Platzhalterformate** und anschließend auf **Beispielwerte**.</span><span class="sxs-lookup"><span data-stu-id="c3403-254">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="c3403-255">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-255">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="c3403-256">Die **salesdate** -Werte werden im Standard Datumsformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-256">The **SalesDate** values display in the default date format.</span></span>  
  
##  <a name="7-optional-change-column-widths"></a><a name="Width"></a><span data-ttu-id="c3403-257">7. (optional) Ändern der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="c3403-257">7. (Optional) Change Column Widths</span></span>  
 <span data-ttu-id="c3403-258">Standardmäßig enthält jede Zelle in einer Tabelle ein Textfeld.</span><span class="sxs-lookup"><span data-stu-id="c3403-258">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="c3403-259">Textfelder werden beim Rendern der Seite entsprechend dem anzuzeigenden Text vertikal erweitert.</span><span class="sxs-lookup"><span data-stu-id="c3403-259">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="c3403-260">Im gerenderten Bericht werden alle Zeilen auf die Höhe des größten gerenderten Textfelds in der Zeile vergrößert.</span><span class="sxs-lookup"><span data-stu-id="c3403-260">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="c3403-261">Die Höhe der Zeile auf der Entwurfsoberfläche hat keinen Einfluss auf die Höhe der Zeile im gerenderten Bericht.</span><span class="sxs-lookup"><span data-stu-id="c3403-261">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="c3403-262">Um die Höhe der Zeilen zu reduzieren, vergrößern Sie die Spaltenbreite, sodass der erwartete Inhalt der Textfelder in der Spalte in einer Zeile untergebracht werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3403-262">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-columns"></a><span data-ttu-id="c3403-263">So ändern Sie die Breite von Spalten</span><span class="sxs-lookup"><span data-stu-id="c3403-263">To change the width of columns</span></span>  
  
1.  <span data-ttu-id="c3403-264">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="c3403-264">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c3403-265">Klicken Sie auf die Tabelle, damit die Spalten- und Zeilenhandles über und neben der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-265">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="c3403-266">Die grauen Balken oberhalb und neben der Tabelle stellen die Spalten- und Zeilenhandles dar.</span><span class="sxs-lookup"><span data-stu-id="c3403-266">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="c3403-267">Zeigen Sie auf die Zeile zwischen Spaltenhandles, sodass sich der Cursor in einen Doppelpfeil ändert.</span><span class="sxs-lookup"><span data-stu-id="c3403-267">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="c3403-268">Ziehen Sie die Spalten auf die gewünschte Größe.</span><span class="sxs-lookup"><span data-stu-id="c3403-268">Drag the columns to the size you want.</span></span> <span data-ttu-id="c3403-269">Beispiel: Erweitern Sie die Spalte für **Produkt** , damit der Produktname auf einer Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c3403-269">For example, expand the column for **Product** so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="c3403-270">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3403-270">Click **Run** to preview your report.</span></span>  
  
##  <a name="8-optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="c3403-271">8. (optional) Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="c3403-271">8. (Optional) Add a Report Title</span></span>  
 <span data-ttu-id="c3403-272">Ein Berichtstitel wird oben im Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-272">A report title appears at the top of the report.</span></span> <span data-ttu-id="c3403-273">Sie können den Berichtstitel in eine Berichtskopfzeile einfügen oder, wenn der Bericht keine Kopfzeile enthält, in einem Textfeld am oberen Rand des Berichtshauptteils.</span><span class="sxs-lookup"><span data-stu-id="c3403-273">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="c3403-274">In diesem Lernprogramm verwenden Sie das Textfeld, das automatisch am oberen Rand des Berichtshauptteils platziert wird.</span><span class="sxs-lookup"><span data-stu-id="c3403-274">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="c3403-275">Die Darstellung des Texts kann weiter verbessert werden, indem andere Schriftschnitte, Größen und Farben für Ausdrücke und einzelne Zeichen des Texts angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3403-275">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="c3403-276">Weitere Informationen finden Sie unter [Formatieren von Text in einem Textfeld (Berichts-Generator und SSRS)](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c3403-276">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c3403-277">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="c3403-277">To add a report title</span></span>  
  
1.  <span data-ttu-id="c3403-278">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="c3403-278">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="c3403-279">Geben Sie **Product Sales**ein, und klicken Sie anschließend außerhalb des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="c3403-279">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="c3403-280">Klicken Sie mit der rechten Maustaste auf das Textfeld, das **Product Sales** enthält, und klicken Sie auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c3403-280">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="c3403-281">Klicken Sie im Dialogfeld **Textfeldeigenschaften** auf **Schriftart**.</span><span class="sxs-lookup"><span data-stu-id="c3403-281">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="c3403-282">Wählen Sie in der Liste **Schriftgrad** den Eintrag **18pt**aus.</span><span class="sxs-lookup"><span data-stu-id="c3403-282">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="c3403-283">Wählen Sie in der Liste **Farbe** die Option **Maroon**aus.</span><span class="sxs-lookup"><span data-stu-id="c3403-283">In the **Color** list, select **Maroon**.</span></span>  
  
7.  <span data-ttu-id="c3403-284">Wählen Sie **Fett**aus.</span><span class="sxs-lookup"><span data-stu-id="c3403-284">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="c3403-285">9. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="c3403-285">9. Save the Report</span></span>  
 <span data-ttu-id="c3403-286">Speichern Sie den Bericht auf einem Berichtsserver oder auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="c3403-286">Save the report to a report server or your computer.</span></span> <span data-ttu-id="c3403-287">Wenn Sie den Bericht nicht auf dem Berichtsserver speichern, ist eine Reihe von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen nicht verfügbar, z. B. Berichtsteile und Unterberichte.</span><span class="sxs-lookup"><span data-stu-id="c3403-287">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="c3403-288">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="c3403-288">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="c3403-289">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-289">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c3403-290">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="c3403-290">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="c3403-291">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="c3403-291">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="c3403-292">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-292">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="c3403-293">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="c3403-293">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="c3403-294">Ersetzen Sie im Feld **Name**den Standardnamen durch **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="c3403-294">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="c3403-295">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c3403-295">Click **Save**.</span></span>  
  
 <span data-ttu-id="c3403-296">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c3403-296">The report is saved to the report server.</span></span> <span data-ttu-id="c3403-297">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3403-297">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="c3403-298">So speichern Sie den Bericht auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="c3403-298">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="c3403-299">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="c3403-299">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c3403-300">Klicken Sie auf **Desktop**, **Eigene Dokumente**oder **Computer**, und navigieren Sie zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="c3403-300">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="c3403-301">Ersetzen Sie im Feld **Name**den Standardnamen durch **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="c3403-301">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="c3403-302">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c3403-302">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c3403-303">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c3403-303">Next Steps</span></span>  
 <span data-ttu-id="c3403-304">Hiermit ist das Lernprogramm zum Erstellen eines Tabellenberichts mit Sparklinediagrammen abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c3403-304">This concludes the tutorial for creating a table report with sparkline charts.</span></span> <span data-ttu-id="c3403-305">Weitere Informationen zu Sparklines finden Sie unter [Sparklines und Datenbalken &#40;Berichts-Generator und SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c3403-305">For more information about sparklines, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3403-306">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3403-306">See Also</span></span>  
 <span data-ttu-id="c3403-307">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="c3403-307">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="c3403-308">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c3403-308">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
