---
title: Optimieren der NewOrg-Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- optimizing tables
ms.assetid: 89ff6d37-94c0-4773-8be9-dde943fff023
author: stevestein
ms.author: sstein
ms.openlocfilehash: 39c09a3a73051e7a61f3a62a125232d83d1570c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607597"
---
# <a name="optimizing-the-neworg-table"></a><span data-ttu-id="bd769-102">Optimieren der NewOrg-Tabelle</span><span class="sxs-lookup"><span data-stu-id="bd769-102">Optimizing the NewOrg Table</span></span>
  <span data-ttu-id="bd769-103">Die Tabelle " **netword** ", die Sie im Task "Auffüllen [einer Tabelle mit vorhandenen hierarchischen Daten](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) " erstellt haben, enthält alle Mitarbeiter Informationen und stellt die hierarchische Struktur mithilfe eines- `hierarchyid` Datentyps dar.</span><span class="sxs-lookup"><span data-stu-id="bd769-103">The **NewOrd** table that you created in the [Populating a Table with Existing Hierarchical Data](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) task contains all the employee information, and represents the hierarchical structure by using a `hierarchyid` data type.</span></span> <span data-ttu-id="bd769-104">In dieser Aufgabe werden neue Indizes hinzugefügt, die das Suchen in der `hierarchyid`-Spalte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bd769-104">This task adds new indexes to support searches on the `hierarchyid` column.</span></span>  
  
## <a name="clustered-index"></a><span data-ttu-id="bd769-105">Gruppierter Index</span><span class="sxs-lookup"><span data-stu-id="bd769-105">Clustered Index</span></span>  
 <span data-ttu-id="bd769-106">Die `hierarchyid` Spalte (**OrgNode**) ist der Primärschlüssel für die Tabelle " **networg** ".</span><span class="sxs-lookup"><span data-stu-id="bd769-106">The `hierarchyid` column (**OrgNode**) is the primary key for the **NewOrg** table.</span></span> <span data-ttu-id="bd769-107">Als die Tabelle erstellt wurde, enthielt sie den gruppierten Index **PK_NewOrg_OrgNode** , der die Eindeutigkeit der **OrgNode** -Spalte erzwingen sollte.</span><span class="sxs-lookup"><span data-stu-id="bd769-107">When the table was created, it contained a clustered index named **PK_NewOrg_OrgNode** to enforce the uniqueness of the **OrgNode** column.</span></span> <span data-ttu-id="bd769-108">Dieser gruppierte Index unterstützt auch eine Tiefensuche in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bd769-108">This clustered index also supports a depth-first search of the table.</span></span>  
  
## <a name="nonclustered-index"></a><span data-ttu-id="bd769-109">Nicht gruppierter Index</span><span class="sxs-lookup"><span data-stu-id="bd769-109">Nonclustered Index</span></span>  
 <span data-ttu-id="bd769-110">Dieser Schritt erstellt zwei nicht gruppierte Indizes, um typische Suchoperationen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bd769-110">This step creates two nonclustered indexes to support typical searches.</span></span>  
  
#### <a name="to-index-the-neworg-table-for-efficient-searches"></a><span data-ttu-id="bd769-111">So indizieren Sie die Tabelle 'NewOrg' für effiziente Suchoperationen</span><span class="sxs-lookup"><span data-stu-id="bd769-111">To index the NewOrg table for efficient searches</span></span>  
  
1.  <span data-ttu-id="bd769-112">Verwenden Sie zur Unterstützung von Abfragen der gleichen Ebene in der Hierarchie die [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) -Methode, um eine berechnete Spalte zu erstellen, welche die Ebene in der Hierarchie enthält.</span><span class="sxs-lookup"><span data-stu-id="bd769-112">To help queries at the same level in the hierarchy, use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to create a computed column that contains the level in the hierarchy.</span></span> <span data-ttu-id="bd769-113">Erstellen Sie dann für diese und die `Hierarchyid`-Spalte einen zusammengesetzten Index.</span><span class="sxs-lookup"><span data-stu-id="bd769-113">Then, create a composite index on the level and the `Hierarchyid`.</span></span> <span data-ttu-id="bd769-114">Führen Sie den folgenden Code aus, um die berechnete Spalte und den Breitensuchindex zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bd769-114">Run the following code to create the computed column and the breadth-first index:</span></span>  
  
    ```  
    ALTER TABLE NewOrg   
       ADD H_Level AS OrgNode.GetLevel() ;  
    CREATE UNIQUE INDEX EmpBFInd   
       ON NewOrg(H_Level, OrgNode) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="bd769-115">Erstellen Sie für die Spalte **EmployeeID** einen eindeutigen Index.</span><span class="sxs-lookup"><span data-stu-id="bd769-115">Create a unique index on the **EmployeeID** column.</span></span> <span data-ttu-id="bd769-116">Dies ist der übliche Singleton-Suchvorgang nach einem einzelnen Mitarbeiter entsprechend der **EmployeeID** -Nummer.</span><span class="sxs-lookup"><span data-stu-id="bd769-116">This is the traditional singleton lookup of a single employee by **EmployeeID** number.</span></span> <span data-ttu-id="bd769-117">Führen Sie den folgenden Code aus, um für **EmployeeID**einen Index zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bd769-117">Run the following code to create an index on **EmployeeID**:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmpIDs_unq ON NewOrg(EmployeeID) ;  
    GO  
    ```  
  
3.  <span data-ttu-id="bd769-118">Fügen Sie folgenden Code aus, um die Daten der Tabelle in der Reihenfolge jedes der drei Indizes abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bd769-118">Run the following code to retrieve data from the table in the order of each of the three indexes:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID  
    FROM NewOrg   
    ORDER BY OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY H_Level, OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY EmployeeID;  
    GO  
    ```  
  
4.  <span data-ttu-id="bd769-119">Vergleichen Sie die Resultsets, um zu sehen, wie die Reihenfolge in jedem Indextyp gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="bd769-119">Compare the result sets to see how the order is stored in each type of index.</span></span> <span data-ttu-id="bd769-120">Im Folgenden werden nur die ersten vier Zeilen jeder Ausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd769-120">Only the first four rows of each output follow.</span></span>  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     <span data-ttu-id="bd769-121">Tiefensuchindex: Mitarbeiterdatensätze sind angrenzend an den ihres Managers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd769-121">Depth-first index: Employee records are stored adjacent to their manager.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     <span data-ttu-id="bd769-122">Sortiert nach**EmployeeID**: Die Zeilen werden in der Reihenfolge der **EmployeeID** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd769-122">**EmployeeID**-first index: Rows are stored in **EmployeeID** sequence.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
> [!NOTE]  
>  <span data-ttu-id="bd769-123">Diagramme, die den Unterschied zwischen einem Tiefensuchindex und einem Breitensuchindex zeigen, finden Sie unter [Hierarchische Daten &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd769-123">For diagrams that show the difference between a depth-first index and a breadth-first index, see [Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span></span>  
  
#### <a name="to-drop-the-unnecessary-columns"></a><span data-ttu-id="bd769-124">So löschen Sie die unnötigen Spalten</span><span class="sxs-lookup"><span data-stu-id="bd769-124">To drop the unnecessary columns</span></span>  
  
1.  <span data-ttu-id="bd769-125">Die Spalte **ManagerID** stellt die Mitarbeiter-/Managerbeziehung dar, die jetzt von der Spalte **OrgNode** dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bd769-125">The **ManagerID** column represents the employee/manager relationship, which is now represented by the **OrgNode** column.</span></span> <span data-ttu-id="bd769-126">Wenn andere Anwendungen die Spalte **ManagerID** nicht benötigen, könnten Sie diese Spalte löschen, indem Sie die folgende Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="bd769-126">If other applications do not need the **ManagerID** column, consider dropping it by using the following statement:</span></span>  
  
    ```  
    ALTER TABLE NewOrg DROP COLUMN ManagerID ;  
    GO  
    ```  
  
2.  <span data-ttu-id="bd769-127">Die Spalte **EmployeeID** ist ebenfalls überflüssig.</span><span class="sxs-lookup"><span data-stu-id="bd769-127">The **EmployeeID** column is also redundant.</span></span> <span data-ttu-id="bd769-128">Jeder Mitarbeiter wird bereits durch die Spalte **OrgNode** eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bd769-128">The **OrgNode** column uniquely identifies each employee.</span></span> <span data-ttu-id="bd769-129">Wenn andere Anwendungen die Spalte **EmployeeID** nicht benötigen, könnten Sie den Index und dann die Spalte löschen, indem Sie folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="bd769-129">If other applications do not need the **EmployeeID** column, consider dropping the index and then the column by using the following code:</span></span>  
  
    ```  
    DROP INDEX EmpIDs_unq ON NewOrg ;  
    ALTER TABLE NewOrg DROP COLUMN EmployeeID ;  
    GO  
    ```  
  
#### <a name="to-replace-the-original-table-with-the-new-table"></a><span data-ttu-id="bd769-130">So ersetzen Sie die ursprüngliche durch die neue Tabelle</span><span class="sxs-lookup"><span data-stu-id="bd769-130">To replace the original table with the new table</span></span>  
  
1.  <span data-ttu-id="bd769-131">Wenn die ursprüngliche Tabelle irgendwelche zusätzlichen Indizes oder Einschränkungen enthält, dann fügen Sie diese der Tabelle **NewOrg** hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd769-131">If your original table contained any additional indexes or constraints, add them to the **NewOrg** table.</span></span>  
  
2.  <span data-ttu-id="bd769-132">So ersetzen Sie die alte **EmployeeDemo** -Tabelle durch die neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bd769-132">Replace the old **EmployeeDemo** table with the new table.</span></span> <span data-ttu-id="bd769-133">Führen Sie folgenden Code aus, um die alte Tabelle zu löschen und dann die neue Tabelle mit dem Namen der alten Tabelle zu benennen:</span><span class="sxs-lookup"><span data-stu-id="bd769-133">Run the following code to drop the old table, and then rename the new table with the old name:</span></span>  
  
    ```  
    DROP TABLE EmployeeDemo ;  
    GO  
    sp_rename 'NewOrg', EmployeeDemo ;  
    GO  
    ```  
  
3.  <span data-ttu-id="bd769-134">Führen Sie den folgenden Code aus, um die neue Tabelle zu untersuchen:</span><span class="sxs-lookup"><span data-stu-id="bd769-134">Run the following code to examine the final table:</span></span>  
  
    ```  
    SELECT * FROM EmployeeDemo ;  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bd769-135">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="bd769-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bd769-136">Zusammenfassung: Konvertieren einer Tabelle in eine hierarchische Struktur</span><span class="sxs-lookup"><span data-stu-id="bd769-136">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
  
