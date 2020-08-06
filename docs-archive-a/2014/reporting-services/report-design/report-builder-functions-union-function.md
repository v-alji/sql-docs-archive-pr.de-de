---
title: Union-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c87e16fe-c12a-4c9d-a9df-7a94e229fd04
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c80926be53254ec512b2189c4b67e8cd5885733f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617690"
---
# <a name="union-function-report-builder-and-ssrs"></a><span data-ttu-id="3fce7-102">Union-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="3fce7-102">Union Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3fce7-103">Gibt die Vereinigung aller numerischen Werte ungleich NULL aus dem angegebenen Ausdruck im Kontext des festgelegten Bereichs ausgewertet zurück.</span><span class="sxs-lookup"><span data-stu-id="3fce7-103">Returns the union of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="3fce7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fce7-104">Syntax</span></span>  
  
```  
  
Union(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fce7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fce7-105">Parameters</span></span>  
 <span data-ttu-id="3fce7-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="3fce7-106">*expression*</span></span>  
 <span data-ttu-id="3fce7-107">(`SqlGeometry` oder `SqlGeography`) Der Ausdruck, für den die Aggregation ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fce7-107">(`SqlGeometry` or `SqlGeography`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="3fce7-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="3fce7-108">*scope*</span></span>  
 <span data-ttu-id="3fce7-109">(`String`) optional.</span><span class="sxs-lookup"><span data-stu-id="3fce7-109">(`String`) Optional.</span></span> <span data-ttu-id="3fce7-110">Der Name eines Datasets, einer Gruppe oder eines Datenbereichs mit den Berichtselementen, auf die die Aggregatfunktion anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="3fce7-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="3fce7-111">Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fce7-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="3fce7-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="3fce7-112">*recursive*</span></span>  
 <span data-ttu-id="3fce7-113">(**Enumerationstyp**) Optional.</span><span class="sxs-lookup"><span data-stu-id="3fce7-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="3fce7-114">`Simple` (Standardwert) oder `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="3fce7-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="3fce7-115">Gibt an, ob die Aggregation rekursiv auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="3fce7-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return"></a><span data-ttu-id="3fce7-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3fce7-116">Return</span></span>  
 <span data-ttu-id="3fce7-117">Gibt ein räumliches Objekt zurück. Dies ist je nach Ausdruckstyp vom Typ `SqlGeometry` oder `SqlGeography`.</span><span class="sxs-lookup"><span data-stu-id="3fce7-117">Returns a spatial object, either `SqlGeometry` or `SqlGeography`, based on the expression type.</span></span> <span data-ttu-id="3fce7-118">Weitere Informationen zu `SqlGeometry` und `SqlGeography` räumlichen Datentypen finden Sie unter [Übersicht über räumliche Datentypen](../../relational-databases/spatial/spatial-data-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3fce7-118">For more information about `SqlGeometry` and `SqlGeography` spatial data types, see [Spatial Data Types Overview](../../relational-databases/spatial/spatial-data-types-overview.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fce7-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3fce7-119">Remarks</span></span>  
 <span data-ttu-id="3fce7-120">Die im Ausdruck angegebene Gruppe von Daten muss über den gleichen Datentyp verfügen.</span><span class="sxs-lookup"><span data-stu-id="3fce7-120">The set of data specified in the expression must have the same data type.</span></span>  
  
 <span data-ttu-id="3fce7-121">Der Wert des *scope* -Objekts muss eine Zeichenfolgenkonstante sein und darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="3fce7-121">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="3fce7-122">Für äußere Aggregate oder Aggregate, die keine anderen Aggregate angeben, muss das *scope* -Objekt auf den aktuellen Bereich oder einen enthaltenen Bereich verweisen.</span><span class="sxs-lookup"><span data-stu-id="3fce7-122">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="3fce7-123">Datasetbereiche werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3fce7-123">Dataset scopes are not supported.</span></span> <span data-ttu-id="3fce7-124">Bei Aggregaten von Aggregaten können geschachtelte Aggregate einen untergeordneten Bereich angeben.</span><span class="sxs-lookup"><span data-stu-id="3fce7-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="3fce7-125">Das*Expression* -Objekt kann Aufrufe von geschachtelten Aggregatfunktionen enthalten. Dabei gelten folgende Ausnahmen und Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="3fce7-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="3fce7-126">Das*Scope* -Objekt für geschachtelte Aggregate muss dem Bereich des äußeren Aggregats entsprechen oder darin enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="3fce7-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="3fce7-127">In allen eindeutigen Bereichen des Ausdrucks muss ein Bereich eine untergeordnete Beziehung zu allen anderen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="3fce7-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="3fce7-128">Das*Scope* -Objekt für geschachtelte Aggregate darf nicht der Name eines Datasets sein.</span><span class="sxs-lookup"><span data-stu-id="3fce7-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="3fce7-129">Der *Ausdruck* darf keine-,-,- `First` oder-Funktionen enthalten `Last` `Previous` `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="3fce7-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="3fce7-130">Das*Expression* -Objekt darf keine geschachtelten Aggregate enthalten, die ein *recursive*-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="3fce7-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="3fce7-131">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="3fce7-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="3fce7-132">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3fce7-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fce7-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fce7-133">Example</span></span>  
 <span data-ttu-id="3fce7-134">In der folgenden Tabelle werden Beispiele für `SqlGeometry`-Ausdrücke und `Union`-Ergebnisausdrücke im WKT-Format (Well Known Text) für räumliche Daten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fce7-134">The following table shows examples of `SqlGeometry` expressions and `Union` result expression, shown in WKT (Well Known Text) format for spatial data.</span></span>  
  
|<span data-ttu-id="3fce7-135">Feld mit räumlichen Daten</span><span class="sxs-lookup"><span data-stu-id="3fce7-135">Field with spatial data</span></span>|<span data-ttu-id="3fce7-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fce7-136">Example</span></span>|<span data-ttu-id="3fce7-137">Union-Ergebnis</span><span class="sxs-lookup"><span data-stu-id="3fce7-137">Union result</span></span>|  
|-----------------------------|-------------|------------------|  
|<span data-ttu-id="3fce7-138">[PointLocation]</span><span class="sxs-lookup"><span data-stu-id="3fce7-138">[PointLocation]</span></span>|<span data-ttu-id="3fce7-139">POINT(1 2)</span><span class="sxs-lookup"><span data-stu-id="3fce7-139">POINT(1 2)</span></span><br /><br /> <span data-ttu-id="3fce7-140">POINT(3 4)</span><span class="sxs-lookup"><span data-stu-id="3fce7-140">POINT(3 4)</span></span>|<span data-ttu-id="3fce7-141">MULTIPOINT((1 2), (3 4))</span><span class="sxs-lookup"><span data-stu-id="3fce7-141">MULTIPOINT((1 2), (3 4))</span></span>|  
|<span data-ttu-id="3fce7-142">[PathDefinition]</span><span class="sxs-lookup"><span data-stu-id="3fce7-142">[PathDefinition]</span></span>|<span data-ttu-id="3fce7-143">LINESTRING(1 2, 3 4)</span><span class="sxs-lookup"><span data-stu-id="3fce7-143">LINESTRING(1 2, 3 4)</span></span><br /><br /> <span data-ttu-id="3fce7-144">LINESTRING(5 6, 7 8)</span><span class="sxs-lookup"><span data-stu-id="3fce7-144">LINESTRING(5 6, 7 8)</span></span>|<span data-ttu-id="3fce7-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span><span class="sxs-lookup"><span data-stu-id="3fce7-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span></span>|  
|<span data-ttu-id="3fce7-146">[PolygonDefinition]</span><span class="sxs-lookup"><span data-stu-id="3fce7-146">[PolygonDefinition]</span></span>|<span data-ttu-id="3fce7-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span><span class="sxs-lookup"><span data-stu-id="3fce7-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span></span><br /><br /> <span data-ttu-id="3fce7-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span><span class="sxs-lookup"><span data-stu-id="3fce7-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span></span>|<span data-ttu-id="3fce7-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span><span class="sxs-lookup"><span data-stu-id="3fce7-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span></span>|  
  
```  
=Union(Fields!PointLocation.Value)  
=Union(Fields!PathDefinition.Value)  
=Union(Fields!PolygonDefinition.Value, "Group1")  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fce7-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fce7-150">See Also</span></span>  
 <span data-ttu-id="3fce7-151">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3fce7-151">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3fce7-152">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3fce7-152">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3fce7-153">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3fce7-153">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3fce7-154">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3fce7-154">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
