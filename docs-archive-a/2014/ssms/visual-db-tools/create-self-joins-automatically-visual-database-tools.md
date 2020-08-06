---
title: Automatisches Erstellen von Selbstverknüpfungen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a428a44d33b5990e849772b43841df472ca7f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608199"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a><span data-ttu-id="ccf2a-102">Automatisches Erstellen von Selbstjoins (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ccf2a-102">Create Self-Joins Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="ccf2a-103">Wenn die Tabelle über eine reflexive Beziehung in der Datenbank verfügt, können Sie diese automatisch mit sich selbst verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ccf2a-103">If a table has a reflexive relationship in the database, you can join it to itself automatically.</span></span>  
  
### <a name="to-create-a-self-join-automatically"></a><span data-ttu-id="ccf2a-104">So erstellen Sie automatisch einen Selbstjoin</span><span class="sxs-lookup"><span data-stu-id="ccf2a-104">To create a self-join automatically</span></span>  
  
1.  <span data-ttu-id="ccf2a-105">Fügen Sie dem [Diagrammbereich](visual-database-tools.md) die Tabelle hinzu, mit der Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ccf2a-105">Add to the [Diagram pane](visual-database-tools.md) the table you want to work with.</span></span>  
  
2.  <span data-ttu-id="ccf2a-106">Fügen Sie dieselbe Tabelle erneut hinzu, sodass die Tabelle im Diagrammbereich zweimal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ccf2a-106">Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="ccf2a-107">Der [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) weist der zweiten Instanz einen Alias zu, indem er dem Tabellennamen eine laufende Nummer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="ccf2a-107">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="ccf2a-108">Außerdem erstellt der Abfrage- und Sicht-Designer eine Joinlinie zwischen den zwei Rechtecken, die die zwei verschiedenen Beteiligungsarten der Tabelle an der Abfrage darstellen.</span><span class="sxs-lookup"><span data-stu-id="ccf2a-108">In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf2a-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccf2a-109">See Also</span></span>  
 [<span data-ttu-id="ccf2a-110">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ccf2a-110">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
