---
title: Sortieren von Zeilen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4939c08a4be8c6a7aa3a52d55928abe077f25d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722141"
---
# <a name="sort-rows-visual-database-tools"></a><span data-ttu-id="6b5c5-102">Sortieren von Zeilen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6b5c5-102">Sort Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="6b5c5-103">Sie können die Zeilen in einem Abfrageergebnis sortieren.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-103">You can order the rows in a query result.</span></span> <span data-ttu-id="6b5c5-104">Das heißt, Sie können eine bestimmte Spalte oder eine Spaltengruppe angeben und die Zeilen im Resultset anhand der Werte in diesen Spalten neu ordnen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-104">That is, you can name a particular column or set of columns whose values determine the order of rows in the result set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b5c5-105">Die Sortierreihenfolge wird teilweise durch die Sortierreihenfolge der Spalte bestimmt.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-105">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="6b5c5-106">Sie können die Sortierreihenfolge im [Dialogfeld Sortierreihenfolge](visual-database-tools.md)ändern.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-106">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="6b5c5-107">Zum Sortieren der Abfrageergebnisse stehen Ihnen mehrere Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-107">There are several ways in which you can sort query results:</span></span>  
  
-   <span data-ttu-id="6b5c5-108">**Sie können Zeilen in auf- oder absteigender Reihenfolge sortieren.** Standardmäßig werden die ORDER BY-Spalten in SQL verwendet, um Zeilen in aufsteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-108">**You can arrange rows in ascending or descending order** By default, SQL uses order-by columns to arrange rows in ascending order.</span></span> <span data-ttu-id="6b5c5-109">Wenn Sie z. B. Buchtitel in aufsteigender Reihenfolge nach dem Preis ordnen möchten, sortieren Sie die Zeilen einfach nach der Preisspalte.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-109">For example, to arrange the book titles by ascending price, simply sort the rows by the price column.</span></span> <span data-ttu-id="6b5c5-110">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-110">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
  
    ```  
  
     <span data-ttu-id="6b5c5-111">Wenn Sie die Titel beginnend mit den teuersten Büchern ordnen möchten, können Sie dies für die Sortierreihenfolge explizit festlegen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-111">On the other hand, if you want to arrange the titles with the more expensive books first, you can explicitly specify a highest-first ordering.</span></span> <span data-ttu-id="6b5c5-112">Das heißt, Sie legen fest, dass die Ergebniszeilen nach absteigenden Werten in der Preisspalte sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-112">That is, you indicate that the result rows should be arranged by descending values of the price column.</span></span> <span data-ttu-id="6b5c5-113">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-113">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="6b5c5-114">**Sie können nach mehreren Spalten sortieren.** Sie können z. B. ein Resultset mit einer Zeile für jeden Autor erstellen und die Zeilen zunächst nach dem Land bzw. der Region und anschließend nach der Stadt sortieren.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-114">**You can sort by multiple columns** For example, you can create a result set with one row for each author, ordering first by state and then by city.</span></span> <span data-ttu-id="6b5c5-115">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-115">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
  
    ```  
  
-   <span data-ttu-id="6b5c5-116">**Sie können nach Spalten sortieren, die nicht im Resultset angezeigt werden.** Sie können z. B. ein Resultset erstellen, in dem die teuersten Titel zuerst aufgeführt werden, das jedoch keine Preisspalte enthält.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-116">**You can sort by columns not appearing in the result set** For example, you can create a result set with the most expensive titles first, even though the prices do not appear.</span></span> <span data-ttu-id="6b5c5-117">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-117">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="6b5c5-118">**Sie können nach abgeleiteten Spalten sortieren.** Sie können z.B. ein Resultset erstellen, in dem jede Zeile einen Buchtitel enthält und zuerst die Bücher aufgeführt werden, die die höchsten Tantiemen pro Exemplar erzielen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-118">**You can sort by derived columns** For example, you can create a result set in which each row contains a book title - with the books that pay the highest royalty per copy appearing first.</span></span> <span data-ttu-id="6b5c5-119">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-119">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
  
    ```  
  
     <span data-ttu-id="6b5c5-120">(Die Formel zur Berechnung der erzielten Tantiemen pro Buchexemplar ist hervorgehoben.)</span><span class="sxs-lookup"><span data-stu-id="6b5c5-120">(The formula for calculating the royalty that each book earns per copy is emphasized.)</span></span>  
  
     <span data-ttu-id="6b5c5-121">Zum Berechnen einer abgeleiteten Spalte können Sie wie im vorhergehenden Beispiel SQL-Syntax verwenden, Sie können aber auch eine benutzerdefinierte Funktion verwenden, die einen Skalarwert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-121">To calculate a derived column, you can use SQL syntax, as in the preceding example, or you can use a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="6b5c5-122">Weitere Informationen über benutzerdefinierte Funktionen finden Sie in der SQL Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-122">For more information about user-defined functions, see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="6b5c5-123">**Sie können gruppierte Zeilen sortieren.** Sie können z.B. ein Resultset erstellen, in dem jede Zeile eine Stadt sowie die Anzahl der in dieser Stadt lebenden Autoren enthält, wobei die Städte mit mehreren Autoren zuerst aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-123">**You can sort grouped rows** For example; you can create a result set in which each row describes a city, plus the number of authors in that city - with the cities containing many authors appearing first.</span></span> <span data-ttu-id="6b5c5-124">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-124">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
  
    ```  
  
     <span data-ttu-id="6b5c5-125">Beachten Sie, dass die Abfrage `state` als zweite Sortierspalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-125">Notice that the query uses `state` as a secondary sort column.</span></span> <span data-ttu-id="6b5c5-126">Wenn daher mehrere Länder/Regionen mit der gleichen Anzahl Autoren vorhanden sind, werden die Länder/Regionen in alphabetischer Reihenfolge aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-126">Thus, if two states have the same number of authors, those states will appear in alphabetical order.</span></span>  
  
-   <span data-ttu-id="6b5c5-127">**Sie können Daten nach internationalen Kriterien sortieren.** Das heißt, Sie können beim Sortieren einer Spalte Ordnungskonventionen zugrunde legen, die von den Standardkonventionen für diese Spalte abweichen.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-127">**You can sort using international data** That is; you can sort a column using collating conventions that differ from the default conventions for that column.</span></span> <span data-ttu-id="6b5c5-128">Beispielsweise können Sie eine Abfrage schreiben, die alle Buch Titel von Jaime pati abruft? '.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-128">For example, you can write a query that retrieves all the book titles by Jaime Pati??o.</span></span> <span data-ttu-id="6b5c5-129">Um die Titel in alphabetischer Reihenfolge anzuzeigen, verwenden Sie eine spanische Sortierreihenfolge für die Titelspalte.</span><span class="sxs-lookup"><span data-stu-id="6b5c5-129">To display the titles in alphabetical order, you use a Spanish collating sequence for the title column.</span></span> <span data-ttu-id="6b5c5-130">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="6b5c5-130">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Pati??o'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6b5c5-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b5c5-131">See Also</span></span>  
 <span data-ttu-id="6b5c5-132">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6b5c5-132">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6b5c5-133">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6b5c5-133">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
