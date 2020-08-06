---
title: Erstellen eines benutzerdefinierten Sammlungs Satzes, der den generischen T-SQL-Abfrage Sammlertyp verwendet (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- T-SQL Query collector type
- collection sets [SQL Server], creating custom
ms.assetid: 6b06db5b-cfdc-4ce0-addd-ec643460605b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab21ad5fd65556dec639fd5ca6999d23e2de673b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619874"
---
# <a name="create-a-custom-collection-set-that-uses-the-generic-t-sql-query-collector-type-transact-sql"></a><span data-ttu-id="cac83-102">Erstellen eines benutzerdefinierten Sammlungssatzes, der einen generischen T-SQL-Abfragesammlertyp verwendet (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cac83-102">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type (Transact-SQL)</span></span>
  <span data-ttu-id="cac83-103">Sie können auch mithilfe der mit dem Datensammler bereitgestellten gespeicherten Prozeduren einen benutzerdefinierten Sammlungssatz mit Sammelelementen erstellen, die den generischen T-SQL-Abfragesammlertyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="cac83-103">You can create a custom collection set with collection items that use the Generic T-SQL Query collector type by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="cac83-104">Das Ausführen dieses Tasks umfasst die Verwendung des Abfrage-Editors in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , um die folgenden Vorgänge durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="cac83-104">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedures:</span></span>  
  
-   <span data-ttu-id="cac83-105">Konfigurieren von Uploadzeitplänen</span><span class="sxs-lookup"><span data-stu-id="cac83-105">Configure upload schedules.</span></span>  
  
-   <span data-ttu-id="cac83-106">Definieren und Erstellen des Sammlungssatzes</span><span class="sxs-lookup"><span data-stu-id="cac83-106">Define and create the collection set.</span></span>  
  
-   <span data-ttu-id="cac83-107">Definieren und Erstellen eines Auflistelements</span><span class="sxs-lookup"><span data-stu-id="cac83-107">Define and create a collection item.</span></span>  
  
-   <span data-ttu-id="cac83-108">Überprüfen, ob der Sammlungssatz und die Sammelelemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cac83-108">Verify that the collection set and collection items exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cac83-109">Bevor Sie einen benutzerdefinierten Sammlungssatz erstellen, müssen Sie Datensammlungsparameter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cac83-109">Before you create a custom collection set, you must configure data collection parameters.</span></span> <span data-ttu-id="cac83-110">Weitere Informationen finden Sie unter [Konfigurieren von Parametern für die Datensammlung &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cac83-110">For more information, see [Configure Data Collection Parameters &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span></span>  
  
### <a name="define-and-create-the-collection-set"></a><span data-ttu-id="cac83-111">Definieren und Erstellen des Sammlungssatzes</span><span class="sxs-lookup"><span data-stu-id="cac83-111">Define and create the collection set</span></span>  
  
1.  <span data-ttu-id="cac83-112">Definieren Sie mit der gespeicherten Prozedur „sp_syscollector_create_collection_set“ einen neuen Sammlungssatz.</span><span class="sxs-lookup"><span data-stu-id="cac83-112">Define a new collection set using the sp_syscollector_create_collection_set stored procedure.</span></span>  
  
    ```  
    USE msdb;  
    DECLARE @collection_set_id int;  
    DECLARE @collection_set_uid uniqueidentifier;  
    EXEC sp_syscollector_create_collection_set   
        @name=N'DMV Test 1',   
        @collection_mode=0,   
        @description=N'This is a test collection set',   
        @logging_level=1,   
        @days_until_expiration=14,   
        @schedule_name=N'CollectorSchedule_Every_15min',   
        @collection_set_id=@collection_set_id OUTPUT,   
        @collection_set_uid=@collection_set_uid OUTPUT;  
    SELECT @collection_set_id, @collection_set_uid;  
    ```  
  
     <span data-ttu-id="cac83-113">Der Auflistmodus kann auf 0 (zwischengespeichert) oder 1 (nicht zwischengespeichert) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cac83-113">The collection mode can be set to either 0 (cached) or to 1 (non-cached).</span></span>  
  
     <span data-ttu-id="cac83-114">Der Protokolliergrad kann auf 0, 1 oder 2 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cac83-114">The logging level can be set to 0, 1 or 2.</span></span>  
  
     <span data-ttu-id="cac83-115">Die folgenden vorkonfigurierten Zeitpläne werden mit dem Datensammler bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="cac83-115">The following preconfigured schedules are provided with the data collector:</span></span>  
  
    -   <span data-ttu-id="cac83-116">CollectorSchedule_Every_5min</span><span class="sxs-lookup"><span data-stu-id="cac83-116">CollectorSchedule_Every_5min</span></span>  
  
    -   <span data-ttu-id="cac83-117">CollectorSchedule_Every_10min</span><span class="sxs-lookup"><span data-stu-id="cac83-117">CollectorSchedule_Every_10min</span></span>  
  
    -   <span data-ttu-id="cac83-118">CollectorSchedule_Every_15min</span><span class="sxs-lookup"><span data-stu-id="cac83-118">CollectorSchedule_Every_15min</span></span>  
  
    -   <span data-ttu-id="cac83-119">CollectorSchedule_Every_30min</span><span class="sxs-lookup"><span data-stu-id="cac83-119">CollectorSchedule_Every_30min</span></span>  
  
    -   <span data-ttu-id="cac83-120">CollectorSchedule_Every_60min</span><span class="sxs-lookup"><span data-stu-id="cac83-120">CollectorSchedule_Every_60min</span></span>  
  
    -   <span data-ttu-id="cac83-121">CollectorSchedule_Every_6h</span><span class="sxs-lookup"><span data-stu-id="cac83-121">CollectorSchedule_Every_6h</span></span>  
  
     <span data-ttu-id="cac83-122">Wenn Sie keinen der bereitgestellten Zeitpläne verwenden möchten, können Sie einen neuen Zeitplan erstellen und für den Sammlungssatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="cac83-122">If you do not want to use one of the schedules that are provided, you can create a new schedule and use it for the collection set.</span></span> <span data-ttu-id="cac83-123">Weitere Informationen finden Sie unter [Anlegen und Zuweisen von Zeitplänen zu Aufträgen](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="cac83-123">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
### <a name="define-and-create-a-collection-item"></a><span data-ttu-id="cac83-124">Definieren und Erstellen eines Auflistelements</span><span class="sxs-lookup"><span data-stu-id="cac83-124">Define and create a collection item</span></span>  
  
1.  <span data-ttu-id="cac83-125">Da das neue Sammelelement auf einem generischen Sammlertyp basiert, der bereits installiert ist, können Sie den folgenden Code ausführen, um die GUID so festzulegen, dass Sie dem generischen T-SQL-Abfragesammlertyp entspricht.</span><span class="sxs-lookup"><span data-stu-id="cac83-125">Because the new collection item is based on a generic collector type that is already installed, you can run the following code to set the GUID to correspond to the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid uniqueidentifier;  
    SELECT @collector_type_uid = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
    WHERE name = N'Generic T-SQL Query Collector Type';  
    DECLARE @collection_item_id int;  
    ```  
  
2.  <span data-ttu-id="cac83-126">Verwenden Sie die gespeicherte Prozedur „sp_syscollector_create_collection_item“, um das Sammelelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cac83-126">Use the sp_syscollector_create_collection_item stored procedure to create the collection item.</span></span> <span data-ttu-id="cac83-127">Deklarieren Sie das Schema für das Auflistelement so, dass es dem Schema zugeordnet wird, das für den generischen T-SQL-Abfragesammlertyp erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cac83-127">Declare the schema for the collection item so it maps to the schema that is required for the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    EXEC sp_syscollector_create_collection_item   
        @name=N'Query Stats - Test 1',   
        @parameters=N'  
            <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
            <Query>  
            <Value>SELECT * FROM sys.dm_exec_query_stats</Value>  
            <OutputTable>dm_exec_query_stats</OutputTable>  
            </Query>  
            </ns:TSQLQueryCollector>',   
        @collection_item_id=@collection_item_id OUTPUT,   
        @frequency=5,   
        @collection_set_id=@collection_set_id,   
        @collector_type_uid=@collector_type_uid;  
    SELECT @collection_item_id;  
    ```  
  
### <a name="verify-that-the-new-collection-set-and-collection-item-exist"></a><span data-ttu-id="cac83-128">Überprüfen, ob der neue Sammlungssatz und das Sammelelement vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="cac83-128">Verify that the new collection set and collection item exist</span></span>  
  
1.  <span data-ttu-id="cac83-129">Bevor Sie den neuen Sammlungssatz starten, führen Sie die folgende Abfrage aus, um zu überprüfen, dass der neue Sammlungssatz und sein Auflistelement erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cac83-129">Before starting the new collection set, run the following query to verify that the new collection set and its collection item have been created.</span></span>  
  
    ```sql  
    USE msdb;  
    SELECT * FROM syscollector_collection_sets;  
    SELECT * FROM syscollector_collection_items;  
    GO  
    ```  
  
     <span data-ttu-id="cac83-130">Sie können auch eine visuelle Prüfung in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]durchführen.</span><span class="sxs-lookup"><span data-stu-id="cac83-130">You can also do a visual check in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cac83-131">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** , und erweitern Sie dann **Datensammlung**.</span><span class="sxs-lookup"><span data-stu-id="cac83-131">In Object Explorer, expand the **Management** node, and then expand **Data Collection**.</span></span> <span data-ttu-id="cac83-132">Der neue Sammlungssatz wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cac83-132">The new collection set will be displayed.</span></span> <span data-ttu-id="cac83-133">Das rote Kreissymbol für den Sammlungssatz gibt an, dass der Sammlungssatz beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cac83-133">The red circle icon for the collection set indicates that the collection set is stopped.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cac83-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cac83-134">Example</span></span>  
 <span data-ttu-id="cac83-135">Im folgenden Codebeispiel werden die in den vorherigen Schritten dokumentierten Beispiele miteinander kombiniert.</span><span class="sxs-lookup"><span data-stu-id="cac83-135">The following code sample combines the examples that are documented in the previous steps.</span></span> <span data-ttu-id="cac83-136">Beachten Sie, dass die für das Sammelelement festgelegte Auflistungshäufigkeit (5 Sekunden) ignoriert wird, da der Auflistungsmodus des Sammlungssatzes auf 0 festgelegt ist, was dem Modus mit Zwischenspeicherung entspricht.</span><span class="sxs-lookup"><span data-stu-id="cac83-136">Note that the collection frequency that is set for the collection item (5 seconds) is ignored because the collection set collection mode is set to 0, which is cached mode.</span></span> <span data-ttu-id="cac83-137">Weitere Informationen finden Sie unter [Data Collection](data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="cac83-137">For more information, see [Data Collection](data-collection.md).</span></span>  
  
```sql  
USE msdb;  
  
DECLARE @collection_set_id int;  
DECLARE @collection_set_uid uniqueidentifier  
  
EXEC dbo.sp_syscollector_create_collection_set  
    @name = N'DMV Stats Test 1',  
    @collection_mode = 0,  
    @description = N'This is a test collection set',  
    @logging_level=1,  
    @days_until_expiration = 14,  
    @schedule_name=N'CollectorSchedule_Every_15min',  
    @collection_set_id = @collection_set_id OUTPUT,  
    @collection_set_uid = @collection_set_uid OUTPUT;  
SELECT @collection_set_id,@collection_set_uid;  
  
DECLARE @collector_type_uid uniqueidentifier;  
SELECT @collector_type_uid = collector_type_uid FROM syscollector_collector_types   
WHERE name = N'Generic T-SQL Query Collector Type';  
  
DECLARE @collection_item_id int;  
EXEC sp_syscollector_create_collection_item  
@name= N'Query Stats - Test 1',  
@parameters=N'  
<ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
<Query>  
  <Value>select * from sys.dm_exec_query_stats</Value>  
  <OutputTable>dm_exec_query_stats</OutputTable>  
</Query>  
 </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 5, -- This parameter is ignored in cached mode  
    @collection_set_id = @collection_set_id,  
    @collector_type_uid = @collector_type_uid;  
SELECT @collection_item_id;  
  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cac83-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cac83-138">See Also</span></span>  
 <span data-ttu-id="cac83-139">[Gespeicherte Prozeduren für den Datensammler &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cac83-139">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="cac83-140">[Zeitpläne verwalten](../../ssms/agent/manage-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="cac83-140">[Manage Schedules](../../ssms/agent/manage-schedules.md) </span></span>  
 [<span data-ttu-id="cac83-141">Starten oder Beenden eines Sammlungssatzes</span><span class="sxs-lookup"><span data-stu-id="cac83-141">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
  
