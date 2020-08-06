---
title: Spalten aus einer Tabelle löschen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], deleting
- removing columns
- deleting columns
- dropping columns
ms.assetid: 0d8f6e4f-bc71-4fa3-8615-74249c8e072d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 62f9bca8ee53ae97bb1ac7f37e597b7814a0c370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619032"
---
# <a name="delete-columns-from-a-table"></a><span data-ttu-id="7a784-102">Spalten aus einer Tabelle löschen</span><span class="sxs-lookup"><span data-stu-id="7a784-102">Delete Columns from a Table</span></span>
  <span data-ttu-id="7a784-103">In diesem Thema wird beschrieben, wie Tabellenspalten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="7a784-103">This topic describes how to delete table columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7a784-104">Wenn Sie eine Spalte aus einer Tabelle löschen, wird die Spalte mit allen darin enthaltenen Daten aus der Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7a784-104">When you delete a column from a table, it and all the data it contains are deleted from the database.</span></span> <span data-ttu-id="7a784-105">Diese Aktion kann nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7a784-105">This action cannot be undone.</span></span>  
  
 <span data-ttu-id="7a784-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7a784-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a784-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7a784-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a784-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7a784-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7a784-109">Security</span><span class="sxs-lookup"><span data-stu-id="7a784-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a784-110">**So entfernen Sie eine Spalte aus der Tabelle mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="7a784-110">**To delete a column from a table, using:**</span></span>  
  
     [<span data-ttu-id="7a784-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a784-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a784-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a784-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a784-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7a784-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7a784-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7a784-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7a784-115">Sie können keine Spalte löschen, die eine CHECK-Einschränkung hat.</span><span class="sxs-lookup"><span data-stu-id="7a784-115">You cannot delete a column that has a CHECK constraint.</span></span> <span data-ttu-id="7a784-116">Sie müssen zuerst die Einschränkung löschen.</span><span class="sxs-lookup"><span data-stu-id="7a784-116">You must first delete the constraint.</span></span>  
  
 <span data-ttu-id="7a784-117">Eine Spalte, für die PRIMARY KEY- oder FOREIGN KEY-Einschränkungen oder andere Abhängigkeiten bestehen, können Sie nur mit dem Tabellen-Designer löschen.</span><span class="sxs-lookup"><span data-stu-id="7a784-117">You cannot delete a column that has PRIMARY KEY or FOREIGN KEY constraints or other dependencies except when using the Table Designer.</span></span> <span data-ttu-id="7a784-118">Wenn Sie den Objekt-Explorer oder [!INCLUDE[tsql](../../includes/tsql-md.md)]verwenden, müssen Sie zuerst alle Abhängigkeiten von der Spalte entfernen.</span><span class="sxs-lookup"><span data-stu-id="7a784-118">When using Object Explorer or [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first remove all dependencies on the column.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a784-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7a784-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a784-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7a784-120">Permissions</span></span>  
 <span data-ttu-id="7a784-121">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7a784-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a784-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a784-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-columns-by-using-object-explorer"></a><span data-ttu-id="7a784-123">So löschen Sie Spalten mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="7a784-123">To delete columns by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="7a784-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7a784-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a784-125">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle, aus der Sie Spalten löschen möchten, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="7a784-125">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Delete**.</span></span>  
  
3.  <span data-ttu-id="7a784-126">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a784-126">In **Delete Object** dialog box, click **OK**.</span></span>  
  
 <span data-ttu-id="7a784-127">Wenn die Spalte Einschränkungen oder andere Abhängigkeiten enthält, wird eine Fehlermeldung im Dialogfeld **Objekt löschen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a784-127">If the column contains constraints or other dependencies, an error message will display in the **Delete Object** dialog box.</span></span> <span data-ttu-id="7a784-128">Beheben Sie den Fehler, indem Sie die Einschränkungen löschen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7a784-128">Resolve the error by deleting the referenced constraints.</span></span>  
  
#### <a name="to-delete-columns-by-using-table-designer"></a><span data-ttu-id="7a784-129">So löschen Sie Spalten mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="7a784-129">To delete columns by using Table Designer</span></span>  
  
1.  <span data-ttu-id="7a784-130">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle, aus der Sie Spalten löschen möchten, und wählen Sie **Entwurf**aus.</span><span class="sxs-lookup"><span data-stu-id="7a784-130">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="7a784-131">Klicken Sie mit der rechten Maustaste auf die zu löschende Spalte, und wählen Sie im Kontextmenü die Option **Spalte löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="7a784-131">Right-click the column you want to delete and choose **Delete Column** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="7a784-132">Wenn die betreffende Spalte in eine Beziehung eingebunden ist (FOREIGN KEY oder PRIMARY KEY), werden Sie in einer Meldung aufgefordert, das Löschen der ausgewählten Spalten und der zugehörigen Beziehungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7a784-132">If the column participates in a relationship (FOREIGN KEY or PRIMARY KEY), a message prompts you to confirm the deletion of the selected columns and their relationships.</span></span> <span data-ttu-id="7a784-133">Wählen Sie die Option **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="7a784-133">Choose **Yes**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a784-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a784-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-columns"></a><span data-ttu-id="7a784-135">So löschen Sie Spalten</span><span class="sxs-lookup"><span data-stu-id="7a784-135">To delete columns</span></span>  
  
1.  <span data-ttu-id="7a784-136">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7a784-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a784-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7a784-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a784-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7a784-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.doc_exb DROP COLUMN column_b ;  
    ```  
  
 <span data-ttu-id="7a784-139">Wenn die Spalte Einschränkungen oder andere Abhängigkeiten enthält, wird eine Fehlermeldung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a784-139">If the column contains constraints or other dependencies, an error message will be returned.</span></span> <span data-ttu-id="7a784-140">Beheben Sie den Fehler, indem Sie die Einschränkungen löschen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7a784-140">Resolve the error by deleting the referenced constraints.</span></span>  
  
 <span data-ttu-id="7a784-141">Weitere Beispiele finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a784-141">For additional examples, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
##  <a name="FollowUp"></a>  
