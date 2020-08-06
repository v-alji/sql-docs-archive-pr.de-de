---
title: RunningValue-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6bee2f15-0e69-49c8-9689-b04544063b1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 168073a0409455041f4ebe3aa4c5dcfc8fa129a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617695"
---
# <a name="runningvalue-function-report-builder-and-ssrs"></a><span data-ttu-id="7f9f6-102">RunningValue-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="7f9f6-102">RunningValue Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7f9f6-103">Gibt ein laufendes Aggregat aller numerischen Werte ungleich NULL aus dem angegebenen Ausdruck für den Kontext des angegebenen Bereichs ausgewertet zurück.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-103">Returns a running aggregate of all non-null numeric values specified by the expression, evaluated for the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="7f9f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f9f6-104">Syntax</span></span>  
  
```  
  
RunningValue(expression, function, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f9f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f9f6-105">Parameters</span></span>  
 <span data-ttu-id="7f9f6-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="7f9f6-106">*expression*</span></span>  
 <span data-ttu-id="7f9f6-107">Der Ausdruck, für den die Aggregation auszuführen ist, z.B. `[Quantity]`.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-107">The expression on which to perform the aggregation, for example, `[Quantity]`.</span></span>  
  
 <span data-ttu-id="7f9f6-108">*Funktion*</span><span class="sxs-lookup"><span data-stu-id="7f9f6-108">*function*</span></span>  
 <span data-ttu-id="7f9f6-109">(`Enum`) Der Name der Aggregatfunktion, die auf den Ausdruck angewendet werden soll. Beispiel: `Sum`.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-109">(`Enum`) The name of the aggregate function to apply to the expression, for example, `Sum`.</span></span> <span data-ttu-id="7f9f6-110">Diese Funktion kann nicht `RunningValue`, `RowNumber` oder `Aggregate` sein.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-110">This function cannot be `RunningValue`, `RowNumber`, or `Aggregate`.</span></span>  
  
 <span data-ttu-id="7f9f6-111">*scope*</span><span class="sxs-lookup"><span data-stu-id="7f9f6-111">*scope*</span></span>  
 <span data-ttu-id="7f9f6-112">(`String`) Eine Zeichenfolgenkonstante als Name eines Datasets, eines Datenbereichs oder einer Gruppe oder NULL (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), der den Kontext angibt, in dem die Aggregation ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-112">(`String`) A string constant that is the name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the aggregation.</span></span> <span data-ttu-id="7f9f6-113">Durch `Nothing` wird der äußerste Kontext angegeben, normalerweise das Berichtsdataset.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-113">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="7f9f6-114">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="7f9f6-114">Return Type</span></span>  
 <span data-ttu-id="7f9f6-115">Wird durch die im *function* -Parameter angegebene Aggregatfunktion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-115">Determined by the aggregate function that is specified in the *function* parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f9f6-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7f9f6-116">Remarks</span></span>  
 <span data-ttu-id="7f9f6-117">Der Wert für `RunningValue` wird für jede neue Instanz des Bereichs auf 0 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-117">The value for `RunningValue` resets to 0 for each new instance of the scope.</span></span> <span data-ttu-id="7f9f6-118">Wenn eine Gruppe angegeben wird, wird der laufende Wert zurückgesetzt, wenn sich der Gruppenausdruck ändert.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-118">If a group is specified, the running value is reset when the group expression changes.</span></span> <span data-ttu-id="7f9f6-119">Wenn ein Datenbereich angegeben wird, wird der laufende Wert für jede neue Instanz des Datenbereichs zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-119">If a data region is specified, the running value is reset for each new instance of the data region.</span></span> <span data-ttu-id="7f9f6-120">Wenn ein Dataset angegeben wird, wird der laufende Wert für das gesamte Dataset nicht zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-120">If a dataset is specified, the running value is not reset throughout the entire dataset.</span></span>  
  
 <span data-ttu-id="7f9f6-121">`RunningValue` darf nicht in einem Filter- oder Sortierausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-121">`RunningValue` cannot be used in a filter or sort expression.</span></span>  
  
 <span data-ttu-id="7f9f6-122">Der Datensatz, für den der ausgeführte Wert berechnet wird, muss den gleichen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-122">The set of data for which the running value is calculated must have the same data type.</span></span> <span data-ttu-id="7f9f6-123">Um Daten mit mehreren numerischen Datentypen in den gleichen Datentyp zu konvertieren, verwenden Sie Konvertierungsfunktionen wie `CInt`, `CDbl` oder `CDec`.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-123">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="7f9f6-124">Weitere Informationen finden Sie unter [Funktionen für die Typkonvertierung](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="7f9f6-124">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="7f9f6-125">*Scope* darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-125">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="7f9f6-126">Das*Expression* -Objekt kann Aufrufe von geschachtelten Aggregatfunktionen enthalten. Dabei gelten folgende Ausnahmen und Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="7f9f6-126">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="7f9f6-127">Der Bereich für geschachtelte Aggregate muss dem Bereich des äußeren Aggregats entsprechen oder darin enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-127">Scope for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="7f9f6-128">In allen eindeutigen Bereichen des Ausdrucks muss ein Bereich eine untergeordnete Beziehung zu allen anderen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-128">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="7f9f6-129">Der Bereich für geschachtelte Aggregate darf nicht der Name eines Datasets sein.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-129">Scope for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="7f9f6-130">Der *Ausdruck* darf keine-,-,- `First` oder-Funktionen enthalten `Last` `Previous` `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="7f9f6-130">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="7f9f6-131">Das*Expression* -Objekt darf keine geschachtelten Aggregate enthalten, die ein *recursive*-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-131">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="7f9f6-132">Verwenden Sie `RowNumber` zur Berechnung des laufenden Werts für die Zeilenanzahl.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-132">To calculate the running value of the number of rows, use `RowNumber`.</span></span> <span data-ttu-id="7f9f6-133">Weitere Informationen finden Sie unter [RowNumber-Funktion (Berichts-Generator und SSRS)](report-builder-functions-rownumber-function.md).</span><span class="sxs-lookup"><span data-stu-id="7f9f6-133">For more information, see [RowNumber Function &#40;Report Builder and SSRS&#41;](report-builder-functions-rownumber-function.md).</span></span>  
  
 <span data-ttu-id="7f9f6-134">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="7f9f6-134">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="7f9f6-135">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7f9f6-135">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7f9f6-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7f9f6-136">Examples</span></span>  
 <span data-ttu-id="7f9f6-137">Das folgende Codebeispiel generiert eine laufende Summe für das Feld mit dem Namen `Cost` im äußersten Bereich, den das Dataset darstellt.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-137">The following code example provides a running sum of the field named `Cost` in the outermost scope, which is the dataset.</span></span>  
  
```  
=RunningValue(Fields!Cost.Value, Sum, Nothing)  
```  
  
 <span data-ttu-id="7f9f6-138">Das folgende Codebeispiel generiert eine laufende Summe für das Feld mit dem Namen `Score` im Dataset mit dem Namen `DataSet1`.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-138">The following code example provides a running sum of the field named `Score` in the dataset named `DataSet1`.</span></span>  
  
```  
=RunningValue(Fields!Score.Value,sum,"DataSet1")  
```  
  
 <span data-ttu-id="7f9f6-139">Das folgende Codebeispiel generiert eine laufende Summe für das Feld mit dem Namen `Traffic Charges` im äußersten Bereich.</span><span class="sxs-lookup"><span data-stu-id="7f9f6-139">The following code example provides a running sum of the field named `Traffic Charges` in the outermost scope.</span></span>  
  
```  
=RunningValue(Fields!Traffic Charges.Value, Sum, Nothing)  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f9f6-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f9f6-140">See Also</span></span>  
 <span data-ttu-id="7f9f6-141">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f9f6-141">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7f9f6-142">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f9f6-142">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7f9f6-143">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f9f6-143">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7f9f6-144">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f9f6-144">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
