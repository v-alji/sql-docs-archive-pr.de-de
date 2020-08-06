---
title: Auffüllen einer hierarchischen Tabelle mit hierarchischen Methoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- HierarchyID
helpviewer_keywords:
- HierarchyID
ms.assetid: 2c95fa60-5b8e-4a05-ac09-cffe2b05900a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ef99d711a772a075f568a83f5d56fcecaaa598f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619698"
---
# <a name="populating-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="e0be8-102">Auffüllen einer hierarchischen Tabelle mit hierarchischen Methoden</span><span class="sxs-lookup"><span data-stu-id="e0be8-102">Populating a Hierarchical Table Using Hierarchical Methods</span></span>
  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="e0be8-103">hat 8 Mitarbeiter, die in der Marketingabteilung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e0be8-103">has 8 employees working in the Marketing department.</span></span> <span data-ttu-id="e0be8-104">Die Angestelltenhierarchie sieht ungefähr wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e0be8-104">The employee hierarchy looks like this:</span></span>  
  
 <span data-ttu-id="e0be8-105">**David**, **EmployeeID** 6, ist der Marketing-Manager.</span><span class="sxs-lookup"><span data-stu-id="e0be8-105">**David**, **EmployeeID** 6, is the Marketing Manager.</span></span> <span data-ttu-id="e0be8-106">Drei Marketingspezialisten berichten **David**:</span><span class="sxs-lookup"><span data-stu-id="e0be8-106">Three Marketing Specialists report to **David**:</span></span>  
  
-   <span data-ttu-id="e0be8-107">**Sariya**, **EmployeeID** 46</span><span class="sxs-lookup"><span data-stu-id="e0be8-107">**Sariya**, **EmployeeID** 46</span></span>  
  
-   <span data-ttu-id="e0be8-108">**John**, **EmployeeID** 271</span><span class="sxs-lookup"><span data-stu-id="e0be8-108">**John**, **EmployeeID** 271</span></span>  
  
-   <span data-ttu-id="e0be8-109">**Jill**, **EmployeeID** 119</span><span class="sxs-lookup"><span data-stu-id="e0be8-109">**Jill**, **EmployeeID** 119</span></span>  
  
 <span data-ttu-id="e0be8-110">Marketingassistent **Wanida** (**EmployeeID** 269) berichtet **Sariya**, und Marketingassistent **Mary** (**EmployeeID** 272) berichtet **John**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-110">Marketing Assistant **Wanida** (**EmployeeID** 269), reports to **Sariya**, and Marketing Assistant **Mary** (**EmployeeID** 272), reports to **John**.</span></span>  
  
### <a name="to-insert-the-root-of-the-hierarchy-tree"></a><span data-ttu-id="e0be8-111">So fügen Sie den Stamm in die Hierarchiestruktur ein</span><span class="sxs-lookup"><span data-stu-id="e0be8-111">To insert the root of the hierarchy tree</span></span>  
  
1.  <span data-ttu-id="e0be8-112">Das folgende Beispiel fügt den Marketing-Manager **David** als Stamm der Hierarchie in die Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="e0be8-112">The following example inserts **David** the Marketing Manager into the table at the root of the hierarchy.</span></span> <span data-ttu-id="e0be8-113">Die Spalte **OrdLevel** ist eine berechnete Spalte.</span><span class="sxs-lookup"><span data-stu-id="e0be8-113">The **OrdLevel** column is a computed column.</span></span> <span data-ttu-id="e0be8-114">Sie ist daher kein Teil der INSERT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e0be8-114">Therefore, it is not part of the INSERT statement.</span></span> <span data-ttu-id="e0be8-115">Der erste Datensatz verwendet die Methode [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) , um diesem ersten Datensatz als Stamm der Hierarchie zu füllen.</span><span class="sxs-lookup"><span data-stu-id="e0be8-115">This first record uses the [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) method to populate this first record as the root of the hierarchy.</span></span>  
  
    ```  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES (hierarchyid::GetRoot(), 6, 'David', 'Marketing Manager') ;  
    GO  
    ```  
  
2.  <span data-ttu-id="e0be8-116">Führen Sie den folgenden Code aus, um die Anfangszeile in der Tabelle zu untersuchen:</span><span class="sxs-lookup"><span data-stu-id="e0be8-116">Execute the following code to examine initial row in the table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    ```  
  
 <span data-ttu-id="e0be8-117">Wie in der vorigen Lektion verwenden wir die Methode `ToString()`, um den `hierarchyid`-Datentyp in ein leichter verständliches Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e0be8-117">As in the previous lesson, we use the `ToString()` method to convert the `hierarchyid` data type to a format that is more easily understood.</span></span>  
  
### <a name="to-insert-a-subordinate-employee"></a><span data-ttu-id="e0be8-118">So fügen Sie einen unterstellten Mitarbeiter ein</span><span class="sxs-lookup"><span data-stu-id="e0be8-118">To insert a subordinate employee</span></span>  
  
1.  <span data-ttu-id="e0be8-119">**Sariya** berichtet **David**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-119">**Sariya** reports to **David**.</span></span> <span data-ttu-id="e0be8-120">Zum Einfügen des Knotens **Sariya** müssen Sie einen entsprechenden **OrgNode** -Wert vom Datentyp erstellen `hierarchyid` .</span><span class="sxs-lookup"><span data-stu-id="e0be8-120">To insert **Sariya's** node, you must create an appropriate **OrgNode** value of data type `hierarchyid`.</span></span> <span data-ttu-id="e0be8-121">Das folgende Beispiel erstellt eine Variable des Datentyps `hierarchyid` und füllt sie mit dem OrgNode-Stammwert der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0be8-121">The following code creates a variable of data type `hierarchyid` and populates it with the root OrgNode value of the table.</span></span> <span data-ttu-id="e0be8-122">Diese Variable wird zusammen mit der Methode [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) verwendet, um eine Zeile einzufügen, die den untergeordneten Knoten darstellt.</span><span class="sxs-lookup"><span data-stu-id="e0be8-122">Then uses that variable with the [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) method to insert row that is a subordinate node.</span></span> <span data-ttu-id="e0be8-123">`GetDescendant` übernimmt zwei Argumente.</span><span class="sxs-lookup"><span data-stu-id="e0be8-123">`GetDescendant` takes two arguments.</span></span> <span data-ttu-id="e0be8-124">Für die Argumentwerte gelten die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="e0be8-124">Review the following options for the argument values:</span></span>  
  
    -   <span data-ttu-id="e0be8-125">Ist parent NULL, gibt `GetDescendant` NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="e0be8-125">If parent is NULL, `GetDescendant` returns NULL.</span></span>  
  
    -   <span data-ttu-id="e0be8-126">Ist parent nicht NULL und sind sowohl child1 als auch child2 NULL, dann gibt `GetDescendant` einen parent untergeordneten Knoten zurück.</span><span class="sxs-lookup"><span data-stu-id="e0be8-126">If parent is not NULL, and both child1 and child2 are NULL, `GetDescendant` returns a child of parent.</span></span>  
  
    -   <span data-ttu-id="e0be8-127">Sind parent und child1 nicht NULL und ist child2 NULL, dann gibt `GetDescendant` einen parent untergeordneten Knoten zurück, der größer als child1 ist.</span><span class="sxs-lookup"><span data-stu-id="e0be8-127">If parent and child1 are not NULL, and child2 is NULL, `GetDescendant` returns a child of parent greater than child1.</span></span>  
  
    -   <span data-ttu-id="e0be8-128">Sind parent und child2 nicht NULL und ist child1 NULL, dann gibt `GetDescendant` einen parent untergeordneten Knoten zurück, der kleiner als child2 ist.</span><span class="sxs-lookup"><span data-stu-id="e0be8-128">If parent and child2 are not NULL and child1 is NULL, `GetDescendant` returns a child of parent less than child2.</span></span>  
  
    -   <span data-ttu-id="e0be8-129">Sind parent, child1 und child2 alle nicht NULL, dann gibt `GetDescendant` einen parent untergeordneten Knoten zurück, der größer als child1 und kleiner als child2 ist.</span><span class="sxs-lookup"><span data-stu-id="e0be8-129">If parent, child1, and child2 are all not NULL, `GetDescendant` returns a child of parent greater than child1 and less than child2.</span></span>  
  
     <span data-ttu-id="e0be8-130">Der folgende Code verwendet die Argumente `(NULL, NULL)` des Stammknotens, da außer diesem Stammknoten noch keine Zeilen in der Tabelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e0be8-130">The following code uses the `(NULL, NULL)` arguments of the root parent because there are not yet any rows in the table except the root.</span></span> <span data-ttu-id="e0be8-131">Führen Sie den folgenden Code aus, um **Sariya**einzufügen:</span><span class="sxs-lookup"><span data-stu-id="e0be8-131">Execute the following code to insert **Sariya**:</span></span>  
  
    ```  
    DECLARE @Manager hierarchyid   
    SELECT @Manager = hierarchyid::GetRoot()  
    FROM HumanResources.EmployeeOrg ;  
  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES  
    (@Manager.GetDescendant(NULL, NULL), 46, 'Sariya', 'Marketing Specialist') ;  
  
    ```  
  
2.  <span data-ttu-id="e0be8-132">Wiederholen Sie die Abfrage der ersten Prozedur, um die Tabelle abzufragen und zu sehen, wie die Einträge angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e0be8-132">Repeat the query from the first procedure to query the table and see how the entries appear:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    ```  
  
### <a name="to-create-a-procedure-for-entering-new-nodes"></a><span data-ttu-id="e0be8-133">So erstellen Sie ein Verfahren dafür, neue Knoten einzufügen</span><span class="sxs-lookup"><span data-stu-id="e0be8-133">To create a procedure for entering new nodes</span></span>  
  
1.  <span data-ttu-id="e0be8-134">Um die Eingabe der Daten zu vereinfachen, erstellen Sie die folgende gespeicherte Prozedur, um Mitarbeiterdaten in die Tabelle **EmployeeOrg** einzufügen.</span><span class="sxs-lookup"><span data-stu-id="e0be8-134">To simplify entering data, create the following stored procedure to add employees to the **EmployeeOrg** table.</span></span> <span data-ttu-id="e0be8-135">Die Prozedur akzeptiert Eingabewerte über den Mitarbeiter, der hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e0be8-135">The procedure accepts input values about the employee being added.</span></span> <span data-ttu-id="e0be8-136">Diese Daten bestehen aus der **EmployeeID** des Vorgesetzten des neuen Mitarbeiters, der **EmployeeID** des neuen Mitarbeiters, seinem Vornamen und seinem Titel.</span><span class="sxs-lookup"><span data-stu-id="e0be8-136">This includes the **EmployeeID** of the new employee's manager, the new employee's **EmployeeID** number, and their first name and title.</span></span> <span data-ttu-id="e0be8-137">Die Prozedur verwendet `GetDescendant()` und auch die [GetAncestor ()](/sql/t-sql/data-types/getancestor-database-engine) -Methode.</span><span class="sxs-lookup"><span data-stu-id="e0be8-137">The procedure uses `GetDescendant()` and also the [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="e0be8-138">Führen Sie den folgenden Code aus, um die Prozedur zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e0be8-138">Execute the following code to create the procedure:</span></span>  
  
    ```  
    CREATE PROC AddEmp(@mgrid int, @empid int, @e_name varchar(20), @title varchar(20))   
    AS   
    BEGIN  
       DECLARE @mOrgNode hierarchyid, @lc hierarchyid  
       SELECT @mOrgNode = OrgNode   
       FROM HumanResources.EmployeeOrg   
       WHERE EmployeeID = @mgrid  
       SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
       BEGIN TRANSACTION  
          SELECT @lc = max(OrgNode)   
          FROM HumanResources.EmployeeOrg   
          WHERE OrgNode.GetAncestor(1) =@mOrgNode ;  
  
          INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
          VALUES(@mOrgNode.GetDescendant(@lc, NULL), @empid, @e_name, @title)  
       COMMIT  
    END ;  
    GO  
    ```  
  
2.  <span data-ttu-id="e0be8-139">Im folgenden Beispiel werden die verbliebenen 4 Mitarbeiter, die **David**direkt oder indirekt berichten, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e0be8-139">The following example adds the remaining 4 employees that report directly or indirectly to **David**.</span></span>  
  
    ```  
    EXEC AddEmp 6, 271, 'John', 'Marketing Specialist' ;  
    EXEC AddEmp 6, 119, 'Jill', 'Marketing Specialist' ;  
    EXEC AddEmp 46, 269, 'Wanida', 'Marketing Assistant' ;  
    EXEC AddEmp 271, 272, 'Mary', 'Marketing Assistant' ;  
    ```  
  
3.  <span data-ttu-id="e0be8-140">Führen Sie auch hier wieder die folgende Abfrage aus, um die Zeilen in der Tabelle **EmployeeOrg** zu untersuchen:</span><span class="sxs-lookup"><span data-stu-id="e0be8-140">Again, execute the following query examine the rows in the **EmployeeOrg** table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    /1/1/        0x5AC0  2        269        Wanida  Marketing Assistant  
    /2/          0x68    1        271        John    Marketing Specialist  
    /2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
    /3/          0x78    1        119        Jill    Marketing Specialist  
    ```  
  
 <span data-ttu-id="e0be8-141">Die Tabelle ist jetzt vollständig mit den Daten der Marketingabteilung aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="e0be8-141">The table is now fully populated with the Marketing organization.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e0be8-142">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="e0be8-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e0be8-143">Abfragen einer hierarchischen Tabelle mit hierarchischen Methoden</span><span class="sxs-lookup"><span data-stu-id="e0be8-143">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
  
