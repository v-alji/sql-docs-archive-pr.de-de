---
title: Automatisches Verknüpfen von Tabellen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- joins [SQL Server], creating
- joins [SQL Server], automatic
ms.assetid: f152af82-bcb6-49ca-af19-48cdb7fc9ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: d05100f801d972759c1b5c105814f5cdbdccf84f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695121"
---
# <a name="join-tables-automatically-visual-database-tools"></a><span data-ttu-id="0de13-102">Automatisches Verknüpfen von Tabellen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0de13-102">Join Tables Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="0de13-103">Wenn Sie einer Abfrage zwei oder mehr Tabellen hinzufügen, versucht der [Abfrage- und Sicht-Designer](visual-database-tools.md) zu ermitteln, ob diese verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="0de13-103">When you add two or more tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to determine if they are related.</span></span> <span data-ttu-id="0de13-104">Wenn dies der Fall ist, zieht der Abfrage- und Sicht-Designer automatisch Joinlinien zwischen den Rechtecken, die die Tabellen bzw. Objekte mit Tabellenstruktur darstellen.</span><span class="sxs-lookup"><span data-stu-id="0de13-104">If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.</span></span>  
  
 <span data-ttu-id="0de13-105">Der Abfrage- und Sicht-Designer erkennt Tabellen unter den folgenden Umständen als verknüpft:</span><span class="sxs-lookup"><span data-stu-id="0de13-105">The Query and View Designer will recognize tables as joined if:</span></span>  
  
-   <span data-ttu-id="0de13-106">Die Datenbank enthält Informationen, die angeben, dass die Tabellen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="0de13-106">The database contains information that specifies that the tables are related.</span></span>  
  
-   <span data-ttu-id="0de13-107">Wenn zwei Spalten aus jeweils einer Tabelle denselben Namen und denselben Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0de13-107">If two columns, one in each table, have the same name and data type.</span></span> <span data-ttu-id="0de13-108">Die Spalte muss in mindestens einer der Tabellen ein Primärschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="0de13-108">The column must be a primary key in at least one of the tables.</span></span> <span data-ttu-id="0de13-109">Wenn Sie z. B. die Tabellen `employee` und `jobs` hinzufügen, wobei die `job_id` -Spalte in der Tabelle `jobs` der Primärschlüssel ist und beide Tabellen eine `job_id` -Spalte mit demselben Datentyp enthalten, verknüpft der Abfrage- und Sicht-Designer die Tabellen automatisch.</span><span class="sxs-lookup"><span data-stu-id="0de13-109">For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer will automatically join the tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0de13-110">Der Abfrage- und Sicht-Designer erstellt für Spalten mit demselben Namen und demselben Datentyp nur einen Join.</span><span class="sxs-lookup"><span data-stu-id="0de13-110">The Query and View Designer will create only one join based on columns with the same name and data type.</span></span> <span data-ttu-id="0de13-111">Wenn mehrere Joins möglich sind, beendet der Abfrage- und Sicht-Designer den Vorgang nach dem Erstellen eines Joins, der auf dem ersten gefundenen Satz übereinstimmender Spalten basiert.</span><span class="sxs-lookup"><span data-stu-id="0de13-111">If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.</span></span>  
  
-   <span data-ttu-id="0de13-112">Der Abfrage- und Sicht-Designer erkennt, dass eine Suchbedingung (eine WHERE-Klausel) eigentlich eine Joinbedingung ist.</span><span class="sxs-lookup"><span data-stu-id="0de13-112">The Query and View Designer detects that a search condition (a WHERE clause) is actually a join condition.</span></span> <span data-ttu-id="0de13-113">Sie fügen z. B. die Tabellen `employee` und `jobs`hinzu und erstellen anschließend eine Suchbedingung, die in der `job_id` -Spalte beider Tabellen nach demselben Wert sucht.</span><span class="sxs-lookup"><span data-stu-id="0de13-113">For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables.</span></span> <span data-ttu-id="0de13-114">Wenn Sie diesen Vorgang ausführen, erkennt der Abfrage- und Sicht-Designer, dass die Suchbedingung zu einem Join führt und erstellt anschließend eine Joinbedingung auf der Grundlage der Suchbedingung.</span><span class="sxs-lookup"><span data-stu-id="0de13-114">When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.</span></span>  
  
 <span data-ttu-id="0de13-115">Wenn der Abfrage- und Sicht-Designer einen Join erstellt hat, der für die Abfrage nicht geeignet ist, können Sie den Join ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="0de13-115">If the Query and View Designer has created a join that is not suitable to your query, you can modify the join or remove it.</span></span> <span data-ttu-id="0de13-116">Ausführliche Informationen finden Sie unter [Ändern von Joinoperatoren &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) und [Entfernen von Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0de13-116">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) and [Remove Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="0de13-117">Wenn der Abfrage- und Sicht-Designer die Tabellen in der Abfrage nicht automatisch verknüpft, können Sie selbst einen Join erstellen.</span><span class="sxs-lookup"><span data-stu-id="0de13-117">If the Query and View Designer does not automatically join the tables in your query, you can create a join yourself.</span></span> <span data-ttu-id="0de13-118">Ausführliche Informationen finden Sie unter [Manuelles Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0de13-118">For details, see [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de13-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0de13-119">See Also</span></span>  
 <span data-ttu-id="0de13-120">[Wie der Abfrage-und Sicht-Designer Joins &#40;Visual Database Tools darstellt&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0de13-120">[How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0de13-121">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0de13-121">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0de13-122">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0de13-122">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
