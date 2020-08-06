---
title: Kombinieren von Bedingungen, wenn „AND“ Vorrang hat (Visual Database Tools) | Microsoft-Dokumentation
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
- AND, Criteria pane
ms.assetid: 450eb2eb-6ea3-405b-8dd2-1ff926c016e7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 917d5381bc83083ee1fa3c07375945c0908da521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695169"
---
# <a name="combine-conditions-when-and-has-precedence-visual-database-tools"></a><span data-ttu-id="db529-102">Kombinieren von Bedingungen, wenn AND Vorrang hat (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="db529-102">Combine Conditions When AND Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="db529-103">Um Bedingungen mit AND zu kombinieren, fügen Sie die Spalte zur Abfrage zweimal hinzu – je einmal für jede Bedingung.</span><span class="sxs-lookup"><span data-stu-id="db529-103">To combine conditions with AND, you add the column to the query twice--once for each condition.</span></span> <span data-ttu-id="db529-104">Um Bedingungen mit OR zu kombinieren, setzen Sie die erste Bedingung in die Filterspalte und die weiteren Bedingungen in eine Spalte **Oder...** .</span><span class="sxs-lookup"><span data-stu-id="db529-104">To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.</span></span>  
  
 <span data-ttu-id="db529-105">Angenommen, Sie möchten nach Mitarbeitern suchen, die entweder seit mehr als fünf Jahren in der Firma beschäftigt sind und gering qualifizierte Tätigkeiten auf unterer Betriebsebene ausüben oder unabhängig vom Einstellungsdatum auf mittlerer Betriebsebene tätig sind.</span><span class="sxs-lookup"><span data-stu-id="db529-105">For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date.</span></span> <span data-ttu-id="db529-106">Diese Abfrage erfordert drei Bedingungen, von denen zwei mit AND verknüpft sind:</span><span class="sxs-lookup"><span data-stu-id="db529-106">This query requires three conditions, two of them linked with AND:</span></span>  
  
-   <span data-ttu-id="db529-107">Mitarbeiter, die vor weniger als fünf Jahren eingestellt wurden UND deren Tätigkeitsstufe 100 beträgt.</span><span class="sxs-lookup"><span data-stu-id="db529-107">Employees with a hire date earlier than five years ago AND with a job level of 100.</span></span>  
  
     <span data-ttu-id="db529-108">Oder</span><span class="sxs-lookup"><span data-stu-id="db529-108">-or-</span></span>  
  
-   <span data-ttu-id="db529-109">Mitarbeiter mit der Tätigkeitsstufe 200.</span><span class="sxs-lookup"><span data-stu-id="db529-109">Employees with a job level of 200.</span></span>  
  
### <a name="to-combine-conditions-when-and-has-precedence"></a><span data-ttu-id="db529-110">So kombinieren Sie Bedingungen, wenn AND Vorrang hat</span><span class="sxs-lookup"><span data-stu-id="db529-110">To combine conditions when AND has precedence</span></span>  
  
1.  <span data-ttu-id="db529-111">Fügen Sie dem [Kriterienbereich](visual-database-tools.md)die Datenspalten hinzu, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="db529-111">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="db529-112">Wenn Sie dieselbe Spalte nach zwei oder mehr mit AND verbundenen Bedingungen durchsuchen möchten, müssen Sie den Namen der Datenspalte für jeden zu suchenden Wert einmal in das Datenblatt einfügen.</span><span class="sxs-lookup"><span data-stu-id="db529-112">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="db529-113">Geben Sie in der Spalte **Kriterien** sämtliche Bedingungen ein, die mit AND verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="db529-113">In the **Filter** column, enter all the conditions that you want to link with AND.</span></span> <span data-ttu-id="db529-114">Um beispielsweise Bedingungen mit AND zu verknüpfen, nach denen in den Spalten `hire_date` und `job_lvl` gesucht werden soll, geben Sie in die Filterspalte die Werte `< '1/1/91'` und `= 100`ein.</span><span class="sxs-lookup"><span data-stu-id="db529-114">For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.</span></span>  
  
     <span data-ttu-id="db529-115">Diese Datenblatteinträge generieren die folgende WHERE-Klausel in der Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="db529-115">These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  <span data-ttu-id="db529-116">Geben Sie in der Datenblattspalte **Oder...** Bedingungen ein, die mit OR verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="db529-116">In the **Or...** grid column, enter conditions that you want to link with OR.</span></span> <span data-ttu-id="db529-117">Wenn beispielsweise eine Bedingung hinzugefügt werden soll, die nach einem anderen Wert in der Spalte `job_lvl` sucht, fügen Sie einen zusätzlichen Wert in die Spalte **Oder...** ein, z. B. `= 200`.</span><span class="sxs-lookup"><span data-stu-id="db529-117">For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.</span></span>  
  
     <span data-ttu-id="db529-118">Durch das Hinzufügen eines Werts in der Spalte **Oder...** wird der WHERE-Klausel in der Anweisung im SQL-Bereich eine weitere Bedingung hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="db529-118">Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="db529-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db529-119">See Also</span></span>  
 <span data-ttu-id="db529-120">[Kombinieren von Bedingungen, wenn or Vorrang &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="db529-120">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="db529-121">[Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="db529-121">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 <span data-ttu-id="db529-122">[Regeln für das Eingeben von Such Werten &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="db529-122">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="db529-123">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="db529-123">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
