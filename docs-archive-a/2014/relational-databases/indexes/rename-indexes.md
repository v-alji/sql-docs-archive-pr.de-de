---
title: Umbenennen von Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- renaming indexes
- index names [SQL Server]
- indexes [SQL Server], renaming
ms.assetid: d3d612a1-ea1b-4d99-85d2-0a2ad54f4b0e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 184d6e20f7857c5ea3535e77e21a0630ffc7b678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622088"
---
# <a name="rename-indexes"></a><span data-ttu-id="436ae-102">Umbenennen von Indizes</span><span class="sxs-lookup"><span data-stu-id="436ae-102">Rename Indexes</span></span>
  <span data-ttu-id="436ae-103">In diesem Thema wird beschrieben, wie ein Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="436ae-103">This topic describes how to rename an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="436ae-104">Wenn Sie einen Index umbenennen, wird der aktuelle Name des Indexes durch den neuen Namen ersetzt, den Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="436ae-104">Renaming an index replaces the current index name with the new name that you provide.</span></span> <span data-ttu-id="436ae-105">Der angegebene Name muss innerhalb der Tabelle oder Sicht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="436ae-105">The specified name must be unique within the table or view.</span></span> <span data-ttu-id="436ae-106">So können z.B. zwei Tabellen über einen Index mit dem Namen **XPK_1**verfügen; innerhalb derselben Tabelle können jedoch nicht zwei Indizes mit dem Namen **XPK_1**verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="436ae-106">For example, two tables can have an index named **XPK_1**, but the same table cannot have two indexes named **XPK_1**.</span></span> <span data-ttu-id="436ae-107">Sie können keinen Index mit dem gleichen Namen erstellen, den ein vorhandener deaktivierter Index aufweist.</span><span class="sxs-lookup"><span data-stu-id="436ae-107">You cannot create an index with the same name as an existing disabled index.</span></span> <span data-ttu-id="436ae-108">Das Umbenennen eines Indexes bewirkt nicht, dass der Index neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="436ae-108">Renaming an index does not cause the index to be rebuilt.</span></span>  
  
 <span data-ttu-id="436ae-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="436ae-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="436ae-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="436ae-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="436ae-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="436ae-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="436ae-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="436ae-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="436ae-113">**So benennen Sie einen Index um mit:**</span><span class="sxs-lookup"><span data-stu-id="436ae-113">**To rename an index, using:**</span></span>  
  
     [<span data-ttu-id="436ae-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="436ae-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="436ae-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="436ae-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="436ae-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="436ae-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="436ae-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="436ae-117">Limitations and Restrictions</span></span>  
 <span data-ttu-id="436ae-118">Wenn Sie eine PRIMARY KEY- oder eine UNIQUE-Einschränkung für eine Tabelle erstellen, wird für die Tabelle automatisch ein Index erstellt, der denselben Namen wie die Einschränkung erhält.</span><span class="sxs-lookup"><span data-stu-id="436ae-118">When you create a PRIMARY KEY or UNIQUE constraint on a table, an index with the same name as the constraint is automatically created for the table.</span></span> <span data-ttu-id="436ae-119">Da Indexnamen innerhalb der Tabelle eindeutig sein müssen, können Sie keinen Index erstellen oder umbenennen, wenn dieser anschließend denselben Namen wie eine vorhandene PRIMARY KEY- oder UNIQUE-Einschränkung für die Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="436ae-119">Because index names must be unique within the table, you cannot create or rename an index to have the same name as an existing PRIMARY KEY or UNIQUE constraint on the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="436ae-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="436ae-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="436ae-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="436ae-121">Permissions</span></span>  
 <span data-ttu-id="436ae-122">Erfordert die ALTER-Berechtigung für den Index.</span><span class="sxs-lookup"><span data-stu-id="436ae-122">Requires ALTER permission on the index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="436ae-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="436ae-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-an-index-by-using-the-table-designer"></a><span data-ttu-id="436ae-124">So benennen Sie einen Index mit dem Tabellen-Designer um</span><span class="sxs-lookup"><span data-stu-id="436ae-124">To rename an index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="436ae-125">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie einen Index umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="436ae-125">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="436ae-126">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="436ae-126">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="436ae-127">Klicken Sie mit der rechten Maustaste auf die Tabelle, für die Sie einen Index umbenennen möchten, und wählen Sie **Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="436ae-127">Right-click the table on which you want to rename an index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="436ae-128">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="436ae-128">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="436ae-129">Wählen Sie im Textfeld **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** den Index aus, den Sie umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="436ae-129">Select the index you want to rename in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
6.  <span data-ttu-id="436ae-130">Klicken Sie im Raster auf **Name** , und geben Sie in das Textfeld einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="436ae-130">In the grid, click **Name** and type a new name into the text box.</span></span>  
  
7.  <span data-ttu-id="436ae-131">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="436ae-131">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="436ae-132">Klicken Sie im Menü **Datei** auf **Speichern**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="436ae-132">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-rename-an-index-by-using-object-explorer"></a><span data-ttu-id="436ae-133">So benennen Sie einen Index mit dem Objekt-Explorer um</span><span class="sxs-lookup"><span data-stu-id="436ae-133">To rename an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="436ae-134">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie einen Index umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="436ae-134">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="436ae-135">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="436ae-135">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="436ae-136">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, für die Sie einen Index umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="436ae-136">Click the plus sign to expand the table on which you want to rename an index.</span></span>  
  
4.  <span data-ttu-id="436ae-137">Klicken Sie auf das Pluszeichen, um den Ordner **Indizes** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="436ae-137">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="436ae-138">Klicken Sie mit der rechten Maustaste auf den Index, den Sie umbenennen möchten, und wählen Sie **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="436ae-138">Right-click the index you want to rename and select **Rename**.</span></span>  
  
6.  <span data-ttu-id="436ae-139">Geben Sie den neuen Namen des Indexes ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="436ae-139">Type the index's new name and press Enter.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="436ae-140">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="436ae-140">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-an-index"></a><span data-ttu-id="436ae-141">So benennen Sie einen Index um</span><span class="sxs-lookup"><span data-stu-id="436ae-141">To rename an index</span></span>  
  
1.  <span data-ttu-id="436ae-142">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="436ae-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="436ae-143">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="436ae-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="436ae-144">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="436ae-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    --Renames the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table to IX_VendorID.   
  
    EXEC sp_rename N'Purchasing.ProductVendor.IX_ProductVendor_VendorID', N'IX_VendorID', N'INDEX';   
    GO  
    ```  
  
 <span data-ttu-id="436ae-145">Weitere Informationen finden Sie unter [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="436ae-145">For more information, see  [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
