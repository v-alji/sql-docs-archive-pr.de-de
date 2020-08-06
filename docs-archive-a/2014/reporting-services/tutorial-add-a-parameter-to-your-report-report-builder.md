---
title: 'Tutorial: Hinzufügen eines Parameters zum Bericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eab34ec4-b3ad-4a76-95cc-07b2f75ee6d7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dff41066a2d505ab53b17a10fb3da9b6cb17130f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720965"
---
# <a name="tutorial-add-a-parameter-to-your-report-report-builder"></a><span data-ttu-id="79289-102">Lernprogramm: Hinzufügen eines Parameters zum Bericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="79289-102">Tutorial: Add a Parameter to Your Report (Report Builder)</span></span>
  <span data-ttu-id="79289-103">Fügen Sie dem Bericht einen Parameter hinzu, um Benutzern das Filtern von Berichtsdaten aus der Datenquelle oder im Bericht zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="79289-103">Add a parameter to your report to let users filter report data from the data source or in the report.</span></span> <span data-ttu-id="79289-104">Berichtsparameter werden automatisch für jeden Abfrageparameter erstellt, den Sie in eine Datasetabfrage einschließen.</span><span class="sxs-lookup"><span data-stu-id="79289-104">Report parameters are created automatically for each query parameter that you include in a dataset query.</span></span> <span data-ttu-id="79289-105">Der Parameterdatentyp bestimmt, wie der Parameter auf der Symbolleiste der Berichtsansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="79289-105">The parameter data type determines how it appears on the report view toolbar.</span></span>  
  
 <span data-ttu-id="79289-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span><span class="sxs-lookup"><span data-stu-id="79289-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="79289-107">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="79289-107">What You Will Learn</span></span>  
 <span data-ttu-id="79289-108">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="79289-108">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="79289-109">Erstellen eines Matrixberichts und eines Datasets mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="79289-109">Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="79289-110">Organisieren von Daten und Auswählen des Layouts und Formats mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="79289-110">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="79289-111">Hinzufügen eines Abfrageparameters zum Erstellen eines Berichtsparameters</span><span class="sxs-lookup"><span data-stu-id="79289-111">Add a Query Parameter to Create a Report Parameter</span></span>](#Query)  
  
4.  [<span data-ttu-id="79289-112">Ändern des Standarddatentyps und anderer Eigenschaften für einen Berichtsparameter</span><span class="sxs-lookup"><span data-stu-id="79289-112">Change Default Data Type and Other Properties for a Report Parameter</span></span>](#ChangeDefaultProperties)  
  
    1.  [<span data-ttu-id="79289-113">Hinzufügen eines Datasets, um verfügbare Werte und Anzeigenamen anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="79289-113">Add a Dataset to Provide Available Values and Display Names</span></span>](#AddDataset)  
  
    2.  [<span data-ttu-id="79289-114">Angeben verfügbarer Werte zum Erstellen einer Dropdownliste von Werten</span><span class="sxs-lookup"><span data-stu-id="79289-114">Specify Available Values to Create a Drop-List of Values</span></span>](#AvailableValues)  
  
    3.  [<span data-ttu-id="79289-115">Angeben von Standardwerten zur automatischen Ausführung des Berichts</span><span class="sxs-lookup"><span data-stu-id="79289-115">Specify Default Values so the Report Runs Automatically</span></span>](#DefaultValues)  
  
    4.  [<span data-ttu-id="79289-116">Suchen nach Werten in einem Dataset mit Name-Wert-Paaren</span><span class="sxs-lookup"><span data-stu-id="79289-116">Look up a Value from a Dataset that has Name/Value Pairs</span></span>](#NameValue)  
  
5.  [<span data-ttu-id="79289-117">Anzeigen des ausgewählten Parameterwerts im Bericht</span><span class="sxs-lookup"><span data-stu-id="79289-117">Display the Selected Parameter Value in the Report</span></span>](#Expression)  
  
6.  [<span data-ttu-id="79289-118">Verwenden des Berichtsparameters in einem Filter</span><span class="sxs-lookup"><span data-stu-id="79289-118">Use the Report Parameter in a Filter</span></span>](#Filter)  
  
7.  [<span data-ttu-id="79289-119">Ändern des Berichtsparameters in einen mehrwertigen Parameter</span><span class="sxs-lookup"><span data-stu-id="79289-119">Change the Report Parameter to Accept Multiple Values</span></span>](#Multivalued)  
  
8.  [<span data-ttu-id="79289-120">Hinzufügen eines booleschen Parameters für bedingte Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="79289-120">Add a Boolean Parameter for Conditional Visibility</span></span>](#Boolean)  
  
9. [<span data-ttu-id="79289-121">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="79289-121">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="79289-122">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="79289-122">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="79289-123">In diesem Lernprogramm werden die Schritte für den Assistenten in einem Verfahren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="79289-123">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="79289-124">Im ersten Tutorial dieser Reihe erhalten Sie detaillierte Anweisungen zum Navigieren zu einem Berichtsserver, zum Auswählen einer Datenquelle sowie zum Erstellen eines Datasets: [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="79289-124">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="79289-125">Ungefähre Dauer dieses Lernprogramms: 25 Minuten.</span><span class="sxs-lookup"><span data-stu-id="79289-125">Estimated time to complete this tutorial: 25 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79289-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="79289-126">Requirements</span></span>  
 <span data-ttu-id="79289-127">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="79289-127">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="79289-128">1. Erstellen eines Matrix Berichts und eines Datasets mit dem Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="79289-128">1. Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="79289-129">Erstellen Sie einen Matrixbericht, eine Datenquelle und ein Dataset.</span><span class="sxs-lookup"><span data-stu-id="79289-129">Create a matrix report, a data source, and a dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79289-130">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="79289-130">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="79289-131">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="79289-131">This makes the query quite long.</span></span> <span data-ttu-id="79289-132">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="79289-132">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="79289-133">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="79289-133">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix-report"></a><span data-ttu-id="79289-134">So erstellen Sie einen neuen Matrixbericht</span><span class="sxs-lookup"><span data-stu-id="79289-134">To create a new matrix report</span></span>  
  
1.  <span data-ttu-id="79289-135">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="79289-135">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="79289-136">Das Dialogfeld " **Getting Started** " wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-136">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79289-137">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche " **Berichts-Generator** " auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="79289-137">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="79289-138">Vergewissern Sie sich im linken Bereich, dass der **Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="79289-138">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="79289-139">Klicken Sie im rechten Bereich auf **Tabellen- oder Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="79289-139">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="79289-140">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="79289-140">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="79289-141">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**.</span><span class="sxs-lookup"><span data-stu-id="79289-141">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
6.  <span data-ttu-id="79289-142">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="79289-142">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="79289-143">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine Datenquelle vom Typ **SQL Server**aus.</span><span class="sxs-lookup"><span data-stu-id="79289-143">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="79289-144">Wählen Sie in der Liste eine Datenquelle aus, oder navigieren Sie zum Berichtsserver, um eine Datenquelle auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="79289-144">Select a data source from the list or browse to the report server to select one.</span></span>  
  
8.  <span data-ttu-id="79289-145">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="79289-145">Click **Next**.</span></span>  
  
9. <span data-ttu-id="79289-146">Klicken Sie auf der Seite **Abfrage entwerfen** auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="79289-146">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
10. <span data-ttu-id="79289-147">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="79289-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    ;WITH CTE (StoreID, Subcategory, Quantity)   
    AS (  
    SELECT 200 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 2002 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Camcorders' AS Subcategory, 1954 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Accessories' AS Subcategory, 1895 AS Quantity  
    UNION SELECT  199 AS StoreID, 'Digital Cameras' AS Subcategory, 1849 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1579 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Camcorders' AS Subcategory, 1561 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital Cameras' AS Subcategory, 1553 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Accessories' AS Subcategory, 1534 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Accessories' AS Subcategory, 1755 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Camcorders' AS Subcategory, 1631 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1772 AS Quantity)  
    SELECT StoreID, Subcategory, Quantity  
    FROM CTE  
    ```  
  
     <span data-ttu-id="79289-148">Durch diese Abfrage werden die Ergebnisse mehrerer [!INCLUDE[tsql](../includes/tsql-md.md)]-SELECT-Anweisungen in einem allgemeinen Tabellenausdruck kombiniert, um Werte anzugeben, die auf vereinfachten Daten aus der Contoso-Beispieldatenbank basieren.</span><span class="sxs-lookup"><span data-stu-id="79289-148">This query combines the results of several [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT statements inside a common table expression to specify values that are based on simplified data from the Contoso sample database.</span></span> <span data-ttu-id="79289-149">Die Contoso-Umsatzdaten stellen internationale Umsatzdaten für Verbrauchsgüter dar.</span><span class="sxs-lookup"><span data-stu-id="79289-149">The Contoso sales data represents international sales data for consumer goods.</span></span> <span data-ttu-id="79289-150">In diesem Lernprogramm werden Umsatzdaten für Kameras verwendet.</span><span class="sxs-lookup"><span data-stu-id="79289-150">This tutorial uses sales data for cameras.</span></span> <span data-ttu-id="79289-151">Die Unterkategorien sind Digitalkameras, digitale Spiegelreflexkameras (SLR), Camcorder und Zubehör.</span><span class="sxs-lookup"><span data-stu-id="79289-151">The subcategories represent digital cameras, digital single lens reflex (SLR) cameras, camcorders, and accessories.</span></span>  
  
     <span data-ttu-id="79289-152">Zu den in der Abfrage angegebenen Spaltennamen zählen eine Geschäfts-ID, eine Verkaufselement-Unterkategorie und die bestellte Menge für Verkaufsaufträge von drei Geschäften.</span><span class="sxs-lookup"><span data-stu-id="79289-152">The query specifies column names that include a store identifier, a sales item subcategory, and the quantity ordered for sales orders from three stores.</span></span> <span data-ttu-id="79289-153">In dieser Abfrage ist der Geschäftsname nicht Teil des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="79289-153">In this query, the store name is not part of the result set.</span></span> <span data-ttu-id="79289-154">An späterer Stelle dieses Lernprogramms suchen Sie in einem separaten Dataset nach dem Namen des Geschäfts, das der Geschäfts-ID entspricht.</span><span class="sxs-lookup"><span data-stu-id="79289-154">Later in this tutorial, you will look up the name of the store that corresponds to the store identifier from a separate dataset.</span></span>  
  
     <span data-ttu-id="79289-155">Diese Abfrage enthält keine Abfrageparameter.</span><span class="sxs-lookup"><span data-stu-id="79289-155">This query does not contain query parameters.</span></span> <span data-ttu-id="79289-156">Abfrageparameter werden später in diesem Lernprogramm hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79289-156">You will add query parameters later in this tutorial.</span></span>  
  
11. <span data-ttu-id="79289-157">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="79289-157">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="79289-158">Das Resultset enthält 11 Datenzeilen, in denen die Menge verkaufter Artikel in jeder Unterkategorie für vier Geschäfte angezeigt wird, und die folgenden Spalten: "StoreID", "Subcategory" und "Quantity".</span><span class="sxs-lookup"><span data-stu-id="79289-158">The result set displays 11 rows of data that show the quantity of items sold for each subcategory for four stores, and includes the following columns: StoreID, Subcategory, Quantity.</span></span>  
  
12. <span data-ttu-id="79289-159">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="79289-159">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="79289-160">2. Organisieren von Daten, auswählen von Layout und Stil im Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="79289-160">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="79289-161">Stellen Sie mithilfe des Assistenten einen Startentwurf für die Anzeige von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="79289-161">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="79289-162">Im Vorschaufenster des Assistenten können Sie das Ergebnis der Datengruppierung visualisieren, bevor Sie den Tabellen- oder Matrixentwurf abschließen.</span><span class="sxs-lookup"><span data-stu-id="79289-162">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="79289-163">So gruppieren Sie Daten</span><span class="sxs-lookup"><span data-stu-id="79289-163">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="79289-164">Ziehen Sie „Subcategory“ auf der Seite **Felder anordnen** in **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="79289-164">On the **Arrange fields** page, drag Subcategory to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="79289-165">Ziehen Sie „StoreID“ in **Spaltengruppen**.</span><span class="sxs-lookup"><span data-stu-id="79289-165">Drag StoreID to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="79289-166">Ziehen Sie „Quantity“ in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="79289-166">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="79289-167">Sie haben die Werte für die verkaufte Menge in Zeilen organisiert und nach Unterkategorie gruppiert.</span><span class="sxs-lookup"><span data-stu-id="79289-167">You have organized the quantity sold values in rows grouped by subcategory.</span></span> <span data-ttu-id="79289-168">Für jedes Geschäft wird eine Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-168">There will be one column for each store.</span></span>  
  
4.  <span data-ttu-id="79289-169">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="79289-169">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="79289-170">Vergewissern Sie sich, dass auf der Seite **Layout auswählen** unter **Optionen die Option** **Teil-und Gesamtsummen anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="79289-170">On the **Choose a Layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="79289-171">Wenn Sie den Bericht ausführen, werden in der letzten Spalte die Gesamtmenge jeder Unterkategorie für alle Geschäfte und in der letzten Zeile die Gesamtmenge für alle Unterkategorien für jedes Geschäft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-171">When you run the report, the last column will show the total quantity of each subcategory for all stores, and the last row will show the total quantity for all subcategories for each store.</span></span>  
  
6.  <span data-ttu-id="79289-172">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="79289-172">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="79289-173">Wählen Sie auf der Seite Format **auswählen** im Bereich Stile einen Stil aus.</span><span class="sxs-lookup"><span data-stu-id="79289-173">On the **Choose a Style** page, in the Styles pane, select a style.</span></span>  
  
8.  <span data-ttu-id="79289-174">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="79289-174">Click **Finish**.</span></span>  
  
     <span data-ttu-id="79289-175">Die Matrix wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79289-175">The matrix is added to the design surface.</span></span> <span data-ttu-id="79289-176">Die Matrix enthält drei Spalten und drei Zeilen.</span><span class="sxs-lookup"><span data-stu-id="79289-176">The matrix displays three columns and three rows.</span></span> <span data-ttu-id="79289-177">Die Zellen in der ersten Zeile enthalten "Subcategory", "[StoreID]" und "Total".</span><span class="sxs-lookup"><span data-stu-id="79289-177">The contents of the cells in the first row are Subcategory, [StoreID], and Total.</span></span> <span data-ttu-id="79289-178">Die Zellen in der zweiten Zeile enthalten Ausdrücke, die die Unterkategorie, die Menge verkaufter Artikel für jedes Geschäft und die Gesamtmenge in jeder Unterkategorie für alle Geschäfte darstellen.</span><span class="sxs-lookup"><span data-stu-id="79289-178">The contents of the cells in the second row contain expressions that represent the subcategory, the quantity of items sold for each store, and the total quantity for each subcategory for all stores.</span></span> <span data-ttu-id="79289-179">Die Zellen in der letzten Zeile enthalten das Gesamtergebnis für jedes Geschäft.</span><span class="sxs-lookup"><span data-stu-id="79289-179">The cells in the final row display the grand total for each store.</span></span>  
  
9. <span data-ttu-id="79289-180">Klicken Sie in die Matrix, zeigen Sie auf den Rand der ersten Spalte, und vergrößern Sie die Spaltenbreite mithilfe des Ziehpunkts.</span><span class="sxs-lookup"><span data-stu-id="79289-180">Click in the matrix, hover over the edge of the first column, grab the handle, and expand the column width.</span></span>  
  
10. <span data-ttu-id="79289-181">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="79289-181">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="79289-182">Der Bericht wird auf dem Berichtsserver ausgeführt. Titel und Zeitpunkt der Verarbeitung des Berichts werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-182">The report runs on the report server and displays the title and the time the report processing occurred.</span></span>  
  
 <span data-ttu-id="79289-183">In diesem Szenario wird in den Spaltenüberschriften die Geschäfts-ID, aber nicht der Geschäftsnamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-183">In this scenario, the column headings display the store identifier but not the store name.</span></span> <span data-ttu-id="79289-184">Später fügen Sie einen Ausdruck hinzu, um in einem Dataset, das Geschäfts-ID/Geschäftsname-Paare enthält, nach dem Geschäftsnamen suchen.</span><span class="sxs-lookup"><span data-stu-id="79289-184">Later, you will add an expression to look up the store name in a dataset that contains store identifier/store name pairs.</span></span>  
  
##  <a name="3-add-a-query-parameter-to-create-a-report-parameter"></a><a name="Query"></a><span data-ttu-id="79289-185">3. Hinzufügen eines Abfrage Parameters zum Erstellen eines Berichts Parameters</span><span class="sxs-lookup"><span data-stu-id="79289-185">3. Add a Query Parameter to Create a Report Parameter</span></span>  
 <span data-ttu-id="79289-186">Wenn Sie einer Abfrage einen Abfrageparameter hinzufügen, erstellt der Berichts-Generator automatisch einen eindeutigen Berichtsparameter mit Standardeigenschaften für Name, Eingabe und Datentyp.</span><span class="sxs-lookup"><span data-stu-id="79289-186">When you add a query parameter to a query, Report Builder automatically creates a single-valued report parameter with default properties for name, prompt, and data type.</span></span>  
  
#### <a name="to-add-a-query-parameter"></a><span data-ttu-id="79289-187">So fügen Sie einen Abfrageparameter hinzu</span><span class="sxs-lookup"><span data-stu-id="79289-187">To add a query parameter</span></span>  
  
1.  <span data-ttu-id="79289-188">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-188">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-189">Erweitern Sie im Berichtsdatenbereich den Ordner **Datasets** , klicken Sie mit der rechten Maustaste auf **DataSet1**, und klicken Sie anschließend auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="79289-189">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
3.  <span data-ttu-id="79289-190">Fügen Sie die folgende [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` Klausel als letzte Zeile in der Abfrage hinzu:</span><span class="sxs-lookup"><span data-stu-id="79289-190">Add the following [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause as the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID = (@StoreID)  
    ```  
  
     <span data-ttu-id="79289-191">Die- `WHERE` Klausel schränkt die abgerufenen Daten auf die Geschäfts-ID ein, die durch den-Abfrage Parameter angegeben wird *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="79289-191">The `WHERE` clause limits the retrieved data to the store identifier that is specified by the query parameter *@StoreID*.</span></span>  
  
4.  <span data-ttu-id="79289-192">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="79289-192">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="79289-193">Das Dialogfeld **Abfrageparameter definieren** wird geöffnet, und Sie werden aufgefordert, einen Wert für den Abfrageparameter *@StoreID*.</span><span class="sxs-lookup"><span data-stu-id="79289-193">The **Define Query Parameters** dialog box opens and prompts for a value for the query parameter *@StoreID*.</span></span>  
  
5.  <span data-ttu-id="79289-194">Geben Sie im Feld **Parameterwert**die Zahl **200**ein.</span><span class="sxs-lookup"><span data-stu-id="79289-194">In **Parameter Value**, type **200**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="79289-195">Im Resultset werden die verkauften Mengen für Zubehör, Camcorder und digitale SLR-Kameras für die Geschäfts-ID **200**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-195">The result set displays the quantities sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="79289-196">Erweitern Sie im Berichtsdatenbereich den Ordner **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="79289-196">In the Report Data pane, expand the **Parameters** folder.</span></span>  
  
 <span data-ttu-id="79289-197">Beachten Sie, dass nun ein Berichts Parameter mit dem Namen vorhanden ist *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="79289-197">Notice that there is now a report parameter named *@StoreID*.</span></span> <span data-ttu-id="79289-198">Standardmäßig weist der-Parameter den Datentyp **Text**auf.</span><span class="sxs-lookup"><span data-stu-id="79289-198">By default, the parameter has data type **Text**.</span></span> <span data-ttu-id="79289-199">Da es sich bei der Geschäfts-ID um eine ganze Zahl handelt, ändern Sie den Datentyp im nächsten Verfahren in "Integer".</span><span class="sxs-lookup"><span data-stu-id="79289-199">Because the store identifier is an integer, you will change the data type to Integer in the next procedure.</span></span>  
  
##  <a name="4-change-default-data-type-and-other-properties-for-a-report-parameter"></a><a name="ChangeDefaultProperties"></a><span data-ttu-id="79289-200">4. Ändern des Standard Datentyps und anderer Eigenschaften für einen Berichts Parameter</span><span class="sxs-lookup"><span data-stu-id="79289-200">4. Change Default Data Type and Other Properties for a Report Parameter</span></span>  
 <span data-ttu-id="79289-201">Nachdem Sie einen Berichtsparameter erstellt haben, können Sie die Standardwerte für Eigenschaften anpassen.</span><span class="sxs-lookup"><span data-stu-id="79289-201">After a report parameter is created, you can adjust the default values for properties.</span></span>  
  
#### <a name="to-change-the-default-data-type-for-a-report-parameter"></a><span data-ttu-id="79289-202">So ändern Sie den Standarddatentyp für einen Berichtsparameter</span><span class="sxs-lookup"><span data-stu-id="79289-202">To change the default data type for a report parameter</span></span>  
  
1.  <span data-ttu-id="79289-203">Klicken Sie im Berichtsdaten Bereich unter dem Knoten **Parameter** mit der rechten Maustaste auf *@StoreID* , und klicken Sie dann auf **Parameter Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-203">In the Report Data pane under the **Parameters** node, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="79289-204">Geben Sie in der Eingabeaufforderung **Store Identifier ein?**</span><span class="sxs-lookup"><span data-stu-id="79289-204">In Prompt, type **Store identifier?**</span></span> <span data-ttu-id="79289-205">Dieser Text wird auf der Berichts-Viewer-Symbolleiste angezeigt, wenn Sie den Bericht ausführen.</span><span class="sxs-lookup"><span data-stu-id="79289-205">This text appears on the report viewer toolbar when you run the report.</span></span>  
  
3.  <span data-ttu-id="79289-206">Wählen Sie in der Dropdownliste **Datentyp**die Option **Ganze Zahl**aus.</span><span class="sxs-lookup"><span data-stu-id="79289-206">In **Data type**, from the drop-down list, select **Integer**.</span></span>  
  
4.  <span data-ttu-id="79289-207">Nehmen Sie die verbleibenden Standardwerte im Dialogfeld an.</span><span class="sxs-lookup"><span data-stu-id="79289-207">Accept the remaining default values in the dialog box.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="79289-208">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-208">Preview the report.</span></span> <span data-ttu-id="79289-209">Der Berichts-Viewer zeigt die Eingabeaufforderung für an *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="79289-209">The report viewer displays the prompt for *@StoreID*.</span></span>  
  
7.  <span data-ttu-id="79289-210">Geben Sie auf der Berichts-Viewer-Symbolleiste neben Geschäfts-ID die Zahl **200**ein, und klicken anschließend auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="79289-210">On the report viewer toolbar, next to Store ID, type **200**, and then click **View Report**.</span></span>  
  
##  <a name="4a-add-a-dataset-to-provide-available-values-and-display-names"></a><a name="AddDataset"></a><span data-ttu-id="79289-211">4a.</span><span class="sxs-lookup"><span data-stu-id="79289-211">4a.</span></span> <span data-ttu-id="79289-212">Hinzufügen eines Datasets, um verfügbare Werte und Anzeigenamen anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="79289-212">Add a Dataset to Provide Available Values and Display Names</span></span>  
 <span data-ttu-id="79289-213">Um sicherzustellen dass ein Benutzer nur gültige Werte für einen Parameter eingeben kann, können Sie eine Dropdownliste von Werten erstellen.</span><span class="sxs-lookup"><span data-stu-id="79289-213">To ensure a user can type only valid values for a parameter, you can create a drop-down list of values to choose from.</span></span> <span data-ttu-id="79289-214">Die Werte können aus einem Dataset oder einer von Ihnen angegebenen Liste stammen.</span><span class="sxs-lookup"><span data-stu-id="79289-214">The values can come from a dataset or from a list that you specify.</span></span> <span data-ttu-id="79289-215">Verfügbare Werte müssen aus einem Dataset stammen, dessen Abfrage keinen Verweis auf den Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="79289-215">Available values must be supplied from a dataset that has a query that does not contain a reference to the parameter.</span></span>  
  
#### <a name="to-create-a-dataset-for-valid-values-for-a-parameter"></a><span data-ttu-id="79289-216">So erstellen Sie ein Dataset für gültige Werte für einen Parameter</span><span class="sxs-lookup"><span data-stu-id="79289-216">To create a dataset for valid values for a parameter</span></span>  
  
1.  <span data-ttu-id="79289-217">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-217">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-218">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf den Ordner **Datasets** , und klicken Sie anschließend auf **Dataset hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="79289-218">In the Report Data pane, right-click the **Datasets** folder, and then click **Add Dataset**.</span></span>  
  
3.  <span data-ttu-id="79289-219">Geben Sie im Feld **Name**den Namen **Geschäfte**ein.</span><span class="sxs-lookup"><span data-stu-id="79289-219">In **Name**, type **Stores**.</span></span>  
  
4.  <span data-ttu-id="79289-220">Wählen Sie die Option **in meinen Bericht eingebettetes DataSet verwenden aus** .</span><span class="sxs-lookup"><span data-stu-id="79289-220">Select the **Use a dataset embedded in my report** option.</span></span>  
  
5.  <span data-ttu-id="79289-221">Wählen Sie unter **Datenquelle**in der Dropdown Liste die Datenquelle aus, die Sie im ersten Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="79289-221">In **Data source**, from the drop-down list, choose the data source you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="79289-222">Vergewissern Sie sich, dass unter **Abfragetyp**die Option **Text** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="79289-222">In **Query type**, verify that **Text** is selected.</span></span>  
  
7.  <span data-ttu-id="79289-223">Fügen Sie unter **Abfrage**folgende Abfrage ein:</span><span class="sxs-lookup"><span data-stu-id="79289-223">In **Query**, paste the following text:</span></span>  
  
    ```  
    SELECT 200 AS StoreID, 'Contoso Catalog Store' as StoreName  
    UNION SELECT 199 AS StoreID, 'Contoso North America Online Store' as StoreName  
    UNION SELECT 307 AS StoreID, 'Contoso Asia Online Store' as StoreName  
    UNION SELECT 306 AS StoreID, 'Contoso Europe Online Store' as StoreName  
    ```  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="79289-224">Im Berichtsdatenbereich werden die Felder „StoreID“ und „StoreName“ unter dem Datasetknoten **Geschäfte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-224">The Report Data pane displays the fields StoreID and StoreName under the **Stores** dataset node.</span></span>  
  
##  <a name="4b-specify-available-values-to-create-a-drop-down-list-of-values"></a><a name="AvailableValues"></a><span data-ttu-id="79289-225">4B.</span><span class="sxs-lookup"><span data-stu-id="79289-225">4b.</span></span> <span data-ttu-id="79289-226">Angeben verfügbarer Werte zum Erstellen einer Dropdownliste von Werten</span><span class="sxs-lookup"><span data-stu-id="79289-226">Specify Available Values to Create a Drop-down List of Values</span></span>  
 <span data-ttu-id="79289-227">Nachdem Sie ein Dataset erstellt haben, um verfügbare Werte bereitzustellen, müssen Sie die Berichtseigenschaften ändern, um das Dataset und das Feld anzugeben, aus denen die Dropdownliste gültiger Werte auf der Berichts-Viewer-Symbolleiste aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="79289-227">After you create a dataset to provide available values, you must change the report properties to specify which dataset and which field to use to populate the drop-down list of valid values on the reportviewer toolbar.</span></span>  
  
#### <a name="to-provide-available-values-for-a-parameter-from-a-dataset"></a><span data-ttu-id="79289-228">So stellen Sie verfügbare Werte für einen Parameter aus einem Dataset bereit</span><span class="sxs-lookup"><span data-stu-id="79289-228">To provide available values for a parameter from a dataset</span></span>  
  
1.  <span data-ttu-id="79289-229">Klicken Sie im Berichtsdaten Bereich mit der rechten Maustaste auf den Parameter *@StoreID* , und klicken Sie dann auf **Parameter Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-229">In the Report Data pane, right-click the parameter *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="79289-230">Klicken Sie auf **Verfügbare Werte**und anschließend auf **Werte aus Abfrage abrufen**.</span><span class="sxs-lookup"><span data-stu-id="79289-230">Click **Available Values**, and then click **Get values from a query**.</span></span>  
  
3.  <span data-ttu-id="79289-231">Klicken Sie unter **Dataset**in der Dropdownliste auf den Eintrag **Stores**.</span><span class="sxs-lookup"><span data-stu-id="79289-231">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
4.  <span data-ttu-id="79289-232">Wählen Sie unter **Wertfeld**den Eintrag „StoreID“ aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="79289-232">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
5.  <span data-ttu-id="79289-233">Wählen Sie unter **Bezeichnungsfeld**den Eintrag „StoreName“ aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="79289-233">In **Label field**, from the drop-down list, click StoreName.</span></span> <span data-ttu-id="79289-234">Das Bezeichnungsfeld gibt den Anzeigenamen für den Wert an.</span><span class="sxs-lookup"><span data-stu-id="79289-234">The label field specifies the display name for the value.</span></span>  
  
6.  <span data-ttu-id="79289-235">Klicken Sie auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="79289-235">Click **General**.</span></span>  
  
7.  <span data-ttu-id="79289-236">Geben Sie in der Eingabeaufforderung den **Namen Store Name ein?**</span><span class="sxs-lookup"><span data-stu-id="79289-236">In Prompt, type **Store name?**</span></span>  
  
     <span data-ttu-id="79289-237">Dem Benutzer steht jetzt anstelle einer Liste von Geschäfts-IDs eine Liste von Geschäftsnamen zur Verfügung, um seine Auswahl zu treffen.</span><span class="sxs-lookup"><span data-stu-id="79289-237">The user will now select from a list of store names instead of store identifiers.</span></span> <span data-ttu-id="79289-238">Beachten Sie, dass der Parameterdatentyp weiterhin **Integer** lautet, da der Parameter nicht auf dem Geschäftsnamen, sondern auf der Geschäfts-ID basiert.</span><span class="sxs-lookup"><span data-stu-id="79289-238">Note that the parameter data type remains **Integer** because the parameter is based on the store identifier, not the store name.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="79289-239">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-239">Preview the report.</span></span>  
  
     <span data-ttu-id="79289-240">In der Berichts-Viewer-Symbolleiste ist das Parameter Textfeld jetzt eine Dropdown Liste, in der angezeigt wird **\<Select a Value>** .</span><span class="sxs-lookup"><span data-stu-id="79289-240">In the report viewer toolbar, the parameter text box is now a drop-down list that displays **\<Select a Value>**.</span></span>  
  
10. <span data-ttu-id="79289-241">Wählen Sie in der Dropdown Liste die Option "Configuration Catalog Store" aus, und klicken Sie dann auf " **Bericht anzeigen**".</span><span class="sxs-lookup"><span data-stu-id="79289-241">From the drop-down list, select Contoso Catalog Store, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="79289-242">Im Bericht werden die verkauften Mengen für Zubehör, Camcorder und digitale SLR-Kameras für die Geschäfts-ID **200**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-242">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4c-specify-default-values-so-the-report-runs-automatically"></a><a name="DefaultValues"></a><span data-ttu-id="79289-243">4C.</span><span class="sxs-lookup"><span data-stu-id="79289-243">4c.</span></span> <span data-ttu-id="79289-244">Angeben von Standardwerten zur automatischen Ausführung des Berichts</span><span class="sxs-lookup"><span data-stu-id="79289-244">Specify Default Values so the Report Runs Automatically</span></span>  
 <span data-ttu-id="79289-245">Sie können einen Standardwert für jeden Berichtsparameter angeben, damit der Bericht automatisch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="79289-245">You can specify a default value for each parameter so the report runs automatically.</span></span>  
  
#### <a name="to-specify-a-default-value-from-a-dataset"></a><span data-ttu-id="79289-246">So geben Sie einen Standardwert aus einem Dataset an</span><span class="sxs-lookup"><span data-stu-id="79289-246">To specify a default value from a dataset</span></span>  
  
1.  <span data-ttu-id="79289-247">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-247">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-248">Klicken Sie im Berichtsdaten Bereich mit der rechten Maustaste auf *@StoreID* , und klicken Sie dann auf **Parameter Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-248">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="79289-249">Klicken Sie auf **Standardwerte**und dann auf **Werte aus Abfrage erhalten**.</span><span class="sxs-lookup"><span data-stu-id="79289-249">Click **Default Values**, and then click **Get values from a query**.</span></span>  
  
4.  <span data-ttu-id="79289-250">Klicken Sie unter **Dataset**in der Dropdownliste auf den Eintrag **Stores**.</span><span class="sxs-lookup"><span data-stu-id="79289-250">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
5.  <span data-ttu-id="79289-251">Wählen Sie unter **Wertfeld**den Eintrag „StoreID“ aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="79289-251">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="79289-252">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-252">Preview the report.</span></span>  
  
 <span data-ttu-id="79289-253">Für *@StoreID* zeigt der Berichts-Viewer den Wert "Configuration Manager-Nordamerika Online Store" an.</span><span class="sxs-lookup"><span data-stu-id="79289-253">For *@StoreID*, the report viewer displays the value "Contoso North America Online Store".</span></span> <span data-ttu-id="79289-254">Dies ist der erste Wert aus dem Resultset für das DataSet **Stores**.</span><span class="sxs-lookup"><span data-stu-id="79289-254">This is the first value from the result set for the dataset **Stores**.</span></span> <span data-ttu-id="79289-255">Im Bericht wird die verkaufte Menge von Digitalkameras für die Geschäfts-ID **199**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-255">The report displays the quantity sold for Digital Cameras for store identifier **199**.</span></span>  
  
#### <a name="to-specify-a-custom-default-value"></a><span data-ttu-id="79289-256">So geben Sie einen benutzerdefinierten Standardwert an</span><span class="sxs-lookup"><span data-stu-id="79289-256">To specify a custom default value</span></span>  
  
1.  <span data-ttu-id="79289-257">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-257">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-258">Klicken Sie im Berichtsdaten Bereich mit der rechten Maustaste auf *@StoreID* , und klicken Sie dann auf **Parameter Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-258">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="79289-259">Klicken Sie auf **Standardwerte**, und klicken Sie auf **Werte angeben**und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="79289-259">Click **Default Values**, and click **Specify values**, and then click **Add**.</span></span> <span data-ttu-id="79289-260">Eine neue Wertzeile wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79289-260">A new value row is added.</span></span>  
  
4.  <span data-ttu-id="79289-261">Geben Sie im Feld **Wert**die Zeichenfolge **200**ein.</span><span class="sxs-lookup"><span data-stu-id="79289-261">In **Value**, type **200**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="79289-262">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-262">Preview the report.</span></span>  
  
 <span data-ttu-id="79289-263">Für *@StoreID* zeigt der Berichts-Viewer den Wert "Configuration Manager-Katalog Speicher" an.</span><span class="sxs-lookup"><span data-stu-id="79289-263">For *@StoreID*, the report viewer displays the value "Contoso Catalog Store".</span></span> <span data-ttu-id="79289-264">Dies ist der Anzeige Name für die Geschäfts-ID **200**.</span><span class="sxs-lookup"><span data-stu-id="79289-264">This is the display name for store identifier **200**.</span></span> <span data-ttu-id="79289-265">Im Bericht werden die verkauften Mengen für Zubehör, Camcorder und digitale SLR-Kameras für die Geschäfts-ID **200**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-265">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4d-look-up-a-value-from-a-dataset-that-has-namevalue-pairs"></a><a name="NameValue"></a><span data-ttu-id="79289-266">4D.</span><span class="sxs-lookup"><span data-stu-id="79289-266">4d.</span></span> <span data-ttu-id="79289-267">Suchen nach Werten in einem Dataset mit Name-Wert-Paaren</span><span class="sxs-lookup"><span data-stu-id="79289-267">Look up a Value from a Dataset that has Name/Value Pairs</span></span>  
 <span data-ttu-id="79289-268">Ein Dataset kann sowohl den Bezeichner als auch das entsprechende Namensfeld enthalten.</span><span class="sxs-lookup"><span data-stu-id="79289-268">A dataset might contain both the identifier and the corresponding name field.</span></span> <span data-ttu-id="79289-269">Wenn Sie nur einen Bezeichner haben, können Sie in einem von Ihnen erstellten Dataset, das Name-Wert-Paare enthält, nach dem entsprechenden Namen suchen.</span><span class="sxs-lookup"><span data-stu-id="79289-269">When you only have an identifier, you can look up the corresponding name in a dataset that you created that includes name/value pairs.</span></span>  
  
#### <a name="to-look-up-a-value-from-a-dataset"></a><span data-ttu-id="79289-270">So suchen Sie nach einem Wert in einem Dataset</span><span class="sxs-lookup"><span data-stu-id="79289-270">To look up a value from a dataset</span></span>  
  
1.  <span data-ttu-id="79289-271">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-271">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-272">Klicken Sie auf der Entwurfsoberfläche in der Matrix im ersten Zeilenspaltenheader mit der rechten Maustaste auf `[StoreID]` , und klicken Sie anschließend auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="79289-272">On the design surface, in the matrix, in the first row column header, right-click `[StoreID]` and then click **Expression**.</span></span>  
  
3.  <span data-ttu-id="79289-273">Löschen Sie im Ausdrucksbereich den gesamten Text mit Ausnahme des Anfangs `equals` (=).</span><span class="sxs-lookup"><span data-stu-id="79289-273">In the expression pane, delete all text except the beginning `equals` (=).</span></span>  
  
4.  <span data-ttu-id="79289-274">Erweitern Sie unter **Kategorie**den Knoten **Allgemeine Funktionen**, und klicken Sie auf **Sonstiges**.</span><span class="sxs-lookup"><span data-stu-id="79289-274">In **Category**, expand **Common Functions**, and click **Miscellaneous**.</span></span> <span data-ttu-id="79289-275">Im Bereich "Element" wird ein Satz von Funktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-275">The Item pane displays a set of functions.</span></span>  
  
5.  <span data-ttu-id="79289-276">Doppelklicken Sie in „Element“ auf **Suche**.</span><span class="sxs-lookup"><span data-stu-id="79289-276">In Item, double-click **Lookup**.</span></span> <span data-ttu-id="79289-277">Im Ausdrucksbereich wird `=Lookup(`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-277">The expression pane displays `=Lookup(`.</span></span> <span data-ttu-id="79289-278">Der Bereich "Beispiel" enthält ein Beispiel für die Suchsyntax.</span><span class="sxs-lookup"><span data-stu-id="79289-278">The Example pane displays an example of Lookup syntax.</span></span>  
  
6.  <span data-ttu-id="79289-279">Geben Sie den folgenden Ausdruck ein: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span><span class="sxs-lookup"><span data-stu-id="79289-279">Type the following expression: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span></span>  
  
     <span data-ttu-id="79289-280">Die Suchfunktion empfängt den Wert für "StoreID", sucht im Dataset "Geschäfte" danach und gibt den "StoreName"-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="79289-280">The Lookup function takes the value for StoreID, looks it up in the "Stores" dataset, and returns the StoreName value.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="79289-281">Der Spaltenheader für das Geschäft enthält den Anzeige Text für einen komplexen Ausdruck: **<\<Expr>>** .</span><span class="sxs-lookup"><span data-stu-id="79289-281">The store column header contains the display text for a complex expression: **<\<Expr>>**.</span></span>  
  
8.  <span data-ttu-id="79289-282">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-282">Preview the report.</span></span>  
  
 <span data-ttu-id="79289-283">Im Textfeld oben auf jeder Seite wird anstelle der Geschäfts-ID der Geschäftsname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-283">The text box at the top of each page displays the store name instead of the store identifier.</span></span>  
  
##  <a name="5-display-the-selected-parameter-value-in-the-report"></a><a name="Expression"></a><span data-ttu-id="79289-284">5. Anzeigen des ausgewählten Parameter Werts im Bericht</span><span class="sxs-lookup"><span data-stu-id="79289-284">5. Display the Selected Parameter Value in the Report</span></span>  
 <span data-ttu-id="79289-285">Wenn ein Benutzer Fragen zu einem Bericht hat, ist es hilfreich, die ausgewählten Parameterwerte zu kennen.</span><span class="sxs-lookup"><span data-stu-id="79289-285">When a user has questions about a report, it helps to know which parameter values they chose.</span></span> <span data-ttu-id="79289-286">Die vom Benutzer ausgewählten Werte können für jeden Parameter im Bericht beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="79289-286">You can preserve user-selected values for each parameter in the report.</span></span> <span data-ttu-id="79289-287">Sie können die Parameter z. B. in einem Textfeld im Seitenfuß anzeigen.</span><span class="sxs-lookup"><span data-stu-id="79289-287">One way is to display the parameters in a text box in the page footer.</span></span>  
  
#### <a name="to-display-the-selected-parameter-value-and-label-on-a-page-footer"></a><span data-ttu-id="79289-288">So zeigen Sie den ausgewählten Parameterwert und die Bezeichnung in einem Seitenfuß an</span><span class="sxs-lookup"><span data-stu-id="79289-288">To display the selected parameter value and label on a page footer</span></span>  
  
1.  <span data-ttu-id="79289-289">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-289">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-290">Klicken Sie mit der rechten Maustaste auf den Seitenfuß, zeigen Sie auf **Einfügen**, und klicken Sie dann auf **Textfeld**.</span><span class="sxs-lookup"><span data-stu-id="79289-290">Right-click the page footer, point to **Insert**, and then click **Text Box**.</span></span> <span data-ttu-id="79289-291">Ziehen Sie das Textfeld neben das Textfeld mit dem Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="79289-291">Drag the text box next to the text box with the time stamp.</span></span> <span data-ttu-id="79289-292">Vergrößern Sie die Breite des Textfelds mit dem seitlichen Ziehpunkt.</span><span class="sxs-lookup"><span data-stu-id="79289-292">Grab the side handle of the text box and expand the width.</span></span>  
  
3.  <span data-ttu-id="79289-293">Ziehen Sie den Parameter im Berichtsdaten Bereich *@StoreID* in das Textfeld.</span><span class="sxs-lookup"><span data-stu-id="79289-293">From the Report Data pane, drag the parameter *@StoreID* to the text box.</span></span> <span data-ttu-id="79289-294">Im Textfeld wird `[@StoreID]`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-294">The text box displays `[@StoreID]`.</span></span>  
  
4.  <span data-ttu-id="79289-295">Um die Parameterbezeichnung anzuzeigen, klicken Sie auf das Textfeld, bis der Einfügecursor nach dem vorhandenen Ausdruck angezeigt wird, geben Sie ein Leerzeichen ein, und ziehen Sie dann eine andere Kopie des Parameters im Berichtsdatenbereich in das Textfeld.</span><span class="sxs-lookup"><span data-stu-id="79289-295">To display the parameter label, click in the text box until the insert cursor appears after the existing expression, type a space, and then drag another copy of the parameter from the Report Data pane to the text box.</span></span> <span data-ttu-id="79289-296">Im Textfeld wird `[@StoreID] [@StoreID]`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-296">The text box displays `[@StoreID] [@StoreID]`.</span></span>  
  
5.  <span data-ttu-id="79289-297">Klicken Sie mit der rechten Maustaste auf den ersten Ausdruck und dann auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="79289-297">Right-click the first expression and click **Expression**.</span></span> <span data-ttu-id="79289-298">Das Dialogfeld **Ausdruck** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="79289-298">The **Expression** dialog box opens.</span></span> <span data-ttu-id="79289-299">Ersetzen Sie den Text `Value` durch `Label`.</span><span class="sxs-lookup"><span data-stu-id="79289-299">Replace the text `Value` by `Label`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="79289-300">Der folgende Text wird angezeigt: `[@StoreID.Label] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="79289-300">The text displays: `[@StoreID.Label] [@StoreID]`.</span></span>  
  
7.  <span data-ttu-id="79289-301">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-301">Preview the report.</span></span>  
  
##  <a name="6-use-the-report-parameter-in-a-filter"></a><a name="Filter"></a><span data-ttu-id="79289-302">6. Verwenden des Berichts Parameters in einem Filter</span><span class="sxs-lookup"><span data-stu-id="79289-302">6. Use the Report Parameter in a Filter</span></span>  
 <span data-ttu-id="79289-303">Mithilfe von Filtern können die in einem Bericht zu verwendenden Daten gesteuert werden, nachdem sie aus einer externen Datenquelle abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="79289-303">Filters help control which data to use in a report after it is retrieved from an external data source.</span></span> <span data-ttu-id="79289-304">Schließen Sie den Berichtsparameter in einen Filter für die Matrix ein, um Benutzern das Steuern der angezeigten Daten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="79289-304">To let a user help control the data they want to see, you can include the report parameter in a filter for the matrix.</span></span>  
  
#### <a name="to-specify-a-parameter-in-a-matrix-filter"></a><span data-ttu-id="79289-305">So geben Sie einen Parameter in einem Matrixfilter an</span><span class="sxs-lookup"><span data-stu-id="79289-305">To specify a parameter in a matrix filter</span></span>  
  
1.  <span data-ttu-id="79289-306">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-306">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-307">Klicken Sie mit der rechten Maustaste auf einen Zeilen- oder Spaltenheaderziehpunkt in der Matrix und anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-307">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="79289-308">Klicken Sie auf **Filter**und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="79289-308">Click **Filters**, and then click **Add**.</span></span> <span data-ttu-id="79289-309">Es wird ein neuer Zeilenfilter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-309">A new filter row appears.</span></span>  
  
4.  <span data-ttu-id="79289-310">Wählen Sie im Feld **Ausdruck**aus der Dropdownliste das Datasetfeld StoreID aus.</span><span class="sxs-lookup"><span data-stu-id="79289-310">In **Expression**, from the drop-down list, select the dataset field StoreID.</span></span> <span data-ttu-id="79289-311">Der Datentyp zeigt **Ganze Zahl**an.</span><span class="sxs-lookup"><span data-stu-id="79289-311">The data type displays **Integer**.</span></span> <span data-ttu-id="79289-312">Wenn der Ausdruckswert ein Datasetfeld ist, wird der Datentyp automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79289-312">When the expression value is a dataset field, the data type is set automatically.</span></span>  
  
5.  <span data-ttu-id="79289-313">Überprüfen Sie unter **Operator**, ob `equals` (=) ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="79289-313">In **Operator**, verify that `equals` (=) is selected.</span></span>  
  
6.  <span data-ttu-id="79289-314">Geben Sie in **Wert** Folgendes ein: `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="79289-314">In **Value**, type `[@StoreID]`.</span></span> <span data-ttu-id="79289-315">`[@StoreID]` ist die einfache Ausdruckssyntax, die `=Parameters!StoreID.Value`darstellt.</span><span class="sxs-lookup"><span data-stu-id="79289-315">`[@StoreID]` is the simple expression syntax that represents `=Parameters!StoreID.Value`.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="79289-316">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-316">Preview the report.</span></span>  
  
     <span data-ttu-id="79289-317">In der Matrix werden nur Daten für "Contoso Catalog Store" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-317">The matrix displays data only for "Contoso Catalog Store".</span></span>  
  
9. <span data-ttu-id="79289-318">Wählen Sie auf der Berichts-Viewer-Symbolleiste für **Geschäftsname?** die Option **Contoso Asia Online Store**aus, und klicken Sie anschließend auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="79289-318">On the report viewer toolbar, for **Store name?**, select **Contoso Asia Online Store**, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="79289-319">In der Matrix werden Daten für das ausgewählte Geschäft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-319">The matrix displays data that corresponds to the store that you selected.</span></span>  
  
##  <a name="7-change-the-report-parameter-to-accept-multiple-values"></a><a name="Multivalued"></a><span data-ttu-id="79289-320">7. Ändern des Berichts Parameters zur Annahme mehrerer Werte</span><span class="sxs-lookup"><span data-stu-id="79289-320">7. Change the Report Parameter to Accept Multiple Values</span></span>  
 <span data-ttu-id="79289-321">Wenn Sie einen einwertigen Parameter in einen mehrwertigen Parameter ändern möchten, müssen Sie die Abfrage und alle Ausdrücke, die einen Verweis auf den Parameter enthalten (einschließlich Filter) ändern.</span><span class="sxs-lookup"><span data-stu-id="79289-321">To change a parameter from single to multivalued, you must change the query, and all expressions that contain a reference to the parameter, including filters.</span></span> <span data-ttu-id="79289-322">Ein mehrwertiger Parameter ist ein Wertarray.</span><span class="sxs-lookup"><span data-stu-id="79289-322">A multivalued parameter is an array of values.</span></span> <span data-ttu-id="79289-323">In einer Datasetabfrage muss die Abfragesyntax überprüfen, ob ein Wert in einem Satz von Werten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="79289-323">In a dataset query, query syntax must test for inclusion of one value in a set of values.</span></span> <span data-ttu-id="79289-324">In einem Berichtsausdruck greift die Ausdruckssyntax nicht auf einzelnen Wert, sondern auf ein Wertarray zu.</span><span class="sxs-lookup"><span data-stu-id="79289-324">In a report expression, expression syntax must access an array of values instead of an individual value.</span></span>  
  
#### <a name="to-change-a-parameter-from-single-to-multivalued"></a><span data-ttu-id="79289-325">So ändern Sie einen einwertigen Parameter in einen mehrwertigen Parameter</span><span class="sxs-lookup"><span data-stu-id="79289-325">To change a parameter from single to multivalued</span></span>  
  
1.  <span data-ttu-id="79289-326">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="79289-326">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="79289-327">Klicken Sie im Berichtsdaten Bereich mit der rechten Maustaste auf *@StoreID* , und klicken Sie dann auf **Parameter Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-327">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="79289-328">Aktivieren Sie **Mehrere Werte zulassen**.</span><span class="sxs-lookup"><span data-stu-id="79289-328">Select **Allow multiple values**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="79289-329">Erweitern Sie im Berichtsdatenbereich den Ordner **Datasets** , klicken Sie mit der rechten Maustaste auf **DataSet1**, und klicken Sie anschließend auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="79289-329">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
6.  <span data-ttu-id="79289-330">Ändern `equals` Sie (=) in `IN` der- [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` Klausel in der letzten Zeile in der Abfrage:</span><span class="sxs-lookup"><span data-stu-id="79289-330">Change `equals` (=) to `IN` in the [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause in the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID IN (@StoreID)  
    ```  
  
     <span data-ttu-id="79289-331">Der `IN`-Operator testet, ob ein Wert in einem Satz von Werten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="79289-331">The `IN` operator tests a value for inclusion in a set of values.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="79289-332">Klicken Sie mit der rechten Maustaste auf einen Zeilen- oder Spaltenheaderziehpunkt in der Matrix und anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-332">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
9. <span data-ttu-id="79289-333">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="79289-333">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="79289-334">Wählen Sie unter **Operator**die Option **IN**aus.</span><span class="sxs-lookup"><span data-stu-id="79289-334">In **Operator**, select **In**.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="79289-335">Löschen Sie im Textfeld, in dem der Parameter im Seitenfuß angezeigt wird, den gesamten Text.</span><span class="sxs-lookup"><span data-stu-id="79289-335">In the text box that displays the parameter in the page footer, delete all text.</span></span>  
  
13. <span data-ttu-id="79289-336">Klicken Sie mit der rechten Maustaste auf das Textfeld, und klicken Sie anschließend auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="79289-336">Right-click the text box, and then click **Expression**.</span></span> <span data-ttu-id="79289-337">Geben Sie den folgenden Ausdruck ein: `=Join(Parameters!StoreID.Label, ", ")`</span><span class="sxs-lookup"><span data-stu-id="79289-337">Type the following expression: `=Join(Parameters!StoreID.Label, ", ")`</span></span>  
  
     <span data-ttu-id="79289-338">Durch diesen Ausdruck werden alle Geschäftsnamen, die der Benutzer ausgewählt hat, verkettet.</span><span class="sxs-lookup"><span data-stu-id="79289-338">This expression concatenates all store names that the user selected.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
15. <span data-ttu-id="79289-339">Klicken Sie vor dem soeben erstellten Ausdruck in das Textfeld, und geben Sie dann Folgendes ein: "Ausgewählte Parameterwerte:".</span><span class="sxs-lookup"><span data-stu-id="79289-339">Click in the text box in front of the expression that you just created, and then type the following: Parameter Values Selected:.</span></span>  
  
16. <span data-ttu-id="79289-340">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-340">Preview the report.</span></span>  
  
17. <span data-ttu-id="79289-341">Klicken Sie auf die Dropdownliste neben "Geschäftsname?"</span><span class="sxs-lookup"><span data-stu-id="79289-341">Click the drop-down list next to Store Name?</span></span>  
  
     <span data-ttu-id="79289-342">Alle gültigen Werte werden neben einem Kontrollkästchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-342">Each valid value appears next to a check box.</span></span>  
  
18. <span data-ttu-id="79289-343">Klicken Sie auf **Alles auswählen**und anschließend auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="79289-343">Click **Select All**, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="79289-344">Im Bericht wird die verkaufte Menge in allen Unterkategorien für alle Geschäfte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-344">The report displays the quantity sold for all subcategories for all stores.</span></span>  
  
19. <span data-ttu-id="79289-345">Klicken Sie in der Dropdownliste auf **Alles auswählen** , um die Liste zu löschen, klicken Sie auf „Contoso Catalog Store“ und „Contoso Asia Online Store“ und anschließend auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="79289-345">From the drop-down list, click **Select All** to clear the list, click "Contoso Catalog Store" and "Contoso Asia Online Store", and then click **View Report**.</span></span>  
  
##  <a name="8-add-a-boolean-parameter-for-conditional-visibility"></a><a name="Boolean"></a><span data-ttu-id="79289-346">8. Hinzufügen eines booleschen Parameters für bedingte Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="79289-346">8. Add a Boolean Parameter for Conditional Visibility</span></span>  
  
#### <a name="to-add-a-boolean-parameter"></a><span data-ttu-id="79289-347">So fügen Sie einen booleschen Parameter hinzu</span><span class="sxs-lookup"><span data-stu-id="79289-347">To add a boolean parameter</span></span>  
  
1.  <span data-ttu-id="79289-348">Klicken Sie auf der Entwurfsoberfläche im Berichtsdatenbereich mit der rechten Maustaste auf **Parameter**, und klicken Sie anschließend auf **Parameter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="79289-348">On the design surface, in the Report Data pane, right-click **Parameters**, and click **Add Parameter**.</span></span>  
  
2.  <span data-ttu-id="79289-349">Geben Sie im Feld **Name**„ShowSelections“ ein.</span><span class="sxs-lookup"><span data-stu-id="79289-349">In **Name**, type ShowSelections.</span></span>  
  
3.  <span data-ttu-id="79289-350">Geben Sie im Feld **Eingabeaufforderung**„Auswahl anzeigen?“ ein.</span><span class="sxs-lookup"><span data-stu-id="79289-350">In **Prompt**, type Show selections?</span></span>  
  
4.  <span data-ttu-id="79289-351">Klicken Sie unter **Datentyp**in der Dropdown Liste auf **Boolean**.</span><span class="sxs-lookup"><span data-stu-id="79289-351">In **Data type**, from the drop-down list, click **Boolean**.</span></span>  
  
5.  <span data-ttu-id="79289-352">Klicken Sie auf **Standardwerte**.</span><span class="sxs-lookup"><span data-stu-id="79289-352">Click **Default Values**.</span></span>  
  
6.  <span data-ttu-id="79289-353">Klicken Sie auf **Wert angeben**und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="79289-353">Click **Specify value**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="79289-354">Geben Sie im Feld **Wert**den Wert **FALSE**ein.</span><span class="sxs-lookup"><span data-stu-id="79289-354">In **Value**, type **False**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-set-visibility-based-on-a-boolean-parameter"></a><span data-ttu-id="79289-355">So legen Sie die Sichtbarkeit basierend auf einem booleschen Parameter fest</span><span class="sxs-lookup"><span data-stu-id="79289-355">To set visibility based on a boolean parameter</span></span>  
  
1.  <span data-ttu-id="79289-356">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Textfeld im Seitenfuß, in dem die Parameterwerte angezeigt werden, und klicken Sie anschließend auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79289-356">On the design surface, right-click the text box in the page footer that displays the parameter values, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="79289-357">Klicken Sie auf **Sichtbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="79289-357">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="79289-358">Aktivieren Sie die Option **Je nach Ausdruck einblenden/ausblenden**, und klicken Sie anschließend auf die Ausdrucksschaltfläche **Fx**.</span><span class="sxs-lookup"><span data-stu-id="79289-358">Select the option **Show or hide based on an expression**, and then click the expression button **Fx**.</span></span>  
  
4.  <span data-ttu-id="79289-359">Geben Sie den folgenden Ausdruck ein: `=Not Parameters!ShowSelections.Value`</span><span class="sxs-lookup"><span data-stu-id="79289-359">Type the following expression: `=Not Parameters!ShowSelections.Value`</span></span>  
  
     <span data-ttu-id="79289-360">Die Textfeldoption "Sichtbarkeit" wird durch die Hidden-Eigenschaft gesteuert.</span><span class="sxs-lookup"><span data-stu-id="79289-360">The text box Visibility option is controlled by the property Hidden.</span></span> <span data-ttu-id="79289-361">Wenden Sie den `Not`-Operator an, sodass die Hidden-Eigenschaft bei Auswahl des Parameters den Wert "False" hat und das Textfeld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="79289-361">Apply the `Not` operator so that when the parameter is selected, the Hidden property is false, and the text box will be displayed.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="79289-362">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-362">Preview the report.</span></span>  
  
     <span data-ttu-id="79289-363">Das Textfeld mit der Parameterauswahl wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-363">The text box that displays the parameter choices does not appear.</span></span>  
  
8.  <span data-ttu-id="79289-364">Klicken Sie auf der Berichts-Viewer-Symbolleiste neben **Auswahl anzeigen**auf `True` .</span><span class="sxs-lookup"><span data-stu-id="79289-364">In the report viewer toolbar, next to **Show selections**, click `True`.</span></span>  
  
9. <span data-ttu-id="79289-365">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="79289-365">Preview the report.</span></span>  
  
 <span data-ttu-id="79289-366">Im Textfeld im Seitenfuß werden alle Geschäftsnamen angezeigt, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="79289-366">The text box in the page footer displays all the store names that you selected.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="79289-367">9. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="79289-367">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="79289-368">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="79289-368">To add a report title</span></span>  
  
1.  <span data-ttu-id="79289-369">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="79289-369">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="79289-370">Geben Sie "Parametrisierte Produktumsätze" ein, und klicken Sie dann außerhalb des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="79289-370">Type Parameterized Product Sales, and then click outside the text box.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="79289-371">10. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="79289-371">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="79289-372">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="79289-372">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="79289-373">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="79289-373">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="79289-374">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="79289-374">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="79289-375">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="79289-375">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="79289-376">Die Meldung **Verbindung mit Berichtsserver wird hergestellt**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-376">The message **Connecting to report server appears**.</span></span> <span data-ttu-id="79289-377">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="79289-377">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="79289-378">Ersetzen Sie im Feld **Name**den Standardnamen durch „Parametrisierter Umsatzbericht“.</span><span class="sxs-lookup"><span data-stu-id="79289-378">In **Name**, replace the default name with Parameterized Sales Report.</span></span>  
  
5.  <span data-ttu-id="79289-379">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="79289-379">Click **Save**.</span></span>  
  
 <span data-ttu-id="79289-380">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="79289-380">The report is saved to the report server.</span></span> <span data-ttu-id="79289-381">Der Berichtsserver, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79289-381">The report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79289-382">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="79289-382">Next Steps</span></span>  
 <span data-ttu-id="79289-383">Damit ist die exemplarische Vorgehensweise zum Hinzufügen eines Parameters zum Bericht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="79289-383">This concludes the walkthrough for how to add a parameter to your report.</span></span> <span data-ttu-id="79289-384">Weitere Informationen zu Parametern finden Sie unter [Berichtsparameter (Berichts-Generator und Berichts-Designer)](report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="79289-384">To learn more about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79289-385">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79289-385">See Also</span></span>  
 <span data-ttu-id="79289-386">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="79289-386">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="79289-387">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="79289-387">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
