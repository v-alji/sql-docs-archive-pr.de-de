---
title: Erstellen von Unterabfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 540228839b9734992be008b5d4fb7d717176832e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618992"
---
# <a name="create-subqueries-visual-database-tools"></a><span data-ttu-id="88666-102">Erstellen von Unterabfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="88666-102">Create Subqueries (Visual Database Tools)</span></span>
  <span data-ttu-id="88666-103">Sie können die Ergebnisse einer Abfrage als Eingabe für eine andere Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="88666-103">You can use the results of one query as the input for another.</span></span> <span data-ttu-id="88666-104">Sie können die Ergebnisse einer Unterabfrage in einer Anweisung verwenden, die die IN( )-Funktion, den EXISTS-Operator oder die FROM-Klausel gebraucht.</span><span class="sxs-lookup"><span data-stu-id="88666-104">You can use the results of a subquery as a statement that uses the IN( ) function, the EXISTS operator, or the FROM clause.</span></span>  
  
 <span data-ttu-id="88666-105">Sie können eine Unterabfrage erstellen, indem Sie sie entweder direkt im SQL-Bereich eingeben oder indem Sie eine Abfrage kopieren und in eine andere einfügen.</span><span class="sxs-lookup"><span data-stu-id="88666-105">You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.</span></span>  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a><span data-ttu-id="88666-106">So definieren Sie eine Unterabfrage im SQL-Bereich</span><span class="sxs-lookup"><span data-stu-id="88666-106">To define a subquery in the SQL pane</span></span>  
  
1.  <span data-ttu-id="88666-107">Erstellen Sie die primäre Abfrage.</span><span class="sxs-lookup"><span data-stu-id="88666-107">Create the primary query.</span></span>  
  
2.  <span data-ttu-id="88666-108">Markieren Sie im SQL-Bereich die SQL-Anweisung, und kopieren Sie sie mit **Kopieren** in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="88666-108">In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="88666-109">Dann rufen Sie die neue Abfrage auf und fügen die erste Abfrage mit **Einfügen** in die WHERE- oder FROM-Klausel der neuen Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="88666-109">Start the new query, and then use **Paste** to move the first query into the new query's WHERE or FROM clause.</span></span>  
  
     <span data-ttu-id="88666-110">Angenommen, Sie haben zwei Tabellen, `products` und `suppliers`, und möchten eine Abfrage erstellen, in der alle Produkte von Lieferanten aus Schweden angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="88666-110">For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden.</span></span> <span data-ttu-id="88666-111">Dazu erstellen Sie die erste Abfrage anhand der Tabelle `suppliers` , um alle schwedischen Lieferanten zu herauszusuchen:</span><span class="sxs-lookup"><span data-stu-id="88666-111">Create the first query on the `suppliers` table to find all Swedish suppliers:</span></span>  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     <span data-ttu-id="88666-112">Kopieren Sie diese Abfrage mit dem Befehl Kopieren in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="88666-112">Use the Copy command to move this query to the Clipboard.</span></span> <span data-ttu-id="88666-113">Die zweite Abfrage erstellen Sie anhand der Tabelle `products` , in der die erforderlichen Produktinformationen aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="88666-113">Create the second query using the `products` table, listing the information you need about products:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     <span data-ttu-id="88666-114">Fügen Sie der zweiten Abfrage im SQL-Bereich eine WHERE-Klausel hinzu. Dann fügen Sie die erste Abfrage aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="88666-114">In the SQL pane, add a WHERE clause to the second query, then paste the first query from the Clipboard.</span></span> <span data-ttu-id="88666-115">Setzen Sie die erste Abfrage in Klammern, sodass das Endergebnis wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="88666-115">Place parentheses around the first query, so that the end result looks like this:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="88666-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88666-116">See Also</span></span>  
 <span data-ttu-id="88666-117">[Unterstützte Abfrage Typen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="88666-117">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="88666-118">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88666-118">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
