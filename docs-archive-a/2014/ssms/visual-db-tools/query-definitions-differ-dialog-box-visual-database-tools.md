---
title: Unterschiedliche Abfragedefinitionen (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69639
- vdtsql.chm:69640
- vdt.dlgbox.querydefinitionsdiffer
ms.assetid: 90383473-2922-40e5-9682-3850849aa856
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9a39d5d6b739fa4ab1a96ea95b513ecb7f6682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720767"
---
# <a name="query-definitions-differ-dialog-box-visual-database-tools"></a><span data-ttu-id="d2b36-102">Unterschiedliche Abfragedefinitionen (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d2b36-102">Query Definitions Differ Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="d2b36-103">In diesem Dialogfeld werden Sie darauf hingewiesen, dass die Abfrage in den Bereichen Diagramm und Kriterien grafisch nicht dargestellt und daher nur im SQL-Bereich bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d2b36-103">This dialog box notifies you that your query cannot be represented graphically in the Diagram and Criteria panes, and that you can edit your query only in the SQL pane.</span></span>  
  
 <span data-ttu-id="d2b36-104">Dieses Dialogfeld wird angezeigt, wenn Sie eine SQL-Anweisung im SQL-Bereich eingeben oder bearbeiten, dann zu einem anderen Bereich wechseln, die Abfrage überprüfen oder versuchen, sie auszuführen, und gleichzeitig eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d2b36-104">This dialog box may appear when you enter or edit an SQL statement in the SQL pane; you then move to another pane, verify the query, or attempt to execute the query; and one of the following conditions applies:</span></span>  
  
-   <span data-ttu-id="d2b36-105">Die SQL-Anweisung ist unvollständig oder enthält mindestens einen Syntaxfehler.</span><span class="sxs-lookup"><span data-stu-id="d2b36-105">The SQL statement is incomplete or contains one or more syntax errors.</span></span>  
  
-   <span data-ttu-id="d2b36-106">Die SQL-Anweisung ist gültig, wird aber von den grafischen Bereichen nicht unterstützt (z. B. eine Union-Abfrage).</span><span class="sxs-lookup"><span data-stu-id="d2b36-106">The SQL statement is valid but is not supported in the graphical panes (for example, a Union query).</span></span>  
  
-   <span data-ttu-id="d2b36-107">Die SQL-Anweisung ist gültig, enthält aber Syntax, die nur für die verwendete Datenverbindung gilt.</span><span class="sxs-lookup"><span data-stu-id="d2b36-107">The SQL statement is valid but contains syntax specific to the data connection you are using.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d2b36-108">Sie können die Gültigkeit einer Anweisung auf der Symbolleiste **Abfrage** mithilfe der Schaltfläche **Analysieren** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d2b36-108">You can check whether a statement is valid using the **Verify SQL Statement** button on the **Query** toolbar.</span></span>  
  
 <span data-ttu-id="d2b36-109">Das Dialogfeld zeigt eine Meldung mit dem Hinweis an, dass die SQL-Anweisung nicht dargestellt werden kann. Geben Sie an, wie Sie weiter vorgehen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2b36-109">The dialog box displays a message with the reason that the SQL statement cannot be represented, and then asks how you want to proceed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2b36-110">Das Dialogfeld **Unterschiedliche Abfragedefinitionen** wird nicht angezeigt, wenn die Bereiche „Diagramm“ und „Kriterien“ ausgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="d2b36-110">The **Query Definitions Differ** dialog box does not appear if you have hidden the Diagram and Criteria panes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2b36-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d2b36-111">Options</span></span>  
 <span data-ttu-id="d2b36-112">**Schaltfläche Ignorieren**</span><span class="sxs-lookup"><span data-stu-id="d2b36-112">**Ignore Button**</span></span>  
 <span data-ttu-id="d2b36-113">Mit dieser Schaltfläche können Sie die SQL-Anweisung übernehmen, um sie weiter zu bearbeiten oder auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d2b36-113">Choose this button to specify that you want to accept the SQL statement, either to edit it further or to execute it.</span></span> <span data-ttu-id="d2b36-114">Wenn Sie die Anweisung übernehmen, werden die Bereiche Diagramm und Kriterien abgeblendet, um anzuzeigen, dass die Anweisung im SQL-Bereich darin nicht dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2b36-114">If you accept the statement, the Diagram and Criteria panes appear dimmed to indicate that they do not represent the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="d2b36-115">**Schaltfläche Rückgängig**</span><span class="sxs-lookup"><span data-stu-id="d2b36-115">**Undo Button**</span></span>  
 <span data-ttu-id="d2b36-116">Mit dieser Schaltfläche können Sie die im SQL-Bereich vorgenommenen Änderungen verwerfen.</span><span class="sxs-lookup"><span data-stu-id="d2b36-116">Choose this button to discard your changes to the SQL pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2b36-117">Wenn die Anweisung richtig ist, aber vom Abfrage- und Sicht-Designer nicht grafisch unterstützt wird, können Sie sie ausführen, obwohl sie nicht in den Bereichen Diagramm und Kriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2b36-117">If the statement is correct but not supported graphically by the Query and View Designer, you can execute it even though it cannot be represented in the Diagram and Criteria panes.</span></span> <span data-ttu-id="d2b36-118">Wenn Sie beispielsweise eine Union-Abfrage eingeben, kann die Anweisung ausgeführt, aber nicht in den anderen Bereichen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d2b36-118">For example, if you enter a Union query, the statement can be executed but not represented in the other panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b36-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2b36-119">See Also</span></span>  
 [<span data-ttu-id="d2b36-120">Tools im Abfrage- und Sicht-Designer &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d2b36-120">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
