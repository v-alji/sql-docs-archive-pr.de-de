---
title: Bereinigen von Mergemetadaten (Replikationsprogrammierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- metadata [SQL Server replication]
- sp_mergemetadataretentioncleanup
ms.assetid: 9b88baea-b7c6-4e5d-88f9-93d6a0ff0368
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5a2306db72fd3f0098e18ff058796a5498eafcac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721402"
---
# <a name="clean-up-merge-metadata-replication-transact-sql-programming"></a><span data-ttu-id="6c176-102">Cleanup von Mergemetadaten (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6c176-102">Clean Up Merge Metadata (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="6c176-103">Der Cleanup von Mergereplikationsmetadaten wird basierend auf der Beibehaltungseinstellung für die Veröffentlichung in regelmäßigen Abständen vom Merge-Agent ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6c176-103">Merge replication metadata is cleaned up periodically by the Merge Agent based on the retention setting for the publication.</span></span> <span data-ttu-id="6c176-104">Dies erfolgt auf dem Verleger und auf dem Abonnenten in den Systemtabellen [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql)und [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) .</span><span class="sxs-lookup"><span data-stu-id="6c176-104">This occurs at the Publisher and Subscriber in the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql), and [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) system tables.</span></span> <span data-ttu-id="6c176-105">Der Cleanup der Daten in diesen Tabellen kann mithilfe gespeicherter Replikationsprozeduren auch programmgesteuert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6c176-105">You can also programmatically clean up the data in these tables using replication stored procedures.</span></span>  
  
### <a name="to-manually-clean-up-merge-metadata"></a><span data-ttu-id="6c176-106">So führen Sie einen Cleanup von Mergemetadaten manuell aus</span><span class="sxs-lookup"><span data-stu-id="6c176-106">To manually clean up merge metadata</span></span>  
  
1.  <span data-ttu-id="6c176-107">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="6c176-107">At the Publisher on the publication database, execute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span></span>  
  
2.  <span data-ttu-id="6c176-108">(Optional) Beachten Sie die Anzahl von Zeilen, die in Schritt 1aus den Systemtabellen [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql)und [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) entfernt und jeweils in den Ausgabeparametern **@num_genhistory_rows**, **@num_contents_rows**und **@num_tombstone_rows** zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6c176-108">(Optional) Note the number of rows removed in step 1 from the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), and [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) system tables, returned respectively in the **@num_genhistory_rows**, **@num_contents_rows**, and **@num_tombstone_rows** output parameters.</span></span>  
  
3.  <span data-ttu-id="6c176-109">Wiederholen Sie die Schritte 1 und 2 auf dem Abonnenten, um einen Cleanup der Metadaten für die Abonnementdatenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c176-109">Repeat steps 1 and 2 at the Subscriber to clean up metadata on the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c176-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c176-110">See Also</span></span>  
 [<span data-ttu-id="6c176-111">Abonnementablauf und -deaktivierung</span><span class="sxs-lookup"><span data-stu-id="6c176-111">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
