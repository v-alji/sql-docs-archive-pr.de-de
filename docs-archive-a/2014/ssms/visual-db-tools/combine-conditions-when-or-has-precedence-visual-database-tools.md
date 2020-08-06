---
title: Kombinieren von Bedingungen, wenn „OR“ Vorrang hat (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- combining search conditions
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8be0d2f783c28662eb01f6bf191dc24d339534f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695162"
---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a><span data-ttu-id="c0ed1-102">Kombinieren von Bedingungen, wenn OR Vorrang hat (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c0ed1-102">Combine Conditions When OR Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="c0ed1-103">Wenn die mit OR verbundene Bedingungen den Vorrang vor den mit AND verbundenen Bedingungen haben sollen, muss die AND-Bedingung für jede OR-Bedingung wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-103">To link conditions with OR and give them precedence over conditions linked with AND, you must repeat the AND condition for each OR condition.</span></span>  
  
 <span data-ttu-id="c0ed1-104">Angenommen, Sie möchten alle Mitarbeiter suchen, die der Firma seit mehr als fünf Jahren angehören und gering qualifizierte Tätigkeiten auf unterer Betriebsebene ausführen oder im Ruhestand sind.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-104">For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired.</span></span> <span data-ttu-id="c0ed1-105">Diese Abfrage erfordert drei Bedingungen: eine einzelne Bedingung, die mit zwei weiteren Bedingungen durch AND verknüpft ist:</span><span class="sxs-lookup"><span data-stu-id="c0ed1-105">This query requires three conditions, a single condition linked to two additional conditions with AND:</span></span>  
  
-   <span data-ttu-id="c0ed1-106">Mitarbeiter, deren Einstellungsdatum mehr als fünf Jahre zurückliegt und</span><span class="sxs-lookup"><span data-stu-id="c0ed1-106">Employees with a hire date earlier than five years ago, and</span></span>  
  
-   <span data-ttu-id="c0ed1-107">Mitarbeiter mit einer Tätigkeitsstufe von 100 oder Mitarbeiter, deren Status "R" (Ruhestand) ist.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-107">Employees with a job level of 100 or whose status is "R" (for retired).</span></span>  
  
 <span data-ttu-id="c0ed1-108">Das folgende Verfahren illustriert die Erstellung einer derartigen Abfrage im Kriterienbereich.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-108">The following procedure illustrates how to create this type of query in the Criteria pane.</span></span>  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a><span data-ttu-id="c0ed1-109">So kombinieren Sie Bedingungen, wenn OR Vorrang hat</span><span class="sxs-lookup"><span data-stu-id="c0ed1-109">To combine conditions when OR has precedence</span></span>  
  
1.  <span data-ttu-id="c0ed1-110">Fügen Sie dem [Kriterienbereich](visual-database-tools.md)die Datenspalten hinzu, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-110">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="c0ed1-111">Wenn Sie dieselbe Spalte nach zwei oder mehr mit AND verbundenen Bedingungen durchsuchen möchten, müssen Sie den Namen der Datenspalte für jeden zu suchenden Wert einmal in das Datenblatt einfügen.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-111">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="c0ed1-112">Erstellen Sie die Bedingungen, die mit OR verknüpft werden sollen, indem Sie die erste Bedingung in die Datenblattspalte **Filter** und die zweite (sowie alle weiteren) Bedingungen in jeweils unterschiedliche Spalten **Oder...** eingeben.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-112">Create the conditions to be linked with OR by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns.</span></span> <span data-ttu-id="c0ed1-113">Geben Sie `job_lvl` in die Spalte `status` Filter `= 100` für **und** in die Spalte `job_lvl` Oder... `= 'R'` für **ein, um beispielsweise Bedingungen mit OR zum Durchsuchen der Spalten** und `status`zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-113">For example, to link conditions with OR that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.</span></span>  
  
     <span data-ttu-id="c0ed1-114">Wenn Sie diese Werte im Datenblatt eingeben, wird die folgende WHERE-Klausel in der Anweisung im SQL-Bereich erstellt:</span><span class="sxs-lookup"><span data-stu-id="c0ed1-114">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  <span data-ttu-id="c0ed1-115">Erstellen Sie die AND-Bedingung, indem Sie sie für jede OR-Bedingungen einmal eingeben.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-115">Create the AND condition by entering it once for each OR condition.</span></span> <span data-ttu-id="c0ed1-116">Nehmen Sie den Eintrag jeweils in der Datenblattspalte der entsprechenden OR-Bedingung vor.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-116">Place each entry in the same grid column as the OR condition it corresponds to.</span></span> <span data-ttu-id="c0ed1-117">Geben Sie beispielsweise `hire_date` sowohl in die Spalte „Kriterien“ als auch in die Spalte `< '1/1/91'` Oder... **ein, um eine AND-Bedingung hinzuzufügen, die in der Spalte** sucht und für beide OR-Bedingungen gilt.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-117">For example, to add an AND condition that searches the `hire_date` column and applies to both OR conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.</span></span>  
  
     <span data-ttu-id="c0ed1-118">Wenn Sie diese Werte im Datenblatt eingeben, wird die folgende WHERE-Klausel in der Anweisung im SQL-Bereich erstellt:</span><span class="sxs-lookup"><span data-stu-id="c0ed1-118">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="c0ed1-119">Sie können eine AND-Bedingung wiederholen, indem Sie sie einmal einfügen und dann mithilfe der Befehle **Ausschneiden** und **Einfügen** aus dem Menü **Bearbeiten** für die anderen OR-Bedingungen kopieren.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-119">You can repeat an AND condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other OR conditions.</span></span>  
  
 <span data-ttu-id="c0ed1-120">Die WHERE-Klausel, die vom Abfrage- und Sicht-Designer erstellt wird, entspricht der folgenden WHERE-Klausel, in der zum Festlegen des Vorrangs von OR vor AND Klammern verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c0ed1-120">The WHERE clause created by the Query and View Designer is equivalent to the following WHERE clause, which uses parentheses to specify the precedence of OR over AND:</span></span>  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c0ed1-121">Wenn Sie die Suchbedingungen im unmittelbar oberhalb des [SQL-Bereichs](sql-pane-visual-database-tools.md)angezeigten Format eingeben und dann im Diagramm- oder Kriterienbereich Änderungen an der Abfrage vornehmen, wird die SQL-Anweisung vom Abfrage- und Sicht-Designer neu erstellt, damit sie mit dem Formular übereinstimmt, das die explizit auf beide OR-Bedingungen verteilte AND-Bedingung enthält.</span><span class="sxs-lookup"><span data-stu-id="c0ed1-121">If you enter the search conditions in the format shown immediately above in the [SQL Pane](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the AND condition explicitly distributed to both OR conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ed1-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0ed1-122">See Also</span></span>  
 <span data-ttu-id="c0ed1-123">[Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c0ed1-123">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="c0ed1-124">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c0ed1-124">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
