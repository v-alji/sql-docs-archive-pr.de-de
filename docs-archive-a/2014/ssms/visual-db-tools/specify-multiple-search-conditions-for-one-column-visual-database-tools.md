---
title: Angeben mehrerer Suchbedingungen für eine Spalte (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a07322120bd3b3f543e6f54fa50cdf75aa32be59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617353"
---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a><span data-ttu-id="0a04f-102">Angeben mehrerer Suchbedingungen für eine Spalte (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0a04f-102">Specify Multiple Search Conditions for One Column (Visual Database Tools)</span></span>
  <span data-ttu-id="0a04f-103">In manchen Fällen kann es sinnvoll sein, mehrere Suchkriterien auf dieselbe Datenspalte anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0a04f-103">In some instances, you might want to apply a number of search conditions to the same data column.</span></span> <span data-ttu-id="0a04f-104">Auf diese Weise können Sie beispielsweise folgende Vorgänge durchführen:</span><span class="sxs-lookup"><span data-stu-id="0a04f-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="0a04f-105">Sie können in der Tabelle `employee` nach mehreren verschiedenen Namen oder nach Mitarbeitern in verschiedenen Gehaltsgruppen suchen.</span><span class="sxs-lookup"><span data-stu-id="0a04f-105">Search for several different names in an `employee` table or for employees who are in different salary ranges.</span></span> <span data-ttu-id="0a04f-106">Diese Art von Suche erfordert die Verwendung einer OR-Bedingung.</span><span class="sxs-lookup"><span data-stu-id="0a04f-106">This type of search requires an OR condition.</span></span>  
  
-   <span data-ttu-id="0a04f-107">Sie können nach einem Buchtitel suchen, der mit dem Wort "Der" beginnt und das Wort "Koch" enthält.</span><span class="sxs-lookup"><span data-stu-id="0a04f-107">Search for a book title that both starts with the word "The" and contains the word "Cook."</span></span> <span data-ttu-id="0a04f-108">Diese Art von Suche erfordert die Verwendung einer AND-Bedingung.</span><span class="sxs-lookup"><span data-stu-id="0a04f-108">This type of search requires an AND condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a04f-109">Die Angaben zu diesem Thema beziehen sich auf Suchbedingungen in WHERE- und HAVING-Klauseln einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="0a04f-109">The information in this topic applies to search conditions in both the WHERE and HAVING clauses of a query.</span></span> <span data-ttu-id="0a04f-110">Die Beispiele behandeln vorrangig die Erstellung von WHERE-Klauseln, aber die Regeln sind auf beide Arten von Suchbedingungen anwendbar.</span><span class="sxs-lookup"><span data-stu-id="0a04f-110">The examples focus on creating WHERE clauses, but the principles apply to both types of search conditions.</span></span>  
  
 <span data-ttu-id="0a04f-111">Zum Suchen nach verschiedenen Werten in derselben Datenspalte wird eine OR-Bedingung eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="0a04f-111">To search for alternative values in the same data column, you specify an OR condition.</span></span> <span data-ttu-id="0a04f-112">Für die Suche nach Werten, die mehrere Bedingungen erfüllen, wird eine AND-Bedingung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0a04f-112">To search for values that meet several conditions, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="0a04f-113">Angeben einer OR-Bedingung</span><span class="sxs-lookup"><span data-stu-id="0a04f-113">Specifying an OR Condition</span></span>  
 <span data-ttu-id="0a04f-114">Mit einer OR-Bedingung können Sie mehrere verschiedene Werte angeben, nach denen in einer Spalte gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a04f-114">Using an OR condition enables you to specify several alternative values to search for in a column.</span></span> <span data-ttu-id="0a04f-115">Diese Möglichkeit erweitert den Bereich der Suche, und es werden unter Umständen mehr Zeilen als bei der Angabe eines einzelnen Werts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0a04f-115">This option expands the scope of the search and can return more rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="0a04f-116">Wenn Sie nach mehreren Werten in derselben Spalte suchen, können Sie häufig auch den Operator IN verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a04f-116">You can often use the IN operator instead to search for multiple values in the same data column.</span></span>  
  
#### <a name="to-specify-an-or-condition"></a><span data-ttu-id="0a04f-117">So geben Sie eine OR-Bedingung an</span><span class="sxs-lookup"><span data-stu-id="0a04f-117">To specify an OR condition</span></span>  
  
1.  <span data-ttu-id="0a04f-118">Fügen Sie dem [Kriterienbereich](visual-database-tools.md)die Spalte für die Suche hinzu.</span><span class="sxs-lookup"><span data-stu-id="0a04f-118">In the [Criteria Pane](visual-database-tools.md), add the column to search.</span></span>  
  
2.  <span data-ttu-id="0a04f-119">Geben Sie in der Spalte **Filter** für die soeben hinzugefügte Datenspalte die erste Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="0a04f-119">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="0a04f-120">Geben Sie in der Spalte **Oder...** für dieselbe Datenspalte die zweite Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="0a04f-120">In the **Or...** column for the same data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="0a04f-121">Der Abfrage- und Sicht-Designer erstellt eine WHERE-Klausel mit einer OR-Bedingung, z. B.:</span><span class="sxs-lookup"><span data-stu-id="0a04f-121">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="0a04f-122">Angeben einer AND-Bedingung</span><span class="sxs-lookup"><span data-stu-id="0a04f-122">Specifying an AND Condition</span></span>  
 <span data-ttu-id="0a04f-123">Mit einer AND-Bedingung können Sie angeben, dass die Werte in einer Spalte zwei oder mehr Bedingungen erfüllen müssen, damit die entsprechende Zeile in das Resultset aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="0a04f-123">Using an AND condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set.</span></span> <span data-ttu-id="0a04f-124">Diese Möglichkeit schränkt den Bereich der Suche ein, sodass normalerweise weniger Zeilen als bei der Suche nach einem einzigen Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0a04f-124">This option narrows the scope of the search and usually returns fewer rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="0a04f-125">Wenn Sie nach einem Wertebereich suchen, können Sie den Operator BETWEEN verwenden, anstatt zwei Bedingungen mit AND zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0a04f-125">If you are searching for a range of values, you can use the BETWEEN operator instead of linking two conditions with AND.</span></span>  
  
#### <a name="to-specify-an-and-condition"></a><span data-ttu-id="0a04f-126">So geben Sie eine AND-Bedingung an</span><span class="sxs-lookup"><span data-stu-id="0a04f-126">To specify an AND condition</span></span>  
  
1.  <span data-ttu-id="0a04f-127">Fügen Sie dem Kriterienbereich die Spalte für die Suche hinzu.</span><span class="sxs-lookup"><span data-stu-id="0a04f-127">In the Criteria pane, add the column to search.</span></span>  
  
2.  <span data-ttu-id="0a04f-128">Geben Sie in der Spalte **Filter** für die soeben hinzugefügte Datenspalte die erste Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="0a04f-128">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="0a04f-129">Fügen Sie dem Kriterienbereich noch einmal dieselbe Datenspalte hinzu, und platzieren Sie diese in einer leeren Zeile des Datenblatts.</span><span class="sxs-lookup"><span data-stu-id="0a04f-129">Add the same data column to the Criteria pane again, placing it in an empty row of the grid.</span></span>  
  
4.  <span data-ttu-id="0a04f-130">Geben Sie in der Spalte **Filter** für die zweite Instanz der Datenspalte die zweite Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="0a04f-130">In the **Filter** column for the second instance of the data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="0a04f-131">Der Abfrage-Designer erstellt eine WHERE-Klausel mit einer AND-Bedingung, z. B.:</span><span class="sxs-lookup"><span data-stu-id="0a04f-131">The Query Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a04f-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a04f-132">See Also</span></span>  
 <span data-ttu-id="0a04f-133">[Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0a04f-133">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="0a04f-134">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0a04f-134">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
