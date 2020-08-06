---
title: Ändern von benutzerdefinierten Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 891c37b3-cb72-411f-9937-ee87e6d95f34
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cf25fef91834e237f5cbaac26350220840830bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621898"
---
# <a name="modify-user-defined-functions"></a><span data-ttu-id="11c2f-102">Ändern benutzerdefinierter Funktionen</span><span class="sxs-lookup"><span data-stu-id="11c2f-102">Modify User-defined Functions</span></span>
  <span data-ttu-id="11c2f-103">Sie können benutzerdefinierte Funktionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="11c2f-103">You can modify user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="11c2f-104">Durch die Änderung von benutzerdefinierten Funktionen wie unten beschrieben werden die Funktionsberechtigungen nicht geändert. Es ergeben sich auch keine Auswirkungen auf abhängige Funktionen, gespeicherte Prozeduren oder Trigger.</span><span class="sxs-lookup"><span data-stu-id="11c2f-104">Modifying user-defined functions as described below will not change the functions' permissions, nor will it affect any dependent functions, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="11c2f-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="11c2f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="11c2f-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="11c2f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="11c2f-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11c2f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="11c2f-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="11c2f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="11c2f-109">**So ändern Sie eine benutzerdefinierte Funktion mit:**</span><span class="sxs-lookup"><span data-stu-id="11c2f-109">**To modify a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="11c2f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11c2f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="11c2f-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="11c2f-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="11c2f-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="11c2f-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="11c2f-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11c2f-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="11c2f-114">ALTER FUNCTION kann nicht verwendet werden, um irgendeine der folgenden Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="11c2f-114">ALTER FUNCTION cannot be used to perform any of the following actions:</span></span>  
  
-   <span data-ttu-id="11c2f-115">Ändern einer Skalarwertfunktion in eine Tabellenwertfunktion oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="11c2f-115">Change a scalar-valued function to a table-valued function, or vice versa.</span></span>  
  
-   <span data-ttu-id="11c2f-116">Ändern einer Inlinefunktion in eine Funktion mit mehreren Anweisungen oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="11c2f-116">Change an inline function to a multistatement function, or vice versa.</span></span>  
  
-   <span data-ttu-id="11c2f-117">Ändern einer Transact-SQL-Funktion in eine CLR-Funktion oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="11c2f-117">Change a Transact-SQL function to a CLR function, or vice-versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="11c2f-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="11c2f-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="11c2f-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="11c2f-119">Permissions</span></span>  
 <span data-ttu-id="11c2f-120">Erfordert die ALTER-Berechtigung auf der Funktion oder auf dem Schema.</span><span class="sxs-lookup"><span data-stu-id="11c2f-120">Requires ALTER permission on the function or on the schema.</span></span> <span data-ttu-id="11c2f-121">Wenn die Funktion einen benutzerdefinierten Typ angibt, wird die EXECUTE-Berechtigung für den Typ benötigt.</span><span class="sxs-lookup"><span data-stu-id="11c2f-121">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="11c2f-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11c2f-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="11c2f-123">So ändern Sie eine benutzerdefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="11c2f-123">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="11c2f-124">Klicken Sie neben der Datenbank, die die Funktion enthält, die Sie ändern möchten, auf das Pluszeichen.</span><span class="sxs-lookup"><span data-stu-id="11c2f-124">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="11c2f-125">Klicken Sie neben dem Ordner **Programmierbarkeit** auf das Pluszeichen.</span><span class="sxs-lookup"><span data-stu-id="11c2f-125">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="11c2f-126">Klicken Sie neben dem Ordner, der die Funktion enthält, die Sie ändern möchten, auf das Pluszeichen:</span><span class="sxs-lookup"><span data-stu-id="11c2f-126">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="11c2f-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="11c2f-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="11c2f-128">Skalarwertfunktion</span><span class="sxs-lookup"><span data-stu-id="11c2f-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="11c2f-129">Aggregatfunktion</span><span class="sxs-lookup"><span data-stu-id="11c2f-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="11c2f-130">Klicken Sie mit der rechten Maustaste auf die Funktion, die Sie ändern möchten, und klicken Sie dann auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="11c2f-130">Right-click the function you want to modify and select **Modify**.</span></span>  
  
5.  <span data-ttu-id="11c2f-131">Nehmen Sie im Abfragefenster die notwendigen Änderungen an der ALTER FUNCTION-Anweisung vor.</span><span class="sxs-lookup"><span data-stu-id="11c2f-131">In the Query Window, make the necessary changes to the ALTER FUNCTION statement.</span></span>  
  
6.  <span data-ttu-id="11c2f-132">Klicken Sie im Menü **Datei** auf **Speichern**_Funktionsname_.</span><span class="sxs-lookup"><span data-stu-id="11c2f-132">On the **File** menu, click **Save**_function_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="11c2f-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="11c2f-133">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="11c2f-134">So ändern Sie eine benutzerdefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="11c2f-134">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="11c2f-135">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="11c2f-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="11c2f-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="11c2f-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="11c2f-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="11c2f-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Scalar-Valued Function  
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetAccountingEndDate]()  
    RETURNS [datetime]   
    AS   
    BEGIN  
        RETURN DATEADD(millisecond, -2, CONVERT(datetime, '20040701', 112));  
    END;  
    ```  
  
    ```  
    -- Table-Valued Function   
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetContactInformation](@PersonID int)  
    RETURNS @retContactInformation TABLE   
    (  
        -- Columns returned by the function  
        [PersonID] int NOT NULL,   
        [FirstName] [nvarchar](50) NULL,   
        [LastName] [nvarchar](50) NULL,   
        [JobTitle] [nvarchar](50) NULL,  
        [BusinessEntityType] [nvarchar](50) NULL  
    )  
    AS   
    -- Returns the first name, last name, job title and business entity type for the specified contact.  
    -- Since a contact can serve multiple roles, more than one row may be returned.  
    BEGIN  
    IF @PersonID IS NOT NULL   
    BEGIN  
         IF EXISTS(SELECT * FROM [HumanResources].[Employee] e   
         WHERE e.[BusinessEntityID] = @PersonID)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, e.[JobTitle], 'Employee'  
              FROM [HumanResources].[Employee] AS e  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = e.[BusinessEntityID]  
              WHERE e.[BusinessEntityID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Purchasing].[Vendor] AS v  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Vendor Contact'   
              FROM [Purchasing].[Vendor] AS v  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Sales].[Store] AS s  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Store Contact'   
              FROM [Sales].[Store] AS s  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Person].[Person] AS p  
         INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
         WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, NULL, 'Consumer'   
              FROM [Person].[Person] AS p  
              INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
              WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL;   
         END  
    RETURN;  
    END;  
    ```  
  
 <span data-ttu-id="11c2f-138">Weitere Informationen finden Sie unter [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11c2f-138">For more information, see [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span></span>  
  
  
