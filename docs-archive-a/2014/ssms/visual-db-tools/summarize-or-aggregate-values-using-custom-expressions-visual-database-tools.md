---
title: Zusammenfassen oder Aggregieren von Werten mithilfe von benutzerdefinierten Ausdrücken (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9f03f82842178a68c8a3d04ebc1bd738c0ab0b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720722"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a><span data-ttu-id="86945-102">Wertzusammenfassung oder -aggregation über benutzerdefinierte Ausdrücke (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="86945-102">Summarize or Aggregate Values Using Custom Expressions (Visual Database Tools)</span></span>
  <span data-ttu-id="86945-103">Zusätzlich zu den Aggregatfunktionen zum Aggregieren von Daten können Sie benutzerdefinierte Ausdrücke zum Erstellen von Aggregatwerten verwenden.</span><span class="sxs-lookup"><span data-stu-id="86945-103">In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values.</span></span> <span data-ttu-id="86945-104">Außerdem können in allen Bereichen einer Aggregatabfrage benutzerdefinierte Ausdrücke an Stelle der Aggregatfunktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86945-104">You can use custom expressions in place of aggregate functions anywhere in an aggregate query.</span></span>  
  
 <span data-ttu-id="86945-105">In der Tabelle `titles` kann beispielsweise eine Abfrage erstellt werden, die nicht nur den Durchschnittspreis anzeigt, sondern auch angibt, welcher Durchschnittspreis sich unter Berücksichtigung von Preisnachlässen ergeben würde.</span><span class="sxs-lookup"><span data-stu-id="86945-105">For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.</span></span>  
  
 <span data-ttu-id="86945-106">Ausdrücke auf Grundlage von Berechnungen für einzelne Zeilen in der Tabelle können nicht in die Abfrage aufgenommen werden. Ein Ausdruck muss auf einem Aggregatwert beruhen, da während der Berechnung des Ausdrucks nur Aggregatwerte verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="86945-106">You cannot include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.</span></span>  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a><span data-ttu-id="86945-107">So geben Sie einen benutzerdefinierten Ausdruck für einen Zusammenfassungswert an</span><span class="sxs-lookup"><span data-stu-id="86945-107">To specify a custom expression for a summary value</span></span>  
  
1.  <span data-ttu-id="86945-108">Geben Sie die Gruppen für die Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="86945-108">Specify the groups for your query.</span></span> <span data-ttu-id="86945-109">Weitere Informationen finden Sie unter [Gruppieren von Zeilen in Abfrageergebnissen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="86945-109">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="86945-110">Setzen Sie den Cursor in eine leere Zeile im Kriterienbereich, und geben Sie dann den Ausdruck in die Spalte **Spalten** ein.</span><span class="sxs-lookup"><span data-stu-id="86945-110">Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.</span></span>  
  
     <span data-ttu-id="86945-111">Der [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) weist dem Ausdruck automatisch einen Spaltenalias zu, damit im Abfrageergebnis eine aussagekräftige Spaltenüberschrift erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="86945-111">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output.</span></span> <span data-ttu-id="86945-112">Weitere Informationen finden Sie unter [Erstellen von Spaltenaliasen &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="86945-112">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
3.  <span data-ttu-id="86945-113">Wählen Sie in der Spalte **Gruppieren nach** für den jeweiligen Ausdruck die Option **Ausdruck** aus.</span><span class="sxs-lookup"><span data-stu-id="86945-113">In the **Group By** column for the expression, select **Expression**.</span></span>  
  
4.  <span data-ttu-id="86945-114">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="86945-114">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86945-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86945-115">See Also</span></span>  
 <span data-ttu-id="86945-116">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="86945-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="86945-117">Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="86945-117">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
