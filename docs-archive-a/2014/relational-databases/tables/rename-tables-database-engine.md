---
title: Umbenennen von Tabellen (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
ms.assetid: 2f5c922d-4d71-4694-9fca-28dd99375799
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e73bbb92d8fd3fdcaa7756ce1dcb74d8cd598b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620757"
---
# <a name="rename-tables-database-engine"></a><span data-ttu-id="1b8d3-102">Umbenennen von Tabellen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1b8d3-102">Rename Tables (Database Engine)</span></span>
  <span data-ttu-id="1b8d3-103">Sie können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] eine Tabelle mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenennen.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-103">You can rename a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1b8d3-104">Das Umbenennen einer Tabelle muss sorgfältig überlegt sein.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-104">Think carefully before you rename a table.</span></span> <span data-ttu-id="1b8d3-105">Alle Abfragen, Sichten, benutzerdefinierten Funktionen, gespeicherten Prozeduren und Programme, die auf diese Tabelle verweisen, werden durch die Namensänderung ungültig.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="1b8d3-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1b8d3-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1b8d3-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1b8d3-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1b8d3-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1b8d3-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1b8d3-109">Security</span><span class="sxs-lookup"><span data-stu-id="1b8d3-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1b8d3-110">**So benennen Sie eine Tabelle um mit:**</span><span class="sxs-lookup"><span data-stu-id="1b8d3-110">**To rename a table, using:**</span></span>  
  
     [<span data-ttu-id="1b8d3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b8d3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1b8d3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b8d3-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1b8d3-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1b8d3-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1b8d3-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1b8d3-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1b8d3-115">Durch Umbenennen einer Tabelle werden die Verweise auf diese Tabelle nicht automatisch umbenannt.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-115">Renaming a table will not automatically rename references to that table.</span></span> <span data-ttu-id="1b8d3-116">Sie müssen Objekte, die auf die umbenannte Tabelle verweisen, manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-116">You must manually modify any objects that reference the renamed table.</span></span> <span data-ttu-id="1b8d3-117">Wenn Sie z. B. eine Tabelle umbenennen und in einem Trigger auf diese Tabelle verwiesen wird, müssen Sie den Trigger ändern, sodass er den neuen Tabellennamen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-117">For example, if you rename a table and that table is referenced in a trigger, you must modify the trigger to reflect the new table name.</span></span> <span data-ttu-id="1b8d3-118">Verwenden Sie [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) für eine Auflistung der Abhängigkeiten von der Tabelle, bevor Sie sie umbenennen.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the table before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1b8d3-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1b8d3-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1b8d3-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1b8d3-120">Permissions</span></span>  
 <span data-ttu-id="1b8d3-121">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1b8d3-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b8d3-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="1b8d3-123">So benennen Sie eine Tabelle um</span><span class="sxs-lookup"><span data-stu-id="1b8d3-123">To rename a table</span></span>  
  
1.  <span data-ttu-id="1b8d3-124">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle, die umbenannt werden soll, und wählen Sie im Kontextmenü **Entwerfen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-124">In Object Explorer, right-click the table you want to rename and choose **Design** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="1b8d3-125">Wählen Sie im Menü **Ansicht** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-125">From the **View** menu, choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="1b8d3-126">Geben Sie im Fenster **Eigenschaften** im Feld **Name** einen neuen Namen für die Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-126">In the field for the **Name** value in the **Properties** window, type a new name for the table.</span></span>  
  
4.  <span data-ttu-id="1b8d3-127">Wenn Sie diesen Vorgang abbrechen möchten, drücken Sie die ESC-TASTE, bevor Sie das Feld verlassen.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-127">To cancel this action, press the ESC key before leaving this field.</span></span>  
  
5.  <span data-ttu-id="1b8d3-128">Wählen Sie im Menü **Datei** die Option_Tabellennamen_ **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-128">From the **File** menu choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1b8d3-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b8d3-129">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="1b8d3-130">So benennen Sie eine Tabelle um</span><span class="sxs-lookup"><span data-stu-id="1b8d3-130">To rename a table</span></span>  
  
1.  <span data-ttu-id="1b8d3-131">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1b8d3-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1b8d3-133">Im folgenden Beispiel wird die `SalesTerritory` -Tabelle im Schema `SalesTerr` in `Sales` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-133">The following example renames the `SalesTerritory` table to `SalesTerr` in the `Sales` schema.</span></span> <span data-ttu-id="1b8d3-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1b8d3-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 <span data-ttu-id="1b8d3-135">Weitere Beispiele finden Sie unter [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b8d3-135">For additional examples, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
