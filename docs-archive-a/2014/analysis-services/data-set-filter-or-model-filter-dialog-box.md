---
title: Daten Satz Filter oder Modell Filter (Dialog Feld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9602174-b7e2-4e16-8ded-dfd8eb9264d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa796cd8cb23894c059deba411b3e1d6676e3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717014"
---
# <a name="data-set-filter-or-model-filter-dialog-box"></a><span data-ttu-id="b04a7-102">Datasetfilter oder Modellfilter (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="b04a7-102">Data Set Filter or Model Filter Dialog Box</span></span>
  <span data-ttu-id="b04a7-103">In diesem Dialogfeld können Sie die Filter erstellen, die Sie auf ein Dataset anwenden können.</span><span class="sxs-lookup"><span data-stu-id="b04a7-103">This dialog box helps you build the filters that you can apply to a data set.</span></span>  <span data-ttu-id="b04a7-104">Bei dem Dataset kann es sich um ein zum Testen verwendetes externes Dataset oder um die Falldaten für ein Miningmodell handeln.</span><span class="sxs-lookup"><span data-stu-id="b04a7-104">The data set can be an external data set used for testing, or the case data for a mining model.</span></span> <span data-ttu-id="b04a7-105">Der Name des Dialogfelds ändert sich je nachdem, ob der Filter für ein externes Dataset oder für ein Miningmodell gilt.</span><span class="sxs-lookup"><span data-stu-id="b04a7-105">The name of the dialog box changes depending on whether the filter is for an external data set or for a mining model.</span></span>  
  
 <span data-ttu-id="b04a7-106">Wenn Sie den Filter auf ein neues Dataset anwenden, werden zum Auswerten des Data Mining-Modells nur die Fälle in den Daten verwendet, die die Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-106">If you apply the filter to a new data set, the data mining model is evaluated by using only those cases in the data set that meet the conditions.</span></span> <span data-ttu-id="b04a7-107">Wenn Sie den Filter auf das Miningmodell direkt anwenden, werden zum Trainieren und Testen des Modells nur die Fälle in den vorhandenen Testdaten verwendet, die den Filterkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-107">If you apply the filter to the mining model itself, the model will be trained and tested by using only the cases in the existing test data set that meet the filter criteria.</span></span>  
  
-   <span data-ttu-id="b04a7-108">Das Dialogfeld **Datasetfilter** kann über die Registerkarte **Eingabeauswahl** von **Mininggenauigkeitsdiagramm** aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b04a7-108">The **Data Set Filter** dialog box is available from the **Input Selection** tab of the **Mining Accuracy Chart** designer.</span></span>  
  
-   <span data-ttu-id="b04a7-109">Das Dialogfeld **Modellfilter** kann über die Registerkarte **Miningmodelle** des Data Mining-Designers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b04a7-109">The **Model Filter** dialog box is available from the **Mining Models** tab of the Data Miningdesigner.</span></span>  
  
-   <span data-ttu-id="b04a7-110">Das Raster **Bedingungen** weist Spalten auf, in denen Sie einen Tabellen- oder Spaltennamen, einen Operator oder Zielwerte angeben können.</span><span class="sxs-lookup"><span data-stu-id="b04a7-110">The **Conditions** grid contains columns where you can specify a table or column name, an operator, and target values.</span></span> <span data-ttu-id="b04a7-111">Mithilfe dieses Raster erstellen Sie in Wirklichkeit eine WHERE-Klausel.</span><span class="sxs-lookup"><span data-stu-id="b04a7-111">By using this grid you are essentially creating a WHERE clause.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b04a7-112">Zum Testen der Genauigkeit einer Untergruppe der ursprünglichen Trainingsdaten können Sie die Datenquellensicht hinzufügen, mit der der Trainingssatz als externe Testdaten definiert wurde, und dann Bedingungen im Raster **Datasetfilter** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-112">To test accuracy on a subset of the original training data, you can add the data source view that was used to define the training set as the external testing data, and then add conditions in the **Data Set Filter** grid.</span></span>  
  
 <span data-ttu-id="b04a7-113">**Weitere Informationen:** [Tests und Überprüfung &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="b04a7-113">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="b04a7-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b04a7-114">Options</span></span>  
 <span data-ttu-id="b04a7-115">**Bedingungen**</span><span class="sxs-lookup"><span data-stu-id="b04a7-115">**Conditions**</span></span>  
 <span data-ttu-id="b04a7-116">Zeigt Tabellennamen gefolgt von Spaltennamen mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="b04a7-116">Displays table names, followed by column names with conditions.</span></span>  
  
|<span data-ttu-id="b04a7-117">Wert</span><span class="sxs-lookup"><span data-stu-id="b04a7-117">Value</span></span>|<span data-ttu-id="b04a7-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b04a7-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b04a7-119">**Und/oder**</span><span class="sxs-lookup"><span data-stu-id="b04a7-119">**And/Or**</span></span>|<span data-ttu-id="b04a7-120">Wählen Sie einen Operator aus, um mehrere Bedingungen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-120">Choose an operator to join multiple conditions.</span></span>|  
|<span data-ttu-id="b04a7-121">**Miningstrukturspalte**</span><span class="sxs-lookup"><span data-stu-id="b04a7-121">**Mining Structure Column**</span></span>|<span data-ttu-id="b04a7-122">Klicken Sie hierauf, um eine Datenquelle auszuwählen, und klicken Sie dann im Raster auf aufeinander folgenden Zeilen, um Spalten aus der Datenquelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-122">Click to select a data source, and then click successive lines in the grid to add columns from the data source.</span></span><br /><br /> <span data-ttu-id="b04a7-123">Die erste Zeile im Raster gibt die Datenquellensicht an.</span><span class="sxs-lookup"><span data-stu-id="b04a7-123">The first line in the grid specifies the data source view.</span></span> <span data-ttu-id="b04a7-124">Nach Auswahl einer Datenquellensicht wird im Feld **Miningstrukturspalte** ein Tabellensymbol angezeigt, und im Feld **Wert** wird die Kombination aller Kriterien angezeigt, die Sie für diese Datenquelle definiert haben.</span><span class="sxs-lookup"><span data-stu-id="b04a7-124">After you select a data source view, **Mining Structure Column** displays a table icon, and the **Value** field displays the combination of all criteria that you have defined for this data source.</span></span><br /><br /> <span data-ttu-id="b04a7-125">Nach Auswahl einer Datenquelle wird im Feld **Miningstrukturspalte** eine Dropdownliste mit den einzelnen Spalten in der Datenquelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b04a7-125">After you have selected a data source, the **Mining Structure Column** box provides a dropdown list of individual columns in the data source.</span></span>|  
|<span data-ttu-id="b04a7-126">**Operator**</span><span class="sxs-lookup"><span data-stu-id="b04a7-126">**Operator**</span></span>|<span data-ttu-id="b04a7-127">Wählen Sie in der Liste einen Operator aus.</span><span class="sxs-lookup"><span data-stu-id="b04a7-127">Select an operator from the list.</span></span>|  
|<span data-ttu-id="b04a7-128">**Wert**</span><span class="sxs-lookup"><span data-stu-id="b04a7-128">**Value**</span></span>|<span data-ttu-id="b04a7-129">Bei Tabellen wird im Feld **Wert** die Kombination aller auf die Datenquelle angewendeten Filter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b04a7-129">For tables, the **Value** field shows the combination of all filters applied to the data source.</span></span> <span data-ttu-id="b04a7-130">Sie können auch auf die Schaltfläche zum Erstellen **(...)** rechts neben dem Textfeld klicken, um das Dialogfeld **Filter** zu öffnen und eine Bedingung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-130">You can also click the build **(...)** button at the right of the text box to open the **Filter** dialog box and build a condition.</span></span>|  
  
 <span data-ttu-id="b04a7-131">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="b04a7-131">**Expression**</span></span>  
 <span data-ttu-id="b04a7-132">Zeigt die Gruppe von Kriterien an, die Sie mit dem Raster erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b04a7-132">Displays the set of criteria that you built by using the grid.</span></span>  
  
 <span data-ttu-id="b04a7-133">**Abfrage bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="b04a7-133">**Edit Query**</span></span>  
 <span data-ttu-id="b04a7-134">Ändert den Filterbearbeitungsmodus, sodass Sie einen Filterausdruck direkt in das Textfeld **Ausdruck** eingeben können.</span><span class="sxs-lookup"><span data-stu-id="b04a7-134">Changes the filter editing mode so that you can type a filter expression directly in the **Expression** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b04a7-135">Nachdem Sie manuell Änderungen am Filter Ausdruck vorgenommen haben, können Sie nicht mehr in den Raster Bearbeitungsmodus zurückkehren, auch nachdem Sie den Ausdruck auf der Registerkarte **Eingabeauswahl** im Feld **Filter Ausdruck** gespeichert haben. Wenn Sie einen Ausdruck mithilfe des Rasters erstellen möchten, müssen Sie den vorhandenen Filter Ausdruck löschen und beginnen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-135">After you have made manual changes to the filter expression, you cannot return to grid edit mode, even after you have saved the expression in the **Filter Expression** box on the **Input Selection** tab. If you want to build an expression by using the grid, you must delete the existing filter expression and start over.</span></span>  
  
 <span data-ttu-id="b04a7-136">**Abfragebearbeitung wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="b04a7-136">**Revert Query Edits**</span></span>  
 <span data-ttu-id="b04a7-137">Stellt den vorherigen Zustand des Rasters wieder her und verwirft alle am Filterausdruck vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="b04a7-137">Restores the grid to its previous state and cancels any changes that you made to the filter expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04a7-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b04a7-138">See Also</span></span>  
 <span data-ttu-id="b04a7-139">[Test-und validierungsaufgaben und Anleitungen &#40;Data Mining-&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b04a7-139">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="b04a7-140">Mining Genauigkeits Diagramm-Designer &#40;Data Mining-&#41;</span><span class="sxs-lookup"><span data-stu-id="b04a7-140">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
