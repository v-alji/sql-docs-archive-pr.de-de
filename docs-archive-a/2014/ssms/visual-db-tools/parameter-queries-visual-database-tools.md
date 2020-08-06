---
title: Parameterabfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- parameter queries [SQL Server]
ms.assetid: 4897c41a-324a-47b8-a30b-cbc9e9e19a8b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f6fd94ef180a34ae91d52c213092898612dc77d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619494"
---
# <a name="parameter-queries-visual-database-tools"></a><span data-ttu-id="e82eb-102">Parameterabfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e82eb-102">Parameter Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="e82eb-103">Für bestimmte Aufgaben werden Abfragen benötigt, die bei sich wiederholenden Aufrufen die Übergabe eines wechselnden Werts ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e82eb-103">In some cases you want to create a query that you can use many times, but with a different value each time.</span></span> <span data-ttu-id="e82eb-104">Angenommen, Sie führen des Öfteren eine Abfrage aus, mit der alle `title_ids` eines Autors abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e82eb-104">For example, you might frequently run a query to find all the `title_ids` written by one author.</span></span> <span data-ttu-id="e82eb-105">In diesem Fall führen Sie für jede Anforderung dieselbe Abfrage aus, wobei jedoch die ID bzw. der Name des Autors jeweils unterschiedlich ist.</span><span class="sxs-lookup"><span data-stu-id="e82eb-105">You could run the same query for each request, except that the author's ID or name would be different each time.</span></span>  
  
 <span data-ttu-id="e82eb-106">Zum Erstellen einer Abfrage, die bei jedem Aufruf mit unterschiedlichen Werten ausgeführt werden kann, verwenden Sie Parameter innerhalb der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="e82eb-106">To create a query that can have different values at different times, you use parameters in the query.</span></span> <span data-ttu-id="e82eb-107">Ein Parameter ist ein Platzhalter für einen Wert, der erst beim Ausführen der Abfrage festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e82eb-107">A parameter is a placeholder for a value that is supplied when the query runs.</span></span> <span data-ttu-id="e82eb-108">Eine SQL-Anweisung mit einem Parameter könnte folgendermaßen lauten, wobei "?" als Parameter für die ID des Autors dient:</span><span class="sxs-lookup"><span data-stu-id="e82eb-108">An SQL statement with a parameter might look like the following, where "?" represents the parameter for the author's ID:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
## <a name="where-you-can-use-parameters"></a><span data-ttu-id="e82eb-109">Verwendungsmöglichkeit von Parametern</span><span class="sxs-lookup"><span data-stu-id="e82eb-109">Where You Can Use Parameters</span></span>  
 <span data-ttu-id="e82eb-110">Sie können Parameter als Platzhalter für Literalwerte verwenden, d.h. sowohl für Textwerte als auch für numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="e82eb-110">You can use parameters as placeholders for literal values - for either text or numeric values.</span></span> <span data-ttu-id="e82eb-111">Sehr häufig werden Parameter als Platzhalter in Suchbedingungen für einzelne Zeilen oder Zeilengruppen verwendet (also in den WHERE- oder HAVING-Klauseln einer SQL-Anweisung).</span><span class="sxs-lookup"><span data-stu-id="e82eb-111">Most commonly, parameters are used as placeholders in search conditions for individual rows or for groups (that is, in the WHERE or HAVING clauses of an SQL statement).</span></span>  
  
 <span data-ttu-id="e82eb-112">Sie können Parameter als Platzhalter in Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="e82eb-112">You can use parameters as placeholders in expressions.</span></span> <span data-ttu-id="e82eb-113">Angenommen, Sie möchten Rabattpreise berechnen und bei jedem Ausführen der Abfrage einen anderen Rabattwert angeben können.</span><span class="sxs-lookup"><span data-stu-id="e82eb-113">For example, you might want to calculate discounted prices by supplying a different discount value each time you run a query.</span></span> <span data-ttu-id="e82eb-114">Hierzu lässt sich folgender Ausdruck verwenden:</span><span class="sxs-lookup"><span data-stu-id="e82eb-114">To do so, you could specify the following expression:</span></span>  
  
```  
(price * ?)  
```  
  
## <a name="specifying-unnamed-and-named-parameters"></a><span data-ttu-id="e82eb-115">Angeben unbenannter und benannter Parameter</span><span class="sxs-lookup"><span data-stu-id="e82eb-115">Specifying Unnamed and Named Parameters</span></span>  
 <span data-ttu-id="e82eb-116">Sie können zwei Parametertypen angeben: unbenannte und benannte Parameter.</span><span class="sxs-lookup"><span data-stu-id="e82eb-116">You can specify two types of parameters: unnamed and named.</span></span> <span data-ttu-id="e82eb-117">Ein unbenannter Parameter wird durch ein Fragezeichen (?) bezeichnet, das Sie in einer Abfrage an der Position einfügen, an der Sie einen Literalwert abfragen oder einsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="e82eb-117">An unnamed parameter is a question mark (?) that you put anywhere in the query that you want to prompt for or substitute a literal value.</span></span> <span data-ttu-id="e82eb-118">Wenn Sie z. B. einen unbenannten Parameter für die Suche nach einer Autoren-ID in der Tabelle `titleauthor` verwenden, ergibt sich folgende Anweisung im [SQL-Bereich](visual-database-tools.md) :</span><span class="sxs-lookup"><span data-stu-id="e82eb-118">For example, if you use an unnamed parameter to search for an author's id in the `titleauthor` table, the resulting statement in the [SQL Pane](visual-database-tools.md) might look like this:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
 <span data-ttu-id="e82eb-119">Wenn Sie die Abfrage im [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md)ausführen, wird das [Dialogfeld „Abfrageparameter“](query-parameters-dialog-box-visual-database-tools.md) mit „?“ als Name des Parameters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e82eb-119">When you run the query in the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md), the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with "?" as the name of the parameter.</span></span>  
  
 <span data-ttu-id="e82eb-120">Sie können einem Parameter auch einen Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e82eb-120">Alternatively, you can assign a name to a parameter.</span></span> <span data-ttu-id="e82eb-121">Benannte Parameter sind dann hilfreich, wenn in einer Abfrage mehrere Parameter enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e82eb-121">Named parameters are particularly useful if you have multiple parameters in a query.</span></span> <span data-ttu-id="e82eb-122">Wenn Sie z. B. benannte Parameter für die Suche nach dem Vor- und Nachnamen eines Autors in der Tabelle `authors` verwenden, ergibt sich folgende Anweisung im SQL-Bereich:</span><span class="sxs-lookup"><span data-stu-id="e82eb-122">For example, if you use named parameters to search for an author's first and last names in the `authors` table, the resulting statement in the SQL pane might look like this:</span></span>  
  
```  
SELECT au_id  
FROM authors  
WHERE au_fname = %first name% AND  
      au_lname = %last name%  
```  
  
> [!TIP]  
>  <span data-ttu-id="e82eb-123">Definieren Sie Präfix- und Suffixzeichen, bevor Sie eine Abfrage mit benannten Parametern erstellen.</span><span class="sxs-lookup"><span data-stu-id="e82eb-123">You must define prefix and suffix characters before creating a named parameter query.</span></span>  
  
 <span data-ttu-id="e82eb-124">Wenn Sie die Abfrage im Abfrage- und Sicht-Designer ausführen, wird das [Dialogfeld „Abfrageparameter“](query-parameters-dialog-box-visual-database-tools.md) mit einer Liste benannter Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e82eb-124">When you run the query in the Query and View Designer, the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with a list of named parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82eb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e82eb-125">See Also</span></span>  
 <span data-ttu-id="e82eb-126">[Abfragen mit Parametern &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e82eb-126">[Query with Parameters &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span></span>  
 <span data-ttu-id="e82eb-127">[Unterstützte Abfrage Typen &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e82eb-127">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e82eb-128">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e82eb-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
