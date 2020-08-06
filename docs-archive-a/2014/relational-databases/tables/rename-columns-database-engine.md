---
title: Umbenennen von Spalten (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], names
- renaming columns
- column names [SQL Server]
ms.assetid: 7c71ec9f-0180-4398-b32a-4bfb7592e75d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6871ab82eaa17aa5e392e6b2bb3f5c60058f9af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620760"
---
# <a name="rename-columns-database-engine"></a><span data-ttu-id="bd79f-102">Umbenennen von Spalten (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="bd79f-102">Rename Columns (Database Engine)</span></span>
  <span data-ttu-id="bd79f-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Tabellenspalte in [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenennen.</span><span class="sxs-lookup"><span data-stu-id="bd79f-103">You can rename a table column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="bd79f-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="bd79f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bd79f-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="bd79f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bd79f-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bd79f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bd79f-107">Security</span><span class="sxs-lookup"><span data-stu-id="bd79f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bd79f-108">**So benennen Sie Spalten um mit**</span><span class="sxs-lookup"><span data-stu-id="bd79f-108">**To rename columns, using:**</span></span>  
  
     [<span data-ttu-id="bd79f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd79f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bd79f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd79f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bd79f-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="bd79f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bd79f-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bd79f-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="bd79f-113">Durch die Umbenennung einer Spalte werden nicht automatisch auch die Verweise auf diese Spalte umbenannt.</span><span class="sxs-lookup"><span data-stu-id="bd79f-113">Renaming a column will not automatically rename references to that column.</span></span> <span data-ttu-id="bd79f-114">Sie müssen Objekte, die auf die umbenannte Spalte verweisen, manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="bd79f-114">You must modify any objects that reference the renamed column manually.</span></span> <span data-ttu-id="bd79f-115">Wenn Sie z. B. eine Tabellenspalte umbenennen und in einem Trigger auf diese Spalte verwiesen wird, müssen Sie den Trigger ändern, sodass er den neuen Spaltennamen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="bd79f-115">For example, if you rename a table column and that column is referenced in a trigger, you must modify the trigger to reflect the new column name.</span></span> <span data-ttu-id="bd79f-116">Verwenden Sie [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) , um Abhängigkeiten vom Objekt aufzulisten, bevor Sie es umbenennen.</span><span class="sxs-lookup"><span data-stu-id="bd79f-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the object before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bd79f-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bd79f-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bd79f-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bd79f-118">Permissions</span></span>  
 <span data-ttu-id="bd79f-119">Erfordert die ALTER-Berechtigung für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="bd79f-119">Requires ALTER permission on the object.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bd79f-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd79f-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-column-using-object-explorer"></a><span data-ttu-id="bd79f-121">So benennen Sie eine Spalte mit Objekt-Explorer um</span><span class="sxs-lookup"><span data-stu-id="bd79f-121">To rename a column using Object Explorer</span></span>  
  
1.  <span data-ttu-id="bd79f-122">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="bd79f-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bd79f-123">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle, in der Sie Spalten umbenennen möchten, und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="bd79f-123">In **Object Explorer**, right-click the table in which you want to rename columns and choose **Rename**.</span></span>  
  
3.  <span data-ttu-id="bd79f-124">Geben Sie einen neuen Spaltennamen ein.</span><span class="sxs-lookup"><span data-stu-id="bd79f-124">Type a new column name.</span></span>  
  
#### <a name="to-rename-a-column-using-table-designer"></a><span data-ttu-id="bd79f-125">So benennen Sie eine Spalte mit dem Tabellen-Designer um</span><span class="sxs-lookup"><span data-stu-id="bd79f-125">To rename a column using Table Designer</span></span>  
  
1.  <span data-ttu-id="bd79f-126">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle, in der Sie Spalten umbenennen möchten, und klicken Sie dann auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="bd79f-126">In **Object Explorer**, right-click the table to which you want to rename columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="bd79f-127">Wählen Sie unter **Spaltenname**den zu ändernden Namen aus, und geben Sie einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="bd79f-127">Under **Column Name**, select the name you want to change and type a new one.</span></span>  
  
3.  <span data-ttu-id="bd79f-128">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="bd79f-128">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd79f-129">Sie können den Spaltennamen auch auf der Registerkarte **Spalteneigenschaften** ändern. Wählen Sie die Spalte aus, deren Name geändert werden soll, und geben Sie für **Name**einen neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="bd79f-129">You can also change the name of a column in the **Column Properties** tab. Select the column whose name you want to change and type a new value for **Name**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bd79f-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd79f-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="bd79f-131">**So benennen Sie eine Spalte um**</span><span class="sxs-lookup"><span data-stu-id="bd79f-131">**To rename a column**</span></span>  
  
#### <a name="to-rename-a-column"></a><span data-ttu-id="bd79f-132">So benennen Sie eine Spalte um</span><span class="sxs-lookup"><span data-stu-id="bd79f-132">To rename a column</span></span>  
  
1.  <span data-ttu-id="bd79f-133">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="bd79f-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bd79f-134">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="bd79f-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bd79f-135">Im folgenden Beispiel wird die Spalte `TerritoryID` in der Tabelle `Sales.SalesTerritory` in `TerrID`umbenannt.</span><span class="sxs-lookup"><span data-stu-id="bd79f-135">The following example renames the column `TerritoryID` in the table `Sales.SalesTerritory` to `TerrID`.</span></span> <span data-ttu-id="bd79f-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bd79f-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename 'Sales.SalesTerritory.TerritoryID', 'TerrID', 'COLUMN';  
    GO  
    ```  
  
 <span data-ttu-id="bd79f-137">Weitere Informationen finden Sie unter [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bd79f-137">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
