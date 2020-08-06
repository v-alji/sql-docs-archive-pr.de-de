---
title: Festlegen von Indexoptionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- ALLOW_ROW_LOCKS option
- SORT_IN_TEMPDB option
- DROP_EXISTING clause
- large data, indexes
- PAD_INDEX
- STATISTICS_NORECOMPUTE
- MAXDOP index option, setting
- index options [SQL Server]
- MAXDOP index option
- IGNORE_DUP_KEY option
- ALLOW_PAGE_LOCKS option
- ONLINE
ms.assetid: 7969af33-e94c-41f7-ab89-9d9a2747cd5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9f2d7f0bbbf0d152d3f510ae9ddbe3168634ef96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723870"
---
# <a name="set-index-options"></a><span data-ttu-id="6c580-102">Festlegen von Indexoptionen</span><span class="sxs-lookup"><span data-stu-id="6c580-102">Set Index Options</span></span>
  <span data-ttu-id="6c580-103">In diesem Thema wird beschrieben, wie die Eigenschaften eines Indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6c580-103">This topic describes how to modify the properties of an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6c580-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="6c580-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6c580-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="6c580-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6c580-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6c580-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6c580-107">Security</span><span class="sxs-lookup"><span data-stu-id="6c580-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6c580-108">**So ändern Sie die Eigenschaften eines Indexes mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="6c580-108">**To modify the properties of an index, using:**</span></span>  
  
     [<span data-ttu-id="6c580-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c580-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6c580-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c580-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c580-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="6c580-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6c580-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6c580-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6c580-113">Die folgenden Optionen werden sofort mit der SET-Klausel in der ALTER INDEX-Anweisung für den Index übernommen: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY und STATISTICS_NORECOMPUTE.</span><span class="sxs-lookup"><span data-stu-id="6c580-113">The following options are immediately applied to the index by using the SET clause in the ALTER INDEX statement: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY, and STATISTICS_NORECOMPUTE.</span></span>  
  
-   <span data-ttu-id="6c580-114">Die folgenden Optionen können beim Neuerstellen eines Indexes mithilfe von ALTER INDEX REBUILD oder CREATE INDEX WITH DROP_EXISTING festgelegt werden: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP und DROP_EXISTING (nur CREATE INDEX).</span><span class="sxs-lookup"><span data-stu-id="6c580-114">The following options can be set when you rebuild an index by using either ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP, and DROP_EXISTING (CREATE INDEX only).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c580-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6c580-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c580-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6c580-116">Permissions</span></span>  
 <span data-ttu-id="6c580-117">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="6c580-117">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6c580-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c580-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-table-designer"></a><span data-ttu-id="6c580-119">So ändern Sie die Eigenschaften eines Indexes im Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="6c580-119">To modify the properties of an index in Table Designer</span></span>  
  
1.  <span data-ttu-id="6c580-120">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, in der Sie die Eigenschaften eines Indexes ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6c580-120">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="6c580-121">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6c580-121">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="6c580-122">Klicken Sie mit der rechten Maustaste auf die Tabelle, in der Sie die Eigenschaften eines Indexes ändern möchten, und wählen Sie **Entwurf** aus.</span><span class="sxs-lookup"><span data-stu-id="6c580-122">Right-click the table on which you want to modify an index's properties and select **Design**.</span></span>  
  
4.  <span data-ttu-id="6c580-123">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="6c580-123">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="6c580-124">Wählen Sie den Index aus, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6c580-124">Select the index that you want to modify.</span></span> <span data-ttu-id="6c580-125">Seine Eigenschaften werden im Hauptraster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c580-125">Its properties will show up in the main grid.</span></span>  
  
6.  <span data-ttu-id="6c580-126">Ändern Sie die Einstellungen beliebiger oder aller Eigenschaften, um den Index anzupassen.</span><span class="sxs-lookup"><span data-stu-id="6c580-126">Change the settings of any and all properties to customize the index.</span></span>  
  
7.  <span data-ttu-id="6c580-127">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="6c580-127">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="6c580-128">Klicken Sie im Menü **Datei** auf **Save**_Tabellenname_.</span><span class="sxs-lookup"><span data-stu-id="6c580-128">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-object-explorer"></a><span data-ttu-id="6c580-129">So ändern Sie die Eigenschaften eines Indexes in Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="6c580-129">To modify the properties of an index in Object Explorer</span></span>  
  
1.  <span data-ttu-id="6c580-130">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, in der Sie die Eigenschaften eines Indexes ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6c580-130">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="6c580-131">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6c580-131">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="6c580-132">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie die Eigenschaften eines Indexes ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6c580-132">Click the plus sign to expand the table on which you want to modify an index's properties.</span></span>  
  
4.  <span data-ttu-id="6c580-133">Klicken Sie auf das Pluszeichen, um den Ordner **Indizes** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6c580-133">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="6c580-134">Klicken Sie mit der rechten Maustaste auf den Index, dessen Eigenschaften Sie ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="6c580-134">Right-click the index of which you want to modify the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="6c580-135">Wählen Sie unter **Seite auswählen**die Option **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="6c580-135">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="6c580-136">Ändern Sie die Einstellungen beliebiger oder aller Eigenschaften, um den Index anzupassen.</span><span class="sxs-lookup"><span data-stu-id="6c580-136">Change the settings of any and all properties to customize the index.</span></span>  
  
8.  <span data-ttu-id="6c580-137">Zum Hinzufügen, Entfernen oder Ändern der Position einer Indexspalte wählen Sie auf der Seite **Allgemein** im Dialogfeld **Index Properties –** _Indexname_ (Indexeigenschaften – Indexname) aus.</span><span class="sxs-lookup"><span data-stu-id="6c580-137">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties -** _index_name_ dialog box.</span></span> <span data-ttu-id="6c580-138">Weitere Informationen finden Sie unter [Index Properties F1 Help](index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="6c580-138">For more information, see [Index Properties F1 Help](index-properties-f1-help.md)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6c580-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c580-139">Using Transact-SQL</span></span>  
  
#### <a name="to-see-the-properties-of-all-the-indexes-in-a-table"></a><span data-ttu-id="6c580-140">So sehen Sie die Eigenschaften aller Indizes in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="6c580-140">To see the properties of all the indexes in a table</span></span>  
  
1.  <span data-ttu-id="6c580-141">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="6c580-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c580-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="6c580-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6c580-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6c580-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT i.name AS index_name,   
        i.type_desc,   
        i.is_unique,   
        ds.type_desc AS filegroup_or_partition_scheme,   
        ds.name AS filegroup_or_partition_scheme_name,   
        i.ignore_dup_key,   
        i.is_primary_key,   
        i.is_unique_constraint,   
        i.fill_factor,   
        i.is_padded,   
        i.is_disabled,   
        i.allow_row_locks,   
        i.allow_page_locks,   
        i.has_filter,   
        i.filter_definition  
    FROM sys.indexes AS i  
       INNER JOIN sys.data_spaces AS ds ON i.data_space_id = ds.data_space_id  
    WHERE is_hypothetical = 0 AND i.index_id <> 0   
       AND i.object_id = OBJECT_ID('HumanResources.Employee');   
    GO  
  
    ```  
  
#### <a name="to-set-the-properties-of-an-index"></a><span data-ttu-id="6c580-144">So stellen Sie die Eigenschaften eines Indexes ein</span><span class="sxs-lookup"><span data-stu-id="6c580-144">To set the properties of an index</span></span>  
  
1.  <span data-ttu-id="6c580-145">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="6c580-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c580-146">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="6c580-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6c580-147">Kopieren Sie die folgenden Beispiele, fügen Sie sie in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6c580-147">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="6c580-148">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c580-148">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
