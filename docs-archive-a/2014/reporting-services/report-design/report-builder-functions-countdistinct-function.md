---
title: CountDistinct-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 902c251e-e1e8-41d2-ac20-5bb6138ac410
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62fab53d4f26a874ac40e0a915c4242a41c72ce0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617726"
---
# <a name="countdistinct-function-report-builder-and-ssrs"></a><span data-ttu-id="e66cf-102">CountDistinct-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e66cf-102">CountDistinct Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e66cf-103">Gibt die Anzahl aller unterschiedlichen Werte ungleich NULL aus dem angegebenen Ausdruck im Kontext des angegebenen Bereichs ausgewertet zurück.</span><span class="sxs-lookup"><span data-stu-id="e66cf-103">Returns a count of all distinct non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="e66cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e66cf-104">Syntax</span></span>  
  
```  
  
CountDistinct(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e66cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e66cf-105">Parameters</span></span>  
 <span data-ttu-id="e66cf-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="e66cf-106">*expression*</span></span>  
 <span data-ttu-id="e66cf-107">(`Variant`) Der Ausdruck, für den die Aggregation auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="e66cf-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="e66cf-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="e66cf-108">*scope*</span></span>  
 <span data-ttu-id="e66cf-109">(`String`) optional.</span><span class="sxs-lookup"><span data-stu-id="e66cf-109">(`String`) Optional.</span></span> <span data-ttu-id="e66cf-110">Der Name eines Datasets, einer Gruppe oder eines Datenbereichs mit den Berichtselementen, auf die die Aggregatfunktion anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="e66cf-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="e66cf-111">Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="e66cf-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="e66cf-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="e66cf-112">*recursive*</span></span>  
 <span data-ttu-id="e66cf-113">(**Enumerationstyp**) Optional.</span><span class="sxs-lookup"><span data-stu-id="e66cf-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="e66cf-114">`Simple` (Standardwert) oder `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="e66cf-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="e66cf-115">Gibt an, ob die Aggregation rekursiv auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="e66cf-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="e66cf-116">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="e66cf-116">Return Type</span></span>  
 <span data-ttu-id="e66cf-117">Gibt einen `Integer` zurück.</span><span class="sxs-lookup"><span data-stu-id="e66cf-117">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e66cf-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e66cf-118">Remarks</span></span>  
 <span data-ttu-id="e66cf-119">Der Wert des *scope* -Objekts muss eine Zeichenfolgenkonstante sein und darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="e66cf-119">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="e66cf-120">Für äußere Aggregate oder Aggregate, die keine anderen Aggregate angeben, muss das *scope* -Objekt auf den aktuellen Bereich oder einen enthaltenen Bereich verweisen.</span><span class="sxs-lookup"><span data-stu-id="e66cf-120">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="e66cf-121">Bei Aggregaten von Aggregaten können geschachtelte Aggregate einen untergeordneten Bereich angeben.</span><span class="sxs-lookup"><span data-stu-id="e66cf-121">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="e66cf-122">Das*Expression* -Objekt kann Aufrufe von geschachtelten Aggregatfunktionen enthalten. Dabei gelten folgende Ausnahmen und Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="e66cf-122">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="e66cf-123">Das*Scope* -Objekt für geschachtelte Aggregate muss dem Bereich des äußeren Aggregats entsprechen oder darin enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="e66cf-123">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="e66cf-124">In allen eindeutigen Bereichen des Ausdrucks muss ein Bereich eine untergeordnete Beziehung zu allen anderen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="e66cf-124">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="e66cf-125">Das*Scope* -Objekt für geschachtelte Aggregate darf nicht der Name eines Datasets sein.</span><span class="sxs-lookup"><span data-stu-id="e66cf-125">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="e66cf-126">Der *Ausdruck* darf keine-,-,- `First` oder-Funktionen enthalten `Last` `Previous` `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="e66cf-126">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="e66cf-127">Das*Expression* -Objekt darf keine geschachtelten Aggregate enthalten, die ein *recursive*-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="e66cf-127">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="e66cf-128">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="e66cf-128">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="e66cf-129">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e66cf-129">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e66cf-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e66cf-130">Example</span></span>  
 <span data-ttu-id="e66cf-131">Das folgende Codebeispiel zeigt einen Ausdruck, der die Anzahl eindeutiger Wert ungleich NULL von `Size` für den Standardbereich oder für einen übergeordneten Gruppenbereich berechnet.</span><span class="sxs-lookup"><span data-stu-id="e66cf-131">The following code example shows an expression that calculates the number of unique non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="e66cf-132">Der Ausdruck wird einer Zelle in einer Zeile, die zur untergeordneten Gruppe `GroupbySubcategory`gehört, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e66cf-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="e66cf-133">Die übergeordnete Gruppe ist `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="e66cf-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="e66cf-134">Der Ausdruck zeigt die Ergebnisse für `GroupbySubcategory` (Standardbereich) und anschließend für `GroupbyCategory` (übergeordneter Gruppenbereich) an.</span><span class="sxs-lookup"><span data-stu-id="e66cf-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e66cf-135">Ausdrücke sollten keine tatsächlichen Wagenrückläufe und Zeilenumbrüche enthalten; diese sind im Beispielcode enthalten, um Dokumentationsrenderer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e66cf-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example code to support documentation renderers.</span></span> <span data-ttu-id="e66cf-136">Wenn Sie das folgende Beispiel kopieren, entfernen Sie Wagenrückläufe aus jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="e66cf-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
```  
="Distinct count (Subcategory): " & CountDistinct(Fields!Size.Value) &   
"Distinct count (Category): " & CountDistinct(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="e66cf-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e66cf-137">See Also</span></span>  
 <span data-ttu-id="e66cf-138">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66cf-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66cf-139">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66cf-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66cf-140">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66cf-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e66cf-141">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e66cf-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
