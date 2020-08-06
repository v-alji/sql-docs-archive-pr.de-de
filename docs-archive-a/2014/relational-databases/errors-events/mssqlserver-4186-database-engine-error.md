---
title: MSSQLSERVER_4186 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4186 (Database Engine error)
ms.assetid: 1ae88554-f291-45bc-a186-6f41d9cd0fca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 525c1c3bd6e631044b8bc7f17b2c2a01aeb1ef8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608724"
---
# <a name="mssqlserver_4186"></a><span data-ttu-id="44aff-102">MSSQLSERVER_4186</span><span class="sxs-lookup"><span data-stu-id="44aff-102">MSSQLSERVER_4186</span></span>
    
## <a name="details"></a><span data-ttu-id="44aff-103">Details</span><span class="sxs-lookup"><span data-stu-id="44aff-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44aff-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="44aff-104">Product Name</span></span>|<span data-ttu-id="44aff-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44aff-105">SQL Server</span></span>|  
|<span data-ttu-id="44aff-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="44aff-106">Event ID</span></span>|<span data-ttu-id="44aff-107">4186</span><span class="sxs-lookup"><span data-stu-id="44aff-107">4186</span></span>|  
|<span data-ttu-id="44aff-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="44aff-108">Event Source</span></span>|<span data-ttu-id="44aff-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="44aff-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="44aff-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="44aff-110">Component</span></span>|<span data-ttu-id="44aff-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="44aff-111">SQLEngine</span></span>|  
|<span data-ttu-id="44aff-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="44aff-112">Symbolic Name</span></span>||  
|<span data-ttu-id="44aff-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="44aff-113">Message Text</span></span>|<span data-ttu-id="44aff-114">Auf die Spalte "%ls.%.\*ls" kann in der OUTPUT-Klausel nicht verwiesen werden, weil die Spaltendefinition eine Unterabfrage enthält oder auf eine Funktion verweist, die einen Zugriff auf Benutzer- oder Systemdaten ausführt.</span><span class="sxs-lookup"><span data-stu-id="44aff-114">Column '%ls.%.\*ls' cannot be referenced in the OUTPUT clause because the column definition contains a subquery or references a function that performs user or system data access.</span></span> <span data-ttu-id="44aff-115">Für eine Funktion, die nicht schemagebunden ist, wird standardmäßig angenommen, dass sie auf Daten zugreift.</span><span class="sxs-lookup"><span data-stu-id="44aff-115">A function is assumed by default to perform data access if it is not schemabound.</span></span> <span data-ttu-id="44aff-116">Erwägen Sie, die Unterabfrage bzw. die Funktion aus der Spaltendefinition zu entfernen oder die Spalte aus der OUTPUT-Klausel zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="44aff-116">Consider removing the subquery or function from the column definition or removing the column from the OUTPUT clause.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44aff-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="44aff-117">Explanation</span></span>  
 <span data-ttu-id="44aff-118">Um nicht deterministisches Verhalten zu vermeiden, darf die OUTPUT-Klausel nicht auf eine Spalte einer Sicht oder Inline-Tabellenwertfunktion verweisen, wenn diese Spalte mithilfe einer der folgenden Methoden definiert wurde:</span><span class="sxs-lookup"><span data-stu-id="44aff-118">To prevent nondeterministic behavior, the OUTPUT clause cannot reference a column from a view or inline table-valued function when that column is defined by one of the following methods:</span></span>  
  
-   <span data-ttu-id="44aff-119">Eine Unterabfrage.</span><span class="sxs-lookup"><span data-stu-id="44aff-119">A subquery.</span></span>  
  
-   <span data-ttu-id="44aff-120">Eine benutzerdefinierte Funktion, die auf Benutzer- oder Systemdaten zugreift bzw. bei der davon ausgegangen wird, dass sie einen solchen Zugriff ausführt.</span><span class="sxs-lookup"><span data-stu-id="44aff-120">A user-defined function that performs user or system data access, or is assumed to perform such access.</span></span>  
  
-   <span data-ttu-id="44aff-121">Eine berechnete Spalte, die eine benutzerdefinierte Funktion enthält, die in ihrer Definition auf Benutzer- oder Systemdaten zugreift.</span><span class="sxs-lookup"><span data-stu-id="44aff-121">A computed column that contains a user-defined function that performs user or system data access in its definition.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="44aff-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="44aff-122">Examples</span></span>  
 <span data-ttu-id="44aff-123">**Von einer Unterabfrage definierte Sichtspalte**</span><span class="sxs-lookup"><span data-stu-id="44aff-123">**View Column Defined by a Subquery**</span></span>  
  
 <span data-ttu-id="44aff-124">Im folgenden Beispiel wird eine Sicht erstellt, die eine Unterabfrage in der Auswahlliste verwendet, um die Spalte `State` zu definieren.</span><span class="sxs-lookup"><span data-stu-id="44aff-124">The following example creates a view that uses a subquery in the select list to define the column `State`.</span></span> <span data-ttu-id="44aff-125">Anschließend verweist eine UPDATE-Anweisung auf die `State`-Spalte in der OUTPUT-Klausel und verursacht aufgrund der Unterabfrage in der Auswahlliste einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="44aff-125">An UPDATE statement then references the `State` column in the OUTPUT clause and fails because ob the subquery in the select list.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW dbo.V1  
AS  
    SELECT City,  
-- subquery to return the State name  
           (SELECT Name FROM Person.StateProvince AS sp   
            WHERE sp.StateProvinceID = a.StateProvinceID) AS State  
    FROM Person.Address AS a;  
GO  
--Reference the State column in the OUTPUT clause of an UPDATE statement  
UPDATE dbo.V1   
SET City = City + 'Test'   
OUTPUT deleted.City, deleted.State, inserted.City, inserted.State  
WHERE State = 'Texas';  
GO  
```  
  
 <span data-ttu-id="44aff-126">**Von einer Funktion definierte Sichtspalte**</span><span class="sxs-lookup"><span data-stu-id="44aff-126">**View Column Defined by a Function**</span></span>  
  
 <span data-ttu-id="44aff-127">Im folgenden Beispiel wird eine Sicht erstellt, die eine Datenzugriff-Skalarfunktion `dbo.ufnGetStock` in der Auswahlliste verwendet, um die `CurrentInventory`-Spalte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="44aff-127">The following example creates a view that uses the data accessing, scalar function `dbo.ufnGetStock` in the select list to define the column `CurrentInventory`.</span></span> <span data-ttu-id="44aff-128">Anschließend verweist eine UPDATE-Anweisung auf die `CurrentInventory`-Spalte in der OUTPUT-Klausel.</span><span class="sxs-lookup"><span data-stu-id="44aff-128">An UPDATE statement then references the `CurrentInventory` column in the OUTPUT clause .</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW Production.ReorderLevels  
AS  
    SELECT ProductID, ProductModelID, ReorderPoint,  
           dbo.ufnGetStock(ProductID) AS CurrentInventory  
    FROM Production.Product;  
GO  
  
UPDATE Production.ReorderLevels  
SET ReorderPoint += CurrentInventory  
OUTPUT deleted.ReorderPoint, deleted.CurrentInventory,  
       inserted.ReorderPoint, inserted.CurrentInventory  
WHERE ProductModelID BETWEEN 75 and 80;  
```  
  
## <a name="user-action"></a><span data-ttu-id="44aff-129">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="44aff-129">User Action</span></span>  
 <span data-ttu-id="44aff-130">Sie können Fehler 4186 auf eine der folgenden Arten beheben:</span><span class="sxs-lookup"><span data-stu-id="44aff-130">Error 4186 can be corrected in one of the following ways:</span></span>  
  
-   <span data-ttu-id="44aff-131">Verwenden Sie anstelle von Unterabfragen Joins, um die Spalte in der Sicht oder der Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="44aff-131">Use joins instead of subqueries to define the column in the view or function.</span></span> <span data-ttu-id="44aff-132">Sie können die Sicht `dbo.V1` z. B. wie folgt umschreiben.</span><span class="sxs-lookup"><span data-stu-id="44aff-132">For example, you can rewrite the view `dbo.V1` as follows.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE VIEW dbo.V1  
    AS  
        SELECT City, sp.Name AS State  
        FROM Person.Address AS a   
        JOIN Person.StateProvince AS sp   
        ON sp.StateProvinceID = a.StateProvinceID;  
    ```  
  
-   <span data-ttu-id="44aff-133">Untersuchen Sie die Definition der benutzerdefinierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="44aff-133">Examine the definition of the user-defined function.</span></span> <span data-ttu-id="44aff-134">Wenn die Funktion keinen Zugriff auf Benutzer- oder Systemdaten ausführt, können Sie die Funktion ändern, um die WITH SCHEMABINDING-Klausel einzubinden.</span><span class="sxs-lookup"><span data-stu-id="44aff-134">If the function does not perform user or system data access, alter the function to include the WITH SCHEMABINDING clause.</span></span>  
  
-   <span data-ttu-id="44aff-135">Entfernen Sie die Spalte aus der OUTPUT-Klausel.</span><span class="sxs-lookup"><span data-stu-id="44aff-135">Remove the column from the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44aff-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44aff-136">See Also</span></span>  
 [<span data-ttu-id="44aff-137">OUTPUT Clause &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="44aff-137">OUTPUT Clause &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/output-clause-transact-sql)  
  
  
