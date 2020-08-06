---
title: Erstellen von Vorhersagen (Tutorial zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a8410ed2-bb98-4d51-a9eb-b239be1201c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 456aec6c6b9d0d1a5d0ee1d9949507a37577130c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694885"
---
# <a name="creating-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="229b0-102">Erstellen von Vorhersagen (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="229b0-102">Creating Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="229b0-103">Nachdem Sie die Genauigkeit der Mining Modelle getestet haben und sich entschieden haben, dass Sie mit den Ergebnissen zufrieden sind, können Sie Vorhersagen generieren, indem Sie die Vorhersage Abfrage-Generator auf der Registerkarte **Mining Modellvorhersage** im Data Mining-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="229b0-103">After you have tested the accuracy of your mining models and decided that you are satisfied with the results, you can then generate predictions by using the Prediction Query Builder on the **Mining Model Prediction** tab in the Data Mining Designer.</span></span>  
  
 <span data-ttu-id="229b0-104">Der Generator für Vorhersageabfragen verfügt über drei Sichten.</span><span class="sxs-lookup"><span data-stu-id="229b0-104">The Prediction Query Builder has three views.</span></span> <span data-ttu-id="229b0-105">Mit den **Entwurfs** -und **Abfrage** Ansichten können Sie die Abfrage erstellen und untersuchen.</span><span class="sxs-lookup"><span data-stu-id="229b0-105">With the **Design** and **Query** views, you can build and examine your query.</span></span> <span data-ttu-id="229b0-106">Anschließend können Sie die Abfrage ausführen und die Ergebnisse in der **Ergebnis** Ansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="229b0-106">You can then run the query and view the results in the **Result** view.</span></span>  
  
 <span data-ttu-id="229b0-107">Alle Vorhersageabfragen verwenden die DMX-Programmiersprache, die Kurzform für Data Mining Extensions (Data Mining-Erweiterungen).</span><span class="sxs-lookup"><span data-stu-id="229b0-107">All prediction queries use DMX, which is short for the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="229b0-108">DMX hat eine ähnliche Syntax wie T-SQL, wird jedoch für Abfragen von Data Mining-Objekten verwendet.</span><span class="sxs-lookup"><span data-stu-id="229b0-108">DMX has syntax like that of T-SQL but is used for queries against data mining objects.</span></span> <span data-ttu-id="229b0-109">Obwohl die DMX-Syntax nicht kompliziert ist, wird die Auswahl von Eingaben und buildausdrücken mit einem Abfrage-Generator wie diesem oder dem in den [SQL Server Data Mining-Add-Ins für Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md)erheblich vereinfacht. Daher wird dringend empfohlen, die Grundlagen zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="229b0-109">Although DMX syntax is not complicated, using a query builder like this one, or the one in the [SQL Server Data Mining Add-Ins for Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), makes it much easier to select inputs and build expressions, so we highly recommend that you learn the basics.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="229b0-110">Erstellen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="229b0-110">Creating the Query</span></span>  
 <span data-ttu-id="229b0-111">Der erste Schritt beim Erstellen einer Vorhersageabfrage ist die Auswahl eines Miningmodells und einer Eingabetabelle.</span><span class="sxs-lookup"><span data-stu-id="229b0-111">The first step in creating a prediction query is to select a mining model and input table.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="229b0-112">So wählen Sie ein Modell und eine Eingabetabelle aus</span><span class="sxs-lookup"><span data-stu-id="229b0-112">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="229b0-113">Klicken Sie im Data Mining-Designer auf der Registerkarte **Mining Modellvorhersage** im Feld **Mining Modell** auf **Modell auswählen**.</span><span class="sxs-lookup"><span data-stu-id="229b0-113">On the **Mining Model Prediction** tab of Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="229b0-114">Navigieren Sie im Dialogfeld **Mining Modell auswählen** durch die Struktur zur Ziel- **Mailing** -Struktur, erweitern Sie die Struktur, wählen Sie aus `TM_Decision_Tree` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="229b0-114">In the **Select Mining Model** dialog box, navigate through the tree to the **Targeted Mailing** structure, expand the structure, select `TM_Decision_Tree`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="229b0-115">Klicken Sie im Feld **Eingabe Tabelle (n) auswählen** auf **Fall Tabelle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="229b0-115">In the **Select Input Table(s)** box, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="229b0-116">Wählen Sie im Dialogfeld **Tabelle auswählen** in der Liste **Datenquelle** die Datenquellen Sicht aus [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="229b0-116">In the **Select Table** dialog box, in the **Data Source** list, select the data source view [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
5.  <span data-ttu-id="229b0-117">Wählen Sie unter **Tabellen-/Sichtname**die Tabelle **ProspectiveBuyer (dbo)** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="229b0-117">In **Table/View Name**, select the **ProspectiveBuyer (dbo)** table, and then click **OK**.</span></span>  
  
     <span data-ttu-id="229b0-118">Die `ProspectiveBuyer` Tabelle ähnelt am ehesten der Fall Tabelle **vTargetMail** .</span><span class="sxs-lookup"><span data-stu-id="229b0-118">The `ProspectiveBuyer` table most closely resembles the **vTargetMail** case table.</span></span>  
  
## <a name="mapping-the-columns"></a><span data-ttu-id="229b0-119">Zuordnen der Spalten</span><span class="sxs-lookup"><span data-stu-id="229b0-119">Mapping the Columns</span></span>  
 <span data-ttu-id="229b0-120">Wenn Sie die Eingabetabelle ausgewählt haben, erstellt der Generator für Vorhersageabfragen eine Standardzuordnung zwischen dem Miningmodell und der Eingabetabelle, die auf den Spaltennamen basiert.</span><span class="sxs-lookup"><span data-stu-id="229b0-120">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="229b0-121">Mindestens eine Spalte in der Struktur muss mit einer Spalte in den externen Daten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="229b0-121">At least one column from the structure must match a column in the external data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="229b0-122">Die Daten, die Sie zur Ermittlung der Genauigkeit der Modelle verwenden, müssen eine Spalte enthalten, die der vorhersagbaren Spalte zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="229b0-122">The data that you use to determine the accuracy of the models must contain a column that can be mapped to the predictable column.</span></span> <span data-ttu-id="229b0-123">Wenn so eine Spalte nicht vorhanden ist, können Sie eine Spalte mit leeren Werten erstellen. Sie muss jedoch den gleichen Datentyp wie die vorhersagbare Spalte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="229b0-123">If such a column does not exist, you can create one with empty values, but it must have the same data type as the predictable column.</span></span>  
  
#### <a name="to-map-the-inputs-to-the-model"></a><span data-ttu-id="229b0-124">So ordnen Sie dem Modell die Eingaben zu</span><span class="sxs-lookup"><span data-stu-id="229b0-124">To map the inputs to the model</span></span>  
  
1.  <span data-ttu-id="229b0-125">Klicken Sie mit der rechten Maustaste auf die Zeilen, die das Fenster **Mining Modell** mit dem Fenster **Eingabe Tabelle auswählen** verbinden, und wählen Sie **Verbindungen ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-125">Right-click the lines connecting the **Mining Model** window to the **Select Input Table** window, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="229b0-126">Beachten Sie, dass nicht jede Spalte zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="229b0-126">Notice that not every column is mapped.</span></span> <span data-ttu-id="229b0-127">Wir fügen Zuordnungen für mehrere **Tabellen Spalten**hinzu.</span><span class="sxs-lookup"><span data-stu-id="229b0-127">We will add mappings for several **Table Columns**.</span></span> <span data-ttu-id="229b0-128">Wir generieren außerdem eine neue Geburtsdatumsspalte, die auf der aktuellen Datumsspalte basiert, um die Übereinstimmung zwischen den Spalten zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="229b0-128">We will also generate a new birth date column based on the current date column, so that the columns match better.</span></span>  
  
2.  <span data-ttu-id="229b0-129">Klicken Sie unter **Tabellenspalte**auf die `Bike Buyer` Zelle, und wählen Sie ProspectiveBuyer. Unknown aus der Dropdown Liste aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-129">Under **Table Column**, click the `Bike Buyer` cell and select ProspectiveBuyer.Unknown from the dropdown.</span></span>  
  
     <span data-ttu-id="229b0-130">Dies ordnet die vorhersagbare Spalte [Bike Buyer] einer Eingabetabellenspalte zu.</span><span class="sxs-lookup"><span data-stu-id="229b0-130">This maps the predictable column, [Bike Buyer], to an input table column.</span></span>  
  
3.  <span data-ttu-id="229b0-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="229b0-131">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="229b0-132">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf die gewünschte **Mailing** Datenquellen Sicht, und wählen Sie **Ansicht-Designer**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-132">In **Solution Explorer**, right-click the **Targeted Mailing** data source view and select **View Designer**.</span></span>  
  
5.  <span data-ttu-id="229b0-133">Klicken Sie mit der rechten Maustaste auf die Tabelle ProspectiveBuyer, und wählen Sie **neue benannte Berechnung**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-133">Right-click the table, ProspectiveBuyer, and select **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="229b0-134">Geben Sie im Dialogfeld **benannte Berechnung erstellen** im Feld **Spaltenname den Namen**ein `calcAge` .</span><span class="sxs-lookup"><span data-stu-id="229b0-134">In the **Create Named Calculation** dialog box, for **Column name**, type `calcAge`.</span></span>  
  
7.  <span data-ttu-id="229b0-135">Geben **Description**Sie als Beschreibung **Age date based on BirthDate**ein.</span><span class="sxs-lookup"><span data-stu-id="229b0-135">For **Description**, type **Calculate age based on birthdate**.</span></span>  
  
8.  <span data-ttu-id="229b0-136">Geben Sie im Feld **Ausdruck** ein, `DATEDIFF(YYYY,[BirthDate],getdate())` und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="229b0-136">In the **Expression** box, type `DATEDIFF(YYYY,[BirthDate],getdate())` and then click **OK**.</span></span>  
  
     <span data-ttu-id="229b0-137">Da die Eingabe Tabelle keine **Alters** Spalte enthält, die der Tabelle im Modell entspricht, können Sie diesen Ausdruck verwenden, um das Kunden Alter anhand der Spalte BirthDate in der Eingabe Tabelle zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="229b0-137">Because the input table has no **Age** column corresponding to the one in the model, you can use this expression to calculate customer age from the BirthDate column in the input table.</span></span> <span data-ttu-id="229b0-138">Da **Age** als die einflussreichste Spalte für die Vorhersage von Fahrrad Käufen identifiziert wurde, muss es sowohl im Modell als auch in der Eingabe Tabelle vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="229b0-138">Since **Age** was identified as the most influential column for predicting bike buying, it must exist in both the model and in the input table.</span></span>  
  
9. <span data-ttu-id="229b0-139">Wählen Sie im Data Mining-Designer die Registerkarte **Mining Modellvorhersage** aus, und öffnen Sie das Fenster **Verbindungen ändern** erneut.</span><span class="sxs-lookup"><span data-stu-id="229b0-139">In Data Mining Designer, select the **Mining Model Prediction** tab and re-open the **Modify Connections** window.</span></span>  
  
10. <span data-ttu-id="229b0-140">Klicken Sie unter **Tabellenspalte**auf die Zelle **Age** , und wählen Sie ProspectiveBuyer. CalcAge aus der Dropdown Liste aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-140">Under **Table Column**, click the **Age** cell and select ProspectiveBuyer.calcAge from the dropdown.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="229b0-141">Wenn die Spalte in der Liste nicht angezeigt wird, müssen Sie u. U. die Definition der im Designer geladenen Datenquellensicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="229b0-141">If you do not see the column in the list, you might have to refresh the definition of the data source view that is loaded in the designer.</span></span> <span data-ttu-id="229b0-142">Wählen Sie hierzu im Menü **Datei** die Option **Alle speichern**aus, und schließen Sie dann das Projekt im Designer, und öffnen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="229b0-142">To do this, from the **File** menu, select **Save all**, and then close and re-open the project in the designer.</span></span>  
  
11. <span data-ttu-id="229b0-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="229b0-143">Click **OK**.</span></span>  
  
## <a name="designing-the-prediction-query"></a><span data-ttu-id="229b0-144">Entwerfen der Vorhersage Abfrage</span><span class="sxs-lookup"><span data-stu-id="229b0-144">Designing the Prediction Query</span></span>  
  
1.  <span data-ttu-id="229b0-145">Die erste Schaltfläche auf der Symbolleiste der Registerkarte **Mining Modellvorhersage** ist die Schaltfläche **zur Entwurfs Sicht wechseln/zur Ergebnis Sicht wechseln/zur Abfrage Ansicht wechseln** .</span><span class="sxs-lookup"><span data-stu-id="229b0-145">The first button on the toolbar of the **Mining Model Prediction** tab is the **Switch to design view / Switch to result view / Switch to query view** button.</span></span> <span data-ttu-id="229b0-146">Klicken Sie auf der Schaltfläche auf den Pfeil nach unten, und wählen Sie **Entwurf**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-146">Click the down arrow on this button, and select **Design**.</span></span>  
  
2.  <span data-ttu-id="229b0-147">Klicken Sie im Raster auf der Registerkarte **Mining Modellvorhersage** auf die Zelle in der ersten leeren Zeile in der Spalte **Quelle** , und wählen Sie dann **Vorhersagefunktion**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-147">In the grid on the **Mining Model Prediction** tab, click the cell in the first empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
3.  <span data-ttu-id="229b0-148">Wählen Sie in der Zeile **Vorhersagefunktion** in der Spalte **Feld** den Wert aus `PredictProbability` .</span><span class="sxs-lookup"><span data-stu-id="229b0-148">In the **Prediction Function** row, in the **Field** column, select `PredictProbability`.</span></span>  
  
     <span data-ttu-id="229b0-149">Geben Sie in der Spalte **Alias** der gleichen Zeile die **Wahrscheinlichkeit für Ergebnis**ein.</span><span class="sxs-lookup"><span data-stu-id="229b0-149">In the **Alias** column of the same row, type **Probability of result**.</span></span>  
  
4.  <span data-ttu-id="229b0-150">Wählen Sie im obigen Fenster **Mining Modell** die Option [Bike Buyer] aus, und ziehen Sie Sie in die Zelle **Kriterium/Argument** .</span><span class="sxs-lookup"><span data-stu-id="229b0-150">From the **Mining Model** window above, select and drag [Bike Buyer] into the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="229b0-151">Wenn Sie los gehen, [TM_Decision_Tree]. [Bike Buyer] wird in der Zelle " **Kriterium/Argument** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="229b0-151">When you let go, [TM_Decision_Tree].[Bike Buyer] appears in the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="229b0-152">Hierdurch wird die Zielspalte für die `PredictProbability`-Funktion angegeben.</span><span class="sxs-lookup"><span data-stu-id="229b0-152">This specifies the target column for the `PredictProbability` function.</span></span> <span data-ttu-id="229b0-153">Weitere Informationen zu Funktionen finden Sie unter [Data Mining-Erweiterungen &#40;DMX-&#41; Funktionsreferenz](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="229b0-153">For more information about functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
5.  <span data-ttu-id="229b0-154">Klicken Sie in der Spalte **Quelle** auf die nächste leere Zeile, und wählen Sie dann **TM_Decision_Tree** Mining Modell aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-154">Click the next empty row in the **Source** column, and then select **TM_Decision_Tree** mining model.</span></span>  
  
6.  <span data-ttu-id="229b0-155">`TM_Decision_Tree`Wählen Sie in der Zeile in der Spalte **Feld** den Wert aus `Bike Buyer` .</span><span class="sxs-lookup"><span data-stu-id="229b0-155">In the `TM_Decision_Tree` row, in the **Field** column, select `Bike Buyer`.</span></span>  
  
7.  <span data-ttu-id="229b0-156">Geben Sie in der `TM_Decision_Tree` Zeile in der Spalte **Kriterium/Argument** den Namen ein `=1` .</span><span class="sxs-lookup"><span data-stu-id="229b0-156">In the `TM_Decision_Tree` row, in the **Criteria/Argument** column, type `=1`.</span></span>  
  
8.  <span data-ttu-id="229b0-157">Klicken Sie in der Spalte **Quelle** auf die nächste leere Zeile, und wählen Sie dann **ProspectiveBuyer Table**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-157">Click the next empty row in the **Source** column, and then select **ProspectiveBuyer table**.</span></span>  
  
9. <span data-ttu-id="229b0-158">`ProspectiveBuyer`Wählen Sie in der Zeile in der Spalte **Feld** die Option **ProspectiveBuyerKey**aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-158">In the `ProspectiveBuyer` row, in the **Field** column, select **ProspectiveBuyerKey**.</span></span>  
  
     <span data-ttu-id="229b0-159">Damit wird der Vorhersageabfrage ein eindeutiger Bezeichner hinzugefügt, sodass Sie feststellen können, wer wahrscheinlich ein Fahrrad kaufen wird und wer nicht.</span><span class="sxs-lookup"><span data-stu-id="229b0-159">This adds the unique identifier to the prediction query so that you can identify who is and who is not likely to buy a bicycle.</span></span>  
  
10. <span data-ttu-id="229b0-160">Fügen Sie dem Raster fünf weitere Zeilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="229b0-160">Add five more rows to the grid.</span></span> <span data-ttu-id="229b0-161">Wählen Sie für jede Zeile **ProspectiveBuyer Table** als **Quelle** aus, und fügen Sie dann die folgenden Spalten in den **Feld** Zellen hinzu:</span><span class="sxs-lookup"><span data-stu-id="229b0-161">For each row, select **ProspectiveBuyer table** as the **Source** and then add the following columns in the **Field** cells:</span></span>  
  
    -   <span data-ttu-id="229b0-162">calcAge</span><span class="sxs-lookup"><span data-stu-id="229b0-162">calcAge</span></span>  
  
    -   <span data-ttu-id="229b0-163">LastName</span><span class="sxs-lookup"><span data-stu-id="229b0-163">LastName</span></span>  
  
    -   <span data-ttu-id="229b0-164">FirstName</span><span class="sxs-lookup"><span data-stu-id="229b0-164">FirstName</span></span>  
  
    -   <span data-ttu-id="229b0-165">AddressLine1</span><span class="sxs-lookup"><span data-stu-id="229b0-165">AddressLine1</span></span>  
  
    -   <span data-ttu-id="229b0-166">AddressLine2</span><span class="sxs-lookup"><span data-stu-id="229b0-166">AddressLine2</span></span>  
  
 <span data-ttu-id="229b0-167">Führen Sie zum Schluss die Abfrage aus, und durchsuchen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="229b0-167">Finally, run the query and browse the results.</span></span>  
  
 <span data-ttu-id="229b0-168">Die **Vorhersage Abfrage-Generator** enthält auch die folgenden Steuerelemente:</span><span class="sxs-lookup"><span data-stu-id="229b0-168">The **Prediction Query Builder** also includes these controls:</span></span>  
  
-   <span data-ttu-id="229b0-169">Kontrollkästchen **anzeigen**</span><span class="sxs-lookup"><span data-stu-id="229b0-169">**Show** check box</span></span>  
  
     <span data-ttu-id="229b0-170">Ermöglicht das Entfernen von Klauseln aus der Abfrage, ohne sie aus dem Designer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="229b0-170">Lets you remove clauses from the query without having to delete them from the designer.</span></span> <span data-ttu-id="229b0-171">Diese Funktion kann bei komplexen Abfragen hilfreich sein, wenn Sie die Syntax beibehalten und keine DMX kopieren und in das Fenster einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="229b0-171">This can be useful when you are working with complex queries and want to preserve syntax without having to copy and paste DMX into the window.</span></span>  
  
-   <span data-ttu-id="229b0-172">**Gruppe**</span><span class="sxs-lookup"><span data-stu-id="229b0-172">**Group**</span></span>  
  
     <span data-ttu-id="229b0-173">Fügt eine öffnende (linke) Klammer am Anfang der ausgewählten Zeile oder eine schließende (rechte) Klammer am Ende der aktuellen Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="229b0-173">Inserts an opening (left) parentheses at the beginning of the selected line, or inserts a closing (right) parenthesis at the end of the current line.</span></span>  
  
-   <span data-ttu-id="229b0-174">**und/oder**</span><span class="sxs-lookup"><span data-stu-id="229b0-174">**AND/OR**</span></span>  
  
     <span data-ttu-id="229b0-175">Fügt den `AND`-Operator oder `OR`-Operator unmittelbar nach der aktuellen Funktion oder der Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="229b0-175">Inserts the  `AND` operator or the `OR` operator immediately after the current function or column.</span></span>  
  
#### <a name="to-run-the-query-and-view-results"></a><span data-ttu-id="229b0-176">So führen Sie die Abfrage aus und zeigen die Ergebnisse an</span><span class="sxs-lookup"><span data-stu-id="229b0-176">To run the query and view results</span></span>  
  
1.  <span data-ttu-id="229b0-177">Wählen Sie auf der Registerkarte **Mining Modellvorhersage** die **Ergebnis** Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="229b0-177">In the **Mining Model Prediction** tab, select the **Result** button.</span></span>  
  
2.  <span data-ttu-id="229b0-178">Nachdem die Abfrage ausgeführt wurde und die Ergebnisse angezeigt werden, können Sie die Ergebnisse überprüfen.</span><span class="sxs-lookup"><span data-stu-id="229b0-178">After the query runs and the results are displayed, you can review the results.</span></span>  
  
     <span data-ttu-id="229b0-179">Auf der Registerkarte **Mining Modellvorhersage** werden Kontaktinformationen für potenzielle Kunden angezeigt, die wahrscheinlich Fahrrad Käufer sind.</span><span class="sxs-lookup"><span data-stu-id="229b0-179">The **Mining Model Prediction** tab displays contact information for potential customers who are likely to be bike buyers.</span></span> <span data-ttu-id="229b0-180">Die **Wahrscheinlichkeit der Ergebnis** Spalte gibt die Wahrscheinlichkeit an, dass die Vorhersage richtig ist.</span><span class="sxs-lookup"><span data-stu-id="229b0-180">The **Probability of result** column indicates the probability of the prediction being correct.</span></span> <span data-ttu-id="229b0-181">Anhand dieser Ergebnisse können Sie entscheiden, welche potenziellen Kunden beim Targeted Mailing angeschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="229b0-181">You can use these results to determine which potential customers to target for the mailing.</span></span>  
  
3.  <span data-ttu-id="229b0-182">An diesem Punkt können Sie die Ergebnisse speichern.</span><span class="sxs-lookup"><span data-stu-id="229b0-182">At this point, you can save the results.</span></span> <span data-ttu-id="229b0-183">Hierfür stehen drei Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="229b0-183">You have three options:</span></span>  
  
    -   <span data-ttu-id="229b0-184">Klicken Sie mit der rechten Maustaste auf eine Daten Zeile in den Ergebnissen, und wählen Sie **Kopieren** aus, um nur diesen Wert (und die Spaltenüberschrift) in der Zwischenablage zu speichern.</span><span class="sxs-lookup"><span data-stu-id="229b0-184">Right-click a row of data in the results, and select **Copy** to save just that value (and the column heading) to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="229b0-185">Klicken Sie mit der rechten Maustaste auf eine beliebige Zeile in den Ergebnissen, und wählen Sie **Alle kopieren** , um das gesamte Resultset einschließlich der Spaltenüberschriften in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="229b0-185">Right-click any row in the results, and select **Copy All** to copy the entire result set, including column headings, to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="229b0-186">Klicken Sie auf **Abfrageergebnis speichern** , um die Ergebnisse wie folgt direkt in einer Datenbank zu speichern:</span><span class="sxs-lookup"><span data-stu-id="229b0-186">Click **Save query result** to save the results directly to a database as follows:</span></span>  
  
        1.  <span data-ttu-id="229b0-187">Wählen Sie im Dialogfeld **Ergebnis der Data Mining-Abfrage speichern** eine Datenquelle aus, oder definieren Sie eine neue Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="229b0-187">In the **Save Data Mining Query Result** dialog box, select a data source, or define a new data source.</span></span>  
  
        2.  <span data-ttu-id="229b0-188">Geben Sie einen Namen für die Tabelle ein, in die die Abfrageergebnisse eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="229b0-188">Type a name for the table that will contain the query results.</span></span>  
  
        3.  <span data-ttu-id="229b0-189">Verwenden Sie die Option zur Datenquellen Sicht **Hinzufügen**, um die Tabelle zu erstellen und zu einer vorhandenen Datenquellen Sicht hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="229b0-189">Use the option, **Add to DSV**, to create the table and add it to an existing data source view.</span></span> <span data-ttu-id="229b0-190">Dies ist hilfreich, wenn Sie alle verknüpften Tabellen für ein Modell (z. b. Trainingsdaten, Vorhersage Quelldaten und Abfrageergebnisse) in derselben Datenquellen Sicht beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="229b0-190">This is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source view.</span></span>  
  
        4.  <span data-ttu-id="229b0-191">Verwenden Sie die Option über **schreiben, falls vorhanden**, um eine vorhandene Tabelle mit den neuesten Ergebnissen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="229b0-191">Use the option, **Overwrite if exists**, to update an existing table with the latest results.</span></span>  
  
             <span data-ttu-id="229b0-192">Sie müssen die Option verwenden, um die Tabelle zu überschreiben, falls Sie der Vorhersageabfrage Spalten hinzugefügt, die Namen oder Datentypen von Spalten in der Vorhersageabfrage geändert oder ALTER-Anweisungen für die Zieltabelle ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="229b0-192">You must use the option to overwrite the table if you have added any columns to the prediction query, changed the names or data types of any columns in the prediction query, or if you have run any ALTER statements on the destination table.</span></span>  
  
             <span data-ttu-id="229b0-193">Wenn mehrere Spalten denselben Namen aufweisen (z. b. den standardmäßigen Spaltennamen **Ausdruck**), müssen Sie außerdem einen Alias für die Spalten mit doppelten Namen erstellen, oder es wird ein Fehler ausgelöst, wenn der Designer versucht, die Ergebnisse in SQL Server zu speichern.</span><span class="sxs-lookup"><span data-stu-id="229b0-193">Also, if multiple columns have the same name (for example, the default column name **Expression**) you must create an alias for the columns with duplicate names, or an error will be raised when the designer tries to save the results to SQL Server.</span></span> <span data-ttu-id="229b0-194">Dies liegt daran, dass mehrere Spalten unter SQL Server nicht über denselben Namen verfügen dürfen.</span><span class="sxs-lookup"><span data-stu-id="229b0-194">The reason is that SQL Server does not allow multiple columns to have the same name.</span></span>  
  
             <span data-ttu-id="229b0-195">Weitere Informationen finden Sie unter [Dialog Feld "Ergebnisse der Data Mining-Abfrage speichern" &#40;Mining Modell-Vorhersage Ansicht&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span><span class="sxs-lookup"><span data-stu-id="229b0-195">For more information, see [Save Data Mining Query Result Dialog Box &#40;Mining Model Prediction View&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="229b0-196">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="229b0-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="229b0-197">Verwenden von Drillthrough für Strukturdaten &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="229b0-197">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="229b0-198">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="229b0-198">See Also</span></span>  
 [<span data-ttu-id="229b0-199">erstellt eine Vorhersage mithilfe des Generators für Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="229b0-199">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
