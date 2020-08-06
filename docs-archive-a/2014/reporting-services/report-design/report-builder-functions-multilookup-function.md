---
title: Multilookup-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1fec079e-33b3-4e4d-92b3-6b4d06a49a77
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f2aff7a2a39e1a072cf4b05f0a04e12ced529af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617707"
---
# <a name="multilookup-function-report-builder-and-ssrs"></a><span data-ttu-id="ec4f2-102">Multilookup-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ec4f2-102">Multilookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ec4f2-103">Gibt den Satz der ersten übereinstimmenden Werte für den angegebenen Satz von Namen aus einem Dataset mit Name-Wert-Paaren zurück.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-103">Returns the set of first-match values for the specified set of names from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="ec4f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec4f2-104">Syntax</span></span>  
  
```  
  
Multilookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec4f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec4f2-105">Parameters</span></span>  
 <span data-ttu-id="ec4f2-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="ec4f2-106">*source_expression*</span></span>  
 <span data-ttu-id="ec4f2-107">(`VariantArray`) Ein Ausdruck, der im aktuellen Bereich ausgewertet wird und der den Satz der zu suchenden Namen oder Schlüssel angibt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-107">(`VariantArray`) An expression that is evaluated in the current scope and that specifies the set of names or keys to look up.</span></span> <span data-ttu-id="ec4f2-108">Beispiel für einen mehrwertigen Parameter: `=Parameters!IDs.value`.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-108">For example, for a multivalue parameter, `=Parameters!IDs.value`.</span></span>  
  
 <span data-ttu-id="ec4f2-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="ec4f2-109">*destination_expression*</span></span>  
 <span data-ttu-id="ec4f2-110">(`Variant`) Ein Ausdruck, der für jede Zeile in einem Dataset ausgewertet wird und der den Namen oder den Schlüssel für die Übereinstimmung angibt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="ec4f2-111">Beispiel: `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-111">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="ec4f2-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="ec4f2-112">*result_expression*</span></span>  
 <span data-ttu-id="ec4f2-113">( `Variant` ) Ein Ausdruck, der für die Zeile im Dataset ausgewertet wird, in der *source_expression*  =  *destination_expression*und der den abzurufenden Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="ec4f2-114">Beispiel: `=Fields!Name.Value`.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-114">For example, `=Fields!Name.Value`.</span></span>  
  
 <span data-ttu-id="ec4f2-115">*Dataset (dataset)*</span><span class="sxs-lookup"><span data-stu-id="ec4f2-115">*dataset*</span></span>  
 <span data-ttu-id="ec4f2-116">Eine Konstante, die den Namen eines Datasets im Bericht angibt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="ec4f2-117">Beispiel: "Colors".</span><span class="sxs-lookup"><span data-stu-id="ec4f2-117">For example, "Colors".</span></span>  
  
## <a name="return"></a><span data-ttu-id="ec4f2-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec4f2-118">Return</span></span>  
 <span data-ttu-id="ec4f2-119">Gibt einen Wert vom Typ `VariantArray` zurück; gibt `Nothing` zurück, wenn keine Übereinstimmung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec4f2-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ec4f2-120">Remarks</span></span>  
 <span data-ttu-id="ec4f2-121">Verwenden Sie `Multilookup`, um eine Wertemenge aus einem Dataset für Name-Wert-Paare abzurufen, in dem jedes Paar über eine 1:1-Beziehung verfügt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-121">Use `Multilookup` to retrieve a set of values from a dataset for name-value pairs where each pair has a 1-to-1 relationship.</span></span> <span data-ttu-id="ec4f2-122">`MultiLookup` ist mit dem Aufrufen von `Lookup` für eine Menge von Namen oder Schlüsseln vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-122">`MultiLookup` is the equivalent of calling `Lookup` for a set of names or keys.</span></span> <span data-ttu-id="ec4f2-123">Beispiel: Für einen mehrwertigen Parameter, der auf Primärschlüsselbezeichnern basiert, können Sie `Multilookup` in einem Ausdruck in einem Textfeld in einer Tabelle verwenden, um zugeordnete Werte aus einem Dataset abzurufen, das nicht an den Parameter oder die Tabelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-123">For example, for a multivalue parameter that is based on primary key identifiers, you can use `Multilookup` in an expression in a text box in a table to retrieve associated values from a dataset that is not bound to the parameter or to the table.</span></span>  
  
 <span data-ttu-id="ec4f2-124">Mit `Multilookup` wird Folgendes ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="ec4f2-124">`Multilookup` does the following:</span></span>  
  
-   <span data-ttu-id="ec4f2-125">Der Quellausdruck wird im aktuellen Bereich ausgewertet, und ein Array von Variant-Objekten wird generiert.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-125">Evaluates the source expression in the current scope and generates an array of variant objects.</span></span>  
  
-   <span data-ttu-id="ec4f2-126">Für jedes Objekt im Array wird die [Lookup-Funktion (Berichts-Generator und SSRS)](report-builder-functions-lookup-function.md) aufgerufen und dem Rückgabearray das Ergebnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-126">For each object in the array, calls [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md) and adds the result to the return array.</span></span>  
  
-   <span data-ttu-id="ec4f2-127">Der Satz von Ergebnissen wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-127">Returns the set of results.</span></span>  
  
 <span data-ttu-id="ec4f2-128">Verwenden Sie die [Lookup-Funktion (Berichts-Generator und SSRS)](report-builder-functions-lookup-function.md), um einen einzelnen Wert aus einem Dataset mit Name-Wert-Paaren für einen angegebenen Namen abzurufen, wenn eine 1:1-Beziehung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-128">To retrieve a single value from a dataset with name-value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="ec4f2-129">Verwenden Sie die [LookupSet-Funktion (Berichts-Generator und SSRS)](report-builder-functions-lookupset-function.md), um mehrere Werte aus einem Dataset mit Name-Wert-Paaren für einen Namen abzurufen, wenn eine 1:n-Beziehung besteht.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-129">To retrieve multiple values from a dataset with name-value pairs for a name where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span>  
  
 <span data-ttu-id="ec4f2-130">Es gelten folgende Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="ec4f2-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="ec4f2-131">`Multilookup` wird ausgewertet, nachdem alle Filterausdrücke angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-131">`Multilookup` is evaluated after all filter expressions are applied</span></span>  
  
-   <span data-ttu-id="ec4f2-132">Nur eine Suchebene wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-132">Only one level of look-up is supported.</span></span> <span data-ttu-id="ec4f2-133">Ein Quell-, Ziel- oder Ergebnisausdruck kann keinen Verweis auf eine Suchfunktion einschließen.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="ec4f2-134">Quell- und Zielausdrücke müssen den gleichen Datentyp ergeben.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="ec4f2-135">Quell-, Ziel- und Ergebnisausdrücke können keine Verweise auf Berichts- oder Gruppenvariablen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="ec4f2-136">`Multilookup` kann nicht als Ausdruck für die folgenden Berichtselemente verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ec4f2-136">`Multilookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="ec4f2-137">Dynamische Verbindungszeichenfolgen für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="ec4f2-138">Berechnete Felder in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="ec4f2-139">Abfrageparameter in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="ec4f2-140">Filter in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="ec4f2-141">Berichtsparameter.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="ec4f2-142">Die Eigenschaft „Report.Language“.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="ec4f2-143">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="ec4f2-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec4f2-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec4f2-144">Example</span></span>  
 <span data-ttu-id="ec4f2-145">Angenommen, ein Dataset mit dem Namen "Category" enthält das Feld "CategoryList", das eine durch Trennzeichen getrennte Liste von Kategoriebezeichnern enthält, wie z. B. "2, 4, 2, 1".</span><span class="sxs-lookup"><span data-stu-id="ec4f2-145">Assume a dataset called "Category" contains the field CategoryList, which is a field that contains a comma-separated list of category identifers, for example, "2, 4, 2, 1".</span></span>  
  
 <span data-ttu-id="ec4f2-146">Das Dataset "CategoryNames" enthält den Kategoriebezeichner und den Kategorienamen, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-146">The dataset CategoryNames contains the category identifier and category name, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ec4f2-147">id</span><span class="sxs-lookup"><span data-stu-id="ec4f2-147">ID</span></span>|<span data-ttu-id="ec4f2-148">Name</span><span class="sxs-lookup"><span data-stu-id="ec4f2-148">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="ec4f2-149">1</span><span class="sxs-lookup"><span data-stu-id="ec4f2-149">1</span></span>|<span data-ttu-id="ec4f2-150">Accessories</span><span class="sxs-lookup"><span data-stu-id="ec4f2-150">Accessories</span></span>|  
|<span data-ttu-id="ec4f2-151">2</span><span class="sxs-lookup"><span data-stu-id="ec4f2-151">2</span></span>|<span data-ttu-id="ec4f2-152">Bikes</span><span class="sxs-lookup"><span data-stu-id="ec4f2-152">Bikes</span></span>|  
|<span data-ttu-id="ec4f2-153">3</span><span class="sxs-lookup"><span data-stu-id="ec4f2-153">3</span></span>|<span data-ttu-id="ec4f2-154">Clothing</span><span class="sxs-lookup"><span data-stu-id="ec4f2-154">Clothing</span></span>|  
|<span data-ttu-id="ec4f2-155">4</span><span class="sxs-lookup"><span data-stu-id="ec4f2-155">4</span></span>|<span data-ttu-id="ec4f2-156">Komponenten</span><span class="sxs-lookup"><span data-stu-id="ec4f2-156">Components</span></span>|  
  
 <span data-ttu-id="ec4f2-157">Verwenden Sie für die Suche der Namen, die der Liste der Bezeichner entsprechen, `Multilookup`.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-157">To look up the names that correspond to the list of  identifiers, use `Multilookup`.</span></span> <span data-ttu-id="ec4f2-158">Sie müssen zuerst die Liste in ein Zeichenfolgenarray aufteilen, `Multilookup` aufrufen, um die Kategorienamen abzurufen, und die Ergebnisse zu einer Zeichenfolge verketten.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-158">You must first split the list into a string array, call `Multilookup` to retrieve the category names, and concatenate the results into a string.</span></span>  
  
 <span data-ttu-id="ec4f2-159">Wenn der folgende Ausdruck in ein Textfeld in einem Datenbereich platziert wird, der an das Dataset "Category" gebunden ist, wird "Bikes, Components, Bikes, Accessories" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec4f2-159">The following expression, when placed in a text box in a data region bound to the Category dataset, displays "Bikes, Components, Bikes, Accessories":</span></span>  
  
```  
=Join(MultiLookup(Split(Fields!CategoryList.Value,","),  
   Fields!CategoryID.Value,Fields!CategoryName.Value,"Category")),  
   ", ")  
```  
  
## <a name="example"></a><span data-ttu-id="ec4f2-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec4f2-160">Example</span></span>  
 <span data-ttu-id="ec4f2-161">Angenommen, ein Dataset "ProductColors" enthält ein Farbbezeichnerfeld "ColorID" und ein Farbwertfeld "Color", wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-161">Assume a dataset ProductColors contains a color identifier field ColorID and a color value field Color, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ec4f2-162">ColorID</span><span class="sxs-lookup"><span data-stu-id="ec4f2-162">ColorID</span></span>|<span data-ttu-id="ec4f2-163">Color</span><span class="sxs-lookup"><span data-stu-id="ec4f2-163">Color</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="ec4f2-164">1</span><span class="sxs-lookup"><span data-stu-id="ec4f2-164">1</span></span>|<span data-ttu-id="ec4f2-165">Red</span><span class="sxs-lookup"><span data-stu-id="ec4f2-165">Red</span></span>|  
|<span data-ttu-id="ec4f2-166">2</span><span class="sxs-lookup"><span data-stu-id="ec4f2-166">2</span></span>|<span data-ttu-id="ec4f2-167">Blau</span><span class="sxs-lookup"><span data-stu-id="ec4f2-167">Blue</span></span>|  
|<span data-ttu-id="ec4f2-168">3</span><span class="sxs-lookup"><span data-stu-id="ec4f2-168">3</span></span>|<span data-ttu-id="ec4f2-169">Grün</span><span class="sxs-lookup"><span data-stu-id="ec4f2-169">Green</span></span>|  
  
 <span data-ttu-id="ec4f2-170">Angenommen, der mehrwertige Parameter *MyColors* ist nicht an ein Dataset für seine verfügbaren Werte gebunden.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-170">Assume the multivalue parameter *MyColors* is not bound to a dataset for its available values.</span></span> <span data-ttu-id="ec4f2-171">Die Standardwerte für den Parameter sind auf 2 und 3 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-171">The default values for the parameter are set to 2 and 3.</span></span> <span data-ttu-id="ec4f2-172">Wenn der folgende Ausdruck in einem Textfeld in einer Tabelle platziert wird, werden die ausgewählten Werte für den Parameter zu einer durch Trennzeichen getrennten Liste verkettet, und es wird "Blue, Green" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec4f2-172">The following expression, when placed in a text box in a table, concatenates the multiple selected values for the parameter into a comma-separated list and displays "Blue, Green".</span></span>  
  
```  
=Join(MultiLookup(Parameters!MyColors.Value,Fields!ColorID.Value,Fields!Color.Value,"ProductColors"),", ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec4f2-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec4f2-173">See Also</span></span>  
 <span data-ttu-id="ec4f2-174">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec4f2-174">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec4f2-175">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec4f2-175">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec4f2-176">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec4f2-176">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ec4f2-177">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ec4f2-177">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
