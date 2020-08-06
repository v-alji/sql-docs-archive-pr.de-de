---
title: Auffüllen einer Tabelle mit vorhandenen hierarchischen Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: fd943d84-dbe6-4a05-912b-c88164998d80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 966548b11ad4697abc06de5c5c239a511f80b7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696705"
---
# <a name="populating-a-table-with-existing-hierarchical-data"></a><span data-ttu-id="b0f10-102">Auffüllen einer Tabelle mit vorhandenen hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="b0f10-102">Populating a Table with Existing Hierarchical Data</span></span>
  <span data-ttu-id="b0f10-103"> In dieser Aufgabe wird eine neue Tabelle erstellt und mit den Daten aus der Tabelle **EmployeeDemo** aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b0f10-103">This task creates a new table and populates it with the data in the **EmployeeDemo** table.</span></span> <span data-ttu-id="b0f10-104">Diese Aufgabe umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="b0f10-104">This task has the following steps:</span></span>  
  
-   <span data-ttu-id="b0f10-105">Erstellen Sie eine neue Tabelle, die eine `hierarchyid`-Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="b0f10-105">Create a new table that contains a `hierarchyid` column.</span></span> <span data-ttu-id="b0f10-106">Diese Spalte könnte die vorhandenen Spalten **EmployeeID** und **ManagerID** ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b0f10-106">This column could replace the existing **EmployeeID** and **ManagerID** columns.</span></span> <span data-ttu-id="b0f10-107">Sie behalten diese Spalten jedoch bei,</span><span class="sxs-lookup"><span data-stu-id="b0f10-107">However, you will retain those columns.</span></span> <span data-ttu-id="b0f10-108">weil bestehende Anwendungen möglicherweise auf diese Spalten verweisen und weil dann die Daten nach der Übertragung leichter verständlich sind.</span><span class="sxs-lookup"><span data-stu-id="b0f10-108">This is because existing applications might refer to those columns, and also to help you understand the data after the transfer.</span></span> <span data-ttu-id="b0f10-109">Gemäß der Tabellendefinition ist **OrgNode** der Primärschlüssel, so dass diese Spalte eindeutige Werte enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="b0f10-109">The table definition specifies that **OrgNode** is the primary key, which requires the column to contain unique values.</span></span> <span data-ttu-id="b0f10-110">Der gruppierte Index der Spalte **OrgNode** speichert das Datum in **OrgNode** -Sequenz.</span><span class="sxs-lookup"><span data-stu-id="b0f10-110">The clustered index on the **OrgNode** column will store the date in **OrgNode** sequence.</span></span>  
  
-   <span data-ttu-id="b0f10-111">Erstellen Sie eine temporäre Tabelle, mit deren Hilfe verfolgt wird, wie viele Mitarbeiter jedem Manager direkt unterstellt sind.</span><span class="sxs-lookup"><span data-stu-id="b0f10-111">Create a temporary table that is used to track how many employees report directly to each manager.</span></span>  
  
-   <span data-ttu-id="b0f10-112">Füllen Sie die neue Tabelle mit Daten aus der Tabelle **EmployeeDemo** auf.</span><span class="sxs-lookup"><span data-stu-id="b0f10-112">Populate the new table by using data from the **EmployeeDemo** table.</span></span>  
  
### <a name="to-create-a-new-table-named-neworg"></a><span data-ttu-id="b0f10-113">So erstellen Sie eine neue Tabelle namens NewOrg</span><span class="sxs-lookup"><span data-stu-id="b0f10-113">To create a new table named NewOrg</span></span>  
  
-   <span data-ttu-id="b0f10-114">Führen Sie in einem Abfrage-Editorfenster den folgenden Code aus, um eine einfache Tabelle namens **HumanResources.NewOrg**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0f10-114">In a Query Editor window, run the following code to create a new table named **HumanResources.NewOrg**:</span></span>  
  
    ```  
    CREATE TABLE NewOrg  
    (  
      OrgNode hierarchyid,  
      EmployeeID int,  
      LoginID nvarchar(50),  
      ManagerID int  
    CONSTRAINT PK_NewOrg_OrgNode  
      PRIMARY KEY CLUSTERED (OrgNode)  
    );  
    GO  
    ```  
  
### <a name="to-create-a-temporary-table-named-children"></a><span data-ttu-id="b0f10-115">So erstellen Sie eine temporäre Tabelle namens #Children</span><span class="sxs-lookup"><span data-stu-id="b0f10-115">To create a temporary table named #Children</span></span>  
  
1.  <span data-ttu-id="b0f10-116">Erstellen Sie eine temporäre Tabelle namens **#Children** mit einer Spalte namens **Num** , in der für jeden Knoten die Anzahl der untergeordneten Elemente verzeichnet wird:</span><span class="sxs-lookup"><span data-stu-id="b0f10-116">Create a temporary table named **#Children** with a column named **Num** that will contain the number of children for each node:</span></span>  
  
    ```  
    CREATE TABLE #Children   
       (  
        EmployeeID int,  
        ManagerID int,  
        Num int  
    );  
    GO  
    ```  
  
2.  <span data-ttu-id="b0f10-117">Fügen Sie einen Index hinzu, der die Abfrage, mit der die Tabelle **NewOrg** aufgefüllt wird, erheblich beschleunigt:</span><span class="sxs-lookup"><span data-stu-id="b0f10-117">Add an index that will significantly speed up the query that populates the **NewOrg** table:</span></span>  
  
    ```  
    CREATE CLUSTERED INDEX tmpind ON #Children(ManagerID, EmployeeID);  
    GO  
    ```  
  
### <a name="to-populate-the-neworg-table"></a><span data-ttu-id="b0f10-118">So füllen Sie die Tabelle NewOrg auf</span><span class="sxs-lookup"><span data-stu-id="b0f10-118">To populate the NewOrg table</span></span>  
  
1.  <span data-ttu-id="b0f10-119">In rekursiven Abfragen sind Unterabfragen mit Aggregaten nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b0f10-119">Recursive queries forbid subqueries with aggregates.</span></span> <span data-ttu-id="b0f10-120">Füllen Sie die Tabelle **#Children** stattdessen mit folgendem Code auf, in dem die [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) -Methode zum Auffüllen der Spalte **Num** verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="b0f10-120">Instead, populate the **#Children** table with the following code, which uses the [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) method to populate the **Num** column:</span></span>  
  
    ```  
    INSERT #Children (EmployeeID, ManagerID, Num)  
    SELECT EmployeeID, ManagerID,  
      ROW_NUMBER() OVER (PARTITION BY ManagerID ORDER BY ManagerID)   
    FROM EmployeeDemo  
    GO  
  
    ```  
  
2.  <span data-ttu-id="b0f10-121">Überprüfen Sie die Tabelle **#Children** .</span><span class="sxs-lookup"><span data-stu-id="b0f10-121">Review the **#Children** table.</span></span> <span data-ttu-id="b0f10-122">Die Spalte **Num** enthält fortlaufende Nummern für die einzelnen Manager.</span><span class="sxs-lookup"><span data-stu-id="b0f10-122">Note how the **Num** column contains sequential numbers for each manager.</span></span>  
  
    ```  
    SELECT * FROM #Children ORDER BY ManagerID, Num  
    GO  
  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     `EmployeeID ManagerID Num`  
  
     `---------- --------- ---`  
  
     `1        NULL       1`  
  
     `2         1         1`  
  
     `3         1         2`  
  
     `4         2         1`  
  
     `5         2         2`  
  
     `6         2         3`  
  
     `7         3         1`  
  
     `8         3         2`  
  
     `9         4         1`  
  
     `10        4         2`  
  
3.  <span data-ttu-id="b0f10-123">Füllt die Tabelle " **networg** " auf.</span><span class="sxs-lookup"><span data-stu-id="b0f10-123">Populate the **NewOrg** table.</span></span> <span data-ttu-id="b0f10-124">Verwenden Sie die GetRoot-Methode und die ToString-Methode, um die **NUM** -Werte im Format zu verketten `hierarchyid` , und aktualisieren Sie dann die Spalte **OrgNode** mit den resultierenden hierarchischen Werten:</span><span class="sxs-lookup"><span data-stu-id="b0f10-124">Use the GetRoot and ToString methods to concatenate the **Num** values into the `hierarchyid` format, and then update the **OrgNode** column with the resultant hierarchical values:</span></span>  
  
    ```  
    WITH paths(path, EmployeeID)   
    AS (  
    -- This section provides the value for the root of the hierarchy  
    SELECT hierarchyid::GetRoot() AS OrgNode, EmployeeID   
    FROM #Children AS C   
    WHERE ManagerID IS NULL   
  
    UNION ALL   
    -- This section provides values for all nodes except the root  
    SELECT   
    CAST(p.path.ToString() + CAST(C.Num AS varchar(30)) + '/' AS hierarchyid),   
    C.EmployeeID  
    FROM #Children AS C   
    JOIN paths AS p   
       ON C.ManagerID = P.EmployeeID   
    )  
    INSERT NewOrg (OrgNode, O.EmployeeID, O.LoginID, O.ManagerID)  
    SELECT P.path, O.EmployeeID, O.LoginID, O.ManagerID  
    FROM EmployeeDemo AS O   
    JOIN Paths AS P   
       ON O.EmployeeID = P.EmployeeID  
    GO  
  
    ```  
  
4.  <span data-ttu-id="b0f10-125">Eine `hierarchyid`-Spalte ist verständlicher, wenn sie in das Zeichenformat konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="b0f10-125">A `hierarchyid` column is more understandable when you convert it to character format.</span></span> <span data-ttu-id="b0f10-126">Überprüfen Sie die Daten der Tabelle **NewOrg** , indem Sie den folgenden Code ausführen, der zwei Darstellungen der Spalte **OrgNode** enthält:</span><span class="sxs-lookup"><span data-stu-id="b0f10-126">Review the data in the **NewOrg** table by executing the following code, which contains two representations of the **OrgNode** column:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode, *   
    FROM NewOrg   
    ORDER BY LogicalNode;  
    GO  
  
    ```  
  
     <span data-ttu-id="b0f10-127">In der Spalte **LogicalNode** wird die `hierarchyid` Spalte in ein lesbares Textformular konvertiert, das die Hierarchie darstellt.</span><span class="sxs-lookup"><span data-stu-id="b0f10-127">The **LogicalNode** column converts the `hierarchyid` column into a more readable text form that represents the hierarchy.</span></span> <span data-ttu-id="b0f10-128">In den restlichen Aufgaben werden Sie die `ToString()`-Methode verwenden, um die `hierarchyid`-Spalten im logischen Format anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0f10-128">In the remaining tasks, you will use the `ToString()` method to show the logical format of the `hierarchyid` columns.</span></span>  
  
5.  <span data-ttu-id="b0f10-129">Löschen Sie die temporäre Tabelle, die nicht mehr benötigt wird:</span><span class="sxs-lookup"><span data-stu-id="b0f10-129">Drop the temporary table, which is no longer needed:</span></span>  
  
    ```  
    DROP TABLE #Children  
    GO  
    ```  
  
 <span data-ttu-id="b0f10-130">In der nächsten Aufgabe werden Indizes erstellt, um die hierarchische Struktur zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b0f10-130">The next task will create indexes to support the hierarchical structure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b0f10-131">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="b0f10-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b0f10-132">Optimieren der NewOrg-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b0f10-132">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
  
