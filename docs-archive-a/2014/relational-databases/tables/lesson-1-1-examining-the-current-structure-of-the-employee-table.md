---
title: Untersuchen der aktuellen Struktur der Mitarbeitertabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- examining the current structure of the employee
ms.assetid: d546a820-105a-417d-ac35-44a6d1d70ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7f63773ebc1f28fb24f8f1000c3f87ee4d50544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607600"
---
# <a name="examining-the-current-structure-of-the-employee-table"></a><span data-ttu-id="5f323-102">Untersuchen der aktuellen Struktur der Mitarbeitertabelle</span><span class="sxs-lookup"><span data-stu-id="5f323-102">Examining the Current Structure of the Employee Table</span></span>
  <span data-ttu-id="5f323-103"> Die Beispieldatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] enthält im Schema **HumanResources** die Tabelle **Employee**.</span><span class="sxs-lookup"><span data-stu-id="5f323-103">The sample [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database contains an **Employee** table in the **HumanResources** schema.</span></span> <span data-ttu-id="5f323-104">Um Änderungen an der ursprünglichen Tabelle zu vermeiden, wird in diesem Schritt eine Kopie der Tabelle **Employee** mit dem Namen **EmployeeDemo**erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f323-104">To avoid changing the original table, this step makes a copy of the **Employee** table named **EmployeeDemo**.</span></span> <span data-ttu-id="5f323-105">Um das Beispiel zu vereinfachen, kopieren Sie nur fünf Spalten aus der ursprünglichen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5f323-105">To simplify the example, you only copy five columns from the original table.</span></span> <span data-ttu-id="5f323-106">Anschließend Fragen Sie die **HumanResources. Mitarbeiter Demo** -Tabelle ab, um zu überprüfen, wie die Daten in einer Tabelle strukturiert sind, ohne den- `hierarchyid` Datentyp zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f323-106">Then, you query the **HumanResources.EmployeeDemo** table to review how the data is structured in a table without using the `hierarchyid` data type.</span></span>  
  
### <a name="to-copy-the-employee-table"></a><span data-ttu-id="5f323-107">So kopieren Sie die Mitarbeitertabelle</span><span class="sxs-lookup"><span data-stu-id="5f323-107">To copy the Employee table</span></span>  
  
1.  <span data-ttu-id="5f323-108">Führen Sie in einem Abfrage-Editorfenster den folgenden Code aus, um die Tabellenstruktur und die Daten der Tabelle **Employee** in eine neue Tabelle namens **EmployeeDemo**zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="5f323-108">In a Query Editor window, run the following code to copy the table structure and data from the **Employee** table into a new table named **EmployeeDemo**.</span></span>  
  
    ```  
    USE AdventureWorks ;  
    GO  
  
    SELECT EmployeeID, LoginID, ManagerID, Title, HireDate   
    INTO HumanResources.EmployeeDemo   
    FROM HumanResources.Employee ;  
    GO  
    ```  
  
### <a name="to-examine-the-structure-and-data-of-the-employeedemo-table"></a><span data-ttu-id="5f323-109">So untersuchen Sie die Struktur und die Daten der Tabelle EmployeeDemo</span><span class="sxs-lookup"><span data-stu-id="5f323-109">To examine the structure and data of the EmployeeDemo table</span></span>  
  
-   <span data-ttu-id="5f323-110">Die neue Tabelle **EmployeeDemo** stellt eine typische Tabelle einer vorhandenen Datenbank dar, die in eine neue Struktur migriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f323-110">This new **EmployeeDemo** table represents a typical table in an existing database that you might want to migrate to a new structure.</span></span> <span data-ttu-id="5f323-111">Führen Sie in einem Abfrage-Editorfenster den folgenden Code aus, um zu zeigen, wie die Mitarbeiter-Manager-Beziehungen mithilfe eines Selbstjoins dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="5f323-111">In a Query Editor window, run the following code to show how the table uses a self join to display the employee/manager relationships:</span></span>  
  
    ```  
    SELECT   
         Mgr.EmployeeID AS MgrID, Mgr.LoginID AS Manager,   
         Emp.EmployeeID AS E_ID, Emp.LoginID, Emp.Title  
    FROM HumanResources.EmployeeDemo AS Emp  
    LEFT JOIN HumanResources.EmployeeDemo AS Mgr  
    ON Emp.ManagerID = Mgr.EmployeeID  
    ORDER BY MgrID, E_ID  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    MgrID Manager                 E_ID LoginID                  Title  
    NULL NULL                      109 adventure-works\ken0     Chief Executive Officer  
    3    adventure-works\roberto0  4   adventure-works\rob0     Senior Tool Designer  
    3    adventure-works\roberto0  9   adventure-works\gail0    Design Engineer  
    3    adventure-works\roberto0  11  adventure-works\jossef0  Design Engineer  
    3    adventure-works\roberto0  158 adventure-works\dylan0   Research and Development Manager  
    3    adventure-works\roberto0  263 adventure-works\ovidiu0  Senior Tool Designer  
    3    adventure-works\roberto0  267 adventure-works\michael8 Senior Design Engineer  
    3    adventure-works\roberto0  270 adventure-works\sharon0  Design Engineer  
    6    adventure-works\david0    2   adventure-works\kevin0   Marketing Assistant  
    ...  
    ```  
  
     <span data-ttu-id="5f323-112">Die Ausgabe umfasst insgesamt 290 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5f323-112">The results continue for a total of 290 rows.</span></span>  
  
 <span data-ttu-id="5f323-113">Beachten Sie, dass die `ORDER BY`-Klausel bewirkt, dass die Mitarbeiter, die einer Managementebene direkt unterstellt sind, jeweils zusammen aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="5f323-113">Notice that the `ORDER BY` clause caused the output to list the direct reports of each management level together.</span></span> <span data-ttu-id="5f323-114">So werden beispielsweise die sieben Mitarbeiter, die **MgrID** 3 (roberto0) direkt unterstellt sind, nebeneinander aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f323-114">For instance, all seven of the direct reports of **MgrID** 3 (roberto0) are listed adjacent to each other.</span></span> <span data-ttu-id="5f323-115">Es ist zwar nicht unmöglich, aber sehr viel schwieriger, alle Mitarbeiter zu gruppieren, die **MgrID** 3 auch indirekt unterstellt sind.</span><span class="sxs-lookup"><span data-stu-id="5f323-115">Although not impossible, it is much more difficult to group all those who eventually report to **MgrID** 3.</span></span>  
  
 <span data-ttu-id="5f323-116">In der nächsten Aufgabe erstellen Sie eine neue Tabelle mit dem `hierarchyid`-Datentyp und verschieben die Daten in diese neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5f323-116">In the next task, we will create a new table with a `hierarchyid` data type, and move the data into the new table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5f323-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="5f323-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5f323-118">Auffüllen einer Tabelle mit vorhandenen hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="5f323-118">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
  
