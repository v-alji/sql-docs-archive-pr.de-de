---
title: Löschen von benutzerdefinierten Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: db1d668a-23b7-4757-a9c5-1bd848ba7f6d
author: rothja
ms.author: jroth
ms.openlocfilehash: e5f6b2b306c4fe8db08b088d9607cfb19ab0f25e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621901"
---
# <a name="delete-user-defined-functions"></a><span data-ttu-id="6051b-102">Löschen von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="6051b-102">Delete User-defined Functions</span></span>
  <span data-ttu-id="6051b-103">Sie können benutzerdefinierte Funktionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] löschen mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6051b-103">You can delete (drop) user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="6051b-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="6051b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6051b-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="6051b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6051b-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6051b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6051b-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6051b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6051b-108">**So löschen Sie eine benutzerdefinierte Funktion mit:**</span><span class="sxs-lookup"><span data-stu-id="6051b-108">**To delete a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="6051b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6051b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6051b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6051b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6051b-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="6051b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6051b-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6051b-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6051b-113">Sie können die Funktion nicht löschen, wenn Transact-SQL-Funktionen oder -Sichten in der Datenbank vorhanden sind, die auf diese Funktion verweisen und mithilfe von SCHEMABINDING erstellt wurden, oder wenn berechnete Spalten, CHECK-Einschränkungen oder DEFAULT-Einschränkungen vorhanden sind, die auf die Funktion verweisen.</span><span class="sxs-lookup"><span data-stu-id="6051b-113">You will not be able to delete the function if there are Transact-SQL functions or views in the database that reference this function and were created by using SCHEMABINDING, or if there are computed columns, CHECK constraints, or DEFAULT constraints that reference the function.</span></span>  
  
-   <span data-ttu-id="6051b-114">Sie können die Funktion nicht löschen, wenn berechnete Spalten vorhanden sind, die auf diese Funktion verweisen und indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="6051b-114">You will not be able to delete the function if there are computed columns that reference this function and have been indexed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6051b-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6051b-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6051b-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6051b-116">Permissions</span></span>  
 <span data-ttu-id="6051b-117">Erfordert die ALTER-Berechtigung im Schema, zu der die Funktion gehört, oder die CONTROL-Berechtigung für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="6051b-117">Requires ALTER permission on the schema to which the function belongs, or CONTROL permission on the function.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6051b-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6051b-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="6051b-119">So löschen Sie eine benutzerdefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="6051b-119">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="6051b-120">Klicken Sie neben der Datenbank, die die Funktion enthält, die Sie ändern möchten, auf das Pluszeichen.</span><span class="sxs-lookup"><span data-stu-id="6051b-120">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="6051b-121">Klicken Sie neben dem Ordner **Programmierbarkeit** auf das Pluszeichen.</span><span class="sxs-lookup"><span data-stu-id="6051b-121">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="6051b-122">Klicken Sie neben dem Ordner, der die Funktion enthält, die Sie ändern möchten, auf das Pluszeichen:</span><span class="sxs-lookup"><span data-stu-id="6051b-122">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="6051b-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="6051b-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="6051b-124">Skalarwertfunktion</span><span class="sxs-lookup"><span data-stu-id="6051b-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="6051b-125">Aggregatfunktion</span><span class="sxs-lookup"><span data-stu-id="6051b-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="6051b-126">Klicken Sie mit der rechten Maustaste auf die Funktion, die Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="6051b-126">Right-click the function you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="6051b-127">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6051b-127">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6051b-128">Klicken Sie im Dialogfeld **Objekt löschen** auf **Abhängigkeiten anzeigen** , um das Dialogfeld _function_name_**Abhängigkeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6051b-128">Click **Show Dependencies** in the **Delete Object** dialog box to open the _function_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="6051b-129">Es werden alle Objekte angezeigt, die von der Funktion abhängig sind, und alle Objekte, von denen die Funktion abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="6051b-129">This will show all of the objects that depend on the function and all of the objects on which the function depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6051b-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6051b-130">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="6051b-131">So löschen Sie eine benutzerdefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="6051b-131">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="6051b-132">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="6051b-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6051b-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="6051b-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6051b-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6051b-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates function called "Sales.ufn_SalesByStore"  
    USE AdventureWorks2012;  
    GO  
    CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
    RETURNS TABLE  
    AS  
    RETURN   
    (  
        SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
        FROM Production.Product AS P   
        JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
        JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
        JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
        WHERE C.StoreID = @storeid  
        GROUP BY P.ProductID, P.Name  
    );  
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- determines if function exists in database  
    IF OBJECT_ID (N'Sales.fn_SalesByStore', N'IF') IS NOT NULL  
    -- deletes function  
        DROP FUNCTION Sales.fn_SalesByStore;  
    GO  
    ```  
  
 <span data-ttu-id="6051b-135">Weitere Informationen finden Sie unter [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6051b-135">For more information, see [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
  
