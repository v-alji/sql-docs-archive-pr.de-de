---
title: First-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0914520-30c5-4d63-9b59-8d9342ed63b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cd8578a1d9a17030d603457d4eaadf107316bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617717"
---
# <a name="first-function-report-builder-and-ssrs"></a><span data-ttu-id="07d1e-102">First-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="07d1e-102">First Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="07d1e-103">Gibt den ersten Wert im festgelegten Bereich des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="07d1e-103">Returns the first value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="07d1e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07d1e-104">Syntax</span></span>  
  
```  
  
First(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07d1e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07d1e-105">Parameters</span></span>  
 <span data-ttu-id="07d1e-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="07d1e-106">*expression*</span></span>  
 <span data-ttu-id="07d1e-107">(`Variant` oder `Binary`) Der Ausdruck, für den die Aggregation auszuführen ist. Beispiel: `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="07d1e-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="07d1e-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="07d1e-108">*scope*</span></span>  
 <span data-ttu-id="07d1e-109">(`String`) optional.</span><span class="sxs-lookup"><span data-stu-id="07d1e-109">(`String`) Optional.</span></span> <span data-ttu-id="07d1e-110">Der Name eines Datasets, einer Gruppe oder eines Datenbereichs mit den Berichtselementen, auf die die Aggregatfunktion anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="07d1e-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="07d1e-111">Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="07d1e-111">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="07d1e-112">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="07d1e-112">Return Type</span></span>  
 <span data-ttu-id="07d1e-113">Wird durch den Typ des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="07d1e-113">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07d1e-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="07d1e-114">Remarks</span></span>  
 <span data-ttu-id="07d1e-115">Die `First`-Funktion gibt den ersten Wert in einem Satz von Daten zurück, nachdem alle Sortierfunktionen und Filter im angegebenen Bereich angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="07d1e-115">The `First` function returns the first value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="07d1e-116">Die `First`-Funktion kann nur in Gruppenfilterausdrücken mit dem aktuellen (Standard-) Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07d1e-116">The `First` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="07d1e-117">Sie können die `First`-Funktion auch in einem Seitenkopf verwenden, um den ersten Wert der `ReportItems`-Auflistung für eine Seite zurückzugeben und Überschriften im Wörterbuchformat zu erstellen, die den ersten und den letzten Eintrag auf einer Seite anzeigen.</span><span class="sxs-lookup"><span data-stu-id="07d1e-117">You can also use `First` in a page header to return the first value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="07d1e-118">Der Wert des *scope* -Objekts muss eine Zeichenfolgenkonstante sein und darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="07d1e-118">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="07d1e-119">Für äußere Aggregate oder Aggregate, die keine anderen Aggregate angeben, muss das *scope* -Objekt auf den aktuellen Bereich oder einen enthaltenen Bereich verweisen.</span><span class="sxs-lookup"><span data-stu-id="07d1e-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="07d1e-120">Bei Aggregaten von Aggregaten können geschachtelte Aggregate einen untergeordneten Bereich angeben.</span><span class="sxs-lookup"><span data-stu-id="07d1e-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="07d1e-121">Das*Expression* -Objekt kann Aufrufe von geschachtelten Aggregatfunktionen enthalten. Dabei gelten folgende Ausnahmen und Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="07d1e-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="07d1e-122">Das*Scope* -Objekt für geschachtelte Aggregate muss dem Bereich des äußeren Aggregats entsprechen oder darin enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="07d1e-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="07d1e-123">In allen eindeutigen Bereichen des Ausdrucks muss ein Bereich eine untergeordnete Beziehung zu allen anderen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="07d1e-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="07d1e-124">Das*Scope* -Objekt für geschachtelte Aggregate darf nicht der Name eines Datasets sein.</span><span class="sxs-lookup"><span data-stu-id="07d1e-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="07d1e-125">Der *Ausdruck* darf keine-,-,- `First` oder-Funktionen enthalten `Last` `Previous` `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="07d1e-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="07d1e-126">Das*Expression* -Objekt darf keine geschachtelten Aggregate enthalten, die ein *recursive*-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="07d1e-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="07d1e-127">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="07d1e-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="07d1e-128">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07d1e-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07d1e-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d1e-129">Example</span></span>  
 <span data-ttu-id="07d1e-130">Das folgende Codebeispiel gibt die erste Produktnummer in der `Category` -Gruppe eines Datenbereichs zurück:</span><span class="sxs-lookup"><span data-stu-id="07d1e-130">The following code example returns the first product number in the `Category` group of a data region:</span></span>  
  
```  
=First(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="07d1e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07d1e-131">See Also</span></span>  
 <span data-ttu-id="07d1e-132">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d1e-132">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07d1e-133">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d1e-133">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07d1e-134">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d1e-134">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="07d1e-135">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="07d1e-135">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
