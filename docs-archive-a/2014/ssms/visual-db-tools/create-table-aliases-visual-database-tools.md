---
title: Erstellen von Tabellenaliasen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f9e6269fe6e24e8d98922094e799fbf4b5af584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618991"
---
# <a name="create-table-aliases-visual-database-tools"></a><span data-ttu-id="3e89f-102">Erstellen von Tabellenaliasen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3e89f-102">Create Table Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="3e89f-103">Aliase können das Arbeiten mit Tabellennamen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="3e89f-103">Aliases can make it easier to work with table names.</span></span> <span data-ttu-id="3e89f-104">Das Verwenden von Aliasen ist in folgenden Fällen hilfreich:</span><span class="sxs-lookup"><span data-stu-id="3e89f-104">Using aliases is helpful when:</span></span>  
  
-   <span data-ttu-id="3e89f-105">Sie möchten die Anweisung im [SQL-Bereich](visual-database-tools.md) kürzen und lesbarer machen.</span><span class="sxs-lookup"><span data-stu-id="3e89f-105">You want to make the statement in the [SQL Pane](visual-database-tools.md) shorter and easier to read.</span></span>  
  
-   <span data-ttu-id="3e89f-106">Sie verweisen in der Abfrage häufig auf den Tabellennamen, z.B. in qualifizierenden Spaltennamen, und möchten sicherstellen, dass in der Abfrage eine bestimmte Anzahl von Zeichen nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="3e89f-106">You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query.</span></span> <span data-ttu-id="3e89f-107">(In einigen Datenbanken ist eine maximale Länge für Abfragen festgelegt.)</span><span class="sxs-lookup"><span data-stu-id="3e89f-107">(Some databases impose a maximum length for queries.)</span></span>  
  
-   <span data-ttu-id="3e89f-108">Sie verwenden mehrere Instanzen derselben Tabelle (z. B. in einem Selbstjoin) und suchen nach einer Möglichkeit, um auf die eine oder andere Instanz zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3e89f-108">You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.</span></span>  
  
 <span data-ttu-id="3e89f-109">Sie können z. B. einen Alias `"e"` für einen Tabellennamen `employee`_`information`erstellen und in der restlichen Abfrage mit `"e"` auf die Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="3e89f-109">For example, you can create an alias `"e"` for a table name `employee`_`information`, and then refer to the table as `"e"` throughout the rest of the query.</span></span>  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a><span data-ttu-id="3e89f-110">So erstellen Sie einen Alias für eine Tabelle oder ein Tabellenwertobjekt</span><span class="sxs-lookup"><span data-stu-id="3e89f-110">To create an alias for a table or table-valued object</span></span>  
  
1.  <span data-ttu-id="3e89f-111">Fügen Sie der Abfrage die Tabelle oder das Tabellenwertobjekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="3e89f-111">Add the table or table-valued object to your query.</span></span>  
  
2.  <span data-ttu-id="3e89f-112">Klicken Sie im **Diagrammbereich**mit der rechten Maustaste auf das Objekt, für das Sie einen Alias erstellen möchten, und wählen Sie anschließend im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="3e89f-112">In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="3e89f-113">Geben Sie im **Eigenschaftenfenster** den Alias in das Feld **Alias** ein.</span><span class="sxs-lookup"><span data-stu-id="3e89f-113">In the **Properties** window, enter the alias in the **Alias** field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e89f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e89f-114">See Also</span></span>  
 <span data-ttu-id="3e89f-115">[Hinzufügen von Tabellen zu Abfragen &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3e89f-115">[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="3e89f-116">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3e89f-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="3e89f-117">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3e89f-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3e89f-118">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3e89f-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
