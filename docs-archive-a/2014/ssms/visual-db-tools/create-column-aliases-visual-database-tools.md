---
title: Erstellen von Spaltenaliasen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: febe7ed27ed10a283cab549bc65299577d69761c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615750"
---
# <a name="create-column-aliases-visual-database-tools"></a><span data-ttu-id="4ad5c-102">Erstellen von Spaltenaliasen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4ad5c-102">Create Column Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="4ad5c-103">Zur Arbeitserleichterung können Sie Aliase für Spaltennamen, Berechnungen und zusammengefasste Werte erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-103">You can create aliases for column names to make it easier to work with column names, calculations, and summary values.</span></span> <span data-ttu-id="4ad5c-104">Beispielsweise können Sie einen Spaltenalias mit folgenden Funktionen erstellen:</span><span class="sxs-lookup"><span data-stu-id="4ad5c-104">For example, you can create a column alias to:</span></span>  
  
-   <span data-ttu-id="4ad5c-105">Erstellen eines Spaltennamens, z. B. "Total Amount" für einen Ausdruck wie `(quantity * unit_price)` oder für eine Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-105">Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.</span></span>  
  
-   <span data-ttu-id="4ad5c-106">Erstellen einer Kurzform für einen Spaltennamen, z. B. `"d_id"` für `"discounts.stor_id."`</span><span class="sxs-lookup"><span data-stu-id="4ad5c-106">Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`</span></span>  
  
 <span data-ttu-id="4ad5c-107">Wenn Sie einen Spaltenalias definiert haben, können Sie den Alias in einer SELECT-Abfrage zum Angeben der Ausgabe der Abfrageergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-107">After you have defined a column alias, you can use the alias in a Select query to specify query output.</span></span>  
  
### <a name="to-create-a-column-alias"></a><span data-ttu-id="4ad5c-108">So erstellen Sie einen Spaltenalias</span><span class="sxs-lookup"><span data-stu-id="4ad5c-108">To create a column alias</span></span>  
  
1.  <span data-ttu-id="4ad5c-109">Suchen Sie im Bereich **Kriterien**die Zeile mit der Datenspalte, für die Sie einen Alias erstellen möchten, und markieren Sie diese ggf. für die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-109">In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output.</span></span> <span data-ttu-id="4ad5c-110">Wenn die Datenspalte noch nicht im Datenblatt vorhanden ist, fügen Sie sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-110">If the data column is not already in the grid, add it.</span></span>  
  
2.  <span data-ttu-id="4ad5c-111">Geben Sie in der zu dieser Zeile gehörigen Spalte **Alias** den Alias ein.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-111">In the **Alias** column for that row, enter the alias.</span></span> <span data-ttu-id="4ad5c-112">Der Alias muss allen Namenskonventionen für SQL entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-112">The alias must follow all naming conventions for SQL.</span></span> <span data-ttu-id="4ad5c-113">Wenn der eingegebene Aliasname Leerzeichen enthält, wird er vom Abfrage- und Sicht-Designer automatisch in Trennzeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-113">If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad5c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ad5c-114">See Also</span></span>  
 <span data-ttu-id="4ad5c-115">[Hinzufügen von Spalten zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4ad5c-115">[Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="4ad5c-116">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4ad5c-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4ad5c-117">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4ad5c-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4ad5c-118">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4ad5c-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
