---
title: Datenbankspiegelung und Volltextkataloge (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- full-text catalogs [SQL Server], database mirroring
- catalogs [SQL Server], database mirroring
ms.assetid: e34072ae-fe8a-462d-bb03-02fa0987f793
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 39929f4bed6edbd1e8ec5c1b72dbe8f7aefeec68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615571"
---
# <a name="database-mirroring-and-full-text-catalogs-sql-server"></a><span data-ttu-id="4c3e5-102">Datenbankspiegelung und Volltextkataloge (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c3e5-102">Database Mirroring and Full-Text Catalogs (SQL Server)</span></span>
  <span data-ttu-id="4c3e5-103">Führen Sie zum Erstellen einer Datenbankspiegelung mit einem Volltextkatalog den üblichen Sicherungsvorgang aus, um eine vollständige Sicherung der Prinzipaldatenbank zu erstellen, und stellen Sie die Sicherung wieder her, um die Datenbank auf den Spiegelserver zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-103">To mirror a database that has a full-text catalog, use backup as usual to create a full database backup of the principal database, and then restore the backup to copy the database to the mirror server.</span></span> <span data-ttu-id="4c3e5-104">Weitere Informationen finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-104">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
## <a name="full-text-catalog-and-indexes-before-failover"></a><span data-ttu-id="4c3e5-105">Volltextkataloge und -indizes vor dem Failover</span><span class="sxs-lookup"><span data-stu-id="4c3e5-105">Full-Text Catalog and Indexes Before Failover</span></span>  
 <span data-ttu-id="4c3e5-106">In einer neu erstellten Spiegeldatenbank ist der Volltextkatalog mit jenem Volltextkatalog identisch, der während der Datenbanksicherung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-106">In a newly created mirror database, the full-text catalog is the same as when the database was backed up.</span></span> <span data-ttu-id="4c3e5-107">Nach Beginn der Datenbankspiegelung werden alle durch DDL-Anweisungen (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) vorgenommenen Änderungen an der Katalogebene protokolliert und an den Spiegelserver gesendet, um in der Spiegeldatenbank wiedergegeben zu werden.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-107">After database mirroring starts, any catalog-level changes that were made by DDL statements (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) are logged and sent to the mirror server to be replayed on the mirror database.</span></span> <span data-ttu-id="4c3e5-108">Änderungen auf Indexebene werden jedoch nicht in der Spiegeldatenbank reproduziert, da sie nicht auf dem Prinzipalserver protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-108">However, index-level changes are not reproduced on the mirror database because it is not logged on to the principal server.</span></span> <span data-ttu-id="4c3e5-109">Daher ist der Inhalt des Volltextkatalogs in der Spiegeldatenbank nicht mehr mit dem Volltextkatalog in der Prinzipaldatenbank synchron, wenn sich letzterer ändert.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-109">Therefore, as the contents of the full-text catalog change on the principal database, the contents of the full-text catalog on the mirror database are unsynchronized.</span></span>  
  
## <a name="full-text-indexes-after-failover"></a><span data-ttu-id="4c3e5-110">Volltextindizes nach einem Failover</span><span class="sxs-lookup"><span data-stu-id="4c3e5-110">Full-Text Indexes After Failover</span></span>  
 <span data-ttu-id="4c3e5-111">Nach einem Failover ist in folgenden Situationen eine vollständige Durchforstung des Volltextindexes auf dem neuen Prinzipalserver erforderlich oder zumindest nützlich:</span><span class="sxs-lookup"><span data-stu-id="4c3e5-111">After a failover, a full crawl of a full-text index on the new principal server might be required or useful in the following situations:</span></span>  
  
-   <span data-ttu-id="4c3e5-112">Wenn die Änderungsnachverfolgung für den Volltextindex AUSgeschaltet ist, müssen Sie eine vollständige Durchforstung für diesen Index durchführen. Verwenden Sie dazu die folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="4c3e5-112">If change-tracking is turned OFF on a full text index, you must start a full crawl on that index by using the following statement:</span></span>  
  
     <span data-ttu-id="4c3e5-113">ALTER FULLTEXT INDEX ON *Tabellenname* START FULL POPULATION</span><span class="sxs-lookup"><span data-stu-id="4c3e5-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span></span>  
  
-   <span data-ttu-id="4c3e5-114">Wenn für einen Volltextindex die automatische Änderungsnachverfolgung konfiguriert ist, wird der Volltextindex automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-114">If a full-text index is configured for automatic change tracking, the full-text index is automatically synchronized.</span></span> <span data-ttu-id="4c3e5-115">Durch die Synchronisierung wird jedoch die Leistung des Volltextindexes beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-115">However, synchronization slows full-text performance somewhat.</span></span> <span data-ttu-id="4c3e5-116">Verlangsamt sich die Ausführung übermäßig, können Sie eine vollständige Durchforstung verursachen, indem Sie die Änderungsnachverfolgung ausschalten und anschließend wieder die automatische Änderungsnachverfolgung festlegen:</span><span class="sxs-lookup"><span data-stu-id="4c3e5-116">If performance is too slow, you can cause a full crawl by setting change tracking off and then resetting it to automatic:</span></span>  
  
    -   <span data-ttu-id="4c3e5-117">So schalten Sie die Änderungsnachverfolgung aus:</span><span class="sxs-lookup"><span data-stu-id="4c3e5-117">To set change tracking off:</span></span>  
  
         <span data-ttu-id="4c3e5-118">ALTER FULLTEXT INDEX ON *Tabellenname* SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="4c3e5-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span></span>  
  
    -   <span data-ttu-id="4c3e5-119">So legen Sie die automatische Änderungsnachverfolgung fest:</span><span class="sxs-lookup"><span data-stu-id="4c3e5-119">To set on automatic change tracking to automatic:</span></span>  
  
         <span data-ttu-id="4c3e5-120">ALTER FULLTEXT INDEX ON *Tabellenname* SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="4c3e5-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c3e5-121">Wenn Sie sehen möchten, ob die automatische Änderungsnachverfolgung aktiviert ist, können Sie die [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) -Funktion zum Abfragen der **TableFullTextBackgroundUpdateIndexOn** -Eigenschaft der Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-121">To see whether auto change tracking is on, you can use the [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) function to query the **TableFullTextBackgroundUpdateIndexOn** property of the table.</span></span>  
  
 <span data-ttu-id="4c3e5-122">Weitere Informationen finden Sie unter [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4c3e5-122">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c3e5-123">Das Starten eines Durchforstungsvorgangs nach einem Failover funktioniert gleichermaßen wie das Starten eines Durchforstungsvorgangs nach einer Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-123">Starting a crawl after failover works the same as starting a crawl after a restore.</span></span>  
  
## <a name="after-forcing-service"></a><span data-ttu-id="4c3e5-124">Nach dem Erzwingen des Diensts</span><span class="sxs-lookup"><span data-stu-id="4c3e5-124">After Forcing Service</span></span>  
 <span data-ttu-id="4c3e5-125">Führen Sie einen vollständige Durchforstung durch, nachdem die Ausführung des Diensts auf dem Spiegelserver (mit möglichem Datenverlust) erzwungen wurde.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-125">After service is forced to the mirror server (with possible data loss), start a full crawl.</span></span> <span data-ttu-id="4c3e5-126">Die zu verwendende Methode zum Starten einer vollständigen Durchforstung hängt davon ab, ob für den betroffenen Volltextindex die Änderungsnachverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4c3e5-126">The method to use for starting a full crawl depends on whether the full-text index is change tracked.</span></span> <span data-ttu-id="4c3e5-127">Weitere Informationen finden Sie weiter oben in diesem Thema unter "Volltextindizes nach einem Failover".</span><span class="sxs-lookup"><span data-stu-id="4c3e5-127">For more information, see "Full-Text Indexes After Failover," earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c3e5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c3e5-128">See Also</span></span>  
 <span data-ttu-id="4c3e5-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c3e5-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="4c3e5-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c3e5-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="4c3e5-131">[DROP FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c3e5-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="4c3e5-132">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c3e5-132">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="4c3e5-133">Sichern und Wiederherstellen von Volltextkatalogen und Indizes</span><span class="sxs-lookup"><span data-stu-id="4c3e5-133">Back Up and Restore Full-Text Catalogs and Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
  
