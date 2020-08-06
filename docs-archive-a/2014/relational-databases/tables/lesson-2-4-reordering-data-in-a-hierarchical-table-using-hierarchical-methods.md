---
title: Neuanordnen von Daten in einer hierarchischen Tabelle mit hierarchischen Methoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 7b8064c7-62c6-488d-84d2-57a5828fb907
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac6c93f359a81a80af81182120f213564680de0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608473"
---
# <a name="reordering-data-in-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="94481-102">Neuanordnen von Daten in einer hierarchischen Tabelle mit hierarchischen Methoden</span><span class="sxs-lookup"><span data-stu-id="94481-102">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>
  <span data-ttu-id="94481-103">Eine Hierarchie neu zu ordnen, ist eine allgemeine Wartungsaufgabe.</span><span class="sxs-lookup"><span data-stu-id="94481-103">Reorganizing a hierarchy is a common maintenance task.</span></span> <span data-ttu-id="94481-104">In dieser Aufgabe werden wir eine UPDATE-Anweisung mit der [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) -Methode verwenden, um zunächst eine einzelne Zeile an eine neue Position in der Hierarchie zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="94481-104">In this task, we will use an UPDATE statement with the [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) method to first move a single row to a new location in the hierarchy.</span></span> <span data-ttu-id="94481-105">Dann verschieben wir eine ganze Teilstruktur an eine neue Position.</span><span class="sxs-lookup"><span data-stu-id="94481-105">Then we will move an entire sub-tree to a new location.</span></span>  
  
 <span data-ttu-id="94481-106">Die `GetReparentedValue` -Methode benötigt zwei Argumente.</span><span class="sxs-lookup"><span data-stu-id="94481-106">The `GetReparentedValue` method takes two arguments.</span></span> <span data-ttu-id="94481-107">Das erste Argument beschreibt den Teil der Hierarchie, der geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="94481-107">The first argument describes the part of the hierarchy to be modified.</span></span> <span data-ttu-id="94481-108">Möchten Sie zum Beispiel in der Hierarchie **/1/4/2/3/** den Abschnitt **/1/4/** so ändern, dass die Hierarchie zu **/2/1/2/3/** wird, wobei die beiden letzten Knoten (**2/3/**) unverändert bleiben, müssen Sie die zu ändernden Knoten (**/1/4/**) als erstes Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="94481-108">For example, if a hierarchy is **/1/4/2/3/** and you want to change the **/1/4/** section, the hierarchy becomes **/2/1/2/3/**, leaving the last two nodes (**2/3/**) unchanged, you must provide the changing nodes (**/1/4/**) as the first argument.</span></span> <span data-ttu-id="94481-109">Das zweite Argument gibt die neue Hierarchieebene an, in unserem Beispiel **/2/1/**.</span><span class="sxs-lookup"><span data-stu-id="94481-109">The second argument provides the new hierarchy level, in our example **/2/1/**.</span></span> <span data-ttu-id="94481-110">Die zwei Argumente dürfen nicht die gleichen Ebenennummern enthalten.</span><span class="sxs-lookup"><span data-stu-id="94481-110">The two arguments do not have to contain the same number of levels.</span></span>  
  
### <a name="to-move-a-single-row-to-a-new-location-in-the-hierarchy"></a><span data-ttu-id="94481-111">So verschieben Sie eine einzelne Zeile an eine neue Position in der Hierarchie</span><span class="sxs-lookup"><span data-stu-id="94481-111">To move a single row to a new location in the hierarchy</span></span>  
  
1.  <span data-ttu-id="94481-112">Wanida berichtet aktuell Sariya.</span><span class="sxs-lookup"><span data-stu-id="94481-112">Currently Wanida reports to Sariya.</span></span> <span data-ttu-id="94481-113">In dieser Prozedur verschieben Sie Wanida von ihrem aktuellen Knoten **/1/1/** so, dass sie Jill berichtet.</span><span class="sxs-lookup"><span data-stu-id="94481-113">In this procedure, you move Wanida from her current node **/1/1/,** so that she reports to Jill.</span></span> <span data-ttu-id="94481-114">Ihr neuer Knoten wird **/3/1/** , daher ist **/1/** das erste Argument und **/3/** das zweite.</span><span class="sxs-lookup"><span data-stu-id="94481-114">Her new node will become **/3/1/** so **/1/** is the first argument and **/3/** is the second.</span></span> <span data-ttu-id="94481-115">Diese Werte entsprechen den **OrgNode** -Werten von Sariya und Jill.</span><span class="sxs-lookup"><span data-stu-id="94481-115">These correspond to the **OrgNode** values of Sariya and Jill.</span></span> <span data-ttu-id="94481-116">Führen Sie den folgenden Code aus, um Wanida von Sariyas Organisation in die Jills zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="94481-116">Execute the following code to move Wanida from Sariya's organization to Jill's:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @CurrentEmployee = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 269 ;   
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 46 ;   
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 119 ;   
  
    UPDATE HumanResources.EmployeeOrg  
    SET OrgNode = @CurrentEmployee. GetReparentedValue(@OldParent, @NewParent)   
    WHERE OrgNode = @CurrentEmployee ;  
    GO  
    ```  
  
2.  <span data-ttu-id="94481-117">Führen Sie den folgenden Code aus, um die Ergebnisse sehen zu können:</span><span class="sxs-lookup"><span data-stu-id="94481-117">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     <span data-ttu-id="94481-118">Wanida ist jetzt dem Knoten **/3/1/** zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="94481-118">Wanida is now at node **/3/1/**.</span></span>  
  
### <a name="to-reorganize-a-section-of-a-hierarchy"></a><span data-ttu-id="94481-119">So reorganisieren Sie einen Abschnitt einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="94481-119">To reorganize a section of a hierarchy</span></span>  
  
1.  <span data-ttu-id="94481-120">Um zu veranschaulichen, wie eine größere Anzahl von Leuten gleichzeitig verschoben werden kann, führen Sie zunächst den folgenden Code aus, um einen neuen Mitarbeiter einzufügen, der Wanida berichtet:</span><span class="sxs-lookup"><span data-stu-id="94481-120">To demonstrate how to move a larger number of people at the same time, first execute the following code to add an intern reporting to Wanida:</span></span>  
  
    ```  
    EXEC AddEmp 269, 291, 'Kevin', 'Marketing Intern'  ;  
    GO  
    ```  
  
2.  <span data-ttu-id="94481-121">Jetzt berichtet Kevin Wanida, der Jill berichtet, die ihrerseits David berichtet.</span><span class="sxs-lookup"><span data-stu-id="94481-121">Now Kevin reports to Wanida, who reports to Jill, who reports to David.</span></span> <span data-ttu-id="94481-122">Das bedeutet, dass sich Kevin auf Ebene **/3/1/1/** befindet.</span><span class="sxs-lookup"><span data-stu-id="94481-122">That means that Kevin is at level **/3/1/1/**.</span></span> <span data-ttu-id="94481-123">Um alle Untergebenen von Jill zu einem neuen Manager zu verschieben, aktualisieren wir alle Knoten mit dem Wert **/3/** für **OrgNode** mit einem neuen Wert.</span><span class="sxs-lookup"><span data-stu-id="94481-123">To move all of Jill's subordinates to a new manager, we will update all nodes that have **/3/** as their **OrgNode** to a new value.</span></span> <span data-ttu-id="94481-124">Führen Sie den folgenden Code aus, um Wanida so zu aktualisieren, dass sie Sariya unterstellt ist; Kevin hingegen soll weiterhin Wanida unterstellt sein:</span><span class="sxs-lookup"><span data-stu-id="94481-124">Execute the following code to update Wanida to report to Sariya, but keep  Kevin reporting to Wanida:</span></span>  
  
    ```  
    DECLARE @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 119 ; -- Jill  
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ; -- Sariya  
    DECLARE children_cursor CURSOR FOR  
    SELECT OrgNode FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @OldParent;  
    DECLARE @ChildId hierarchyid;  
    OPEN children_cursor  
    FETCH NEXT FROM children_cursor INTO @ChildId;  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
    START:  
        DECLARE @NewId hierarchyid;  
        SELECT @NewId = @NewParent.GetDescendant(MAX(OrgNode), NULL)  
        FROM HumanResources.EmployeeOrg WHERE OrgNode.GetAncestor(1) = @NewParent;  
  
        UPDATE HumanResources.EmployeeOrg  
        SET OrgNode = OrgNode.GetReparentedValue(@ChildId, @NewId)  
        WHERE OrgNode.IsDescendantOf(@ChildId) = 1;  
        IF @@error <> 0 GOTO START -- On error, retry  
            FETCH NEXT FROM children_cursor INTO @ChildId;  
    END  
    CLOSE children_cursor;  
    DEALLOCATE children_cursor;  
  
    ```  
  
3.  <span data-ttu-id="94481-125">Führen Sie den folgenden Code aus, um die Ergebnisse sehen zu können:</span><span class="sxs-lookup"><span data-stu-id="94481-125">Execute the following code to see the result:</span></span>  
  
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
/1/1//2      0x5AD0  3        291        Kevin   Marketing Intern  
/2/          0x68    1        271        John    Marketing Specialist  
/2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
/3/          0x78    1        119        Jill    Marketing Specialist  
```  
  
 <span data-ttu-id="94481-126">Die gesamte Organisationsstruktur, die Jill (sowohl Wanida als auch Kevin) berichtet hatte, berichtet jetzt Sariya.</span><span class="sxs-lookup"><span data-stu-id="94481-126">The entire organizational tree that had reported to Jill (both Wanida and Kevin) now reports to Sariya.</span></span>  
  
 <span data-ttu-id="94481-127">Eine gespeicherte Prozedur für die Neuorganisation eines Bereichs einer Hierarchie finden Sie im Abschnitt „Verschieben von Teilstrukturen“ unter [Hierarchische Daten (SQL Server)](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span><span class="sxs-lookup"><span data-stu-id="94481-127">For a stored procedure to reorganize a section of a hierarchy, see the "Moving Subtrees" section of [Moving Subtrees](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="94481-128">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="94481-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="94481-129">Zusammenfassung: Verwalten von Daten in einer hierarchischen Tabelle</span><span class="sxs-lookup"><span data-stu-id="94481-129">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
  
