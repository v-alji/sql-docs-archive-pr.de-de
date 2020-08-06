---
title: Zusammenfassen von Abfrageergebnissen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08713be2d4439e520df07ec5efd6cb761a78a994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720719"
---
# <a name="summarize-query-results-visual-database-tools"></a><span data-ttu-id="c3488-102">Zusammenfassen von Abfrageergebnissen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c3488-102">Summarize Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="c3488-103">Wenn Sie Aggregatabfragen erstellen, folgen diese bestimmten logischen Prinzipien.</span><span class="sxs-lookup"><span data-stu-id="c3488-103">When you create aggregate queries, certain logical principles apply.</span></span> <span data-ttu-id="c3488-104">Beispielsweise können Sie keine Inhalte aus einzelnen Zeilen einer zusammenfassenden Abfrage anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="c3488-104">For example, you cannot display the contents of individual rows in a summary query.</span></span> <span data-ttu-id="c3488-105">Der Abfrage- und Sicht-Designer unterstützt Sie bei der Einhaltung dieser Prinzipien durch das Verhalten von [Diagrammbereich](visual-database-tools.md) und [Kriterienbereich](criteria-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="c3488-105">The Query and View Designer helps you comply with these principles in the way the [Diagram pane](visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.</span></span>  
  
 <span data-ttu-id="c3488-106">Wenn Sie sich mit den für Aggregatabfragen gültigen Prinzipien und dem Verhalten des Abfrage- und Sicht-Designers vertraut machen, hilft dies beim Entwurf logisch richtiger Aggregatabfragen.</span><span class="sxs-lookup"><span data-stu-id="c3488-106">By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries.</span></span> <span data-ttu-id="c3488-107">Als vorrangiges Prinzip ist zu beachten, dass Aggregatabfragen ausschließlich zusammenfassende Informationen liefern können.</span><span class="sxs-lookup"><span data-stu-id="c3488-107">The overriding principle is that aggregate queries can result only in summary information.</span></span> <span data-ttu-id="c3488-108">Ein Großteil der folgenden Prinzipien beschreibt daher die Methoden, mit denen Sie in einer Aggregatabfrage auf einzelne Datenspalten verweisen können.</span><span class="sxs-lookup"><span data-stu-id="c3488-108">Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3488-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c3488-109">In This Section</span></span>  
 [<span data-ttu-id="c3488-110">Verwenden von Spalten in Aggregatabfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3488-110">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
 <span data-ttu-id="c3488-111">Erläutert Konzepte zum Gruppieren und Zusammenfassen von Spalten mithilfe der Klauseln GROUP BY, WHERE und HAVING.</span><span class="sxs-lookup"><span data-stu-id="c3488-111">Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.</span></span>  
  
 [<span data-ttu-id="c3488-112">Zählen der Zeilen in einer Tabelle &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3488-112">Count Rows in a Table &#40;Visual Database Tools&#41;</span></span>](count-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="c3488-113">Erläutert schrittweise, wie Sie die Anzahl von Zeilen in einer Tabelle ermitteln, oder die Anzahl von Zeilen, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c3488-113">Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.</span></span>  
  
 [<span data-ttu-id="c3488-114">Wertzusammenfassung oder -aggregation für alle Zeilen in einer Tabelle &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3488-114">Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="c3488-115">Erläutert schrittweise, wie alle Zeilen zusammengefasst werden, anstatt einen Satz gruppierter Zeilen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3488-115">Provides steps for summarizing all rows rather than for a set of grouped rows.</span></span>  
  
 [<span data-ttu-id="c3488-116">Wertzusammenfassung oder -aggregation über benutzerdefinierte Ausdrücke &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3488-116">Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
 <span data-ttu-id="c3488-117">Erläutert schrittweise, wie Sie Zusammenfassungen oder Aggregate mithilfe von Ausdrücken anstelle mithilfe vordefinierter Klauseln erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c3488-117">Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c3488-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c3488-118">Related Sections</span></span>  
 [<span data-ttu-id="c3488-119">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3488-119">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="c3488-120">Stellt Links zu Themen bereit, die die Verwendung des Abfrage- und Sicht-Designers erläutern.</span><span class="sxs-lookup"><span data-stu-id="c3488-120">Provides links to topics covering how to use the Query and View Designer.</span></span>  
  
  
