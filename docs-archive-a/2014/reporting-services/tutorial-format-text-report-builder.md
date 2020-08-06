---
title: 'Tutorial: Formatieren von Text (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 67d8513e-8a70-464b-b87f-e91d010cfd82
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c96b500f8aa30b77c78f75ccd1342398fd44eb2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722433"
---
# <a name="tutorial-format-text-report-builder"></a><span data-ttu-id="b9e6c-102">Lernprogramm: Formatieren von Text (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="b9e6c-102">Tutorial: Format Text (Report Builder)</span></span>
  <span data-ttu-id="b9e6c-103">In diesem Tutorial können Sie die Formatierung von Text auf verschiedene Weise üben.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-103">In this tutorial, you can practice formatting text in various ways.</span></span> <span data-ttu-id="b9e6c-104">Nach dem Einrichten des leeren Berichts mit der Datenquelle und dem Dataset können Sie die Schritte auswählen, mit denen Sie sich vertraut machen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-104">After you set up the blank report with the data source and dataset, you can pick and choose the steps that you want to explore.</span></span>  
  
 <span data-ttu-id="b9e6c-105">Die folgende Abbildung zeigt einen Bericht, der mit dem Bericht vergleichbar ist, den Sie erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-105">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="b9e6c-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span><span class="sxs-lookup"><span data-stu-id="b9e6c-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span></span>  
  
 <span data-ttu-id="b9e6c-107">In einem Schritt machen Sie absichtlich einen Fehler, um dadurch erkennen zu können, warum es sich um einen Fehler handelt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-107">In one step, you make a mistake on purpose so you can see why it is a mistake.</span></span> <span data-ttu-id="b9e6c-108">Anschließend beheben Sie den Fehler, um den gewünschten Effekt zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-108">Then you correct the mistake to achieve the desired effect.</span></span>  
  
 <span data-ttu-id="b9e6c-109">Eine erweiterte Version des Berichts, den Sie in diesem Lernprogramm erstellen, ist als [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Berichts-Generator-Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-109">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="b9e6c-110">Weitere Informationen zum Herunterladen dieses Beispiel Berichts und anderer Informationen finden Sie unter [Berichts-Generator-Beispiel Berichte](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="b9e6c-110">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="b9e6c-111">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="b9e6c-111">What You Will Learn</span></span>  
  
### <a name="set-up-the-report"></a><span data-ttu-id="b9e6c-112">Einrichten des Berichts</span><span class="sxs-lookup"><span data-stu-id="b9e6c-112">Set Up the Report</span></span>  
 1. [<span data-ttu-id="b9e6c-113">Erstellen eines leeren Berichts mit einer Datenquelle und einem DataSet</span><span class="sxs-lookup"><span data-stu-id="b9e6c-113">Create a Blank Report with a Data Source and Dataset</span></span>](#CreateReport)  
  
 2. [<span data-ttu-id="b9e6c-114">Hinzufügen eines Felds zur Berichtsentwurfsoberfläche (falsch, dann ordnungsgemäß)</span><span class="sxs-lookup"><span data-stu-id="b9e6c-114">Add a Field to the Report Design Surface (Incorrectly, then Correctly)</span></span>](#AddField)  
  
 3. [<span data-ttu-id="b9e6c-115">Fügen Sie dem Bericht eine Tabelle hinzu Designoberfläche</span><span class="sxs-lookup"><span data-stu-id="b9e6c-115">Add a Table to the Report Design Surface</span></span>](#AddTable)  
  
### <a name="pick-and-choose"></a><span data-ttu-id="b9e6c-116">Auswählen</span><span class="sxs-lookup"><span data-stu-id="b9e6c-116">Pick and Choose</span></span>  
 [<span data-ttu-id="b9e6c-117">Hinzufügen eines Links zum Bericht</span><span class="sxs-lookup"><span data-stu-id="b9e6c-117">Add a Hyperlink to the Report</span></span>](#AddHyperlink)  
  
 [<span data-ttu-id="b9e6c-118">Drehen von Text im Bericht</span><span class="sxs-lookup"><span data-stu-id="b9e6c-118">Rotate Text in the Report</span></span>](#RotateText)  
  
 [<span data-ttu-id="b9e6c-119">Anzeigen von Text mit HTML-Formatierung</span><span class="sxs-lookup"><span data-stu-id="b9e6c-119">Displaying Text with HTML Formatting</span></span>](#FormatHTML)  
  
 [<span data-ttu-id="b9e6c-120">Formatieren von Währungen</span><span class="sxs-lookup"><span data-stu-id="b9e6c-120">Format Currency</span></span>](#FormatCurrency)  
  
 [<span data-ttu-id="b9e6c-121">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="b9e6c-121">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="b9e6c-122">Ungefähre Dauer dieses Lernprogramms: 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9e6c-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b9e6c-123">Requirements</span></span>  
 <span data-ttu-id="b9e6c-124">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b9e6c-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="create-a-blank-report-with-a-data-source-and-dataset"></a><a name="CreateReport"></a><span data-ttu-id="b9e6c-125">Erstellen eines leeren Berichts mit einer Datenquelle und einem DataSet</span><span class="sxs-lookup"><span data-stu-id="b9e6c-125">Create a Blank Report with a Data Source and Dataset</span></span>  
  
#### <a name="to-create-a-blank-report"></a><span data-ttu-id="b9e6c-126">So erstellen Sie einen leeren Bericht</span><span class="sxs-lookup"><span data-stu-id="b9e6c-126">To create a blank report</span></span>  
  
1.  <span data-ttu-id="b9e6c-127">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-127">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9e6c-128">Das Dialogfeld **Erste Schritte** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-128">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="b9e6c-129">Wenn dies nicht der Fall ist, klicken Sie auf der Schaltfläche des Berichts-Generators auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-129">If it does not, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="b9e6c-130">Vergewissern Sie sich links im Dialogfeld **Erste Schritte** , dass die Option **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-130">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="b9e6c-131">Klicken Sie im rechten Bereich auf **Leerer Bericht**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-131">In the right pane, click **Blank Report**.</span></span>  
  
#### <a name="to-create-a-data-source"></a><span data-ttu-id="b9e6c-132">So erstellen Sie eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="b9e6c-132">To create a data source</span></span>  
  
1.  <span data-ttu-id="b9e6c-133">Klicken Sie im Berichtsdatenbereich auf **Neu**, und klicken Sie dann auf **Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-133">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="b9e6c-134">Geben Sie im Feld **Name** Folgendes ein: **TextDataSource**</span><span class="sxs-lookup"><span data-stu-id="b9e6c-134">In the **Name** box, type: **TextDataSource**</span></span>  
  
3.  <span data-ttu-id="b9e6c-135">Klicken Sie auf **In Bericht eingebettete Verbindung verwenden**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-135">Click **Use a connection embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="b9e6c-136">Vergewissern Sie sich, dass der Verbindungstyp Microsoft SQL Server ist, und geben Sie dann im Feld **Verbindungs Zeichenfolge** Folgendes ein: \*\*Datenquelle = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="b9e6c-136">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9e6c-137">Der Ausdruck \<servername>, z.B. „Report001“, bezeichnet einen Computer, auf dem eine Instanz der SQL Server-Datenbank-Engine installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-137">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="b9e6c-138">Für dieses Lernprogramm sind keine bestimmten Daten erforderlich; es wird lediglich eine Verbindung mit einer [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] -Datenbank benötigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-138">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="b9e6c-139">Wenn unter **Datenquellenverbindungen**bereits eine Datenquellenverbindung aufgeführt ist, können Sie sie auswählen und zum nächsten Schritt übergehen, nämlich „So erstellen Sie ein Dataset“.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-139">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to the next procedure, "To create a dataset."</span></span> <span data-ttu-id="b9e6c-140">Weitere Informationen finden Sie unter [Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b9e6c-140">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-create-a-dataset"></a><span data-ttu-id="b9e6c-141">So erstellen Sie ein Dataset</span><span class="sxs-lookup"><span data-stu-id="b9e6c-141">To create a dataset</span></span>  
  
1.  <span data-ttu-id="b9e6c-142">Klicken Sie im Berichtsdatenbereich auf **Neu**und anschließend auf **Dataset**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-142">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>  
  
2.  <span data-ttu-id="b9e6c-143">Vergewissern Sie sich, dass die Datenquelle **TextDataSource**ist.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-143">Verify that the data source is **TextDataSource**.</span></span>  
  
3.  <span data-ttu-id="b9e6c-144">Geben Sie im Feld **Name** Folgendes ein: **TextDataset**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-144">In the **Name** box, type: **TextDataset.**</span></span>  
  
4.  <span data-ttu-id="b9e6c-145">Überprüfen Sie, ob der Abfragetyp **Text** ausgewählt ist, und klicken Sie anschließend auf **Abfrage-Designer**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-145">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>  
  
5.  <span data-ttu-id="b9e6c-146">Klicken Sie auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-146">Click **Edit as Text**.</span></span>  
  
6.  <span data-ttu-id="b9e6c-147">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="b9e6c-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    ```  
  
7.  <span data-ttu-id="b9e6c-148">Klicken Sie auf „Ausführen“ (**!**), um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-148">Click Run (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="b9e6c-149">Bei den Abfrageergebnissen handelt es sich um die Daten, die im Bericht angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-149">The query results are the data available to display in your report.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="add-a-field-to-the-report-design-surface"></a><a name="AddField"></a><span data-ttu-id="b9e6c-150">Fügen Sie dem Bericht ein Feld hinzu Designoberfläche</span><span class="sxs-lookup"><span data-stu-id="b9e6c-150">Add a Field to the Report Design Surface</span></span>  
 <span data-ttu-id="b9e6c-151">Wenn Sie möchten, dass ein Feld aus dem Dataset in einem Bericht erscheint, werden Sie möglicherweise zunächst versuchen, das Feld direkt auf die Entwurfsoberfläche zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-151">If you want a field from your dataset to appear in a report, your first impulse may be to drag it directly to the design surface.</span></span> <span data-ttu-id="b9e6c-152">Diese Übung zeigt auf, warum dies nicht funktioniert und wie stattdessen vorzugehen ist.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-152">This exercise points out why that doesn't work and what to do instead.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-wrong-result"></a><span data-ttu-id="b9e6c-153">So fügen Sie dem Bericht ein Feld hinzu (und erhalten das falsche Ergebnis)</span><span class="sxs-lookup"><span data-stu-id="b9e6c-153">To add a field to the report (and get the wrong result)</span></span>  
  
1.  <span data-ttu-id="b9e6c-154">Ziehen Sie das Feld **FullName** aus dem Berichtsdatenbereich auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-154">Drag the **FullName** field from the Report Data pane to the design surface.</span></span>  
  
     <span data-ttu-id="b9e6c-155">Der Berichts-Generator erstellt ein Textfeld mit einem darin enthaltenen Ausdruck, der als \<Expr>dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-155">Report Builder creates a text box with an expression in it, represented as \<Expr>.</span></span>  
  
2.  <span data-ttu-id="b9e6c-156">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-156">Click **Run**.</span></span>  
  
     <span data-ttu-id="b9e6c-157">Beachten Sie, dass es nur einen Datensatz, **Fernando Ross**, gibt, der alphabetisch den ersten Datensatz in der Abfrage ist.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-157">Note that there is just one record, **Fernando Ross**, which is alphabetically the first record in the query.</span></span> <span data-ttu-id="b9e6c-158">Die anderen Datensätze in diesem Feld werden nicht erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-158">The field does not repeat to show the other records in that field.</span></span>  
  
3.  <span data-ttu-id="b9e6c-159">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-159">Click **Design** to return to design view.</span></span>  
  
4.  <span data-ttu-id="b9e6c-160">Wählen Sie den Ausdruck \<Expr> im Textfeld aus.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-160">Select the expression \<Expr> in the text box.</span></span>  
  
5.  <span data-ttu-id="b9e6c-161">Im Eigenschaftenbereich für die **Value** -Eigenschaft wird Folgendes angezeigt (wenn der Bereich nicht angezeigt wird, wählen Sie auf der Registerkarte **Ansicht** die Option **Eigenschaften**aus):</span><span class="sxs-lookup"><span data-stu-id="b9e6c-161">In the Properties pane, for the **Value** property, you see the following (if you don't see the Properties pane, on the **View** tab, check **Properties**):</span></span>  
  
    ```  
    =First(Fields!FullName.Value, "TextDataSet")  
    ```  
  
     <span data-ttu-id="b9e6c-162">Die `First` -Funktion dient dazu, dass nur der erste Wert in einem Feld abgerufen wird, und genau dies war auch der Fall.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-162">The `First` function is designed to retrieve only the first value in a field, and that is what it has done.</span></span>  
  
     <span data-ttu-id="b9e6c-163">Durch das direkte Ziehen des Felds auf die Entwurfsoberfläche wurde ein Textfeld erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-163">Dragging the field directly to the design surface created a text box.</span></span> <span data-ttu-id="b9e6c-164">Textfelder an sich sind keine Datenbereiche, weshalb darin keine Daten aus einem Berichtsdataset angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-164">Text boxes by themselves are not data regions, so they do not display data from a report dataset.</span></span> <span data-ttu-id="b9e6c-165">In Textfeldern in Datenbereichen, z. B. Tabellen, Matrizen und Listen werden hingegen Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-165">Text boxes in data regions, such as tables, matrices, and lists, do display data.</span></span>  
  
6.  <span data-ttu-id="b9e6c-166">Wählen Sie das Textfeld aus (wenn der Ausdruck ausgewählt wurde, drücken Sie ESC, um das Textfeld auszuwählen), und drücken Sie die ENTF-TASTE.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-166">Select the text box (if you have the expression selected, press ESC to select the text box), and press the DELETE key.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-right-result"></a><span data-ttu-id="b9e6c-167">So fügen Sie dem Bericht ein Feld hinzu (und erhalten das richtige Ergebnis)</span><span class="sxs-lookup"><span data-stu-id="b9e6c-167">To add a field to the report (and get the right result)</span></span>  
  
1.  <span data-ttu-id="b9e6c-168">Klicken Sie auf der Registerkarte **Einfügen** des Menübands im Bereich **Datenbereiche** auf **Liste**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-168">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List**.</span></span> <span data-ttu-id="b9e6c-169">Klicken Sie auf die Entwurfsoberfläche, und ziehen Sie anschließend den Mauszeiger, um ein Feld mit einer Breite von ungefähr fünf Zentimetern und einer Höhe von ca. 2,5 Zentimetern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-169">Click the design surface, and then drag to create a box that about two inches wide and one inch tall.</span></span>  
  
2.  <span data-ttu-id="b9e6c-170">Ziehen Sie das Feld **FullName** aus dem Berichtsdatenbereich in das Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-170">Drag the **FullName** field from the Report Data pane to the list box.</span></span>  
  
     <span data-ttu-id="b9e6c-171">Dieses Mal erstellt der Berichts-Generator ein Textfeld mit dem Ausdruck `[FullName]` darin.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-171">This time Report Builder creates a text box with the expression `[FullName]` in it.</span></span>  
  
3.  <span data-ttu-id="b9e6c-172">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-172">Click **Run**.</span></span>  
  
     <span data-ttu-id="b9e6c-173">Dieses Mal werden im Feld alle Datensätze in der Abfrage erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-173">Note that this time the box repeats to show all the records in the query.</span></span>  
  
4.  <span data-ttu-id="b9e6c-174">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-174">Click **Design** to return to design view.</span></span>  
  
5.  <span data-ttu-id="b9e6c-175">Wählen Sie den Ausdruck im Textfeld aus.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-175">Select the expression in the text box.</span></span>  
  
6.  <span data-ttu-id="b9e6c-176">Im Eigenschaftenbereich für die **Value** -Eigenschaft wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b9e6c-176">In the Properties pane, for the **Value** property, you see the following:</span></span>  
  
    ```  
    =Fields!FullName.Value  
    ```  
  
     <span data-ttu-id="b9e6c-177">Durch Ziehen des Textfelds in den Listendatenbereich werden die im Dataset enthaltenen Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-177">By dragging the text box to the list data region, you display the data that is in the dataset.</span></span>  
  
7.  <span data-ttu-id="b9e6c-178">Wählen Sie das Listenfeld aus, und drücken Sie die ENTF-TASTE.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-178">Select the list box and press the DELETE key.</span></span>  
  
##  <a name="add-a-table-to-the-report-design-surface"></a><a name="AddTable"></a><span data-ttu-id="b9e6c-179">Fügen Sie dem Bericht eine Tabelle hinzu Designoberfläche</span><span class="sxs-lookup"><span data-stu-id="b9e6c-179">Add a Table to the Report Design Surface</span></span>  
 <span data-ttu-id="b9e6c-180">Erstellen Sie diese Tabelle, damit Sie Hyperlinks und den gedrehten Text an einer bestimmten Stelle ablegen können.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-180">Create this table so that you'll have a place to put hyperlinks and rotated text.</span></span>  
  
#### <a name="to-add-a-table-to-the-report"></a><span data-ttu-id="b9e6c-181">So fügen Sie dem Bericht eine Tabelle hinzu</span><span class="sxs-lookup"><span data-stu-id="b9e6c-181">To add a table to the report</span></span>  
  
1.  <span data-ttu-id="b9e6c-182">Klicken Sie im Menü **Einfügen** auf **Tabelle**, und klicken Sie dann auf **Tabellen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-182">On the **Insert** menu, click **Table**, and then click **Table Wizard**.</span></span>  
  
2.  <span data-ttu-id="b9e6c-183">Klicken Sie auf der Seite **Dataset auswählen** des Assistenten für neue Tabellen oder Matrizen auf **vorhandenes Dataset in diesem Bericht oder einem freigegebenen Dataset auswählen**, und klicken Sie dann auf **textdataset (in diesem Bericht)**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-183">On the **Choose a dataset** page of the New Table or Matrix wizard, click **Choose an existing dataset in this report or a shared dataset**, and click **TextDataset (in this Report)**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="b9e6c-184">Ziehen Sie auf der Seite **Felder anordnen** die Felder **Territory**, **Linktext**und **Product** nach **Zeilen Gruppen**, ziehen Sie das Feld **Sales** in **Werte**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-184">On the **Arrange fields** page, drag the **Territory**, **LinkText**, and **Product** fields to **Row groups**, drag the **Sales** field to **Values**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="b9e6c-185">Deaktivieren Sie auf der Seite **Layout auswählen** das Kontrollkästchen **Gruppen erweitern/** reduzieren, damit die gesamte Tabelle angezeigt wird, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-185">On the **Choose the layout** page, clear the **Expand/collapse groups** check box so you can see the whole table, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="b9e6c-186">Klicken Sie auf der Seite Format **auswählen** auf **Slate**, und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-186">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="b9e6c-187">Ziehen Sie die Tabelle, damit sie sich unter dem Titelblock befindet.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-187">Drag the table so it is below the title block.</span></span>  
  
7.  <span data-ttu-id="b9e6c-188">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-188">Click **Run**.</span></span>  
  
     <span data-ttu-id="b9e6c-189">Die Tabelle sieht einwandfrei aus, enthält jedoch zwei Ergebniszeilen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-189">The table looks OK, but it has two Total rows.</span></span> <span data-ttu-id="b9e6c-190">Das **Linktext** -Feld benötigt keine Gesamt Zeile.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-190">The **LinkText** field doesn't need a Total row.</span></span>  
  
8.  <span data-ttu-id="b9e6c-191">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-191">Click **Design** to return to design view.</span></span>  
  
9. <span data-ttu-id="b9e6c-192">Klicken Sie mit der rechten Maustaste auf das Textfeld mit `[LinkText]` , und klicken Sie dann auf **Zellen teilen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-192">Right-click the text box that contains `[LinkText]`, and click **Split Cells**.</span></span>  
  
10. <span data-ttu-id="b9e6c-193">Wählen Sie die leere Zelle unterhalb der `[LinkText]` Zelle aus, halten Sie die UMSCHALTTASTE gedrückt, und wählen Sie die zwei Zellen rechts aus: die **gesamte** Zelle in der **Product** -Spalte und die- `[Sum(Sales)]` Zelle in der Spalte **Sales** .</span><span class="sxs-lookup"><span data-stu-id="b9e6c-193">Select the empty cell below the `[LinkText]` cell, and then hold down the SHIFT key and select the two cells to its right: the **Total** cell in the **Product** column and the `[Sum(Sales)]` cell in the **Sales** column.</span></span>  
  
11. <span data-ttu-id="b9e6c-194">Wenn diese drei Zellen ausgewählt sind, klicken Sie mit der rechten Maustaste auf eine der Zellen, und klicken Sie auf **Zeile löschen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-194">With those three cells selected, right-click one of those cells and click **Delete Row**.</span></span>  
  
12. <span data-ttu-id="b9e6c-195">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-195">Click **Run**.</span></span>  
  
##  <a name="add-a-hyperlink-to-the-report"></a><a name="AddHyperlink"></a><span data-ttu-id="b9e6c-196">Hinzufügen eines Links zum Bericht</span><span class="sxs-lookup"><span data-stu-id="b9e6c-196">Add a Hyperlink to the Report</span></span>  
 <span data-ttu-id="b9e6c-197">In diesem Abschnitt fügen Sie dem Text in der Tabelle aus dem vorherigen Abschnitt einen Link hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-197">In this section, you add a hyperlink to text in the table from the previous section.</span></span>  
  
#### <a name="to-add-a-hyperlink-to-the-report"></a><span data-ttu-id="b9e6c-198">So fügen Sie dem Bericht einen Link hinzu</span><span class="sxs-lookup"><span data-stu-id="b9e6c-198">To add a hyperlink to the report</span></span>  
  
1.  <span data-ttu-id="b9e6c-199">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-199">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="b9e6c-200">Klicken Sie mit der rechten Maustaste auf die Zelle, die `[LinkText]`enthält, und klicken Sie auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-200">Right-click in the cell containing `[LinkText]`, and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="b9e6c-201">Klicken Sie im Feld **Text Feldeigenschaften** auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-201">In the **Text Box Properties** box, click **Action**.</span></span>  
  
4.  <span data-ttu-id="b9e6c-202">Klicken Sie auf **Gehe zu URL**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-202">Click **Go to URL**.</span></span>  
  
5.  <span data-ttu-id="b9e6c-203">Klicken Sie im Feld **URL auswählen** auf **[URL]**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-203">In the **Select URL** box, click **[URL]**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b9e6c-204">Das Aussehen des Texts unterscheidet sich nicht.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-204">Note that the text does not look any different.</span></span> <span data-ttu-id="b9e6c-205">Es muss jedoch dem des Linktexts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-205">You need to make it look like link text.</span></span>  
  
7.  <span data-ttu-id="b9e6c-206">Wählen Sie `[LinkText]`aus.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-206">Select `[LinkText]`.</span></span>  
  
8.  <span data-ttu-id="b9e6c-207">Klicken Sie im Abschnitt **Schriftart** der Registerkarte **Home** auf die Schaltfläche unter **streichen** , klicken Sie auf den Dropdown Pfeil neben der Schaltfläche **Farbe** , und klicken Sie dann auf **blau**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-207">In the **Font** section of the **Home** tab, click the **Underline** button, and then click the drop-down arrow next to the **Color** button, and click **Blue**.</span></span>  
  
9. <span data-ttu-id="b9e6c-208">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-208">Click **Run**.</span></span>  
  
     <span data-ttu-id="b9e6c-209">Der Text sieht nun wie ein Link aus.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-209">The text now looks like a link.</span></span>  
  
10. <span data-ttu-id="b9e6c-210">Klicken Sie auf einen Link.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-210">Click a link.</span></span> <span data-ttu-id="b9e6c-211">Wenn der Computer mit dem Internet verbunden ist, wird vom Browser ein Hilfethema zu Berichts-Generator geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-211">If the computer is connected to the Internet, a browser will open to a Report Builder Help topic.</span></span>  
  
##  <a name="rotate-text-in-the-report"></a><a name="RotateText"></a><span data-ttu-id="b9e6c-212">Drehen von Text im Bericht</span><span class="sxs-lookup"><span data-stu-id="b9e6c-212">Rotate Text in the Report</span></span>  
 <span data-ttu-id="b9e6c-213">In diesem Abschnitt drehen Sie Text in der Tabelle aus den vorherigen Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-213">In this section, you rotate some of the text in the table from the previous sections.</span></span>  
  
#### <a name="to-rotate-text"></a><span data-ttu-id="b9e6c-214">So drehen Sie Text</span><span class="sxs-lookup"><span data-stu-id="b9e6c-214">To rotate text</span></span>  
  
1.  <span data-ttu-id="b9e6c-215">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-215">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="b9e6c-216">Klicken Sie in die Zelle, die enthält. `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="b9e6c-216">Click in the cell containing `[Territory].`</span></span>  
  
3.  <span data-ttu-id="b9e6c-217">Klicken Sie auf der Registerkarte **Stamm** im Abschnitt **Schriftart** auf die Schaltfläche **Fett** .</span><span class="sxs-lookup"><span data-stu-id="b9e6c-217">On the **Home** tab in the **Font** section, click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="b9e6c-218">Wenn der Eigenschaftenbereich nicht geöffnet ist, aktivieren Sie auf der Registerkarte **Ansicht** das Kontrollkästchen **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="b9e6c-218">If the Properties pane is not open, on the **View** tab, select the **Properties** check box.</span></span>  
  
5.  <span data-ttu-id="b9e6c-219">Suchen Sie im Bereich "Eigenschaften" die Eigenschaft "Schreibmodus".</span><span class="sxs-lookup"><span data-stu-id="b9e6c-219">Locate the WritingMode property in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9e6c-220">Wenn die Eigenschaften im Eigenschaftenbereich in Kategorien angeordnet sind, befindet sich WritingMode in der Kategorie **Lokalisierung** .</span><span class="sxs-lookup"><span data-stu-id="b9e6c-220">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span> <span data-ttu-id="b9e6c-221">Stellen Sie sicher, dass Sie die Zelle und nicht den Text ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-221">Be sure you have selected the cell and not the text.</span></span> <span data-ttu-id="b9e6c-222">WritingMode ist eine Eigenschaft des Textfeldes, nicht des Texts.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-222">WritingMode is a property of the text box, not of the text.</span></span>  
  
6.  <span data-ttu-id="b9e6c-223">Klicken Sie im Listenfeld auf **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-223">In the list box, click **Rotate270**.</span></span>  
  
7.  <span data-ttu-id="b9e6c-224">Klicken Sie auf der Registerkarte **Startseite** im Abschnitt **Absatz** auf die **Schaltflächen** **Mitte** und zentriert, um den Text sowohl vertikal als auch horizontal in der Mitte der Zelle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-224">On the **Home** tab in the **Paragraph** section, click the **Middle** and **Center** buttons to locate the text in the center of the cell both vertically and horizontally.</span></span>  
  
8.  <span data-ttu-id="b9e6c-225">Klicken Sie auf Ausführen (**!**).</span><span class="sxs-lookup"><span data-stu-id="b9e6c-225">Click Run (**!**).</span></span>  
  
 <span data-ttu-id="b9e6c-226">Nun verläuft der Text in der `[Territory]` -Zelle in den Zellen vertikal von unten nach oben.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-226">Now the text in the `[Territory]` cell runs vertically from the bottom to the top of the cells.</span></span>  
  
##  <a name="displaying-text-with-html-formatting"></a><a name="FormatHTML"></a><span data-ttu-id="b9e6c-227">Anzeigen von Text mit HTML-Formatierung</span><span class="sxs-lookup"><span data-stu-id="b9e6c-227">Displaying Text with HTML Formatting</span></span>  
  
#### <a name="to-display-text-formatted-as-html"></a><span data-ttu-id="b9e6c-228">So zeigen Sie als HTML formatierten Text an</span><span class="sxs-lookup"><span data-stu-id="b9e6c-228">To display text formatted as HTML</span></span>  
  
1.  <span data-ttu-id="b9e6c-229">Klicken Sie auf **Entwurf** , um zur Entwurfs Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-229">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="b9e6c-230">Klicken Sie auf der Registerkarte **Einfügen** auf **Textfeld**. Klicken Sie anschließend auf die Entwurfsoberfläche, und ziehen Sie den Mauszeiger, um unter der Tabelle ein Textfeld mit einer Breite von etwa zehn Zentimetern und einer Höhe von etwa 7,5 Zentimetern zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-230">On the **Insert** tab, click **Text Box**, and then on the design surface, click and drag to create a text box under the table, about four inches wide and three inches tall.</span></span>  
  
3.  <span data-ttu-id="b9e6c-231">Kopieren Sie diesen Text, und fügen Sie ihn in das Textfeld ein:</span><span class="sxs-lookup"><span data-stu-id="b9e6c-231">Copy this text and paste it into the text box:</span></span>  
  
    ```  
    <h4>Limitations of cascading style sheet attributes</h4>  
          <p>Only a basic set of <b>cascading style sheet (CSS)</b> attributes are defined:</p>  
          <ul><li>  
              text-align, text-indent  
            </li><li>  
              font-family, font-size  
            </li><li>  
              color  
            </li><li>  
              padding, padding-bottom, padding-top, padding-right, padding-left  
            </li><li>  
              font-weight  
            </li></ul>  
    ```  
  
4.  <span data-ttu-id="b9e6c-232">Wählen Sie den gesamten Text im Textfeld aus.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-232">Select all of the text in the text box.</span></span>  
  
     <span data-ttu-id="b9e6c-233">Dies ist eine Eigenschaft des Texts (nicht des Textfelds). Daher kann in einem Textfeld eine Mischung aus Nur-Text und Text, die HTML-Tags als Formatvorlagen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-233">This is a property of the text, not the text box, so in one text box you could have a mixture of plain text and text that uses HTML tags as styles.</span></span>  
  
5.  <span data-ttu-id="b9e6c-234">Klicken Sie mit der rechten Maustaste auf den gesamten ausgewählten Text und anschließend auf **Texteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-234">Right-click all of the selected text and click **Text Properties**.</span></span>  
  
6.  <span data-ttu-id="b9e6c-235">Klicken Sie auf der Seite **Allgemein** unter **Markuptyp**auf HTML **-HTML-Tags als Formate interpretieren**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-235">On the **General** page, under **Markup type**, click **HTML - Interpret HTML tags as styles**.</span></span>  
  
7.  <span data-ttu-id="b9e6c-236">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-236">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="b9e6c-237">Klicken Sie auf „Ausführen“ (**!**), um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-237">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="b9e6c-238">Der Text im Textfeld wird als Überschrift, Absatz und Aufzählung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-238">The text in the text box is displayed as a heading, paragraph, and bulleted list.</span></span>  
  
##  <a name="format-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="b9e6c-239">Formatieren von Währungen</span><span class="sxs-lookup"><span data-stu-id="b9e6c-239">Format Currency</span></span>  
  
#### <a name="to-format-numbers-as-currency"></a><span data-ttu-id="b9e6c-240">So formatieren Sie Zahlen als Währung</span><span class="sxs-lookup"><span data-stu-id="b9e6c-240">To format numbers as currency</span></span>  
  
1.  <span data-ttu-id="b9e6c-241">Klicken Sie auf **Entwurf** , um zur Entwurfs Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-241">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="b9e6c-242">Klicken Sie auf die oberste Tabellenzelle, die `[Sum(Sales)]`enthält, halten Sie die UMSCHALTTASTE gedrückt, und klicken Sie auf die unterste Tabellenzelle, die `[Sum(Sales)]`enthält.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-242">Click the top table cell that contains `[Sum(Sales)]`, hold down the SHIFT key, and click the bottom table cell that contains `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="b9e6c-243">Klicken Sie auf der Registerkarte **Stamm** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="b9e6c-243">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>  
  
4.  <span data-ttu-id="b9e6c-244">Optionale Klicken Sie auf der Registerkarte **Startseite** in der Gruppe **Zahl** auf die Schaltfläche **Platzhalter** Formate und dann auf **Beispiel Werte** , um zu sehen, wie die Zahlen formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-244">(Optional) On the **Home** tab, in the **Number** group, click the **Placeholder Styles** button and click **Sample Values** to see how the numbers will be formatted.</span></span>  
  
5.  <span data-ttu-id="b9e6c-245">(Optional) Klicken Sie auf der Registerkarte **Stamm** in der Gruppe **Zahl** zweimal auf die Schaltfläche **Dezimalstellen verringern** , um volle Dollarbeträge ohne Centangaben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-245">(Optional) On the **Home** tab, in the **Number** group, click the **Decrease Decimals** button twice to display dollar figures with no cents.</span></span>  
  
6.  <span data-ttu-id="b9e6c-246">Klicken Sie auf „Ausführen“ (**!**), um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-246">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="b9e6c-247">Im Bericht werden nun formatierte Daten angezeigt, und die Lesbarkeit wurde verbessert.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-247">The report now displays formatted data and is easier to read.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="b9e6c-248">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="b9e6c-248">Save the Report</span></span>  
 <span data-ttu-id="b9e6c-249">Sie können Berichte auf einem Berichtsserver, in einer SharePoint-Bibliothek oder auf dem Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-249">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="b9e6c-250">Speichern Sie in diesem Lernprogramm den Bericht auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-250">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="b9e6c-251">Wenn Sie keinen Zugriff auf einen Berichtsserver besitzen, speichern Sie den Bericht auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-251">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="b9e6c-252">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="b9e6c-252">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="b9e6c-253">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-253">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="b9e6c-254">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-254">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="b9e6c-255">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-255">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="b9e6c-256">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-256">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="b9e6c-257">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-257">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="b9e6c-258">Ersetzen Sie in **Name**den Standardnamen durch einen Namen Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-258">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
5.  <span data-ttu-id="b9e6c-259">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-259">Click **Save**.</span></span>  
  
 <span data-ttu-id="b9e6c-260">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-260">The report is saved to the report server.</span></span> <span data-ttu-id="b9e6c-261">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-261">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="b9e6c-262">So speichern Sie den Bericht auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="b9e6c-262">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="b9e6c-263">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-263">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="b9e6c-264">Klicken Sie auf **Desktop**, **Meine Dokumente**oder **Arbeitsplatz**, und navigieren Sie anschließend zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-264">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="b9e6c-265">Ersetzen Sie in **Name**den Standardnamen durch einen Namen Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-265">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
4.  <span data-ttu-id="b9e6c-266">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-266">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b9e6c-267">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b9e6c-267">Next Steps</span></span>  
 <span data-ttu-id="b9e6c-268">Es gibt viele Methoden zum Formatieren von Text in Berichts-Generator [Tutorial: Erstellen eines frei Form Berichts &#40;Berichts-Generator&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) enthält weitere Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b9e6c-268">There are many ways to format text in Report Builder [Tutorial: Creating a Free Form Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contains more examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e6c-269">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9e6c-269">See Also</span></span>  
 <span data-ttu-id="b9e6c-270">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="b9e6c-270">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="b9e6c-271">[Formatieren von Berichts Elementen &#40;Berichts-Generator und SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9e6c-271">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b9e6c-272">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b9e6c-272">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
