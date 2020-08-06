---
title: Erstellen nicht gruppierter Indizes | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fae0c06b1f562dc3fc518a319df1787b3384c0cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724617"
---
# <a name="create-nonclustered-indexes"></a><span data-ttu-id="0a72f-102">Erstellen nicht gruppierter Indizes</span><span class="sxs-lookup"><span data-stu-id="0a72f-102">Create Nonclustered Indexes</span></span>
  <span data-ttu-id="0a72f-103">Sie können nicht gruppierte Indizes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a72f-103">You can create nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0a72f-104">Ein nicht gruppierter Index ist eine von den in einer Tabelle gespeicherten Daten getrennte Indexstruktur, durch die ausgewählte Spalten neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="0a72f-104">A nonclustered index is an index structure separate from the data stored in a table that reorders one or more selected columns.</span></span> <span data-ttu-id="0a72f-105">In vielen Fällen können Daten mithilfe von nicht gruppierten Indizes schneller gefunden werden als mit einer Suche in der zugrunde liegenden Tabelle. Mitunter lassen sich Abfragen vollständig mit den Daten im nicht gruppierten Index beantworten, oder der nicht gruppierte Index kann [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf die Zeilen in der zugrunde liegenden Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="0a72f-105">Nonclustered indexes can often help you find data more quickly than searching the underlying table; queries can sometimes be answered entirely by the data in the nonclustered index, or the nonclustered index can point the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to the rows in the underlying table.</span></span> <span data-ttu-id="0a72f-106">Im Allgemeinen werden nicht gruppierte Indizes erstellt, um die Leistung von häufig verwendeten Abfragen zu verbessern, die nicht vom gruppierten Index abgedeckt werden, oder Zeilen in einer Tabelle ohne gruppierten Index (als Heap bezeichnet) zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0a72f-106">Generally, nonclustered indexes are created to improve the performance of frequently used queries not covered by the clustered index or to locate rows in a table without a clustered index (called a heap).</span></span> <span data-ttu-id="0a72f-107">Sie können mehrere nicht gruppierte Indizes für eine Tabelle oder eine indizierte Sicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a72f-107">You can create multiple nonclustered indexes on a table or indexed view.</span></span>  
  
 <span data-ttu-id="0a72f-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="0a72f-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a72f-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="0a72f-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a72f-110">Typische Implementierungen</span><span class="sxs-lookup"><span data-stu-id="0a72f-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="0a72f-111">Security</span><span class="sxs-lookup"><span data-stu-id="0a72f-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0a72f-112">**Erstellen eines nicht gruppierten Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="0a72f-112">**To create a nonclustered index, using:**</span></span>  
  
     [<span data-ttu-id="0a72f-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a72f-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0a72f-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a72f-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a72f-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0a72f-115">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a><span data-ttu-id="0a72f-116">Typische Implementierungen</span><span class="sxs-lookup"><span data-stu-id="0a72f-116">Typical Implementations</span></span>  
 <span data-ttu-id="0a72f-117">Nicht gruppierte Indizes werden auf folgende Weise implementiert:</span><span class="sxs-lookup"><span data-stu-id="0a72f-117">Nonclustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="0a72f-118">**Unique-Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="0a72f-118">**UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="0a72f-119">Wenn Sie eine UNIQUE-Einschränkung erstellen, wird ein eindeutiger nicht gruppierter Index erstellt, um standardmäßig eine UNIQUE-Einschränkung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="0a72f-119">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="0a72f-120">Sie können einen eindeutigen gruppierten Index angeben, wenn noch kein gruppierter Index für die Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0a72f-120">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span> <span data-ttu-id="0a72f-121">Weitere Informationen finden Sie unter [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="0a72f-121">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="0a72f-122">**Index unabhängig von einer Einschränkung**</span><span class="sxs-lookup"><span data-stu-id="0a72f-122">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="0a72f-123">Wenn der gruppierte Index nicht angegeben wird, wird standardmäßig ein nicht gruppierter Index erstellt.</span><span class="sxs-lookup"><span data-stu-id="0a72f-123">By default, a nonclustered index is created if clustered is not specified.</span></span> <span data-ttu-id="0a72f-124">Die maximale Anzahl nicht gruppierter Indizes, die pro Tabelle erstellt werden können, beträgt 999.</span><span class="sxs-lookup"><span data-stu-id="0a72f-124">The maximum number of nonclustered indexes that can be created per table is 999.</span></span> <span data-ttu-id="0a72f-125">Dies schließt alle Indizes ein, die durch PRIMARY KEY- oder UNIQUE-Einschränkungen erstellt wurden, jedoch keine XML-Indizes.</span><span class="sxs-lookup"><span data-stu-id="0a72f-125">This includes any indexes created by PRIMARY KEY or UNIQUE constraints, but does not include XML indexes.</span></span>  
  
-   <span data-ttu-id="0a72f-126">**Nicht gruppierter Index für eine indizierte Sicht**</span><span class="sxs-lookup"><span data-stu-id="0a72f-126">**Nonclustered index on an indexed view**</span></span>  
  
     <span data-ttu-id="0a72f-127">Nachdem ein eindeutiger gruppierter Index für eine Sicht erstellt wurde, können nicht gruppierte Indizes erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0a72f-127">After a unique clustered index has been created on a view, nonclustered indexes can be created.</span></span> <span data-ttu-id="0a72f-128">Weitere Informationen finden Sie unter [Erstellen von indizierten Sichten](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="0a72f-128">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a72f-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0a72f-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a72f-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0a72f-130">Permissions</span></span>  
 <span data-ttu-id="0a72f-131">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="0a72f-131">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="0a72f-132">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="0a72f-132">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a72f-133">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a72f-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a><span data-ttu-id="0a72f-134">So erstellen Sie einen nicht gruppierten Index mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="0a72f-134">To create a nonclustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="0a72f-135">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, für die Sie einen nicht gruppierten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a72f-135">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="0a72f-136">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="0a72f-136">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="0a72f-137">Klicken Sie mit der rechten Maustaste auf die Tabelle, für die Sie einen nicht gruppierten Index erstellen möchten, und wählen Sie **Entwurf**aus.</span><span class="sxs-lookup"><span data-stu-id="0a72f-137">Right-click the table on which you want to create a nonclustered index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="0a72f-138">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-138">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="0a72f-139">Klicken Sie im Dialogfeld **Indizes/Schlüssel** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-139">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="0a72f-140">Wählen Sie im Textfeld **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** den neuen Index aus.</span><span class="sxs-lookup"><span data-stu-id="0a72f-140">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="0a72f-141">Wählen Sie im Raster **Als CLUSTERED erstellen**aus, und wählen Sie in der Dropdownliste rechts neben der Eigenschaft **Nein** aus.</span><span class="sxs-lookup"><span data-stu-id="0a72f-141">In the grid, select **Create as Clustered**, and choose **No** from the drop-down list to the right of the property.</span></span>  
  
8.  <span data-ttu-id="0a72f-142">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-142">Click **Close**.</span></span>  
  
9. <span data-ttu-id="0a72f-143">Klicken Sie im Menü **Datei** auf **Save**_table_name_speichern.</span><span class="sxs-lookup"><span data-stu-id="0a72f-143">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a><span data-ttu-id="0a72f-144">So erstellen Sie einen nicht gruppierten Index mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="0a72f-144">To create a nonclustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="0a72f-145">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, für die Sie einen nicht gruppierten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a72f-145">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="0a72f-146">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="0a72f-146">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="0a72f-147">Erweitern Sie die Tabelle, für die Sie einen nicht gruppierten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a72f-147">Expand the table on which you want to create a nonclustered index.</span></span>  
  
4.  <span data-ttu-id="0a72f-148">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes**, zeigen Sie auf **Neuer Index**, und wählen Sie **Nicht gruppierter Index...** aus.</span><span class="sxs-lookup"><span data-stu-id="0a72f-148">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="0a72f-149">Geben Sie in das Dialogfeld **Neuer Index** auf der Seite **Allgemein** den Namen des neuen Indexes in das Feld **Indexname** ein.</span><span class="sxs-lookup"><span data-stu-id="0a72f-149">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="0a72f-150">Klicken Sie unter **Indexschlüsselspalten** auf **Hinzufügen…** .</span><span class="sxs-lookup"><span data-stu-id="0a72f-150">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="0a72f-151">Aktivieren Sie im Dialogfeld **Spalten auswählen aus**_table_name_ die Kontrollkästchen der Tabellenspalten, die dem nicht gruppierten Index hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a72f-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the nonclustered index.</span></span>  
  
8.  <span data-ttu-id="0a72f-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0a72f-153">Klicken Sie im Dialogfeld **Neuer Index** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a72f-154">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a72f-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a><span data-ttu-id="0a72f-155">So erstellen Sie einen nicht gruppierten Index für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="0a72f-155">To create a nonclustered index on a table</span></span>  
  
1.  <span data-ttu-id="0a72f-156">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="0a72f-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0a72f-157">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0a72f-158">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0a72f-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 <span data-ttu-id="0a72f-159">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0a72f-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
