---
title: Erweiterte Zeitreihen Vorhersagen (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b614ebdb-07ca-44af-a0ff-893364bd4b71
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 70ebf856ba0782cbf44969aba30602818015582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720539"
---
# <a name="advanced-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="91c1c-102">Erweiterte Zeitreihenvorhersagen (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="91c1c-102">Advanced Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="91c1c-103">Bei der Untersuchung des Prognosemodells wurde gezeigt, dass die Verkäufe in den meisten Regionen einem ähnlichen Muster folgen. Einige Regionen und Modelle wie das Modell M200 im Pazifischen Raum weisen jedoch deutlich abweichende Trends auf.</span><span class="sxs-lookup"><span data-stu-id="91c1c-103">You saw from exploring the forecasting model that although sales in most of the regions follow a similar pattern, some regions and some models, such as the M200 model in the Pacific region, exhibit very different trends.</span></span> <span data-ttu-id="91c1c-104">Dies ist wenig überraschend, da bekanntermaßen häufig regionale Unterschiede auftreten und durch zahlreiche Faktoren verursacht werden können, einschließlich Marketingaktionen, fehlerhafter Berichterstellung sowie politischer Faktoren.</span><span class="sxs-lookup"><span data-stu-id="91c1c-104">This does not surprise you, as you know that differences among regions are common and can be caused by many factors, including marketing promotions, inaccurate reporting, or geopolitical events.</span></span>  
  
 <span data-ttu-id="91c1c-105">Ihre Benutzer benötigen jedoch ein Modell, das weltweit angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="91c1c-105">However, your users are asking for a model that can be applied worldwide.</span></span> <span data-ttu-id="91c1c-106">Sie können daher die Auswirkungen einzelner Faktoren auf Vorhersagen minimieren, indem Sie ein Modell erstellen, das auf den aggregierten Zahlen aller Verkäufe weltweit basiert.</span><span class="sxs-lookup"><span data-stu-id="91c1c-106">Therefore, to minimize the effect of individual factors on projections, you decide to build a model that is based on aggregated measures of worldwide sales.</span></span> <span data-ttu-id="91c1c-107">Sie können dann dieses Modell für Vorhersagen für jede einzelne Region nutzen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-107">You can then use this model to make predictions for each individual region.</span></span>  
  
 <span data-ttu-id="91c1c-108">In dieser Aufgabe erstellen Sie alle Datenquellen, die für die erweiterten Vorhersagetasks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="91c1c-108">In this task, you will build all the data sources that you need to perform the advanced prediction tasks.</span></span> <span data-ttu-id="91c1c-109">Sie erstellen zwei Datenquellensichten zur Verwendung als Eingaben in die Vorhersageabfrage und eine Datenquellensicht, die beim Erstellen eines neuen Modells zum Einsatz kommt.</span><span class="sxs-lookup"><span data-stu-id="91c1c-109">You will create two data source views for use as inputs to the prediction query, and one data source view to use in building a new model.</span></span>  
  
 <span data-ttu-id="91c1c-110">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="91c1c-110">**Steps**</span></span>  
  
1.  [<span data-ttu-id="91c1c-111">Vorbereiten der erweiterten Umsatzdaten (für die Vorhersage)</span><span class="sxs-lookup"><span data-stu-id="91c1c-111">Prepare the extended sales data (for prediction)</span></span>](#bkmk_newExtendData)  
  
2.  [<span data-ttu-id="91c1c-112">Vorbereiten der aggregierten Daten (zum Erstellen des Modells)</span><span class="sxs-lookup"><span data-stu-id="91c1c-112">Prepare the aggregated data (for building the model)</span></span>](#bkmk_newReplaceData)  
  
3.  [<span data-ttu-id="91c1c-113">Vorbereiten der Reihendaten (für Kreuzvorhersagen)</span><span class="sxs-lookup"><span data-stu-id="91c1c-113">Prepare the series data (for cross-prediction)</span></span>](#bkmk_CrossData2)  
  
4.  [<span data-ttu-id="91c1c-114">Vorhersagen mit EXTEND</span><span class="sxs-lookup"><span data-stu-id="91c1c-114">Predict using EXTEND</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
5.  [<span data-ttu-id="91c1c-115">Erstellen des Modells für Kreuzvorhersagen</span><span class="sxs-lookup"><span data-stu-id="91c1c-115">Create the cross-prediction model</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
6.  [<span data-ttu-id="91c1c-116">Vorhersagen mit REPLACE</span><span class="sxs-lookup"><span data-stu-id="91c1c-116">Predict using REPLACE</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
7.  [<span data-ttu-id="91c1c-117">Überprüfen der neuen Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="91c1c-117">Review the new predictions</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
##  <a name="creating-the-new-extended-sales-data"></a><a name="bkmk_newExtendData"></a><span data-ttu-id="91c1c-118">Erstellen der neuen erweiterten Umsatzdaten</span><span class="sxs-lookup"><span data-stu-id="91c1c-118">Creating the New Extended Sales Data</span></span>  
 <span data-ttu-id="91c1c-119">Um die Umsatzdaten zu aktualisieren, müssen Sie die letzten Umsatzzahlen abrufen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-119">To update your sales data, you will need to get the latest sales figures.</span></span> <span data-ttu-id="91c1c-120">Die Daten aus der Pazifikregion sind von besonderem Interesse, da dort eine regionale Werbeaktion durchgeführt wurde, um neue Niederlassungen einzuführen und ihre Produkte bekannt zu machen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-120">Of particular interest are the data just in from the Pacific region, which launched a regional sales promotion to call attention to the new stores and raise awareness of their products.</span></span>  
  
 <span data-ttu-id="91c1c-121">In diesem Szenario gehen wir davon aus, dass die Daten aus einer Excel-Arbeitsmappe importiert wurden, die für eine Reihe von Regionen nur drei Monate neue Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="91c1c-121">For this scenario, we'll assume that the data has been imported from an Excel workbook that contains just three months of new data for a couple of regions.</span></span> <span data-ttu-id="91c1c-122">Sie erstellen mit einem Transact-SQL-Skript eine Tabelle für die Daten und definieren dann eine Datenquellen Sicht, die für die Vorhersage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91c1c-122">You'll create a table for the data using a Transact-SQL script, and then define a data source view to use for prediction.</span></span>  
  
#### <a name="create-the-table-with-new-sales-data"></a><span data-ttu-id="91c1c-123">Erstellen der Tabelle mit neuen Umsatzdaten</span><span class="sxs-lookup"><span data-stu-id="91c1c-123">Create the table with new sales data</span></span>  
  
1.  <span data-ttu-id="91c1c-124">Führen Sie in einem Transact-SQL-Abfragefenster die folgende Anweisung aus, um der Datenbank "AdventureWorksDW" (bzw. einer anderen Datenbank) die Umsatzdaten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-124">In a Transact-SQL query window, execute the following statement to add the sales data to the AdventureWorksDW database (or any other database).</span></span>  
  
    ```  
    USE [database name];  
    GO  
    IF OBJECT_ID ([dbo].[NewSalesData]) IS NOT NULL   
        DROP TABLE [dbo].[NewSalesData];  
    GO  
    CREATE TABLE [dbo].[NewSalesData]([Series] [nvarchar](255) NULL,  
    [NewDate] [datetime] NULL,  
    [NewQty] [float] NULL,  
    [NewAmount] [money] NULL) ON [PRIMARY]  
  
    GO  
    ```  
  
2.  <span data-ttu-id="91c1c-125">Fügen Sie die neuen Werte mithilfe des folgenden Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="91c1c-125">Insert the new values using the following script.</span></span>  
  
    ```  
    INSERT INTO [NewSalesData]  
    (Series,NewDate,NewQty,NewAmount)  
    VALUES('T1000 Pacific', '7/25/08', 55, '$130,170.22'),  
    ('T1000 Pacific', '8/25/08', 50, '$114,435.36 '),  
    ('T1000 Pacific', '9/25/08', 50, '$117,296.24 '),  
    ('T1000 Europe', '7/25/08', 37, '$88,210.00 '),  
    ('T1000 Europe', '8/25/08', 41, '$97,746.00 '),  
    ('T1000 Europe', '9/25/08', 37, '$88,210.00 '),  
    ('T1000 North America', '7/25/08', 69, '$164,500.00 '),  
    ('T1000 North America', '8/25/08', 66, '$157,348.00 '),  
    ('T1000 North America', '9/25/08', 58, '$138,276.00 '),  
    ('M200 Pacific', '7/25/08', 65, '$149,824.35'),  
    ('M200 Pacific', '8/25/08', 54,  '$124,619.46'),  
    ('M200 Pacific', '9/25/08', 61, '$141,143.39'),  
    ('M200 Europe', '7/25/08', 75, '$173,026.00'),  
    ('M200 Europe', '8/25/08', 76, '$175,212.00'),  
    ('M200 Europe', '9/25/08', 84, '$193,731.00'),  
    ('M200 North America', '7/25/08', 94, '$216,916.00'),  
    ('M200 North America', '8/25/08', 94, '$216,891.00'),  
    ('M200 North America', '9/25/08', 91,'$209,943.00');  
    ```  
  
    > [!WARNING]  
    >  <span data-ttu-id="91c1c-126">Die Anführungszeichen werden mit Währungswerten verwendet, um Probleme mit dem Komma als Trennzeichen und dem Währungssymbol zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="91c1c-126">The quotation marks are used with the currency values to prevent problems with the comma separator and the currency symbol.</span></span> <span data-ttu-id="91c1c-127">Sie könnten die Währungswerte auch in diesem Format übergeben: `130170.22`</span><span class="sxs-lookup"><span data-stu-id="91c1c-127">You could also pass in the currency values in this format: `130170.22`</span></span>  
    >   
    >  <span data-ttu-id="91c1c-128">Die in der Beispieldatenbank verwendeten Datumsangaben wurden für diese Version geändert.</span><span class="sxs-lookup"><span data-stu-id="91c1c-128">Note that the dates used in the sample database have changed for this release.</span></span> <span data-ttu-id="91c1c-129">Wenn Sie eine frühere Edition von AdventureWorks verwenden, müssen Sie die eingefügten Datumsangaben ggf. anpassen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-129">If you are using an earlier edition of AdventureWorks, you might need to adjust the inserted dates accordingly.</span></span>  
  
###  <a name="create-a-data-source-view-using-the-new-sales-data"></a><a name="bkmk_newReplaceData"></a><span data-ttu-id="91c1c-130">Erstellen einer Datenquellen Sicht mit den neuen Umsatzdaten</span><span class="sxs-lookup"><span data-stu-id="91c1c-130">Create a data source view using the new sales data</span></span>  
  
1.  <span data-ttu-id="91c1c-131">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Datenquellensichten**und wählen Sie dann **Neue Datenquellensicht**aus.</span><span class="sxs-lookup"><span data-stu-id="91c1c-131">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="91c1c-132">Treffen Sie im Datenquellensicht-Assistenten die folgende Auswahl:</span><span class="sxs-lookup"><span data-stu-id="91c1c-132">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="91c1c-133">**Datenquelle**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91c1c-133">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="91c1c-134">**Tabellen und Sichten auswählen**: Wählen Sie die Tabelle aus, die Sie soeben erstellt haben, newsalesdata.</span><span class="sxs-lookup"><span data-stu-id="91c1c-134">**Select Tables and Views**: Select the table that you just created, NewSalesData.</span></span>  
  
3.  <span data-ttu-id="91c1c-135">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="91c1c-135">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="91c1c-136">Klicken Sie in der Entwurfs Oberfläche der Datenquellen Sicht mit der rechten Maustaste auf newsalesdata, und wählen Sie **Daten durchsuchen** aus, um die Daten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-136">In the Data Source View design surface, right-click NewSalesData, and then select **Explore Data** to verify the data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="91c1c-137">Sie verwenden diese Daten nur für Vorhersagen; daher ist es nicht wichtig, dass sie unvollständig sind.</span><span class="sxs-lookup"><span data-stu-id="91c1c-137">You will use this data for prediction only, so it does not matter that the data is incomplete.</span></span>  
  
##  <a name="creating-the-data-for-the-cross-prediction-model"></a><a name="bkmk_CrossData2"></a><span data-ttu-id="91c1c-138">Erstellen der Daten für das Kreuz Vorhersagemodell</span><span class="sxs-lookup"><span data-stu-id="91c1c-138">Creating the Data for the Cross-Prediction Model</span></span>  
 <span data-ttu-id="91c1c-139">Die Daten, die im ursprünglichen Prognosemodell verwendet wurden, wurden in der Sicht vTimeSeries bereits ein wenig gruppiert, da dort mehrere Fahrradmodelle in eine kleinere Anzahl von Kategorien und die Ergebnisse einzelner Länder in Regionen zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-139">The data that was used in the original forecasting model was already grouped somewhat by the view vTimeSeries, which collapsed several bike models into a smaller number of categories, and merged results from individual countries into regions.</span></span> <span data-ttu-id="91c1c-140">Sie erstellen ein Modell, das für weltweite Prognosen verwendet werden kann, indem Sie direkt im Datenquellensicht-Designer einige zusätzliche einfache Aggregationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-140">To create a model that can be used for world-wide projections, you will create some additional simple aggregations directly in the Data Source View Designer.</span></span> <span data-ttu-id="91c1c-141">Die neue Datenquellensicht enthält nur die Summe und den Durchschnitt der Umsätze aller Produkte in allen Regionen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-141">The new data source view will contain just a sum and an average of the sales of all products for all regions.</span></span>  
  
 <span data-ttu-id="91c1c-142">Nachdem Sie die für das Modell verwendete Datenquelle erstellt haben, müssen Sie eine neue Datenquellensicht erstellen, die für Vorhersage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91c1c-142">After you have created the data source used for the model, you must create a new data source view to use for prediction.</span></span> <span data-ttu-id="91c1c-143">Wenn Sie z. B. die Umsätze in Europa mit dem neuen weltweite Modell vorhersagen möchten, dürfen Sie nur Daten aus der Region Europa eingeben.</span><span class="sxs-lookup"><span data-stu-id="91c1c-143">For example, if you want to predict sales for Europe using the new worldwide model, you must feed in data for the Europe region only.</span></span> <span data-ttu-id="91c1c-144">Daher richten Sie eine neue Datenquellensicht ein, die die ursprünglichen Daten filtert, und ändern die Filterbedingung für jeden Satz von Vorhersageabfragen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-144">So you will set up a new data source view that filters the original data, and change the filter condition for each set of prediction queries.</span></span>  
  
#### <a name="to-create-the-model-data-using-a-custom-data-source-view"></a><span data-ttu-id="91c1c-145">So erstellen Sie die Modelldaten mithilfe einer benutzerdefinierten Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="91c1c-145">To create the model data using a custom data source view</span></span>  
  
1.  <span data-ttu-id="91c1c-146">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Datenquellensichten**und wählen Sie dann **Neue Datenquellensicht**aus.</span><span class="sxs-lookup"><span data-stu-id="91c1c-146">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="91c1c-147">Klicken Sie auf der Begrüßungsseite des Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="91c1c-147">On the welcome page of the wizard, click **Next**.</span></span>  
  
3.  <span data-ttu-id="91c1c-148">Wählen Sie auf der Seite **Datenquelle auswählen**[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]aus und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="91c1c-148">On the **Select Data Source** page, select [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="91c1c-149">Wählen Sie auf der Seite **Tabellen und Sichten**, keine Tabellen hinzufügen aus. Klicken Sie einfach auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="91c1c-149">In the page, **Select Tables and Views**, do not add any tables-just click **Next**.</span></span>  
  
5.  <span data-ttu-id="91c1c-150">Geben Sie auf der Seite **Assistenten abschließen**den Namen ein `AllRegions` , und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-150">On the page, **Completing the Wizard**, type the name `AllRegions`, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="91c1c-151">Klicken Sie danach mit der rechten Maustaste auf die leere Entwurfsoberfläche der Datenquellensicht und wählen Sie **Neue benannte Abfrage**aus.</span><span class="sxs-lookup"><span data-stu-id="91c1c-151">Next, right-click the blank data source view design surface, and then select **New Named Query**.</span></span>  
  
7.  <span data-ttu-id="91c1c-152">Geben Sie im Dialogfeld **benannte Abfrage erstellen** unter **Name den Namen**ein, `AllRegions` und geben Sie für **Beschreibung**den Wert **Sum und Average of Sales für alle Modelle und Regionen**ein.</span><span class="sxs-lookup"><span data-stu-id="91c1c-152">In the **Create Named Query** dialog box, for **Name**, type `AllRegions`, and for **Description**, type **Sum and average of sales for all models and regions**.</span></span>  
  
8.  <span data-ttu-id="91c1c-153">Geben Sie im SQL-Textbereich die folgende Anweisung ein, und klicken Sie dann auf "OK":</span><span class="sxs-lookup"><span data-stu-id="91c1c-153">In the SQL text pane, type the following statement and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate,   
    SUM([Quantity]) as SumQty, AVG([Quantity]) as AvgQty,  
    SUM([Amount]) AS SumAmt, AVG([Amount]) AS AvgAmt,  
    'All Regions' as [Region]  
    FROM dbo.vTimeSeries   
    GROUP BY ReportingDate  
    ```  
  
9. <span data-ttu-id="91c1c-154">Klicken Sie mit der rechten Maustaste auf die `AllRegions` Tabelle, und wählen Sie **Daten durchsuchen**aus.</span><span class="sxs-lookup"><span data-stu-id="91c1c-154">Right-click the `AllRegions` table, and then select **Explore Data**.</span></span>  
  
###  <a name="to-create-the-series-data-for-cross-prediction"></a><a name="bkmk_CrossData"></a><span data-ttu-id="91c1c-155">So erstellen Sie die Reihen Daten für Kreuz Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="91c1c-155">To create the series data for cross-prediction</span></span>  
  
1.  <span data-ttu-id="91c1c-156">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Datenquellensichten**und wählen Sie dann **Neue Datenquellensicht**aus.</span><span class="sxs-lookup"><span data-stu-id="91c1c-156">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="91c1c-157">Treffen Sie im Datenquellensicht-Assistenten die folgende Auswahl:</span><span class="sxs-lookup"><span data-stu-id="91c1c-157">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="91c1c-158">**Datenquelle**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91c1c-158">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="91c1c-159">**Tabellen und Sichten auswählen**: keine Auswahl</span><span class="sxs-lookup"><span data-stu-id="91c1c-159">**Select Tables and Views**: Do not select any tables</span></span>  
  
     <span data-ttu-id="91c1c-160">**Name**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="91c1c-160">**Name**: `T1000 Pacific Region`</span></span>  
  
3.  <span data-ttu-id="91c1c-161">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="91c1c-161">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="91c1c-162">Klicken Sie mit der rechten Maustaste auf die leere Entwurfsoberfläche für **T1000 Pacific Region.dsv**und wählen Sie dann **Neue benannte Abfrage**aus.</span><span class="sxs-lookup"><span data-stu-id="91c1c-162">Right-click the empty design surface for **T1000 Pacific Region.dsv**, and then select **New Named Query**.</span></span>  
  
     <span data-ttu-id="91c1c-163">Das Dialogfeld **Benannte Abfrage erstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="91c1c-163">The **Create Named Query** dialog box appears.</span></span> <span data-ttu-id="91c1c-164">Geben Sie den Namen erneut ein und fügen Sie die folgende Beschreibung hinzu:</span><span class="sxs-lookup"><span data-stu-id="91c1c-164">Retype the name, and then add the following description:</span></span>  
  
     <span data-ttu-id="91c1c-165">**Name**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="91c1c-165">**Name**: `T1000 Pacific Region`</span></span>  
  
     <span data-ttu-id="91c1c-166">**Beschreibung**: \*\* `vTimeSeries` nach Region und Modell Filtern\*\*</span><span class="sxs-lookup"><span data-stu-id="91c1c-166">**Description**: **Filter`vTimeSeries`by region and model**</span></span>  
  
5.  <span data-ttu-id="91c1c-167">Geben Sie im Textbereich die folgende Abfrage ein, und klicken Sie dann auf "OK":</span><span class="sxs-lookup"><span data-stu-id="91c1c-167">In the text pane, type the following query, and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate, ModelRegion, Quantity, Amount  
    FROM dbo.vTimeSeries  
    WHERE (ModelRegion = N'T1000 Pacific')  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="91c1c-168">Da Sie Vorhersagen für jede Reihe getrennt erstellen müssen, könnten Sie den Abfragetext kopieren und als Textdatei speichern, damit Sie ihn für die andere Datenreihe erneut verwenden können.</span><span class="sxs-lookup"><span data-stu-id="91c1c-168">Since you will need to create predictions for each series separately, you might want to copy the query text and save it to a text file so that you can re-use it for the other data series.</span></span>  
  
6.  <span data-ttu-id="91c1c-169">Klicken Sie in der Entwurfs Oberfläche der Datenquellen Sicht mit der rechten Maustaste auf T1000 Pacific, und wählen Sie **Daten durchsuchen** , um zu überprüfen, ob die Daten ordnungsgemäß gefiltert wurden.</span><span class="sxs-lookup"><span data-stu-id="91c1c-169">In the Data Source View design surface, right-click T1000 Pacific, and then select **Explore Data** to verify that the data is filtered correctly.</span></span>  
  
     <span data-ttu-id="91c1c-170">Sie verwenden diese Daten als Eingabe in das Modell, wenn Sie Abfragen für Kreuzvorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="91c1c-170">You will use this data as the input to the model when creating cross-prediction queries.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="91c1c-171">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="91c1c-171">Next Task in Lesson</span></span>  
 [<span data-ttu-id="91c1c-172">Zeitreihen Vorhersagen mit aktualisierten Data &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="91c1c-172">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="91c1c-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91c1c-173">See Also</span></span>  
 <span data-ttu-id="91c1c-174">[Microsoft Time Series-Algorithmus](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="91c1c-174">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 <span data-ttu-id="91c1c-175">[Technische Referenz für den Microsoft Time Series-Algorithmus](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="91c1c-175">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="91c1c-176">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="91c1c-176">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  
