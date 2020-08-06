---
title: Sichern und Wiederherstellen von Volltextkatalogen und Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], backing up
- full-text search [SQL Server], back up and restore
- recovery [full-text search]
- backups [SQL Server], full-text indexes
- full-text indexes [SQL Server], restoring
- restore operations [full-text search]
ms.assetid: 6a4080d9-e43f-4b7b-a1da-bebf654c1194
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0df49c03325da375427c6566799f374fcc9dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621445"
---
# <a name="back-up-and-restore-full-text-catalogs-and-indexes"></a><span data-ttu-id="1b474-102">Sichern und Wiederherstellen von Volltextkatalogen und Indizes</span><span class="sxs-lookup"><span data-stu-id="1b474-102">Back Up and Restore Full-Text Catalogs and Indexes</span></span>
  <span data-ttu-id="1b474-103">In diesem Thema wird erläutert, wie Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]erstellte Volltextindizes sichern und wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="1b474-103">This topic explains how to back up and restore full-text indexes created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1b474-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist der Volltextkatalog ein logisches Konzept und befindet sich nicht in einer Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="1b474-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the full-text catalog is a logical concept and does not reside in a filegroup.</span></span> <span data-ttu-id="1b474-105">Um in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]einen Volltextkatalog zu sichern, müssen Sie daher jede Dateigruppe identifizieren, die einen Volltextindex enthält, der zum Katalog gehört.</span><span class="sxs-lookup"><span data-stu-id="1b474-105">Therefore, to back up a full-text catalog in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must identify every filegroup that contains a full-text index that belongs to the catalog.</span></span> <span data-ttu-id="1b474-106">Dann müssen Sie diese Dateigruppen einzeln sichern.</span><span class="sxs-lookup"><span data-stu-id="1b474-106">Then you must back up those filegroups, one by one.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b474-107">Beim Aktualisieren einer [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] -Datenbank ist es möglich, Volltextkataloge zu importieren.</span><span class="sxs-lookup"><span data-stu-id="1b474-107">It is possible to import full-text catalogs when upgrading a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database.</span></span> <span data-ttu-id="1b474-108">Jeder importierte Volltextkatalog ist eine Datenbankdatei in einer eigenen Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="1b474-108">Each imported full-text catalog is a database file in its own filegroup.</span></span> <span data-ttu-id="1b474-109">Um einen importierten Katalog zu sichern, können Sie einfach die entsprechende Dateigruppe sichern.</span><span class="sxs-lookup"><span data-stu-id="1b474-109">To back up an imported catalog, simply back up its filegroup.</span></span> <span data-ttu-id="1b474-110">Weitere Informationen finden Sie unter [Sichern und Wiederherstellen von Volltextkatalogen](https://go.microsoft.com/fwlink/?LinkID=121052)in der [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1b474-110">For more information, see [Backing Up and Restoring Full-Text Catalogs](https://go.microsoft.com/fwlink/?LinkID=121052), in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Books Online.</span></span>  
  
##  <a name="backing-up-the-full-text-indexes-of-a-full-text-catalog"></a><a name="backingup"></a> <span data-ttu-id="1b474-111">Sichern der Volltextindizes eines Volltextkatalogs</span><span class="sxs-lookup"><span data-stu-id="1b474-111">Backing Up the Full-Text Indexes of a Full-Text Catalog</span></span>  
  
###  <a name="finding-the-full-text-indexes-of-a-full-text-catalog"></a><a name="Find_FTIs_of_a_Catalog"></a> <span data-ttu-id="1b474-112">Suchen der Volltextindizes eines Volltextkatalogs</span><span class="sxs-lookup"><span data-stu-id="1b474-112">Finding the Full-Text Indexes of a Full-Text Catalog</span></span>  
 <span data-ttu-id="1b474-113">Sie können die Eigenschaften der Volltextindizes abrufen, indem Sie die folgende [SELECT](/sql/t-sql/queries/select-transact-sql) -Anweisung verwenden. Diese Anweisung wählt Spalten aus den Katalogsichten [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) und [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="1b474-113">You can retrieve the properties of the full-text indexes by using the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement, which selects columns from the [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) and [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) catalog views.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @TableID int;  
SET @TableID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product'));  
SELECT object_name(@TableID), i.is_enabled, i.change_tracking_state,   
   i.has_crawl_completed, i.crawl_type, c.name as fulltext_catalog_name   
   FROM sys.fulltext_indexes i, sys.fulltext_catalogs c   
   WHERE i.fulltext_catalog_id = c.fulltext_catalog_id;  
GO  
```  
  

  
###  <a name="finding-the-filegroup-or-file-that-contains-a-full-text-index"></a><a name="Find_FG_of_FTI"></a> <span data-ttu-id="1b474-114">Suchen der Dateigruppe oder der Datei, die einen Volltextindex enthält</span><span class="sxs-lookup"><span data-stu-id="1b474-114">Finding the Filegroup or File That Contains a Full-Text Index</span></span>  
 <span data-ttu-id="1b474-115">Wenn ein Volltextindex erstellt wird, wird dieser an einem der folgenden Speicherorte gespeichert:</span><span class="sxs-lookup"><span data-stu-id="1b474-115">When a full-text index is created, it is placed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="1b474-116">In einer vom Benutzer angegebenen Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="1b474-116">A user-specified filegroup.</span></span>  
  
-   <span data-ttu-id="1b474-117">In derselben Dateigruppe als Basistabelle oder Sicht für eine nicht partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="1b474-117">The same filegroup as base table or view, for a nonpartitioned table.</span></span>  
  
-   <span data-ttu-id="1b474-118">In der primären Dateigruppe für eine partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="1b474-118">The primary filegroup, for a partitioned table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b474-119">Informationen zum Erstellen eines Volltextindex finden Sie unter [Erstellen und Verwalten von Volltextindizes](create-and-manage-full-text-indexes.md)[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b474-119">For information about creating a full-text index, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) and [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="1b474-120">Um die Dateigruppe eines Volltextindex für eine Tabelle oder Sicht zu finden, verwenden Sie die folgende Abfrage, in der *object_name* für den Namen der Tabelle oder Sicht steht:</span><span class="sxs-lookup"><span data-stu-id="1b474-120">To find the filegroup of full-text index on a table or view, use the following query, where *object_name* is the name of the table or view:</span></span>  
  
```  
SELECT name FROM sys.filegroups f, sys.fulltext_indexes i   
   WHERE f.data_space_id = i.data_space_id   
      and i.object_id = object_id('object_name');  
GO  
  
```  
  

  
###  <a name="backing-up-the-filegroups-that-contain-full-text-indexes"></a><a name="Back_up_FTIs_of_FTC"></a> <span data-ttu-id="1b474-121">Sichern der Dateigruppen, die Volltextindizes enthalten</span><span class="sxs-lookup"><span data-stu-id="1b474-121">Backing Up the Filegroups That Contain Full-Text Indexes</span></span>  
 <span data-ttu-id="1b474-122">Nachdem Sie die Dateigruppen gefunden haben, die die Indizes eines Volltextkatalogs enthalten, müssen Sie die einzelnen Dateigruppen sichern.</span><span class="sxs-lookup"><span data-stu-id="1b474-122">After you find the filegroups that contain the indexes of a full-text catalog, you need back up each of the filegroups.</span></span> <span data-ttu-id="1b474-123">Während der Sicherung können Volltextkataloge nicht gelöscht oder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1b474-123">During the backup process, full-text catalogs may not be dropped or added.</span></span>  
  
 <span data-ttu-id="1b474-124">Die erste Sicherung einer Dateigruppe muss eine vollständige Dateisicherung sein.</span><span class="sxs-lookup"><span data-stu-id="1b474-124">The first backup of a filegroup must be a full file backup.</span></span> <span data-ttu-id="1b474-125">Nachdem Sie eine vollständige Dateisicherung für eine Dateigruppe erstellt haben, können Sie bei Bedarf nur die Änderungen in einer Dateigruppe sichern, indem Sie eine oder mehrere differenzielle Dateisicherungen erstellen, die auf dieser vollständigen Dateisicherung basieren.</span><span class="sxs-lookup"><span data-stu-id="1b474-125">After you have created a full file backup for a filegroup, you could back up only the changes in a filegroup by creating a series of one or more differential file backups that are based on the full file backup.</span></span>  
  
 <span data-ttu-id="1b474-126">**So sichern Sie Dateien und Dateigruppen**</span><span class="sxs-lookup"><span data-stu-id="1b474-126">**To back up files and filegroups**</span></span>  
  
-   [<span data-ttu-id="1b474-127">Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1b474-127">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="1b474-128">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b474-128">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  

  
##  <a name="restoring-a-full-text-index"></a><a name="Restore_FTI"></a> <span data-ttu-id="1b474-129">Wiederherstellen eines Volltextindexes</span><span class="sxs-lookup"><span data-stu-id="1b474-129">Restoring a Full-Text Index</span></span>  
 <span data-ttu-id="1b474-130">Beim Wiederherstellen einer gesicherten Dateigruppe werden die Volltextindexdateien und die anderen Dateien der Dateigruppe wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="1b474-130">Restoring a backed-up filegroup restores the full-text index files, as well as the other files in the filegroup.</span></span> <span data-ttu-id="1b474-131">Standardmäßig wird die Dateigruppe an dem Speicherort auf einem Datenträger wiederhergestellt, an dem die Dateigruppe gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b474-131">By default, the filegroup is restored to the disk location on which the filegroup was backed up.</span></span>  
  
 <span data-ttu-id="1b474-132">Wenn bei der Erstellung der Sicherung eine Tabelle mit Volltextindizierung online war und eine Auffüllung ausgeführt wurde, wird die Auffüllung nach der Wiederherstellung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1b474-132">If a full-text indexed table was online and a population was running when the backup was created, the population is resumed after the restore.</span></span>  
  
 <span data-ttu-id="1b474-133">**So stellen Sie eine Dateigruppe wieder her**</span><span class="sxs-lookup"><span data-stu-id="1b474-133">**To restore a filegroup**</span></span>  
  
-   [<span data-ttu-id="1b474-134">Wiederherstellen von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1b474-134">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="1b474-135">Wiederherstellen von Dateien und Dateigruppen über vorhandene Dateien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1b474-135">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="1b474-136">Wiederherstellen von Dateien an einem neuen Speicherort &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1b474-136">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="1b474-137">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b474-137">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  

  
## <a name="see-also"></a><span data-ttu-id="1b474-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b474-138">See Also</span></span>  
 <span data-ttu-id="1b474-139">[Verwalten und Überwachen der Volltextsuche auf einer Serverinstanz](manage-and-monitor-full-text-search-for-a-server-instance.md) </span><span class="sxs-lookup"><span data-stu-id="1b474-139">[Manage and Monitor Full-Text Search for a Server Instance](manage-and-monitor-full-text-search-for-a-server-instance.md) </span></span>  
 [<span data-ttu-id="1b474-140">Upgrade der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="1b474-140">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  
