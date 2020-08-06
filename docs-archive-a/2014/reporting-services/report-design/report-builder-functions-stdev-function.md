---
title: StDev-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cb51e96e-a828-42f0-b67c-cee3f4d221e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 58f913501c708b10ca01c24dd591d3378584afa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617694"
---
# <a name="stdev-function-report-builder-and-ssrs"></a><span data-ttu-id="37b23-102">StDev-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="37b23-102">StDev Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="37b23-103">Gibt die Standardabweichung aller numerischen Werte ungleich NULL aus dem angegebenen Ausdruck im Kontext des angegebenen Bereichs ausgewertet zurück.</span><span class="sxs-lookup"><span data-stu-id="37b23-103">Returns the standard deviation of all non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="37b23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37b23-104">Syntax</span></span>  
  
```  
  
StDev(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37b23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37b23-105">Parameters</span></span>  
 <span data-ttu-id="37b23-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="37b23-106">*expression*</span></span>  
 <span data-ttu-id="37b23-107">(`Integer` oder `Float`) Der Ausdruck, für den die Aggregation ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="37b23-107">(`Integer` or `Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="37b23-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="37b23-108">*scope*</span></span>  
 <span data-ttu-id="37b23-109">(`String`) optional.</span><span class="sxs-lookup"><span data-stu-id="37b23-109">(`String`) Optional.</span></span> <span data-ttu-id="37b23-110">Der Name eines Datasets, einer Gruppe oder eines Datenbereichs mit den Berichtselementen, auf die die Aggregatfunktion anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="37b23-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="37b23-111">Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="37b23-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="37b23-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="37b23-112">*recursive*</span></span>  
 <span data-ttu-id="37b23-113">(**Enumerationstyp**) Optional.</span><span class="sxs-lookup"><span data-stu-id="37b23-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="37b23-114">`Simple` (Standardwert) oder `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="37b23-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="37b23-115">Gibt an, ob die Aggregation rekursiv auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="37b23-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="37b23-116">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="37b23-116">Return Type</span></span>  
 <span data-ttu-id="37b23-117">Gibt für Dezimalausdrücke einen Wert vom Typ `Decimal` und für alle anderen Ausdrücke einen Wert vom Typ `Double` zurück.</span><span class="sxs-lookup"><span data-stu-id="37b23-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b23-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="37b23-118">Remarks</span></span>  
 <span data-ttu-id="37b23-119">Die im Ausdruck angegebene Gruppe von Daten muss über den gleichen Datentyp verfügen.</span><span class="sxs-lookup"><span data-stu-id="37b23-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="37b23-120">Um Daten mit mehreren numerischen Datentypen in den gleichen Datentyp zu konvertieren, verwenden Sie Konvertierungsfunktionen wie `CInt`, `CDbl` oder `CDec`.</span><span class="sxs-lookup"><span data-stu-id="37b23-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="37b23-121">Weitere Informationen finden Sie unter [Funktionen für die Typkonvertierung](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="37b23-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="37b23-122">Der Wert des *scope* -Objekts muss eine Zeichenfolgenkonstante sein und darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="37b23-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="37b23-123">Für äußere Aggregate oder Aggregate, die keine anderen Aggregate angeben, muss das *scope* -Objekt auf den aktuellen Bereich oder einen enthaltenen Bereich verweisen.</span><span class="sxs-lookup"><span data-stu-id="37b23-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="37b23-124">Bei Aggregaten von Aggregaten können geschachtelte Aggregate einen untergeordneten Bereich angeben.</span><span class="sxs-lookup"><span data-stu-id="37b23-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="37b23-125">Das*Expression* -Objekt kann Aufrufe von geschachtelten Aggregatfunktionen enthalten. Dabei gelten folgende Ausnahmen und Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="37b23-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="37b23-126">Das*Scope* -Objekt für geschachtelte Aggregate muss dem Bereich des äußeren Aggregats entsprechen oder darin enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="37b23-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="37b23-127">In allen eindeutigen Bereichen des Ausdrucks muss ein Bereich eine untergeordnete Beziehung zu allen anderen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="37b23-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="37b23-128">Das*Scope* -Objekt für geschachtelte Aggregate darf nicht der Name eines Datasets sein.</span><span class="sxs-lookup"><span data-stu-id="37b23-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="37b23-129">Der *Ausdruck* darf keine-,-,- `First` oder-Funktionen enthalten `Last` `Previous` `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="37b23-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="37b23-130">Das*Expression* -Objekt darf keine geschachtelten Aggregate enthalten, die ein *recursive*-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="37b23-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="37b23-131">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="37b23-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="37b23-132">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="37b23-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37b23-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37b23-133">Example</span></span>  
 <span data-ttu-id="37b23-134">Das folgende Codebeispiel stellt die Standardabweichung der Einzelpostensummen in der Gruppierung bzw. dem Datenbereich `Order` bereit.</span><span class="sxs-lookup"><span data-stu-id="37b23-134">The following code example provides the standard deviation of line item totals in the `Order` group or data region.</span></span>  
  
```  
=StDev(Fields!LineTotal.Value, "Order")  
```  
  
## <a name="see-also"></a><span data-ttu-id="37b23-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37b23-135">See Also</span></span>  
 <span data-ttu-id="37b23-136">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="37b23-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="37b23-137">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="37b23-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="37b23-138">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="37b23-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="37b23-139">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="37b23-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
