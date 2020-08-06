---
title: Ändern von Daten über eine Ansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
author: stevestein
ms.author: sstein
ms.openlocfilehash: df1eb4a33d1d10e63363e52760dad805b20c0a8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608459"
---
# <a name="modify-data-through-a-view"></a><span data-ttu-id="14993-102">Ändern von Daten über eine Sicht</span><span class="sxs-lookup"><span data-stu-id="14993-102">Modify Data Through a View</span></span>
  <span data-ttu-id="14993-103">Sie können die Daten einer zugrunde liegenden Basistabelle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="14993-103">You can modify the data of an underlying base table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="14993-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="14993-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="14993-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="14993-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="14993-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="14993-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="14993-107">Security</span><span class="sxs-lookup"><span data-stu-id="14993-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="14993-108">**So ändern Sie Tabellendaten durch eine Sicht mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="14993-108">**To modify table data through a view, using:**</span></span>  
  
     [<span data-ttu-id="14993-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="14993-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="14993-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="14993-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="14993-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="14993-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="14993-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="14993-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="14993-113">Weitere Informationen finden Sie im Abschnitt „Aktualisierbare Sichten“ in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="14993-113">See the section 'Updatable Views' in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="14993-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="14993-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="14993-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="14993-115">Permissions</span></span>  
 <span data-ttu-id="14993-116">Erfordert je nach ausgeführter Aktion Berechtigungen für UPDATE, INSERT oder DELETE in der Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="14993-116">Requires UPDATE, INSERT, or DELETE permissions on the target table, depending on the action being performed.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="14993-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="14993-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-table-data-through-a-view"></a><span data-ttu-id="14993-118">So ändern Sie Tabellendaten durch eine Sicht</span><span class="sxs-lookup"><span data-stu-id="14993-118">To modify table data through a view</span></span>  
  
1.  <span data-ttu-id="14993-119">Erweitern Sie in **Objekt-Explorer**die Datenbank, die die Sicht enthält, und erweitern Sie dann **Sichten**.</span><span class="sxs-lookup"><span data-stu-id="14993-119">In **Object Explorer**, expand the database that contains the view and then expand **Views**.</span></span>  
  
2.  <span data-ttu-id="14993-120">Klicken Sie mit der rechten Maustaste auf die Sicht, und wählen Sie **Die ersten 200 Zeilen bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="14993-120">Right-click the view and select **Edit Top 200 Rows**.</span></span>  
  
3.  <span data-ttu-id="14993-121">Sie müssen möglicherweise die SELECT-Anweisung im Bereich **SQL** ändern, um die Zeilen zurückzugeben, die geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14993-121">You may need to modify the SELECT statement in the **SQL** pane to return the rows to be modified.</span></span>  
  
4.  <span data-ttu-id="14993-122">Suchen Sie im Bereich **Ergebnisse** die zu ändernde oder zu löschende Zeile.</span><span class="sxs-lookup"><span data-stu-id="14993-122">In the **Results** pane, locate the row to be changed or deleted.</span></span> <span data-ttu-id="14993-123">Klicken Sie mit der rechten Maustaste auf die zu löschende Zeile, und wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="14993-123">To delete the row, right-click the row and select **Delete**.</span></span> <span data-ttu-id="14993-124">Zum Ändern von Daten in mindestens einer Spalte ändern Sie die Daten in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="14993-124">To change data in one or more columns, modify the data in the column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="14993-125">Sie können keine Zeile löschen, wenn die Sicht auf mehr als eine Basistabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="14993-125">You cannot delete a row if the view references more than one base table.</span></span> <span data-ttu-id="14993-126">Sie können nur Spalten aktualisieren, die zu einer einzelnen Basistabelle gehören.</span><span class="sxs-lookup"><span data-stu-id="14993-126">You can only update columns that belong to a single base table.</span></span>  
  
5.  <span data-ttu-id="14993-127">Zum Einfügen einer Zeile führen Sie einen Bildlauf nach unten zum Ende der Zeilen durch, und fügen Sie die neuen Werte ein.</span><span class="sxs-lookup"><span data-stu-id="14993-127">To insert a row, scroll down to the end of the rows and insert the new values.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="14993-128">Sie können keine Zeile einfügen, wenn die Sicht auf mehr als eine Basistabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="14993-128">You cannot insert a row if the view references more than one base table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="14993-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="14993-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-table-data-through-a-view"></a><span data-ttu-id="14993-130">So aktualisieren Sie Tabellendaten durch eine Sicht</span><span class="sxs-lookup"><span data-stu-id="14993-130">To update table data through a view</span></span>  
  
1.  <span data-ttu-id="14993-131">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="14993-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="14993-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="14993-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="14993-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="14993-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="14993-134">In diesem Beispiel wird der Wert in den Spalten `StartDate` und `EndDate` für einen bestimmten Mitarbeiter geändert, indem in der Sicht `HumanResources.vEmployeeDepartmentHistory`auf Spalten verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="14993-134">This example changes the value in the `StartDate` and `EndDate` columns for a specific employee by referencing columns in the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="14993-135">Diese Sicht gibt Werte von zwei Tabellen zurück.</span><span class="sxs-lookup"><span data-stu-id="14993-135">This view returns values from two tables.</span></span> <span data-ttu-id="14993-136">Diese Anweisung ist erfolgreich, da die geänderten Spalten aus nur einer der Basistabellen stammen.</span><span class="sxs-lookup"><span data-stu-id="14993-136">This statement succeeds because the columns being modified are from only one of the base tables.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 <span data-ttu-id="14993-137">Weitere Informationen finden Sie unter [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="14993-137">For more information, see [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span></span>  
  
#### <a name="to-insert-table-data-through-a-view"></a><span data-ttu-id="14993-138">So fügen Sie Tabellendaten durch eine Sicht ein</span><span class="sxs-lookup"><span data-stu-id="14993-138">To insert table data through a view</span></span>  
  
1.  <span data-ttu-id="14993-139">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="14993-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="14993-140">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="14993-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="14993-141">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="14993-141">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="14993-142">Im Beispiel wird eine neue Zeile in die Basistabelle `HumanResouces.Department` eingefügt, indem die relevanten Spalten der Sicht `HumanResources.vEmployeeDepartmentHistory`angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="14993-142">The example inserts a new row into the base table `HumanResouces.Department` by specifying the relevant columns from the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="14993-143">Die Anweisung ist erfolgreich, da nur Spalten von einer einzelnen Basistabelle angegeben werden. In den anderen Spalten der Basistabelle befinden sich Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="14993-143">The statement succeeds because only columns from a single base table are specified and the other columns in the base table have default values.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 <span data-ttu-id="14993-144">Weitere Informationen finden Sie unter [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="14993-144">For more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span></span>  
  
  
