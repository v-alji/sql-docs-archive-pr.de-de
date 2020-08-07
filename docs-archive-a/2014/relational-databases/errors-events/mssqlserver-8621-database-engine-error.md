---
title: MSSQLSERVER_8621 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8621 (Database Engine error)
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48c36cf936475e3deea37a172c7dc59f88d0a31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619857"
---
# <a name="mssqlserver_8621"></a><span data-ttu-id="f41ae-102">MSSQLSERVER_8621</span><span class="sxs-lookup"><span data-stu-id="f41ae-102">MSSQLSERVER_8621</span></span>
    
## <a name="details"></a><span data-ttu-id="f41ae-103">Details</span><span class="sxs-lookup"><span data-stu-id="f41ae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f41ae-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f41ae-104">Product Name</span></span>|<span data-ttu-id="f41ae-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f41ae-105">SQL Server</span></span>|  
|<span data-ttu-id="f41ae-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f41ae-106">Event ID</span></span>|<span data-ttu-id="f41ae-107">8621</span><span class="sxs-lookup"><span data-stu-id="f41ae-107">8621</span></span>|  
|<span data-ttu-id="f41ae-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f41ae-108">Event Source</span></span>|<span data-ttu-id="f41ae-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f41ae-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f41ae-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f41ae-110">Component</span></span>|<span data-ttu-id="f41ae-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f41ae-111">SQLEngine</span></span>|  
|<span data-ttu-id="f41ae-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f41ae-112">Symbolic Name</span></span>|<span data-ttu-id="f41ae-113">OPTIMIZER_STACK_OVERFLOW_ERR</span><span class="sxs-lookup"><span data-stu-id="f41ae-113">OPTIMIZER_STACK_OVERFLOW_ERR</span></span>|  
|<span data-ttu-id="f41ae-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f41ae-114">Message Text</span></span>|<span data-ttu-id="f41ae-115">Der Abfrageprozessor hatte während der Abfrageoptimierung zu wenig Stapelspeicherplatz.</span><span class="sxs-lookup"><span data-stu-id="f41ae-115">The query processor ran out of stack space during query optimization.</span></span> <span data-ttu-id="f41ae-116">Vereinfachen Sie die Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f41ae-116">Please simplify the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f41ae-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f41ae-117">Explanation</span></span>  
 <span data-ttu-id="f41ae-118">Die Größe der erweiterten Abfrage ist die wahrscheinlichste Ursache für den Fehler.</span><span class="sxs-lookup"><span data-stu-id="f41ae-118">The size of the expanded query is the most likely cause of the error.</span></span> <span data-ttu-id="f41ae-119">Die erweiterte Abfrage ersetzt in der ursprünglichen Abfrage die Definitionen aller Ansichten, berechneten Spalten, [!INCLUDE[tsql](../../includes/tsql-md.md)]-Funktionen und allgemeinen Tabellenausdrücke, auf die sie verweist, sowie kaskadierende Aktionen wie das Aktualisieren von sekundären Indizes, Ansichten und Triggern.</span><span class="sxs-lookup"><span data-stu-id="f41ae-119">The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.</span></span>  
  
 <span data-ttu-id="f41ae-120">Höchstwahrscheinlich ist die Abfrage in einer Dimension groß, wie z. B. in der Anzahl der Tabellen, auf die von Sichtdefinitionen verwiesen wird, oder in einem sehr großen Skalarausdruck.</span><span class="sxs-lookup"><span data-stu-id="f41ae-120">Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f41ae-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f41ae-121">User Action</span></span>  
 <span data-ttu-id="f41ae-122">Vereinfachen Sie die Abfrage, indem Sie sie in mehrere Abfragen entlang der größten Dimension teilen.</span><span class="sxs-lookup"><span data-stu-id="f41ae-122">Simplify the query by breaking the query into multiple queries along the largest dimension.</span></span> <span data-ttu-id="f41ae-123">Entfernen Sie zuerst alle Abfrageelemente, die nicht wirklich erforderlich sind. Versuchen Sie dann, eine temporäre Tabelle hinzuzufügen und die Abfrage in zwei Teile zu teilen.</span><span class="sxs-lookup"><span data-stu-id="f41ae-123">First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.</span></span>  <span data-ttu-id="f41ae-124">Es genügt nicht, lediglich einen Teil der Abfrage in eine Unterabfrage, eine Funktion oder einen allgemeinen Tabellenausdruck zu verschieben, da diese durch den [!INCLUDE[tsql](../../includes/tsql-md.md)]-Compiler erneut kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="f41ae-124">Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.</span></span>  
  
  
