---
title: Erstellen von UNION-Abfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618990"
---
# <a name="create-union-queries-visual-database-tools"></a><span data-ttu-id="a632a-102">Erstellen von UNION-Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a632a-102">Create UNION Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="a632a-103">Mit dem Schlüsselwort UNION können Sie die Ergebnisse von zwei SELECT-Anweisungen in eine Ergebnistabelle aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="a632a-103">The UNION keyword enables you to include the results of two SELECT statements in one resulting table.</span></span> <span data-ttu-id="a632a-104">Alle Zeilen, die von den beiden SELECT-Anweisungen zurückgegeben werden, werden zum Ergebnis des UNION-Ausdrucks kombiniert.</span><span class="sxs-lookup"><span data-stu-id="a632a-104">All rows returned from either SELECT statement are combined into the result of the UNION expression.</span></span> <span data-ttu-id="a632a-105">Beispiele finden Sie unter [Auswählen von Beispielen &#40;Transact-SQL-&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a632a-105">For examples, see [SELECT Examples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a632a-106">Im Diagrammbereich kann nur eine SELECT-Klausel angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a632a-106">The Diagram pane can only display one SELECT clause.</span></span> <span data-ttu-id="a632a-107">Wenn Sie eine UNION-Abfrage verwenden, wird der Bereich Tabellenvorgänge Abfrage-Designer daher nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a632a-107">Therefore, when you are working with a UNION query, Query Designer hides the Table Operations pane.</span></span>  
  
### <a name="to-create-a-merged-select-query"></a><span data-ttu-id="a632a-108">So erstellen Sie eine zusammengeführte SELECT-Abfrage</span><span class="sxs-lookup"><span data-stu-id="a632a-108">To create a Merged SELECT query</span></span>  
  
1.  <span data-ttu-id="a632a-109">Öffnen Sie eine Abfrage, oder erstellen Sie eine neue.</span><span class="sxs-lookup"><span data-stu-id="a632a-109">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="a632a-110">Geben Sie im Bereich SQL einen gültigen UNION-Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="a632a-110">In the SQL pane, type a valid UNION expression.</span></span>  
  
     <span data-ttu-id="a632a-111">Das folgende Beispiel stellt einen gültigen UNION-Ausdruck dar.</span><span class="sxs-lookup"><span data-stu-id="a632a-111">The following example is a valid UNION expression.</span></span>  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  <span data-ttu-id="a632a-112">Klicken Sie im Menü **Abfrage-Designer** auf **SQL ausführen** , um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a632a-112">On the **Query Designer** menu, click **Execute SQL** to run the query.</span></span>  
  
     <span data-ttu-id="a632a-113">Die UNION-Abfrage wird jetzt vom Abfrage-Designer formatiert.</span><span class="sxs-lookup"><span data-stu-id="a632a-113">Your UNION query is now formatted by Query Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a632a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a632a-114">See Also</span></span>  
 <span data-ttu-id="a632a-115">[Unterstützte Abfrage Typen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a632a-115">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="a632a-116">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a632a-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a632a-117">[Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a632a-117">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a632a-118">UNION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a632a-118">UNION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
