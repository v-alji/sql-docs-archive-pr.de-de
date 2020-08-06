---
title: Lookup-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 053fefff51e4b4e338e262664bd7570280c92540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617709"
---
# <a name="lookup-function-report-builder-and-ssrs"></a><span data-ttu-id="e7635-102">Lookup-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e7635-102">Lookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e7635-103">Gibt den ersten übereinstimmenden Wert für den angegebenen Namen aus einem Dataset mit Name-Wert-Paaren zurück.</span><span class="sxs-lookup"><span data-stu-id="e7635-103">Returns the first matching value for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="e7635-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7635-104">Syntax</span></span>  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7635-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7635-105">Parameters</span></span>  
 <span data-ttu-id="e7635-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="e7635-106">*source_expression*</span></span>  
 <span data-ttu-id="e7635-107">(`Variant`) Ein Ausdruck, der im aktuellen Bereich ausgewertet wird und der den zu suchenden Namen oder Schlüssel angibt.</span><span class="sxs-lookup"><span data-stu-id="e7635-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="e7635-108">Beispiel: `=Fields!ProdID.Value`.</span><span class="sxs-lookup"><span data-stu-id="e7635-108">For example, `=Fields!ProdID.Value`.</span></span>  
  
 <span data-ttu-id="e7635-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="e7635-109">*destination_expression*</span></span>  
 <span data-ttu-id="e7635-110">(`Variant`) Ein Ausdruck, der für jede Zeile in einem Dataset ausgewertet wird und der den Namen oder den Schlüssel für die Übereinstimmung angibt.</span><span class="sxs-lookup"><span data-stu-id="e7635-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="e7635-111">Beispiel: `=Fields!ProductID.Value`.</span><span class="sxs-lookup"><span data-stu-id="e7635-111">For example, `=Fields!ProductID.Value`.</span></span>  
  
 <span data-ttu-id="e7635-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="e7635-112">*result_expression*</span></span>  
 <span data-ttu-id="e7635-113">( `Variant` ) Ein Ausdruck, der für die Zeile im Dataset ausgewertet wird, in der *source_expression*  =  *destination_expression*und der den abzurufenden Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="e7635-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="e7635-114">Beispiel: `=Fields!ProductName.Value`.</span><span class="sxs-lookup"><span data-stu-id="e7635-114">For example, `=Fields!ProductName.Value`.</span></span>  
  
 <span data-ttu-id="e7635-115">*Dataset (dataset)*</span><span class="sxs-lookup"><span data-stu-id="e7635-115">*dataset*</span></span>  
 <span data-ttu-id="e7635-116">Eine Konstante, die den Namen eines Datasets im Bericht angibt.</span><span class="sxs-lookup"><span data-stu-id="e7635-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="e7635-117">Beispiel: "Products".</span><span class="sxs-lookup"><span data-stu-id="e7635-117">For example, "Products".</span></span>  
  
## <a name="return"></a><span data-ttu-id="e7635-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7635-118">Return</span></span>  
 <span data-ttu-id="e7635-119">Gibt einen Wert vom Typ `Variant` zurück; gibt `Nothing` zurück, wenn keine Übereinstimmung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e7635-119">Returns a `Variant`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7635-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e7635-120">Remarks</span></span>  
 <span data-ttu-id="e7635-121">Rufen Sie für ein Name-Wert-Paar, für das eine 1:1-Beziehung vorhanden ist, den Wert mithilfe von `Lookup` aus dem angegebenen Dataset ab.</span><span class="sxs-lookup"><span data-stu-id="e7635-121">Use `Lookup` to retrieve the value from the specified dataset for a name/value pair where there is a 1-to-1 relationship.</span></span> <span data-ttu-id="e7635-122">Beispiel: Für ein ID-Feld in einer Tabelle können Sie das entsprechende Namensfeld mithilfe von `Lookup` aus einem Dataset abrufen, das nicht an den Datenbereich gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="e7635-122">For example, for an ID field in a table, you can use `Lookup` to retrieve the corresponding Name field from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="e7635-123">Mit `Lookup` wird Folgendes ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="e7635-123">`Lookup` does the following:</span></span>  
  
-   <span data-ttu-id="e7635-124">Der Quellausdruck wird im aktuellen Bereich ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e7635-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="e7635-125">Der Zielausdruck wird für jede Zeile des angegebenen Datasets ausgewertet, nachdem Filter angewendet wurden, und zwar anhand der Sortierung des angegebenen Datasets.</span><span class="sxs-lookup"><span data-stu-id="e7635-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="e7635-126">Bei der ersten Übereinstimmung von Quellausdruck und Zielausdruck wird der Ergebnisausdruck für diese Zeile im Dataset ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e7635-126">On the first match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="e7635-127">Der Ergebnisausdruckswert wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7635-127">Returns the result expression value.</span></span>  
  
 <span data-ttu-id="e7635-128">Verwenden Sie [LookupSet-Funktion (Berichts-Generator und SSRS)](report-builder-functions-lookupset-function.md), um mehrere Werte für einen einzelnen Namen oder ein Schlüsselfeld abzurufen, für das eine 1:n-Beziehung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e7635-128">To retrieve multiple values for a single name or key field where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span> <span data-ttu-id="e7635-129">Um `Lookup` einen Satz von Werten aufzurufen, verwenden Sie die [Multilookup-Funktion &#40;Berichts-Generator und SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="e7635-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span>  
  
 <span data-ttu-id="e7635-130">Es gelten folgende Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="e7635-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="e7635-131">`Lookup`wird ausgewertet, nachdem alle Filter Ausdrücke angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e7635-131">`Lookup` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="e7635-132">Nur eine Suchebene wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7635-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="e7635-133">Ein Quell-, Ziel- oder Ergebnisausdruck kann keinen Verweis auf eine Suchfunktion einschließen.</span><span class="sxs-lookup"><span data-stu-id="e7635-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="e7635-134">Quell- und Zielausdrücke müssen den gleichen Datentyp ergeben.</span><span class="sxs-lookup"><span data-stu-id="e7635-134">Source and destination expressions must evaluate to the same data type.</span></span> <span data-ttu-id="e7635-135">Der Rückgabetyp ist der gleiche wie der Datentyp des ausgewerteten Ergebnisausdrucks.</span><span class="sxs-lookup"><span data-stu-id="e7635-135">The return type is the same as the data type of the evaluated result expression.</span></span>  
  
-   <span data-ttu-id="e7635-136">Quell-, Ziel- und Ergebnisausdrücke können keine Verweise auf Berichts- oder Gruppenvariablen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e7635-136">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="e7635-137">`Lookup` kann nicht als Ausdruck für die folgenden Berichtselemente verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e7635-137">`Lookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="e7635-138">Dynamische Verbindungszeichenfolgen für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="e7635-138">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="e7635-139">Berechnete Felder in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="e7635-139">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="e7635-140">Abfrageparameter in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="e7635-140">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="e7635-141">Filter in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="e7635-141">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="e7635-142">Berichtsparameter.</span><span class="sxs-lookup"><span data-stu-id="e7635-142">Report parameters.</span></span>  
  
    -   <span data-ttu-id="e7635-143">Die Eigenschaft „Report.Language“.</span><span class="sxs-lookup"><span data-stu-id="e7635-143">The Report.Language property.</span></span>  
  
 <span data-ttu-id="e7635-144">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="e7635-144">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7635-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7635-145">Example</span></span>  
 <span data-ttu-id="e7635-146">Nehmen Sie im folgenden Beispiel an, dass eine Tabelle an ein Dataset gebunden wird, das ein Feld für den Produktbezeichner "ProductID" enthält.</span><span class="sxs-lookup"><span data-stu-id="e7635-146">In the following example, assume that a table is bound to a dataset that includes a field for the product identifier ProductID.</span></span> <span data-ttu-id="e7635-147">Ein separates Dataset mit dem Namen "Product" enthält den entsprechenden Produktbezeichner "ID" und den Produktnamen "Name".</span><span class="sxs-lookup"><span data-stu-id="e7635-147">A separate dataset called "Product" contains the corresponding product identifier ID and the product name Name.</span></span>  
  
 <span data-ttu-id="e7635-148">Im folgenden Ausdruck vergleicht `Lookup` in jeder Zeile des Datasets "Product" den Wert von "ProductID" mit "ID". Wenn eine Übereinstimmung gefunden wird, wird der Wert des Felds "Name" für diese Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7635-148">In the following expression, `Lookup` compares the value of ProductID to ID in each row of the dataset called "Product" and, when a match is found, returns the value of the Name field for that row.</span></span>  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7635-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7635-149">See Also</span></span>  
 <span data-ttu-id="e7635-150">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7635-150">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7635-151">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7635-151">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7635-152">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7635-152">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e7635-153">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e7635-153">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
