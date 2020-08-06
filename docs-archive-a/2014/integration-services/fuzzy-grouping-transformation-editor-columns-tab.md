---
title: Transformations-Editor für Fuzzygruppierung (Registerkarte Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.columns.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 24f4539f-2a9f-4acd-acc7-06228a07f7df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3aef9c30a81760b7f09378a8ecd66fee0dac62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696989"
---
# <a name="fuzzy-grouping-transformation-editor-columns-tab"></a><span data-ttu-id="39afd-102">Transformations-Editor für Fuzzygruppierung (Registerkarte Spalten)</span><span class="sxs-lookup"><span data-stu-id="39afd-102">Fuzzy Grouping Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="39afd-103">Mithilfe der Registerkarte **Spalten** des Dialogfelds **Transformations-Editor für Fuzzygruppierung** können Sie die Spalten angeben, die zum Gruppieren von Zeilen mit doppelten Werten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39afd-103">Use the **Columns** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify the columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="39afd-104">Weitere Informationen zur Transformation für Fuzzygruppierung finden Sie unter [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="39afd-104">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="39afd-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="39afd-105">Options</span></span>  
 <span data-ttu-id="39afd-106">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="39afd-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="39afd-107">Wählen Sie aus dieser Liste die Eingabespalten, mit denen Zeilen mit doppelten Werten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39afd-107">Select from this list the input columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="39afd-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="39afd-108">**Name**</span></span>  
 <span data-ttu-id="39afd-109">Zeigt die Namen der verfügbaren Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="39afd-109">View the names of available input columns.</span></span>  
  
 <span data-ttu-id="39afd-110">**Pass-Through**</span><span class="sxs-lookup"><span data-stu-id="39afd-110">**Pass Through**</span></span>  
 <span data-ttu-id="39afd-111">Wählen Sie aus, ob die Eingabespalte in der Ausgabe der Transformation eingeschlossen sein soll.</span><span class="sxs-lookup"><span data-stu-id="39afd-111">Select whether to include the input column in the output of the transformation.</span></span> <span data-ttu-id="39afd-112">Alle für die Gruppierung verwendeten Spalten werden automatisch in die Ausgabe kopiert.</span><span class="sxs-lookup"><span data-stu-id="39afd-112">All columns used for grouping are automatically copied to the output.</span></span> <span data-ttu-id="39afd-113">Sie können weitere Spalten einschließen, indem Sie diese Spalten auswählen.</span><span class="sxs-lookup"><span data-stu-id="39afd-113">You can include additional columns by checking this column.</span></span>  
  
 <span data-ttu-id="39afd-114">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="39afd-114">**Input Column**</span></span>  
 <span data-ttu-id="39afd-115">Wählen Sie eine der zu einem früheren Zeitpunkt aus der Liste **Verfügbare Eingabespalten** ausgewählten Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="39afd-115">Select one of the input columns selected earlier in the **Available Input Columns** list.</span></span>  
  
 <span data-ttu-id="39afd-116">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="39afd-116">**Output Alias**</span></span>  
 <span data-ttu-id="39afd-117">Geben Sie einen beschreibenden Namen für die entsprechende Ausgabespalte ein.</span><span class="sxs-lookup"><span data-stu-id="39afd-117">Enter a descriptive name for the corresponding output column.</span></span> <span data-ttu-id="39afd-118">Standardmäßig stimmt der Name der Ausgabespalte mit dem Namen der Eingabespalte überein.</span><span class="sxs-lookup"><span data-stu-id="39afd-118">By default, the output column name is the same as the input column name.</span></span>  
  
 <span data-ttu-id="39afd-119">**Gruppenausgabealias**</span><span class="sxs-lookup"><span data-stu-id="39afd-119">**Group Output Alias**</span></span>  
 <span data-ttu-id="39afd-120">Geben Sie einen beschreibenden Namen für die Spalte ein, die den kanonischen Wert für die gruppierten Duplikate enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="39afd-120">Enter a descriptive name for the column that will contain the canonical value for the grouped duplicates.</span></span> <span data-ttu-id="39afd-121">Der Standardname dieser Ausgabespalte entspricht dem Namen der Eingabespalte mit dem Anhang _clean.</span><span class="sxs-lookup"><span data-stu-id="39afd-121">The default name of this output column is the input column name with _clean appended.</span></span>  
  
 <span data-ttu-id="39afd-122">**Übereinstimmungstyp**</span><span class="sxs-lookup"><span data-stu-id="39afd-122">**Match Type**</span></span>  
 <span data-ttu-id="39afd-123">Wählen Sie genaue oder Fuzzyübereinstimmungen aus.</span><span class="sxs-lookup"><span data-stu-id="39afd-123">Select fuzzy or exact matching.</span></span> <span data-ttu-id="39afd-124">Zeilen werden als Duplikate angesehen, wenn Sie über alle Spalten hinweg eine genügend große Ähnlichkeit mit dem Typ einer Fuzzyübereinstimmung haben.</span><span class="sxs-lookup"><span data-stu-id="39afd-124">Rows are considered duplicates if they are sufficiently similar across all columns with a fuzzy match type.</span></span> <span data-ttu-id="39afd-125">Wenn Sie für bestimmte Spalten auch die genaue Übereinstimmung angeben, werden in den Spalten mit den genauen Übereinstimmungen nur Zeilen mit identischen Werten als mögliche Duplikate angesehen.</span><span class="sxs-lookup"><span data-stu-id="39afd-125">If you also specify exact matching on certain columns, only rows that contain identical values in the exact matching columns are considered as possible duplicates.</span></span> <span data-ttu-id="39afd-126">Wenn Sie also wissen, dass eine bestimmte Spalte keine Fehler oder Inkonsistenzen enthält, können Sie für diese Spalte die genaue Übereinstimmung angeben, um die Genauigkeit der Fuzzyübereinstimmungen für andere Spalten zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="39afd-126">Therefore, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column to increase the accuracy of the fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="39afd-127">**Minimale Ähnlichkeit**</span><span class="sxs-lookup"><span data-stu-id="39afd-127">**Minimum Similarity**</span></span>  
 <span data-ttu-id="39afd-128">Legen Sie mithilfe des Schiebereglers den Schwellenwert für Ähnlichkeit auf Joinebene fest.</span><span class="sxs-lookup"><span data-stu-id="39afd-128">Set the similarity threshold at the join level by using the slider.</span></span> <span data-ttu-id="39afd-129">Je näher der Wert an 1 liegt, desto stärker muss die Ähnlichkeit zwischen Suchwert und Quellwert sein, um als Übereinstimmung zu gelten.</span><span class="sxs-lookup"><span data-stu-id="39afd-129">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="39afd-130">Durch eine Erhöhung des Schwellenwertes kann die Geschwindigkeit beim Abgleich erhöht werden, weil als Kandidaten dann weniger Datensätze berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="39afd-130">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="39afd-131">**Ähnlichkeitsausgabealias**</span><span class="sxs-lookup"><span data-stu-id="39afd-131">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="39afd-132">Geben Sie den Namen für eine Ausgabespalte an, die die Ähnlichkeitsergebnisse für den ausgewählten Join enthält.</span><span class="sxs-lookup"><span data-stu-id="39afd-132">Specify the name for a new output column that contains the similarity scores for the selected join.</span></span> <span data-ttu-id="39afd-133">Wenn Sie diesen Wert nicht angeben, wird die Ausgabespalte nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="39afd-133">If you leave this value empty, the output column is not created.</span></span>  
  
 <span data-ttu-id="39afd-134">**Zahlen**</span><span class="sxs-lookup"><span data-stu-id="39afd-134">**Numerals**</span></span>  
 <span data-ttu-id="39afd-135">Gibt die Bedeutung führender und nachfolgender Zahlen beim Vergleichen der Spaltendaten an.</span><span class="sxs-lookup"><span data-stu-id="39afd-135">Specify the significance of leading and trailing numerals in comparing the column data.</span></span> <span data-ttu-id="39afd-136">Wenn beispielsweise führende Zahlen von Bedeutung sind, wird "123 Main Street" nicht mit "456 Main Street" gruppiert.</span><span class="sxs-lookup"><span data-stu-id="39afd-136">For example, if leading numerals are significant, "123 Main Street" will not be grouped with "456 Main Street."</span></span>  
  
|<span data-ttu-id="39afd-137">Wert</span><span class="sxs-lookup"><span data-stu-id="39afd-137">Value</span></span>|<span data-ttu-id="39afd-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="39afd-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39afd-139">**Neither**</span><span class="sxs-lookup"><span data-stu-id="39afd-139">**Neither**</span></span>|<span data-ttu-id="39afd-140">Weder führende noch nachfolgende Zahlen sind von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="39afd-140">Leading and trailing numerals are not significant.</span></span>|  
|<span data-ttu-id="39afd-141">**Führende**</span><span class="sxs-lookup"><span data-stu-id="39afd-141">**Leading**</span></span>|<span data-ttu-id="39afd-142">Nur führende Zahlen sind von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="39afd-142">Only leading numerals are significant.</span></span>|  
|<span data-ttu-id="39afd-143">**Trailing**</span><span class="sxs-lookup"><span data-stu-id="39afd-143">**Trailing**</span></span>|<span data-ttu-id="39afd-144">Nur nachfolgende Zahlen sind von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="39afd-144">Only trailing numerals are significant.</span></span>|  
|<span data-ttu-id="39afd-145">**LeadingAndTrailing**</span><span class="sxs-lookup"><span data-stu-id="39afd-145">**LeadingAndTrailing**</span></span>|<span data-ttu-id="39afd-146">Sowohl führende als auch nachfolgende Zahlen sind von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="39afd-146">Both leading and trailing numerals are significant.</span></span>|  
  
 <span data-ttu-id="39afd-147">**Vergleichsflags**</span><span class="sxs-lookup"><span data-stu-id="39afd-147">**Comparison Flags**</span></span>  
 <span data-ttu-id="39afd-148">Weitere Informationen zu den Optionen für das Vergleichen von Zeichenfolgen finden Sie unter [Vergleichen von Zeichenfolgendaten](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="39afd-148">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39afd-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39afd-149">See Also</span></span>  
 <span data-ttu-id="39afd-150">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="39afd-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="39afd-151">Identifizieren ähnlicher Datenzeilen mithilfe der Transformation für Fuzzygruppierung</span><span class="sxs-lookup"><span data-stu-id="39afd-151">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
