---
title: Replikation mit Abonnenten von speicheroptimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
ms.assetid: 1a8e6bc7-433e-471d-b646-092dc80a2d1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df61b83d2f6d07cbbd21773b8940dd4e5341f76b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608524"
---
# <a name="replication-to-memory-optimized-table-subscribers"></a><span data-ttu-id="815e3-102">Replikation mit Abonnenten von speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="815e3-102">Replication to Memory-Optimized Table Subscribers</span></span>
  <span data-ttu-id="815e3-103">Die Tabellen, die als Transaktionsreplikationsabonnenten fungieren, können (mit Ausnahme der Peer-zu-Peer-Transaktionsreplikation) als speicheroptimierte Tabellen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-103">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="815e3-104">Andere Replikationskonfigurationen sind mit speicheroptimierten Tabellen nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="815e3-104">Other replication configurations are not compatible with memory-optimized tables.</span></span>  
  
## <a name="configuring-a-memory-optimized-table-as-a-subscriber"></a><span data-ttu-id="815e3-105">Konfigurieren einer speicheroptimierten Tabelle als Abonnent</span><span class="sxs-lookup"><span data-stu-id="815e3-105">Configuring a memory-optimized table as a subscriber</span></span>  
 <span data-ttu-id="815e3-106">Führen Sie die folgenden Schritte aus, um eine speicheroptimierte Tabelle als Abonnenten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="815e3-106">To configure a memory-optimized table as a subscriber, perform the following steps.</span></span>  
  
 <span data-ttu-id="815e3-107">**Erstellen und Aktivieren einer Veröffentlichung**</span><span class="sxs-lookup"><span data-stu-id="815e3-107">**Create and Enable Publication**</span></span>  
  
1.  <span data-ttu-id="815e3-108">Erstellen einer Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="815e3-108">Create a publication.</span></span>  
  
2.  <span data-ttu-id="815e3-109">Fügen Sie der Veröffentlichung Artikel hinzu.</span><span class="sxs-lookup"><span data-stu-id="815e3-109">Add articles to the publication.</span></span> <span data-ttu-id="815e3-110">Verwenden Sie für den `@upd_cmd`-Parameter die SCALL- oder SQL-Konvention.</span><span class="sxs-lookup"><span data-stu-id="815e3-110">For the `@upd_cmd` parameter, use the SCALL or SQL convention.</span></span>  
  
    ```  
    EXEC sp_addarticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @source_owner = N'dbo',  
        @source_object = N'Mem_Table',  
        @type = N'logbased',  
        @description = null,  
        @creation_script = null,  
        @pre_creation_cmd = N'none',  
        @schema_option = 0x00000000080050DF,  
        @identityrangemanagementoption = N'manual',  
        @destination_table = N'Mem_Table',  
        @destination_owner = N'dbo',  
        @vertical_partition = N'false',  
        @ins_cmd = N'CALL sp_MSins_Mem_Table',  
        @del_cmd = N'CALL sp_MSdel_Mem_Table',  
        @upd_cmd = N'SCALL sp_MSupd_Mem_Table';  
    GO  
    ```  
  
 <span data-ttu-id="815e3-111">**Generieren einer Momentaufnahme und Anpassen des Schemas**</span><span class="sxs-lookup"><span data-stu-id="815e3-111">**Generate a Snapshot and Adjust the Schema**</span></span>  
  
1.  <span data-ttu-id="815e3-112">Erstellen Sie einen Momentaufnahmeauftrag, und generieren Sie eine Momentaufnahme.</span><span class="sxs-lookup"><span data-stu-id="815e3-112">Create a snapshot job and generate a snapshot.</span></span>  
  
    ```  
    EXEC sp_addpublication_snapshot @publication = N'Publication1', @frequency_type = 1;  
    EXEC sp_startpublication_snapshot @publication = N'Publication1';  
    ```  
  
2.  <span data-ttu-id="815e3-113">Navigieren Sie zum Ordner für Momentaufnahmen.</span><span class="sxs-lookup"><span data-stu-id="815e3-113">Navigate to the snapshot folder.</span></span> <span data-ttu-id="815e3-114">Der Standard Speicherort ist "c:\Programme\Microsoft SQL server\mssql12. \<INSTANCE> ". \Mssql\repldata\unc\xxx\yyyymmddhhmmss \\ .</span><span class="sxs-lookup"><span data-stu-id="815e3-114">The default location is "C:\Program Files\Microsoft SQL Server\MSSQL12.\<INSTANCE>\MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS\\".</span></span>  
  
3.  <span data-ttu-id="815e3-115">Suchen Sie nach **. Sch** -Datei für die Tabelle, und öffnen Sie Sie in Management Studio.</span><span class="sxs-lookup"><span data-stu-id="815e3-115">Locate the **.SCH** file for your table and open it in Management Studio.</span></span> <span data-ttu-id="815e3-116">Ändern Sie das Tabellenschema, und aktualisieren Sie die gespeicherte Prozedur, wie im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="815e3-116">Change the table schema and update the stored procedure as described below.</span></span>  
  
     <span data-ttu-id="815e3-117">Werten Sie die in der IDX-Datei definierten Indizes aus.</span><span class="sxs-lookup"><span data-stu-id="815e3-117">Evaluate the indexes defined in the IDX file.</span></span> <span data-ttu-id="815e3-118">Ändern Sie `CREATE TABLE`, um die erforderlichen Indizes, die Einschränkungen, den Primärschlüssel und die speicheroptimierte Syntax anzugeben.</span><span class="sxs-lookup"><span data-stu-id="815e3-118">Modify `CREATE TABLE` to specify the required indexes, constraints, primary key, and memory-optimized syntax.</span></span> <span data-ttu-id="815e3-119">Für speicheroptimierte Tabellen dürfen Indexspalten NICHT NULL sein, und Indexspalten von Zeichentypen müssen Unicode sein und eine BIN2-Sortierung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="815e3-119">For memory-optimized tables, index columns should be NOT NULL and index columns of character types must be Unicode and use BIN2 collation.</span></span> <span data-ttu-id="815e3-120">Siehe das unten stehende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="815e3-120">See example below:</span></span>  
  
    ```  
    SET ANSI_PADDING ON;  
    GO  
  
    SET ANSI_NULLS ON;  
    GO  
  
    SET QUOTED_IDENTIFIER ON;  
    GO  
  
    CREATE TABLE [dbo].[Mem_Table]([c1] [int] NOT NULL,  
        [c2] [float] NOT NULL,  
        [c3] [decimal](10, 2) NOT NULL,  
        [c4] [nvarchar](5) COLLATE SQL_Latin1_General_CP850_BIN2 NOT NULL,  
        INDEX [hash_index_sample_memoryoptimizedtable_c2] HASH (c2) WITH (BUCKET_COUNT = 1024),  
        INDEX [index_sample_memoryoptimizedtable_c3] NONCLUSTERED ([c3]),  
        INDEX [nvarchar_index_sample_memoryoptimizedtable_c4] ([c4]),  
        CONSTRAINT [PK_sample_memoryoptimizedtable] PRIMARY KEY NONCLUSTERED ([c1])) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);  
    GO  
    ```  
  
4.  <span data-ttu-id="815e3-121">Wenn Sie die SCALL-Konvention für den `@upd_cmd`-Parameter verwenden, navigieren Sie zur Schemadatei (.sch), und ändern Sie die Table Update-Anweisung in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]`, um Primärschlüsselspalten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="815e3-121">When using SCALL convention for the `@upd_cmd` parameter, go to the schema (.SCH) file and change the table update statement in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` to remove primary key columns.</span></span>  
  
     <span data-ttu-id="815e3-122">Um Primärschlüsselupdates zu unterstützen, können Sie die UPDATE-Anweisung für Primärschlüssel wie folgt durch eine benutzerdefinierte gespeicherte Updateprozedur ersetzen:</span><span class="sxs-lookup"><span data-stu-id="815e3-122">To support primary key updates, use a custom update stored procedure to replace the primary key update statement, as follows:</span></span>  
  
    1.  <span data-ttu-id="815e3-123">Wählen Sie fehlende Spaltenwerte aus (SCALL gibt nur die Spalte an, die beim Updatevorgang berücksichtigt wird).</span><span class="sxs-lookup"><span data-stu-id="815e3-123">Select missing column values (SCALL only provides the column involved into the update operation).</span></span>  
  
    2.  <span data-ttu-id="815e3-124">Löschen Sie den vorhandenen Datensatz.</span><span class="sxs-lookup"><span data-stu-id="815e3-124">Delete the existing record.</span></span>  
  
    3.  <span data-ttu-id="815e3-125">Fügen Sie einen neuen Datensatz mit den bereitgestellten neuen Werten ein, einschließlich des neuen Primärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="815e3-125">Insert a new record with new values provided including the new primary key.</span></span>  
  
     <span data-ttu-id="815e3-126">Die ursprüngliche Updateprozedur sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="815e3-126">The original update procedure looks like this:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
                   [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="815e3-127">Der Primärschlüssel sollte nie für einen Verleger aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-127">If the primary key should never be updated on a publisher.</span></span> <span data-ttu-id="815e3-128">Kommentieren Sie das Update solcher Spalten in der Updateprozedur wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="815e3-128">Comment out the update to such columns in the update procedure as follows:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
    --             [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="815e3-129">Um Updates des Primärschlüssels zu unterstützen, ändern Sie die Updateprozedur wie folgt</span><span class="sxs-lookup"><span data-stu-id="815e3-129">To allow the support of updates to the primary key, modify the update procedure to read as follows</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                    @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    select  
                   @c1 = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   @c2 = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   @c3 = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   @c4 = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    from [dbo].[Mem_Table] where [c1] = @pkc1  
    if @@rowcount <> 0 begin  
            delete [dbo].[Mem_Table] where [c1] = @pkc1  
            if @@rowcount <> 0  
                   insert into [dbo].[Mem_Table]([c1],  
                           [c2],  
                           [c3],  
                           [c4]) values (  
                           @c1,  
                           @c2,  
                           @c3,  
                           @c4  
                   )   
    end  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
5.  <span data-ttu-id="815e3-130">Erstellen Sie eine Abonnenten Datenbank mithilfe der Option **Elevate to Snapshot Isolation** , und legen Sie die Standardsortierung auf Latin1_General_CS_AS_KS_WS fest, wenn Sie nicht-Unicode-Zeichen Datentypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="815e3-130">Create subscriber database using the **elevate to snapshot isolation** option and set the default collation to Latin1_General_CS_AS_KS_WS in case of using non Unicode character data types.</span></span>  
  
    ```  
    CREATE DATABASE [Sub]   
    CONTAINMENT = NONE   
    ON PRIMARY ( NAME = [Sub], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.mdf]),   
    FILEGROUP [mem] CONTAINS MEMORY_OPTIMIZED_DATA ( NAME = [mem],   
    FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub])  
    LOG ON ( NAME = [Sub_log], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.ldf])  
    COLLATE Latin1_General_CS_AS_KS_WS;  
  
    ALTER DATABASE [Sub] SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;  
    GO  
    ```  
  
6.  <span data-ttu-id="815e3-131">Wenden Sie das Schema auf die Datenbank eines Abonnenten an, und speichern Sie das Schema für die spätere Verwendung.</span><span class="sxs-lookup"><span data-stu-id="815e3-131">Apply the schema to a subscriber's database and save the schema for future use.</span></span>  
  
7.  <span data-ttu-id="815e3-132">Laden Sie die Verlegerdaten (Quelldaten) in den Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="815e3-132">Load the publisher (source) data to the subscriber.</span></span> <span data-ttu-id="815e3-133">Die Daten dürfen beim Verleger nicht geändert werden, bis Sie ein Abonnement hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="815e3-133">Data should not change at the publisher until you add a subscription.</span></span>  <span data-ttu-id="815e3-134">Sie können BCP verwenden, wie unten veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="815e3-134">You can use BCP as shown below:</span></span>  
  
    ```  
    bcp Pub.dbo.Mem_Table out Mem_Table.bcp -S. -T -C1252 -n  
    bcp Sub.dbo.Mem_Table in Mem_Table.bcp -S. -T -C1252 -n  
    ```  
  
8.  <span data-ttu-id="815e3-135">Konfigurieren Sie den Artikel neu, um Schemaänderungen beim Abonnenten zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="815e3-135">Reconfigure the article to disable schema changes on the subscriber:</span></span>  
  
    ```  
    EXEC sp_changearticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @property = N'schema_option',  
        @value = 0,  
        @force_invalidate_snapshot = 1,  
        @force_reinit_subscription = 1;  
    GO  
    ```  
  
 <span data-ttu-id="815e3-136">**Hinzufügen eines "No sync"-Abonnements**</span><span class="sxs-lookup"><span data-stu-id="815e3-136">**Add no sync Subscription**</span></span>  
  
 <span data-ttu-id="815e3-137">Fügen Sie ein "No sync"-Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="815e3-137">Add a nosync subscription.</span></span>  
  
```  
EXEC sp_addsubscription  
    @publication = N' Publication1',  
    @subscriber = @@ServerName,  
    @destination_db = N'Sub',  
    @subscription_type = N'Push',  
    @sync_type = N'replication support only',  
    @article = N'all',  
    @update_mode = N'read only',  
    @subscriber_type = 0;  
GO  
```  
  
 <span data-ttu-id="815e3-138">Speicheroptimierte Tabellen empfangen nun Updates vom Verleger.</span><span class="sxs-lookup"><span data-stu-id="815e3-138">Memory-optimized tables should now start receiving updates from the publisher.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="815e3-139">Beschränkungen</span><span class="sxs-lookup"><span data-stu-id="815e3-139">Restrictions</span></span>  
 <span data-ttu-id="815e3-140">Es wird nur die unidirektionale Transaktionsreplikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="815e3-140">Only one-way transactional replication is supported.</span></span> <span data-ttu-id="815e3-141">Die Peer-zu-Peer-Transaktionsreplikation wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="815e3-141">Peer-to-peer transactional replication is not supported.</span></span>  
  
 <span data-ttu-id="815e3-142">Speicheroptimierte Tabellen können nicht veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-142">Memory-optimized tables cannot be published.</span></span>  
  
 <span data-ttu-id="815e3-143">Replikationstabellen auf dem Verteiler können nicht als speicheroptimierte Tabellen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-143">Replication tables on the distributor cannot be configured as memory-optimized tables.</span></span>  
  
 <span data-ttu-id="815e3-144">Die Mergereplikation kann speicheroptimierte Tabellen einschließen.</span><span class="sxs-lookup"><span data-stu-id="815e3-144">Merge replication cannot include memory-optimized tables.</span></span>  
  
 <span data-ttu-id="815e3-145">Auf dem Abonnenten können die Tabellen, die bei einer Transaktionsreplikation berücksichtigt werden, als speicheroptimierte Tabellen konfiguriert werden. Die Abonnententabellen müssen jedoch die Anforderungen für speicheroptimierte Tabellen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="815e3-145">At the subscriber, tables involved in transactional replication can be configured as memory optimized tables, but the subscriber tables must meet the requirements of memory-optimized tables.</span></span> <span data-ttu-id="815e3-146">Dies erfordert folgende Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="815e3-146">This requires the following restrictions.</span></span>  
  
-   <span data-ttu-id="815e3-147">Zum Erstellen einer speicheroptimierten Tabelle auf einem Transaktionsreplikationsabonnenten müssen die Momentaufnahme-Schemadateien, mit denen die speicheroptimierten Tabellen erstellt werden, manuell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-147">To create a memory-optimized table on a transactional replication subscriber, the snapshot schema files used to create the memory-optimized tables must be manually modified.</span></span> <span data-ttu-id="815e3-148">Weitere Informationen finden Sie unter [Ändern einer Schema Datei](#Schema).</span><span class="sxs-lookup"><span data-stu-id="815e3-148">For more information, see [Modifying a schema file](#Schema).</span></span>  
  
-   <span data-ttu-id="815e3-149">Tabellen, die mit speicheroptimierten Tabellen auf einem Abonnenten repliziert werden, sind auf das Limit von 8060 Byte pro Zeile für speicheroptimierte Tabellen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="815e3-149">Tables replicated to memory-optimized tables on a subscriber are limited to the 8060 bytes per row limit of memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="815e3-150">Tabellen, die mit speicheroptimierten Tabellen auf Abonnenten repliziert werden, sind auf die Datentypen beschränkt, die für speicheroptimierte Tabellen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="815e3-150">Tables replicated to memory-optimized tables on a subscriber are limited to the data types permitted in memory-optimized tables.</span></span> <span data-ttu-id="815e3-151">Weitere Informationen finden Sie [unter Unterstützte Datentypen](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="815e3-151">For more information, see [Supported Data Types](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span></span>  
  
-   <span data-ttu-id="815e3-152">Es gelten Einschränkungen für das Aktualisieren des Primärschlüssels von Tabellen, die mit einer speicheroptimierten Tabelle auf einem Abonnenten repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-152">There are restrictions on updating the primary key of tables being replicated to a memory-optimized table on a subscriber.</span></span> <span data-ttu-id="815e3-153">Weitere Informationen finden Sie unter [Replizieren von Änderungen an einem Primärschlüssel](#PrimaryKey).</span><span class="sxs-lookup"><span data-stu-id="815e3-153">For more information, see [Replicating changes to a primary key](#PrimaryKey).</span></span>  
  
-   <span data-ttu-id="815e3-154">Fremdschlüssel, UNIQUE-Einschränkung, Trigger, Schemaänderungen, ROWGUIDCOL, berechnete Spalten, die Datenkomprimierung, Aliasdatentypen, Versionsverwaltung und Sperren werden in speicheroptimierte Tabellen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="815e3-154">Foreign key, unique constraint, triggers, schema modifications, ROWGUIDCOL, computed columns, data compression, alias data types, versioning, and locks are not supported in memory-optimized tables.</span></span> <span data-ttu-id="815e3-155">Weitere Informationen finden Sie unter [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) .</span><span class="sxs-lookup"><span data-stu-id="815e3-155">See [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) for information.</span></span>  
  
##  <a name="modifying-a-schema-file"></a><a name="Schema"></a><span data-ttu-id="815e3-156">Ändern einer Schema Datei</span><span class="sxs-lookup"><span data-stu-id="815e3-156">Modifying a schema file</span></span>  
  
-   <span data-ttu-id="815e3-157">Gruppierte Indizes werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="815e3-157">Clustered indexes are not supported.</span></span> <span data-ttu-id="815e3-158">Ändern Sie alle gruppierten Indizes in nicht gruppierte Indizes.</span><span class="sxs-lookup"><span data-stu-id="815e3-158">Change any clustered indexes to nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="815e3-159">Alle Spalten im Schlüssel eines Indexes müssen als `NOT NULL` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-159">All columns in the key of an index must be specified as `NOT NULL`.</span></span>  
  
-   <span data-ttu-id="815e3-160">Bei Verwendung der Option für speicheroptimierte Tabellen `DURABILITY = SCHEMA_AND_DATA` muss die Tabelle einen nicht gruppierten Primärschlüsselindex aufweisen.</span><span class="sxs-lookup"><span data-stu-id="815e3-160">If using the memory-optimized table option `DURABILITY = SCHEMA_AND_DATA` the table must have a nonclustered primary key index.</span></span>  
  
-   <span data-ttu-id="815e3-161">ANSI_PADDING muss auf ON festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="815e3-161">ANSI_PADDING must be ON.</span></span>  
  
##  <a name="replicating-changes-to-a-primary-key"></a><a name="PrimaryKey"></a><span data-ttu-id="815e3-162">Replizieren von Änderungen an einem Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="815e3-162">Replicating changes to a primary key</span></span>  
 <span data-ttu-id="815e3-163">Der Primärschlüssel einer speicheroptimierten Tabelle kann nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="815e3-163">The primary key of a memory-optimized table cannot be updated.</span></span> <span data-ttu-id="815e3-164">Wenn Sie ein Primärschlüsselupdate auf einem Abonnenten replizieren möchten, ändern Sie die gespeicherte Updateprozedur so, dass der Updatevorgang als DELETE/INSERT-Paar übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="815e3-164">To replicate a primary key update on a subscriber, modify the update stored procedure to deliver the update as a delete and insert pair.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815e3-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="815e3-165">See Also</span></span>  
 [<span data-ttu-id="815e3-166">SQL Server-Replikation</span><span class="sxs-lookup"><span data-stu-id="815e3-166">SQL Server Replication</span></span>](sql-server-replication.md)  
  
  
