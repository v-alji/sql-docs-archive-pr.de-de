---
title: Erstellen einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6781840e6a6c84773f40a6cd0557ccb79b676eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621399"
---
# <a name="create-a-stored-procedure"></a><span data-ttu-id="ae14e-102">Erstellen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="ae14e-102">Create a Stored Procedure</span></span>
  <span data-ttu-id="ae14e-103">In diesem Thema wird das Erstellen einer gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] und der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung CREATE PROCEDURE beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae14e-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE statement.</span></span>  
  
##  <a name="Top"></a>   
-   <span data-ttu-id="ae14e-104">**Vorbereitungen:**  [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ae14e-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="ae14e-105">**So erstellen Sie eine Prozedur mithilfe von:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="ae14e-105">**To create a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ae14e-106">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ae14e-106">Permissions</span></span>  
 <span data-ttu-id="ae14e-107">Erfordert die CREATE PROCEDURE-Berechtigung in der Datenbank und die ALTER-Berechtigung auf dem Schema, in dem die Prozedur erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ae14e-107">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
##  <a name="how-to-create-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="ae14e-108">So erstellen Sie eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="ae14e-108">How to Create a Stored Procedure</span></span>  
 <span data-ttu-id="ae14e-109">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ae14e-109">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="ae14e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae14e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="ae14e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae14e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ae14e-112">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae14e-112">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ae14e-113">**So erstellen Sie eine Prozedur im Objekt-Explorer**</span><span class="sxs-lookup"><span data-stu-id="ae14e-113">**To create a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="ae14e-114">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="ae14e-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ae14e-115">Erweitern Sie **Datenbanken**, erweitern Sie die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="ae14e-116">Klicken Sie mit der rechten Maustaste auf **Gespeicherte Prozeduren**, und klicken Sie dann auf **Neue gespeicherte Prozedur**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-116">Right-click **Stored Procedures**, and then click **New Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="ae14e-117">Klicken Sie im Menü **Abfrage** auf **Werte für Vorlagenparameter angeben**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="ae14e-118">Geben Sie im Dialogfeld **Werte für Vorlagenparameter angeben** die folgenden Werte für die angezeigten Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="ae14e-118">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="ae14e-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae14e-119">Parameter</span></span>|<span data-ttu-id="ae14e-120">Wert</span><span class="sxs-lookup"><span data-stu-id="ae14e-120">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="ae14e-121">Autor</span><span class="sxs-lookup"><span data-stu-id="ae14e-121">Author</span></span>|<span data-ttu-id="ae14e-122">*Ihr Name*</span><span class="sxs-lookup"><span data-stu-id="ae14e-122">*Your name*</span></span>|  
    |<span data-ttu-id="ae14e-123">Erstellt am</span><span class="sxs-lookup"><span data-stu-id="ae14e-123">Create Date</span></span>|<span data-ttu-id="ae14e-124">*Das heutige Datum*</span><span class="sxs-lookup"><span data-stu-id="ae14e-124">*Today's date*</span></span>|  
    |<span data-ttu-id="ae14e-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ae14e-125">Description</span></span>|<span data-ttu-id="ae14e-126">Gibt Mitarbeiterdaten zurück.</span><span class="sxs-lookup"><span data-stu-id="ae14e-126">Returns employee data.</span></span>|  
    |<span data-ttu-id="ae14e-127">Prozedurname</span><span class="sxs-lookup"><span data-stu-id="ae14e-127">Procedure_name</span></span>|<span data-ttu-id="ae14e-128">HumanResources.uspGetEmployeesTest</span><span class="sxs-lookup"><span data-stu-id="ae14e-128">HumanResources.uspGetEmployeesTest</span></span>|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|<span data-ttu-id="ae14e-129">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="ae14e-129">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="ae14e-130">Default_Value_For_Param1</span><span class="sxs-lookup"><span data-stu-id="ae14e-130">Default_Value_For_Param1</span></span>|<span data-ttu-id="ae14e-131">NULL</span><span class="sxs-lookup"><span data-stu-id="ae14e-131">NULL</span></span>|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|<span data-ttu-id="ae14e-132">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="ae14e-132">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="ae14e-133">Default_Value_For_Param2</span><span class="sxs-lookup"><span data-stu-id="ae14e-133">Default_Value_For_Param2</span></span>|<span data-ttu-id="ae14e-134">NULL</span><span class="sxs-lookup"><span data-stu-id="ae14e-134">NULL</span></span>|  
  
6.  <span data-ttu-id="ae14e-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-135">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="ae14e-136">Ersetzen Sie im **Abfrage-Editor**die SELECT-Anweisung durch die folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="ae14e-136">In the **Query Editor**, replace the SELECT statement with the following statement:</span></span>  
  
    ```sql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  <span data-ttu-id="ae14e-137">Zum Testen der Syntax klicken Sie im Menü **Abfrage** auf **Analysieren**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-137">To test the syntax, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="ae14e-138">Wenn eine Fehlermeldung zurückgegeben wird, vergleichen Sie die Anweisungen mit den Informationen oben und korrigieren Sie sie gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="ae14e-138">If an error message is returned, compare the statements with the information above and correct as needed.</span></span>  
  
9. <span data-ttu-id="ae14e-139">Zum Erstellen der Prozedur klicken Sie im Menü **Abfrage** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-139">To create the procedure, from  the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="ae14e-140">Die Prozedur wird als Objekt in der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="ae14e-140">The procedure is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="ae14e-141">Damit die Prozedur im Objekt-Explorer angezeigt wird, klicken Sie mit der rechten Maustaste auf **Gespeicherte Prozeduren** und wählen **Aktualisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="ae14e-141">To see the procedure listed in Object Explorer, right-click **Stored Procedures** and select **Refresh**.</span></span>  
  
11. <span data-ttu-id="ae14e-142">Um die Prozedur auszuführen, klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Namen **HumanResources.uspGetEmployeesTest** der gespeicherten Prozedur, und wählen Sie **Gespeicherte Prozedur ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae14e-142">To run the procedure, in Object Explorer, right-click the stored procedure name **HumanResources.uspGetEmployeesTest** and select **Execute Stored Procedure**.</span></span>  
  
12. <span data-ttu-id="ae14e-143">Geben Sie im Fenster **Prozedur ausführen** den Wert „Margheim“ für den Parameter @LastName und den Wert „Diane“ für den Parameter @FirstName ein.</span><span class="sxs-lookup"><span data-stu-id="ae14e-143">In the **Execute Procedure** window, enter Margheim as the value for the parameter @LastName and enter the value Diane as the value for the parameter @FirstName.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ae14e-144">Überprüfen Sie alle Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="ae14e-144">Validate all user input.</span></span> <span data-ttu-id="ae14e-145">Verketten Sie keine Benutzereingaben, bevor Sie sie überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="ae14e-145">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="ae14e-146">Führen Sie niemals Befehle aus, die sich aus nicht überprüften Benutzereingaben zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="ae14e-146">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ae14e-147">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae14e-147">Using Transact-SQL</span></span>  
 <span data-ttu-id="ae14e-148">**So erstellen Sie eine Prozedur im Abfrage-Editor**</span><span class="sxs-lookup"><span data-stu-id="ae14e-148">**To create a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="ae14e-149">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ae14e-149">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ae14e-150">Klicken Sie im Menü **Datei** auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-150">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ae14e-151">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ae14e-152">In diesem Beispiel wird die gleiche gespeicherte Prozedur wie oben mit einem anderen Prozedurnamen erstellt.</span><span class="sxs-lookup"><span data-stu-id="ae14e-152">This example creates the same stored procedure as above using a different procedure name.</span></span>  
  
    ```sql
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO
    ```  
  
4.  <span data-ttu-id="ae14e-153">Um die Prozedur auszuführen, kopieren Sie das folgende Beispiel und fügen es in ein neues Abfragefenster ein und klicken auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ae14e-153">To run the procedure, copy and paste the following example into a new query window and click **Execute**.</span></span> <span data-ttu-id="ae14e-154">Beachten Sie, dass verschiedene Methoden zum Angeben von Parameterwerten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ae14e-154">Notice that different methods of specifying the parameter values are shown.</span></span>  
  
    ```sql
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ae14e-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae14e-155">See Also</span></span>  
 [<span data-ttu-id="ae14e-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae14e-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  