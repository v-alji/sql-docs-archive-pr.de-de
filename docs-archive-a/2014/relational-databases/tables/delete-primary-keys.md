---
title: Löschen von Primärschlüsseln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing primary keys
- deleting primary keys
- primary keys [SQL Server], deleting
ms.assetid: c472e465-7bdd-4d74-8fc9-e47fca007ccb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 44fa1271143f813364bfd2109f8147f1d04294a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630588"
---
# <a name="delete-primary-keys"></a><span data-ttu-id="1cf7c-102">Löschen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="1cf7c-102">Delete Primary Keys</span></span>
  <span data-ttu-id="1cf7c-103">Sie können einen Primärschlüssel mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen (DROP).</span><span class="sxs-lookup"><span data-stu-id="1cf7c-103">You can delete (drop) a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1cf7c-104">Wenn der Primärschlüssel gelöscht wird, wird auch der zugehörige Index gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-104">When the primary key is deleted, the corresponding index is deleted.</span></span>  
  
 <span data-ttu-id="1cf7c-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1cf7c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1cf7c-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1cf7c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1cf7c-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1cf7c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1cf7c-108">**So löschen Sie einen Primärschlüssel mit:**</span><span class="sxs-lookup"><span data-stu-id="1cf7c-108">**To delete a primary key using:**</span></span>  
  
     [<span data-ttu-id="1cf7c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cf7c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1cf7c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1cf7c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1cf7c-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1cf7c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1cf7c-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1cf7c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1cf7c-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1cf7c-113">Permissions</span></span>  
 <span data-ttu-id="1cf7c-114">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1cf7c-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cf7c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-object-explorer"></a><span data-ttu-id="1cf7c-116">So löschen Sie eine PRIMARY KEY-Einschränkung mit Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="1cf7c-116">To delete a primary key constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="1cf7c-117">Erweitern Sie im Objekt-Explorer die Tabelle, die den Primärschlüssel enthält, und erweitern Sie dann **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-117">In Object Explorer, expand the table that contains the primary key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="1cf7c-118">Klicken Sie mit der rechten Maustaste auf den Schlüssel, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="1cf7c-119">Überprüfen Sie im Dialogfeld **Objekt löschen** , ob der richtige Schlüssel angegeben worden ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-table-designer"></a><span data-ttu-id="1cf7c-120">So löschen Sie eine PRIMARY KEY-Einschränkung mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="1cf7c-120">To delete a primary key constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="1cf7c-121">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle mit dem Primärschlüssel, und klicken Sie dann auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-121">In Object Explorer, right-click the table with the primary key, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="1cf7c-122">Klicken Sie in der Tabelle mit der rechten Maustaste auf die Zeile mit dem Primärschlüssel, und wählen Sie **Primärschlüssel entfernen** aus, um die Einstellung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-122">In the table grid, right-click the row with the primary key and choose **Remove Primary Key** to toggle the setting from on to off.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cf7c-123">Schließen Sie die Tabelle, ohne die Änderungen zu speichern, um diese Aktion rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-123">To undo this action, close the table without saving the changes.</span></span> <span data-ttu-id="1cf7c-124">Das Löschen eines Primärschlüssels lässt sich nicht rückgängig machen, ohne dass auch alle anderen Änderungen an der Tabelle aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-124">Deleting a primary key cannot be undone without losing all other changes made to the table.</span></span>  
  
3.  <span data-ttu-id="1cf7c-125">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1cf7c-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1cf7c-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint"></a><span data-ttu-id="1cf7c-127">So löschen Sie einen Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="1cf7c-127">To delete a primary key constraint</span></span>  
  
1.  <span data-ttu-id="1cf7c-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1cf7c-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1cf7c-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1cf7c-131">Im Beispiel wird zuerst der Name der Primärschlüsseleinschränkung identifiziert, und dann wird die Einschränkung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1cf7c-131">The example first identifies the name of the primary key constraint and then deletes the constraint.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Return the name of primary key.  
    SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK' AND OBJECT_NAME(parent_object_id) = N'TransactionHistoryArchive';  
    GO  
    -- Delete the primary key constraint.  
    ALTER TABLE Production.TransactionHistoryArchive  
    DROP CONSTRAINT PK_TransactionHistoryArchive_TransactionID;   
    GO  
    ```  
  
 <span data-ttu-id="1cf7c-132">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) und [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="1cf7c-132">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span></span>  
  
###  <a name="TsqlExample"></a>  
