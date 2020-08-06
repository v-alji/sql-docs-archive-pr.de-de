---
title: Löschen eines Indexes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- dropping indexes
- indexes [SQL Server], dropping
- index deletions [SQL Server]
ms.assetid: fd38a0ed-26c4-4c76-9ef7-e0a16147329d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4552ba701782e5790f95f54c0c1c66f82573f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724613"
---
# <a name="delete-an-index"></a><span data-ttu-id="b9af3-102">Löschen eines Indexes</span><span class="sxs-lookup"><span data-stu-id="b9af3-102">Delete an Index</span></span>
  <span data-ttu-id="b9af3-103">In diesem Thema wird beschrieben, wie ein Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b9af3-103">This topic describes how to delete (drop) an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b9af3-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b9af3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b9af3-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b9af3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b9af3-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b9af3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b9af3-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b9af3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b9af3-108">**So löschen Sie einen Index mit:**</span><span class="sxs-lookup"><span data-stu-id="b9af3-108">**To delete an index, using:**</span></span>  
  
     [<span data-ttu-id="b9af3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9af3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b9af3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9af3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b9af3-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b9af3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b9af3-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b9af3-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b9af3-113">Indizes, die als Ergebnis einer PRIMARY KEY- oder UNIQUE-Einschränkung erstellt wurden, können mit dieser Methode nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b9af3-113">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be deleted by using this method.</span></span> <span data-ttu-id="b9af3-114">In diesem Fall muss die Einschränkung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b9af3-114">Instead, the constraint must be deleted.</span></span> <span data-ttu-id="b9af3-115">Verwenden Sie [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) mit der DROP CONSTRAINT-Klausel in [!INCLUDE[tsql](../../includes/tsql-md.md)], wenn Sie die Einschränkung und den entsprechenden Index entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9af3-115">To remove the constraint and corresponding index, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) with the DROP CONSTRAINT clause in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b9af3-116">Weitere Informationen finden Sie unter [Delete Primary Keys](../tables/delete-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="b9af3-116">For more information, see [Delete Primary Keys](../tables/delete-primary-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b9af3-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b9af3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b9af3-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b9af3-118">Permissions</span></span>  
 <span data-ttu-id="b9af3-119">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="b9af3-119">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="b9af3-120">Über diese Berechtigungen verfügen standardmäßig die Mitglieder der festen Serverrolle **sysadmin** und die Mitglieder der festen Datenbankrollen **db_ddladmin** und **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="b9af3-120">This permission is granted by default to the **sysadmin** fixed server role and the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b9af3-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9af3-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-index-by-using-object-explorer"></a><span data-ttu-id="b9af3-122">So löschen Sie einen Index mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="b9af3-122">To delete an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="b9af3-123">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, in der Sie einen Index löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9af3-123">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="b9af3-124">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="b9af3-124">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b9af3-125">Erweitern Sie die Tabelle, die den zu löschenden Index enthält.</span><span class="sxs-lookup"><span data-stu-id="b9af3-125">Expand the table that contains the index you want to delete.</span></span>  
  
4.  <span data-ttu-id="b9af3-126">Erweitern Sie den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="b9af3-126">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="b9af3-127">Klicken Sie mit der rechten Maustaste auf den Index, den Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-127">Right-click the index you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="b9af3-128">Überprüfen Sie im Dialogfeld **Objekt löschen** , ob sich der richtige Index im Raster **Zu löschendes Objekt** befindet, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-128">In the **Delete Object** dialog box, verify that the correct index is in the **Object to be deleted** grid and click **OK**.</span></span>  
  
#### <a name="to-delete-an-index-using-table-designer"></a><span data-ttu-id="b9af3-129">So löschen Sie einen Index mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="b9af3-129">To delete an index using Table Designer</span></span>  
  
1.  <span data-ttu-id="b9af3-130">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, in der Sie einen Index löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9af3-130">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="b9af3-131">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="b9af3-131">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b9af3-132">Klicken Sie mit der rechten Maustaste auf die Tabelle, die den zu löschenden Index enthält, und klicken Sie auf Entwurf.</span><span class="sxs-lookup"><span data-stu-id="b9af3-132">Right-click the table that contains the index you want to delete and click Design.</span></span>  
  
4.  <span data-ttu-id="b9af3-133">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-133">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="b9af3-134">Wählen Sie im Dialogfeld **Indizes/Schlüssel** den Index aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9af3-134">In the **Indexes/Keys** dialog box, select the index you want to delete.</span></span>  
  
6.  <span data-ttu-id="b9af3-135">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-135">Click **Delete**.</span></span>  
  
7.  <span data-ttu-id="b9af3-136">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-136">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="b9af3-137">Klicken Sie im Menü **Datei** auf **Save**_Tabellenname_.</span><span class="sxs-lookup"><span data-stu-id="b9af3-137">On the **File** menu, select **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b9af3-138">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9af3-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-index"></a><span data-ttu-id="b9af3-139">So löschen Sie einen Index</span><span class="sxs-lookup"><span data-stu-id="b9af3-139">To delete an index</span></span>  
  
1.  <span data-ttu-id="b9af3-140">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="b9af3-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b9af3-141">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b9af3-142">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b9af3-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- delete the IX_ProductVendor_BusinessEntityID index  
    -- from the Purchasing.ProductVendor table  
    DROP INDEX IX_ProductVendor_BusinessEntityID   
        ON Purchasing.ProductVendor;  
    GO  
    ```  
  
 <span data-ttu-id="b9af3-143">Weitere Informationen finden Sie unter [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9af3-143">For more information, see [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span></span>  
  
  
