---
title: Umbenennen einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], renaming
- renaming stored procedures
ms.assetid: 5d2e4c68-7e0b-4405-8919-f5b203e46770
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02e1acb528a32ef242e160e0ce5dd0267237c876
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630612"
---
# <a name="rename-a-stored-procedure"></a><span data-ttu-id="271c7-102">Umbenennen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="271c7-102">Rename a Stored Procedure</span></span>
  <span data-ttu-id="271c7-103">In diesem Thema wird beschrieben, wie Sie eine gespeicherte Prozedur in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenennen.</span><span class="sxs-lookup"><span data-stu-id="271c7-103">This topic describes how to rename a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="271c7-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="271c7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="271c7-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="271c7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="271c7-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="271c7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="271c7-107">Security</span><span class="sxs-lookup"><span data-stu-id="271c7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="271c7-108">**Umbenennen einer gespeicherten Prozedur mit:**</span><span class="sxs-lookup"><span data-stu-id="271c7-108">**To rename a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="271c7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="271c7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="271c7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="271c7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="271c7-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="271c7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="271c7-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="271c7-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="271c7-113">Prozedurnamen müssen den Regeln für [Bezeichner](../databases/database-identifiers.md)entsprechen.</span><span class="sxs-lookup"><span data-stu-id="271c7-113">Procedure names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="271c7-114">Beim Umbenennen einer gespeicherten Prozedur wird der Name des entsprechenden Objekts in der Definitionsspalte der **sys.sql_modules** -Katalogsicht nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="271c7-114">Renaming a stored procedure will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="271c7-115">Daher empfiehlt es sich, diesen Objekttyp nicht umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="271c7-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="271c7-116">Löschen Sie die gespeicherte Prozedur stattdessen, und erstellen Sie sie unter dem neuen Namen neu.</span><span class="sxs-lookup"><span data-stu-id="271c7-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="271c7-117">Das Ändern des Namens oder der Definition einer Prozedur kann dazu führen, dass abhängige Objekte fehlschlagen, wenn sie nicht entsprechend den Änderungen an der Prozedur aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="271c7-117">Changing the name or definition of a procedure can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the procedure.</span></span> <span data-ttu-id="271c7-118">Weitere Informationen finden Sie unter [Anzeigen der Abhängigkeiten einer gespeicherten Prozedur](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="271c7-118">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="271c7-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="271c7-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="271c7-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="271c7-120">Permissions</span></span>  
 <span data-ttu-id="271c7-121">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="271c7-121">CREATE PROCEDURE</span></span>  
 <span data-ttu-id="271c7-122">Erfordert die CREATE PROCEDURE-Berechtigung für die Datenbank und die ALTER-Berechtigung für das Schema, in dem die Prozedur erstellt wird, oder die Mitgliedschaft in der festen Datenbankrolle **db_ddladmin**.</span><span class="sxs-lookup"><span data-stu-id="271c7-122">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created, or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
 <span data-ttu-id="271c7-123">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="271c7-123">ALTER PROCEDURE</span></span>  
 <span data-ttu-id="271c7-124">Erfordert die ALTER-Berechtigung für die Prozedur oder die Mitgliedschaft in der festen Datenbankrolle **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="271c7-124">Requires ALTER permission on the procedure or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="271c7-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="271c7-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="271c7-126">So benennen Sie eine gespeicherte Prozedur um</span><span class="sxs-lookup"><span data-stu-id="271c7-126">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="271c7-127">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="271c7-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="271c7-128">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, zu der die Prozedur gehört, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="271c7-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="271c7-129">[Anzeigen der Abhängigkeiten einer gespeicherten Prozedur](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="271c7-129">[Determine the dependencies of the stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
4.  <span data-ttu-id="271c7-130">Erweitern Sie **Gespeicherte Prozeduren**, klicken Sie mit der rechten Maustaste auf die umzubenennende Prozedur, und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="271c7-130">Expand **Stored Procedures**, right-click the procedure to rename, and then click **Rename**.</span></span>  
  
5.  <span data-ttu-id="271c7-131">Ändern Sie den Namen der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="271c7-131">Modify the procedure name.</span></span>  
  
6.  <span data-ttu-id="271c7-132">Ändern Sie den Namen der Prozedur in abhängigen Objekten oder Skripts, in denen auf den Namen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="271c7-132">Modify the procedure name referenced in any dependent objects or scripts.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="271c7-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="271c7-133">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="271c7-134">So benennen Sie eine gespeicherte Prozedur um</span><span class="sxs-lookup"><span data-stu-id="271c7-134">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="271c7-135">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="271c7-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="271c7-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="271c7-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="271c7-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="271c7-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="271c7-138">In diesem Beispiel wird gezeigt, wie eine Prozedur umbenannt wird, indem sie gelöscht und mit einem neuen Namen neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="271c7-138">This example shows how to rename a procedure by dropping the procedure and re-creating the procedure with a new name.</span></span> <span data-ttu-id="271c7-139">Im ersten Beispiel wird die gespeicherte Prozedur `'HumanResources.uspGetAllEmployeesTest`erstellt.</span><span class="sxs-lookup"><span data-stu-id="271c7-139">The first example creates the stored procedure `'HumanResources.uspGetAllEmployeesTest`.</span></span> <span data-ttu-id="271c7-140">Im zweiten Beispiel wird die gespeicherte Prozedur in `HumanResources.uspEveryEmployeeTest`umbenannt.</span><span class="sxs-lookup"><span data-stu-id="271c7-140">The second example renames the stored procedure to `HumanResources.uspEveryEmployeeTest`.</span></span>  
  
```sql  
--Create the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspGetAllEmployeesTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
  
--Rename the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspEveryEmployeeTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="271c7-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="271c7-141">See Also</span></span>  
 <span data-ttu-id="271c7-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="271c7-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span></span>  
 <span data-ttu-id="271c7-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="271c7-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="271c7-144">[Erstellen einer gespeicherten Prozedur](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="271c7-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="271c7-145">[Ändern einer gespeicherten Prozedur](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="271c7-145">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="271c7-146">[Löschen einer gespeicherten Prozedur](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="271c7-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="271c7-147">[Anzeigen der Definition einer gespeicherten Prozedur](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="271c7-147">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="271c7-148">Anzeigen der Abhängigkeiten einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="271c7-148">View the Dependencies of a Stored Procedure</span></span>](view-the-dependencies-of-a-stored-procedure.md)  
  
  
