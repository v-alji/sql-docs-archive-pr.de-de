---
title: Last-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 123b78a0-d6c9-4f78-b0e7-73b21854a250
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c343e72e476d4a717ca551eedeb0f02650479ca4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617714"
---
# <a name="last-function-report-builder-and-ssrs"></a><span data-ttu-id="a444b-102">Last-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="a444b-102">Last Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a444b-103">Gibt den letzten Wert im festgelegten Bereich des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="a444b-103">Returns the last value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="a444b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a444b-104">Syntax</span></span>  
  
```  
  
Last(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a444b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a444b-105">Parameters</span></span>  
 <span data-ttu-id="a444b-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="a444b-106">*expression*</span></span>  
 <span data-ttu-id="a444b-107">(`Variant` oder `Binary`) Der Ausdruck, für den die Aggregation auszuführen ist. Beispiel: `=Fields!Fieldname.Value`.</span><span class="sxs-lookup"><span data-stu-id="a444b-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!Fieldname.Value`.</span></span>  
  
 <span data-ttu-id="a444b-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="a444b-108">*scope*</span></span>  
 <span data-ttu-id="a444b-109">(`String`) (optional) Der Name eines Datasets, eines Datenbereichs oder einer Gruppe mit den Berichtselementen, auf die die Funktion anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="a444b-109">(`String`) (Optional) The name of a dataset, data region, or group that contains the report items to which to apply the function.</span></span> <span data-ttu-id="a444b-110">Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="a444b-110">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="a444b-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="a444b-111">Return Type</span></span>  
 <span data-ttu-id="a444b-112">Wird durch den Typ des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a444b-112">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a444b-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a444b-113">Remarks</span></span>  
 <span data-ttu-id="a444b-114">Die `Last`-Funktion gibt den letzten Wert in einem Satz von Daten zurück, nachdem alle Sortierfunktionen und Filter im angegebenen Bereich angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a444b-114">The `Last` function returns the final value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="a444b-115">Die `Last`-Funktion kann nur in Gruppenfilterausdrücken mit dem aktuellen (Standard-) Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a444b-115">The `Last` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="a444b-116">Sie können die `Last`-Funktion auch in einem Seitenkopf verwenden, um den letzten Wert der `ReportItems`-Auflistung für eine Seite zurückzugeben und Überschriften im Wörterbuchformat zu erstellen, die den ersten und den letzten Eintrag auf einer Seite anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a444b-116">You can also use `Last` in a page header to return the last value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="a444b-117">Der Wert des *scope* -Objekts muss eine Zeichenfolgenkonstante sein und darf kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="a444b-117">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="a444b-118">Für äußere Aggregate oder Aggregate, die keine anderen Aggregate angeben, muss das *scope* -Objekt auf den aktuellen Bereich oder einen enthaltenen Bereich verweisen.</span><span class="sxs-lookup"><span data-stu-id="a444b-118">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="a444b-119">Bei Aggregaten von Aggregaten können geschachtelte Aggregate einen untergeordneten Bereich angeben.</span><span class="sxs-lookup"><span data-stu-id="a444b-119">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="a444b-120">Das*Expression* -Objekt kann Aufrufe von geschachtelten Aggregatfunktionen enthalten. Dabei gelten folgende Ausnahmen und Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="a444b-120">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="a444b-121">Das*Scope* -Objekt für geschachtelte Aggregate muss dem Bereich des äußeren Aggregats entsprechen oder darin enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="a444b-121">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="a444b-122">In allen eindeutigen Bereichen des Ausdrucks muss ein Bereich eine untergeordnete Beziehung zu allen anderen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="a444b-122">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="a444b-123">Das*Scope* -Objekt für geschachtelte Aggregate darf nicht der Name eines Datasets sein.</span><span class="sxs-lookup"><span data-stu-id="a444b-123">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="a444b-124">Der *Ausdruck* darf keine-,-,- `First` oder-Funktionen enthalten `Last` `Previous` `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="a444b-124">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="a444b-125">Das*Expression* -Objekt darf keine geschachtelten Aggregate enthalten, die ein *recursive*-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="a444b-125">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="a444b-126">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a444b-126">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="a444b-127">Weitere Informationen zu rekursiven Aggregaten finden Sie unter [Creating Recursive Hierarchy Groups (Report Builder and SSRS) (Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS))](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a444b-127">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a444b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a444b-128">Example</span></span>  
 <span data-ttu-id="a444b-129">Das folgende Codebeispiel gibt die letzte Produktnummer in der `Category` -Gruppe eines Datenbereichs zurück.</span><span class="sxs-lookup"><span data-stu-id="a444b-129">The following code example returns the last product number in the `Category` group of a data region.</span></span>  
  
```  
=Last(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="a444b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a444b-130">See Also</span></span>  
 <span data-ttu-id="a444b-131">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a444b-131">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a444b-132">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a444b-132">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a444b-133">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a444b-133">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a444b-134">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a444b-134">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
