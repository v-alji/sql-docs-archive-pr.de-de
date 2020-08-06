---
title: Transformation für Pivot | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.pivottrans.f1
helpviewer_keywords:
- Pivot transformation
- normalized data [Integration Services]
- PivotUsage property
- datasets [Integration Services], normalized data
- less normalized data set [Integration Services]
ms.assetid: 55f5db6e-6777-435f-8a06-b68c129f8437
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43bdc5be709ea00d4be4601f52c38e96fe3f1ce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727090"
---
# <a name="pivot-transformation"></a><span data-ttu-id="ff1ca-102">Transformation für Pivot</span><span class="sxs-lookup"><span data-stu-id="ff1ca-102">Pivot Transformation</span></span>
  <span data-ttu-id="ff1ca-103">Die Transformation für Pivot macht aus einem normalisierten Dataset eine weniger normalisierte, aber kompaktere Version, indem die Eingabedaten nach einem Spaltenwert pivotiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-103">The Pivot transformation makes a normalized data set into a less normalized but more compact version by pivoting the input data on a column value.</span></span> <span data-ttu-id="ff1ca-104">Beispielsweise weist ein normalisiertes **Orders** -Dataset, das den Kundennamen, das Produkt und die gekaufte Menge auflistet, in der Regel mehrere Zeilen für jeden Kunden auf, der mehrere Produkte gekauft hat. Dabei zeigt jede Zeile für den betreffenden Kunden Bestelldetails für ein anderes Produkt an.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-104">For example, a normalized **Orders** data set that lists customer name, product, and quantity purchased typically has multiple rows for any customer who purchased multiple products, with each row for that customer showing order details for a different product.</span></span> <span data-ttu-id="ff1ca-105">Durch Pivotieren des Datasets nach der Produktspalte kann mit der Transformation für Pivot ein Dataset mit einer einzigen Zeile pro Kunde ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-105">By pivoting the data set on the product column, the Pivot transformation can output a data set with a single row per customer.</span></span> <span data-ttu-id="ff1ca-106">In dieser Zeile werden alle Einkäufe des Kunden aufgelistet, wobei die Produktnamen als Spaltennamen und die Menge als Wert in der Produktspalte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-106">That single row lists all the purchases by the customer, with the product names shown as column names, and the quantity shown as a value in the product column.</span></span> <span data-ttu-id="ff1ca-107">Da nicht jeder Kunde jedes Produkt kauft, können viele Spalten NULL-Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-107">Because not every customer purchases every product, many columns may contain null values.</span></span>  
  
 <span data-ttu-id="ff1ca-108">Wenn ein Dataset pivotiert wird, übernehmen Eingabespalten unterschiedliche Rollen am Pivotvorgang.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-108">When a dataset is pivoted, input columns perform different roles in the pivoting process.</span></span> <span data-ttu-id="ff1ca-109">Für die Beteiligung einer Spalte gibt es folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="ff1ca-109">A column can participate in the following ways:</span></span>  
  
-   <span data-ttu-id="ff1ca-110">Die Spalte wird unverändert an die Ausgabe übergeben.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-110">The column is passed through unchanged to the output.</span></span> <span data-ttu-id="ff1ca-111">Viele Eingabezeilen können nur eine Ausgabezeile ergeben, weshalb die Transformation nur den ersten Eingabewert für die Spalte kopiert.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-111">Because many input rows can result only in one output row, the transformation copies only the first input value for the column.</span></span>  
  
-   <span data-ttu-id="ff1ca-112">Die Spalte dient als Schlüssel oder Teil des Schlüssels, mit dem ein Recordset definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-112">The column acts as the key or part of the key that identifies a set of records.</span></span>  
  
-   <span data-ttu-id="ff1ca-113">Die Spalte definiert den Pivotvorgang.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-113">The column defines the pivot.</span></span> <span data-ttu-id="ff1ca-114">Die Werte in dieser Spalte sind Spalten im pivotierten Dataset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-114">The values in this column are associated with columns in the pivoted dataset.</span></span>  
  
-   <span data-ttu-id="ff1ca-115">Die Spalte enthält Werte, die den Spalten hinzugefügt werden, die beim Pivotieren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-115">The column contains values that are placed in the columns that the pivot creates.</span></span>  
  
 <span data-ttu-id="ff1ca-116">Diese Transformation weist eine Eingabe, eine reguläre Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-116">This transformation has one input, one regular output, and one error output.</span></span>  
  
## <a name="sort-and-duplicate-rows"></a><span data-ttu-id="ff1ca-117">Sortieren und doppelte Zeilen</span><span class="sxs-lookup"><span data-stu-id="ff1ca-117">Sort and Duplicate Rows</span></span>  
 <span data-ttu-id="ff1ca-118">Die Eingabedaten müssen in der Pivotspalte sortiert sein, damit die Daten effizient pivotiert werden, das heißt, dass möglichst wenige Datensätze im Ausgabedataset erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-118">To pivot data efficiently, which means creating as few records in the output dataset as possible, the input data must be sorted on the pivot column.</span></span> <span data-ttu-id="ff1ca-119">Wenn die Daten nicht sortiert sind, kann es sein, dass die Transformation für Pivot mehrere Datensätze für jeden Wert im festgelegten Schlüssel generiert, bei dem es sich um die Spalte handelt, die die festgelegte Mitgliedschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-119">If the data is not sorted, the Pivot transformation might generate multiple records for each value in the set key, which is the column that defines set membership.</span></span> <span data-ttu-id="ff1ca-120">Wenn beispielsweise ein Dataset nach der **Name** -Spalte pivotiert wird, aber die Namen nicht sortiert sind, könnte das Ausgabedataset pro Kunde mehrere Zeilen aufweisen, denn ein Pivotvorgang wird jedes Mal ausgeführt, wenn der Wert in der **Name** -Spalte geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-120">For example, if a dataset is pivoted on a **Name** column but the names are not sorted, the output dataset could have more than one row for each customer, because a pivot occurs every time that the value in **Name** changes.</span></span>  
  
 <span data-ttu-id="ff1ca-121">Die Eingabedaten können doppelte Zeilen enthalten. Diese bewirken, dass die Transformation für Pivot einen Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-121">The input data might contain duplicate rows, which will cause the Pivot transformation to fail.</span></span> <span data-ttu-id="ff1ca-122">"Doppelte Zeilen" bedeutet Zeilen, die in den festgelegten Schlüsselspalten und Pivotspalten die gleichen Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-122">"Duplicate rows" means rows that have the same values in the set key columns and the pivot columns.</span></span> <span data-ttu-id="ff1ca-123">Zur Vermeidung von Fehlern können Sie entweder die Transformation so konfigurieren, dass Fehlerzeilen in eine Fehlerausgabe umgeleitet werden, oder Sie können Werte vorab aggregieren, um sicherzustellen, dass keine doppelten Zeilen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-123">To avoid failure, you can either configure the transformation to redirect error rows to an error output or you can pre-aggregate values to ensure there are no duplicate rows.</span></span>  
  
##  <a name="options-in-the-pivot-dialog-box"></a><a name="options"></a> <span data-ttu-id="ff1ca-124">Optionen im Dialogfeld "Pivot"</span><span class="sxs-lookup"><span data-stu-id="ff1ca-124">Options in the Pivot Dialog Box</span></span>  
 <span data-ttu-id="ff1ca-125">Sie konfigurieren den Pivotvorgang, indem Sie die Optionen im Dialogfeld **Pivot** festlegen.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-125">You configure the pivot operation by setting the options in the **Pivot** dialog box.</span></span> <span data-ttu-id="ff1ca-126">Um das Dialogfeld **Pivot** zu öffnen, fügen Sie dem Paket die Pivottransformation in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]hinzu. Klicken Sie anschließend mit der rechten Maustaste auf die Komponente, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-126">To open the **Pivot** dialog box, add the Pivot transformation to the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and then right-click the component and click **Edit**.</span></span>  
  
 <span data-ttu-id="ff1ca-127">In der folgenden Liste werden die Optionen des Dialogfelds **Pivot** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-127">The following list describes the options in the **Pivot** dialog box.</span></span>  
  
 <span data-ttu-id="ff1ca-128">**Pivotschlüssel**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-128">**Pivot Key**</span></span>  
 <span data-ttu-id="ff1ca-129">Gibt die Spalte an, die für Werte über der obersten Zeile (Kopfzeile) der Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-129">Specifies the column to use for values across the top row (header row) of the table.</span></span>  
  
 <span data-ttu-id="ff1ca-130">**Schlüssel festlegen**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-130">**Set Key**</span></span>  
 <span data-ttu-id="ff1ca-131">Gibt die zu verwendende Spalte für Werte in der linken Spalte der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-131">Specifies the column to use for values in the left column of the table.</span></span> <span data-ttu-id="ff1ca-132">Das Eingabedatum muss nach dieser Spalte sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-132">The input date must be sorted on this column.</span></span>  
  
 <span data-ttu-id="ff1ca-133">**Pivotwert**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-133">**Pivot Value**</span></span>  
 <span data-ttu-id="ff1ca-134">Gibt die zu verwendende Spalte für die Tabellenwerte an, die sich von den Werten in der Kopfzeile und in der linken Spalte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-134">Specifies the column to use for the table values, other than the values in the header row and the left column.</span></span>  
  
 <span data-ttu-id="ff1ca-135">**Nicht übereinstimmende Pivotschlüsselwerte ignorieren und nach DataFlow-Ausführung melden**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-135">**Ignore un-matched Pivot Key values and report them after DataFlow execution**</span></span>  
 <span data-ttu-id="ff1ca-136">Aktivieren Sie diese Option, um die Pivottransformation so zu konfigurieren, dass Zeilen ignoriert werden, die nicht erkannte Werte in der Spalte **Pivotschlüssel** enthalten und dass alle Pivotschlüsselwerte zu einer Protokollmeldung ausgegeben werden, wenn das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-136">Select this option to configure the Pivot transformation to ignore rows containing unrecognized values in the **Pivot Key** column and to output all of the pivot key values to a log message, when the package is run.</span></span>  
  
 <span data-ttu-id="ff1ca-137">Sie können auch die Transformation konfigurieren, die Werte auszugeben, indem Sie die benutzerdefinierte Eigenschaft von `PassThroughUnmatchedPivotKeys` auf `True` festlegen.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-137">You can also configure the transformation to output the values by setting the `PassThroughUnmatchedPivotKeys` custom property to `True`.</span></span>  
  
 <span data-ttu-id="ff1ca-138">**Pivotausgabespalten aus Werten generieren**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-138">**Generate pivot output columns from values**</span></span>  
 <span data-ttu-id="ff1ca-139">Geben Sie die Pivotschlüsselwerte in diesem Feld ein, um die Pivottransformation zu aktivieren, um Ausgabespalten für jeden Wert zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-139">Enter the pivot key values in this box to enable the Pivot transformation to create output columns for each value.</span></span> <span data-ttu-id="ff1ca-140">Sie können entweder die Werte vor dem Ausführen des Pakets eingeben oder wie folgt vorgehen.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-140">You can either enter the values prior to running the package, or do the following.</span></span>  
  
1.  <span data-ttu-id="ff1ca-141">Wählen Sie die Option **Nicht übereinstimmende Pivotschlüsselwerte ignorieren und nach DataFlow-Ausführung melden** aus, und klicken Sie im Dialogfeld **Pivot** auf **OK** , um die Änderungen in Bezug auf die Pivottransformation zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-141">Select the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then click **OK** in the **Pivot** dialog box to save the changes to the Pivot transformation.</span></span>  
  
2.  <span data-ttu-id="ff1ca-142">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-142">Run the package.</span></span>  
  
3.  <span data-ttu-id="ff1ca-143">Wenn das Paket erfolgreich ist, klicken Sie auf die Registerkarte **Status** , und suchen Sie nach der Informationsprotokollmeldung der Pivottransformation, die die Pivotschlüsselwerte enthält.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-143">When the package succeeds, click the **Progress** tab and look for the information log message from the Pivot transformation that contains the pivot key values.</span></span>  
  
4.  <span data-ttu-id="ff1ca-144">Klicken Sie mit der rechten Maustaste auf die Meldung, und klicken Sie auf **Meldungstext kopieren**.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-144">Right-click the message and click **Copy Message Text**.</span></span>  
  
5.  <span data-ttu-id="ff1ca-145">Klicken Sie im Menü **Debuggen** auf **Debuggen beenden** , um in den Entwurfsmodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-145">Click **Stop Debugging** on the **Debug** menu to switch to the design mode.</span></span>  
  
6.  <span data-ttu-id="ff1ca-146">Klicken mit der rechten Maustaste auf die Pivottransformation, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-146">Right-click the Pivot transformation, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="ff1ca-147">Deaktivieren Sie die Option **Nicht übereinstimmende Pivotschlüsselwerte ignorieren und nach DataFlow-Ausführung melden** , und fügen Sie die Pivotschlüsselwerte anschließend in das Feld **Pivotausgabespalten aus Werten generieren** im folgenden Format ein.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-147">Uncheck the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then paste the pivot key values in the **Generate pivot output columns from values** box using the following format.</span></span>  
  
     <span data-ttu-id="ff1ca-148">[value1],[value2],[value3]</span><span class="sxs-lookup"><span data-stu-id="ff1ca-148">[value1],[value2],[value3]</span></span>  
  
 <span data-ttu-id="ff1ca-149">**Jetzt Spalten generieren**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-149">**Generate Columns Now**</span></span>  
 <span data-ttu-id="ff1ca-150">Klicken Sie auf diese Option, um eine Ausgabespalte für jeden Pivotschlüsselwert zu erstellen, der im Feld **Pivotausgabespalten aus Werten generieren** aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-150">Click to create an output column for each pivot key value that is listed in the **Generate pivot output columns from values** box.</span></span>  
  
 <span data-ttu-id="ff1ca-151">Die Ausgabespalten werden im Feld **Vorhandene pivotierte Ausgabespalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-151">The output columns appear in the **Existing pivoted output columns** box.</span></span>  
  
 <span data-ttu-id="ff1ca-152">**Vorhandene pivotierte Ausgabespalten**</span><span class="sxs-lookup"><span data-stu-id="ff1ca-152">**Existing pivoted output columns**</span></span>  
 <span data-ttu-id="ff1ca-153">Listet die Ausgabespalten für die Pivotschlüsselwerte auf.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-153">Lists the output columns for the pivot key values</span></span>  
  
 <span data-ttu-id="ff1ca-154">In der folgenden Tabelle wird ein Dataset vor dem Anwenden der Pivotierung auf die **Jahr** -Spalte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-154">The following table shows a data set before the data is pivoted on the **Year** column.</span></span>  
  
|<span data-ttu-id="ff1ca-155">Jahr</span><span class="sxs-lookup"><span data-stu-id="ff1ca-155">Year</span></span>|<span data-ttu-id="ff1ca-156">Produktname</span><span class="sxs-lookup"><span data-stu-id="ff1ca-156">Product Name</span></span>|<span data-ttu-id="ff1ca-157">Gesamt</span><span class="sxs-lookup"><span data-stu-id="ff1ca-157">Total</span></span>|  
|----------|------------------|-----------|  
|<span data-ttu-id="ff1ca-158">2004</span><span class="sxs-lookup"><span data-stu-id="ff1ca-158">2004</span></span>|<span data-ttu-id="ff1ca-159">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="ff1ca-159">HL Mountain Tire</span></span>|<span data-ttu-id="ff1ca-160">1504884.15</span><span class="sxs-lookup"><span data-stu-id="ff1ca-160">1504884.15</span></span>|  
|<span data-ttu-id="ff1ca-161">2003</span><span class="sxs-lookup"><span data-stu-id="ff1ca-161">2003</span></span>|<span data-ttu-id="ff1ca-162">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="ff1ca-162">Road Tire Tube</span></span>|<span data-ttu-id="ff1ca-163">35920.50</span><span class="sxs-lookup"><span data-stu-id="ff1ca-163">35920.50</span></span>|  
|<span data-ttu-id="ff1ca-164">2004</span><span class="sxs-lookup"><span data-stu-id="ff1ca-164">2004</span></span>|<span data-ttu-id="ff1ca-165">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-165">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="ff1ca-166">2805.00</span><span class="sxs-lookup"><span data-stu-id="ff1ca-166">2805.00</span></span>|  
|<span data-ttu-id="ff1ca-167">2002</span><span class="sxs-lookup"><span data-stu-id="ff1ca-167">2002</span></span>|<span data-ttu-id="ff1ca-168">Touring Tire</span><span class="sxs-lookup"><span data-stu-id="ff1ca-168">Touring Tire</span></span>|<span data-ttu-id="ff1ca-169">62364.225</span><span class="sxs-lookup"><span data-stu-id="ff1ca-169">62364.225</span></span>|  
  
 <span data-ttu-id="ff1ca-170">In der folgenden Tabelle wird ein Dataset nach dem Pivotieren der Daten nach der **Jahr** -Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-170">The following table shows a data set after the data has been pivoted on the **Year** column.</span></span>  
  
||<span data-ttu-id="ff1ca-171">2002</span><span class="sxs-lookup"><span data-stu-id="ff1ca-171">2002</span></span>|<span data-ttu-id="ff1ca-172">2003</span><span class="sxs-lookup"><span data-stu-id="ff1ca-172">2003</span></span>|<span data-ttu-id="ff1ca-173">2004</span><span class="sxs-lookup"><span data-stu-id="ff1ca-173">2004</span></span>|  
|-|----------|----------|----------|  
|<span data-ttu-id="ff1ca-174">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="ff1ca-174">HL Mountain Tire</span></span>|<span data-ttu-id="ff1ca-175">141164.10</span><span class="sxs-lookup"><span data-stu-id="ff1ca-175">141164.10</span></span>|<span data-ttu-id="ff1ca-176">446297.775</span><span class="sxs-lookup"><span data-stu-id="ff1ca-176">446297.775</span></span>|<span data-ttu-id="ff1ca-177">1504884.15</span><span class="sxs-lookup"><span data-stu-id="ff1ca-177">1504884.15</span></span>|  
|<span data-ttu-id="ff1ca-178">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="ff1ca-178">Road Tire Tube</span></span>|<span data-ttu-id="ff1ca-179">3592.05</span><span class="sxs-lookup"><span data-stu-id="ff1ca-179">3592.05</span></span>|<span data-ttu-id="ff1ca-180">35920.50</span><span class="sxs-lookup"><span data-stu-id="ff1ca-180">35920.50</span></span>|<span data-ttu-id="ff1ca-181">89801.25</span><span class="sxs-lookup"><span data-stu-id="ff1ca-181">89801.25</span></span>|  
|<span data-ttu-id="ff1ca-182">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-182">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="ff1ca-183">*NULL*</span><span class="sxs-lookup"><span data-stu-id="ff1ca-183">*NULL*</span></span>|<span data-ttu-id="ff1ca-184">*NULL*</span><span class="sxs-lookup"><span data-stu-id="ff1ca-184">*NULL*</span></span>|<span data-ttu-id="ff1ca-185">2805.00</span><span class="sxs-lookup"><span data-stu-id="ff1ca-185">2805.00</span></span>|  
|<span data-ttu-id="ff1ca-186">Touring Tire</span><span class="sxs-lookup"><span data-stu-id="ff1ca-186">Touring Tire</span></span>|<span data-ttu-id="ff1ca-187">62364.225</span><span class="sxs-lookup"><span data-stu-id="ff1ca-187">62364.225</span></span>|<span data-ttu-id="ff1ca-188">375051.60</span><span class="sxs-lookup"><span data-stu-id="ff1ca-188">375051.60</span></span>|<span data-ttu-id="ff1ca-189">1041810.00</span><span class="sxs-lookup"><span data-stu-id="ff1ca-189">1041810.00</span></span>|  
  
 <span data-ttu-id="ff1ca-190">Zum Pivotisieren der Daten für die **Jahr** -Spalte (wie oben gezeigt) müssen die folgenden Optionen im Dialogfeld **Pivot** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-190">To pivot the data on the **Year** column, as shown above, the following options are set in the **Pivot** dialog box.</span></span>  
  
-   <span data-ttu-id="ff1ca-191">Im Listenfeld **Pivot Key** wird Jahr ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-191">Year is selected in the **Pivot Key** list box.</span></span>  
  
-   <span data-ttu-id="ff1ca-192">Im Listenfeld **Schlüssel festlegen** wird Produktname ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-192">Product Name is selected in the **Set Key** list box.</span></span>  
  
-   <span data-ttu-id="ff1ca-193">Im Listenfeld **Pivotwert** wird Gesamt ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-193">Total is selected in the **Pivot Value** list box.</span></span>  
  
-   <span data-ttu-id="ff1ca-194">Die folgenden Werte werden im Feld **Pivotausgabespalten aus Werten generieren** eingegeben.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-194">The following values are entered in the **Generate pivot output columns from values** box.</span></span>  
  
     <span data-ttu-id="ff1ca-195">[2002],[2003],[2004]</span><span class="sxs-lookup"><span data-stu-id="ff1ca-195">[2002],[2003],[2004]</span></span>  
  
## <a name="configuration-of-the-pivot-transformation"></a><span data-ttu-id="ff1ca-196">Konfiguration der Transformation für Pivot</span><span class="sxs-lookup"><span data-stu-id="ff1ca-196">Configuration of the Pivot Transformation</span></span>  
 <span data-ttu-id="ff1ca-197">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="ff1ca-197">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ff1ca-198">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="ff1ca-198">For more information about the properties that you can set in the **Advanced Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ff1ca-199">Common Properties</span><span class="sxs-lookup"><span data-stu-id="ff1ca-199">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="ff1ca-200">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="ff1ca-200">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-content"></a><span data-ttu-id="ff1ca-201">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ff1ca-201">Related Content</span></span>  
 <span data-ttu-id="ff1ca-202">Informationen zum Festlegen der Eigenschaften dieser Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ff1ca-202">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1ca-203">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff1ca-203">See Also</span></span>  
 <span data-ttu-id="ff1ca-204">[Entpivotierungstransformation](pivot-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ff1ca-204">[Unpivot Transformation](pivot-transformation.md) </span></span>  
 <span data-ttu-id="ff1ca-205">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="ff1ca-205">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="ff1ca-206">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="ff1ca-206">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
