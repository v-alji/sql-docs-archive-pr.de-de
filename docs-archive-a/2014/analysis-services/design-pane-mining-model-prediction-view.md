---
title: Entwurfs Bereich (Mining Modell-Vorhersage Ansicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.design.f1
ms.assetid: 17f24c8d-43cd-4f4d-83b3-a41ee8fbe8e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32ac73a2d6fde38d15d1f45a8439293695749ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702104"
---
# <a name="design-pane-mining-model-prediction-view"></a><span data-ttu-id="bdd05-102">Entwurfsbereich (Miningmodell-Vorhersageansicht)</span><span class="sxs-lookup"><span data-stu-id="bdd05-102">Design Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="bdd05-103">Der Bereich **Entwurf** enthält den Generator für Vorhersageabfragen, mit dem Sie Data Mining-Vorhersagen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="bdd05-103">The **Design** pane contains the Prediction Query Builder, which you can use to build data mining predictions.</span></span> <span data-ttu-id="bdd05-104">Sie können Vorhersageabfragen entwerfen, die Tabellen mit Eingabedaten einer Datenquellensicht verwenden, um Massenvorhersagen zu erstellen, oder Sie entwerfen Singleton-Vorhersageabfragen, bei denen Sie einzelne Werte angeben können.</span><span class="sxs-lookup"><span data-stu-id="bdd05-104">You can design prediction queries that use tables of input data from a data source view, to generate bulk predictions, or you can create singleton prediction queries, which let you provide individual values.</span></span>  
  
 <span data-ttu-id="bdd05-105">Wechseln Sie zur Ergebnissicht, um die Abfrage auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-105">To run the query and view the results, switch to query result view.</span></span>  
  
 <span data-ttu-id="bdd05-106">Die Ansicht **Abfrage** zeigt die vom Generator für Vorhersageabfragen erstellte DMX-Abfrage (DMX, Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="bdd05-106">The **Query** view displays the Data Mining Extensions (DMX) query that Prediction Query Builder creates.</span></span> <span data-ttu-id="bdd05-107">Wenn Sie mit DMX vertraut sind, können Sie diese Abfrage anpassen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-107">If you are familiar with DMX, you can customize this query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdd05-108">Wenn Sie die Abfrage manuell ändern, gehen diese Änderungen bei Rückkehr zur Entwurfssicht verloren.</span><span class="sxs-lookup"><span data-stu-id="bdd05-108">If you make any manual changes to the query, your changes will be lost when you switch back to Design view.</span></span> <span data-ttu-id="bdd05-109">Wenn Sie die DMX-Abfrage speichern möchten, können Sie die Abfrage in die Windows-Zwischenablage kopieren und dann in eine Textdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-109">If you want to save the DMX query, you can copy the query to the Windows Clipboard and then paste it to a text file.</span></span>  
  
 <span data-ttu-id="bdd05-110">**Weitere Informationen finden Sie unter** [Data Mining-Abfrage](data-mining/data-mining-queries.md)</span><span class="sxs-lookup"><span data-stu-id="bdd05-110">**For More Information:** [Data Mining Queries](data-mining/data-mining-queries.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="bdd05-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="bdd05-111">Options</span></span>  
 <span data-ttu-id="bdd05-112">**Zur Abfrageergebnissicht wechseln**</span><span class="sxs-lookup"><span data-stu-id="bdd05-112">**Switch to query result view**</span></span>  
 <span data-ttu-id="bdd05-113">Klicken Sie hier, um zwischen den Bereichen **Entwurf**, **Abfrage**und **Ergebnis** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="bdd05-113">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="bdd05-114">Der Wechsel zum Bereich **Ergebnis** führt die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="bdd05-114">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="bdd05-115">**Abfrageergebnis speichern**</span><span class="sxs-lookup"><span data-stu-id="bdd05-115">**Save the query result**</span></span>  
 <span data-ttu-id="bdd05-116">Öffnet das Dialogfeld **Ergebnis der Data Mining-Abfrage speichern** .</span><span class="sxs-lookup"><span data-stu-id="bdd05-116">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="bdd05-117">**SINGLETON-Abfrage**</span><span class="sxs-lookup"><span data-stu-id="bdd05-117">**Singleton query**</span></span>  
 <span data-ttu-id="bdd05-118">Ermöglicht das Erstellen einer SINGLETON-Abfrage, in der Sie die Werte direkt für die Abfrage bereitstellen können, statt eine Tabelle als Quelle der bekannten Daten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-118">Enables creating a singleton query, in which you can provide values directly for the query instead of providing a table as the source of the known data.</span></span> <span data-ttu-id="bdd05-119">Die Tabelle **Eingabetabelle(n) auswählen** wird durch die Tabelle **Singleton-Abfrageeingabe** ersetzt.</span><span class="sxs-lookup"><span data-stu-id="bdd05-119">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span>  
  
 <span data-ttu-id="bdd05-120">**Abfrageergebnis aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="bdd05-120">**Refresh query results**</span></span>  
 <span data-ttu-id="bdd05-121">Verarbeitet die Vorhersageabfrage erneut.</span><span class="sxs-lookup"><span data-stu-id="bdd05-121">Reprocesses the prediction query.</span></span> <span data-ttu-id="bdd05-122">Diese Option ist nur im Bereich **Ergebnis** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bdd05-122">This is enabled only in the **Result** pane.</span></span>  
  
 <span data-ttu-id="bdd05-123">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="bdd05-123">**Mining Model**</span></span>  
 <span data-ttu-id="bdd05-124">Zeigt das Miningmodell an, auf dem Sie die Vorhersagen aufbauen wollen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-124">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="bdd05-125">**Modell auswählen**</span><span class="sxs-lookup"><span data-stu-id="bdd05-125">**Select Model**</span></span>  
 <span data-ttu-id="bdd05-126">Öffnet das Dialogfeld **Miningmodell auswählen** .</span><span class="sxs-lookup"><span data-stu-id="bdd05-126">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="bdd05-127">**Eingabetabelle(n) auswählen**</span><span class="sxs-lookup"><span data-stu-id="bdd05-127">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="bdd05-128">Zeigt die ausgewählten Eingabetabellen an, die die bekannten Daten enthalten, auf denen die Vorhersage aufgebaut werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdd05-128">Displays the selected input tables that contain known data on which to base the predictions.</span></span>  
  
 <span data-ttu-id="bdd05-129">**Tabelle löschen**</span><span class="sxs-lookup"><span data-stu-id="bdd05-129">**Delete Table**</span></span>  
 <span data-ttu-id="bdd05-130">Löscht die ausgewählte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bdd05-130">Deletes the selected table.</span></span> <span data-ttu-id="bdd05-131">Diese Schaltfläche ist deaktiviert, wenn keine Tabelle ausgewählt oder vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bdd05-131">This button is disabled if a table has not been selected or does not exist.</span></span>  
  
 <span data-ttu-id="bdd05-132">**Falltabelle auswählen**</span><span class="sxs-lookup"><span data-stu-id="bdd05-132">**Select Case Table**</span></span>  
 <span data-ttu-id="bdd05-133">Öffnet das Dialogfeld **Tabelle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="bdd05-133">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="bdd05-134">Diese Schaltfläche wird nur angezeigt, wenn noch keine Falltabelle ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bdd05-134">This button appears only if a case table has not been selected.</span></span>  
  
 <span data-ttu-id="bdd05-135">**Geschachtelte Tabelle auswählen**</span><span class="sxs-lookup"><span data-stu-id="bdd05-135">**Select Nested Table**</span></span>  
 <span data-ttu-id="bdd05-136">Öffnet das Dialogfeld **Tabelle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="bdd05-136">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="bdd05-137">Diese Schaltfläche wird nur angezeigt, wenn eine Falltabelle ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bdd05-137">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="bdd05-138">Wenn die entsprechende Miningstruktur keine geschachtelte Tabelle enthält, ist diese Schaltfläche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bdd05-138">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="bdd05-139">**Join ändern**</span><span class="sxs-lookup"><span data-stu-id="bdd05-139">**Modify Join**</span></span>  
 <span data-ttu-id="bdd05-140">Öffnet das Dialogfeld **Geschachtelten Join angeben** .</span><span class="sxs-lookup"><span data-stu-id="bdd05-140">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="bdd05-141">Diese Schaltfläche ist nur aktiviert, wenn eine geschachtelte Tabelle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bdd05-141">This button is active only if the nested table is selected.</span></span>  
  
 <span data-ttu-id="bdd05-142">**SINGLETON-Abfrageeingabe**</span><span class="sxs-lookup"><span data-stu-id="bdd05-142">**Singleton Query input**</span></span>  
 <span data-ttu-id="bdd05-143">Aktiviert, wenn Sie die Schaltfläche **SINGLETON-Abfrage** auswählen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-143">Enabled when you select the **Singleton query** button.</span></span> <span data-ttu-id="bdd05-144">Enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="bdd05-144">Contains the following columns:</span></span>  
  
|<span data-ttu-id="bdd05-145">Wert</span><span class="sxs-lookup"><span data-stu-id="bdd05-145">Value</span></span>|<span data-ttu-id="bdd05-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bdd05-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdd05-147">**Miningmodellspalte**</span><span class="sxs-lookup"><span data-stu-id="bdd05-147">**Mining Model Column**</span></span>|<span data-ttu-id="bdd05-148">Listet die Miningmodellspalten auf, die in dem Miningmodell enthalten sind, das in der **Miningmodelle** -Spalte enhalten ist.</span><span class="sxs-lookup"><span data-stu-id="bdd05-148">Lists the mining model columns contained within the mining model that is selected in the **Mining Model** table.</span></span>|  
|<span data-ttu-id="bdd05-149">**Wert**</span><span class="sxs-lookup"><span data-stu-id="bdd05-149">**Value**</span></span>|<span data-ttu-id="bdd05-150">Wählen Sie einen Wert aus der Liste, die die verschiedenen Statusmöglichkeiten der ausgewählten Miningmodellspalte enthält.</span><span class="sxs-lookup"><span data-stu-id="bdd05-150">Select a value from the list that contains each possible state of the selected mining model column.</span></span><br /><br /> <span data-ttu-id="bdd05-151">Wenn es sich bei der Spalte um eine geschachtelte Tabellenspalte handelt, klicken Sie auf die Wertzelle, um das Dialogfeld **Eingabe für geschachtelte Tabelle** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-151">If the column is a nested table column, clicking the value cell opens the **Nested Table Input** dialog box.</span></span>|  
  
 <span data-ttu-id="bdd05-152">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="bdd05-152">**Source**</span></span>  
 <span data-ttu-id="bdd05-153">Wählen Sie die Quelle aus, die das Feld enthält, das Sie für die Spalte verwenden wollen.</span><span class="sxs-lookup"><span data-stu-id="bdd05-153">Select the source that contains the field that you will use for the column.</span></span> <span data-ttu-id="bdd05-154">Sie können entweder das in der Tabelle **Miningmodell** ausgewählte Miningmodell, die in der Tabelle **Eingabetabelle(n) auswählen** ausgewählte(n) Eingabetabelle(n), eine Vorhersagefunktion oder einen benutzerdefinierten Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="bdd05-154">You can either use the mining model that is selected in the **Mining Model** table, the input table or tables that are selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="bdd05-155">Spalten können aus den das Miningmodell enthaltenden Tabellen und den Eingabetabellen auf die Zelle gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="bdd05-155">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
 <span data-ttu-id="bdd05-156">**Feld**</span><span class="sxs-lookup"><span data-stu-id="bdd05-156">**Field**</span></span>  
 <span data-ttu-id="bdd05-157">Wählen Sie eine Spalte aus der Liste der aus der Quelltabelle abgeleiteten Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="bdd05-157">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="bdd05-158">Wenn Sie unter **Quelle** die **Vorhersagefunktion**ausgewählt haben, enthält diese Liste die für das ausgewählte Miningmodell verfügbare Vorhersagefunktion.</span><span class="sxs-lookup"><span data-stu-id="bdd05-158">If you selected **Prediction Function** in **Source**, this contains the prediction function available for the selected mining model.</span></span>  
  
 <span data-ttu-id="bdd05-159">**Gruppe**</span><span class="sxs-lookup"><span data-stu-id="bdd05-159">**Group**</span></span>  
 <span data-ttu-id="bdd05-160">Wird mit der **Und/Oder** -Spalte verwendet, um Ausdrücke zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="bdd05-160">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="bdd05-161">Beispiel: `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="bdd05-161">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="bdd05-162">**Und/oder**</span><span class="sxs-lookup"><span data-stu-id="bdd05-162">**And/Or**</span></span>  
 <span data-ttu-id="bdd05-163">Wird zum Erstellen einer logischen Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="bdd05-163">Use to create a logical query.</span></span> <span data-ttu-id="bdd05-164">Beispiel: `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="bdd05-164">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="bdd05-165">**Kriterium/Argument**</span><span class="sxs-lookup"><span data-stu-id="bdd05-165">**Criteria/Argument**</span></span>  
 <span data-ttu-id="bdd05-166">Geben Sie eine Bedingung oder einen benutzerdefinierten Ausdruck an, der auf die Spalte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="bdd05-166">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="bdd05-167">Spalten können aus den das Miningmodell enthaltenden Tabellen und den Eingabetabellen auf die Zelle gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="bdd05-167">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd05-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdd05-168">See Also</span></span>  
 <span data-ttu-id="bdd05-169">[Data Mining-Erweiterungen &#40;DMX-&#41;-Anweisungs Referenz](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="bdd05-169">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 <span data-ttu-id="bdd05-170">[Schnittstellen für Data Mining-Abfragen](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bdd05-170">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="bdd05-171">Generator für Vorhersageabfragen &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bdd05-171">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
