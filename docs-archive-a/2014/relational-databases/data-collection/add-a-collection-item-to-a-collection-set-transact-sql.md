---
title: Hinzufügen eines Sammelelements zu einem Sammlungssatz (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection items [SQL Server]
- collection sets [SQL Server], adding items
ms.assetid: 9fe6454e-8c0e-4b50-937b-d9871b20fd13
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0b21508761bdfbaf8918242b074f78203c1bcaed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622685"
---
# <a name="add-a-collection-item-to-a-collection-set-transact-sql"></a><span data-ttu-id="2d15f-102">Hinzufügen eines Sammelelements zu einem Sammlungssatz (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2d15f-102">Add a Collection Item to a Collection Set (Transact-SQL)</span></span>
  <span data-ttu-id="2d15f-103">Sie können einem vorhandenen Sammlungssatz mithilfe der mit dem Datensammler bereitgestellten gespeicherten Prozeduren ein Sammlungselement hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2d15f-103">You can add a collection item to an existing collection set using the stored procedures that are provided with the data collector.</span></span>  
  
 <span data-ttu-id="2d15f-104">Führen Sie die folgenden Schritte mithilfe des Abfrage-Editors in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aus.</span><span class="sxs-lookup"><span data-stu-id="2d15f-104">Carry out the following steps using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="add-a-collection-item-to-a-collection-set"></a><span data-ttu-id="2d15f-105">Hinzufügen eines Sammelelements zu einem Sammlungssatz</span><span class="sxs-lookup"><span data-stu-id="2d15f-105">Add a collection item to a collection set</span></span>  
  
1.  <span data-ttu-id="2d15f-106">Beenden Sie den Sammlungssatz, dem Sie das Element hinzufügen möchten, in dem Sie die gespeicherte Prozedur **sp_syscollector_stop_collection_set** ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d15f-106">Stop the collection set that you want to add the item to by running the **sp_syscollector_stop_collection_set** stored procedure.</span></span> <span data-ttu-id="2d15f-107">Um beispielsweise einen Sammlungssatz mit dem Namen "Test Collection Set" zu beenden, führen Sie die folgenden Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="2d15f-107">For example, to stop a collection set that is named "Test Collection Set", run the following statements:</span></span>  
  
    ```sql  
    USE msdb  
    DECLARE @csid int  
    SELECT @csid = collection_set_id  
    FROM syscollector_collection_sets  
    WHERE name = 'Test Collection Set'  
    SELECT @csid  
    EXEC dbo.sp_syscollector_stop_collection_set @collection_set_id = @csid  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d15f-108">Sie können den Sammlungssatz auch durch Verwendung des Objekt-Explorers in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]beenden</span><span class="sxs-lookup"><span data-stu-id="2d15f-108">You can also stop the collection set by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2d15f-109">Weitere Informationen finden Sie unter [Starten oder Beenden eines Sammlungssatzes](start-or-stop-a-collection-set.md).</span><span class="sxs-lookup"><span data-stu-id="2d15f-109">For more information, see [Start or Stop a Collection Set](start-or-stop-a-collection-set.md).</span></span>  
  
2.  <span data-ttu-id="2d15f-110">Deklarieren Sie den Sammlungssatz, dem Sie das Sammelelement hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d15f-110">Declare the collection set that you want to add the collection item to.</span></span> <span data-ttu-id="2d15f-111">Der folgende Code bietet ein Beispiel für das Deklarieren der Sammlungssatz-ID.</span><span class="sxs-lookup"><span data-stu-id="2d15f-111">The following code provides an example of how to declare the collection set ID.</span></span>  
  
    ```sql  
    DECLARE @collection_set_id_1 int  
    SELECT @collection_set_id_1 = collection_set_id FROM [msdb].[dbo].[syscollector_collection_sets]  
    WHERE name = N'Test Collection Set'; -- name of collection set  
    ```  
  
3.  <span data-ttu-id="2d15f-112">Deklarieren Sie den Sammlertyp.</span><span class="sxs-lookup"><span data-stu-id="2d15f-112">Declare the collector type.</span></span> <span data-ttu-id="2d15f-113">Der folgende Code bietet ein Beispiel für das Deklarieren des generischen T-SQL-Abfragesammlertyps.</span><span class="sxs-lookup"><span data-stu-id="2d15f-113">The following code provides an example of how to declare the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid_1 uniqueidentifier  
    SELECT @collector_type_uid_1 = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
       WHERE name = N'Generic T-SQL Query Collector Type';  
    ```  
  
     <span data-ttu-id="2d15f-114">Führen Sie den folgenden Code aus, um eine Liste der installierten Sammlertypen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="2d15f-114">You can run the following code to obtain a list of the installed collector types:</span></span>  
  
    ```sql  
    USE msdb  
    SELECT * from syscollector_collector_types  
    GO  
    ```  
  
4.  <span data-ttu-id="2d15f-115">Führen Sie die gespeicherte Prozedur **sp_syscollector_create_collection_item** aus, um das Sammlungselement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d15f-115">Run the **sp_syscollector_create_collection_item** stored procedure to create the collection item.</span></span> <span data-ttu-id="2d15f-116">Das Schema für das Sammelelement muss so deklariert werden, dass es dem erforderlichen Schema für den gewünschten Sammlertyp zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="2d15f-116">You must declare the schema for the collection item so that it maps to the required schema for the desired collector type.</span></span> <span data-ttu-id="2d15f-117">Im folgenden Beispiel wird das Eingabeschema der generischen T-SQL-Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d15f-117">The following example uses the Generic T-SQL Query input schema.</span></span>  
  
    ```sql  
    DECLARE @collection_item_id int;  
    EXEC [msdb].[dbo].[sp_syscollector_create_collection_item]   
    @name=N'OS Wait Stats', --name of collection item  
    @parameters=N'  
    <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
     <Query>  
      <Value>select * from sys.dm_os_wait_stats</Value>  
      <OutputTable>os_wait_stats</OutputTable>  
    </Query>  
    </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 60,  
    @collection_set_id = @collection_set_id_1, --- Provides the collection set ID number  
    @collector_type_uid = @collector_type_uid_1 -- Provides the collector type UID  
    SELECT @collection_item_id     
    ```  
  
5.  <span data-ttu-id="2d15f-118">Bevor Sie den aktualisierten Sammlungssatz starten, führen Sie die folgende Abfrage aus, um zu überprüfen, ob das neue Sammelelement erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="2d15f-118">Before starting the updated collection set, run the following query to verify that the new collection item has been created:</span></span>  
  
    ```xaml  
    USE msdb  
    SELECT * from syscollector_collection_sets  
    SELECT * from syscollector_collection_items  
    GO  
    ```  
  
     <span data-ttu-id="2d15f-119">Die Sammlungssätze und ihre Sammlungselemente werden auf der Registerkarte **Ergebnisse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d15f-119">The collection sets and their collection items are displayed in the **Results** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d15f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d15f-120">See Also</span></span>  
 <span data-ttu-id="2d15f-121">[Erstellen eines benutzerdefinierten Sammlungssatzes, der einen generischen T-SQL-Abfragesammlertyp verwendet &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span><span class="sxs-lookup"><span data-stu-id="2d15f-121">[Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span></span>  
 [<span data-ttu-id="2d15f-122">Gespeicherte Prozeduren für den Datensammler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2d15f-122">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
