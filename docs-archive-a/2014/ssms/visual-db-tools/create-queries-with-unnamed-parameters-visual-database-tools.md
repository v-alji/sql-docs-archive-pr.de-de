---
title: Erstellen von Abfragen mit unbenannten Parametern (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0ea53afd1fa4d44390f5805d6b28494428608b90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608200"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a><span data-ttu-id="87e7c-102">Erstellen von Abfragen mit unbenannten Parametern (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="87e7c-102">Create Queries with Unnamed Parameters (Visual Database Tools)</span></span>
  <span data-ttu-id="87e7c-103">Sie können eine Abfrage mit einem unbenannten Parameter erstellen, indem Sie ein Fragezeichen (?) als Platzhalter für den Literalwert angeben.</span><span class="sxs-lookup"><span data-stu-id="87e7c-103">You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value.</span></span> <span data-ttu-id="87e7c-104">Der Abfrage- und Sicht-Designer weist dann einen temporären Namen zu.</span><span class="sxs-lookup"><span data-stu-id="87e7c-104">Query and View Designer will give it a temporary name.</span></span> <span data-ttu-id="87e7c-105">In der Abfrage können beliebig viele unbenannte Parameter festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="87e7c-105">You can specify as many unnamed parameters in the query as you need.</span></span>  
  
 <span data-ttu-id="87e7c-106">Wenn Sie die Abfrage im Abfrage- und Sicht-Designer ausführen, wird das Dialogfeld Abfrageparameter mit dem temporären Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87e7c-106">When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.</span></span>  
  
### <a name="to-specify-an-unnamed-parameter"></a><span data-ttu-id="87e7c-107">So geben Sie einen unbenannten Parameter an</span><span class="sxs-lookup"><span data-stu-id="87e7c-107">To specify an unnamed parameter</span></span>  
  
1.  <span data-ttu-id="87e7c-108">Fügen Sie dem [Kriterienbereich](visual-database-tools.md)die Spalten oder Ausdrücke hinzu, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="87e7c-108">Add the columns or expressions that you want to search to the [Criteria pane](visual-database-tools.md).</span></span> <span data-ttu-id="87e7c-109">Wenn in den Abfrageergebnissen keine Suchspalten bzw. Suchausdrücke angezeigt werden sollen, entfernen Sie die entsprechenden Ausgabespalten.</span><span class="sxs-lookup"><span data-stu-id="87e7c-109">If you do not want the search columns or expressions to appear in the query output, remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="87e7c-110">Wechseln Sie zu der Zeile, die die Datenspalte oder den Ausdruck für die Suche enthält, und geben Sie in der Datenblattspalte **Filter** ein Fragezeichen (?) ein.</span><span class="sxs-lookup"><span data-stu-id="87e7c-110">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).</span></span>  
  
     <span data-ttu-id="87e7c-111">Der Abfrage- und Sicht-Designer fügt standardmäßig den Operator "=" hinzu.</span><span class="sxs-lookup"><span data-stu-id="87e7c-111">By default, the Query and View Designer adds the "=" operator.</span></span> <span data-ttu-id="87e7c-112">Sie können die Zelle jedoch so bearbeiten, dass dafür ">", "<" oder ein beliebiger anderer SQL-Vergleichsoperator eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="87e7c-112">However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e7c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87e7c-113">See Also</span></span>  
 [<span data-ttu-id="87e7c-114">Erstellen von Abfragen mit Parametern &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="87e7c-114">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
