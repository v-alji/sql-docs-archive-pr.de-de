---
title: Ändern einer Partitionsfunktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae5bfc09-f27a-4ea9-9518-485278b11674
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bf14e633e62839b1abca7f38f833efab933c18f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696781"
---
# <a name="modify-a-partition-function"></a><span data-ttu-id="f8177-102">Ändern einer Partitionsfunktion</span><span class="sxs-lookup"><span data-stu-id="f8177-102">Modify a Partition Function</span></span>
  <span data-ttu-id="f8177-103">Sie können Tabellen- oder Indexpartitionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ändern, indem Sie mit [!INCLUDE[tsql](../../includes/tsql-md.md)]die angegebene Partitionsanzahl in Einerschritten in der Partitionsfunktion der partitionierten Tabelle bzw. des Indexes hinzufügen oder abziehen.</span><span class="sxs-lookup"><span data-stu-id="f8177-103">You can change the way a table or index is partitioned in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by adding or subtracting the number of partitions specified, in increments of 1, in the partition function of the partitioned table or index by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f8177-104">Beim Hinzufügen einer Partition "teilen" Sie eine vorhandene Partition "auf" und definieren die Partitionsbegrenzungen erneut.</span><span class="sxs-lookup"><span data-stu-id="f8177-104">When you add a partition, you do so by "splitting" an existing partition into two partitions and redefining the boundaries of the new partitions.</span></span> <span data-ttu-id="f8177-105">Wenn Sie eine Partition löschen, "führen" Sie die Begrenzungen von zwei Partitionen "zusammen".</span><span class="sxs-lookup"><span data-stu-id="f8177-105">When you drop a partition, you do so by "merging" the boundaries of two partitions into one.</span></span> <span data-ttu-id="f8177-106">Diese Aktion füllt eine Partition neu und belässt die andere Partition ohne Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="f8177-106">This last action repopulates one partition and leaves the other partition unassigned.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f8177-107">Mehrere Tabellen oder Indizes können dieselbe Partitionsfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8177-107">More than one table or index can use the same partition function.</span></span> <span data-ttu-id="f8177-108">Wenn Sie eine Partitionsfunktion ändern, wirkt sich dies auf alle Funktionen einer einzigen Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="f8177-108">When you modify a partition function, you affect all of them in a single transaction.</span></span> <span data-ttu-id="f8177-109">Überprüfen Sie die Abhängigkeiten der Partitionsfunktion, bevor Sie sie ändern.</span><span class="sxs-lookup"><span data-stu-id="f8177-109">Check the partition function's dependencies before modifying it.</span></span>  
  
 <span data-ttu-id="f8177-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f8177-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f8177-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f8177-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f8177-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f8177-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f8177-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f8177-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f8177-114">**So ändern Sie eine Partitionsfunktion mit:**</span><span class="sxs-lookup"><span data-stu-id="f8177-114">**To modify a partition function, using:**</span></span>  
  
     [<span data-ttu-id="f8177-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f8177-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f8177-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f8177-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f8177-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f8177-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f8177-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f8177-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f8177-119">ALTER PARTITION FUNCTION kann nur verwendet werden, um eine Partition in zwei aufzuteilen bzw. um zwei Partitionen in eine zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="f8177-119">ALTER PARTITION FUNCTION can only be used for splitting one partition into two, or for merging two partitions into one.</span></span> <span data-ttu-id="f8177-120">Um die Partitionierung von Tabellen bzw. Indizes zu ändern (beispielsweise von 10 in 5 Partitionen), können Sie eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="f8177-120">To change the way a table or index is partitioned (from 10 partitions to 5, for example), you can use any one of the following options:</span></span>  
  
    -   <span data-ttu-id="f8177-121">Erstellen Sie eine neue partitionierte Tabelle mit der gewünschten Partitionsfunktion, und fügen Sie dann die Daten aus der alten Tabelle in die neue Tabelle ein, indem Sie entweder eine INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung oder den **Assistenten zum Verwalten von Partitionen** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8177-121">Create a new partitioned table with the desired partition function, and then insert the data from the old table into the new table by using either an INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or the **Manage Partition Wizard** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="f8177-122">Erstellen Sie einen partitionierten gruppierten Index für einen Heap.</span><span class="sxs-lookup"><span data-stu-id="f8177-122">Create a partitioned clustered index on a heap.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f8177-123">Das Löschen eines partitionierten gruppierten Index ergibt einen partitionierten Heap.</span><span class="sxs-lookup"><span data-stu-id="f8177-123">Dropping a partitioned clustered index results in a partitioned heap.</span></span>  
  
    -   <span data-ttu-id="f8177-124">Verwenden Sie die CREATE INDEX-Anweisung von [!INCLUDE[tsql](../../includes/tsql-md.md)] mit der DROP EXISTING = ON-Klausel, um einen vorhandenen partitionierten Index zu löschen und neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8177-124">Drop and rebuild an existing partitioned index by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX statement with the DROP EXISTING = ON clause.</span></span>  
  
    -   <span data-ttu-id="f8177-125">Führen Sie eine Abfolge von ALTER PARTITION FUNCTION-Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="f8177-125">Perform a sequence of ALTER PARTITION FUNCTION statements.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f8177-126">wird die Replikation beim Ändern einer Partitionsfunktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8177-126">does not provide replication support for modifying a partition function.</span></span> <span data-ttu-id="f8177-127">Wenn Sie Änderungen an Partitionsfunktionen in der Veröffentlichungsdatenbank vornehmen möchten, müssen Sie diese manuell in der Abonnementdatenbank durchführen.</span><span class="sxs-lookup"><span data-stu-id="f8177-127">If you want to make changes to a partition function in the publication database, you must do this manually in the subscription database.</span></span>  
  
-   <span data-ttu-id="f8177-128">Alle von ALTER PARTITION FUNCTION betroffenen Dateigruppen müssen online sein.</span><span class="sxs-lookup"><span data-stu-id="f8177-128">All filegroups that are affected by ALTER PARTITION FUNCTION must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f8177-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f8177-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f8177-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f8177-130">Permissions</span></span>  
 <span data-ttu-id="f8177-131">Die folgenden Berechtigungen können zum Ausführen von ALTER PARTITION FUNCTION verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f8177-131">Any one of the following permissions can be used to execute ALTER PARTITION FUNCTION:</span></span>  
  
-   <span data-ttu-id="f8177-132">ALTER ANY DATASPACE-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="f8177-132">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="f8177-133">Diese Berechtigung gilt standardmäßig für Mitglieder der festen Serverrolle **sysadmin** und für Mitglieder der festen Datenbankrollen **db_owner** und **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="f8177-133">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="f8177-134">Die Berechtigung CONTROL oder ALTER für die Datenbank, in der die Partitionsfunktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f8177-134">CONTROL or ALTER permission on the database in which the partition function was created.</span></span>  
  
-   <span data-ttu-id="f8177-135">Die Berechtigung CONTROL SERVER oder ALTER ANY DATABASE auf dem Server der Datenbank, in der die Partitionsfunktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f8177-135">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f8177-136">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f8177-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f8177-137">**So ändern Sie eine Partitionsfunktion:**</span><span class="sxs-lookup"><span data-stu-id="f8177-137">**To modify a partition function:**</span></span>  
  
 <span data-ttu-id="f8177-138">Diese spezielle Aktion kann nicht mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f8177-138">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f8177-139">Um eine Partitionsfunktion zu ändern, müssen Sie zuerst die Funktion löschen und dann mit dem Assistenten zum Erstellen von Partitionen eine neue Funktion mit den gewünschten Eigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8177-139">In order to modify a partition function, you must first delete the function and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="f8177-140">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f8177-140">For more information, see</span></span>  
  
#### <a name="to-delete-a-partition-function"></a><span data-ttu-id="f8177-141">So löschen Sie eine Partitionsfunktion</span><span class="sxs-lookup"><span data-stu-id="f8177-141">To delete a partition function</span></span>  
  
1.  <span data-ttu-id="f8177-142">Erweitern Sie die Datenbank mit der zu löschenden Partitionsfunktion und dann den Ordner **Speicher** .</span><span class="sxs-lookup"><span data-stu-id="f8177-142">Expand the database where you want to delete the partition function and then expand the **Storage** folder.</span></span>  
  
2.  <span data-ttu-id="f8177-143">Erweitern Sie den Ordner **Partitionsfunktionen** .</span><span class="sxs-lookup"><span data-stu-id="f8177-143">Expand the **Partition Functions** folder.</span></span>  
  
3.  <span data-ttu-id="f8177-144">Klicken Sie mit der rechten Maustaste auf die Partitionsfunktion, die Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f8177-144">Right-click the partition function you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="f8177-145">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass die richtige Partitionsfunktion ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8177-145">In the **Delete Object** dialog box, ensure that the correct partition function is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f8177-146">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f8177-146">Using Transact-SQL</span></span>  
  
#### <a name="to-split-a-single-partition-into-two-partitions"></a><span data-ttu-id="f8177-147">So teilen Sie eine einzelne Partition in zwei Partitionen auf</span><span class="sxs-lookup"><span data-stu-id="f8177-147">To split a single partition into two partitions</span></span>  
  
1.  <span data-ttu-id="f8177-148">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="f8177-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8177-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f8177-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f8177-150">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f8177-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Split the partition between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    ```  
  
#### <a name="to-merge-two-partitions-into-one-partition"></a><span data-ttu-id="f8177-151">So führen Sie zwei Partitionen zu einer Partition zusammen</span><span class="sxs-lookup"><span data-stu-id="f8177-151">To merge two partitions into one partition</span></span>  
  
1.  <span data-ttu-id="f8177-152">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="f8177-152">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8177-153">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f8177-153">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f8177-154">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f8177-154">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Merge the partitions between boundary_values 1 and 100  
    --and between boundary_values 100 and 1000 to create one partition  
    --between boundary_values 1 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    MERGE RANGE (100);  
    ```  
  
 <span data-ttu-id="f8177-155">Weitere Informationen finden Sie unter [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f8177-155">For more information, see [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span></span>  
  
  
