---
title: Unterstützte Abfragetypen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Delete query
- queries [SQL Server], types
- Update query
- Query Designer [SQL Server], query types
- Criteria pane
- Insert Values query
- Select query
- Make Table query
- Insert Results query
- Diagram pane [Visual Database Tools]
- View Designer, query types
ms.assetid: 72b9116c-c128-4078-a78d-257a2955a3f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b00b7018fc6d0b631696811bd1870e09842b4162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720710"
---
# <a name="supported-query-types-visual-database-tools"></a><span data-ttu-id="22d20-102">Unterstützte Abfragetypen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="22d20-102">Supported Query Types (Visual Database Tools)</span></span>
  <span data-ttu-id="22d20-103">Sie können folgende Abfragetypen im Diagramm- oder Kriterienbereich (den grafischen Bereichen) des [Abfrage- und Sicht-Designers](visual-database-tools.md)erstellen:</span><span class="sxs-lookup"><span data-stu-id="22d20-103">You can create the following types of queries in the Diagram and Criteria panes (the graphical panes) of the [Query and View Designer](visual-database-tools.md):</span></span>  
  
-   <span data-ttu-id="22d20-104">**Auswahlabfrage** Ruft Daten aus einer oder mehreren Tabellen oder Sichten ab.</span><span class="sxs-lookup"><span data-stu-id="22d20-104">**Select query** Retrieves data from one or more tables or views.</span></span> <span data-ttu-id="22d20-105">Dieser Abfragetyp wird durch eine SELECT-Anweisung in SQL ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="22d20-105">This type of query creates an SQL SELECT statement.</span></span>  
  
-   <span data-ttu-id="22d20-106">**Ergebnisse einfügen** Erstellt neue Zeilen durch Kopieren vorhandener Zeilen als neue Zeilen aus einer Tabelle in eine andere oder in dieselbe Tabelle.</span><span class="sxs-lookup"><span data-stu-id="22d20-106">**Insert Results** Creates new rows by copying existing rows from one table into another, or into the same table as new rows.</span></span> <span data-ttu-id="22d20-107">Dieser Abfragetyp wird durch eine INSERT INTO...SELECT-Anweisung in SQL ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="22d20-107">This type of query creates an SQL INSERT INTO...SELECT statement.</span></span>  
  
-   <span data-ttu-id="22d20-108">**Werte einfügen** Erstellt eine neue Zeile und fügt Werte in die angegebenen Spalten ein.</span><span class="sxs-lookup"><span data-stu-id="22d20-108">**Insert Values** Creates a new row and inserts values into specified columns.</span></span> <span data-ttu-id="22d20-109">Dieser Abfragetyp wird durch eine INSERT INTO...VALUES-Anweisung in SQL ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="22d20-109">This type of query creates an SQL INSERT INTO...VALUES statement.</span></span>  
  
-   <span data-ttu-id="22d20-110">**Aktualisierungsabfrage** Ändert die Werte einzelner Spalten in einer oder mehreren vorhandenen Zeilen einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="22d20-110">**Update query** Changes the values of individual columns in one or more existing rows in a table.</span></span> <span data-ttu-id="22d20-111">Dieser Abfragetyp wird durch eine UPDATE…SET-Anweisung in SQL ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="22d20-111">This type of query creates an SQL UPDATE...SET statement.</span></span>  
  
-   <span data-ttu-id="22d20-112">**Löschabfrage** Entfernt eine oder mehrere Zeilen aus einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="22d20-112">**Delete query** Removes one or more rows from a table.</span></span> <span data-ttu-id="22d20-113">Dieser Abfragetyp wird durch eine DELETE-Anweisung in SQL ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="22d20-113">This type of query creates an SQL DELETE statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22d20-114">Bei einer Löschabfrage werden ganze Zeilen aus der Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="22d20-114">A Delete query removes entire rows from the table.</span></span> <span data-ttu-id="22d20-115">Wenn Sie Werte aus einzelnen Datenspalten löschen möchten, verwenden Sie eine UPDATE-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="22d20-115">If you want to delete values from individual data columns, use an Update query.</span></span>  
  
-   <span data-ttu-id="22d20-116">**Tabellenerstellungsabfrage** Erstellt eine neue Tabelle mit neuen Zeilen, indem die Ergebnisse einer Abfrage in die Tabelle kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="22d20-116">**Make Table query** Creates a new table and creates rows in it by copying the results of a query into it.</span></span> <span data-ttu-id="22d20-117">Dieser Abfragetyp wird durch eine SELECT...INTO-Anweisung in SQL ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="22d20-117">This type of query creates an SQL SELECT...INTO statement.</span></span>  
  
 <span data-ttu-id="22d20-118">Zusätzlich zu den in den grafischen Bereichen erstellten Abfragen können Sie jede SQL-Anweisung im SQL-Bereich eingeben, z. B. UNION-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="22d20-118">In addition to the queries you can create using the graphical panes, you can enter any SQL statement into the SQL pane, such as Union queries.</span></span>  
  
 <span data-ttu-id="22d20-119">Wenn Sie mithilfe von SQL-Anweisungen Abfragen erstellen, die nicht in den grafischen Bereichen dargestellt werden können, blendet der Abfrage- und Sicht-Designer diese Bereiche ab und zeigt damit an, dass in diesen Bereichen nicht die erstellte Abfrage wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="22d20-119">When you create queries using SQL statements that cannot be represented in the graphical panes, the Query and View Designer dims those panes to indicate that they do not reflect the query you are creating.</span></span> <span data-ttu-id="22d20-120">Die abgeblendeten Bereiche bleiben allerdings aktiv, und in vielen Fällen können Sie in diesen Bereichen Änderungen an der Abfrage vornehmen.</span><span class="sxs-lookup"><span data-stu-id="22d20-120">However, the dimmed panes are still active and, in many cases, you can make changes to the query in those panes.</span></span> <span data-ttu-id="22d20-121">Wenn sich aus den von Ihnen vorgenommenen Änderungen eine Abfrage ergibt, die in den grafischen Bereichen dargestellt werden kann, werden die Bereiche nicht länger abgeblendet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22d20-121">If the changes you make result in a query that can be represented in the graphical panes, those panes are no longer dimmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d20-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22d20-122">See Also</span></span>  
 <span data-ttu-id="22d20-123">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="22d20-123">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="22d20-124">Typen von Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="22d20-124">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
