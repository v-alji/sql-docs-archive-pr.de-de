---
title: 'Tutorial: Erstellen eines Matrixberichts (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9ee19c2e-2a8c-4bb0-9274-04a5812c2e96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3df32098d9e6400931ba2a88b2ffd22d6e015a62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722442"
---
# <a name="tutorial-creating-a-matrix-report-report-builder"></a><span data-ttu-id="a9eab-102">Lernprogramm: Erstellen eines Matrixberichts (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="a9eab-102">Tutorial: Creating a Matrix Report (Report Builder)</span></span>
  <span data-ttu-id="a9eab-103">In diesem Lernprogramm erfahren Sie, wie Sie auf Grundlage von Beispielumsatzdaten einen einfachen Matrixbericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-103">This tutorial teaches you how to create a basic matrix report based on sample sales data.</span></span> <span data-ttu-id="a9eab-104">Die Matrix besitzt geschachtelte Zeilen- und Spaltengruppen und eine angrenzende Spaltengruppe.</span><span class="sxs-lookup"><span data-stu-id="a9eab-104">The matrix has nested row and column groups and an adjacent column group.</span></span> <span data-ttu-id="a9eab-105">Sie erhalten auch Informationen zum Formatieren von Spalten und zum Drehen von Text.</span><span class="sxs-lookup"><span data-stu-id="a9eab-105">You will also learn how to format columns and rotate text.</span></span> <span data-ttu-id="a9eab-106">Die folgende Abbildung zeigt einen Bericht, der mit dem Bericht vergleichbar ist, den Sie erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-106">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="a9eab-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="a9eab-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span></span>  
  
 <span data-ttu-id="a9eab-108">Eine erweiterte Version des Berichts, den Sie in diesem Tutorial erstellen, ist als Beispiel [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Berichts-Generator Bericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9eab-108">An enhanced version of the report you will create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="a9eab-109">Weitere Informationen zum Herunterladen dieses Beispiel Berichts und anderer Informationen finden Sie unter [Berichts-Generator-Beispiel Berichte](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="a9eab-109">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="a9eab-110">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="a9eab-110">What You Will Learn</span></span>  
 <span data-ttu-id="a9eab-111">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a9eab-111">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="a9eab-112">Erstellen eines Matrixberichts und eines Datasets mit dem Assistenten für neue Tabellen oder Matrix</span><span class="sxs-lookup"><span data-stu-id="a9eab-112">Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>](#CreateMatrix)  
  
2.  [<span data-ttu-id="a9eab-113">Organisieren von Daten und Auswählen des Layouts und Formats mit dem Assistenten für neue Tabellen oder Matrix</span><span class="sxs-lookup"><span data-stu-id="a9eab-113">Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>](#Groups)  
  
3.  [<span data-ttu-id="a9eab-114">Formatieren von Daten</span><span class="sxs-lookup"><span data-stu-id="a9eab-114">Format Data</span></span>](#FormatData)  
  
4.  [<span data-ttu-id="a9eab-115">Hinzufügen einer angrenzenden Spaltengruppe</span><span class="sxs-lookup"><span data-stu-id="a9eab-115">Add Adjacent Column Group</span></span>](#AdjacentGroup)  
  
5.  [<span data-ttu-id="a9eab-116">Ändern der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="a9eab-116">Change Column Widths</span></span>](#Width)  
  
6.  [<span data-ttu-id="a9eab-117">Verbinden von Matrixzellen</span><span class="sxs-lookup"><span data-stu-id="a9eab-117">Merge Matrix Cells</span></span>](#MergeCells)  
  
7.  [<span data-ttu-id="a9eab-118">Hinzufügen eines Berichtskopfs und -titels</span><span class="sxs-lookup"><span data-stu-id="a9eab-118">Add a Report Header and Report Title</span></span>](#HeaderTitle)  
  
8.  [<span data-ttu-id="a9eab-119">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="a9eab-119">Save the Report</span></span>](#Save)  
  
### <a name="other-optional-step"></a><span data-ttu-id="a9eab-120">Weiterer optionaler Schritt</span><span class="sxs-lookup"><span data-stu-id="a9eab-120">Other Optional Step</span></span>  
  
1.  [<span data-ttu-id="a9eab-121">Drehen des Textfelds um 270 Grad</span><span class="sxs-lookup"><span data-stu-id="a9eab-121">Rotate Text Box 270 Degrees</span></span>](#RotateTextBox)  
  
 <span data-ttu-id="a9eab-122">Ungefähre Dauer dieses Lernprogramms: 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="a9eab-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9eab-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a9eab-123">Requirements</span></span>  
 <span data-ttu-id="a9eab-124">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="a9eab-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-new-table-or-matrix-wizard"></a><a name="CreateMatrix"></a><span data-ttu-id="a9eab-125">1. Erstellen eines Matrix Berichts und eines Datasets mit dem Assistenten für neue Tabellen oder Matrix</span><span class="sxs-lookup"><span data-stu-id="a9eab-125">1. Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="a9eab-126">Wählen Sie im Dialogfeld " **Getting Started** " in Berichts-Generator eine freigegebene Datenquelle aus, erstellen Sie ein eingebettetes DataSet, und zeigen Sie die Daten dann in einer Matrix an.</span><span class="sxs-lookup"><span data-stu-id="a9eab-126">From the **Getting Started** dialog box in Report Builder, choose a shared data source, create an embedded dataset, and then display the data in a matrix.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9eab-127">In diesem Lernprogramm enthält die Abfrage bereits die Datenwerte, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a9eab-127">In this tutorial, the query already contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="a9eab-128">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="a9eab-128">This makes the query quite long.</span></span> <span data-ttu-id="a9eab-129">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9eab-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="a9eab-130">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="a9eab-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix"></a><span data-ttu-id="a9eab-131">So erstellen Sie eine neue Matrix</span><span class="sxs-lookup"><span data-stu-id="a9eab-131">To create a new matrix</span></span>  
  
1.  <span data-ttu-id="a9eab-132">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9eab-133">Das Dialogfeld **Erste Schritte** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-133">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="a9eab-134">Wenn dies nicht der Fall ist, klicken Sie auf der Schaltfläche Berichts-Generator auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-134">If it doesn't, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="a9eab-135">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a9eab-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="a9eab-136">Klicken Sie im rechten Bereich auf **Tabellen- oder Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="a9eab-137">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-137">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="a9eab-138">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a9eab-139">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichts Server, und wählen Sie dann eine Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="a9eab-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server, and then select a data source.</span></span> <span data-ttu-id="a9eab-140">Falls keine Datenquelle verfügbar ist oder Sie über keinen Zugriff auf einen Berichtsserver verfügen, können Sie stattdessen eine eingebettete Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-140">If no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="a9eab-141">Weitere Informationen zum Erstellen einer eingebetteten Datenquelle finden Sie unter [Tutorial: Erstellen eines einfachen Tabellen Berichts &#40;Berichts-Generator&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="a9eab-141">For more information about creating an embedded data source, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="a9eab-142">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="a9eab-143">Klicken Sie auf der Seite **Abfrage entwerfen** auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="a9eab-144">Kopieren Sie die folgende Abfrage, und fügen Sie sie in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="a9eab-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity  
    ```  
  
10. <span data-ttu-id="a9eab-145">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-and-choose-layout-and-style-from-the-new-table-or-matrix-wizard"></a><a name="Groups"></a><span data-ttu-id="a9eab-146">2. Organisieren von Daten und Auswählen von Layout und Stil im Assistenten für neue Tabellen oder Matrix</span><span class="sxs-lookup"><span data-stu-id="a9eab-146">2. Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="a9eab-147">Stellen Sie mithilfe des Assistenten einen Startentwurf für die Anzeige von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="a9eab-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="a9eab-148">Im Vorschaufenster des Assistenten können Sie das Ergebnis der Datengruppierung visualisieren, bevor Sie den Matrixentwurf abschließen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-and-choose-a-layout-and-style"></a><span data-ttu-id="a9eab-149">So organisieren Sie Daten in Gruppen und wählen ein Layout und ein Format aus</span><span class="sxs-lookup"><span data-stu-id="a9eab-149">To organize data into groups and choose a layout and style</span></span>  
  
1.  <span data-ttu-id="a9eab-150">Ziehen Sie auf der Seite **Felder anordnen** „Territory“ von **Verfügbare Felder** nach **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-150">On the **Arrange fields** page, drag Territory from **Available fields** to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="a9eab-151">Ziehen Sie „SalesDate“ in **Zeilengruppen** und platzieren Sie das Feld unter „Territory“.</span><span class="sxs-lookup"><span data-stu-id="a9eab-151">Drag SalesDate to **Row groups** and place it below Territory.</span></span>  
  
     <span data-ttu-id="a9eab-152">Die Gruppenhierarchie wird durch die Reihenfolge, in der Felder in **Zeilengruppen** aufgeführt sind, definiert.</span><span class="sxs-lookup"><span data-stu-id="a9eab-152">The order in which fields are listed in **Row groups** defines the group hierarchy.</span></span> <span data-ttu-id="a9eab-153">Durch die Schritte 1 und 2 werden die Werte der Felder zuerst nach Gebiet und dann nach Verkaufsdatum angeordnet.</span><span class="sxs-lookup"><span data-stu-id="a9eab-153">Steps 1 and 2 organize the values of the fields first by territory, and then by sales date.</span></span>  
  
3.  <span data-ttu-id="a9eab-154">Ziehen Sie die „Subcategory“ in **Spaltengruppen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-154">Drag Subcategory to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="a9eab-155">Ziehen Sie Product in **Spalten Gruppen,** und platzieren Sie dann die Unterkategorie.</span><span class="sxs-lookup"><span data-stu-id="a9eab-155">Drag Product to **Column groups,** and then place below Subcategory.</span></span>  
  
     <span data-ttu-id="a9eab-156">Die Reihenfolge, in der Felder in **Spalten Gruppen** aufgeführt sind, definiert die Gruppen Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="a9eab-156">The order in which fields are listed in **Column groups** defines the group hierarchy.</span></span>  
  
     <span data-ttu-id="a9eab-157">Durch die Schritte 3 und 4 werden die Werte für die Felder zuerst nach Unterkategorie und anschließend nach Produkt geordnet.</span><span class="sxs-lookup"><span data-stu-id="a9eab-157">Steps 3 and 4 organize the values for the fields first by subcategory, and then by product.</span></span>  
  
5.  <span data-ttu-id="a9eab-158">Ziehen Sie „Sales“ in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-158">Drag Sales to **Values**.</span></span>  
  
     <span data-ttu-id="a9eab-159">Sales wird mit der Sum-Funktion zusammengefasst, der Standardfunktion zum Summieren numerischer Felder.</span><span class="sxs-lookup"><span data-stu-id="a9eab-159">Sales is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
6.  <span data-ttu-id="a9eab-160">Ziehen Sie „Quantity“ in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-160">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="a9eab-161">Quantity wird mit der Sum-Funktion zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="a9eab-161">Quantity is summarized with the Sum function.</span></span>  
  
     <span data-ttu-id="a9eab-162">In Schritt 5 und 6 werden die Daten angegeben, die in den Matrixdatenzellen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-162">Steps 5 and 6 specify the data to display in the matrix data cells.</span></span>  
  
7.  <span data-ttu-id="a9eab-163">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-163">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="a9eab-164">Vergewissern Sie sich auf der Seite „Layout auswählen“, dass unter **Optionen**die Option **Teil- und Gesamtergebnisse anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a9eab-164">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
9. <span data-ttu-id="a9eab-165">Überprüfen Sie, ob **Als Block, Teilergebnis unterhalb** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a9eab-165">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
10. <span data-ttu-id="a9eab-166">Überprüfen Sie, ob die Option **Gruppen erweitern/reduzieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a9eab-166">Verify the option **Expand/collapse groups** is selected.</span></span>  
  
11. <span data-ttu-id="a9eab-167">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-167">Click **Next**.</span></span>  
  
12. <span data-ttu-id="a9eab-168">Wählen Sie auf der Seite Format auswählen im Bereich Formate die Option **Schiefer**aus.</span><span class="sxs-lookup"><span data-stu-id="a9eab-168">On the Choose a Style page, in the Styles pane, select **Slate**.</span></span>  
  
13. <span data-ttu-id="a9eab-169">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-169">Click **Finish**.</span></span>  
  
     <span data-ttu-id="a9eab-170">Die Matrix wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-170">The matrix is added to the design surface.</span></span> <span data-ttu-id="a9eab-171">Im Bereich Zeilengruppen werden zwei Zeilengruppen angezeigt: Territory und SalesDate.</span><span class="sxs-lookup"><span data-stu-id="a9eab-171">The Row Groups pane shows two row groups: Territory and SalesDate.</span></span> <span data-ttu-id="a9eab-172">Im Bereich Spaltengruppen werden zwei Spaltengruppen angezeigt: Subcategory und Product.</span><span class="sxs-lookup"><span data-stu-id="a9eab-172">The Column Groups pane shows two column groups: Subcategory and Product.</span></span> <span data-ttu-id="a9eab-173">Detaildaten sind alle Daten, die von der Datasetabfrage abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-173">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
14. <span data-ttu-id="a9eab-174">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-174">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="a9eab-175">Für jedes Produkt, das an einem bestimmten Datum verkauft wird, werden in der Matrix die Unterkategorie, zu der das Produkt gehört, und das Verkaufsgebiet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-175">For each product that is sold on a specific date, the matrix shows the subcategory to which the product belongs and the territory of the sales.</span></span>  
  
##  <a name="3-format-data"></a><a name="FormatData"></a><span data-ttu-id="a9eab-176">3. Formatieren von Daten</span><span class="sxs-lookup"><span data-stu-id="a9eab-176">3. Format Data</span></span>  
 <span data-ttu-id="a9eab-177">Standardmäßig wird in den Zusammenfassungsdaten für das Feld Sales eine allgemeine Zahl angezeigt, wohingegen im Feld SalesDate sowohl Datums- als auch Uhrzeitangaben angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-177">By default, the summary data for the Sales field displays a general number and the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="a9eab-178">Formatieren Sie das Feld Sales, um die Zahl als Währung anzuzeigen und das Feld SalesDate, um nur das Datum anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-178">Format the Sales field to display the number as currency and the SalesDate field to display only the date.</span></span> <span data-ttu-id="a9eab-179">Ändern Sie die Einstellung der Option **Platzhalterformate** , um formatierte Textfelder und Platzhaltertext als Beispielwerte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-179">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-fields"></a><span data-ttu-id="a9eab-180">So formatieren Sie Felder</span><span class="sxs-lookup"><span data-stu-id="a9eab-180">To format fields</span></span>  
  
1.  <span data-ttu-id="a9eab-181">Klicken Sie auf **Entwurf** , um zur Entwurfs Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="a9eab-181">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="a9eab-182">Drücken Sie die STRG-TASTE, und wählen Sie dann die neun Zellen aus, die `[Sum(Sales)]`enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9eab-182">Press the Ctrl key, and then select the nine cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="a9eab-183">Klicken Sie auf der Registerkarte **Stamm** in der Gruppe **Zahl** auf **Währung**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-183">On the **Home** tab, in the **Number** group, click **Currency**.</span></span> <span data-ttu-id="a9eab-184">Die Anzeige der Zellen wird geändert, und die formatierte Währung erscheint.</span><span class="sxs-lookup"><span data-stu-id="a9eab-184">The cells changeto show the formatted currency.</span></span>  
  
     <span data-ttu-id="a9eab-185">Wenn Sie das Gebietsschema „Deutsch (Deutschland)“ verwenden, lautet der Standardbeispieltext [**12,345.00€**].</span><span class="sxs-lookup"><span data-stu-id="a9eab-185">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="a9eab-186">Wenn kein Beispiel Währungswert angezeigt wird, klicken Sie in der Gruppe **Zahlen** auf **Platzhalter** Formate und dann auf **Beispiel Werte**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-186">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="a9eab-187">Klicken Sie auf die Zelle, die `[SalesDate]`enthält.</span><span class="sxs-lookup"><span data-stu-id="a9eab-187">Click the cell that contains `[SalesDate]`.</span></span>  
  
5.  <span data-ttu-id="a9eab-188">Wählen Sie in der Gruppe **Zahl** in der Dropdown Liste **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="a9eab-188">In the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="a9eab-189">In der Zelle wird das Beispieldatum **[31.01.2000]** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-189">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="a9eab-190">Falls kein Beispieldatum angezeigt wird, klicken Sie in der Gruppe **Zahlen** auf **Platzhalterformate** und anschließend auf **Beispielwerte**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-190">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
6.  <span data-ttu-id="a9eab-191">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-191">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="a9eab-192">In den Datumswerten werden nur Datumsangaben angezeigt, und die Umsatzwerte werden als Währung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-192">The date values display only dates and the sales values display as currency.</span></span>  
  
##  <a name="4-add-adjacent-column-group"></a><a name="AdjacentGroup"></a><span data-ttu-id="a9eab-193">4. Hinzufügen einer angrenzenden Spalten Gruppe</span><span class="sxs-lookup"><span data-stu-id="a9eab-193">4. Add Adjacent Column Group</span></span>  
 <span data-ttu-id="a9eab-194">Sie können Zeilen- und Spaltengruppen in Beziehungen über- und untergeordneter Objekte oder angrenzend in Beziehungen gleichgeordneter Objekte schachteln.</span><span class="sxs-lookup"><span data-stu-id="a9eab-194">You can nest row and column groups in parent child relationships or adjacent in sibling relationships.</span></span>  
  
 <span data-ttu-id="a9eab-195">Fügen Sie eine Spaltengruppe hinzu, die an die Spaltengruppe Subcategory grenzt, kopieren Sie Zellen, um die neue Spaltengruppe aufzufüllen, und verwenden Sie anschließend einen Ausdruck, um den Wert der Spaltengruppenkopfzeile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-195">Add a column group that is adjacent to the Subcategory column group, copy cells to populate the new column group, and then use an expression to create the value of the column group header.</span></span>  
  
#### <a name="to-add-an-adjacent-column-group"></a><span data-ttu-id="a9eab-196">So fügen Sie eine angrenzende Spaltengruppe hinzu</span><span class="sxs-lookup"><span data-stu-id="a9eab-196">To add an adjacent column group</span></span>  
  
1.  <span data-ttu-id="a9eab-197">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a9eab-197">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="a9eab-198">Klicken Sie mit der rechten Maustaste auf die Zelle, die `[Subcategory]`enthält, zeigen Sie auf **Gruppe hinzufügen**und klicken Sie anschließend auf **Angrenzend rechts**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-198">Right-click the cell that contains `[Subcategory]`, point to **Add Group**, and then click **Adjacent Right**.</span></span>  
  
     <span data-ttu-id="a9eab-199">Das Dialogfeld **Tablix-Gruppe** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9eab-199">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a9eab-200">Wählen Sie in der Liste **Gruppieren nach** die Option SalesDate aus und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-200">In the **Group By** list, select SalesDate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a9eab-201">Links neben der Spaltengruppe Subcategory wird eine neue Spaltengruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-201">A new column group is added to the left of the Subcategory column group.</span></span>  
  
4.  <span data-ttu-id="a9eab-202">Klicken Sie mit der rechten Maustaste auf die Zelle in der neuen Spaltengruppe, die `[SalesDate],` enthält, und klicken Sie anschließend auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-202">Right-click the cell in the new column group that contains `[SalesDate],` and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="a9eab-203">Kopieren Sie den folgenden Ausdruck in das Feld Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a9eab-203">Copy the following expression to expression box.</span></span>  
  
    ```  
    =WeekdayName(DatePart("w",Fields!SalesDate.Value))  
    ```  
  
     <span data-ttu-id="a9eab-204">Mit diesem Ausdruck wird der Name des Wochentags aus dem Verkaufsdatum extrahiert.</span><span class="sxs-lookup"><span data-stu-id="a9eab-204">This expression extracts the weekday name from the sales date.</span></span> <span data-ttu-id="a9eab-205">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9eab-205">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="a9eab-206">Klicken Sie mit der rechten Maustaste auf die Zelle „Gesamt“ in der Spaltengruppe „Subcategory“, und klicken Sie anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-206">Right-click the cell in the Subcategory column group that contains Total, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="a9eab-207">Klicken Sie mit der rechten Maustaste auf die Zelle, die sich unmittelbar unter der Zelle mit dem Ausdruck befindet, den Sie in Schritt 5 erstellt haben, und klicken Sie anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-207">Right-click the cell immediately below the cell that contains the expression you created in step 5 and click **Paste**.</span></span>  
  
8.  <span data-ttu-id="a9eab-208">Drücken Sie die STRG-TASTE.</span><span class="sxs-lookup"><span data-stu-id="a9eab-208">Press the Ctrl key.</span></span>  
  
9. <span data-ttu-id="a9eab-209">Markieren Sie in der Gruppe „Subcategory“ die Spaltenüberschrift „Sales“ und die darunter liegenden drei Zellen und klicken Sie mit der rechten Maustaste darauf. Klicken Sie anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-209">In the Subcategory group, click the Sales column header and the three cells below it, right-click, and then click **Copy**.</span></span>  
  
10. <span data-ttu-id="a9eab-210">Fügen Sie die vier Zellen in die vier leeren Zellen in der neuen Spaltengruppe ein.</span><span class="sxs-lookup"><span data-stu-id="a9eab-210">Paste the four cells into the four empty cells in the new column group.</span></span>  
  
11. <span data-ttu-id="a9eab-211">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-211">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="a9eab-212">Der Bericht enthält Spalten mit der Bezeichnung "Montag" und "Dienstag".</span><span class="sxs-lookup"><span data-stu-id="a9eab-212">The report includes columns named Monday and Tuesday.</span></span> <span data-ttu-id="a9eab-213">Das Dataset enthält nur Daten für diese zwei Tage.</span><span class="sxs-lookup"><span data-stu-id="a9eab-213">The dataset contains only data for these two days.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9eab-214">Wenn die Daten andere Tage einschließen würden, würde der Bericht auch Spalten für diese Tage enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9eab-214">If the data included other days, the report would include columns for them as well.</span></span> <span data-ttu-id="a9eab-215">Jede Spalte enthält die Spaltenüberschrift, `Sales` und die Gesamtumsätze nach Gebiet.</span><span class="sxs-lookup"><span data-stu-id="a9eab-215">Each column has the column header, `Sales`, and sales totals by territory.</span></span>  
  
##  <a name="5-change-column-widths"></a><a name="Width"></a><span data-ttu-id="a9eab-216">5. Ändern der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="a9eab-216">5. Change Column Widths</span></span>  
 <span data-ttu-id="a9eab-217">Ein Bericht, der eine Matrix enthält, wird bei der Ausführung normalerweise horizontal und vertikal erweitert.</span><span class="sxs-lookup"><span data-stu-id="a9eab-217">A report that includes a matrix typically expands horizontally as well as vertically when it runs.</span></span> <span data-ttu-id="a9eab-218">Die Steuerung der horizontalen Erweiterung ist besonders wichtig, wenn Sie beabsichtigen, den Bericht in Formate wie z. B. Microsoft Word oder Adobe PDF zu exportieren, die für gedruckte Berichte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-218">Controlling horizontal expansion is particularly important if you plan to export the report to formats such as Microsoft Word or Adobe PDF that are used for printed reports.</span></span> <span data-ttu-id="a9eab-219">Wenn sich der Bericht horizontal über mehrere Seiten erstreckt, ist der gedruckte Bericht schwer verständlich.</span><span class="sxs-lookup"><span data-stu-id="a9eab-219">If the report expands horizontally across multiple pages, the printed report is difficult to understand.</span></span> <span data-ttu-id="a9eab-220">Um die horizontale Erweiterung zu minimieren, können Sie die Breite der Spalten so anpassen, dass die Daten darin ohne Zeilenumbruch angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-220">To minimize horizontal expansion, you can resize columns to be only the width necessary to display the data without wrapping.</span></span> <span data-ttu-id="a9eab-221">Sie können auch Spalten umbenennen, damit ihre Titel der Breite entsprechen, die zum Anzeigen der Daten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a9eab-221">You can also rename columns so that their titles fit the width needed to display the data.</span></span>  
  
#### <a name="to-rename-and-resize-the-columns"></a><span data-ttu-id="a9eab-222">So benennen Sie Spalten um und ändern deren Größe</span><span class="sxs-lookup"><span data-stu-id="a9eab-222">To rename and resize the columns</span></span>  
  
1.  <span data-ttu-id="a9eab-223">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a9eab-223">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="a9eab-224">Wählen Sie den Text in der Spalte „Quantity“ ganz links aus, und geben Sie anschließend **QTY**ein.</span><span class="sxs-lookup"><span data-stu-id="a9eab-224">Select the text in the furthest Quantity column to the left, and then type **QTY**.</span></span>  
  
     <span data-ttu-id="a9eab-225">Der Spaltentitel lautet nun QTY.</span><span class="sxs-lookup"><span data-stu-id="a9eab-225">The column title is now QTY.</span></span>  
  
3.  <span data-ttu-id="a9eab-226">Wiederholen Sie Schritt 2 für die anderen Spalten mit dem Namen Quantity.</span><span class="sxs-lookup"><span data-stu-id="a9eab-226">Repeat step 2 for the other columns named Quantity.</span></span> <span data-ttu-id="a9eab-227">Es gibt zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="a9eab-227">There are two of them.</span></span>  
  
4.  <span data-ttu-id="a9eab-228">Klicken Sie auf die Matrix, damit die Spalten- und Zeilenhandles oberhalb und neben der Matrix angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-228">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
     <span data-ttu-id="a9eab-229">Die grauen Balken oberhalb und neben der Tabelle stellen die Spalten- und Zeilenhandles dar.</span><span class="sxs-lookup"><span data-stu-id="a9eab-229">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
5.  <span data-ttu-id="a9eab-230">Wenn Sie die Größe der QTY-Spalte ganz links ändern möchten, zeigen Sie auf die Zeile zwischen den Spaltenhandles, damit die Anzeige des Cursors in einen Doppelpfeil geändert wird.</span><span class="sxs-lookup"><span data-stu-id="a9eab-230">To resize the furthest QTY column to the left, point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="a9eab-231">Ziehen Sie die Spalte nach links bis zu einer Breite von ca. 1,3 cm.</span><span class="sxs-lookup"><span data-stu-id="a9eab-231">Drag the column towards the left until it is 1/2 inch wide.</span></span>  
  
     <span data-ttu-id="a9eab-232">Eine Spaltenbreite von ca. 1,3 cm ist für das Anzeigen der Menge ausreichend.</span><span class="sxs-lookup"><span data-stu-id="a9eab-232">A column width of 1/2 inch is adequate to display the quantity.</span></span>  
  
6.  <span data-ttu-id="a9eab-233">Wiederholen Sie Schritt 5 für die anderen Spalten mit dem Namen QTY.</span><span class="sxs-lookup"><span data-stu-id="a9eab-233">Repeat step 5 for the other columns named QTY.</span></span>  
  
7.  <span data-ttu-id="a9eab-234">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-234">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="a9eab-235">Die Spalten im Bericht, der Mengen enthält, tragen nun die Bezeichnung "QTY", und die Spalten sind schmäler.</span><span class="sxs-lookup"><span data-stu-id="a9eab-235">The columns in the report that contains quantities are now named QTY and the columns are narrower.</span></span>  
  
##  <a name="6-merge-matrix-cells"></a><a name="MergeCells"></a><span data-ttu-id="a9eab-236">6. Zusammenführen von Matrix Zellen</span><span class="sxs-lookup"><span data-stu-id="a9eab-236">6. Merge Matrix Cells</span></span>  
 <span data-ttu-id="a9eab-237">Der Eckenbereich befindet sich oben links in der Matrix.</span><span class="sxs-lookup"><span data-stu-id="a9eab-237">The corner area is in the upper left corner of the matrix.</span></span> <span data-ttu-id="a9eab-238">Abhängig von der Anzahl der Zeilen- und Spaltengruppen in der Matrix unterscheidet sich die Anzahl der Zellen im Eckenbereich.</span><span class="sxs-lookup"><span data-stu-id="a9eab-238">Depending on the number of row and column groups in the matrix, the number of cells in the corner area varies.</span></span> <span data-ttu-id="a9eab-239">Die in diesem Lernprogramm erstellte Matrix enthält vier Zellen in ihrem Eckenbereich.</span><span class="sxs-lookup"><span data-stu-id="a9eab-239">The matrix, built in this tutorial, has four cells in its corner area.</span></span> <span data-ttu-id="a9eab-240">Die Zellen werden in zwei Zeilen und zwei Spalten angeordnet und spiegeln die Tiefe der Zeilen- und Spaltengruppenhierarchien wider.</span><span class="sxs-lookup"><span data-stu-id="a9eab-240">The cells are arranged in two rows and two columns, reflecting the depth of row and column group hierarchies.</span></span> <span data-ttu-id="a9eab-241">Die vier Zellen werden nicht in diesem Bericht verwendet und zu einer Zelle verbunden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-241">The four cells are not used in this report and you will merge them into one.</span></span>  
  
#### <a name="to-merge-matrix-cells"></a><span data-ttu-id="a9eab-242">So verbinden Sie Matrixzellen</span><span class="sxs-lookup"><span data-stu-id="a9eab-242">To merge matrix cells</span></span>  
  
1.  <span data-ttu-id="a9eab-243">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a9eab-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="a9eab-244">Klicken Sie auf die Matrix, damit die Spalten- und Zeilenhandles oberhalb und neben der Matrix angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-244">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
3.  <span data-ttu-id="a9eab-245">Drücken Sie die STRG-TASTE, und wählen Sie dann die vier Eckenzellen aus.</span><span class="sxs-lookup"><span data-stu-id="a9eab-245">Press the Ctrl key, and then select the four corner cells.</span></span>  
  
4.  <span data-ttu-id="a9eab-246">Klicken Sie mit der rechten Maustaste auf die Zellen und dann auf **Zellen zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-246">Right-click the cells and then click **Merge Cells**.</span></span>  
  
5.  <span data-ttu-id="a9eab-247">Klicken Sie mit der rechten Maustaste auf die Eckzelle, und klicken Sie dann auf **Text Feldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-247">Right-click the corner cell, and then click **Text Box Properties**.</span></span>  
  
6.  <span data-ttu-id="a9eab-248">Klicken Sie auf die Registerkarte **Ausfüllen** .</span><span class="sxs-lookup"><span data-stu-id="a9eab-248">Click the **Fill** tab.</span></span>  
  
7.  <span data-ttu-id="a9eab-249">Klicken Sie auf die Schaltfläche (***FX***) für **Füllfarbe**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-249">Click the (***fx***) button for **Fill color**.</span></span>  
  
8.  <span data-ttu-id="a9eab-250">Kopieren Sie den folgenden Ausdruck, und fügen Sie ihn im Ausdrucksfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a9eab-250">Copy and paste the following expression in the expression box.</span></span>  
  
    ```  
    #96a4b2  
    ```  
  
     <span data-ttu-id="a9eab-251">Dies ist der RGB-Hexadezimalwert für eine grau-blaue Farbe, die im Schieferformat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9eab-251">This is the RGB hex value for a gray blue color used in the Slate style.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="a9eab-252">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-252">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="a9eab-253">Die Matrix für die oberen Ecken ist eine einzelne Zelle und besitzt die gleiche Farbe wie die Zeilen- und Spaltengruppenzellen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-253">The upper corner matrix is a single cell and has the same color as the row group and column group cells.</span></span>  
  
##  <a name="7-add-a-report-header-and-report-title"></a><a name="HeaderTitle"></a><span data-ttu-id="a9eab-254">7. Hinzufügen einer Berichts Kopfzeile und eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="a9eab-254">7. Add a Report Header and Report Title</span></span>  
 <span data-ttu-id="a9eab-255">Ein Berichtstitel wird oben im Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-255">A report title appears at the top of the report.</span></span> <span data-ttu-id="a9eab-256">Sie können den Berichtstitel in eine Berichtskopfzeile einfügen oder, wenn der Bericht keine Kopfzeile enthält, in einem Textfeld am oberen Rand des Berichtshauptteils.</span><span class="sxs-lookup"><span data-stu-id="a9eab-256">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="a9eab-257">In diesem Lernprogramm entfernen Sie das Textfeld am Anfang des Berichts und fügen der Kopfzeile einen Titel hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9eab-257">In this tutorial, you will remove the text box at the top of the report and add a title to the header.</span></span>  
  
#### <a name="to-add-a-report-header-and-report-title"></a><span data-ttu-id="a9eab-258">So fügen Sie eine Berichtskopfzeile und einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="a9eab-258">To add a report header and report title</span></span>  
  
1.  <span data-ttu-id="a9eab-259">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a9eab-259">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="a9eab-260">Klicken Sie oben im Hauptteil des Berichts auf das Textfeld, das **zum Hinzufügen eines Titels klicken**enthält, und drücken Sie dann die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="a9eab-260">Click the text box at the top of the report body that contains **Click to add title**, and then press the Delete key.</span></span>  
  
3.  <span data-ttu-id="a9eab-261">Klicken Sie auf der Registerkarte **Einfügen** des Menübands auf **Kopfzeile** und dann auf **Kopfzeile hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-261">On the **Insert** tab of the ribbon, click **Header** and then click **Add Header**.</span></span>  
  
     <span data-ttu-id="a9eab-262">Am Anfang des Berichtstexts wird eine Kopfzeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-262">A header is added to the top of the report body.</span></span>  
  
4.  <span data-ttu-id="a9eab-263">Klicken Sie auf der Registerkarte **Einfügen** auf **Textfeld**und ziehen Sie anschließend ein Textfeld in den Berichtskopf.</span><span class="sxs-lookup"><span data-stu-id="a9eab-263">On the **Insert** tab, click **Text Box**, and then drag a text box inside the report header.</span></span> <span data-ttu-id="a9eab-264">Erweitern Sie das Textfeld auf eine Länge von etwa 15 cm und eine Höhe von etwa 2 cm, und platzieren Sie es links neben der Berichtskopfzeile.</span><span class="sxs-lookup"><span data-stu-id="a9eab-264">Make the text box about 6 inches long and 3/4 inch tall and place it on the left side of the report header.</span></span>  
  
5.  <span data-ttu-id="a9eab-265">Geben Sie im Textfeld **Umsatz nach Territory, Subcategory und Tag**ein.</span><span class="sxs-lookup"><span data-stu-id="a9eab-265">In the text box, type **Sales by Territory, Subcategory, and Day**.</span></span>  
  
6.  <span data-ttu-id="a9eab-266">Wählen Sie den eingegebenen Text aus, klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-266">Select the text you typed, right-click, and then click **Text Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9eab-267">Eine gleichzeitige Formatierung von Zeichen ist nur möglich, wenn diese zusammenhängend sind.</span><span class="sxs-lookup"><span data-stu-id="a9eab-267">To format characters at the same time, they must be contiguous.</span></span>  
  
7.  <span data-ttu-id="a9eab-268">Klicken Sie im Dialogfeld **Text Eigenschaften** auf **Schriftart**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-268">In the **Text Properties** dialog box, click **Font**.</span></span>  
  
8.  <span data-ttu-id="a9eab-269">Wählen Sie in der Liste **Schriftart die Schriftart** **Times New Roman**aus. Wählen Sie Untergröße die Option **24 PT**, in **Farbe** die Option **Maroon**aus, **und wählen Sie** im **Format** **kursiv**aus.</span><span class="sxs-lookup"><span data-stu-id="a9eab-269">In the **Font** list, select **Times New Roman**; in **Size** select **24 pt**, in **Color** select **Maroon**, and in **Style** select **Italic**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="a9eab-270">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-270">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="a9eab-271">Der Bericht enthält einen Berichtstitel in der Kopfzeile des Berichts.</span><span class="sxs-lookup"><span data-stu-id="a9eab-271">The report includes a report title in the report header.</span></span>  
  
##  <a name="8-save-the-report"></a><a name="Save"></a><span data-ttu-id="a9eab-272">8. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="a9eab-272">8. Save the Report</span></span>  
 <span data-ttu-id="a9eab-273">Sie können Berichte auf einem Berichtsserver, in einer SharePoint-Bibliothek oder auf dem Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="a9eab-273">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="a9eab-274">Speichern Sie in diesem Lernprogramm den Bericht auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="a9eab-274">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="a9eab-275">Wenn Sie keinen Zugriff auf einen Berichtsserver besitzen, speichern Sie den Bericht auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="a9eab-275">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="a9eab-276">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="a9eab-276">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="a9eab-277">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-277">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="a9eab-278">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-278">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="a9eab-279">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="a9eab-279">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="a9eab-280">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-280">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="a9eab-281">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a9eab-281">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="a9eab-282">Ersetzen Sie im Feld **Name**den Standardnamen durch **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-282">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
5.  <span data-ttu-id="a9eab-283">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-283">Click **Save**.</span></span>  
  
 <span data-ttu-id="a9eab-284">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a9eab-284">The report is saved to the report server.</span></span> <span data-ttu-id="a9eab-285">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9eab-285">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="a9eab-286">So speichern Sie den Bericht auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="a9eab-286">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="a9eab-287">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-287">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="a9eab-288">Klicken Sie auf **Desktop**, **Meine Dokumente**oder **Arbeitsplatz**, und navigieren Sie anschließend zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="a9eab-288">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="a9eab-289">Ersetzen Sie im Feld **Name**den Standardnamen durch **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-289">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
4.  <span data-ttu-id="a9eab-290">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-290">Click **Save**.</span></span>  
  
##  <a name="9-optional-rotate-text-box-270-degrees"></a><a name="RotateTextBox"></a><span data-ttu-id="a9eab-291">9. (optional) Drehen des Textfelds 270 Grad</span><span class="sxs-lookup"><span data-stu-id="a9eab-291">9. (Optional) Rotate Text Box 270 Degrees</span></span>  
 <span data-ttu-id="a9eab-292">Ein Bericht mit Matrizen kann bei der Ausführung horizontal und vertikal erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-292">A report with matrices can expand horizontally and vertically when it runs.</span></span> <span data-ttu-id="a9eab-293">Durch vertikales Drehen der Textfelder oder um 270 Grad können Sie in horizontaler Richtung Platz sparen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-293">By rotating text boxes vertically, or 270 degrees, you can save horizontal space.</span></span> <span data-ttu-id="a9eab-294">Der gerenderte Bericht ist in diesem Fall schmäler und passt beim Exportieren in ein Format wie Microsoft Word mit einer höheren Wahrscheinlichkeit auf eine gedruckte Seite.</span><span class="sxs-lookup"><span data-stu-id="a9eab-294">The rendered report is then narrower and if exported to a format such as Microsoft Word, will be more likely to fit on a printed page.</span></span>  
  
 <span data-ttu-id="a9eab-295">In einem Textfeld kann Text auch horizontal und vertikal (von oben nach unten) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9eab-295">A text box can also display text as horizontal, vertical (top to bottom).</span></span> <span data-ttu-id="a9eab-296">Weitere Informationen finden Sie unter [Textfelder (Berichts-Generator und SSRS)](report-design/text-boxes-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9eab-296">For more information, see [Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-rotate-text-box-270-degrees"></a><span data-ttu-id="a9eab-297">So drehen Sie das Textfeld um 270 Grad</span><span class="sxs-lookup"><span data-stu-id="a9eab-297">To rotate text box 270 degrees</span></span>  
  
1.  <span data-ttu-id="a9eab-298">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a9eab-298">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="a9eab-299">Klicken Sie auf die Zelle, die `[Territory].` enthält.</span><span class="sxs-lookup"><span data-stu-id="a9eab-299">Click the cell that contains `[Territory].`</span></span>  
  
3.  <span data-ttu-id="a9eab-300">Suchen Sie im Bereich "Eigenschaften" die Eigenschaft "beschreitingmode", und wählen Sie in der Dropdown Liste **Rotate270**aus.</span><span class="sxs-lookup"><span data-stu-id="a9eab-300">In the Properties pane, locate the WritingMode property and in its drop-down list, select **Rotate270**.</span></span>  
  
     <span data-ttu-id="a9eab-301">Wenn der Eigenschaftenbereich nicht geöffnet ist, klicken Sie auf die Registerkarte **Ansicht** des Menübands und aktivieren Sie das Kontrollkästchen **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a9eab-301">If the Properties pane is not open, click the **View** tab of the ribbon, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="a9eab-302">Vergewissern Sie sich, dass die Eigenschaft CanGrow auf festgelegt ist `True` .</span><span class="sxs-lookup"><span data-stu-id="a9eab-302">Verify that the CanGrow property is set to `True`.</span></span>  
  
5.  <span data-ttu-id="a9eab-303">Ändern Sie die Breite der Spalte "Territory" auf ca. 1,3 cm, und löschen Sie den Spaltentitel.</span><span class="sxs-lookup"><span data-stu-id="a9eab-303">Resize the Territory column to be 1/2 inch wide and delete the column title.</span></span>  
  
6.  <span data-ttu-id="a9eab-304">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-304">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="a9eab-305">Der Gebietsname wird vertikal geschrieben (von unten nach oben).</span><span class="sxs-lookup"><span data-stu-id="a9eab-305">The territory name is written vertically, bottom to top.</span></span> <span data-ttu-id="a9eab-306">Die Höhe der Zeilengruppe "Territory" ändert sich abhängig von der Länge des Gebietsnamens.</span><span class="sxs-lookup"><span data-stu-id="a9eab-306">The height of the Territory row group varies by the length of the territory name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a9eab-307">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a9eab-307">Next Steps</span></span>  
 <span data-ttu-id="a9eab-308">Hiermit ist das Lernprogramm für die Erstellung eines Matrixberichts abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a9eab-308">This concludes the tutorial for how to create a matrix report.</span></span> <span data-ttu-id="a9eab-309">Weitere Informationen zu Matrizen finden Sie unter [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrizen &#40;Berichts-Generator und SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix-Datenbereichs Bereiche &#40;Berichts-Generator und SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)und [Zellen, Zeilen und Spalten des Tablix-Datenbereichs &#40;Berichts-Generator&#41; und SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="a9eab-309">For more information about matrices, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9eab-310">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9eab-310">See Also</span></span>  
 <span data-ttu-id="a9eab-311">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="a9eab-311">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="a9eab-312">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a9eab-312">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
