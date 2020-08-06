---
title: Erstellen einer Vorhersage Abfrage mithilfe der Vorhersage Abfrage-Generator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
ms.openlocfilehash: 13f39de4085cb74949e9540570d574c09e72ee27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609536"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a><span data-ttu-id="201da-102">erstellt eine Vorhersage mithilfe des Generators für Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="201da-102">Create a Prediction Query Using the Prediction Query Builder</span></span>
  <span data-ttu-id="201da-103">Sie können Vorhersageabfragen erstellen, indem Sie entweder eine Data Mining-Projektmappe in BI Development Studio erstellen oder indem Sie mit der rechten Maustaste auf ein bereits vorhandenes Miningmodell in SQL Server Management Studio klicken und anschließend die Option **Vorhersageabfrage erstellen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="201da-103">You can create prediction queries either while you are building a data mining solution in BI Development Studio, or by right-clicking an existing mining model in SQL Server Management Studio, and then choosing the option, **Build Prediction Query**.</span></span>  
  
 <span data-ttu-id="201da-104">Der **Generator für Vorhersageabfragen** verfügt über die folgenden drei Entwurfsmodi, zwischen denen Sie wechseln können, indem Sie auf die Symbole in der Ecke links oben klicken.</span><span class="sxs-lookup"><span data-stu-id="201da-104">The **Prediction Query Builder** has the following three design modes, which you can switch among by clicking the icons in the upper-left corner.</span></span>  
  
-   <span data-ttu-id="201da-105">**Design**</span><span class="sxs-lookup"><span data-stu-id="201da-105">**Design**</span></span>  
  
-   <span data-ttu-id="201da-106">**Abfrage**</span><span class="sxs-lookup"><span data-stu-id="201da-106">**Query**</span></span>  
  
-   <span data-ttu-id="201da-107">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="201da-107">**Result**</span></span>  
  
 <span data-ttu-id="201da-108">Mit dem**Entwurfsmodus** können Sie eine Vorhersageabfrage erstellen, indem Sie die Eingabedaten auswählen, dem Modell die Daten zuordnen und anschließend die Vorhersagefunktionen den Anweisungen hinzufügen, die Sie durch die Verwendung des Rasters erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="201da-108">**Design** mode lets you build a prediction query by choosing input data, mapping the data to the model, and then adding prediction functions into statements you build by using the grid.</span></span> <span data-ttu-id="201da-109">Der Entwurfsbereich enthält diese Bausteine:</span><span class="sxs-lookup"><span data-stu-id="201da-109">The design grid contains these building blocks:</span></span>  
  
 <span data-ttu-id="201da-110">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="201da-110">**Source**</span></span>  
 <span data-ttu-id="201da-111">Wählen Sie die Quelle der neuen Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="201da-111">Choose the source of the new column.</span></span> <span data-ttu-id="201da-112">Sie können Spalten aus dem Miningmodell, in der Datenquellenansicht enthaltene Eingabetabellen, eine Vorhersagefunktion oder einen benutzerdefinierten Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="201da-112">You can use columns from the mining model, input tables included in the data source view, a prediction function, or a customized expression.</span></span>  
  
 <span data-ttu-id="201da-113">**Feld**</span><span class="sxs-lookup"><span data-stu-id="201da-113">**Field**</span></span>  
 <span data-ttu-id="201da-114">Bestimmt die spezielle Spalte oder Funktion, die mit der Auswahl in der Spalte **Quelle** verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="201da-114">Determines the specific column or function that is associated with the selection in the **Source** column.</span></span>  
  
 <span data-ttu-id="201da-115">**Alias**</span><span class="sxs-lookup"><span data-stu-id="201da-115">**Alias**</span></span>  
 <span data-ttu-id="201da-116">Bestimmt, wie die Spalte im Resultset benannt wird.</span><span class="sxs-lookup"><span data-stu-id="201da-116">Determines how the column is to be named in the result set.</span></span>  
  
 <span data-ttu-id="201da-117">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="201da-117">**Show**</span></span>  
 <span data-ttu-id="201da-118">Bestimmt, ob die Auswahl in der Spalte **Quelle** in den Ergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="201da-118">Determines whether the selection in the **Source** column is displayed in the results.</span></span>  
  
 <span data-ttu-id="201da-119">**Gruppe**</span><span class="sxs-lookup"><span data-stu-id="201da-119">**Group**</span></span>  
 <span data-ttu-id="201da-120">Verwendet die Spalte **Und/Oder** , um Ausdrücke mithilfe von Klammern zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="201da-120">Works with the **And/Or** column to group expressions together by using parentheses.</span></span> <span data-ttu-id="201da-121">Beispielsweise (expr1 oder expr2) und expr3.</span><span class="sxs-lookup"><span data-stu-id="201da-121">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="201da-122">**Und/oder**</span><span class="sxs-lookup"><span data-stu-id="201da-122">**And/Or**</span></span>  
 <span data-ttu-id="201da-123">Erstellt einen logischen Ausdruck in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="201da-123">Creates logic in the query.</span></span> <span data-ttu-id="201da-124">Beispielsweise (expr1 oder expr2) und expr3.</span><span class="sxs-lookup"><span data-stu-id="201da-124">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="201da-125">**Kriterium/Argument**</span><span class="sxs-lookup"><span data-stu-id="201da-125">**Criteria/Argument**</span></span>  
 <span data-ttu-id="201da-126">Gibt eine Bedingung oder einen benutzerdefinierten Ausdruck an, der auf die Spalte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="201da-126">Specifies a condition or user expression that applies to the column.</span></span> <span data-ttu-id="201da-127">Sie können Spalten aus den Tabelle in die Zelle ziehen.</span><span class="sxs-lookup"><span data-stu-id="201da-127">You can drag columns from the tables to the cell.</span></span>  
  
 <span data-ttu-id="201da-128">Im**Abfragemodus** steht ein Text-Editor bereit, mit dem Sie direkt auf die Data Mining-Erweiterungssprache (DMX) zugreifen können, und mit dem Sie Eingabedaten und Modellspalten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="201da-128">**Query** mode provides a text editor that gives you direct access to the Data Mining Extensions (DMX) language, along with a view of the input data and model columns.</span></span> <span data-ttu-id="201da-129">Wenn Sie den **Abfragemodus** auswählen, wird das Raster, mit dessen Hilfe Sie die Abfrage definiert haben, durch einen einfachen Texteditor ersetzt.</span><span class="sxs-lookup"><span data-stu-id="201da-129">When you select **Query** mode, the grid that you used to define the query is replaced by a basic text editor.</span></span> <span data-ttu-id="201da-130">Sie können diesen Editor verwenden, um von Ihnen erstellte Abfragen zu kopieren und zu speichern oder um sie in vorhandene DMX-Abfragen aus der Zwischenablage einzufügen und sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="201da-130">You can use this editor to copy and save queries you have composed, or to paste in existing DMX queries and from the Clipboard and run them.</span></span>  
  
 <span data-ttu-id="201da-131">In der**Ergebnissicht** werden die aktuelle Abfrage ausgeführt und die Ergebnisse in einem Raster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="201da-131">**Result** view runs the current query and displays the results in a grid.</span></span> <span data-ttu-id="201da-132">Wenn sich die zugrunde liegenden Daten geändert haben und Sie die Abfrage erneut ausführen möchten, klicken Sie auf der Statusleiste auf die Schaltfläche zum Abspielen.</span><span class="sxs-lookup"><span data-stu-id="201da-132">If the underlying data has changed and you want to rerun the query, click the Play button in the status bar</span></span>  
  
 <span data-ttu-id="201da-133">Sie können eine Data Mining-Abfrage entwerfen, indem Sie die visuellen Tools und den Texteditor zusammen verwenden.</span><span class="sxs-lookup"><span data-stu-id="201da-133">You can design a data mining query by using a combination of the visual tools and the text editor.</span></span> <span data-ttu-id="201da-134">Wenn Sie im Texteditor Änderungen an der Abfrage vornehmen und zurück zur **Entwurfsansicht** wechseln, gehen alle Änderungen verloren. Die Abfragen werden dann zur ursprünglichen Abfrage zurückgesetzt, die mit dem Generator für Vorhersageabfragen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="201da-134">If you type changes to the query in the text editor and switch back to the **Design** view, all the changes are lost, and the query reverts to the original query created by Prediction Query Builder This topic walks you through use of the graphical query builder.</span></span>  
  
### <a name="to-create-a-prediction-query"></a><span data-ttu-id="201da-135">So erstellen Sie eine Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="201da-135">To create a prediction query</span></span>  
  
1.  <span data-ttu-id="201da-136">Klicken Sie auf die **Miningmodellvorhersage** -Registerkarte im Data Mining-Designer.</span><span class="sxs-lookup"><span data-stu-id="201da-136">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="201da-137">Klicken Sie in der **Miningmodell** -Tabelle auf **Modell auswählen** .</span><span class="sxs-lookup"><span data-stu-id="201da-137">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="201da-138">Das Dialogfeld **Miningmodell auswählen** wird geöffnet. Es zeigt alle Miningstrukturen an, die im aktuellen Projekt vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="201da-138">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
3.  <span data-ttu-id="201da-139">Wählen Sie das Modell aus, für das Sie eine Vorhersage erstellen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="201da-139">Select the model on which you want to create a prediction, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="201da-140">Klicken Sie in der **Eingabetabelle(n) auswählen** -Tabelle auf **Falltabelle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="201da-140">On the **Select Input Table(s)** table, click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="201da-141">Das Dialogfeld **Tabelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="201da-141">The **Select Table** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="201da-142">Wählen Sie in der Liste **Datenquelle** die Datenquelle aus, die die Daten enthält, mit denen eine Vorhersage erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="201da-142">In the **Data Source** list, select the data source that contains the data on which to create a prediction.</span></span>  
  
6.  <span data-ttu-id="201da-143">Wählen Sie im Feld **Tabellen-/Sichtname** die Tabelle aus, die die Daten enthält, mit denen eine Vorhersage erstellt werden soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="201da-143">In the **Table/View Name** box, select the table that contains the data on which to create a prediction, and then click **OK**.</span></span>  
  
     <span data-ttu-id="201da-144">Wenn Sie die Eingabetabelle ausgewählt haben, erstellt der Generator für Vorhersageabfragen eine Standardzuordnung zwischen dem Miningmodell und der Eingabetabelle, die auf den Spaltennamen basiert.</span><span class="sxs-lookup"><span data-stu-id="201da-144">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="201da-145">Um eine Zuordnung zu löschen, markieren Sie die Linie, die die Spalte der Tabelle **Miningmodell** mit der Spalte der Tabelle **Eingabetabelle(n) auswählen** verbindet, und drücken Sie dann ENTF.</span><span class="sxs-lookup"><span data-stu-id="201da-145">To delete a mapping, click to select the line that links the column in the **Mining Model** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span> <span data-ttu-id="201da-146">Sie können Zuordnungen auch manuell erstellen, indem Sie in der **Eingabetabelle(n) auswählen** -Tabelle auf eine Spalte klicken und diese dann in die **Miningmodell** -Tabelle auf die entsprechende Spalte ziehen.</span><span class="sxs-lookup"><span data-stu-id="201da-146">You can also manually create mappings by clicking a column in the **Select Input Table(s)** table and dragging it onto the corresponding column in the **Mining Model** table.</span></span>  
  
7.  <span data-ttu-id="201da-147">Fügen Sie dem Raster des Generators für Vorhersageabfragen eine beliebige Kombination der folgenden drei Arten von Informationen hinzu:</span><span class="sxs-lookup"><span data-stu-id="201da-147">Add any combination of the following three types of information to the Prediction Query Builder grid:</span></span>  
  
    -   <span data-ttu-id="201da-148">Vorhersagbare Spalten aus dem Feld **Miningmodell** .</span><span class="sxs-lookup"><span data-stu-id="201da-148">Predictable columns from the **Mining Model** box.</span></span>  
  
    -   <span data-ttu-id="201da-149">Eine beliebige Kombination aus Eingabespalten aus dem Feld **Eingabetabelle(n) auswählen** .</span><span class="sxs-lookup"><span data-stu-id="201da-149">Any combination of input columns from the **Select Input Table(s)** box.</span></span>  
  
    -   <span data-ttu-id="201da-150">Vorhersagefunktionen</span><span class="sxs-lookup"><span data-stu-id="201da-150">Prediction functions</span></span>  
  
8.  <span data-ttu-id="201da-151">Führen Sie die Abfrage aus, indem Sie auf der Symbolleiste der Registerkarte **Miningmodellvorhersage** auf die erste Schaltfläche klicken und dann **Ergebnis**auswählen.</span><span class="sxs-lookup"><span data-stu-id="201da-151">Run the query by clicking the first button on the toolbar of the **Mining Model Prediction** tab, and then selecting **Result**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="201da-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="201da-152">See Also</span></span>  
 <span data-ttu-id="201da-153">[Erstellen einer SINGLETON-Abfrage im Data Mining-Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="201da-153">[Create a Singleton Query in the Data Mining Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span></span>  
 [<span data-ttu-id="201da-154">Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="201da-154">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
