---
title: Löschen von Unique-Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2fe2264aed4eb2f292a6bd1e4e565cebe2a833f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619700"
---
# <a name="delete-unique-constraints"></a><span data-ttu-id="6d470-102">Löschen von Unique-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6d470-102">Delete Unique Constraints</span></span>
  <span data-ttu-id="6d470-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine UNIQUE-Einschränkung in [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="6d470-103">You can delete a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6d470-104">Wenn eine Unique-Einschränkung gelöscht wird, werden die Forderung nach Eindeutigkeit für die Werte, die in die Spalte oder Spaltenkombination im Einschränkungsausdruck eingegeben werden, und der zugehörige eindeutige index entfernt.</span><span class="sxs-lookup"><span data-stu-id="6d470-104">Deleting a unique constraint removes the requirement for uniqueness for values entered in the column or combination of columns included in the constraint expression and deletes the corresponding unique index.</span></span>  
  
 <span data-ttu-id="6d470-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="6d470-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6d470-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="6d470-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6d470-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6d470-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6d470-108">**So löschen Sie eine Unique-Einschränkung mit:**</span><span class="sxs-lookup"><span data-stu-id="6d470-108">**To delete a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="6d470-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d470-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6d470-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d470-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6d470-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="6d470-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6d470-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6d470-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6d470-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6d470-113">Permissions</span></span>  
 <span data-ttu-id="6d470-114">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6d470-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6d470-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d470-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a><span data-ttu-id="6d470-116">So löschen Sie eine UNIQUE-Einschränkung im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="6d470-116">To delete a unique constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="6d470-117">Erweitern Sie im Objekt-Explorer die Tabelle, die die eindeutige Einschränkung enthält, und dann erweitern Sie **Einschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="6d470-117">In Object Explorer, expand the table that contains the unique constraint and then expand **Constraints**.</span></span>  
  
2.  <span data-ttu-id="6d470-118">Klicken Sie mit der rechten Maustaste auf den Schlüssel, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="6d470-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="6d470-119">Überprüfen Sie im Dialogfeld **Objekt löschen** , ob der richtige Schlüssel angegeben worden ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d470-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a><span data-ttu-id="6d470-120">So löschen Sie eine eindeutige Einschränkung mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="6d470-120">To delete a unique constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="6d470-121">Klicken Sie im **Objekt-Explorer** mit der rechten Maustaste auf die Tabelle mit der UNIQUE-Einschränkung, und klicken Sie dann auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="6d470-121">In **Object Explorer**, right-click the table with the unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="6d470-122">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="6d470-122">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="6d470-123">Wählen Sie im Dialogfeld **Indizes/Schlüssel** in der Liste **Ausgewählter Primärschlüssel/eindeutiger Schlüssel und Index** den eindeutigen Schlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="6d470-123">In the **Indexes/Keys** dialog box, select the unique key in the **Selected Primary/Unique Key and Index** list.</span></span>  
  
4.  <span data-ttu-id="6d470-124">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="6d470-124">Click **Delete**.</span></span>  
  
5.  <span data-ttu-id="6d470-125">Klicken Sie im Menü **Datei** auf **Tabellenname** _speichern_.</span><span class="sxs-lookup"><span data-stu-id="6d470-125">On the **File** menu, click **Save** _table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6d470-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d470-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-unique-constraint"></a><span data-ttu-id="6d470-127">So löschen Sie eine Unique-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="6d470-127">To delete a unique constraint</span></span>  
  
1.  <span data-ttu-id="6d470-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="6d470-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6d470-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="6d470-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6d470-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6d470-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="6d470-131">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) und [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6d470-131">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
