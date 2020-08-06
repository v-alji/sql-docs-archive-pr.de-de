---
title: Entfernen von Joins (Visual Database Tools)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b037e317b629671f6ec5ea1fa90edfca6fafa627
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607477"
---
# <a name="remove-joins-visual-database-tools"></a><span data-ttu-id="02d06-102">Entfernen von Joins (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="02d06-102">Remove Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="02d06-103">Wenn Tabellen nicht über einen inneren oder äußeren Join miteinander verknüpft werden sollen, können Sie den Join zwischen diesen Tabellen entfernen.</span><span class="sxs-lookup"><span data-stu-id="02d06-103">If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them.</span></span> <span data-ttu-id="02d06-104">Sie können z. B. einen Join entfernen, die der [Abfrage- und Ansicht-Designer](visual-database-tools.md) automatisch zwischen zwei Tabellen erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="02d06-104">For example, you might remove a join that the [Query and View Designer](visual-database-tools.md) has been created automatically between two tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02d06-105">Durch das Entfernen eines Joins aus einer Abfrage wird die zugrunde liegende Beziehung in der Datenbank nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="02d06-105">Removing a join from a query does not alter the underlying relationship in the database.</span></span>  
  
 <span data-ttu-id="02d06-106">Wenn zwei verknüpfte Tabellen Teil der Abfrage sind und Sie alle Joinbedingungen zwischen diesen entfernen, entsteht die resultierende Abfrage als Produkt aus beiden Tabellen, d.h. sie wird als CROSS JOIN bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="02d06-106">If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.</span></span>  
  
### <a name="to-remove-a-join"></a><span data-ttu-id="02d06-107">So entfernen Sie einen Join</span><span class="sxs-lookup"><span data-stu-id="02d06-107">To remove a join</span></span>  
  
-   <span data-ttu-id="02d06-108">Markieren Sie im [Diagrammbereich](diagram-pane-visual-database-tools.md)die Joinlinie für den zu entfernenden Join, und drücken Sie anschließend die ENTF-TASTE.</span><span class="sxs-lookup"><span data-stu-id="02d06-108">In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key.</span></span> <span data-ttu-id="02d06-109">Sie können mehrere Joinlinien gleichzeitig markieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="02d06-109">You can select and delete multiple join lines at one time.</span></span>  
  
 <span data-ttu-id="02d06-110">Der Abfrage- und Sicht-Designer entfernt die Joinlinie und ändert die Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02d06-110">The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d06-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02d06-111">See Also</span></span>  
 <span data-ttu-id="02d06-112">[Automatisches Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="02d06-112">[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span></span>  
 <span data-ttu-id="02d06-113">[Manuelles Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="02d06-113">[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="02d06-114">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="02d06-114">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
