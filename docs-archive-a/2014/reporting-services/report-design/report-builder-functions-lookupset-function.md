---
title: LookupSet-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7685acfd-1c8d-420c-993c-903236fbe1ff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4edc7a17f2aa3813e8aa73e538594b5df3aeabc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617712"
---
# <a name="lookupset-function-report-builder-and-ssrs"></a><span data-ttu-id="bee07-102">LookupSet-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="bee07-102">LookupSet Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bee07-103">Gibt den Satz der übereinstimmenden Werte für den angegebenen Namen aus einem Dataset mit Name-Wert-Paaren zurück.</span><span class="sxs-lookup"><span data-stu-id="bee07-103">Returns the set of matching values for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="bee07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bee07-104">Syntax</span></span>  
  
```  
  
LookupSet(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bee07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bee07-105">Parameters</span></span>  
 <span data-ttu-id="bee07-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="bee07-106">*source_expression*</span></span>  
 <span data-ttu-id="bee07-107">(`Variant`) Ein Ausdruck, der im aktuellen Bereich ausgewertet wird und der den zu suchenden Namen oder Schlüssel angibt.</span><span class="sxs-lookup"><span data-stu-id="bee07-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="bee07-108">Beispiel: `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="bee07-108">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="bee07-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="bee07-109">*destination_expression*</span></span>  
 <span data-ttu-id="bee07-110">(`Variant`) Ein Ausdruck, der für jede Zeile in einem Dataset ausgewertet wird und der den Namen oder den Schlüssel für die Übereinstimmung angibt.</span><span class="sxs-lookup"><span data-stu-id="bee07-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="bee07-111">Beispiel: `=Fields!CustomerID.Value`.</span><span class="sxs-lookup"><span data-stu-id="bee07-111">For example, `=Fields!CustomerID.Value`.</span></span>  
  
 <span data-ttu-id="bee07-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="bee07-112">*result_expression*</span></span>  
 <span data-ttu-id="bee07-113">( `Variant` ) Ein Ausdruck, der für die Zeile im Dataset ausgewertet wird, in der *source_expression*  =  *destination_expression*und der den abzurufenden Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="bee07-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="bee07-114">Beispiel: `=Fields!PhoneNumber.Value`.</span><span class="sxs-lookup"><span data-stu-id="bee07-114">For example, `=Fields!PhoneNumber.Value`.</span></span>  
  
 <span data-ttu-id="bee07-115">*Dataset (dataset)*</span><span class="sxs-lookup"><span data-stu-id="bee07-115">*dataset*</span></span>  
 <span data-ttu-id="bee07-116">Eine Konstante, die den Namen eines Datasets im Bericht angibt.</span><span class="sxs-lookup"><span data-stu-id="bee07-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="bee07-117">Beispiel: "ContactInformation".</span><span class="sxs-lookup"><span data-stu-id="bee07-117">For example, "ContactInformation".</span></span>  
  
## <a name="return"></a><span data-ttu-id="bee07-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bee07-118">Return</span></span>  
 <span data-ttu-id="bee07-119">Gibt einen Wert vom Typ `VariantArray` zurück; gibt `Nothing` zurück, wenn keine Übereinstimmung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bee07-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bee07-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bee07-120">Remarks</span></span>  
 <span data-ttu-id="bee07-121">Rufen Sie für ein Name-Wert-Paar, für das eine 1:n-Beziehung vorhanden ist, einen Satz von Werten mithilfe von `LookupSet` aus dem angegebenen Dataset ab.</span><span class="sxs-lookup"><span data-stu-id="bee07-121">Use `LookupSet` to retrieve a set of values from the specified dataset for a name/value pair where there is a 1-to-many relationship.</span></span> <span data-ttu-id="bee07-122">Beispiel: Für einen Kundenbezeichner in einer Tabelle können Sie alle zugeordneten Telefonnummern dieses Kunden aus einem Dataset, das nicht an den Datenbereich gebunden ist, mithilfe von `LookupSet` abrufen.</span><span class="sxs-lookup"><span data-stu-id="bee07-122">For example, for a customer identifier in a table, you can use `LookupSet` to retrieve all the associated phone numbers for that customer from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="bee07-123">Mit `LookupSet` wird Folgendes ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="bee07-123">`LookupSet` does the following:</span></span>  
  
-   <span data-ttu-id="bee07-124">Der Quellausdruck wird im aktuellen Bereich ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bee07-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="bee07-125">Der Zielausdruck wird für jede Zeile des angegebenen Datasets ausgewertet, nachdem Filter angewendet wurden, und zwar anhand der Sortierung des angegebenen Datasets.</span><span class="sxs-lookup"><span data-stu-id="bee07-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="bee07-126">Für jede Übereinstimmung von Quellausdruck und Zielausdruck wird der Ergebnisausdruck für diese Zeile im Dataset ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bee07-126">For each match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="bee07-127">Der Satz von Ergebnisausdruckswerten wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bee07-127">Returns the set of result expression values.</span></span>  
  
 <span data-ttu-id="bee07-128">Verwenden Sie die [Lookup-Funktion (Berichts-Generator und SSRS)](report-builder-functions-lookup-function.md), um einen einzelnen Wert aus einem Dataset mit Name-Wert-Paaren für einen angegebenen Namen abzurufen, wenn eine 1:1-Beziehung besteht.</span><span class="sxs-lookup"><span data-stu-id="bee07-128">To retrieve a single value from a dataset with name/value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="bee07-129">Um `Lookup` einen Satz von Werten aufzurufen, verwenden Sie die [Multilookup-Funktion &#40;Berichts-Generator und SSRS&#41;](report-builder-functions-multilookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="bee07-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-multilookup-function.md).</span></span>  
  
 <span data-ttu-id="bee07-130">Es gelten folgende Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="bee07-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="bee07-131">`LookupSet`wird ausgewertet, nachdem alle Filter Ausdrücke angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="bee07-131">`LookupSet` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="bee07-132">Nur eine Suchebene wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bee07-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="bee07-133">Ein Quell-, Ziel- oder Ergebnisausdruck kann keinen Verweis auf eine Suchfunktion einschließen.</span><span class="sxs-lookup"><span data-stu-id="bee07-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="bee07-134">Quell- und Zielausdrücke müssen den gleichen Datentyp ergeben.</span><span class="sxs-lookup"><span data-stu-id="bee07-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="bee07-135">Quell-, Ziel- und Ergebnisausdrücke können keine Verweise auf Berichts- oder Gruppenvariablen einschließen.</span><span class="sxs-lookup"><span data-stu-id="bee07-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="bee07-136">`LookupSet` kann nicht als Ausdruck für die folgenden Berichtselemente verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bee07-136">`LookupSet` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="bee07-137">Dynamische Verbindungszeichenfolgen für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="bee07-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="bee07-138">Berechnete Felder in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="bee07-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="bee07-139">Abfrageparameter in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="bee07-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="bee07-140">Filter in einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="bee07-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="bee07-141">Berichtsparameter.</span><span class="sxs-lookup"><span data-stu-id="bee07-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="bee07-142">Die Eigenschaft „Report.Language“.</span><span class="sxs-lookup"><span data-stu-id="bee07-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="bee07-143">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="bee07-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bee07-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bee07-144">Example</span></span>  
 <span data-ttu-id="bee07-145">Nehmen Sie im folgenden Beispiel an, dass die Tabelle an ein Dataset gebunden ist, das einen Vertriebsgebietbezeichner "TerritoryGroupID" enthält.</span><span class="sxs-lookup"><span data-stu-id="bee07-145">In the following example, assume the table is bound to a dataset that includes a sales territory identifier TerritoryGroupID.</span></span> <span data-ttu-id="bee07-146">Ein separates Dataset mit dem Namen "Stores" enthält die Liste aller Läden in einem Gebiet und schließt den Gebietsbezeichner "ID" sowie den Namen des Ladens "StoreName" ein.</span><span class="sxs-lookup"><span data-stu-id="bee07-146">A separate dataset called "Stores" contains the list of all stores in a territory and includes the territory identifier ID and the name of the store StoreName.</span></span>  
  
 <span data-ttu-id="bee07-147">Im folgenden Ausdruck vergleicht `LookupSet` für jede Zeile im Dataset "Stores" den Wert "TerritoryGroupID" mit "ID".</span><span class="sxs-lookup"><span data-stu-id="bee07-147">In the following expression, `LookupSet` compares the value TerritoryGroupID to ID for each row in the dataset called "Stores".</span></span> <span data-ttu-id="bee07-148">Für jede Übereinstimmung wird dem Resultset der Wert des Felds "StoreName" für diese Zeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bee07-148">For each match, the value of the StoreName field for that row is added to the result set.</span></span>  
  
```  
=LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores")  
```  
  
## <a name="example"></a><span data-ttu-id="bee07-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bee07-149">Example</span></span>  
 <span data-ttu-id="bee07-150">Da `LookupSet` eine Sammlung von Objekten zurückgibt, können Sie den Ergebnisausdruck nicht direkt in einem Textfeld anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bee07-150">Because `LookupSet` returns a collection of objects, you cannot display the result expression directly in a text box.</span></span> <span data-ttu-id="bee07-151">Sie können die Werte der Objekte in der Sammlung als Zeichenfolge verketten.</span><span class="sxs-lookup"><span data-stu-id="bee07-151">You can concatenate the value of each object in the collection as a string.</span></span>  
  
 <span data-ttu-id="bee07-152">Verwenden Sie die [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]-Funktion `Join`, um aus einem Satz von Objekten eine Zeichenfolge mit Trennzeichen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bee07-152">Use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] function `Join` create a delimited string from a set of objects.</span></span> <span data-ttu-id="bee07-153">Verwenden Sie ein Komma als Trennzeichen, um die Objekte an einer einzelnen Zeile zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="bee07-153">Use a comma as a separator to combine the objects in a single line.</span></span> <span data-ttu-id="bee07-154">In einigen Renderern könnten Sie einen [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Zeilenvorschub (`vbCrLF`) als Trennzeichen verwenden, um jeden Wert auf einer neuen Zeile aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="bee07-154">In some renderers, you might use a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] line feed (`vbCrLF`) as a separator to list each value on a new line.</span></span>  
  
 <span data-ttu-id="bee07-155">Der folgende Ausdruck verwendet, wenn er als Value-Eigenschaft für ein Textfeld verwendet wird, `Join` um eine Liste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bee07-155">The following expression, when it is used as the Value property for a text box, uses `Join` to create a list.</span></span>  
  
```  
=Join(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"),",")  
```  
  
## <a name="example"></a><span data-ttu-id="bee07-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bee07-156">Example</span></span>  
 <span data-ttu-id="bee07-157">Für Textfelder, die nur wenige Male gerendert werden, könnten Sie wahlweise benutzerdefinierten Code hinzufügen, um HTML-Code zum Anzeigen von Werten in einem Textfeld zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bee07-157">For text boxes that only render a few times, you might choose to add custom code to generate HTML to display values in a text box.</span></span> <span data-ttu-id="bee07-158">HTML-Code in einem Textfeld erfordert zusätzliche Verarbeitung, deshalb ist dies nicht empfehlenswert für ein Textfeld, das Tausende Male gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="bee07-158">HTML in a text box requires extra processing, so this would not be a good choice for a text box that is rendered thousands of times.</span></span>  
  
 <span data-ttu-id="bee07-159">Kopieren Sie die folgenden [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Funktionen in einen Codeblock in einer Berichtsdefinition.</span><span class="sxs-lookup"><span data-stu-id="bee07-159">Copy the following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to a Code block in a report definition.</span></span> <span data-ttu-id="bee07-160">**MakeList** erstellt aus dem Objektarray, das in *result_expression* zurückgegeben wird, mithilfe von HTML-Tags eine ungeordnete Liste.</span><span class="sxs-lookup"><span data-stu-id="bee07-160">**MakeList** takes the object array that is returned in *result_expression* and builds an unordered list by using HTML tags.</span></span> <span data-ttu-id="bee07-161">**Length** gibt die Anzahl der Elemente im Objektarray zurück.</span><span class="sxs-lookup"><span data-stu-id="bee07-161">**Length** returns the number of items in the object array.</span></span>  
  
```  
Function MakeList(ByVal items As Object()) As String  
   If items Is Nothing Then  
      Return Nothing  
   End If  
  
   Dim builder As System.Text.StringBuilder =   
      New System.Text.StringBuilder()  
   builder.Append("<ul>")  
  
   For Each item As Object In items  
      builder.Append("<li>")  
      builder.Append(item)  
   Next  
   builder.Append("</ul>")  
  
   Return builder.ToString()  
End Function  
  
Function Length(ByVal items as Object()) as Integer  
   If items is Nothing Then  
      Return 0  
   End If  
   Return items.Length  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="bee07-162">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bee07-162">Example</span></span>  
 <span data-ttu-id="bee07-163">Um den HTML-Code zu generieren, müssen Sie die Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bee07-163">To generate the HTML, you must call the function.</span></span> <span data-ttu-id="bee07-164">Fügen Sie den folgenden Ausdruck in die Value-Eigenschaft für das Textfeld ein, und legen Sie den Markuptyp für den Text auf HTML fest.</span><span class="sxs-lookup"><span data-stu-id="bee07-164">Paste the following expression in the Value property for the text box and set the markup type for text to HTML.</span></span> <span data-ttu-id="bee07-165">Weitere Informationen finden Sie unter [Hinzufügen von HTML in einem Bericht (Berichts-Generator und SSRS)](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bee07-165">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
```  
=Code.MakeList(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="bee07-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bee07-166">See Also</span></span>  
 <span data-ttu-id="bee07-167">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bee07-167">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bee07-168">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bee07-168">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bee07-169">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bee07-169">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bee07-170">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bee07-170">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
