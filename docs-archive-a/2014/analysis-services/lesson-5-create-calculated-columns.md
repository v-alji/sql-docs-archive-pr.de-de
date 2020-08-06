---
title: 'Lektion 6: Erstellen von berechneten Spalten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
author: minewiskan
ms.author: owend
ms.openlocfilehash: dcebf61955e230c9e61c955683b897026553cb52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616794"
---
# <a name="lesson-6-create-calculated-columns"></a><span data-ttu-id="8fce6-102">Lektion 6: Erstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="8fce6-102">Lesson 6: Create Calculated Columns</span></span>
  <span data-ttu-id="8fce6-103">In dieser Lektion erstellen Sie neue Daten in Ihrem Modell durch Hinzufügen von berechneten Spalten.</span><span class="sxs-lookup"><span data-stu-id="8fce6-103">In this lesson, you will create new data in your model by adding calculated columns.</span></span> <span data-ttu-id="8fce6-104">Eine berechnete Spalte basiert auf Daten, die bereits im Modell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8fce6-104">A calculated column is based on data that already exists in the model.</span></span> <span data-ttu-id="8fce6-105">Weitere Informationen finden Sie unter [Berechnete Spalten &#40;SSAS – tabellarisch&#41;](tabular-models/ssas-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="8fce6-105">To learn more, see [Calculated Columns &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span></span>  
  
 <span data-ttu-id="8fce6-106">Sie erstellen fünf neue berechnete Spalten in drei verschiedenen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="8fce6-106">You will create five new calculated columns in three different tables.</span></span> <span data-ttu-id="8fce6-107">Die Schritte sind für jede Aufgabe etwas anders.</span><span class="sxs-lookup"><span data-stu-id="8fce6-107">The steps are slightly different for each task.</span></span> <span data-ttu-id="8fce6-108">Damit sollen Ihnen verschiedene Methoden zum Erstellen neuer Spalten, zum Umbenennen der Spalten und zum Platzieren der Spalten an verschiedenen Positionen in einer Tabelle aufgezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8fce6-108">This is to show you there are several ways to create new columns, rename them, and place them in various locations in a table.</span></span>  
  
 <span data-ttu-id="8fce6-109">Geschätzte Zeit zum Bearbeiten dieser Lektion: **15 Minuten**</span><span class="sxs-lookup"><span data-stu-id="8fce6-109">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8fce6-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8fce6-110">Prerequisites</span></span>  
 <span data-ttu-id="8fce6-111">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8fce6-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="8fce6-112">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 5: Erstellen von Beziehungen](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="8fce6-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
## <a name="create-calculated-columns"></a><span data-ttu-id="8fce6-113">Erstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="8fce6-113">Create Calculated Columns</span></span>  
  
#### <a name="create-a-month-calendar-calculated-column-in-the-date-table"></a><span data-ttu-id="8fce6-114">Erstellen einer berechneten Spalte "Month Calendar" in der Date-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8fce6-114">Create a Month Calendar calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="8fce6-115">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das Menü **Modell** , zeigen Sie auf **Modellansicht**, und klicken Sie anschließend auf **Datensicht**.</span><span class="sxs-lookup"><span data-stu-id="8fce6-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Model View**, and then click **Data View**.</span></span>  
  
     <span data-ttu-id="8fce6-116">Berechnete Spalten können nur mit dem Modell-Designer in der Datensicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8fce6-116">Calculated columns can only be created by using the model designer in Data View.</span></span>  
  
2.  <span data-ttu-id="8fce6-117">Klicken Sie im Modell-Designer auf die Tabelle (Registerkarte) **Date** .</span><span class="sxs-lookup"><span data-stu-id="8fce6-117">In the model designer, click the **Date** table (tab).</span></span>  
  
3.  <span data-ttu-id="8fce6-118">Klicken Sie mit der rechten Maustaste auf die Spalte **Calendar Quarter** , und klicken Sie dann auf **Spalte einfügen**.</span><span class="sxs-lookup"><span data-stu-id="8fce6-118">Right-click the **Calendar Quarter** column, and then click **Insert Column**.</span></span>  
  
     <span data-ttu-id="8fce6-119">Links von der Spalte **Calendar Quarter** wird eine neue Spalte mit dem Namen **CalculatedColumn1** eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8fce6-119">A new column named **CalculatedColumn1** is inserted to the left of the **Calendar Quarter** column.</span></span>  
  
4.  <span data-ttu-id="8fce6-120">Geben Sie in der Bearbeitungsleiste über der Tabelle die folgende Formel ein.</span><span class="sxs-lookup"><span data-stu-id="8fce6-120">In the formula bar above the table, type the following formula.</span></span> <span data-ttu-id="8fce6-121">Die Funktion AutoVervollständigen unterstützt Sie beim Eingeben des vollqualifizierten Namens von Spalten und Tabellen und listet die verfügbaren Funktionen auf.</span><span class="sxs-lookup"><span data-stu-id="8fce6-121">AutoComplete helps you type the fully qualified names of columns and tables, and lists the functions that are available.</span></span>  
  
     `=RIGHT(" " & FORMAT([Month],"#0"), 2) & " - " & [Month Name]`  
  
     <span data-ttu-id="8fce6-122">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8fce6-122">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="8fce6-123">Anschließend werden Werte für alle Zeilen in der berechneten Spalte aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8fce6-123">Values are then populated for all the rows in the calculated column.</span></span> <span data-ttu-id="8fce6-124">Wenn Sie durch die Tabelle scrollen, werden Sie sehen, dass die Zeilen über verschiedene Werte für diese Spalte verfügen, basierend auf den Daten in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="8fce6-124">If you scroll down through the table, you will see that rows can have different values for this column, based on the data that is in each row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fce6-125">Wenn Sie einen Fehler erhalten, überprüfen Sie, ob die Spaltennamen in der Formel mit den von Ihnen in [Lektion 3: Umbenennen von Spalten](rename-columns.md)geänderten Spaltennamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8fce6-125">If you receive an error, verify the column names in the formula match the column names you changed in [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
5.  <span data-ttu-id="8fce6-126">Benennen Sie diese Spalte in um `Month Calendar` .</span><span class="sxs-lookup"><span data-stu-id="8fce6-126">Rename this column to `Month Calendar`.</span></span>  
  
 <span data-ttu-id="8fce6-127">Die berechnete Spalte "Month Calendar" bietet einen sortierbaren Namen für den Monat.</span><span class="sxs-lookup"><span data-stu-id="8fce6-127">The Month Calendar calculated column provides a sortable name for Month.</span></span>  
  
#### <a name="create-a-day-of-week-calculated-column-in-the-date-table"></a><span data-ttu-id="8fce6-128">Erstellen einer berechneten Spalte "Day of Week" in der Date-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8fce6-128">Create a Day of Week calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="8fce6-129">Klicken Sie bei nach wie vor aktiver Tabelle **Date** auf das Menü **Spalte** und anschließend auf **Spalte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8fce6-129">With the **Date** table still active, click on the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="8fce6-130">Ganz rechts von der Tabelle wird eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8fce6-130">A new column is added to the far right of the table</span></span>  
  
2.  <span data-ttu-id="8fce6-131">Geben Sie in der Bearbeitungsleiste folgende Formel ein:</span><span class="sxs-lookup"><span data-stu-id="8fce6-131">In the formula bar, type the following formula:</span></span>  
  
     `=RIGHT(" " & FORMAT([Day Number Of Week],"#0"), 2) & " - " & [Day Name]`  
  
     <span data-ttu-id="8fce6-132">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8fce6-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="8fce6-133">Benennen Sie die Spalte in um `Day of Week` .</span><span class="sxs-lookup"><span data-stu-id="8fce6-133">Rename the column to `Day of Week`.</span></span>  
  
4.  <span data-ttu-id="8fce6-134">Klicken Sie auf die Spaltenüberschrift und ziehen Sie die Spalte zwischen die Spalte **Day Name** und die Spalte **Day of Month** .</span><span class="sxs-lookup"><span data-stu-id="8fce6-134">Click on the column heading, and then drag the column between the **Day Name** column and the **Day of Month** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="8fce6-135">Durch das Verschieben von Spalten in der Tabelle wird die Navigation vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="8fce6-135">Moving columns in your table makes it easier to navigate.</span></span>  
  
 <span data-ttu-id="8fce6-136">Die berechnete Spalte "Day of Week" bietet einen sortierbaren Namen für den Wochentag.</span><span class="sxs-lookup"><span data-stu-id="8fce6-136">The Day of Week calculated column provides a sortable name for the day of week.</span></span>  
  
#### <a name="create-a-product-subcategory-name-calculated-column-in-the-product-table"></a><span data-ttu-id="8fce6-137">Erstellen einer berechneten Spalte "Product Subcategory Name" in der Product-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8fce6-137">Create a Product Subcategory Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="8fce6-138">Wählen Sie im Modell-Designer die Tabelle **Product** aus.</span><span class="sxs-lookup"><span data-stu-id="8fce6-138">In the model designer, select the **Product** table.</span></span>  
  
2.  <span data-ttu-id="8fce6-139">Führen Sie in der Tabelle einen Bildlauf nach ganz rechts aus.</span><span class="sxs-lookup"><span data-stu-id="8fce6-139">Scroll to the far right of the table.</span></span> <span data-ttu-id="8fce6-140">Beachten Sie, dass die Spalte ganz rechts **Spalte hinzufügen** (in Kursivdruck) benannt ist, und klicken Sie auf die Spaltenüberschrift.</span><span class="sxs-lookup"><span data-stu-id="8fce6-140">Notice the right-most column is named **Add Column** (italicized), click the column heading.</span></span>  
  
3.  <span data-ttu-id="8fce6-141">Geben Sie in der Bearbeitungsleiste folgende Formel ein.</span><span class="sxs-lookup"><span data-stu-id="8fce6-141">In the formula bar, type the following formula.</span></span>  
  
     `=RELATED('Product Subcategory'[Product Subcategory Name])`  
  
     <span data-ttu-id="8fce6-142">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8fce6-142">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="8fce6-143">Benennen Sie die Spalte in um `Product Subcategory Name` .</span><span class="sxs-lookup"><span data-stu-id="8fce6-143">Rename the column to `Product Subcategory Name`.</span></span>  
  
 <span data-ttu-id="8fce6-144">Die berechnete Spalte "Product Subcategory Name" wird verwendet, um eine Hierarchie in der Product-Tabelle zu erstellen, in der Daten der Spalte "Product Subcategory Name" in der Tabelle " Product Subcategory" enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8fce6-144">The Product Subcategory Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Subcategory Name column in the Product Subcategory table.</span></span> <span data-ttu-id="8fce6-145">Hierarchien können nicht mehr als eine Tabelle umfassen.</span><span class="sxs-lookup"><span data-stu-id="8fce6-145">Hierarchies cannot span more than one table.</span></span> <span data-ttu-id="8fce6-146">Sie erstellen Hierarchien später in Lektion 7.</span><span class="sxs-lookup"><span data-stu-id="8fce6-146">You will create hierarchies later in Lesson 7.</span></span>  
  
#### <a name="create-a-product-category-name-calculated-column-in-the-product-table"></a><span data-ttu-id="8fce6-147">Erstellen einer berechneten Spalte "Product Category Name" in der Product-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8fce6-147">Create a Product Category Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="8fce6-148">Klicken Sie bei nach wie vor aktiver Tabelle **Product** auf das Menü **Spalte** und anschließend auf **Spalte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8fce6-148">With the **Product** table still active, click the **Column** menu, and then click **Add Column**.</span></span>  
  
2.  <span data-ttu-id="8fce6-149">Geben Sie in der Bearbeitungsleiste folgende Formel ein:</span><span class="sxs-lookup"><span data-stu-id="8fce6-149">In the formula bar, type the following formula:</span></span>  
  
     `=RELATED('Product Category'[Product Category Name])`  
  
     <span data-ttu-id="8fce6-150">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8fce6-150">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="8fce6-151">Benennen Sie die Spalte in um `Product Category Name` .</span><span class="sxs-lookup"><span data-stu-id="8fce6-151">Rename the column to `Product Category Name`.</span></span>  
  
 <span data-ttu-id="8fce6-152">Die berechnete Spalte "Product Category Name" wird verwendet, um eine Hierarchie in der Product-Tabelle zu erstellen, in der Daten der Spalte "Product Category Name" in der Tabelle " Product Category" enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8fce6-152">The Product Category Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Category Name column in the Product Category table.</span></span> <span data-ttu-id="8fce6-153">Hierarchien können nicht mehr als eine Tabelle umfassen.</span><span class="sxs-lookup"><span data-stu-id="8fce6-153">Hierarchies cannot span more than one table.</span></span>  
  
#### <a name="create-a-margin-calculated-column-in-the-internet-sales-table"></a><span data-ttu-id="8fce6-154">Erstellen einer berechneten Spalte "Margin" in der Internet Sales-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8fce6-154">Create a Margin calculated column in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="8fce6-155">Wählen Sie im Modell-Designer die Tabelle **Internet Sales** aus.</span><span class="sxs-lookup"><span data-stu-id="8fce6-155">In the model designer, select the **Internet Sales** table.</span></span>  
  
2.  <span data-ttu-id="8fce6-156">Fügt eine neue Spalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fce6-156">Add a new column.</span></span>  
  
3.  <span data-ttu-id="8fce6-157">Geben Sie in der Bearbeitungsleiste folgende Formel ein:</span><span class="sxs-lookup"><span data-stu-id="8fce6-157">In the formula bar, type the following formula:</span></span>  
  
     `=[Sales Amount]-[Total Product Cost]`  
  
     <span data-ttu-id="8fce6-158">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8fce6-158">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="8fce6-159">Benennen Sie die Spalte in um `Margin` .</span><span class="sxs-lookup"><span data-stu-id="8fce6-159">Rename the column to `Margin`.</span></span>  
  
5.  <span data-ttu-id="8fce6-160">Ziehen Sie die Spalte zwischen die Spalte **Sales Amount** und die Spalte **Tax Amt** .</span><span class="sxs-lookup"><span data-stu-id="8fce6-160">Drag the column between the **Sales Amount** column and the **Tax Amt** column.</span></span>  
  
 <span data-ttu-id="8fce6-161">Die berechnete Spalte "Margin" dient zur Analyse von Gewinnspannen für jede Zeile (Produktzeile).</span><span class="sxs-lookup"><span data-stu-id="8fce6-161">The Margin calculated column is used to analyze profit margins for each (product) row.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8fce6-162">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8fce6-162">Next Step</span></span>  
 <span data-ttu-id="8fce6-163">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 7: Erstellen von Measures](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="8fce6-163">To continue this lesson, go to the next lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
  
