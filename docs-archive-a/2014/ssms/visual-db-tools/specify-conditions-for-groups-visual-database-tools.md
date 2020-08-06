---
title: Angeben von Bedingungen für Gruppen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query groups
- group query conditions [SQL Server]
ms.assetid: 269ad9c5-3261-4526-badf-7be3c869f229
author: stevestein
ms.author: sstein
ms.openlocfilehash: da9bc1b70fbfae8bf2a68a3a3ba332020020f310
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607476"
---
# <a name="specify-conditions-for-groups-visual-database-tools"></a><span data-ttu-id="1a7a5-102">Angeben von Bedingungen für Gruppen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1a7a5-102">Specify Conditions for Groups (Visual Database Tools)</span></span>
  <span data-ttu-id="1a7a5-103">Sie können die Anzahl der in einer Abfrage aufgeführten Gruppen begrenzen, indem Sie eine Bedingung angeben, die für Gruppen als Ganzes gilt – eine HAVING-Klausel.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-103">You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a HAVING clause.</span></span> <span data-ttu-id="1a7a5-104">Die Bedingungen der HAVING-Klausel werden angewendet, nachdem alle Daten gruppiert und aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-104">After the data has been grouped and aggregated, the conditions in the HAVING clause are applied.</span></span> <span data-ttu-id="1a7a5-105">Nur die Gruppen werden in die Abfrage aufgenommen, die die Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-105">Only the groups that meet the conditions appear in the query.</span></span>  
  
 <span data-ttu-id="1a7a5-106">Angenommen, Sie möchten den Durchschnittspreis aller Bücher der einzelnen Herausgeber in der Tabelle `titles` anzeigen lassen, wenn dieser höher als 10,00 ist.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-106">For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00.</span></span> <span data-ttu-id="1a7a5-107">In diesem Fall kann eine HAVING-Klausel mit folgender Bedingung angegeben werden: `AVG(price) > 10`.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-107">In that case, you could specify a HAVING clause with a condition such as `AVG(price) > 10`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a7a5-108">In einigen Fällen kann es sinnvoll sein, vor Anwendung einer Bedingung auf Gruppen als Ganzes einzelne Zeilen aus den Gruppen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-108">In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole.</span></span> <span data-ttu-id="1a7a5-109">Weitere Informationen finden Sie unter [Verwenden von HAVING- und WHERE-Klauseln in derselben Abfrage &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a7a5-109">For details, see [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="1a7a5-110">Sie können komplexe Bedingungen für eine HAVING-Klausel erstellen, indem Sie Bedingungen mit AND und OR verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-110">You can create complex conditions for a HAVING clause by using AND and OR to link conditions.</span></span> <span data-ttu-id="1a7a5-111">Weitere Informationen zum Verwenden von AND und OR in Suchbedingungen finden Sie unter [Angeben mehrerer Suchbedingungen für eine Spalte &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a7a5-111">For details about using AND and OR in search conditions, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span></span>  
  
### <a name="to-specify-a-condition-for-a-group"></a><span data-ttu-id="1a7a5-112">So geben Sie eine Bedingung für eine Gruppe an</span><span class="sxs-lookup"><span data-stu-id="1a7a5-112">To specify a condition for a group</span></span>  
  
1.  <span data-ttu-id="1a7a5-113">Geben Sie die Gruppen für die Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-113">Specify the groups for your query.</span></span> <span data-ttu-id="1a7a5-114">Weitere Informationen finden Sie unter [Gruppieren von Zeilen in Abfrageergebnissen &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a7a5-114">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="1a7a5-115">Fügen Sie dem [Kriterienbereich](criteria-pane-visual-database-tools.md) die Spalte hinzu, auf der die Bedingung basieren soll, sofern sie dort nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-115">If it is not already in the [Criteria pane](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition.</span></span> <span data-ttu-id="1a7a5-116">(Meistens enthält die Bedingung eine bereits gruppierte bzw. zusammengefasste Spalte.) Spalten, die weder einer Aggregatfunktion noch der GROUP BY-Klausel angehören, können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-116">(Most often the condition involves a column that is already a group or summary column.) You cannot use a column that is not part of an aggregate function or of the GROUP BY clause.</span></span>  
  
3.  <span data-ttu-id="1a7a5-117">Geben Sie die Bedingung für die Gruppe in der Spalte **Filter** an.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-117">In the **Filter** column, specify the condition to apply to the group.</span></span>  
  
     <span data-ttu-id="1a7a5-118">Der [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) erstellt automatisch eine HAVING-Klausel in der Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md). Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1a7a5-118">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically creates a HAVING clause in the statement in the [SQL pane](sql-pane-visual-database-tools.md), such as in the following example:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
  
    ```  
  
4.  <span data-ttu-id="1a7a5-119">Wiederholen Sie die Schritte 2 und 3 für jede weitere Bedingung, die angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a7a5-119">Repeat steps 2 and 3 for each additional condition you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a7a5-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a7a5-120">See Also</span></span>  
 [<span data-ttu-id="1a7a5-121">Sortieren und Gruppieren von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1a7a5-121">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
