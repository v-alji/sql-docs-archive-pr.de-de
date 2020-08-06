---
title: 'Tutorial: Erstellen eines Freiformberichts (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 87288b59-faf2-4b1d-a8e4-a7582baedf2f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 515b0d2566efa4e11216a28648338c7ec43f3950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722454"
---
# <a name="tutorial-creating-a-free-form-report-report-builder"></a><span data-ttu-id="dcd0b-102">Lernprogramm: Erstellen eines Freiformberichts (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="dcd0b-102">Tutorial: Creating a Free Form Report (Report Builder)</span></span>
  <span data-ttu-id="dcd0b-103">Dieses Lernprogramm zeigt Ihnen, wie Sie einen SSRS-Freiformbericht erstellen, der einem Formularbrief gleicht.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-103">This tutorial teaches you how to create an SSRS free form report that resembles a forms letter.</span></span> <span data-ttu-id="dcd0b-104">Sie können Berichtselemente zu einem Formular mit Textfeldern, Bildern und anderen Datenbereichen anordnen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-104">You can arrange report items to create a form with text boxes, images and other data regions.</span></span>

 <span data-ttu-id="dcd0b-105">Der Bericht, den Sie in diesem Lernprogramm erstellen, basiert auf Beispielumsatzdaten, die im Lernprogramm enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-105">The report you create in this tutorial is based on sample sales data that is included in the tutorial.</span></span> <span data-ttu-id="dcd0b-106">Im Bericht werden Informationen nach Gebiet gruppiert und der Name des Vertriebsmanagers für das Gebiet sowie ausführliche und zusammenfassende Umsatzdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-106">The report groups information by territory and displays the name of the sales manager for the territory as well as detailed and summary sales information.</span></span> <span data-ttu-id="dcd0b-107">Der Listendatenbereich wird als Grundlage für den formfreien Bericht verwendet. Anschließend werden folgende Objekte hinzugefügt: ein dekorativer Bereich mit einem Bild, statischer Text mit eingefügten Daten, eine Tabelle zum Anzeigen ausführlicher Informationen und optional Kreis- und Säulendiagramme zum Anzeigen von Zusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-107">You will use the list data region as the foundation for the free form report, and then add a decorative panel with an image, static text with data inserted, a table to show detailed information, and optionally, pie and column charts to display summary information.</span></span>

##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="dcd0b-108">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="dcd0b-108">What You Will Learn</span></span>
 <span data-ttu-id="dcd0b-109">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dcd0b-109">In this tutorial, you will learn how to do the following:</span></span>

-   [<span data-ttu-id="dcd0b-110">Erstellen eines leeren Berichts, einer leeren Datenquelle und eines leeren Datasets</span><span class="sxs-lookup"><span data-stu-id="dcd0b-110">Create a Blank Report, Data Source, and Dataset</span></span>](#BlankReport)

-   [<span data-ttu-id="dcd0b-111">Hinzufügen und Konfigurieren einer Liste</span><span class="sxs-lookup"><span data-stu-id="dcd0b-111">Add and Configure a List</span></span>](#List)

-   [<span data-ttu-id="dcd0b-112">Hinzufügen von Grafiken</span><span class="sxs-lookup"><span data-stu-id="dcd0b-112">Add Graphics</span></span>](#Graphics)

-   [<span data-ttu-id="dcd0b-113">Hinzufügen von Freitext</span><span class="sxs-lookup"><span data-stu-id="dcd0b-113">Add Free Form Text</span></span>](#Text)

-   [<span data-ttu-id="dcd0b-114">Hinzufügen einer Tabelle zum Anzeigen von Details</span><span class="sxs-lookup"><span data-stu-id="dcd0b-114">Add a Table to Show Details</span></span>](#Table)

-   [<span data-ttu-id="dcd0b-115">Formatieren von Daten</span><span class="sxs-lookup"><span data-stu-id="dcd0b-115">Format Data</span></span>](#Format)

-   [<span data-ttu-id="dcd0b-116">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="dcd0b-116">Save the Report</span></span>](#Save)

### <a name="other-optional-steps"></a><span data-ttu-id="dcd0b-117">Weitere optionale Schritte</span><span class="sxs-lookup"><span data-stu-id="dcd0b-117">Other Optional Steps</span></span>

-   [<span data-ttu-id="dcd0b-118">Hinzufügen einer Zeile zum Trennen von Bereichen des Berichts</span><span class="sxs-lookup"><span data-stu-id="dcd0b-118">Add a Line to Separate Areas of Report</span></span>](#Line)

-   [<span data-ttu-id="dcd0b-119">Hinzufügen von Zusammenfassungsdatenvisualisierung</span><span class="sxs-lookup"><span data-stu-id="dcd0b-119">Add Summary Data Visualization</span></span>](#Visualization)

 <span data-ttu-id="dcd0b-120">Ungefähre Dauer dieses Lernprogramms: 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-120">Estimated time to complete this tutorial: 20 minutes.</span></span>

## <a name="requirements"></a><span data-ttu-id="dcd0b-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dcd0b-121">Requirements</span></span>
 <span data-ttu-id="dcd0b-122">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="dcd0b-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>

##  <a name="1-create-a-blank-report-data-source-and-dataset"></a><a name="BlankReport"></a><span data-ttu-id="dcd0b-123">1. Erstellen eines leeren Berichts, einer leeren Datenquelle und eines leeren Datasets</span><span class="sxs-lookup"><span data-stu-id="dcd0b-123">1. Create a Blank Report, Data Source, and Dataset</span></span>

> [!NOTE]
>  <span data-ttu-id="dcd0b-124">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle für den Bericht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-124">In this tutorial, the query contains the data values so that the report does not need an external data source.</span></span> <span data-ttu-id="dcd0b-125">Die Verwendung dieser Art von internen Daten eignet sich hervorragend für Lernzwecke, aber macht die Abfrage lang.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-125">The use of this type of internal data is great for learning purposes, but the approach makes the query long.</span></span> <span data-ttu-id="dcd0b-126">.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-126">.</span></span>

#### <a name="to-create-a-blank-report"></a><span data-ttu-id="dcd0b-127">So erstellen Sie einen leeren Bericht</span><span class="sxs-lookup"><span data-stu-id="dcd0b-127">To create a blank report</span></span>

1.  <span data-ttu-id="dcd0b-128">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-128">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-129">Das Dialogfeld **Erste Schritte** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-129">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="dcd0b-130">Wenn dies nicht der Fall ist, klicken Sie auf der Schaltfläche des Berichts-Generators auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-130">If it does not, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="dcd0b-131">Vergewissern Sie sich links im Dialogfeld **Erste Schritte** , dass die Option **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-131">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>

3.  <span data-ttu-id="dcd0b-132">Klicken Sie im rechten Bereich auf **Leerer Bericht**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-132">In the right pane, click **Blank Report**.</span></span>

#### <a name="to-create-a-new-data-source"></a><span data-ttu-id="dcd0b-133">So erstellen Sie eine neue Datenquelle</span><span class="sxs-lookup"><span data-stu-id="dcd0b-133">To create a new data source</span></span>

1.  <span data-ttu-id="dcd0b-134">Klicken Sie im Berichtsdatenbereich auf **Neu**, und klicken Sie dann auf **Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-134">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>

2.  <span data-ttu-id="dcd0b-135">Geben Sie im Feld Folgendes ein `Name` : **listdatasource**</span><span class="sxs-lookup"><span data-stu-id="dcd0b-135">In the `Name` box, type: **ListDataSource**</span></span>

3.  <span data-ttu-id="dcd0b-136">Klicken Sie auf **In Bericht eingebettete Verbindung verwenden**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-136">Click **Use a connection embedded in my report**.</span></span>

4.  <span data-ttu-id="dcd0b-137">Vergewissern Sie sich, dass der Verbindungstyp Microsoft SQL Server ist, und geben Sie dann im Feld **Verbindungs Zeichenfolge** Folgendes ein: \*\*Datenquelle = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="dcd0b-137">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>

     <span data-ttu-id="dcd0b-138">\<servername>, z. b. Report001, gibt einen Computer an, auf dem eine Instanz des SQL Server-Datenbank-Engine installiert ist.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-138">\<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="dcd0b-139">Da die Berichtsdaten nicht aus einer SQL Server-Datenbank extrahiert werden, muss der Name einer Datenbank nicht eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-139">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="dcd0b-140">Die Standarddatenbank auf dem angegebenen Server wird verwendet, um die Abfrage zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-140">The default database on the specified server is used to parse the query.</span></span>

5.  <span data-ttu-id="dcd0b-141">Klicken Sie auf **Anmeldeinformationen**und geben Sie die zur Verbindung mit der Instanz der SQL Server-Datenbank-Engine benötigten Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-141">Click **Credentials**, and enter the credentials needed to connect to the instance of the SQL Server Database Engine.</span></span>

6.  <span data-ttu-id="dcd0b-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-142">Click **OK**.</span></span>

#### <a name="to-create-a-new-dataset"></a><span data-ttu-id="dcd0b-143">So erstellen Sie ein neues Dataset</span><span class="sxs-lookup"><span data-stu-id="dcd0b-143">To create a new dataset</span></span>

1.  <span data-ttu-id="dcd0b-144">Klicken Sie im Berichtsdatenbereich auf **Neu**und anschließend auf **Dataset**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-144">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>

2.  <span data-ttu-id="dcd0b-145">Geben Sie im Feld Folgendes ein `Name` : **listdataset.**</span><span class="sxs-lookup"><span data-stu-id="dcd0b-145">In the `Name` box, type: **ListDataset.**</span></span>

3.  <span data-ttu-id="dcd0b-146">Klicken Sie auf **Ein in den eigenen Bericht eingebettetes Dataset verwenden**und überprüfen Sie, ob **ListDataSource**die Datenquelle ist.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-146">Click **Use a dataset embedded in my report**, and verify that the data source is **ListDataSource**.</span></span>

4.  <span data-ttu-id="dcd0b-147">Überprüfen Sie, ob der Abfragetyp **Text** ausgewählt ist, und klicken Sie anschließend auf **Abfrage-Designer**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-147">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>

5.  <span data-ttu-id="dcd0b-148">Klicken Sie auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-148">Click **Edit as Text**.</span></span>

6.  <span data-ttu-id="dcd0b-149">Kopieren Sie die folgende Abfrage, und fügen Sie sie in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="dcd0b-149">Copy and paste the following query into the query pane:</span></span>

    ```
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity
    ```

7.  <span data-ttu-id="dcd0b-150">Klicken Sie auf das Symbol „Ausführen“, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-150">Click Run icon to run the query.</span></span>

     <span data-ttu-id="dcd0b-151">Bei den Abfrageergebnissen handelt es sich um die Daten, die im Bericht angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-151">The query results are the data available to display in your report.</span></span>

     <span data-ttu-id="dcd0b-152">![Abfrage-Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Abfrage-Designer")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-152">![Query Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Query Designer")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="2-add-and-configure-a-list"></a><a name="List"></a><span data-ttu-id="dcd0b-153">2. hinzufügen und Konfigurieren einer Liste</span><span class="sxs-lookup"><span data-stu-id="dcd0b-153">2. Add and Configure a List</span></span>
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="dcd0b-154">stellt drei Datenbereichsvorlagen bereit: Tabelle, Matrix und Liste.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-154">provides three data region templates: table, matrix, and list.</span></span> <span data-ttu-id="dcd0b-155">Diese Vorlagen basieren alle auf einem Tablix-Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-155">These templates are all based on a tablix data region.</span></span>

 <span data-ttu-id="dcd0b-156">In diesem Lernprogramm verwenden Sie eine Liste, um die Umsatzdaten für Vertriebsgebiete in einem Bericht anzuzeigen, der einem Newsletter ähnelt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-156">In this tutorial, you will use a list to display the sales information for sales territories in a report that resembles a newsletter.</span></span> <span data-ttu-id="dcd0b-157">Die Informationen werden nach Gebiet gruppiert.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-157">The information is grouped by territory.</span></span> <span data-ttu-id="dcd0b-158">Sie fügen eine neue Zeilengruppe hinzu, in der Daten nach Gebiet gruppiert werden, und löschen dann die integrierte Zeilengruppe "Details".</span><span class="sxs-lookup"><span data-stu-id="dcd0b-158">You will add a new row group that groups data by territory, and then delete the built-in Details row group.</span></span> <span data-ttu-id="dcd0b-159">Die Listenvorlage ist ideal zum Erstellen von Freiformberichten.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-159">The list template is ideal for creating free form reports.</span></span> <span data-ttu-id="dcd0b-160">Weitere Informationen finden Sie unter [Listen &#40;Berichts-Generator und SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dcd0b-160">For more information, see [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="dcd0b-161">Für diesen Bericht werden als Papierformat Letter (21,6 x 28) und Ränder mit einer Breite von ca. 2,5 cm verwendet.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-161">This report uses the paper size Letter (8.5 X11) and 1 inch margins.</span></span> <span data-ttu-id="dcd0b-162">Eine Berichtsseite, die höher als 22,9 cm oder breiter als 16,5 cm ist, kann zu leeren Seiten führen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-162">A report page taller than 9 inches or wider than 6 1/2 inches might generate blank pages.</span></span>

#### <a name="to-add-a-list"></a><span data-ttu-id="dcd0b-163">So fügen Sie eine Liste hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-163">To add a list</span></span>

1.  <span data-ttu-id="dcd0b-164">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Datenbereiche** auf **Liste** , und ziehen Sie dann die Liste in den Berichtstext.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-164">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List** and then drag the list inside the report body.</span></span> <span data-ttu-id="dcd0b-165">Legen Sie für die Liste eine Höhe von 17,8 cm und eine Breite von 15,9 cm fest.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-165">Make the list 7 inches tall and 6.25 inches wide.</span></span>

2.  <span data-ttu-id="dcd0b-166">Klicken Sie in die Liste, klicken Sie mit Rechtsklick auf den oberen Rand der Liste, und klicken Sie dann auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-166">Click inside the list, right-click the top of the list, and then click **Tablix Properties**.</span></span>

     <span data-ttu-id="dcd0b-167">![Hinzufügen einer Liste](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Hinzufügen einer Liste")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-167">![Adding list](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adding list")</span></span>

3.  <span data-ttu-id="dcd0b-168">Wählen Sie in der Dropdownliste **Datasetname** die Option **ListDataset**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-168">In the **Dataset name** drop-down list, select **ListDataset**.</span></span>

4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

5.  <span data-ttu-id="dcd0b-169">Klicken Sie mit der rechten Maustaste in die Liste und anschließend auf **Rechteckeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-169">Right-click inside the list, and then click **Rectangle Properties**.</span></span>

     <span data-ttu-id="dcd0b-170">![Rechteckeigenschaften (Befehl)](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rechteckeigenschaften (Befehl)")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-170">![Rectangle Properties command](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rectangle Properties command")</span></span>

6.  <span data-ttu-id="dcd0b-171">Aktivieren Sie auf der Registerkarte **Allgemein** das Kontrollkästchen **Seitenumbruch hinzufügen nach** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-171">On the **General** tab, select the **Add a page break after** checkbox.</span></span>

7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-new-row-group-and-to-delete-the-details-group"></a><span data-ttu-id="dcd0b-172">So fügen Sie eine neue Zeilengruppe hinzu und löschen die Detailgruppe</span><span class="sxs-lookup"><span data-stu-id="dcd0b-172">To add a new row group and to delete the Details group</span></span>

1.  <span data-ttu-id="dcd0b-173">Klicken Sie im Bereich „Zeilengruppen“ mit der rechten Maustaste auf die Gruppe „Details“, zeigen Sie auf **Gruppe hinzufügen**, und klicken Sie anschließend auf **Übergeordnete Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-173">In the Row Groups pane, right-click the Details group, point to **Add Group**, and then click **Parent Group**.</span></span>

     <span data-ttu-id="dcd0b-174">![Übergeordnete Gruppe (Befehl)](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Übergeordnete Gruppe (Befehl)")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-174">![Parent Group command](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Parent Group command")</span></span>

2.  <span data-ttu-id="dcd0b-175">Wählen Sie in der Dropdown Liste`[Territory].`</span><span class="sxs-lookup"><span data-stu-id="dcd0b-175">In the drop-down list, select `[Territory].`</span></span>

3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="dcd0b-176">Eine neue Spalte wird der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-176">A column is added to the list.</span></span> <span data-ttu-id="dcd0b-177">Die Spalte enthält die Zelle `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="dcd0b-177">The column contains the cell `[Territory].`</span></span>

4.  <span data-ttu-id="dcd0b-178">Klicken Sie mit der rechten Maustaste in der Liste auf die Spalte „Territory“, und klicken Sie anschließend auf **Spalten löschen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-178">Right-click the Territory column in the list, and then click **Delete Columns**.</span></span>

     <span data-ttu-id="dcd0b-179">![Spalten löschen](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Spalten löschen")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-179">![Delete columns](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Delete columns")</span></span>

5.  <span data-ttu-id="dcd0b-180">Klicken Sie auf **Nur Spalten löschen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-180">Click **Delete Columns only**.</span></span>

     <span data-ttu-id="dcd0b-181">![Spalten löschen (Dialogfeld)](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Spalten löschen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-181">![Delete Columns dialog box](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Delete Columns dialog box")</span></span>

6.  <span data-ttu-id="dcd0b-182">Klicken Sie im Bereich "Zeilengruppen" mit der rechten Maustaste auf die Gruppe **Details** , und klicken Sie dann auf **Gruppe löschen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-182">In the Row Groups pane, right-click the **Details** group, and then click **Delete Group**.</span></span>

     <span data-ttu-id="dcd0b-183">![Löschen der Detailgruppe](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Löschen der Detailgruppe")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-183">![Delete Details Group](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Delete Details Group")</span></span>

7.  <span data-ttu-id="dcd0b-184">Klicken Sie auf **Nur Gruppe löschen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-184">Click **Delete Group only**.</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="3-add-graphics"></a><a name="Graphics"></a><span data-ttu-id="dcd0b-185">3. Hinzufügen von Grafiken</span><span class="sxs-lookup"><span data-stu-id="dcd0b-185">3. Add Graphics</span></span>
 <span data-ttu-id="dcd0b-186">Einer der Vorteile der Verwendung eines Listendatenbereichs besteht darin, dass Berichtselemente wie z. B. Rechtecke und Textfelder überall hingefügt werden können und keine Beschränkung auf ein tabellarisches Layout besteht.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-186">One of the advantages of using a list data region is that you can add report items such as rectangles and text boxes anywhere, instead of being limited to a tabular layout.</span></span> <span data-ttu-id="dcd0b-187">Sie verbessern die Darstellung des Berichts durch Hinzufügen einer Grafik (ein mit einer Farbe ausgefülltes Rechteck).</span><span class="sxs-lookup"><span data-stu-id="dcd0b-187">You will enhance the appearance of the report by adding a graphic (a rectangle filled with a color).</span></span>

#### <a name="to-add-graphic-elements-to-the-report"></a><span data-ttu-id="dcd0b-188">So fügen Sie dem Bericht grafische Elemente hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-188">To add graphic elements to the report</span></span>

1.  <span data-ttu-id="dcd0b-189">Klicken Sie im Menüband auf der Registerkarte **Einfügen** auf **Rechteck**, und ziehen Sie dann ein Rechteck in die linke obere Ecke der Liste.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-189">On the **Insert** tab of the ribbon, click **Rectangle**,and then drag a rectangle to the upper left corner of the list.</span></span> <span data-ttu-id="dcd0b-190">Legen Sie für das Rechteck eine Höhe von 17,8 cm und eine Breite von 2,5 cm fest.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-190">Make the rectangle 7 inches tall and 1 inch wide.</span></span>

2.  <span data-ttu-id="dcd0b-191">Klicken Sie mit der rechten Maustaste auf das Rechteck, und klicken Sie anschließend auf **Rechteckeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-191">Right-click the rectangle, and then click **Rectangle Properties**.</span></span>

3.  <span data-ttu-id="dcd0b-192">Klicken Sie auf die Registerkarte **Ausfüllen** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-192">Click the **Fill** tab.</span></span>

4.  <span data-ttu-id="dcd0b-193">Klicken Sie in der Dropdownliste **Füllfarbe** auf **Weitere Farben**, und wählen Sie dann die Farbe **Dunkelgrau** aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-193">In the **Fill color** drop-down list, click **More Colors**, and then select the **DarkGray** color.</span></span>

     <span data-ttu-id="dcd0b-194">![Auswählen der Füllfarbe](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Auswählen der Füllfarbe")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-194">![Select fill color](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Select fill color")</span></span>

5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

6.  <span data-ttu-id="dcd0b-195">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-195">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="dcd0b-196">Die linke Seite des Berichts enthält nun eine vertikale Grafik, die aus einem dunkelgrauen Rechteck besteht.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-196">The left side of the report now has vertical graphic that consists of a dark gray rectangle.</span></span>

##  <a name="4-add-free-form-text"></a><a name="Text"></a><span data-ttu-id="dcd0b-197">4. Hinzufügen von freiem Formular Text</span><span class="sxs-lookup"><span data-stu-id="dcd0b-197">4. Add Free Form Text</span></span>
 <span data-ttu-id="dcd0b-198">Ein Textfeld enthält statischen Text, der auf jeder Berichtsseite sowie in allen Datenfeldern wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-198">A text box contains static text that is repeated on each report page as well as data fields.</span></span>

#### <a name="to-add-text-to-the-report"></a><span data-ttu-id="dcd0b-199">So fügen Sie dem Bericht Text hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-199">To add text to the report</span></span>

1.  <span data-ttu-id="dcd0b-200">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-200">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="dcd0b-201">Klicken Sie auf der Registerkarte **Einfügen** des Menübands auf **Textfeld**, und ziehen Sie dann ein Textfeld in die linke obere Ecke der Liste, jedoch innerhalb des zuvor hinzugefügten Rechtecks.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-201">On the **Insert** tab of the ribbon, click **Text Box**, and then drag a text box to the upper left corner of the list, but inside of the rectangle you added previously.</span></span> <span data-ttu-id="dcd0b-202">Legen Sie für das Textfeld eine Höhe von ca. 7,5 cm und eine Breite von ca. 12,7 cm fest.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-202">Make the text box about 3 inches tall and 5 inches wide.</span></span>

3.  <span data-ttu-id="dcd0b-203">Setzen Sie den Cursor in den oberen Bereich des Textfelds, und geben Sie anschließend Folgendes ein: **Newsletter für** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-203">Place the cursor in the upper part of the text box, and then type: **Newsletter for** .</span></span>

     <span data-ttu-id="dcd0b-204">![Hinzufügen von Text für Newsletterüberschriften](../../2014/tutorials/media/tutorial-newsletterfor.png "Hinzufügen von Text für Newsletterüberschriften")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-204">![Add newsletter heading text](../../2014/tutorials/media/tutorial-newsletterfor.png "Add newsletter heading text")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-205">Fügen Sie nach dem Begriff "für" zusätzliche Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-205">Be sure to include the extra space after the word "for".</span></span> <span data-ttu-id="dcd0b-206">Durch die Leerzeichen werden der Text und das Feld getrennt, die im nächsten Schritt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-206">The space separates the text and the field that you will add in the next step.</span></span>

4.  <span data-ttu-id="dcd0b-207">Ziehen Sie das Feld "Territory" in das Textfeld, und platzieren Sie es nach dem Text, den Sie in Schritt 3 eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-207">Drag the Territory field to the text box and place it after the text you typed in step 3.</span></span>

     <span data-ttu-id="dcd0b-208">![Hinzufügen eines Gebietsfelds](../../2014/tutorials/media/tutorial-addterritorialfield.png "Hinzufügen eines Gebietsfelds")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-208">![Add Territorial field](../../2014/tutorials/media/tutorial-addterritorialfield.png "Add Territorial field")</span></span>

5.  <span data-ttu-id="dcd0b-209">Markieren Sie den gesamten Text, klicken Sie mit der rechten Maustaste, und klicken Sie anschließend auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-209">Select all text, right-click, and then click **Text Properties**.</span></span>

6.  <span data-ttu-id="dcd0b-210">Klicken Sie auf die Registerkarte **Schriftart** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-210">Click the **Font** tab.</span></span>

7.  <span data-ttu-id="dcd0b-211">Wählen Sie in der Liste **Schriftart** die Schriftart **Times New Roman**, in **Größe** den Wert **20 pt**und in **Farbe** die Option **Rot**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-211">In the **Font** list, select **Times New Roman**; in **Size** select **20 pt**, in **Color** select **Red**.</span></span>

     <span data-ttu-id="dcd0b-212">![Text Eigenschaften](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Texteigenschaften")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-212">![Text Properties](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Text Properties")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

9. <span data-ttu-id="dcd0b-213">Platzieren Sie den Cursor unter dem Text, den Sie in Schritt 3 eingegeben haben, und geben Sie **Hello** ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-213">Place the cursor below the text you typed in step 3 and type: **Hello** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-214">Fügen Sie nach dem Begriff "Hello" zusätzliche Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-214">Be sure to include the extra space after the word "Hello".</span></span> <span data-ttu-id="dcd0b-215">Durch die Leerzeichen werden der Text und das Feld getrennt, die im nächsten Schritt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-215">The space separates the text and the field that you will add in the next step.</span></span>

10. <span data-ttu-id="dcd0b-216">Ziehen Sie das Feld "FullName" in das Textfeld, ordnen Sie es hinter dem Text an, den Sie in Schritt 9 eingegeben haben, und geben Sie dann ein Komma (,) ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-216">Drag the FullName field to the text box and place it after the text you typed in step 9, and then type a comma (,).</span></span>

     <span data-ttu-id="dcd0b-217">![Hinzufügen eines Felds für den vollständigen Namen](../../2014/tutorials/media/tutorial-addfullnamefield.png "Hinzufügen eines Felds für den vollständigen Namen")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-217">![Add Full Name field](../../2014/tutorials/media/tutorial-addfullnamefield.png "Add Full Name field")</span></span>

11. <span data-ttu-id="dcd0b-218">Wählen Sie den Text aus, den Sie in Schritt 9 und 10 hinzugefügt haben, klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-218">Select the text you added in steps 9 and 10, right-click, and then click **Text Properties**.</span></span>

12. <span data-ttu-id="dcd0b-219">Klicken Sie auf die Registerkarte **Schriftart** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-219">Click the **Font** tab.</span></span>

13. <span data-ttu-id="dcd0b-220">Wählen Sie in der Liste **Schriftart** die Schriftart **Times New Roman**, in **Größe** den Wert **16 pt**und in **Farbe** die Option **Schwarz** aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-220">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Black** color.</span></span>

14. [!INCLUDE[clickOK](../includes/clickok-md.md)]

15. <span data-ttu-id="dcd0b-221">Setzen Sie den Cursor unter den Text, den Sie in den Schritten 9 bis 13 hinzugefügt haben, und kopieren Sie anschließend den folgenden "griechischen" Text, und fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="dcd0b-221">Place the cursor below the text you added in steps 9 through 13, and then copy and paste the following "greeked" text:</span></span>

    ```
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sed dolor in ipsum pulvinar egestas. Sed sed lacus at leo ornare ultricies. Vivamus velit risus, euismod nec sodales gravida, gravida in dui. Etiam ullamcorper elit vitae justo fermentum ut ullamcorper augue sodales. Ut placerat, nisl quis feugiat adipiscing, nibh est aliquet est, mollis faucibus mauris lectus quis arcu. In mollis tincidunt lacinia. In vitae erat ut lorem tincidunt luctus. Curabitur et magna nunc, sit amet adipiscing nisi. Nulla rhoncus elementum orci nec tincidunt. Aliquam imperdiet cursus erat vel tincidunt. Donec et neque ac urna rutrum sodales. In id purus et nisl dignissim dapibus. Sed rhoncus metus at felis feugiat eu tempor dolor vehicula. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam faucibus consectetur diam eu pellentesque. 
    Nulla facilisi. Proin ligula enim, porta ut tincidunt id, adipiscing sit amet eros. Ut purus sem, bibendum et vulputate sit amet, facilisis eget magna. Sed aliquam erat non erat eleifend hendrerit. Ut a ligula est, sit amet eleifend enim. Ut et nisl enim, sit amet adipiscing augue. Vivamus eu arcu ac libero posuere elementum. Integer condimentum bibendum venenatis. Integer odio tellus, feugiat in pellentesque semper, interdum nec sem. Sed cursus euismod sem, ut elementum sapien placerat vel. 
    ```

16. <span data-ttu-id="dcd0b-222">Markieren Sie den Text, den Sie in Schritt 15 hinzugefügt haben, klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-222">Select the text you added in steps 15, right-click, and then click **Text Properties**.</span></span>

17. <span data-ttu-id="dcd0b-223">Klicken Sie auf die Registerkarte **Schriftart** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-223">Click the **Font** tab.</span></span>

18. <span data-ttu-id="dcd0b-224">Wählen Sie in der Liste **Schriftart** die Schriftart **Arial**in **Größe** den Wert **10 pt**und in **Farbe** die Option **Schwarz**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-224">In the **Font** list, select **Arial**; in **Size** select **10 pt**, in **Color** select **Black**.</span></span>

19. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="dcd0b-225">![Hinzufügen von Newslettertext](../../2014/tutorials/media/tutorial-newslettertext.png "Hinzufügen von Newslettertext")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-225">![Add newsletter text](../../2014/tutorials/media/tutorial-newslettertext.png "Add newsletter text")</span></span>

20. <span data-ttu-id="dcd0b-226">Setzen Sie den Cursor unter den Text, den Sie in Schritt 15 eingefügt haben, und geben Sie dann Folgendes ein: **Glückwünsche zum Gesamtumsatz von** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-226">Place the cursor below the text you pasted in step 15, and then type: **Congratulations on your total sales of** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-227">Fügen Sie nach dem Begriff "von" zusätzliche Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-227">Be sure to include the extra space after the word "of".</span></span> <span data-ttu-id="dcd0b-228">Durch die Leerzeichen werden der Text und das Feld getrennt, die im nächsten Schritt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-228">The space separates the text and the field that you will add in the next step.</span></span>

21. <span data-ttu-id="dcd0b-229">Ziehen Sie das Feld "Sales" in das Textfeld, platzieren Sie es hinter dem in Schritt 20 eingegebenen Text, und geben Sie dann ein Ausrufezeichen (!) ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-229">Drag the Sales field to the text box, place it after the text you typed in step 20, and then type an exclamation mark (!).</span></span>

22. <span data-ttu-id="dcd0b-230">Markieren Sie das Feld Sales, klicken Sie mit der rechten Maustaste auf das Feld, und klicken Sie dann auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-230">Highlight the Sales field, right-click the field, and then click **Expression**.</span></span>

23. <span data-ttu-id="dcd0b-231">Ändern Sie im Ausdrucksfeld den Ausdruck folgendermaßen so, dass er die Sum-Funktion einschließt:</span><span class="sxs-lookup"><span data-stu-id="dcd0b-231">In the expression box, change the expression to include the Sum function as follows:</span></span>

    ```
    =Sum(Fields!Sales.value)
    ```

24. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="dcd0b-232">![Hinzufügen eines Ausdrucks zum Sales-Feld](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Hinzufügen eines Ausdrucks zum Sales-Feld")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-232">![Add an expression to sales field](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Add an expression to sales field")</span></span>

25. <span data-ttu-id="dcd0b-233">Wählen Sie den Text aus, den Sie in den Schritten 20 bis 23 hinzugefügt haben, klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-233">Select the text you added in steps 20 through 23, right-click, and then click **Text Properties**.</span></span>

26. <span data-ttu-id="dcd0b-234">Klicken Sie auf die Registerkarte **Schriftart** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-234">Click the **Font** tab.</span></span>

27. <span data-ttu-id="dcd0b-235">Wählen Sie in der Liste **Schriftart** die Schriftart **Times New Roman**, in **Größe** den Wert **16 pt**und in **Farbe** die Option **Rot**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-235">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Red**.</span></span>

28. [!INCLUDE[clickOK](../includes/clickok-md.md)]

29. <span data-ttu-id="dcd0b-236">Wählen Sie `[Sum(Sales)]` aus. Klicken Sie anschließend auf der Registerkarte **Home** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-236">Select `[Sum(Sales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="dcd0b-237">![Hinzufügen eines Währungssymbols](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Hinzufügen eines Währungssymbols")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-237">![Add currency symbol](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Add currency symbol")</span></span>

30. <span data-ttu-id="dcd0b-238">Klicken Sie mit der rechten Maustaste auf das Textfeld mit dem Text „Zum Hinzufügen eines Titels klicken“, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-238">Right-click the text box with the "Click to add title" text, and then click **Delete**.</span></span>

31. <span data-ttu-id="dcd0b-239">Markieren Sie das Listenfeld, und verschieben Sie es mithilfe der Pfeiltasten an den Seitenanfang.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-239">Select the list box and using the arrow keys, move it to the top of the page.</span></span>

32. <span data-ttu-id="dcd0b-240">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-240">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="dcd0b-241">Im Bericht wird statischer Text angezeigt, und jede Berichtsseite enthält Daten, die sich auf ein Gebiet beziehen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-241">The report displays static text and each report page includes data that pertains to a territory.</span></span> <span data-ttu-id="dcd0b-242">Umsatz wird als Währung formatiert.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-242">Sales are formatted as currency.</span></span>

 <span data-ttu-id="dcd0b-243">![Vorschau für Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Vorschau für Newsletter")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-243">![Preview of Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Preview of Newsletter")</span></span>

##  <a name="5-add-a-table-to-show-sales-details"></a><a name="Table"></a><span data-ttu-id="dcd0b-244">5. Hinzufügen einer Tabelle, um Umsatz Details anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="dcd0b-244">5. Add a Table to Show Sales Details</span></span>
 <span data-ttu-id="dcd0b-245">Fügen Sie dem formfreien Bericht mithilfe des Assistenten für neue Tabellen und Matrizen eine Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-245">Use the New Table and Matrix Wizard to add a table to the free form report.</span></span> <span data-ttu-id="dcd0b-246">Nach Fertigstellung des Assistenten wird manuell eine Zeile für Summen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-246">After you complete the wizard, you will manually add a row for totals.</span></span>

#### <a name="to-add-a-table"></a><span data-ttu-id="dcd0b-247">So fügen Sie eine Tabelle hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-247">To add a table</span></span>

1.  <span data-ttu-id="dcd0b-248">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Datenbereiche** auf **Tabelle**und anschließend auf **Tabellen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-248">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **Table**, and then click **Table Wizard**.</span></span>

2.  <span data-ttu-id="dcd0b-249">Klicken Sie auf der Seite "Dataset auswählen" auf **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-249">On the Choose a dataset page, click **ListDataset**.</span></span>

3.  <span data-ttu-id="dcd0b-250">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-250">Click **Next**.</span></span>

4.  <span data-ttu-id="dcd0b-251">Ziehen Sie auf der Seite **Felder anordnen** das Feld „Product“ von **Verfügbare Felder** zu **Werte**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-251">On the **Arrange fields** page, drag the Product field from **Available fields** to **Values.**</span></span>

5.  <span data-ttu-id="dcd0b-252">Wiederholen Sie Schritt 4 für "SalesDate", "Quantity und "Sales".</span><span class="sxs-lookup"><span data-stu-id="dcd0b-252">Repeat step 4, for SalesDate, Quantity, and Sales.</span></span> <span data-ttu-id="dcd0b-253">Orden Sie "SalesDate" unter Produkt, "Quantity" unter "SalesDate" und "Sales" unter "SalesDate" an.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-253">Place SalesDate below Product, Quantity below SalesDate, and Sales below SalesDate.</span></span>

6.  <span data-ttu-id="dcd0b-254">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-254">Click **Next**.</span></span>

7.  <span data-ttu-id="dcd0b-255">Zeigen Sie auf der Seite **Layout auswählen** das Layout der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-255">On the **Choose the layout** page, view the layout of the table.</span></span>

     <span data-ttu-id="dcd0b-256">Die Tabelle ist sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-256">The table is very simple.</span></span> <span data-ttu-id="dcd0b-257">Sie besteht aus fünf Spalten und enthält keine Zeilen- oder Spaltengruppen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-257">It consists of five columns and has no row or column groups.</span></span> <span data-ttu-id="dcd0b-258">Da die Tabelle keine Gruppen enthält, sind die gruppenbezogenen Layoutoptionen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-258">Because it has no groups, the layout options related to groups, are not available.</span></span> <span data-ttu-id="dcd0b-259">Im späteren Verlauf des Lernprogramms wird Tabelle manuell aktualisiert, damit sie eine Summe enthält.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-259">You will manually update the table to include a total later in the tutorial.</span></span>

8.  <span data-ttu-id="dcd0b-260">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-260">Click **Next**.</span></span>

9. <span data-ttu-id="dcd0b-261">Wählen Sie auf der Seite **Format auswählen** im Bereich **Formate** die Option **Schiefer**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-261">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

10. <span data-ttu-id="dcd0b-262">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-262">Click **Finish**.</span></span>

11. <span data-ttu-id="dcd0b-263">Ziehen Sie die Tabelle unter das Textfeld, das Sie in Lektion 4 hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-263">Drag the table to below the text box that you added in lesson 4.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-264">Stellen Sie sicher, dass sich die Tabelle in der Liste befindet.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-264">Make sure the table is inside the list.</span></span>

12. <span data-ttu-id="dcd0b-265">Nachdem Sie bestätigt haben, dass die Tabelle ausgewählt wurde, klicken Sie im Zeilengruppenbereich mit der rechten Maustaste auf „Details“, zeigen Sie auf **Gesamtergebnis hinzufügen**, und klicken Sie dann auf **Nach**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-265">Confirmed that the table is selected, then in the Row Group pane right-click Details, point to **Add Total**, and then click **After**.</span></span>

     <span data-ttu-id="dcd0b-266">![Hinzufügen einer Summe des Berichts](../../2014/tutorials/media/tutorial-addtotal.png "Hinzufügen einer Summe des Berichts")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-266">![Add report total](../../2014/tutorials/media/tutorial-addtotal.png "Add report total")</span></span>

13. <span data-ttu-id="dcd0b-267">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-267">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="dcd0b-268">Im Bericht wird eine Tabelle mit Umsatzdetails und Gesamtbeträgen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-268">The report displays a table with sales details and totals.</span></span>

 <span data-ttu-id="dcd0b-269">![Gesamtumsatz im Bericht](../../2014/tutorials/media/tutorial-reportsalestotals.png "Gesamtumsatz im Bericht")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-269">![Sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Sales totals in report")</span></span>

##  <a name="6-format-data"></a><a name="Format"></a><span data-ttu-id="dcd0b-270">6. Formatieren von Daten</span><span class="sxs-lookup"><span data-stu-id="dcd0b-270">6. Format Data</span></span>
 <span data-ttu-id="dcd0b-271">Formatieren Sie numerische Daten nur als Währung und Datumsangaben nur als Tag- und Uhrzeitangaben.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-271">Format numeric data as currency and dates as day and time only.</span></span>

#### <a name="to-format-fields-table"></a><span data-ttu-id="dcd0b-272">So formatieren Sie die Feldtabelle</span><span class="sxs-lookup"><span data-stu-id="dcd0b-272">To format fields table</span></span>

1.  <span data-ttu-id="dcd0b-273">Klicken Sie auf **Entwurf** , um zur Entwurfs Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-273">Click **Design** to switch to design view.</span></span>

2.  <span data-ttu-id="dcd0b-274">Klicken Sie auf die Tabellenzellen, die `[Sum(SalesSales)]` enthalten, und klicken Sie auf der Registerkarte **Home** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-274">Click the table cells that contain `[Sum(SalesSales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="dcd0b-275">![Hinzufügen eines Währungssymbols zur Verkaufssumme](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Hinzufügen eines Währungssymbols zur Verkaufssumme")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-275">![Add currency symbol to sum sales](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Add currency symbol to sum sales")</span></span>

3.  <span data-ttu-id="dcd0b-276">Klicken Sie auf die Zelle, die `[SalesDate]` enthält, und wählen Sie in der Gruppe **Zahl** aus der Dropdownliste **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-276">Click the cell that contains `[SalesDate]` and in the **Number** group, from the drop-down list, select **Date**.</span></span>

4.  <span data-ttu-id="dcd0b-277">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-277">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="dcd0b-278">Im Bericht werden nun formatierte Daten angezeigt, und die Lesbarkeit wurde verbessert.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-278">The report now displays formatted data and is easier to read.</span></span>

 <span data-ttu-id="dcd0b-279">![Formatieren von Gesamtumsätzen im Bericht](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Formatieren von Gesamtumsätzen im Bericht")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-279">![Format sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Format sales totals in report")</span></span>

##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="dcd0b-280">7. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="dcd0b-280">7. Save the Report</span></span>
 <span data-ttu-id="dcd0b-281">Sie können Berichte auf einem Berichtsserver, in einer SharePoint-Bibliothek oder auf dem Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-281">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="dcd0b-282">Sie können den Bericht auch in eine Vielzahl von Formaten wie Word und PDF exportieren, indem Sie den Bericht ausführen und das Format aus dem Menü **Exportieren** auswählen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-282">You can also export the report to a variety of formats such as Word and PDF, by running the report and selecting the format from the **Export** menu.</span></span>

 <span data-ttu-id="dcd0b-283">Speichern Sie in diesem Lernprogramm den Bericht auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-283">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="dcd0b-284">Wenn Sie keinen Zugriff auf einen Berichtsserver besitzen, speichern Sie den Bericht auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-284">If you do not have access to a report server, save the report to your computer.</span></span>

#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="dcd0b-285">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="dcd0b-285">To save the report on a report server</span></span>

1.  <span data-ttu-id="dcd0b-286">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-286">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="dcd0b-287">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-287">Click **Recent Sites and Servers**.</span></span>

3.  <span data-ttu-id="dcd0b-288">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-288">Select or type the name of the report server where you have permission to save reports.</span></span>

     <span data-ttu-id="dcd0b-289">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-289">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="dcd0b-290">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-290">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>

4.  <span data-ttu-id="dcd0b-291">Ersetzen Sie in `Name` den Standardnamen durch **salesinformationbyterritory**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-291">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

5.  <span data-ttu-id="dcd0b-292">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-292">Click **Save**.</span></span>

 <span data-ttu-id="dcd0b-293">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-293">The report is saved to the report server.</span></span> <span data-ttu-id="dcd0b-294">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-294">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>

#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="dcd0b-295">So speichern Sie den Bericht auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="dcd0b-295">To save the report on your computer</span></span>

1.  <span data-ttu-id="dcd0b-296">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-296">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="dcd0b-297">Klicken Sie auf **Desktop**, **Meine Dokumente**oder **Arbeitsplatz**, und navigieren Sie anschließend zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-297">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>

3.  <span data-ttu-id="dcd0b-298">Ersetzen Sie in `Name` den Standardnamen durch **salesinformationbyterritory**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-298">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

4.  <span data-ttu-id="dcd0b-299">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-299">Click **Save**.</span></span>

##  <a name="8-optional-add-a-line-to-separate-areas-of-the-report"></a><a name="Line"></a><span data-ttu-id="dcd0b-300">8. (optional) Hinzufügen einer Zeile zum Trennen von Bereichen des Berichts</span><span class="sxs-lookup"><span data-stu-id="dcd0b-300">8. (Optional) Add a Line to Separate Areas of the Report</span></span>
 <span data-ttu-id="dcd0b-301">Fügen Sie eine Zeile hinzu, um den Leitartikel und die Details des Berichts zu trennen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-301">Add a line to separate the editorial and details areas of the report.</span></span>

#### <a name="to-add-a-line"></a><span data-ttu-id="dcd0b-302">So fügen Sie eine Linie hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-302">To add a line</span></span>

1.  <span data-ttu-id="dcd0b-303">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-303">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="dcd0b-304">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Berichtselemente** auf **Linie**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-304">On the **Insert** tab of the ribbon, in the **Report Items** area, click **Line.**</span></span>

3.  <span data-ttu-id="dcd0b-305">Zeichnen Sie eine Linie unter dem Freitextfeld, das Sie in Lektion 4 hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-305">Draw a line below the free form text box you added in lesson 4.</span></span>

4.  <span data-ttu-id="dcd0b-306">Klicken Sie auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-306">Click the line.</span></span>

5.  <span data-ttu-id="dcd0b-307">Klicken Sie auf die Registerkarte **Home** .</span><span class="sxs-lookup"><span data-stu-id="dcd0b-307">Click the **Home** tab.</span></span>

6.  <span data-ttu-id="dcd0b-308">Wählen Sie im Bereich **Rahmen** für die Breite den Wert **4 1/2** pt aus, und wählen Sie für Farbe **Rot**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-308">In the **Border** area, for width select **4 1/2** pt and for color, for color select **Red**.</span></span>

     <span data-ttu-id="dcd0b-309">![Hinzufügen einer Zeile zum Bericht](../../2014/tutorials/media/tutorial-reportwithline.png "Hinzufügen einer Zeile zum Bericht")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-309">![Add line to report](../../2014/tutorials/media/tutorial-reportwithline.png "Add line to report")</span></span>

##  <a name="9-optional-add-summary-data-visualization"></a><a name="Visualization"></a><span data-ttu-id="dcd0b-310">9. (optional) Hinzufügen einer Zusammenfassungs Datenvisualisierung</span><span class="sxs-lookup"><span data-stu-id="dcd0b-310">9. (Optional) Add Summary Data Visualization</span></span>
 <span data-ttu-id="dcd0b-311">Mit Rechtecken kann das Rendern des Berichts beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-311">Rectangles help you control how the report renders.</span></span> <span data-ttu-id="dcd0b-312">Platzieren Sie in einem Rechteck ein Kreis- und ein Säulendiagramm, um sicherzustellen, dass der Bericht wunschgemäß gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-312">Place a pie and column chart inside a rectangle to ensure that the report renders the way you want.</span></span>

#### <a name="to-add-a-rectangle"></a><span data-ttu-id="dcd0b-313">So fügen Sie ein Rechteck hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-313">To add a rectangle</span></span>

1.  <span data-ttu-id="dcd0b-314">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-314">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="dcd0b-315">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Berichtselemente** auf **Rechteck**, und ziehen Sie das Rechteck in die Liste rechts neben der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-315">On the **Insert** tab of the ribbon, in the **Report Items** area click **Rectangle**, and then drag the rectangle inside the list, to the right of the table.</span></span> <span data-ttu-id="dcd0b-316">Legen Sie für das Rechteck eine Breite von 5 cm und eine Höhe von 10 cm fest.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-316">Make the rectangle 2 inches wide and 4 inches tall.</span></span>

3.  <span data-ttu-id="dcd0b-317">Richten Sie den oberen Bereich des Rechtecks und der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-317">Align the tops of the rectangle and the table.</span></span>

#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="dcd0b-318">So fügen Sie ein Kreisdiagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-318">To add a pie chart</span></span>

1.  <span data-ttu-id="dcd0b-319">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Datenvisualisierungen** auf **Diagramm** und anschließend auf **Diagramm-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-319">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="dcd0b-320">Klicken Sie auf der Seite Dataset auswählen auf **ListDataset**, und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-320">On the Choose a dataset page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="dcd0b-321">Klicken Sie auf **Kreis**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-321">Click **Pie**, and then click **Next**.</span></span>

4.  <span data-ttu-id="dcd0b-322">Ziehen Sie auf der Seite „Diagrammfelder anordnen“ das Feld „Product“ in **Kategorien**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-322">On the arrange chart fields page, drag Product to **Categories**.</span></span>

5.  <span data-ttu-id="dcd0b-323">Ziehen Sie Menge in **Werte**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-323">Drag Quantity to **Values**, and then click **Next**.</span></span>

6.  <span data-ttu-id="dcd0b-324">Wählen Sie auf der Seite **Format auswählen** im Bereich **Formate** die Option **Schiefer**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-324">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="dcd0b-325">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-325">Click **Finish**.</span></span>

8.  <span data-ttu-id="dcd0b-326">Ändern Sie die Größe des Diagramms, das oben links im Bericht angezeigt wird, auf eine Höhe von 4 cm und eine Breite von 5 cm.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-326">Resize the chart that appears in the upper left corner of the report, to be 1 1/2 inches tall and 2 inches wide.</span></span>

9. <span data-ttu-id="dcd0b-327">Ziehen Sie das Diagramm in das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-327">Drag the chart inside the rectangle.</span></span>

     <span data-ttu-id="dcd0b-328">![Hinzufügen eines Kreisdiagramms](../../2014/tutorials/media/tutorial-addpiechart.png "Hinzufügen eines Kreisdiagramms")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-328">![Add pie chart](../../2014/tutorials/media/tutorial-addpiechart.png "Add pie chart")</span></span>

10. <span data-ttu-id="dcd0b-329">Klicken Sie mit der rechten Maustaste auf den Diagrammtitel, und klicken Sie dann auf **Titeleigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-329">Right-click the chart title, and then click **Title Properties**.</span></span>

11. <span data-ttu-id="dcd0b-330">Geben Sie im Dialogfeld **Diagrammtiteleigenschaften** im Titeltext Folgendes ein: **Verkaufte Produktmengen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-330">In the **Chart Title Properties** dialog box, in Title text, type: **Product Quantities Sold**.</span></span>

12. <span data-ttu-id="dcd0b-331">Klicken Sie auf die Registerkarte **Schriftart** , und klicken Sie in der Liste **Größe** auf **10 pt**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-331">Click the **Font** tab, and in the **Size** list, click **10pt**.</span></span>

13. [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-column-chart"></a><span data-ttu-id="dcd0b-332">So fügen Sie einem Bericht ein Säulendiagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="dcd0b-332">To add a column chart</span></span>

1.  <span data-ttu-id="dcd0b-333">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Datenvisualisierungen** auf **Diagramm** und anschließend auf **Diagramm-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-333">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="dcd0b-334">Klicken Sie auf der Seite **Dataset auswählen** auf **ListDataset**, und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-334">On the **Choose a dataset** page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="dcd0b-335">Klicken Sie auf **Spalte**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-335">Click **Column**, and then click **Next**.</span></span>

4.  <span data-ttu-id="dcd0b-336">Ziehen Sie auf der Seite Diagramm Felder anordnen das Feld Product in **Kategorien**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-336">On the arrange chart fields page, drag the Product field to **Categories**.</span></span>

5.  <span data-ttu-id="dcd0b-337">Ziehen Sie „Sales“ in das Feld **Werte** , und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-337">Drag Sales to **Values,** and then click **Next**.</span></span>

     <span data-ttu-id="dcd0b-338">Werte werden auf der vertikalen Achse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-338">Values display on the vertical axis.</span></span>

6.  <span data-ttu-id="dcd0b-339">Wählen Sie auf der Seite **Format auswählen** im Bereich **Formate** die Option **Schiefer**aus.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-339">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="dcd0b-340">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-340">Click **Finish**.</span></span>

     <span data-ttu-id="dcd0b-341">Ein Säulendiagramm wird oben links im Bericht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-341">A column chart is added to the upper left corner of the report.</span></span>

8.  <span data-ttu-id="dcd0b-342">Legen Sie die für das Diagramm eine Breite von 5 cm und eine Höhe von 5 cm fest.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-342">Resize the chart to be 2 inches wide and 2 inches tall.</span></span>

9. <span data-ttu-id="dcd0b-343">Ziehen Sie das Diagramm in das Rechteck unter dem Kreisdiagramm.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-343">Drag the chart inside the rectangle, below the pie chart.</span></span>

     <span data-ttu-id="dcd0b-344">![Hinzufügen eines Säulendiagramms](../../2014/tutorials/media/tutorial-addcolumnchart.png "Hinzufügen eines Säulendiagramms")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-344">![Add column chart](../../2014/tutorials/media/tutorial-addcolumnchart.png "Add column chart")</span></span>

10. <span data-ttu-id="dcd0b-345">Klicken Sie mit der rechten Maustaste auf den Diagramm Titel, und klicken Sie auf **Titel Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-345">Right-click the chart title and then click **Title Properties**.</span></span>

11. <span data-ttu-id="dcd0b-346">Geben Sie im Dialogfeld **Diagrammtiteleigenschaften** im Titeltext Folgendes ein: **Produktverkäufe**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-346">In the **Chart Title Properties** dialog box, in Title text, type: **Product Sales**.</span></span>

12. <span data-ttu-id="dcd0b-347">Klicken Sie auf die Registerkarte **Schriftart** , und klicken Sie in der Liste **Größe** auf **10 pt**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-347">Click the **Font** tab, and in the **Size** list click **10pt**, and then click **OK**.</span></span>

13. <span data-ttu-id="dcd0b-348">Klicken Sie im Säulendiagramm mit der rechten Maustaste auf den Titel der vertikalen Achse, und deaktivieren Sie anschließend das Kontrollkästchen **Achsentitel anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-348">In the column chart, right click the vertical axis, and then deselect **Show Axis Title**.</span></span>

14. <span data-ttu-id="dcd0b-349">Wiederholen Sie Schritt 13 für den Titel der horizontalen Achse.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-349">Repeat step 13 for the horizontal axis.</span></span>

15. <span data-ttu-id="dcd0b-350">Klicken Sie mit der rechten Maustaste auf die Legende, und klicken Sie dann auf **Legende löschen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-350">Right click the legend, and then click **Delete Legend**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-351">Durch Entfernen der Achsentitel und der Legende wird die Lesbarkeit des Diagramms bei geringer Größe verbessert.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-351">Removing axis titles and the legend makes the chart more readable when it is a small size.</span></span>

 <span data-ttu-id="dcd0b-352">![Ändern von Diagrammtiteln und Entfernen des Achsentitels](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Ändern von Diagrammtiteln und Entfernen des Achsentitels")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-352">![Change chart titles and remove axis title](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Change chart titles and remove axis title")</span></span>

#### <a name="to-verify-the-charts-are-inside-the-rectangle"></a><span data-ttu-id="dcd0b-353">So überprüfen Sie, ob die Diagramme im Rechteck enthalten sind</span><span class="sxs-lookup"><span data-stu-id="dcd0b-353">To verify the charts are inside the rectangle</span></span>

1.  <span data-ttu-id="dcd0b-354">Klicken Sie auf das Rechteck, das Sie zuvor in dieser Lektion hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-354">Click the rectangle you added earlier in this lesson.</span></span>

     <span data-ttu-id="dcd0b-355">Im Eigenschaftenbereich zeigt die `Name`-Eigenschaft den Namen des Rechtecks an.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-355">In the Properties pane, the `Name` property displays the name of the rectangle.</span></span>

     <span data-ttu-id="dcd0b-356">![Name des Rechtecks](../../2014/tutorials/media/tutorial-rectanglename.png "Name des Rechtecks")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-356">![Name of rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Name of rectangle")</span></span>

2.  <span data-ttu-id="dcd0b-357">Klicken Sie auf das Kreisdiagramm.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-357">Click the pie chart.</span></span>

3.  <span data-ttu-id="dcd0b-358">Überprüfen Sie im **Eigenschaften** Bereich, ob die- `Parent` Eigenschaft den Namen des Rechtecks enthält.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-358">In the **Properties** pane, verify that the `Parent` property contains the name of the rectangle.</span></span>

     <span data-ttu-id="dcd0b-359">![Übergeordnete Eigenschaft für Kreisdiagramm](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Übergeordnete Eigenschaft für Kreisdiagramm")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-359">![Parent property for pie chart](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Parent property for pie chart")</span></span>

4.  <span data-ttu-id="dcd0b-360">Klicken Sie auf das Säulendiagramm, und wiederholen Sie die Schritte 2 und 3.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-360">Click the column chart and repeat steps 2 and 3.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-361">Wenn die Diagramme nicht im Rechteck enthalten sind, werden die Diagramme im gerenderten Bericht nicht zusammen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-361">If the charts are not inside the rectangle, the rendered report does not display the charts together.</span></span>

#### <a name="to-make-the-charts-the-same-size"></a><span data-ttu-id="dcd0b-362">So legen Sie für die Diagramme die gleiche Größe fest</span><span class="sxs-lookup"><span data-stu-id="dcd0b-362">To make the charts the same size</span></span>

1.  <span data-ttu-id="dcd0b-363">Klicken Sie auf das Kreisdiagramm, drücken Sie die STRG-TASTE, und klicken Sie anschließend auf das Säulendiagramm.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-363">Click the pie chart, press the Ctrl key, and then click the column chart.</span></span>

2.  <span data-ttu-id="dcd0b-364">Wenn beide Diagramme markiert sind, klicken Sie mit der rechten Maustaste darauf, zeigen Sie auf **Layout**, und klicken Sie anschließend auf **Breite angleichen**.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-364">With both charts selected, right-click, point to **Layout**, and then click **Make Same Width**.</span></span>

     <span data-ttu-id="dcd0b-365">![Einstellen derselben Diagrammbreiten](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Einstellen derselben Diagrammbreiten")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-365">![Make chart widths the same](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Make chart widths the same")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dcd0b-366">Das Element, auf das Sie zuerst klicken, bestimmt die Breite aller ausgewählten Elemente.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-366">The item you click first determines the width of all the selected items.</span></span>

3.  <span data-ttu-id="dcd0b-367">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-367">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="dcd0b-368">Im Bericht werden nun Zusammenfassungsumsatzdaten in Kreis- und Säulendiagrammen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-368">The report now displays summary sales data in pie and column charts.</span></span>

 <span data-ttu-id="dcd0b-369">![SSRS-Lernprogramm, formfreien Bericht](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS-Lernprogramm, formfreien Bericht")</span><span class="sxs-lookup"><span data-stu-id="dcd0b-369">![SSRS tutorial, free form report](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS tutorial, free form report")</span></span>

## <a name="more-information"></a><span data-ttu-id="dcd0b-370">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dcd0b-370">More Information</span></span>
 <span data-ttu-id="dcd0b-371">Weitere Informationen zu Listen finden Sie unter [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Listet &#40;Berichts-Generator und SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix-Datenbereichs Bereiche &#40;Berichts-Generator und SSRS-&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)und [Zellen, Zeilen und Spalten des Tablix-Datenbereichs &#40;Berichts-Generator&#41; und SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dcd0b-371">For more information about lists, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="dcd0b-372">Weitere Informationen zu Abfrage-Designern finden Sie unter [Abfrage-Designer (Berichts-Generator)](../../2014/reporting-services/query-designers-report-builder.md) und [Benutzeroberfläche des textbasierten Abfrage-Designers (Berichts-Generator)](report-data/text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dcd0b-372">For more information about query designers, see [Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) and [Text-based Query Designer User Interface &#40;Report Builder&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcd0b-373">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dcd0b-373">See Also</span></span>
 <span data-ttu-id="dcd0b-374">Lernprogramme [&#40;Berichts-Generator&#41;](report-builder-tutorials.md) [Berichts-Generator in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="dcd0b-374">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span></span>


