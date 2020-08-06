---
title: Angeben mehrerer Suchbedingungen für mehrere Spalten (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 06617729-0d0b-4da2-9890-b7e2f5cdbc7b
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccf08a98d39d4ab808b7c2df794164b341be363a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615738"
---
# <a name="specify-multiple-search-conditions-for-multiple-columns-visual-database-tools"></a><span data-ttu-id="eba78-102">Angeben mehrerer Suchbedingungen für mehrere Spalten (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="eba78-102">Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="eba78-103">Sie können den Bereich der Abfrage erweitern oder einschränken, indem Sie verschiedene Spalten in die Suchbedingung aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="eba78-103">You can expand or narrow the scope of your query by including several data columns as part of your search condition.</span></span> <span data-ttu-id="eba78-104">Auf diese Weise können Sie beispielsweise folgende Vorgänge durchführen:</span><span class="sxs-lookup"><span data-stu-id="eba78-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="eba78-105">Sie können nach Mitarbeitern suchen, die entweder seit mehr als fünf Jahren in der Firma arbeiten oder bestimmte Tätigkeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="eba78-105">Search for employees who either have worked more than five years at the company or who hold certain jobs.</span></span>  
  
-   <span data-ttu-id="eba78-106">Sie können nach einem Buch suchen, das von einem bestimmten Herausgeber veröffentlicht wurde und gleichzeitig ein Kochbuch ist.</span><span class="sxs-lookup"><span data-stu-id="eba78-106">Search for a book that is both published by a specific publisher and pertains to cooking.</span></span>  
  
 <span data-ttu-id="eba78-107">Für einer Abfrage, die in zwei oder mehr Spalten nach Werten sucht, wird eine OR-Bedingung verwendet.</span><span class="sxs-lookup"><span data-stu-id="eba78-107">To create a query that searches for values in either of two (or more) columns, you specify an OR condition.</span></span> <span data-ttu-id="eba78-108">Demgegenüber wird zur Erstellung einer Abfrage, die alle Bedingungen in zwei oder mehr Spalten erfüllen muss, eine AND-Bedingung eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="eba78-108">To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="eba78-109">Angeben einer OR-Bedingung</span><span class="sxs-lookup"><span data-stu-id="eba78-109">Specifying an OR Condition</span></span>  
 <span data-ttu-id="eba78-110">Wenn Sie mehrere mit OR verknüpfte Bedingungen erstellen möchten, setzen Sie jede Bedingung in eine andere Spalte des Kriterienbereichs.</span><span class="sxs-lookup"><span data-stu-id="eba78-110">To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.</span></span>  
  
#### <a name="to-specify-an-or-condition-for-two-different-columns"></a><span data-ttu-id="eba78-111">So geben Sie eine OR-Bedingung für zwei verschiedene Spalten an</span><span class="sxs-lookup"><span data-stu-id="eba78-111">To specify an OR condition for two different columns</span></span>  
  
1.  <span data-ttu-id="eba78-112">Fügen Sie dem [Kriterienbereich](visual-database-tools.md)die Spalten hinzu, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eba78-112">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="eba78-113">Geben Sie in der Spalte **Filter** für die erste zu durchsuchende Spalte die erste Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="eba78-113">In the **Filter** column for the first column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="eba78-114">Geben Sie in der Spalte **Oder** für die zweite zu durchsuchende Datenspalte die zweite Bedingung an, und lassen Sie die Spalte **Filter** leer.</span><span class="sxs-lookup"><span data-stu-id="eba78-114">In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.</span></span>  
  
     <span data-ttu-id="eba78-115">Der Abfrage- und Sicht-Designer erstellt eine WHERE-Klausel mit einer OR-Bedingung, z. B.:</span><span class="sxs-lookup"><span data-stu-id="eba78-115">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  <span data-ttu-id="eba78-116">Wiederholen Sie die Schritte 2 und 3 für jede weitere Bedingung, die hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eba78-116">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span> <span data-ttu-id="eba78-117">Verwenden Sie für jede neue Bedingung eine neue Spalte **Oder...** .</span><span class="sxs-lookup"><span data-stu-id="eba78-117">Use a different **Or...** column for each new condition.</span></span>  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="eba78-118">Angeben einer AND-Bedingung</span><span class="sxs-lookup"><span data-stu-id="eba78-118">Specifying an AND Condition</span></span>  
 <span data-ttu-id="eba78-119">Um verschiedene Datenspalten nach Bedingungen zu durchsuchen, die mit AND verknüpft sind, setzen Sie alle Bedingungen in die Datenblattspalte **Filter** .</span><span class="sxs-lookup"><span data-stu-id="eba78-119">To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.</span></span>  
  
#### <a name="to-specify-an-and-condition-for-two-different-columns"></a><span data-ttu-id="eba78-120">So geben Sie eine AND-Bedingung für zwei verschiedene Spalten an</span><span class="sxs-lookup"><span data-stu-id="eba78-120">To specify an AND condition for two different columns</span></span>  
  
1.  <span data-ttu-id="eba78-121">Fügen Sie dem [Kriterienbereich](visual-database-tools.md)die Spalten hinzu, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eba78-121">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="eba78-122">Geben Sie in der Spalte **Filter** für die erste zu durchsuchende Datenspalte die erste Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="eba78-122">In the **Filter** column for the first data column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="eba78-123">Geben Sie in der Spalte **Filter** für die zweite Datenspalte die zweite Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="eba78-123">In the **Filter** column for the second data column, specify the second condition.</span></span>  
  
     <span data-ttu-id="eba78-124">Der Abfrage- und Sicht-Designer erstellt eine WHERE-Klausel mit einer AND-Bedingung, z. B.:</span><span class="sxs-lookup"><span data-stu-id="eba78-124">The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  <span data-ttu-id="eba78-125">Wiederholen Sie die Schritte 2 und 3 für jede weitere Bedingung, die hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eba78-125">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba78-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eba78-126">See Also</span></span>  
 <span data-ttu-id="eba78-127">[Kombinieren von Bedingungen, wenn und Vorrang &#40;Visual Database Tools haben&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eba78-127">[Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eba78-128">[Kombinieren von Bedingungen, wenn or Vorrang &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eba78-128">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eba78-129">[Konventionen für das Kombinieren von Suchbedingungen im Kriterienbereich &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eba78-129">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="eba78-130">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="eba78-130">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
