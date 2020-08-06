---
title: Überwachung und Problembehandlung beim Zusammenführen von Daten-und Änderungsdatei Paaren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a8b0bacc-4d2c-42e4-84bf-1a97e0bd385b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5dc57d08f3db1792a9359b3aa79aaceecd03a025
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621668"
---
# <a name="monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs"></a><span data-ttu-id="5768f-102">Überwachung und Problembehandlung beim Zusammenführen von Daten-/Änderungsdateipaaren</span><span class="sxs-lookup"><span data-stu-id="5768f-102">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>
  <span data-ttu-id="5768f-103">In-Memory OLTP verwendet eine Mergerichtlinie, um angrenzende Daten-/Änderungsdateipaare automatisch zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="5768f-103">In-Memory OLTP uses a merge policy to merge adjacent data and delta file pairs automatically.</span></span> <span data-ttu-id="5768f-104">Sie können die Mergeaktivität nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5768f-104">You cannot disable merge activity.</span></span>  
  
 <span data-ttu-id="5768f-105">Sie können Daten-/Änderungsdateipaare wie folgt überwachen:</span><span class="sxs-lookup"><span data-stu-id="5768f-105">You can monitor data and delta file pairs, as follows:</span></span>  
  
-   <span data-ttu-id="5768f-106">Vergleichen Sie die speicherintern genutzte Menge mit der Gesamtgröße des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="5768f-106">Compare the size of in-memory storage to overall size of storage.</span></span> <span data-ttu-id="5768f-107">Wenn die Speichermenge unverhältnismäßig groß ist, ist es wahrscheinlich, dass die Zusammenführung nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5768f-107">If the storage is dis-proportionately large, then it is likely that merge is not getting triggered.</span></span> <span data-ttu-id="5768f-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5768f-108">For information</span></span>  
  
-   <span data-ttu-id="5768f-109">Sehen Sie sich den verwendeten Speicherplatz in Daten-und Änderungs Dateien an, indem Sie [sys. dm_db_xtp_checkpoint_files &#40;Transact-SQL-&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) verwenden, um festzustellen, ob die Zusammenführung nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5768f-109">Look at the used space in data and delta files using [sys.dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) to see if merge is not getting triggered when it should.</span></span>  
  
## <a name="performing-a-manual-merge"></a><span data-ttu-id="5768f-110">Ausführen einer manuellen Zusammenführung</span><span class="sxs-lookup"><span data-stu-id="5768f-110">Performing a Manual Merge</span></span>  
 <span data-ttu-id="5768f-111">Sie können [sys. sp_xtp_merge_checkpoint_files &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) verwenden, um eine manuelle Zusammenführung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5768f-111">You can use [sys.sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) to perform a manual merge.</span></span>  
  
 <span data-ttu-id="5768f-112">Verwenden Sie die folgende Abfrage, um Informationen zu den Daten- und Änderungsdateien abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5768f-112">Use the following query to retrieve information about the data and delta files,</span></span>  
  
```sql  
select checkpoint_file_id, file_type_desc, internal_storage_slot, file_size_in_bytes, file_size_used_in_bytes,   
inserted_row_count, deleted_row_count, lower_bound_tsn, upper_bound_tsn   
from sys.dm_db_xtp_checkpoint_files  
where state = 1  
order by file_type_desc, upper_bound_tsn  
```  
  
 <span data-ttu-id="5768f-113">Angenommen, Sie haben drei Datendateien gefunden, die nicht zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="5768f-113">Assume that you found three data files that have not been merged.</span></span> <span data-ttu-id="5768f-114">Mithilfe des `lower_bound_tsn`-Werts der ersten Datendatei sowie des `upper_bound_tsn`-Werts der letzten Datendatei können Sie den folgenden Befehl ausgeben:</span><span class="sxs-lookup"><span data-stu-id="5768f-114">Using the `lower_bound_tsn` value of the first data file and the `upper_bound_tsn` of the last data file, you can issue the following command:</span></span>  
  
```sql  
exec sys.sp_xtp_merge_checkpoint_files 'H_DB',  12345, 67890  
```  
  
 <span data-ttu-id="5768f-115">Angenommen, die drei Daten-/Änderungsdateipaare enthielten jeweils 15.836 Zeilen und 5.279 gelöschte Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5768f-115">Assume that the three data and delta file pairs each had 15,836 rows and 5,279 deleted rows.</span></span> <span data-ttu-id="5768f-116">Nach der Zusammenführung enthält die neue Datendatei 31.872 Zeilen und 0 gelöschte Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5768f-116">After the merge, the new data file has 31,872 rows and 0 deleted rows.</span></span> <span data-ttu-id="5768f-117">Die Größe der neuen Datendatei kann deutlich oberhalb der ursprünglich zugeordneten Größe von 128 MB liegen.</span><span class="sxs-lookup"><span data-stu-id="5768f-117">The size of the new data file can be much larger than the initially allocated size of 128MB.</span></span> <span data-ttu-id="5768f-118">Dies liegt daran, dass die Mergerichtlinie durch die manuelle Zusammenführung überschrieben und die Zusammenführung der angeforderten Dateien erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="5768f-118">This is because manual merge overrides the merge policy and forces the merge of the requested files.</span></span>  
  
 <span data-ttu-id="5768f-119">Der Blog [Zustandsübergang von Prüf Punkt Dateien in Datenbanken mit Speicher optimierten Tabellen](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) beschreibt den Zustandsübergang von Daten-und Änderungsdatei Paaren von Anfang zu Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5768f-119">The blog [State Transition of Checkpoint Files in Databases with Memory-Optimized Tables](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) describes state transition of data and delta file pairs from inception to garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5768f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5768f-120">See Also</span></span>  
 [<span data-ttu-id="5768f-121">Erstellen und Verwalten von Speicher für speicheroptimierte Objekte</span><span class="sxs-lookup"><span data-stu-id="5768f-121">Creating and Managing Storage for Memory-Optimized Objects</span></span>](../relational-databases/in-memory-oltp/creating-and-managing-storage-for-memory-optimized-objects.md)  
  
