---
title: Einschließen oder Ausschließen von Zeilen (Visual Database Tools) Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- included rows
- search conditions [SQL Server], HAVING clause
- search criteria [SQL Server], including rows
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- search conditions [SQL Server], WHERE clause
- row included in search [SQL Server]
- excluding rows
ms.assetid: ba4e1202-31a2-444d-8365-c68a530ef223
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7b2d31c51296fa73a503e59a14adb60d79a61178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618965"
---
# <a name="include-or-exclude-rows-visual-database-tools"></a><span data-ttu-id="7bc84-102">Einschließen oder Ausschließen von Zeilen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7bc84-102">Include or Exclude Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="7bc84-103">Wenn Sie die Anzahl von durch eine SELECT-Abfrage zurückgegebenen Zeilen einschränken möchten, erstellen Sie Suchbedingungen oder Filterkriterien.</span><span class="sxs-lookup"><span data-stu-id="7bc84-103">To restrict the number of rows a SELECT query should return, you create search conditions or filter criteria.</span></span> <span data-ttu-id="7bc84-104">In SQL werden Suchbedingungen entweder in die WHERE-Klausel der Anweisung eingefügt oder – wenn Sie eine Aggregatabfrage erstellen – in die HAVING-Klausel.</span><span class="sxs-lookup"><span data-stu-id="7bc84-104">In SQL, search conditions appear in the WHERE clause of the statement, or if you are creating an aggregate query, in the HAVING clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bc84-105">Sie können auch Suchbedingungen definieren, welche die von einer UPDATE-, INSERT RESULTS-, INSERT VALUES-, DELETE- oder MAKE TABLE-Abfrage betroffenen Zeilen angeben.</span><span class="sxs-lookup"><span data-stu-id="7bc84-105">You can also use search conditions to indicate which rows are affected by an Update, Insert Results, Insert Values, Delete, or Make Table query.</span></span>  
  
 <span data-ttu-id="7bc84-106">Sobald die Abfrage ausgeführt wird, untersucht [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Suchbedingung und wendet sie auf jede Zeile in den durchsuchten Tabellen an.</span><span class="sxs-lookup"><span data-stu-id="7bc84-106">When the query runs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] examines and applies the search condition to each row in the tables you are searching.</span></span> <span data-ttu-id="7bc84-107">Wenn eine Zeile die Bedingungen erfüllt, wird sie in die Abfrage aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="7bc84-107">If the row meets the condition, it is included in the query.</span></span> <span data-ttu-id="7bc84-108">Eine Suchbedingung, die z. B. alle Mitarbeiter in einer bestimmten Region ermittelt, könnte folgendermaßen formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="7bc84-108">For example, a search condition that would find all the employees in a particular region might be:</span></span>  
  
```  
region = 'UK'  
```  
  
 <span data-ttu-id="7bc84-109">Die Definition der Kriterien für die Auswahl der Ergebniszeilen kann über mehrere Suchbedingungen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="7bc84-109">To establish the criteria for including a row in a result, you can use multiple search conditions.</span></span> <span data-ttu-id="7bc84-110">Das folgende Kriterium für die Suche besteht z. B. aus zwei Suchbedingungen.</span><span class="sxs-lookup"><span data-stu-id="7bc84-110">For example, the following search criterion consists of two search conditions.</span></span> <span data-ttu-id="7bc84-111">Die Abfrage nimmt eine Zeile nur dann in das Resultset auf, wenn sie beide Bedingungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="7bc84-111">The query includes a row in the result set only if that row satisfies both of the conditions.</span></span>  
  
```  
region = 'UK' AND product_line = 'Housewares'  
```  
  
 <span data-ttu-id="7bc84-112">Sie können Bedingungen durch AND oder OR kombinieren.</span><span class="sxs-lookup"><span data-stu-id="7bc84-112">You can combine these conditions with AND or OR.</span></span> <span data-ttu-id="7bc84-113">Im oben dargestellten Beispiel wird AND verwendet.</span><span class="sxs-lookup"><span data-stu-id="7bc84-113">The previous example uses AND.</span></span> <span data-ttu-id="7bc84-114">Im Gegensatz hierzu sind die Bedingungen im folgenden Beispiel durch ein OR kombiniert.</span><span class="sxs-lookup"><span data-stu-id="7bc84-114">In contrast, the following criterion uses OR.</span></span> <span data-ttu-id="7bc84-115">Das zurückgegebene Abfrageergebnis enthält alle Zeilen, die mindestens eine oder beide Suchbedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="7bc84-115">The result set will include any row that satisfies either or both of the search conditions:</span></span>  
  
```  
region = 'UK' OR product_line = 'Housewares'  
```  
  
 <span data-ttu-id="7bc84-116">Für eine Spalte können auch mehrere Suchbedingungen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="7bc84-116">You can even combine search conditions on a single column.</span></span> <span data-ttu-id="7bc84-117">Im folgenden Beispiel sind zwei Bedingungen für die Spalte Region kombiniert:</span><span class="sxs-lookup"><span data-stu-id="7bc84-117">For example, the following criterion combines two conditions on the region column:</span></span>  
  
```  
region = 'UK' OR region = 'US'  
```  
  
 <span data-ttu-id="7bc84-118">Ausführliche Informationen zum Kombinieren von Suchbedingungen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="7bc84-118">For details about combining search conditions, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7bc84-119">Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc84-119">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
  
-   [<span data-ttu-id="7bc84-120">Angeben mehrerer Suchbedingungen für eine Spalte &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc84-120">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
-   [<span data-ttu-id="7bc84-121">Angeben mehrerer Suchbedingungen für mehrere Spalten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc84-121">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
  
-   [<span data-ttu-id="7bc84-122">Kombinieren von Bedingungen, wenn AND Vorrang hat &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc84-122">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
  
-   [<span data-ttu-id="7bc84-123">Kombinieren von Bedingungen, wenn OR Vorrang hat &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc84-123">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
  
## <a name="examples"></a><span data-ttu-id="7bc84-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7bc84-124">Examples</span></span>  
 <span data-ttu-id="7bc84-125">Es folgen einige Beispiele für Abfragen mit verschiedenen Operatoren und Zeilenkriterien:</span><span class="sxs-lookup"><span data-stu-id="7bc84-125">Here are some examples of queries using various operators and row criteria:</span></span>  
  
-   <span data-ttu-id="7bc84-126">**Literalwert** : Ein einzelner numerischer oder logischer Wert, ein Textwert oder eine Datumsangabe.</span><span class="sxs-lookup"><span data-stu-id="7bc84-126">**Literal** A single text, numeric, date, or logical value.</span></span> <span data-ttu-id="7bc84-127">Im folgenden Beispiel wird ein Literalwert für die Suche nach allen Zeilen für Mitarbeiter in Großbritannien verwendet:</span><span class="sxs-lookup"><span data-stu-id="7bc84-127">The following example uses a literal to find all rows for employees in the United Kingdom:</span></span>  
  
    ```  
    WHERE region = 'UK'  
    ```  
  
-   <span data-ttu-id="7bc84-128">**Spaltenverweis** : Vergleicht die Werte einer Spalte mit den Werten einer anderen Spalte.</span><span class="sxs-lookup"><span data-stu-id="7bc84-128">**Column reference** Compares the values in one column with the values in another.</span></span> <span data-ttu-id="7bc84-129">Im folgenden Beispiel wird in der `products` -Tabelle nach allen Zeilen gesucht, in denen für die Produktionskosten ein kleinerer Wert als für die Frachtkosten angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="7bc84-129">The following example searches a `products` table for all rows in which the value of the production cost is lower than the shipping cost:</span></span>  
  
    ```  
    WHERE prod_cost < ship_cost  
    ```  
  
-   <span data-ttu-id="7bc84-130">**Funktion** : Ein Verweis auf eine Funktion, die vom Back-End der Datenbank aufgelöst werden kann, um einen Wert für die Suche zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="7bc84-130">**Function** A reference to a function that the database back-end can resolve to calculate a value for the search.</span></span> <span data-ttu-id="7bc84-131">Bei der Funktion kann es sich um eine durch den Datenbankserver definierte Funktion oder um eine benutzerdefinierte Funktion handeln, die einen Skalarwert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7bc84-131">The function can be a function defined by the database server or a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="7bc84-132">Im folgenden Beispiel wird nach allen am jeweiligen Tag erteilten Aufträgen gesucht (die GETDATE( )-Funktion liefert das aktuelle Datum):</span><span class="sxs-lookup"><span data-stu-id="7bc84-132">The following example searches for orders placed today (the GETDATE( ) function returns the current date):</span></span>  
  
    ```  
    WHERE order_date = GETDATE()  
    ```  
  
-   <span data-ttu-id="7bc84-133">**NULL** : Im folgenden Beispiel wird in einer Tabelle mit dem Namen `authors` nach allen Autoren gesucht, für die der Vorname in der Datenbank gespeichert wurde:</span><span class="sxs-lookup"><span data-stu-id="7bc84-133">**NULL** The following example searches an `authors` table for all authors who have a first name on file:</span></span>  
  
    ```  
    WHERE au_fname IS NOT NULL  
    ```  
  
-   <span data-ttu-id="7bc84-134">**Berechnung** : Das Ergebnis einer Berechnung, die Literalwerte, Spaltenverweise oder andere Ausdrücke enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7bc84-134">**Calculation** The result of a calculation that can involve literals, column references, or other expressions.</span></span> <span data-ttu-id="7bc84-135">Im folgenden Beispiel wird in einer Tabelle mit dem Namen `products` nach allen Zeilen gesucht, in denen der Einzelhandelspreis mindestens doppelt so hoch ist wie der Herstellungspreis:</span><span class="sxs-lookup"><span data-stu-id="7bc84-135">The following example searches a `products` table to find all rows in which the retail sales price is more than twice the production cost:</span></span>  
  
    ```  
    WHERE sales_price > (prod_cost * 2)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7bc84-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bc84-136">See Also</span></span>  
 <span data-ttu-id="7bc84-137">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7bc84-137">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7bc84-138">[Angeben von Suchkriterien &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7bc84-138">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7bc84-139">Erstellen von Abfragen mit Parametern &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc84-139">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
