---
title: MSSQLSERVER_4104 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4104 (Database Engine error)
ms.assetid: 52dc32d8-97ad-4ef0-834d-2e68f215d007
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbbc28a3e15af6fdc8fd44633ccbdfc46e49149d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620431"
---
# <a name="mssqlserver_4104"></a><span data-ttu-id="85958-102">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="85958-102">MSSQLSERVER_4104</span></span>
    
## <a name="details"></a><span data-ttu-id="85958-103">Details</span><span class="sxs-lookup"><span data-stu-id="85958-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85958-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="85958-104">Product Name</span></span>|<span data-ttu-id="85958-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="85958-105">SQL Server</span></span>|  
|<span data-ttu-id="85958-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="85958-106">Event ID</span></span>|<span data-ttu-id="85958-107">4104</span><span class="sxs-lookup"><span data-stu-id="85958-107">4104</span></span>|  
|<span data-ttu-id="85958-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="85958-108">Event Source</span></span>|<span data-ttu-id="85958-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="85958-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="85958-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="85958-110">Component</span></span>|<span data-ttu-id="85958-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="85958-111">SQLEngine</span></span>|  
|<span data-ttu-id="85958-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="85958-112">Symbolic Name</span></span>|<span data-ttu-id="85958-113">ALG_MULTI_ID_BAD</span><span class="sxs-lookup"><span data-stu-id="85958-113">ALG_MULTI_ID_BAD</span></span>|  
|<span data-ttu-id="85958-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="85958-114">Message Text</span></span>|<span data-ttu-id="85958-115">Der mehrteilige Bezeichner '%.\*ls' konnte nicht gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="85958-115">The multi-part identifier "%.\*ls" could not be bound.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="85958-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="85958-116">Explanation</span></span>  
 <span data-ttu-id="85958-117">Der Name einer Entität in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird *Bezeichner* genannt.</span><span class="sxs-lookup"><span data-stu-id="85958-117">The name of an entity in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is referred to as its *identifier*.</span></span> <span data-ttu-id="85958-118">Sie verwenden Bezeichner immer dann, wenn Sie auf Entitäten verweisen, z. B. durch das Angeben von Spalten- und Tabellennamen in einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="85958-118">You use identifiers whenever you reference entities, for example, by specifying column and table names in a query.</span></span> <span data-ttu-id="85958-119">Ein mehrteiliger Bezeichner enthält einen oder mehrere Qualifizierer als Präfix für den Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="85958-119">A multi-part identifier contains one or more qualifiers as a prefix for the identifier.</span></span> <span data-ttu-id="85958-120">Einem Tabellenbezeichner können z. B. Qualifizierer vorangestellt werden, wie z. B. der Datenbankname und der Name des Schemas, in dem die Tabelle enthalten ist, oder einer Spalten-ID können Qualifizierer vorangestellt werden, wie z. B. ein Tabellenname oder ein Tabellenalias.</span><span class="sxs-lookup"><span data-stu-id="85958-120">For example, a table identifier may be prefixed with qualifiers such as the database name and schema name in which the table is contained, or a column identifier may be prefixed with qualifiers such as a table name or table alias.</span></span>  
  
 <span data-ttu-id="85958-121">Der Fehler 4104 gibt an, dass der angegebene mehrteilige Bezeichner keiner vorhandenen Entität zugeordnet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="85958-121">Error 4104 indicates that the specified multi-part identifier could not be mapped to an existing entity.</span></span> <span data-ttu-id="85958-122">Dieser Fehler kann unter folgenden Bedingungen zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="85958-122">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="85958-123">Der als Präfix für einen Spaltennamen angegebene Qualifizierer stimmt mit keinem in der Abfrage verwendeten Tabellen- oder Aliasnamen überein.</span><span class="sxs-lookup"><span data-stu-id="85958-123">The qualifier supplied as a prefix for a column name does not correspond to any table or alias name used in the query.</span></span>  
  
     <span data-ttu-id="85958-124">In der folgenden Anweisung wird beispielsweise ein Tabellenalias (`Dept`) als Spaltenpräfix verwendet, es wird jedoch in der FROM-Klausel nicht auf den Tabellenalias verwiesen.</span><span class="sxs-lookup"><span data-stu-id="85958-124">For example, the following statement uses a table alias (`Dept`) as a column prefix, but the table alias is not referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department;  
    ```  
  
     <span data-ttu-id="85958-125">In den folgenden Anweisungen wird eine mehrteilige Spalten-ID `TableB.KeyCol` in der WHERE-Klausel als Teil einer JOIN-Bedingung zwischen zwei Tabellen angegeben, auf `TableB` wird in der Abfrage jedoch nicht explizit verwiesen.</span><span class="sxs-lookup"><span data-stu-id="85958-125">In the following statements, a multi-part column identifier `TableB.KeyCol` is specified in the WHERE clause as part of a JOIN condition between two tables, however, `TableB` is not explicitly referenced in the query.</span></span>  
  
    ```  
    DELETE FROM TableA WHERE TableA.KeyCol = TableB.KeyCol;  
    ```  
  
    ```  
    SELECT 'X' FROM TableA WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="85958-126">In der FROM-Klausel wird ein Aliasname für die Tabelle festgelegt, aber der für eine Spalte angegebene Qualifizierer ist der Tabellenname.</span><span class="sxs-lookup"><span data-stu-id="85958-126">An alias name for the table is supplied in the FROM clause, but the qualifier supplied for a column is the table name.</span></span> <span data-ttu-id="85958-127">In der folgenden Anweisung wird beispielsweise der Tabellenname `Department` als Spaltenpräfix verwendet, die Tabelle verfügt jedoch über einen Alias (`Dept`), auf den in der FROM-Klausel verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="85958-127">For example, the following statement uses the table name `Department` as the column prefix; however, the table has an alias (`Dept`) referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department AS Dept;  
    ```  
  
     <span data-ttu-id="85958-128">Falls ein Alias verwendet wird, kann der Tabellenname nicht anderweitig in der Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85958-128">When an alias is used, the table name cannot be used elsewhere in the statement.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="85958-129">kann nicht bestimmen, ob der mehrteilige Bezeichner sich auf eine Spalte bezieht, der eine Tabelle vorangestellt ist, oder auf eine Eigenschaft eines CLR-benutzerdefinierten Datentyps (user-defined data type, UDT), dem eine Spalte vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="85958-129">is unable to determine if the multi-part identifier refers to a column prefixed by a table or to a property of a CLR user-defined data type (UDT) prefixed by a column.</span></span> <span data-ttu-id="85958-130">Dies liegt daran, dass auf Eigenschaften von UDT-Spalten mithilfe eines Punkts als Trennzeichen (.) zwischen dem Spaltennamen und dem Eigenschaftsnamen auf dieselbe Weise verwiesen wird, wie einem Spaltennamen ein Tabellenname vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="85958-130">This happens because properties of UDT columns are referenced by using the period separator (.) between the column name and the property name in the same way that a column name is prefixed with a table name.</span></span> <span data-ttu-id="85958-131">Im folgenden Beispiel werden zwei Tabellen erstellt: `a` und `b`.</span><span class="sxs-lookup"><span data-stu-id="85958-131">The following example creates two tables, `a` and `b`.</span></span> <span data-ttu-id="85958-132">Die Tabelle `b` enthält die Spalte `a`, die einen CLR UDT `dbo.myudt2` als Datentyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="85958-132">Table `b` contains column `a`, which uses a CLR UDT `dbo.myudt2` as its data type.</span></span> <span data-ttu-id="85958-133">Die SELECT-Anweisung enthält einem mehrteiligen Bezeichner `a.c2`.</span><span class="sxs-lookup"><span data-stu-id="85958-133">The SELECT statement contains a multi-part identifier `a.c2`.</span></span>  
  
    ```  
    CREATE TABLE a (c2 int);   
    GO  
    ```  
  
    ```  
    CREATE TABLE b (a dbo.myudt2);   
    GO  
    ```  
  
    ```  
    SELECT a.c2 FROM a, b;   
    ```  
  
     <span data-ttu-id="85958-134">Wenn der UDT `myudt2` keine Eigenschaft namens `c2` hat, kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht ermitteln, ob der Bezeichner `a.c2` auf die Spalte `c2` in der Tabelle `a` oder auf die Spalte `a` mit der Eigenschaft `c2` in der Tabelle `b` verweist.</span><span class="sxs-lookup"><span data-stu-id="85958-134">Assuming that the UDT `myudt2` does not have a property named `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot determine whether identifier `a.c2`refers to column `c2` in table `a` or to the column `a`, property `c2` in table `b`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="85958-135">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="85958-135">User Action</span></span>  
  
-   <span data-ttu-id="85958-136">Gleichen Sie die Spaltenpräfixe mit den in der FROM-Klausel der Abfrage angegeben Tabellen- oder Aliasnamen ab.</span><span class="sxs-lookup"><span data-stu-id="85958-136">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="85958-137">Wenn in der FROM-Klausel ein Alias für einen Tabellennamen definiert wurde, kann der Alias nur als Qualifizierer für Spalten verwendet werden, die dieser Tabelle zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="85958-137">If an alias is defined for a table name in the FROM clause, you can only use the alias as a qualifier for columns associated with that table.</span></span>  
  
     <span data-ttu-id="85958-138">Die oben genannten Anweisungen, die auf die `HumanResources.Department`-Tabelle verweisen, können folgendermaßen korrigiert werden:</span><span class="sxs-lookup"><span data-stu-id="85958-138">The statements above that reference the `HumanResources.Department` table can be corrected as follows:</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department AS Dept;  
    GO  
    ```  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department;  
    GO  
    ```  
  
-   <span data-ttu-id="85958-139">Stellen Sie sicher, dass alle Tabellen in der Abfrage angegeben werden und dass die JOIN-Bedingungen zwischen Tabellen ordnungsgemäß angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85958-139">Ensure that all tables are specified in the query and that the JOIN conditions between tables are specified correctly.</span></span> <span data-ttu-id="85958-140">Die oben genannte DELETE-Anweisung kann folgendermaßen korrigiert werden:</span><span class="sxs-lookup"><span data-stu-id="85958-140">The DELETE statement above can be corrected as follows:</span></span>  
  
    ```  
    DELETE FROM dbo.TableA  
    WHERE TableA.KeyCol = (SELECT TableB.KeyCol   
                            FROM TableB   
                            WHERE TableA.KeyCol = TableB.KeyCol);  
    GO  
    ```  
  
     <span data-ttu-id="85958-141">Die oben genannte SELECT-Anweisung für `TableA` kann folgendermaßen korrigiert werden:</span><span class="sxs-lookup"><span data-stu-id="85958-141">The SELECT statement above for `TableA` can be corrected as follows:</span></span>  
  
    ```  
    SELECT 'X' FROM TableA, TableB WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
     <span data-ttu-id="85958-142">oder</span><span class="sxs-lookup"><span data-stu-id="85958-142">or</span></span>  
  
    ```  
    SELECT 'X' FROM TableA INNER JOIN TableB ON TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="85958-143">Verwenden Sie eindeutige, klar definierte Namen für Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="85958-143">Use unique, clearly defined names for identifiers.</span></span> <span data-ttu-id="85958-144">Dadurch wird der Code einfacher zu lesen und zu warten, und das Risiko mehrdeutiger Verweise auf mehrere Entitäten wird minimiert.</span><span class="sxs-lookup"><span data-stu-id="85958-144">Doing so makes your code easier to read and maintain, and it also minimizes the risk of ambiguous references to multiple entities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85958-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85958-145">See Also</span></span>  
 <span data-ttu-id="85958-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="85958-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span></span>  
 [<span data-ttu-id="85958-147">Datenbankbezeichner</span><span class="sxs-lookup"><span data-stu-id="85958-147">Database Identifiers</span></span>](../databases/database-identifiers.md)  
  
  
