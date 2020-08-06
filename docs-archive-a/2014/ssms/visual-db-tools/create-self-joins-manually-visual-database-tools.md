---
title: Manuelles Erstellen von Selbstjoins (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- self-joins
- manual joins [SQL Server]
- joins [SQL Server], self
ms.assetid: 910ed516-cb84-481b-95d0-cba3e89afdba
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31e125fdfe0f7f285ea679cfe85356d1aa10353a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618994"
---
# <a name="create-self-joins-manually-visual-database-tools"></a><span data-ttu-id="fae3f-102">Manuelles Erstellen von Selbstjoins (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fae3f-102">Create Self-Joins Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="fae3f-103">Sie können eine Tabelle mit sich selbst verknüpfen, auch wenn die Tabelle über keine reflexive Beziehung in der Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="fae3f-103">You can join a table to itself even if the table does not have a reflexive relationship in the database.</span></span> <span data-ttu-id="fae3f-104">Mit einem Selbstjoin können Sie z. B. nach Paaren von Autoren suchen, die in derselben Stadt leben.</span><span class="sxs-lookup"><span data-stu-id="fae3f-104">For example, you can use a self-join to find pairs of authors living in the same city.</span></span>  
  
 <span data-ttu-id="fae3f-105">Wie bei jedem Join werden für einen Selbstjoin mindestens zwei Tabellen benötigt.</span><span class="sxs-lookup"><span data-stu-id="fae3f-105">As with any join, a self-join requires at least two tables.</span></span> <span data-ttu-id="fae3f-106">Der Unterschied besteht darin, dass Sie der Abfrage keine zweite Tabelle, sondern eine zweite Instanz derselben Tabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fae3f-106">The difference is that, instead of adding a second table to the query, you add a second instance of the same table.</span></span> <span data-ttu-id="fae3f-107">Auf diese Weise können Sie eine Spalte in der ersten Instanz der Tabelle mit derselben Spalte in der zweiten Instanz vergleichen, wodurch Sie die Werte einer Spalte miteinander vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="fae3f-107">That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other.</span></span> <span data-ttu-id="fae3f-108">Der [Abfrage- und Sicht-Designer](visual-database-tools.md) weist der zweiten Instanz der Tabelle einen Alias zu.</span><span class="sxs-lookup"><span data-stu-id="fae3f-108">The [Query and View Designer](visual-database-tools.md) assigns an alias to the second instance of the table.</span></span>  
  
 <span data-ttu-id="fae3f-109">Wenn Sie z. B. einen Selbstjoin zum Suchen aller Autorenpaare in Berkeley erstellen, vergleichen Sie die Spalte `city` in der ersten Instanz der Tabelle mit der Spalte `city` in der zweiten Instanz.</span><span class="sxs-lookup"><span data-stu-id="fae3f-109">For example, if you are creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance.</span></span> <span data-ttu-id="fae3f-110">Die entsprechende Abfrage könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="fae3f-110">The resulting query might look like the following:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="fae3f-111">Das Erstellen eines Selbstjoins erfordert oft mehrere Joinbedingungen.</span><span class="sxs-lookup"><span data-stu-id="fae3f-111">Creating a self-join often requires multiple join conditions.</span></span> <span data-ttu-id="fae3f-112">Die Gründe dafür werden aus dem Ergebnis der vorherigen Abfrage ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="fae3f-112">To understand why, consider the result of the preceding query:</span></span>  
  
```  
Cheryl Carson       Cheryl Carson  
Abraham Bennet      Abraham Bennet  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="fae3f-113">Die erste Zeile ist ohne Belang; sie gibt an, dass Cheryl Carson in derselben Stadt wie Cheryl Carson lebt.</span><span class="sxs-lookup"><span data-stu-id="fae3f-113">The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson.</span></span> <span data-ttu-id="fae3f-114">Die zweite Zeile wird ebenfalls nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="fae3f-114">The second row is equally useless.</span></span> <span data-ttu-id="fae3f-115">Fügen Sie eine weitere Bedingung hinzu, durch die nur die Ergebniszeilen beibehalten werden, in denen die Autorennamen verschiedene Autoren bezeichnen, um diese überflüssigen Daten auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="fae3f-115">To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors.</span></span> <span data-ttu-id="fae3f-116">Die sich ergebende Abfrage könnte so aussehen:</span><span class="sxs-lookup"><span data-stu-id="fae3f-116">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             <> authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="fae3f-117">Das Resultset wurde verbessert:</span><span class="sxs-lookup"><span data-stu-id="fae3f-117">The result set is improved:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="fae3f-118">Die zwei Ergebniszeilen sind jedoch redundant.</span><span class="sxs-lookup"><span data-stu-id="fae3f-118">But the two result rows are redundant.</span></span> <span data-ttu-id="fae3f-119">Die erste Zeile gibt an, dass Carson in derselben Stadt wie Bennet lebt, und mit der zweiten Zeile wird angegeben, dass Bennet in derselben Stadt wie Carson lebt.</span><span class="sxs-lookup"><span data-stu-id="fae3f-119">The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson.</span></span> <span data-ttu-id="fae3f-120">Sie können Sie die zweite Joinbedingung von "ungleich" in "kleiner als" ändern, um diese Redundanz auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="fae3f-120">To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than."</span></span> <span data-ttu-id="fae3f-121">Die sich ergebende Abfrage könnte so aussehen:</span><span class="sxs-lookup"><span data-stu-id="fae3f-121">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             < authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="fae3f-122">Das Resultset sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="fae3f-122">And the result set looks like this:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
```  
  
### <a name="to-create-a-self-join-manually"></a><span data-ttu-id="fae3f-123">So erstellen Sie manuell einen Selbstjoin</span><span class="sxs-lookup"><span data-stu-id="fae3f-123">To create a self-join manually</span></span>  
  
1.  <span data-ttu-id="fae3f-124">Fügen Sie dem [Diagrammbereich](diagram-pane-visual-database-tools.md) die gewünschte Tabelle bzw. das gewünschte Tabellenwertobjekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="fae3f-124">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.</span></span>  
  
2.  <span data-ttu-id="fae3f-125">Fügen Sie dieselbe Tabelle erneut hinzu, sodass die Tabelle bzw. das Tabellenwertobjekt im Diagrammbereich zweimal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fae3f-125">Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="fae3f-126">Der Abfrage- und Sicht-Designer weist der zweiten Instanz einen Alias zu, indem dem Tabellennamen eine laufende Nummer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fae3f-126">The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="fae3f-127">Außerdem erstellt der Abfrage- und Sicht-Designer im Diagrammbereich eine Joinlinie zwischen den beiden Instanzen der Tabelle bzw. des Tabellenwertobjekts.</span><span class="sxs-lookup"><span data-stu-id="fae3f-127">In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.</span></span>  
  
3.  <span data-ttu-id="fae3f-128">Klicken Sie mit der rechten Maustaste auf die Joinlinie, und wählen Sie im Kontextmenü die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="fae3f-128">Right-click the join line and choose **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="fae3f-129">Klicken Sie im Eigenschaftenfenster auf **Joinkondition und -typ** und anschließend auf die **Auslassungspunkte (...)** , die rechts neben der Eigenschaft angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fae3f-129">In the Properties window click **Join Condition and Type** and click the **ellipses (...)** to the right of the property.</span></span>  
  
5.  <span data-ttu-id="fae3f-130">Ändern Sie nach Bedarf im [Dialogfeld „Join“](join-dialog-box-visual-database-tools.md) den Vergleichsoperator zwischen den Primärschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="fae3f-130">In the [Join Dialog Box](join-dialog-box-visual-database-tools.md) change the comparison operator between the primary keys as required.</span></span> <span data-ttu-id="fae3f-131">Sie können z. B. den Operator in "kleiner als" (<) ändern.</span><span class="sxs-lookup"><span data-stu-id="fae3f-131">For example, you might change the operator to less than (<).</span></span>  
  
6.  <span data-ttu-id="fae3f-132">Erstellen Sie die zusätzliche Joinbedingung (z. B. authors.zip = authors1.zip), indem Sie den Namen der primären Joinspalte aus der ersten Instanz der Tabelle bzw. des Tabellenwertobjekts ziehen und in der entsprechenden Spalte der zweiten Instanz ablegen.</span><span class="sxs-lookup"><span data-stu-id="fae3f-132">Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.</span></span>  
  
7.  <span data-ttu-id="fae3f-133">Geben Sie weitere Optionen für die Abfrage an (z. B. Ausgabespalten, Suchbedingungen und Sortierreihenfolge).</span><span class="sxs-lookup"><span data-stu-id="fae3f-133">Specify other options for the query such as output columns, search conditions, and sort order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae3f-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fae3f-134">See Also</span></span>  
 <span data-ttu-id="fae3f-135">[Automatisches Erstellen von Selbstjoins &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fae3f-135">[Create Self-Joins Automatically &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fae3f-136">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fae3f-136">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
