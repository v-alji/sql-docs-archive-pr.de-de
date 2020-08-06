---
title: Ändern eines Partitionsschemas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d57984228e23143d2061df6bf447f978f9bd3c46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619790"
---
# <a name="modify-a-partition-scheme"></a><span data-ttu-id="7087c-102">Ändern eines Partitionsschemas</span><span class="sxs-lookup"><span data-stu-id="7087c-102">Modify a Partition Scheme</span></span>
  <span data-ttu-id="7087c-103">Sie können ein Partitionsschema in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ändern, indem Sie eine Dateigruppe zum Aufnehmen der nächsten Partition bestimmen, die der partitionierten Tabelle mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7087c-103">You can modify a partition scheme in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by designating a filegroup to hold the next partition that is added to a partitioned table using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7087c-104">Dies erreichen Sie, indem Sie einer Dateigruppe die NEXT USED-Eigenschaft zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7087c-104">You do this by assigning the NEXT USED property to a filegroup.</span></span> <span data-ttu-id="7087c-105">Die NEXT USED-Eigenschaft können Sie einer leeren Dateigruppe zuweisen oder einer Dateigruppe, die bereits eine Partition besitzt.</span><span class="sxs-lookup"><span data-stu-id="7087c-105">You can assign the NEXT USED property to an empty filegroup or to one that already holds a partition.</span></span> <span data-ttu-id="7087c-106">Eine Dateigruppe kann also mehr als eine Partition aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7087c-106">In other words, a filegroup can hold more than one partition.</span></span>  
  
 <span data-ttu-id="7087c-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7087c-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7087c-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7087c-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7087c-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7087c-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7087c-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7087c-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7087c-111">**Erstellen einer partitionierten Tabelle oder eines partitionierten Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="7087c-111">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="7087c-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7087c-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7087c-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7087c-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7087c-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7087c-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7087c-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7087c-115">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7087c-116">Jede Dateigruppe, die von ALTER PARTITION SCHEME betroffen ist, muss online sein.</span><span class="sxs-lookup"><span data-stu-id="7087c-116">Any filegroup affected by ALTER PARTITION SCHEME must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7087c-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7087c-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7087c-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7087c-118">Permissions</span></span>  
 <span data-ttu-id="7087c-119">Die folgenden Berechtigungen können verwendet werden, um ALTER PARTITION SCHEME auszuführen:</span><span class="sxs-lookup"><span data-stu-id="7087c-119">The following permissions can be used to execute ALTER PARTITION SCHEME:</span></span>  
  
-   <span data-ttu-id="7087c-120">ALTER ANY DATASPACE-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="7087c-120">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="7087c-121">Diese Berechtigung gilt standardmäßig für Mitglieder der festen Serverrolle **sysadmin** und für Mitglieder der festen Datenbankrollen **db_owner** und **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="7087c-121">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="7087c-122">CONTROL- oder ALTER-Berechtigung für die Datenbank, in der das Partitionsschema erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7087c-122">CONTROL or ALTER permission on the database in which the partition scheme was created.</span></span>  
  
-   <span data-ttu-id="7087c-123">Die CONTROL SERVER-Berechtigung oder ALTER ANY DATABASE-Berechtigung auf dem Server der Datenbank, in der das Partitionsschema erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7087c-123">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition scheme was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7087c-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7087c-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7087c-125">**So ändern Sie ein Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="7087c-125">**To modify a partition scheme:**</span></span>  
  
 <span data-ttu-id="7087c-126">Diese spezielle Aktion kann nicht mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7087c-126">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7087c-127">Um ein Partitionsschema zu ändern, müssen Sie zuerst das Schema löschen und dann mit dem Assistenten zum Erstellen von Partitionen eine neue Funktion mit den gewünschten Eigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="7087c-127">In order to modify a partition scheme, you must first delete the scheme and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="7087c-128">Weitere Informationen finden Sie unter [Erstellen von partitionierten Tabellen und Indizes mithilfe von SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) unter **Erstellen von partitionierten Tabellen und Indizes**.</span><span class="sxs-lookup"><span data-stu-id="7087c-128">For more information, see [Create Partitioned Tables and Indexes Using SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) under **Create Partitioned Tables and Indexes**.</span></span>  
  
#### <a name="to-delete-a-partition-scheme"></a><span data-ttu-id="7087c-129">So löschen Sie ein Partitionsschema</span><span class="sxs-lookup"><span data-stu-id="7087c-129">To delete a partition scheme</span></span>  
  
1.  <span data-ttu-id="7087c-130">Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, die das zu löschende Partitionsschema enthält.</span><span class="sxs-lookup"><span data-stu-id="7087c-130">Click the plus sign to expand the database where you want to delete the partition scheme.</span></span>  
  
2.  <span data-ttu-id="7087c-131">Klicken Sie auf das Pluszeichen, um den Ordner **Speicher** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="7087c-131">Click the plus sign to expand the **Storage** folder.</span></span>  
  
3.  <span data-ttu-id="7087c-132">Klicken Sie auf das Pluszeichen, um den Ordner **Partitionsschemas** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="7087c-132">Click the plus sign to expand the **Partition Schemes** folder.</span></span>  
  
4.  <span data-ttu-id="7087c-133">Klicken Sie mit der rechten Maustaste auf das Partitionsschema, das Sie löschen möchten, und wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="7087c-133">Right-click the partition scheme you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="7087c-134">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass das richtige Partitionsschema ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7087c-134">In the **Delete Object** dialog box, ensure that the correct partition scheme is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7087c-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7087c-135">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-partition-scheme"></a><span data-ttu-id="7087c-136">So ändern Sie ein Partitionsschema</span><span class="sxs-lookup"><span data-stu-id="7087c-136">To modify a partition scheme</span></span>  
  
1.  <span data-ttu-id="7087c-137">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7087c-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7087c-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7087c-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7087c-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7087c-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 <span data-ttu-id="7087c-140">Weitere Informationen finden Sie unter [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7087c-140">For more information, see [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span></span>  
  
  
