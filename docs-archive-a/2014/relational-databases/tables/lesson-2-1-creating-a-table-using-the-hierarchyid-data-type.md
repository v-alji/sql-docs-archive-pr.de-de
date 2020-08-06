---
title: Erstellen einer Tabelle mit dem hierarchyid-Datentyp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 0d1f361f-336c-4571-99d1-f4813b2d9fc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2c9b59795949e11cabd21b0be8de844b33d73c37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724469"
---
# <a name="creating-a-table-using-the-hierarchyid-data-type"></a><span data-ttu-id="3b327-102">Erstellen einer Tabelle mit dem hierarchyid-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3b327-102">Creating a Table Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="3b327-103">Im folgenden Beispiel wird eine Tabelle namens EmployeeOrg erstellt, die Mitarbeiterdaten zusammen mit ihrer Berichtshierarchie aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="3b327-103">The following example creates a table named EmployeeOrg, which includes employee data together with their reporting hierarchy.</span></span> <span data-ttu-id="3b327-104">Das Beispiel erstellt die neue Tabelle in der Datenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] ; dies ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="3b327-104">The example creates the table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, but that is optional.</span></span> <span data-ttu-id="3b327-105">Um das Beispiel einfach zu halten, enthält die Tabelle nur fünf Spalten:</span><span class="sxs-lookup"><span data-stu-id="3b327-105">To keep the example simple, this table includes only five columns:</span></span>  
  
-   <span data-ttu-id="3b327-106">OrgNode ist eine `hierarchyid`-Spalte, die die hierarchische Beziehung speichert.</span><span class="sxs-lookup"><span data-stu-id="3b327-106">OrgNode is a `hierarchyid` column that stores the hierarchical relationship.</span></span>  
  
-   <span data-ttu-id="3b327-107">OrgLevel ist eine auf der Spalte OrgNode basierende berechnete Spalte, die die Ebene in der Hierarchie speichert.</span><span class="sxs-lookup"><span data-stu-id="3b327-107">OrgLevel is a computed column, based on the OrgNode column that stores each nodes level in the hierarchy.</span></span> <span data-ttu-id="3b327-108">Sie wird für einen Breitensuchindex verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b327-108">It will be used for a breadth-first index.</span></span>  
  
-   <span data-ttu-id="3b327-109">EmployeeID enthält die typische Mitarbeiter-ID, die für Anwendungen wie beispielsweise die Gehaltsdaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b327-109">EmployeeID contains the typical employee identification number that is used for applications such as payroll.</span></span> <span data-ttu-id="3b327-110">Bei der Entwicklung neuer Anwendungen können diese die Spalte OrgNode verwenden, und die eigene Spalte EmployeeID wird nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="3b327-110">In new application development, applications can use the OrgNode column and this separate EmployeeID column is not needed.</span></span>  
  
-   <span data-ttu-id="3b327-111">EmpName enthält den Namen des Angestellten.</span><span class="sxs-lookup"><span data-stu-id="3b327-111">EmpName contains the name of the employee.</span></span>  
  
-   <span data-ttu-id="3b327-112">Title enthält den Titel des Angestellten.</span><span class="sxs-lookup"><span data-stu-id="3b327-112">Title contains the title of the employee.</span></span>  
  
### <a name="to-create-the-employeeorg-table"></a><span data-ttu-id="3b327-113">So erstellen Sie die Tabelle "EmployeeOrg"</span><span class="sxs-lookup"><span data-stu-id="3b327-113">To create the EmployeeOrg table</span></span>  
  
1.  <span data-ttu-id="3b327-114">Führen Sie in einem Abfrage-Editorfenster den folgenden Code aus, um die Tabelle `EmployeeOrg` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b327-114">In a Query Editor window, run the following code to create the `EmployeeOrg` table.</span></span> <span data-ttu-id="3b327-115">Wenn Sie die Spalte `OrgNode` als Primärschlüssel mit einem gruppierten Index angeben, wird ein Tiefensuchindex erstellt:</span><span class="sxs-lookup"><span data-stu-id="3b327-115">Specifying the `OrgNode` column as the primary key with a clustered index will create a depth-first index:</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    CREATE TABLE HumanResources.EmployeeOrg  
    (  
       OrgNode hierarchyid PRIMARY KEY CLUSTERED,  
       OrgLevel AS OrgNode.GetLevel(),  
       EmployeeID int UNIQUE NOT NULL,  
       EmpName varchar(20) NOT NULL,  
       Title varchar(20) NULL  
    ) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="3b327-116">Führen Sie den folgenden Code aus, um einen zusammengesetzten Index für die Spalten `OrgLevel` und `OrgNode` zu erstellen, der effiziente Breitensuchoperationen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="3b327-116">Run the following code to create a composite index on the `OrgLevel` and `OrgNode` columns to support efficient breadth-first searches:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmployeeOrgNc1   
    ON HumanResources.EmployeeOrg(OrgLevel, OrgNode) ;  
    GO  
    ```  
  
 <span data-ttu-id="3b327-117">Die Tabelle ist jetzt bereit, Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3b327-117">The table is now ready for data.</span></span> <span data-ttu-id="3b327-118">Die nächste Aufgabe besteht darin, die Tabelle mithilfe hierarchischer Methoden aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="3b327-118">The next task will populate the table by using hierarchical methods.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3b327-119">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="3b327-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3b327-120">Auffüllen einer hierarchischen Tabelle mit hierarchischen Methoden</span><span class="sxs-lookup"><span data-stu-id="3b327-120">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
