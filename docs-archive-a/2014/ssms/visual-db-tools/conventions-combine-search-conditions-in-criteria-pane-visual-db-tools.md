---
title: Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- multiple OR clauses
- combining search conditions
- OR operator
- AND, Criteria pane
- multiple AND clauses
ms.assetid: d4859be5-ff5b-48b2-a101-ad40c6dbcc68
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684521baa87d5325366a0e18296cd35342a0e947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695166"
---
# <a name="conventions-for-combining-search-conditions-in-the-criteria-pane-visual-database-tools"></a><span data-ttu-id="112ff-102">Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="112ff-102">Conventions for Combining Search Conditions in the Criteria Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="112ff-103">Abfragen können eine beliebige Anzahl von Suchbedingungen enthalten, die mit beliebig vielen AND-Operatoren und OR-Operatoren verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="112ff-103">You can create queries that include any number of search conditions, linked with any number of AND and OR operators.</span></span> <span data-ttu-id="112ff-104">Eine Abfrage mit mehreren AND-Klauseln und OR-Klauseln kann sehr komplex sein. Es ist daher hilfreich zu wissen, wie eine Abfrage bei der Ausführung interpretiert wird und wie sie im [Kriterienbereich](visual-database-tools.md) und im [SQL-Bereich](sql-pane-visual-database-tools.md) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="112ff-104">A query with a combination of AND and OR clauses can become complex, so it is helpful to understand how such a query is interpreted when you execute it, and how such a query is represented in the [Criteria Pane](visual-database-tools.md) and [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="112ff-105">Ausführliche Informationen zu Suchbedingungen, die nur einen AND- oder OR-Operator enthalten, finden Sie unter [Angeben mehrerer Suchbedingungen für eine Spalte &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) und [Angeben mehrerer Suchbedingungen für mehrere Spalten &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="112ff-105">For details about search conditions that contain only one AND or OR operator, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) and [Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="112ff-106">Nachstehend erhalten Sie Informationen zu den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="112ff-106">Below you will find information about:</span></span>  
  
-   <span data-ttu-id="112ff-107">Der Vorrang von AND und OR in Abfragen mit beiden Operatoren.</span><span class="sxs-lookup"><span data-stu-id="112ff-107">The precedence of AND and OR in queries that contain both.</span></span>  
  
-   <span data-ttu-id="112ff-108">Die logische Beziehung der Bedingungen in AND-Klauseln und OR-Klauseln.</span><span class="sxs-lookup"><span data-stu-id="112ff-108">How the conditions in AND and OR clauses relate logically to one another.</span></span>  
  
-   <span data-ttu-id="112ff-109">Die Darstellung von Abfragen, die AND und OR enthalten, durch den Abfrage- und Sicht-Designer im Kriterienbereich.</span><span class="sxs-lookup"><span data-stu-id="112ff-109">How the Query and View Designer represents in the Criteria Pane queries that contain both AND and OR.</span></span>  
  
 <span data-ttu-id="112ff-110">In den Beispielen in den folgenden Abschnitten wird eine `employee` -Tabelle verwendet, die die Spalten `hire_date`, `job_lvl`und `status`enthält.</span><span class="sxs-lookup"><span data-stu-id="112ff-110">To help you understand the discussion below, imagine that you are working with an `employee` table containing the columns `hire_date`, `job_lvl`, and `status`.</span></span> <span data-ttu-id="112ff-111">In den Beispielen wird angenommen, dass Sie Informationen suchen, beispielsweise die Betriebszugehörigkeit eines Mitarbeiters (Einstellungsdatum), die Art der Tätigkeit des Mitarbeiters (Stellenbeschreibung) und den Mitarbeiterstatus (z. B. Ruhestand).</span><span class="sxs-lookup"><span data-stu-id="112ff-111">The examples assume that you need to know information such as how long an employee has worked with the company (that is, what the employee's hire date is), what type of job the employee performs (what the job level is), and the employee's status (for example, retired).</span></span>  
  
## <a name="precedence-of-and-and-or"></a><span data-ttu-id="112ff-112">Vorrang von AND und OR</span><span class="sxs-lookup"><span data-stu-id="112ff-112">Precedence of AND and OR</span></span>  
 <span data-ttu-id="112ff-113">Bei der Ausführung einer Abfrage werden zuerst die mit AND verknüpften Klauseln und anschließend die mit OR verknüpften Klauseln ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="112ff-113">When a query is executed, it evaluates first the clauses linked with AND, and then those linked with OR.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="112ff-114">Der NOT-Operator hat gegenüber AND und OR Vorrang.</span><span class="sxs-lookup"><span data-stu-id="112ff-114">The NOT operator takes precedence over both AND and OR.</span></span>  
  
 <span data-ttu-id="112ff-115">Sie können eine dem folgenden Beispiel entsprechende WHERE-Klausel erstellen, um beispielsweise nach Mitarbeitern zu suchen, die seit mindestens fünf Jahren in Tätigkeiten einer unteren Stufe in der Firma beschäftigt sind, oder die unabhängig vom Einstellungsdatum in einer Tätigkeit einer mittleren Stufe angestellt sind:</span><span class="sxs-lookup"><span data-stu-id="112ff-115">For example, to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs without regard for their hire date, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   job_lvl = 100 OR  
   job_lvl = 200  
  
```  
  
 <span data-ttu-id="112ff-116">Zum Überschreiben des Standardvorrangs von AND gegenüber OR können Sie Klammern um bestimmte Bedingungen im SQL-Bereich setzen.</span><span class="sxs-lookup"><span data-stu-id="112ff-116">To override the default precedence of AND over OR, you can put parentheses around specific conditions in the SQL pane.</span></span> <span data-ttu-id="112ff-117">Bedingungen in Klammern werden immer zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="112ff-117">Conditions in parentheses are always evaluated first.</span></span> <span data-ttu-id="112ff-118">Sie können eine dem folgenden Beispiel entsprechende WHERE-Klausel erstellen, um beispielsweise nach allen Mitarbeitern zu suchen, die länger als fünf Jahre in einer Tätigkeit der unteren oder mittleren Stufe in der Firma arbeiten:</span><span class="sxs-lookup"><span data-stu-id="112ff-118">For example, to find all employees who have been with the company more than five years in either lower or middle-level jobs, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
> [!TIP]  
>  <span data-ttu-id="112ff-119">Es wird empfohlen, aus Gründen der Übersichtlichkeit beim Kombinieren von AND-Klauseln und OR-Klauseln immer Klammern zu setzen, auch wenn der Standardvorrang gilt.</span><span class="sxs-lookup"><span data-stu-id="112ff-119">It is recommended that, for clarity, you always include parentheses when combining AND and OR clauses instead of relying on the default precedence.</span></span>  
  
## <a name="how-and-works-with-multiple-or-clauses"></a><span data-ttu-id="112ff-120">Verwenden von AND mit mehreren OR-Klauseln</span><span class="sxs-lookup"><span data-stu-id="112ff-120">How AND Works with Multiple OR Clauses</span></span>  
 <span data-ttu-id="112ff-121">Wenn Sie wissen, wie AND-Klauseln und OR-Klauseln beim Kombinieren miteinander verknüpft werden, erleichtert dies das Erstellen und Verstehen komplexer Abfragen im Abfrage- und Sicht-Designer.</span><span class="sxs-lookup"><span data-stu-id="112ff-121">Understanding how AND and OR clauses are related when combined can help you construct and understand complex queries in the Query and View Designer.</span></span>  
  
 <span data-ttu-id="112ff-122">Wenn Sie mehrere Bedingungen mit AND verknüpfen, gilt der erste Satz der mit AND verknüpften Bedingungen für alle Bedingungen im zweiten Satz.</span><span class="sxs-lookup"><span data-stu-id="112ff-122">If you link multiple conditions using AND, the first set of conditions linked with AND applies to all the conditions in the second set.</span></span> <span data-ttu-id="112ff-123">Das heißt, dass eine Bedingung, die durch AND mit einer anderen Bedingung verknüpft ist, an alle Bedingungen im zweiten Satz verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="112ff-123">In other words, a condition linked with AND to another condition is distributed to all the conditions in the second set.</span></span> <span data-ttu-id="112ff-124">Die folgende schematische Darstellung enthält eine mit einem Satz von OR-Bedingungen verknüpfte AND-Bedingung:</span><span class="sxs-lookup"><span data-stu-id="112ff-124">For example, the following schematic representation shows an AND condition linked to a set of OR conditions:</span></span>  
  
```  
A AND (B OR C)  
```  
  
 <span data-ttu-id="112ff-125">Die Darstellung ist logisch equivalent zu der folgenden schematischen Darstellung, die zeigt, wie sich die AND-Bedingung zum zweiten Satz von Bedingungen verhält:</span><span class="sxs-lookup"><span data-stu-id="112ff-125">The representation above is logically equivalent to the following schematic representation, which shows how the AND condition is distributed to the second set of conditions:</span></span>  
  
```  
(A AND B) OR (A AND C)  
```  
  
 <span data-ttu-id="112ff-126">Dieses Distributivprinzip beeinflusst auch die Verwendung des Abfrage- und Sicht-Designers.</span><span class="sxs-lookup"><span data-stu-id="112ff-126">This distributive principle affects how you use the Query and View Designer.</span></span> <span data-ttu-id="112ff-127">Angenommen, Sie suchen alle Mitarbeiter, die der Firma seit mehr als fünf Jahren angehören und Tätigkeiten einer niedrigen oder mittleren Stufe ausführen.</span><span class="sxs-lookup"><span data-stu-id="112ff-127">For example, imagine that you are looking for all employees who have been with the company more than five years in either lower or middle-level jobs.</span></span> <span data-ttu-id="112ff-128">Geben Sie die folgende WHERE-Klausel im SQL-Bereich in die Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="112ff-128">You enter the following WHERE clause into the statement in the SQL pane:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
 <span data-ttu-id="112ff-129">Die mit AND verknüpfte Klausel gilt für beide mit OR verknüpften Klauseln.</span><span class="sxs-lookup"><span data-stu-id="112ff-129">The clause linked with AND applies to both clauses linked with OR.</span></span> <span data-ttu-id="112ff-130">Sie können dies auch durch Wiederholen der AND-Bedingung für jede Bedingung in der OR-Klausel ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="112ff-130">An explicit way to express this is to repeat the AND condition once for each condition in the OR clause.</span></span> <span data-ttu-id="112ff-131">Die folgende Anweisung ist genauer (und länger) als die vorhergehende Anweisung, ist jedoch logisch equivalent:</span><span class="sxs-lookup"><span data-stu-id="112ff-131">The following statement is more explicit (and longer) than the previous statement, but is logically equivalent to it:</span></span>  
  
```  
WHERE    (hire_date < '01/01/95' ) AND  
  (job_lvl = 100) OR   
  (hire_date < '01/01/95' ) AND   
  (job_lvl = 200)  
```  
  
 <span data-ttu-id="112ff-132">Die Distribution von AND-Klauseln zu verknüpften OR-Klauseln kann immer angewendet werden, unabhängig von der Anzahl von einzelnen Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="112ff-132">The principle of distributing AND clauses to linked OR clauses applies no matter how many individual conditions are involved.</span></span> <span data-ttu-id="112ff-133">Angenommen, Sie möchten alle Mitarbeiter suchen, die der Firma seit mehr als fünf Jahren angehören und die Tätigkeiten der mittleren oder höheren Stufe ausführen oder im Ruhestand sind.</span><span class="sxs-lookup"><span data-stu-id="112ff-133">For example, imagine that you want to find higher or middle-level employees who have been with the company more than five years or are retired.</span></span> <span data-ttu-id="112ff-134">Die entsprechende WHERE-Klausel kann folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="112ff-134">The WHERE clause might look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 OR job_lvl = 300) AND  
   (hire_date < '01/01/95' ) OR (status = 'R')  
```  
  
 <span data-ttu-id="112ff-135">Nachdem die mit AND verknüpften Bedingungen verteilt wurden, ergibt sich folgende WHERE-Klausel:</span><span class="sxs-lookup"><span data-stu-id="112ff-135">After the conditions linked with AND have been distributed, the WHERE clause will look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 200 AND status = 'R') OR  
   (job_lvl = 300 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 300 AND status = 'R')   
```  
  
## <a name="how-multiple-and-and-or-clauses-are-represented-in-the-criteria-pane"></a><span data-ttu-id="112ff-136">Darstellung mehrerer AND-Klauseln und OR-Klauseln im Kriterienbereich</span><span class="sxs-lookup"><span data-stu-id="112ff-136">How Multiple AND and OR Clauses Are Represented in the Criteria Pane</span></span>  
 <span data-ttu-id="112ff-137">Der Abfrage- und Sicht-Designer stellt die Suchbedingungen im [Kriterienbereich](visual-database-tools.md)dar.</span><span class="sxs-lookup"><span data-stu-id="112ff-137">The Query and View Designer represents your search conditions in the [Criteria Pane](visual-database-tools.md).</span></span> <span data-ttu-id="112ff-138">Bei mehreren mit AND und OR verknüpften Klauseln kann diese Darstellung im Kriterienbereich jedoch abweichen.</span><span class="sxs-lookup"><span data-stu-id="112ff-138">However, in some cases that involve multiple clauses linked with AND and OR, the representation in the Criteria Pane might not be what you expect.</span></span> <span data-ttu-id="112ff-139">Außerdem kann die SQL-Anweisung von den Eingaben abweichen, wenn Sie die Abfrage im Kriterienbereich oder im [Diagrammbereich](diagram-pane-visual-database-tools.md)ändern.</span><span class="sxs-lookup"><span data-stu-id="112ff-139">In addition, if you modify your query in the Criteria Pane or [Diagram Pane](diagram-pane-visual-database-tools.md), you might find that your SQL statement has been changed from what you entered.</span></span>  
  
 <span data-ttu-id="112ff-140">Diese Regeln legen grundsätzlich fest, wie AND- und OR-Klauseln im Kriterienbereich angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="112ff-140">In general, these rules dictate how AND and OR clauses appear in the Criteria Pane:</span></span>  
  
-   <span data-ttu-id="112ff-141">Alle mit AND verknüpften Bedingungen werden in der Datenblattspalte **Filter** oder in derselben **Oder** -Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="112ff-141">All conditions linked with AND appear in the **Filter** grid column or in the same **Or...** column.</span></span>  
  
-   <span data-ttu-id="112ff-142">Alle mit OR verknüpften Bedingungen werden in separaten **Oder** Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="112ff-142">All conditions linked with OR appear in separate **Or...** columns.</span></span>  
  
-   <span data-ttu-id="112ff-143">Wenn das logische Ergebnis einer Kombination von AND- und OR-Klauseln die Verteilung von AND in verschiedene OR-Klauseln ist, wird dies im Kriterienbereich entsprechend angezeigt, indem die AND-Klausel so oft wie erforderlich wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="112ff-143">If the logical result of a combination of AND and OR clauses is that the AND is distributed into several OR clauses, the Criteria Pane represents this explicitly by repeating the AND clause as many times as necessary.</span></span>  
  
 <span data-ttu-id="112ff-144">Sie könnten z. B. im SQL-Bereich eine Suchbedingung nach folgendem Muster erstellen. Dabei haben zwei mit AND verknüpfte Klauseln Vorrang gegenüber einer dritten mit OR verknüpften Klausel:</span><span class="sxs-lookup"><span data-stu-id="112ff-144">For example, in the SQL pane you might create a search condition such as the following, in which two clauses linked with AND take precedence over a third one linked with OR:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  (job_lvl = 100) OR   
  (status = 'R')  
```  
  
 <span data-ttu-id="112ff-145">Diese WHERE-Klausel wird vom Abfrage- und Sicht-Designer folgendermaßen im Kriterienbereich dargestellt:</span><span class="sxs-lookup"><span data-stu-id="112ff-145">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="112ff-146">![OR-Klauselrangfolge im Kriterienbereich](../../database-engine/media//vs-criteriapane1.gif "OR-Klauselrangfolge im Kriterienbereich")</span><span class="sxs-lookup"><span data-stu-id="112ff-146">![OR clause precedence in the Criteria Pane](../../database-engine/media//vs-criteriapane1.gif "OR clause precedence in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="112ff-147">Wenn die verknüpfte OR-Klausel Vorrang vor einer AND-Klausel erhält, wird die AND-Klausel für jede OR-Klausel wiederholt.</span><span class="sxs-lookup"><span data-stu-id="112ff-147">However, if the linked OR clauses take precedence over an AND clause, the AND clause is repeated for each OR clause.</span></span> <span data-ttu-id="112ff-148">Dadurch wird die AND-Klausel an jede OR-Klausel verteilt.</span><span class="sxs-lookup"><span data-stu-id="112ff-148">This causes the AND clause to be distributed to each OR clause.</span></span> <span data-ttu-id="112ff-149">Sie können im SQL-Bereich z. B. folgende WHERE-Klausel erstellen:</span><span class="sxs-lookup"><span data-stu-id="112ff-149">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ( (job_lvl = 100) OR   
  (status = 'R') )  
```  
  
 <span data-ttu-id="112ff-150">Diese WHERE-Klausel wird vom Abfrage- und Sicht-Designer folgendermaßen im Kriterienbereich dargestellt:</span><span class="sxs-lookup"><span data-stu-id="112ff-150">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="112ff-151">![Mehrere AND- und OR-Klauseln im Kriterienbereich](../../database-engine/media//vs-criteriapane2.gif "Mehrere AND- und OR-Klauseln im Kriterienbereich")</span><span class="sxs-lookup"><span data-stu-id="112ff-151">![Multiple AND and OR clauses in the Criteria Pane](../../database-engine/media//vs-criteriapane2.gif "Multiple AND and OR clauses in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="112ff-152">Wenn die verknüpften OR-Klauseln nur eine Datenspalte enthalten, kann der Abfrage- und Sicht-Designer die gesamte OR-Klausel in eine Zelle des DatenBlatts einfügen, sodass die AND-Klausel nicht ständig wiederholt werden muss.</span><span class="sxs-lookup"><span data-stu-id="112ff-152">If the linked OR clauses involve only one data column, the Query and View Designer can place the entire OR clause into a single cell of the grid, avoiding the need to repeat the AND clause.</span></span> <span data-ttu-id="112ff-153">Sie können im SQL-Bereich z. B. folgende WHERE-Klausel erstellen:</span><span class="sxs-lookup"><span data-stu-id="112ff-153">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ((status = 'R') OR (status = 'A'))  
```  
  
 <span data-ttu-id="112ff-154">Diese WHERE-Klausel wird vom Abfrage- und Sicht-Designer folgendermaßen im Kriterienbereich dargestellt:</span><span class="sxs-lookup"><span data-stu-id="112ff-154">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="112ff-155">![Im Kriterienbereich definierte, verknüpfte OR-Klauseln](../../database-engine/media//vs-criteriapane3.gif "Im Kriterienbereich definierte, verknüpfte OR-Klauseln")</span><span class="sxs-lookup"><span data-stu-id="112ff-155">![Linked OR clauses defined in the Criteria Pane](../../database-engine/media//vs-criteriapane3.gif "Linked OR clauses defined in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="112ff-156">Wenn Sie die Abfrage ändern (z. B. durch Ändern eines der Werte im Kriterienbereich), erstellt der Abfrage- und Sicht-Designer die SQL-Anweisung im SQL-Bereich neu.</span><span class="sxs-lookup"><span data-stu-id="112ff-156">If you make a change to the query (such as changing one of the values in the Criteria Pane), the Query and View Designer recreates the SQL statement in the SQL pane.</span></span> <span data-ttu-id="112ff-157">Die neu erstellte SQL-Anweisung stimmt eher mit der Anzeige im Kriterienbereich als mit der ursprünglichen Anweisung überein.</span><span class="sxs-lookup"><span data-stu-id="112ff-157">The recreated SQL statement will resemble the Criteria Pane display rather than your original statement.</span></span> <span data-ttu-id="112ff-158">Wenn der Kriterienbereich z. B. verteilte AND-Klauseln enthält, wird die Anweisung im SQL-Bereich mit eindeutig verteilten AND-Klauseln erstellt.</span><span class="sxs-lookup"><span data-stu-id="112ff-158">For example, if the Criteria Pane contains distributed AND clauses, the resulting statement in the SQL pane will be recreated with explicit distributed AND clauses.</span></span> <span data-ttu-id="112ff-159">Ausführliche Informationen finden Sie weiter oben unter "Verwenden von AND mit mehreren OR-Klauseln".</span><span class="sxs-lookup"><span data-stu-id="112ff-159">For details, see "How AND Works with Multiple OR Clauses" earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="112ff-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="112ff-160">See Also</span></span>  
 [<span data-ttu-id="112ff-161">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="112ff-161">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
