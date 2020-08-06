---
title: Erstellen gruppierter Indizes | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], clustered indexes
- clustered indexes, creating
- clustered indexes, PRIMARY KEY constraint
- clustered indexes, UNIQUE constraint
- indexes [SQL Server], clustered
ms.assetid: 47148383-c2c7-4f08-a9e4-7016bf2d1d13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 567ff9a01bd93323149168b9e3aa0f34d78aee39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616997"
---
# <a name="create-clustered-indexes"></a><span data-ttu-id="31125-102">Erstellen gruppierter Indizes</span><span class="sxs-lookup"><span data-stu-id="31125-102">Create Clustered Indexes</span></span>
  <span data-ttu-id="31125-103">Sie können gruppierte Indizes für Tabellen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="31125-103">You can create clustered indexes on tables in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="31125-104">Abgesehen von wenigen Ausnahmen sollte jede Tabelle über einen gruppierten Index verfügen.</span><span class="sxs-lookup"><span data-stu-id="31125-104">With few exceptions, every table should have a clustered index.</span></span> <span data-ttu-id="31125-105">Ein gruppierter Index steigert nicht nur die Abfrageleistung, sondern kann bei Bedarf auch neu erstellt oder neu organisiert werden, um die Tabellenfragmentierung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="31125-105">Besides improving query performance, a clustered index can be rebuilt or reorganized on demand to control table fragmentation.</span></span> <span data-ttu-id="31125-106">Ein gruppierter Index kann auch für eine Sicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="31125-106">A clustered index can also be created on a view.</span></span> <span data-ttu-id="31125-107">(Gruppierte Indizes sind im Thema [Beschreibung von gruppierten und nicht gruppierten Indizes](clustered-and-nonclustered-indexes-described.md)definiert.)</span><span class="sxs-lookup"><span data-stu-id="31125-107">(Clustered indexes are defined in the topic [Clustered and Nonclustered Indexes Described](clustered-and-nonclustered-indexes-described.md).)</span></span>  
  
 <span data-ttu-id="31125-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="31125-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="31125-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="31125-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="31125-110">Typische Implementierungen</span><span class="sxs-lookup"><span data-stu-id="31125-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="31125-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="31125-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="31125-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="31125-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="31125-113">**Erstellen eines gruppierten Indexes für eine Tabelle mit:**</span><span class="sxs-lookup"><span data-stu-id="31125-113">**To create a clustered index on a table, using:**</span></span>  
  
     [<span data-ttu-id="31125-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31125-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="31125-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31125-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="31125-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="31125-116">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="31125-117">Typische Implementierungen</span><span class="sxs-lookup"><span data-stu-id="31125-117">Typical Implementations</span></span>  
 <span data-ttu-id="31125-118">Gruppierte Indizes werden auf folgende Weise implementiert:</span><span class="sxs-lookup"><span data-stu-id="31125-118">Clustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="31125-119">**PRIMARY KEY- und UNIQUE-Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="31125-119">**PRIMARY KEY and UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="31125-120">Wenn Sie eine PRIMARY KEY-Einschränkung erstellen, wird automatisch ein eindeutiger gruppierter Index für die Spalte(n) erstellt, wenn noch kein gruppierter Index für die Tabelle vorhanden ist und Sie keinen eindeutigen nicht gruppierten Index angeben.</span><span class="sxs-lookup"><span data-stu-id="31125-120">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="31125-121">Die Primärschlüsselspalte darf keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="31125-121">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="31125-122">Wenn Sie eine UNIQUE-Einschränkung erstellen, wird ein eindeutiger nicht gruppierter Index erstellt, um standardmäßig eine UNIQUE-Einschränkung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="31125-122">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="31125-123">Sie können einen eindeutigen gruppierten Index angeben, wenn noch kein gruppierter Index für die Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="31125-123">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="31125-124">Ein Index, der als Bestandteil der Einschränkung erstellt wird, erhält automatisch denselben Namen wie die Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="31125-124">An index created as part of the constraint is automatically given the same name as the constraint name.</span></span> <span data-ttu-id="31125-125">Weitere Informationen finden Sie unter [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) und [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="31125-125">For more information, see [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) and [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="31125-126">**Index unabhängig von einer Einschränkung**</span><span class="sxs-lookup"><span data-stu-id="31125-126">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="31125-127">Sie können einen gruppierten Index für eine andere Spalte als die Primärschlüsselspalte erstellen, wenn eine nicht gruppierte Primärschlüsseleinschränkung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="31125-127">You can create a clustered index on a column other than primary key column if a nonclustered primary key constraint was specified.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="31125-128">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="31125-128">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="31125-129">Beim Erstellen einer gruppierten Indexstruktur wird Speicherplatz sowohl für die alte Struktur (Quelle) als auch für die neue Struktur (Ziel) in den jeweiligen Dateien und Dateigruppen benötigt.</span><span class="sxs-lookup"><span data-stu-id="31125-129">When a clustered index structure is created, disk space for both the old (source) and new (target) structures is required in their respective files and filegroups.</span></span> <span data-ttu-id="31125-130">Die Speicherzuordnung für die alte Struktur wird erst dann aufgehoben, wenn die vollständige Transaktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="31125-130">The old structure is not deallocated until the complete transaction commits.</span></span> <span data-ttu-id="31125-131">Eventuell wird weiterer Speicherplatz temporär für Sortierzwecke benötigt.</span><span class="sxs-lookup"><span data-stu-id="31125-131">Additional temporary disk space for sorting may also be required.</span></span> <span data-ttu-id="31125-132">Weitere Informationen finden Sie unter [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span><span class="sxs-lookup"><span data-stu-id="31125-132">For more information, see [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span></span>  
  
-   <span data-ttu-id="31125-133">Wenn ein gruppierter Index in einem Heap mit mehreren nicht gruppierten Indizes erstellt wird, müssen alle nicht gruppierten Indizes neu erstellt werden, damit sie statt der Zeilen-ID (RID) den Gruppierungsschlüsselwert enthalten.</span><span class="sxs-lookup"><span data-stu-id="31125-133">If a clustered index is created on a heap with several existing nonclustered indexes, all the nonclustered indexes must be rebuilt so that they contain the clustering key value instead of the row identifier (RID).</span></span> <span data-ttu-id="31125-134">Entsprechend gilt, dass beim Löschen eines gruppierten Indexes in einer Tabelle mit mehreren nicht gruppierten Indizes alle nicht gruppierten Indizes beim Ausführen der DROP-Anweisung neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="31125-134">Similarly, if a clustered index is dropped on a table that has several nonclustered indexes, the nonclustered indexes are all rebuilt as part of the DROP operation.</span></span> <span data-ttu-id="31125-135">Dies kann bei umfangreichen Tabellen sehr lange dauern.</span><span class="sxs-lookup"><span data-stu-id="31125-135">This may take significant time on large tables.</span></span>  
  
     <span data-ttu-id="31125-136">Beim Erstellen von Indizes für umfangreiche Tabellen sollten Sie möglichst mit dem gruppierten Index beginnen und dann die nicht gruppierten Indizes erstellen.</span><span class="sxs-lookup"><span data-stu-id="31125-136">The preferred way to build indexes on large tables is to start with the clustered index and then build any nonclustered indexes.</span></span> <span data-ttu-id="31125-137">Legen Sie gegebenenfalls die ONLINE-Option auf ON fest, wenn Sie Indizes für vorhandene Tabellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="31125-137">Consider setting the ONLINE option to ON when you create indexes on existing tables.</span></span> <span data-ttu-id="31125-138">Beim Wert ON werden keine lang andauernden Tabellensperren aufrechterhalten.</span><span class="sxs-lookup"><span data-stu-id="31125-138">When set to ON, long-term table locks are not held.</span></span> <span data-ttu-id="31125-139">Damit wird die Fortsetzung von Abfragen oder Updates für die zugrunde liegende Tabelle ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="31125-139">This enables queries or updates to the underlying table to continue.</span></span> <span data-ttu-id="31125-140">Weitere Informationen finden Sie unter [Ausführen von Onlineindexvorgängen](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="31125-140">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="31125-141">Der Indexschlüssel eines gruppierten Indexes kann keine Spalten des Datentyps `varchar` enthalten, bei denen Daten in der Zuordnungseinheit ROW_OVERFLOW_DATA vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="31125-141">The index key of a clustered index cannot contain `varchar` columns that have existing data in the ROW_OVERFLOW_DATA allocation unit.</span></span> <span data-ttu-id="31125-142">Wird ein gruppierter Index für eine `varchar`-Spalte erstellt, bei der in der Zuordnungseinheit IN_ROW_DATA Daten vorhanden sind, erzeugen alle nachfolgenden Einfügungen und Updates der Spalte einen Fehler, bei der diese Daten aus der Zeile entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="31125-142">If a clustered index is created on a `varchar` column and the existing data is in the IN_ROW_DATA allocation unit, subsequent insert or update actions on the column that would push the data off-row will fail.</span></span> <span data-ttu-id="31125-143">Zum Abrufen von Informationen zu Tabellen, die ggf. Daten mit Zeilenüberlauf enthalten, verwenden Sie die dynamische Verwaltungsfunktion [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31125-143">To obtain information about tables that might contain row-overflow data, use the [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) dynamic management function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="31125-144">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="31125-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="31125-145">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="31125-145">Permissions</span></span>  
 <span data-ttu-id="31125-146">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="31125-146">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="31125-147">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="31125-147">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="31125-148">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31125-148">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-object-explorer"></a><span data-ttu-id="31125-149">So erstellen Sie einen gruppierten Index mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="31125-149">To create a clustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="31125-150">Erweitern Sie im Objekt-Explorer die Tabelle, für die Sie einen gruppierten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="31125-150">In Object Explorer, expand the table on which you want to create a clustered index.</span></span>  
  
2.  <span data-ttu-id="31125-151">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes**, zeigen Sie auf **Neuer Index**, und wählen Sie **Gruppierter Index** aus.</span><span class="sxs-lookup"><span data-stu-id="31125-151">Right-click the **Indexes** folder, point to **New Index**, and select **Clustered Index...**.</span></span>  
  
3.  <span data-ttu-id="31125-152">Geben Sie in das Dialogfeld **Neuer Index** auf der Seite **Allgemein** den Namen des neuen Indexes in das Feld **Indexname** ein.</span><span class="sxs-lookup"><span data-stu-id="31125-152">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
4.  <span data-ttu-id="31125-153">Klicken Sie unter **Indexschlüsselspalten** auf **Hinzufügen…** .</span><span class="sxs-lookup"><span data-stu-id="31125-153">Under **Index key columns**, click **Add...**.</span></span>  
  
5.  <span data-ttu-id="31125-154">Aktivieren Sie im Dialogfeld **Spalten auswählen aus**_table_name_ das Kontrollkästchen der Tabellenspalte, die dem gruppierten Index hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="31125-154">In the **Select Columns from**_table_name_ dialog box, select the check box of the table column to be added to the clustered index.</span></span>  
  
6.  <span data-ttu-id="31125-155">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="31125-155">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="31125-156">Klicken Sie im Dialogfeld **Neuer Index** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="31125-156">In the **New Index** dialog box, click **OK**.</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-the-table-designer"></a><span data-ttu-id="31125-157">So erstellen Sie einen gruppierten Index mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="31125-157">To create a clustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="31125-158">Erweitern Sie im Objekt-Explorer die Datenbank, für die Sie eine Tabelle mit einem gruppierten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="31125-158">In Object Explorer, expand the database on which you want to create a table with a clustered index.</span></span>  
  
2.  <span data-ttu-id="31125-159">Klicken Sie mit der rechten Maustaste auf den Ordner **Tabellen**, und klicken Sie auf **Neue Tabelle...** .</span><span class="sxs-lookup"><span data-stu-id="31125-159">Right-click the **Tables** folder and click **New Table...**.</span></span>  
  
3.  <span data-ttu-id="31125-160">Erstellen Sie eine neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="31125-160">Create a new table as you normally would.</span></span> <span data-ttu-id="31125-161">Weitere Informationen finden Sie unter [Verbindungsserver &#40;Datenbank-Engine&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="31125-161">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span>  
  
4.  <span data-ttu-id="31125-162">Klicken Sie mit der rechten Maustaste auf die neue Tabelle, und klicken Sie auf **Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="31125-162">Right-click the new table created above and click **Design**.</span></span>  
  
5.  <span data-ttu-id="31125-163">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="31125-163">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
6.  <span data-ttu-id="31125-164">Klicken Sie im Dialogfeld **Indizes/Schlüssel** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="31125-164">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
7.  <span data-ttu-id="31125-165">Wählen Sie im Textfeld **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** den neuen Index aus.</span><span class="sxs-lookup"><span data-stu-id="31125-165">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
8.  <span data-ttu-id="31125-166">Wählen Sie im Datenblatt **Als CLUSTERED erstellen**aus, und wählen Sie in der Dropdownliste rechts neben der Eigenschaft **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="31125-166">In the grid, select **Create as Clustered**, and choose **Yes** from the drop-down list to the right of the property.</span></span>  
  
9. <span data-ttu-id="31125-167">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="31125-167">Click **Close**.</span></span>  
  
10. <span data-ttu-id="31125-168">Klicken Sie im Menü **Datei** auf **Save**_table_name_speichern.</span><span class="sxs-lookup"><span data-stu-id="31125-168">On the **File** menu, click **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="31125-169">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31125-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-clustered-index"></a><span data-ttu-id="31125-170">So erstellen Sie einen gruppierten Index</span><span class="sxs-lookup"><span data-stu-id="31125-170">To create a clustered index</span></span>  
  
1.  <span data-ttu-id="31125-171">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="31125-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="31125-172">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="31125-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="31125-173">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="31125-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Create a new table with three columns.  
    CREATE TABLE dbo.TestTable  
        (TestCol1 int NOT NULL,  
         TestCol2 nchar(10) NULL,  
         TestCol3 nvarchar(50) NULL);  
    GO  
    -- Create a clustered index called IX_TestTable_TestCol1  
    -- on the dbo.TestTable table using the TestCol1 column.  
    CREATE CLUSTERED INDEX IX_TestTable_TestCol1   
        ON dbo.TestTable (TestCol1);   
    GO  
    ```  
  
 <span data-ttu-id="31125-174">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31125-174">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31125-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31125-175">See Also</span></span>  
 <span data-ttu-id="31125-176">[Erstellen von Primärschlüsseln](../tables/create-primary-keys.md) </span><span class="sxs-lookup"><span data-stu-id="31125-176">[Create Primary Keys](../tables/create-primary-keys.md) </span></span>  
 [<span data-ttu-id="31125-177">Erstellen von Unique-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="31125-177">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
