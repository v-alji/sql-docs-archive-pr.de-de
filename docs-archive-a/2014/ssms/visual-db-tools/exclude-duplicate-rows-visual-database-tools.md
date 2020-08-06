---
title: Ausschließen doppelter Zeilen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b396f2738f6895684d828884d4822ea9165e0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621798"
---
# <a name="exclude-duplicate-rows-visual-database-tools"></a><span data-ttu-id="be8fc-102">Ausschließen doppelter Zeilen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="be8fc-102">Exclude Duplicate Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="be8fc-103">Wenn in einem Resultset nur eindeutige Werte angezeigt werden sollen, können Sie das Ausschließen von Duplikaten aus dem Resultset angeben.</span><span class="sxs-lookup"><span data-stu-id="be8fc-103">If you want to see only unique values in a result set, you can specify that you want to exclude duplicates from the result set.</span></span>  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a><span data-ttu-id="be8fc-104">So schließen Sie doppelte Zeilen aus dem Resultset aus</span><span class="sxs-lookup"><span data-stu-id="be8fc-104">To exclude duplicate rows from the result set</span></span>  
  
1.  <span data-ttu-id="be8fc-105">Klicken Sie mit der rechten Maustaste auf den Hintergrund des Diagrammbereichs, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="be8fc-105">Right-click the background of the Diagram pane, then choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="be8fc-106">Klicken Sie im Eigenschaftenfenster auf **DISTINCT-Werte** , und legen Sie als Wert **Ja**fest.</span><span class="sxs-lookup"><span data-stu-id="be8fc-106">In the Property window, click **Distinct values** and set the value to **Yes**.</span></span>  
  
     <span data-ttu-id="be8fc-107">Der Abfrage- und Sicht-Designer fügt das Schlüsselwort DISTINCT vor der Liste der Anzeigespalten in der SQL-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="be8fc-107">The Query and View Designer inserts the keyword DISTINCT in front of the list of display columns in the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="be8fc-108">Wenn Sie das Schlüsselwort DISTINCT verwenden, können Sie möglicherweise die Ergebnisse im Ergebnisbereich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="be8fc-108">If you use the DISTINCT keyword you may not be able to modify the result set in the results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8fc-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be8fc-109">See Also</span></span>  
 <span data-ttu-id="be8fc-110">[Angeben von Suchkriterien &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="be8fc-110">[Specify Search Criteria &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="be8fc-111">Sortieren und Gruppieren von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="be8fc-111">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
