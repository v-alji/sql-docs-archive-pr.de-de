---
title: Modell Filter Syntax und Beispiele (Analysis Services-Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696330"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a><span data-ttu-id="76bd6-102">Modellfiltersyntax und Beispiele (Analysis Services - Data Mining)</span><span class="sxs-lookup"><span data-stu-id="76bd6-102">Model Filter Syntax and Examples (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="76bd6-103">Dieser Abschnitt enthält ausführliche Informationen zur Syntax von Modellfiltern sowie Beispielausdrücke.</span><span class="sxs-lookup"><span data-stu-id="76bd6-103">This section provides detailed information about the syntax for model filters, together with sample expressions.</span></span>  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a><span data-ttu-id="76bd6-104">Filter Syntax</span><span class="sxs-lookup"><span data-stu-id="76bd6-104">Filter Syntax</span></span>  
 <span data-ttu-id="76bd6-105">Filterausdrücke entsprechen im Allgemeinen dem Inhalt einer WHERE-Klausel.</span><span class="sxs-lookup"><span data-stu-id="76bd6-105">Filter expressions generally are equivalent to the content of a WHERE clause.</span></span> <span data-ttu-id="76bd6-106">Sie können mehrere Bedingungen mithilfe der logischen Operatoren `AND`, `OR` und `NOT` verbinden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-106">You can connect multiple conditions by using the logical operators `AND`, `OR`, and `NOT`.</span></span>  
  
 <span data-ttu-id="76bd6-107">In geschachtelten Tabellen können Sie auch die Operatoren `EXISTS` und `NOT EXISTS` verwenden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-107">In nested tables, you can also use the `EXISTS` and `NOT EXISTS` operators.</span></span> <span data-ttu-id="76bd6-108">Eine `EXISTS`-Bedingung ergibt `true`, wenn die Unterabfrage mindestens eine Zeile zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-108">An `EXISTS` condition evaluates to `true` if the subquery returns at least one row.</span></span> <span data-ttu-id="76bd6-109">Dies ist hilfreich, wenn Sie das Modell auf Fälle beschränken möchten, die in der geschachtelten Tabelle einen bestimmten Wert enthalten: beispielsweise Kunden, die einen Artikel mindestens ein Mal gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="76bd6-109">This is useful in cases where you want to restrict the model to cases that contain a particular value in the nested table: for example, customers who have purchased an item at least once.</span></span>  
  
 <span data-ttu-id="76bd6-110">Eine `NOT EXISTS`-Bedingung ergibt `true`, wenn die in der Unterabfrage angegebene Bedingung nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76bd6-110">A `NOT EXISTS` condition evaluates to `true` if the condition specified in the subquery does not exist.</span></span> <span data-ttu-id="76bd6-111">Ein Beispiel dafür ist, wenn Sie das Modell auf Kunden beschränken möchten, die einen bestimmten Artikel noch nie gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="76bd6-111">An example is when you want to restrict the model to customers who have never purchased a particular item.</span></span>  
  
 <span data-ttu-id="76bd6-112">Die allgemeine Syntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="76bd6-112">The general syntax is as follows:</span></span>  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 <span data-ttu-id="76bd6-113">*filter*</span><span class="sxs-lookup"><span data-stu-id="76bd6-113">*filter*</span></span>  
 <span data-ttu-id="76bd6-114">Enthält ein oder mehrere Prädikate, die durch logische Operatoren verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-114">Contains one or more predicates, connected by logical operators.</span></span>  
  
 <span data-ttu-id="76bd6-115">*predicate list*</span><span class="sxs-lookup"><span data-stu-id="76bd6-115">*predicate list*</span></span>  
 <span data-ttu-id="76bd6-116">Ein oder mehrere gültige Filterausdrücke, die durch logische Operatoren getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-116">One or more valid filter expressions, separated by logical operators.</span></span>  
  
 <span data-ttu-id="76bd6-117">*ColumnName*</span><span class="sxs-lookup"><span data-stu-id="76bd6-117">*columnName*</span></span>  
 <span data-ttu-id="76bd6-118">Der Name einer Miningstrukturspalte.</span><span class="sxs-lookup"><span data-stu-id="76bd6-118">The name of a mining structure column.</span></span>  
  
 <span data-ttu-id="76bd6-119">logical operator</span><span class="sxs-lookup"><span data-stu-id="76bd6-119">logical operator</span></span>  
 <span data-ttu-id="76bd6-120">`AND`, `OR`, `NOT`</span><span class="sxs-lookup"><span data-stu-id="76bd6-120">`AND`, `OR`, `NOT`</span></span>  
  
 <span data-ttu-id="76bd6-121">*avPredicate*</span><span class="sxs-lookup"><span data-stu-id="76bd6-121">*avPredicate*</span></span>  
 <span data-ttu-id="76bd6-122">Filterausdruck, der nur auf skalare Miningstrukturspalten angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="76bd6-122">Filter expression that can be applied to scalar mining structure column only.</span></span> <span data-ttu-id="76bd6-123">Ein *avPredicate* -Ausdruck kann sowohl in Modellfiltern als auch in geschachtelten Tabellenfiltern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-123">An *avPredicate* expression can be used in both model filters or nested table filters.</span></span>  
  
 <span data-ttu-id="76bd6-124">Ein Ausdruck, der einen der folgenden Operatoren verwendet, kann nur auf eine kontinuierliche Spalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-124">An expression that uses any of the following operators can only be applied to a continuous column.</span></span> <span data-ttu-id="76bd6-125">:</span><span class="sxs-lookup"><span data-stu-id="76bd6-125">:</span></span>  
  
-   <span data-ttu-id="76bd6-126">**\<**(kleiner als)</span><span class="sxs-lookup"><span data-stu-id="76bd6-126">**\<** (less than)</span></span>  
  
-   <span data-ttu-id="76bd6-127">**>**(größer als)</span><span class="sxs-lookup"><span data-stu-id="76bd6-127">**>** (greater than)</span></span>  
  
-   <span data-ttu-id="76bd6-128">**>=**(größer als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="76bd6-128">**>=** (greater than or equal to)</span></span>  
  
-   <span data-ttu-id="76bd6-129">**\<=**(kleiner als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="76bd6-129">**\<=** (less than or equal to)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76bd6-130">Unabhängig vom Datentyp können diese Operatoren nicht auf eine Spalte angewendet werden, die den Typ `Discrete`, `Discretized` oder `Key` besitzt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-130">Regardless of the data type, these operators cannot be applied to a column that has the type `Discrete`, `Discretized`, or `Key`.</span></span>  
  
 <span data-ttu-id="76bd6-131">Ein Ausdruck, der einen der folgenden Operatoren verwendet, kann nur auf eine Spalte vom Typ Continuous, Discrete, Discretized oder Key angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-131">An expression that uses any of the following operators can be applied to a continuous, discrete, discretized, or key column:</span></span>  
  
-   <span data-ttu-id="76bd6-132">**=** aufbauen</span><span class="sxs-lookup"><span data-stu-id="76bd6-132">**=** (equals)</span></span>  
  
-   <span data-ttu-id="76bd6-133">**! =** (ungleich)</span><span class="sxs-lookup"><span data-stu-id="76bd6-133">**!=** (not equal to)</span></span>  
  
-   <span data-ttu-id="76bd6-134">**ist NULL**</span><span class="sxs-lookup"><span data-stu-id="76bd6-134">**IS NULL**</span></span>  
  
 <span data-ttu-id="76bd6-135">Wenn das Argument *avPredicate*für eine diskretisierte Spalte gilt, kann der im Filter verwendete Wert ein beliebiger Wert in einem bestimmten Bucket sein.</span><span class="sxs-lookup"><span data-stu-id="76bd6-135">If the argument, *avPredicate*, applies to a discretized column, the value used in the filter can be any value in a specific bucket.</span></span>  
  
 <span data-ttu-id="76bd6-136">Mit anderen Worten, Sie definieren die Bedingung nicht als `AgeDisc = '25-35'`, sondern Sie berechnen und verwenden einen Wert aus diesem Intervall.</span><span class="sxs-lookup"><span data-stu-id="76bd6-136">In other words, you do not define the condition as `AgeDisc = '25-35'`, but instead compute and then use a value from that interval.</span></span>  
  
 <span data-ttu-id="76bd6-137">Beispiel:  `AgeDisc = 27`  bedeutet jeden Wert im gleichen Intervall wie 27, in diesem Fall also 25–35.</span><span class="sxs-lookup"><span data-stu-id="76bd6-137">Example:  `AgeDisc = 27`  means any value in the same interval as 27, which in this case is 25-35.</span></span>  
  
 <span data-ttu-id="76bd6-138">*nestedTablePredicate*</span><span class="sxs-lookup"><span data-stu-id="76bd6-138">*nestedTablePredicate*</span></span>  
 <span data-ttu-id="76bd6-139">Filterausdruck, der für eine geschachtelte Tabelle gilt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-139">Filter expression that applies to a nested table.</span></span> <span data-ttu-id="76bd6-140">Kann nur in Modellfiltern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-140">Can be used in model filters only.</span></span>  
  
 <span data-ttu-id="76bd6-141">Das Unterabfrageargument *nestedTablePredicate*kann nur auf eine Spalten in einer Tabellenminingstruktur angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-141">The sub-query argument of the argument, *nestedTablePredicate*, can only apply to a table mining structure column</span></span>  
  
 <span data-ttu-id="76bd6-142">Unterabfrage</span><span class="sxs-lookup"><span data-stu-id="76bd6-142">subquery</span></span>  
 <span data-ttu-id="76bd6-143">Eine SELECT-Anweisung, gefolgt von einem gültigen Prädikat oder einer Liste von Prädikaten.</span><span class="sxs-lookup"><span data-stu-id="76bd6-143">A SELECT statement followed by a valid predicate or list of predicates.</span></span>  
  
 <span data-ttu-id="76bd6-144">Alle Prädikate müssen dem in *avPredicates*beschriebenen Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-144">All the predicates must be of the type described in *avPredicates*.</span></span> <span data-ttu-id="76bd6-145">Außerdem können die Prädikate nur auf Spalten verweisen, die in der aktuellen geschachtelten Tabelle enthalten sind, die durch das Argument *columnName*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76bd6-145">Furthermore, the predicates can refer only to columns that are included in the current nested table, identified by the argument, *columnName*.</span></span>  
  
### <a name="limitations-on-filter-syntax"></a><span data-ttu-id="76bd6-146">Einschränkungen der Filtersyntax</span><span class="sxs-lookup"><span data-stu-id="76bd6-146">Limitations on Filter Syntax</span></span>  
 <span data-ttu-id="76bd6-147">Für Filter gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="76bd6-147">The following restrictions apply to filters:</span></span>  
  
-   <span data-ttu-id="76bd6-148">Ein Filter kann nur einfache Prädikate enthalten.</span><span class="sxs-lookup"><span data-stu-id="76bd6-148">A filter can contain only simple predicates.</span></span> <span data-ttu-id="76bd6-149">Dazu gehören mathematische Operatoren, Skalare und Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-149">These include mathematical operators, scalars, and column names.</span></span>  
  
-   <span data-ttu-id="76bd6-150">Benutzerdefinierte Funktionen werden in der Filtersyntax nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-150">User-defined functions are not supported in the filter syntax.</span></span>  
  
-   <span data-ttu-id="76bd6-151">Nichtboolesche Operatoren, z. B. das Plus oder das Minuszeichen, werden in der Filtersyntax nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-151">Non-Boolean operators, such as the plus or minus signs, are not supported in the filter syntax.</span></span>  
  
## <a name="examples-of-filters"></a><span data-ttu-id="76bd6-152">Beispiele für Filter</span><span class="sxs-lookup"><span data-stu-id="76bd6-152">Examples of Filters</span></span>  
 <span data-ttu-id="76bd6-153">In den folgenden Beispielen wird die Anwendung von Filtern auf ein Miningmodell veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="76bd6-153">The following examples demonstrate the use of filters applied to a mining model.</span></span> <span data-ttu-id="76bd6-154">Wenn Sie den Filterausdruck unter Verwendung von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]erstellen, sehen Sie im Fenster **Eigenschaft** und im Bereich **Ausdruck** des Dialogfelds Filter nur die Zeichenfolge, die nach den WITH FILTER-Schlüsselwörtern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="76bd6-154">If you create the filter expression by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Property** window and the **Expression** pane of the filter dialog box, you would see only the string that appears after the WITH FILTER keywords.</span></span> <span data-ttu-id="76bd6-155">Hier wird die Definition der Miningstruktur eingefügt, um den Spaltentyp und die Spaltenverwendung verständlicher zu machen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-155">Here, the definition of the mining structure is included to make it easier to understand the column type and usage.</span></span>  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a> <span data-ttu-id="76bd6-156">Beispiel 1: Typische Filterung auf Fallebene</span><span class="sxs-lookup"><span data-stu-id="76bd6-156">Example 1: Typical Case-Level Filtering</span></span>  
 <span data-ttu-id="76bd6-157">Dieses Beispiel zeigt einen einfachen Filter, der die im Modell verwendeten Fälle auf Kunden mit dem Beruf Architekt und einem Alter von über 30 Jahren einschränkt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-157">This example shows a simple filter that restricts the cases used in the model to customers whose occupation is architect and whose age is over 30.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a> <span data-ttu-id="76bd6-158">Beispiel 2: Filterung auf Fallebene unter Verwendung von Attributen in geschachtelten Tabellen</span><span class="sxs-lookup"><span data-stu-id="76bd6-158">Example 2: Case-Level Filtering using Nested Table Attributes</span></span>  
 <span data-ttu-id="76bd6-159">Wenn Ihre Miningstruktur geschachtelte Tabellen enthält, können Sie entweder auf das Vorhandensein eines Werts in einer geschachtelten Tabelle filtern oder auf Zeilen in der geschachtelten Tabelle, die einen bestimmten Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="76bd6-159">If your mining structure contains nested tables, you can either filter on the existence of a value in a nested table, or filter on nested table rows that contain a specific value.</span></span> <span data-ttu-id="76bd6-160">Dieses Beispiel schränkt die für das Modell verwendeten Fälle auf Kunden ein, die über 30 Jahre alt sind und mindestens einen Einkauf getätigt haben, der Milch enthielt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-160">This example restricts the cases used for the model to customers over the age of 30 who made at least one purchase that included milk.</span></span>  
  
 <span data-ttu-id="76bd6-161">Dieses Beispiel zeigt, dass der Filter nicht nur Spalten zu verwenden braucht, die im Modell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="76bd6-161">As this example shows, it is not necessary that the filter use only columns that are included in the model.</span></span> <span data-ttu-id="76bd6-162">Die geschachtelte Tabelle **Products** ist Bestandteil der Miningstruktur, ist jedoch nicht im Miningmodell enthalten.</span><span class="sxs-lookup"><span data-stu-id="76bd6-162">The nested table **Products** is part of the mining structure, but is not included in the mining model.</span></span> <span data-ttu-id="76bd6-163">Sie können jedoch auf Werte und Attribute in der geschachtelten Tabelle filtern.</span><span class="sxs-lookup"><span data-stu-id="76bd6-163">However, you can still filter on values and attributes in the nested table.</span></span> <span data-ttu-id="76bd6-164">Um die Details dieser Fälle anzuzeigen, muss Drillthrough aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-164">To view the details of these cases, drillthrough must be enabled.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a> <span data-ttu-id="76bd6-165">Beispiel 3: Filterung auf Fallebene unter Verwendung von mehreren Attributen in geschachtelten Tabellen</span><span class="sxs-lookup"><span data-stu-id="76bd6-165">Example 3: Case-Level Filtering on Multiple Nested Table Attributes</span></span>  
 <span data-ttu-id="76bd6-166">Dieses Beispiel zeigt einen dreiteiligen Filter: Eine Bedingung gilt für die Falltabelle, eine andere Bedingung für ein Attribut in der geschachtelten Tabelle und eine weitere Bedingung für einen bestimmten Wert in einer der geschachtelten Tabellenspalten.</span><span class="sxs-lookup"><span data-stu-id="76bd6-166">This example shows a three-part filter: a condition applies to the case table, another condition to an attribute in the nested table, and another condition on a specific value in one of the nested table columns.</span></span>  
  
 <span data-ttu-id="76bd6-167">Die erste Bedingung im Filter, `Age > 30`, gilt für eine Spalte in der Falltabelle.</span><span class="sxs-lookup"><span data-stu-id="76bd6-167">The first condition in the filter, `Age > 30`, applies to a column in the case table.</span></span> <span data-ttu-id="76bd6-168">Die übrigen Bedingungen gelten für die geschachtelte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="76bd6-168">The remaining conditions apply to the nested table.</span></span>  
  
 <span data-ttu-id="76bd6-169">Die zweite Bedingung, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, überprüft, ob in der geschachtelten Tabelle mindestens ein Einkauf vorhanden ist, der Milch enthält.</span><span class="sxs-lookup"><span data-stu-id="76bd6-169">The second condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, checks for the presence of at least one purchase in the nested table that included milk.</span></span> <span data-ttu-id="76bd6-170">Die dritte Bedingung, `Quantity>=2`, bedeutet, dass der Kunde in einer Transaktion mindestens zwei Einheiten Milch gekauft haben muss.</span><span class="sxs-lookup"><span data-stu-id="76bd6-170">The third condition, `Quantity>=2`, means that the customer must have purchased at least two units of milk in a single transaction.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a> <span data-ttu-id="76bd6-171">Beispiel 4: Filterung auf Fallebene unter Verwendung der Abwesenheit von Attributen in der geschachtelten Tabelle</span><span class="sxs-lookup"><span data-stu-id="76bd6-171">Example 4: Case-Level Filtering On Absence of Nested Table Attributes</span></span>  
 <span data-ttu-id="76bd6-172">Dieses Beispiel zeigt, wie Fälle auf Kunden beschränkt werden, die einen bestimmten Artikel nicht gekauft haben, indem auf das Nichtvorhandensein eines Attributs in der geschachtelten Tabelle gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="76bd6-172">This example shows how to limit cases to customer who did not purchase a specific item, by filtering on the absence of an attribute in the nested table.</span></span> <span data-ttu-id="76bd6-173">In diesem Beispiel wird das Modell so eingerichtet, dass damit Kunden ermittelt werden können, die älter als 30 Jahre sind und noch nie Milch gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="76bd6-173">In this example, the model is trained using customers over the age of 30 who have never bought milk.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a> <span data-ttu-id="76bd6-174">Beispiel 5: Filterung unter Verwendung von mehreren Werten in geschachtelten Tabellen</span><span class="sxs-lookup"><span data-stu-id="76bd6-174">Example 5: Filtering on Multiple Nested Table Values</span></span>  
 <span data-ttu-id="76bd6-175">Dieses Beispiel soll das Filtern von geschachtelten Tabellen veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-175">The purpose of the example is to show nested table filtering.</span></span> <span data-ttu-id="76bd6-176">Der Filter für geschachtelte Tabellen wird nach dem Fallfilter angewendet und schränkt nur Zeilen in geschachtelten Tabellen ein.</span><span class="sxs-lookup"><span data-stu-id="76bd6-176">The nested table filter is applied after the case filter, and only restricts nested table rows.</span></span>  
  
 <span data-ttu-id="76bd6-177">Dieses Modell kann mehrere Fälle mit leeren geschachtelten Tabellen enthalten, da EXISTS nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="76bd6-177">This model could contain multiple cases with empty nested tables because EXISTS is not specified.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a> <span data-ttu-id="76bd6-178">Beispiel 6: Filterung unter Verwendung von Attributen in geschachtelten Tabellen und EXISTS</span><span class="sxs-lookup"><span data-stu-id="76bd6-178">Example 6: Filtering on Nested Table Attributes and EXISTS</span></span>  
 <span data-ttu-id="76bd6-179">In diesem Beispiel beschränkt der Filter für die geschachtelte Tabelle die Zeilen auf solche, die entweder Milch oder Wasser in Flaschen enthalten.</span><span class="sxs-lookup"><span data-stu-id="76bd6-179">In this example, the filter on the nested table restricts the rows to those that contain either milk or bottled water.</span></span> <span data-ttu-id="76bd6-180">Anschließend werden die Fälle im Modell mithilfe einer `EXISTS`-Anweisung eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-180">Then, the cases in the model are restricted by using an `EXISTS` statement.</span></span> <span data-ttu-id="76bd6-181">Dies stellt sicher, dass die geschachtelte Tabelle nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="76bd6-181">This makes sure that the nested table is not empty.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a> <span data-ttu-id="76bd6-182">Beispiel 7: Komplexe Filterkombinationen</span><span class="sxs-lookup"><span data-stu-id="76bd6-182">Example 7: Complex Filter Combinations</span></span>  
 <span data-ttu-id="76bd6-183">Das Szenario für dieses Modell ähnelt dem von Beispiel 4, ist jedoch wesentlich komplexer.</span><span class="sxs-lookup"><span data-stu-id="76bd6-183">The scenario for this model resembles that of Example 4, but is far more complex.</span></span> <span data-ttu-id="76bd6-184">Die in der Tabelle **ProductsOnSale**angezeigte Tabelle enthält die Filterbedingung, `(OnSale)` Was bedeutet, dass der Wert von **OnSale** `true` für das in **ProductName**aufgelistete Produkt lauten muss.</span><span class="sxs-lookup"><span data-stu-id="76bd6-184">The nested table, **ProductsOnSale**, has the filter condition `(OnSale)` meaning that the value of **OnSale** must be `true` for the product listed in **ProductName**.</span></span> <span data-ttu-id="76bd6-185">Hier ist **OnSale** eine Strukturspalte.</span><span class="sxs-lookup"><span data-stu-id="76bd6-185">Here, **OnSale** is a structure column.</span></span>  
  
 <span data-ttu-id="76bd6-186">Der zweite Teil des Filters für **ProductsNotOnSale**wiederholt diese Syntax, filtert jedoch nach Produkten, bei denen der Wert von **OnSale** ist `not true``(!OnSale)` .</span><span class="sxs-lookup"><span data-stu-id="76bd6-186">The second part of the filter, for **ProductsNotOnSale**, repeats this syntax, but filters on products for which the value of **OnSale** is `not true``(!OnSale)`.</span></span>  
  
 <span data-ttu-id="76bd6-187">Schließlich werden die Bedingungen kombiniert und der Falltabelle wird eine weitere Einschränkung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="76bd6-187">Finally, the conditions are combined and one additional restriction is added to the case table.</span></span> <span data-ttu-id="76bd6-188">Das Ergebnis ist die Vorhersage von Käufen der Produkte in der Liste **ProductsNotOnSale** auf der Grundlage der Fälle in der Liste **ProductsOnSale** für alle Kunden mit einem Alter von über 25.</span><span class="sxs-lookup"><span data-stu-id="76bd6-188">The result is to predict purchases of products in the **ProductsNotOnSale** list, based on the cases that are included in the **ProductsOnSale** list, for all customers over the age of 25.</span></span>  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a> <span data-ttu-id="76bd6-189">Beispiel 8: Filtern unter Verwendung von Datumsangaben</span><span class="sxs-lookup"><span data-stu-id="76bd6-189">Example 8: Filtering on Dates</span></span>  
 <span data-ttu-id="76bd6-190">Sie können Eingabespalten genau wie alle anderen Daten nach Datumsangaben filtern.</span><span class="sxs-lookup"><span data-stu-id="76bd6-190">You can filter input columns on dates, as you would any other data.</span></span> <span data-ttu-id="76bd6-191">In einer Spalte des Typs Datum/Uhrzeit enthaltene Datumsangaben sind kontinuierliche Werte. Sie können daher mit Operatoren wie Größer als (>) oder Kleiner als (<) einen Datumsbereich festlegen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-191">Dates contained in a column of type date/time are continuous values; therefore, you can specify a date range by using operators such as greater than (>) or less than (<).</span></span> <span data-ttu-id="76bd6-192">Wenn die Datenquelle Datumsangaben nicht durch einen kontinuierlichen Datentyp, sondern als Einzel- oder Textwerte darstellt, können Sie nicht nach einem Datumsbereich filtern, sondern müssen einzelne Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="76bd6-192">If your data source does not represent dates by a Continuous data type, but as discrete or text values, you cannot filter on a date range, but must specify individual discrete values.</span></span>  
  
 <span data-ttu-id="76bd6-193">Sie können jedoch keinen Filter für die Datumsspalte in einem Zeitreihenmodell erstellen, wenn die für den Filter verwendete Datumsspalte gleichzeitig die Schlüsselspalte für das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="76bd6-193">However, you cannot create a filter on the date column in a time series model if the date column used for the filter is also the key column for the model.</span></span> <span data-ttu-id="76bd6-194">Dies liegt daran, dass die Datumsspalte in Zeitreihenmodellen und Sequenzclustermodellen als eine Spalte vom Typ `KeyTime` oder `KeySequence` verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="76bd6-194">That is because, in time series models and sequence clustering models, the date column might be handled as type `KeyTime` or `KeySequence`.</span></span>  
  
 <span data-ttu-id="76bd6-195">Wenn Sie in einem Zeitreihenmodell nach kontinuierlichen Datumsangaben filtern müssen, können Sie in der Miningstruktur eine Kopie der Spalte erstellen und das Modell unter Verwendung der neuen Spalte filtern.</span><span class="sxs-lookup"><span data-stu-id="76bd6-195">If you need to filter on continuous dates in a time series model, you can create a copy of the column in the mining structure, and filter the model on the new column.</span></span>  
  
 <span data-ttu-id="76bd6-196">Der folgende Ausdruck stellt beispielsweise einen Filter für eine Datumsspalte von Typ `Continuous` dar, die dem Modell für die Planung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="76bd6-196">For example, the following expression represents a filter on a date column of type `Continuous` that has been added to the Forecasting model.</span></span>  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  <span data-ttu-id="76bd6-197">Beachten Sie, dass sich alle zusätzlichen Spalten, die Sie dem Modell hinzufügen, auf die Ergebnisse auswirken können.</span><span class="sxs-lookup"><span data-stu-id="76bd6-197">Note that any extra columns that you add to the model might affect the results.</span></span> <span data-ttu-id="76bd6-198">Wenn Sie nicht möchten, dass die Spalte zur Berechnung der Reihe verwendet wird, sollten Sie die Spalte daher nur der Miningstruktur und nicht dem Modell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-198">Therefore, if you do not want the column to be used in computation of the series, you should add the column only to the mining structure, and not to the model.</span></span> <span data-ttu-id="76bd6-199">Sie können auch das Modellflag für die Spalte auf `PredictOnly` oder `Ignore` festlegen.</span><span class="sxs-lookup"><span data-stu-id="76bd6-199">You can also set the model flag on the column to `PredictOnly` or to `Ignore`.</span></span> <span data-ttu-id="76bd6-200">Weitere Informationen finden Sie unter [Modellierungsflags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="76bd6-200">For more information, see [Modeling Flags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span></span>  
  
 <span data-ttu-id="76bd6-201">Für andere Modelltypen können Sie Datumsangaben ebenso wie jede andere Spalte als Eingabekriterien oder Filterkriterien verwenden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-201">For other model types, you can use dates as input criteria or filter criteria just like you would in any other column.</span></span> <span data-ttu-id="76bd6-202">Wenn Sie jedoch einen bestimmten Grad an Granularität benötigen, die von einem `Continuous`-Datentyp nicht unterstützt wird, können Sie einen abgeleiteten Wert in der Datenquelle erstellen, indem Sie mithilfe von Ausdrücken die Einheit extrahieren, die zur Filterung und Analyse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76bd6-202">However, if you need to use a specific level of granularity that is not supported by a `Continuous` data type, you can create a derived value in the data source by using expressions to extract the unit to use in filtering and analysis.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="76bd6-203">Wenn Sie Datumsangaben als Filterkriterien angeben, müssen Sie unabhängig vom Datumsformat für das aktuelle Betriebssystem das folgende Format verwenden: `mm/dd/yyyy`.</span><span class="sxs-lookup"><span data-stu-id="76bd6-203">When you specify a dates as filter criteria, you must use the following format, regardless of the date format for the current OS: `mm/dd/yyyy`.</span></span> <span data-ttu-id="76bd6-204">Jedes andere Format führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="76bd6-204">Any other format results in an error.</span></span>  
  
 <span data-ttu-id="76bd6-205">Wenn Sie beispielsweise die Callcenterergebnisse filtern möchten, um nur Wochenenden anzuzeigen, können Sie in der Datenquellensicht einen Ausdruck erstellen, der den Namen des Wochentags für jedes Datum extrahiert, und dann diesen Wert als Eingabe oder als diskreten Wert für die Filterung verwenden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-205">For example, if you want to filter your call center results to show only weekends, you can create an expression in the data source view that extracts the weekday name for each date, and then use that weekday name value for input or as a discrete value in filtering.</span></span> <span data-ttu-id="76bd6-206">Bedenken Sie jedoch, dass sich wiederholende Werte auf das Modell auswirken können. Sie sollten deshalb nicht die Datumsspalte und den abgeleiteten Wert, sondern nur eine der Spalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="76bd6-206">Just remember that repeating values can affect the model, so you should use only one of the columns, not the date column plus the derived value.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="76bd6-207">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76bd6-207">See Also</span></span>  
 <span data-ttu-id="76bd6-208">[Filter für Mining Modelle &#40;Analysis Services Data Mining-&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="76bd6-208">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="76bd6-209">Tests und Überprüfung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="76bd6-209">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
  
