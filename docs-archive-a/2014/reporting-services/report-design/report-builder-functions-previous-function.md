---
title: Previous-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3891deec3f152cdf46da77a7f2d11d38387c5c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617703"
---
# <a name="previous-function-report-builder-and-ssrs"></a><span data-ttu-id="0c4d8-102">Previous-Funktion (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0c4d8-102">Previous Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0c4d8-103">Gibt den Wert oder den angegebenen Aggregatwert für die vorherige Instanz eines Elements innerhalb des angegebenen Bereichs zurück.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-103">Returns the value or the specified aggregate value for the previous instance of an item within the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="0c4d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c4d8-104">Syntax</span></span>  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c4d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c4d8-105">Parameters</span></span>  
 <span data-ttu-id="0c4d8-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="0c4d8-106">*expression*</span></span>  
 <span data-ttu-id="0c4d8-107">(`Variant` oder `Binary`) Der Ausdruck, mit dem die Daten identifiziert werden und für den der vorherige Wert abgerufen wird. Beispiel: `Fields!Fieldname.Value` oder `Sum(Fields!Fieldname.Value)`.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-107">(`Variant` or `Binary`) The expression to use to identify the data and for which to retrieve the previous value, for example, `Fields!Fieldname.Value` or `Sum(Fields!Fieldname.Value)`.</span></span>  
  
 <span data-ttu-id="0c4d8-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="0c4d8-108">*scope*</span></span>  
 <span data-ttu-id="0c4d8-109">(`String`) optional.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-109">(`String`) Optional.</span></span> <span data-ttu-id="0c4d8-110">Der Name einer Gruppe oder eines Datenbereichs oder NULL ( `Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ), der den Bereich angibt, aus dem der von *Ausdruck*angegebene vorherige Wert abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-110">The name of a group or data region, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the scope from which to retrieve the previous value specified by *expression*.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="0c4d8-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="0c4d8-111">Return Type</span></span>  
 <span data-ttu-id="0c4d8-112">Gibt einen `Variant`- oder `Binary`-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-112">Returns a `Variant` or `Binary`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c4d8-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0c4d8-113">Remarks</span></span>  
 <span data-ttu-id="0c4d8-114">Die `Previous`-Funktion gibt den vorherigen Wert für den Ausdruck zurück, der in dem angegebenen Bereich ausgewertet wird, nachdem die Sortierfunktionen und Filter angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-114">The `Previous` function returns the previous value for the expression evaluated in the specified scope after all sorting and filtering have been applied.</span></span>  
  
 <span data-ttu-id="0c4d8-115">Wenn *Expression* kein Aggregat enthält, wird die `Previous` Funktion standardmäßig auf den aktuellen Bereich für das Berichts Element eingestellt.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-115">If *expression* does not contain an aggregate, the `Previous` function defaults to the current scope for the report item.</span></span>  
  
 <span data-ttu-id="0c4d8-116">Verwenden Sie in einer Detailgruppe `Previous`, um den Wert eines Feldverweises in der vorherigen Instanz der Detailzeile anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-116">In a details group, use `Previous` to specify the value of a field reference in the previous instance of the detail row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c4d8-117">Die- `Previous` Funktion unterstützt nur Feldverweise in der Detail Gruppe.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-117">The `Previous` function only supports field references in the details group.</span></span> <span data-ttu-id="0c4d8-118">Beispielsweise werden in einem Textfeld in der Detailgruppe durch `=Previous(Fields!Quantity.Value)` die Daten für das Feld `Quantity` aus der vorherigen Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-118">For example, in a text box in the details group, `=Previous(Fields!Quantity.Value)` returns the data for the field `Quantity` from the previous row.</span></span> <span data-ttu-id="0c4d8-119">In der ersten Zeile gibt dieser Ausdruck NULL zurück (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="0c4d8-119">In the first row, this expression returns a null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  
  
 <span data-ttu-id="0c4d8-120">Wenn *Expression* eine Aggregatfunktion enthält, die einen Standardbereich verwendet, `Previous` aggregiert die Daten innerhalb der vorherigen Instanz des im Aggregat Funktions aufrufsausdruck angegebenen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-120">If *expression* contains an aggregate function that uses a default scope, `Previous` aggregates the data within the previous instance of the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="0c4d8-121">Wenn *Expression* eine Aggregatfunktion enthält, die einen anderen als den Standardbereich angibt, muss der *Scope* -Parameter für die `Previous` Funktion ein enthaltender Bereich für den Bereich sein, der im Aggregat Funktions aufrufsausdruck angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-121">If *expression* contains an aggregate function that specifies a scope other than the default, the *scope* parameter for the `Previous` function must be a containing scope for the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="0c4d8-122">Die Funktionen `Level` , `InScope` `Aggregate` und `Previous` können nicht im *Expression*-Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-122">The functions `Level`, `InScope`, `Aggregate` and `Previous` cannot be used in the *expression*parameter.</span></span> <span data-ttu-id="0c4d8-123">Die Angabe des *recursive* -Parameters für eine Aggregatfunktion wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-123">Specifying the *recursive* parameter for any aggregate function is not supported.</span></span>  
  
 <span data-ttu-id="0c4d8-124">Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="0c4d8-124">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0c4d8-125">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0c4d8-125">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="0c4d8-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c4d8-126">Description</span></span>  
 <span data-ttu-id="0c4d8-127">Das folgende Codebeispiel stellt bei Angabe in der Standarddatenzeile eines Datenbereichs den Wert für das Feld `LineTotal` in der vorherigen Zeile bereit.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-127">The following code example, when placed in the default data row of a data region, provides the value for the field `LineTotal` in the previous row.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0c4d8-128">Code</span><span class="sxs-lookup"><span data-stu-id="0c4d8-128">Code</span></span>  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a><span data-ttu-id="0c4d8-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c4d8-129">Description</span></span>  
 <span data-ttu-id="0c4d8-130">Das folgende Codebeispiel zeigt einen Ausdruck, der die Summe der Umsätze an einem bestimmten Tag des Monats und den vorherigen Wert für den Tag des Monats in einem vorhergehenden Jahr berechnet.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-130">The following example shows an expression that calculates the sum of sales on a specific day of the month and the previous value for that day of the month in a previous year.</span></span> <span data-ttu-id="0c4d8-131">Der Ausdruck wird einer Zelle in einer Zeile, die zur untergeordneten Gruppe `GroupbyDay`gehört, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-131">The expression is added to a cell in a row that belongs to the child group `GroupbyDay`.</span></span> <span data-ttu-id="0c4d8-132">Die übergeordnete Gruppe ist `GroupbyMonth`, deren übergeordnete Gruppe wiederum `GroupbyYear`ist.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-132">Its parent group is `GroupbyMonth`, which has a parent group `GroupbyYear`.</span></span> <span data-ttu-id="0c4d8-133">Der Ausdruck zeigt die Ergebnisse für GroupbyDay (Standardbereich) und anschließend für `GroupbyYear` (der übergeordneten Gruppe der übergeordneten Gruppe `GroupbyMonth`) an.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-133">The expression displays the results for GroupbyDay (the default scope) and then for `GroupbyYear` (the parent of the parent group `GroupbyMonth`).</span></span>  
  
 <span data-ttu-id="0c4d8-134">Angenommen, in einem Datenbereich verfügt eine übergeordnete Gruppe namens `Year`über die untergeordnete Gruppe `Month`, der wiederum die Gruppe `Day` untergeordnet ist (drei geschachtelte Ebenen).</span><span class="sxs-lookup"><span data-stu-id="0c4d8-134">For example, for a data region with a parent group named `Year`, its child group named `Month`, and its child group named `Day` (3 nested levels).</span></span> <span data-ttu-id="0c4d8-135">Der Ausdruck `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in einer mit der Gruppe `Day` verknüpften Zeile gibt den Umsatzwert für denselben Tag und Monat des vorherigen Jahrs zurück.</span><span class="sxs-lookup"><span data-stu-id="0c4d8-135">The expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in a row associated with the group `Day` returns the sales value for the same day and month for the previous year.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0c4d8-136">Code</span><span class="sxs-lookup"><span data-stu-id="0c4d8-136">Code</span></span>  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c4d8-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c4d8-137">See Also</span></span>  
 <span data-ttu-id="0c4d8-138">[Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0c4d8-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0c4d8-139">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0c4d8-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0c4d8-140">[Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0c4d8-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0c4d8-141">Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4d8-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
