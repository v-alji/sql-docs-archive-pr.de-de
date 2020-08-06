---
title: Abfragen einer hierarchischen Tabelle mit hierarchischen Methoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c86c8e8678fc821dc3796a511349c1c3498bdb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619033"
---
# <a name="querying-a-hierarchical-table-using-hierarchy-methods"></a><span data-ttu-id="5bdb3-102">Abfragen einer hierarchischen Tabelle mit hierarchischen Methoden</span><span class="sxs-lookup"><span data-stu-id="5bdb3-102">Querying a Hierarchical Table Using Hierarchy Methods</span></span>
  <span data-ttu-id="5bdb3-103">Nachdem die Tabelle HumanResources.EmployeeOrg nun vollständig gefüllt ist, zeigt Ihnen diese Aufgabe, wie Sie die Hierarchie mithilfe einiger der hierarchischen Methoden abfragen können.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-103">Now that the HumanResources.EmployeeOrg table is fully populated, this task will show you how to query the hierarchy using some of the hierarchical methods.</span></span>  
  
### <a name="to-find-subordinate-nodes"></a><span data-ttu-id="5bdb3-104">So suchen Sie untergeordnete Knoten</span><span class="sxs-lookup"><span data-stu-id="5bdb3-104">To find subordinate nodes</span></span>  
  
1.  <span data-ttu-id="5bdb3-105">Sariya ist ein Mitarbeiter unterstellt.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-105">Sariya has one subordinate employee.</span></span> <span data-ttu-id="5bdb3-106">Um den unterstellten Mitarbeiter abzufragen, führen Sie die folgende Abfrage aus, die die [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) -Methode verwendet:</span><span class="sxs-lookup"><span data-stu-id="5bdb3-106">To query for Sariya's subordinates, execute the following query that uses the [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) method:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
     <span data-ttu-id="5bdb3-107">Das Ergebnis listet sowohl Sariya als auch Wanida auf.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-107">The result lists both Sariya and Wanida.</span></span> <span data-ttu-id="5bdb3-108">Sariya wird aufgelistet, weil sie Nachfolger auf Ebene 0 ist.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-108">Sariya is listed because she is the descendant at the 0 level.</span></span> <span data-ttu-id="5bdb3-109">Wanida ist Nachfolger auf Ebene 1.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-109">Wanida is the descendant at the 1 level.</span></span>  
  
2.  <span data-ttu-id="5bdb3-110">Sie können diese Informationen auch mit der [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) -Methode abfragen.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-110">You can also query for this information by using the [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="5bdb3-111">`GetAncestor` übernimmt ein Argument für die Ebene, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-111">`GetAncestor` takes an argument for the level that you are trying to return.</span></span> <span data-ttu-id="5bdb3-112">Da Wanida eine Ebene unter Sariya angesiedelt ist, können Sie `GetAncestor(1)` verwenden, wie der folgende Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5bdb3-112">Since Wanida is one level underneath Sariya, use `GetAncestor(1)` as demonstrated in the following code:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="5bdb3-113">Dieses Mal listet das Ergebnis nur Wanida auf.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-113">This time the result lists only Wanida.</span></span>  
  
3.  <span data-ttu-id="5bdb3-114">Ändern Sie jetzt `@CurrentEmployee` in David (EmployeeID 6) und die Ebene in 2.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-114">Now change the `@CurrentEmployee` to David (EmployeeID 6) and the level to 2.</span></span> <span data-ttu-id="5bdb3-115">Führen Sie folgenden Code aus, um auch Wanida zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="5bdb3-115">Execute the following to also return Wanida:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="5bdb3-116">Dieses Mal erhalten Sie auch Mary, die, zwei Ebenen darunter, ebenfalls David unterstellt ist.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-116">This time, you also receive Mary who also reports to David, two levels down.</span></span>  
  
### <a name="to-use-getroot-and-getlevel"></a><span data-ttu-id="5bdb3-117">So verwenden Sie 'GetRoot' und 'GetLevel'</span><span class="sxs-lookup"><span data-stu-id="5bdb3-117">To use GetRoot, and GetLevel</span></span>  
  
1.  <span data-ttu-id="5bdb3-118">Mit dem Anwachsen der Hierarchie wird es schwieriger zu ermitteln, wo innerhalb der Hierarchie sich die Elemente befinden.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-118">As the hierarchy grows larger it is more difficult to determine where the members are in the hierarchy.</span></span> <span data-ttu-id="5bdb3-119">Verwenden Sie die [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) -Methode, um zu ermitteln, auf welcher Ebene der Hierarchie sich eine Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-119">Use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to find how many levels down each row is in the hierarchy.</span></span> <span data-ttu-id="5bdb3-120">Führen Sie den folgenden Code aus, um die Ebenen aller Zeilen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="5bdb3-120">Execute the following code to view the levels of all the rows:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  <span data-ttu-id="5bdb3-121">Verwenden Sie die [GetRoot](/sql/t-sql/data-types/getroot-database-engine) -Methode, um den Stammknoten in der Hierarchie zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-121">Use the [GetRoot](/sql/t-sql/data-types/getroot-database-engine) method to find the root node in the hierarchy.</span></span> <span data-ttu-id="5bdb3-122">Im folgenden Code wird die einzelne Zeile, die der Stamm ist, zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="5bdb3-122">The following code returns the single row which is the root:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
 <span data-ttu-id="5bdb3-123">In der nächsten Aufgabe wird die Hierarchie neu organisiert.</span><span class="sxs-lookup"><span data-stu-id="5bdb3-123">The next task will reorganize the hierarchy.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5bdb3-124">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="5bdb3-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5bdb3-125">Neuanordnen von Daten in einer hierarchischen Tabelle mit hierarchischen Methoden</span><span class="sxs-lookup"><span data-stu-id="5bdb3-125">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
