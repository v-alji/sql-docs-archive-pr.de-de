---
title: Datenbankeigenschaften (Seite des Abfragespeichers) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.querystore.f1
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
author: stevestein
ms.author: sstein
ms.openlocfilehash: bab0d9b697e9ad9ec4b27f320d26b9b9edb5944e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718223"
---
# <a name="database-properties-query-store-page"></a><span data-ttu-id="e0ab8-102">Datenbankeigenschaften (Seite des Abfragespeichers)</span><span class="sxs-lookup"><span data-stu-id="e0ab8-102">Database Properties (Query Store Page)</span></span>
  <span data-ttu-id="e0ab8-103">Greifen Sie von der Prinzipaldatenbank aus auf diese Seite zu, um damit die Eigenschaften des Datenbank-Abfragespeichers zu konfigurieren und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-103">Access this page from the principal database, and use it to configure and to modify the properties of the database query store.</span></span> <span data-ttu-id="e0ab8-104">Diese Optionen können auch mithilfe der [ALTER DATABASE SET-Optionen](/sql/t-sql/statements/alter-database-transact-sql-set-options)konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-104">These options can also be configure by using the [ALTER DATABASE SET options](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span> <span data-ttu-id="e0ab8-105">Weitere Informationen zum Abfragespeicher finden Sie unter [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="e0ab8-105">For information about the query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="e0ab8-106">**Gilt für**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0ab8-106">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span></span>|  
  
## <a name="options"></a><span data-ttu-id="e0ab8-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e0ab8-107">Options</span></span>  
 <span data-ttu-id="e0ab8-108">Aktivieren</span><span class="sxs-lookup"><span data-stu-id="e0ab8-108">Enable</span></span>  
 <span data-ttu-id="e0ab8-109">Aktiviert und deaktiviert den Abfragespeicher.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-109">Enables and disables the query store.</span></span>  
  
 <span data-ttu-id="e0ab8-110">Betriebsmodus</span><span class="sxs-lookup"><span data-stu-id="e0ab8-110">Operation Mode</span></span>  
 <span data-ttu-id="e0ab8-111">Gültige Werte sind READ_ONLY und READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-111">Valid values are READ_ONLY and READ_WRITE.</span></span> <span data-ttu-id="e0ab8-112">Im Modus READ_WRITE sammelt und speichert der Abfragespeicher Angaben zum Abfrageplan und statistische Informationen zur Laufzeitausführung.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-112">In READ_WRITE mode, the query store collects and persists query plan and runtime execution statistics information.</span></span> <span data-ttu-id="e0ab8-113">Im Modus READ_ONLY können Informationen aus dem Abfragespeicher gelesen werden, es werden jedoch keine neuen Informationen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-113">In READ_ONLY mode, information can be read from the query store, but new information is not added.</span></span> <span data-ttu-id="e0ab8-114">Wenn die maximale Speicherplatzbelegung des Abfragespeichers ausgelastet ist, wird der Betriebsmodus in READ_ONLY geändert.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-114">If the maximum allocated space of the query store has been exhausted, the query store will change its operation mode to READ_ONLY.</span></span>  
  
 <span data-ttu-id="e0ab8-115">Betriebsmodus (tatsächlich)</span><span class="sxs-lookup"><span data-stu-id="e0ab8-115">Operation Mode (Actual)</span></span>  
 <span data-ttu-id="e0ab8-116">Ruft den tatsächlichen Betriebsmodus des Abfragespeichers ab.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-116">Gets the actual operation mode of the query store.</span></span>  
  
 <span data-ttu-id="e0ab8-117">Betriebsmodus (angefordert)</span><span class="sxs-lookup"><span data-stu-id="e0ab8-117">Operation Mode (Requested)</span></span>  
 <span data-ttu-id="e0ab8-118">Ruft den gewünschten Betriebsmodus des Abfragespeichers ab und legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-118">Gets and sets the desired operation mode of the query store.</span></span>  
  
 <span data-ttu-id="e0ab8-119">Datenleerungsintervall (Minuten)</span><span class="sxs-lookup"><span data-stu-id="e0ab8-119">Data Flush Interval (Minutes)</span></span>  
 <span data-ttu-id="e0ab8-120">Bestimmt die Häufigkeit, mit der in den Abfragespeicher geschriebene Daten auf Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-120">Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="e0ab8-121">Um die Leistung zu optimieren, werden durch den Abfragespeicher gesammelte Daten asynchron auf den Datenträger geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-121">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="e0ab8-122">Konfiguriert die Häufigkeit, mit der diese asynchrone Übertragung auftritt.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-122">The frequency at which this asynchronous transfer occurs is configured.</span></span>  
  
 <span data-ttu-id="e0ab8-123">Statistiksammlungsintervall</span><span class="sxs-lookup"><span data-stu-id="e0ab8-123">Statistics Collection Interval</span></span>  
 <span data-ttu-id="e0ab8-124">Ruft den Wert für das Statistiksammlungsintervall ab und legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-124">Gets and sets the statistics collection interval value.</span></span>  
  
 <span data-ttu-id="e0ab8-125">Maximale Größe (MB)</span><span class="sxs-lookup"><span data-stu-id="e0ab8-125">Max Size (MB)</span></span>  
 <span data-ttu-id="e0ab8-126">Ruft die Größe des gesamten Speicherplatzes ab, der dem Abfragespeicher zugeordnet ist, und legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-126">Gets and sets the total space allocated to the query store.</span></span>  
  
 <span data-ttu-id="e0ab8-127">Schwellenwert für veraltete Abfrage (Tage)</span><span class="sxs-lookup"><span data-stu-id="e0ab8-127">Stale Query Threshold (Days)</span></span>  
 <span data-ttu-id="e0ab8-128">Ruft den Schwellenwert für veraltete Abfragen ab und legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-128">Gets and sets the stale query threshold.</span></span> <span data-ttu-id="e0ab8-129">Konfigurieren Sie das STALE_QUERY_THRESHOLD_DAYS-Argument, um die Anzahl der Tage anzugeben, für die Daten im Abfragespeicher beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-129">Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>  
  
 <span data-ttu-id="e0ab8-130">Abfragedaten bereinigen</span><span class="sxs-lookup"><span data-stu-id="e0ab8-130">Purge Query Data</span></span>  
 <span data-ttu-id="e0ab8-131">Entfernt den Inhalt des Abfragespeichers.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-131">Removes the contents of the query store.</span></span>  
  
 <span data-ttu-id="e0ab8-132">Kreisdiagramme</span><span class="sxs-lookup"><span data-stu-id="e0ab8-132">Pie Charts</span></span>  
 <span data-ttu-id="e0ab8-133">Das linke Diagramm zeigt die gesamte Nutzung der Datenbankdatei auf dem Datenträger und den Teil der Datei, der mit der Abfragespeicherdaten gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-133">The left chart shows the total database file consumption on the disk, and the portion of the file which is filled with the query store data.</span></span>  
  
 <span data-ttu-id="e0ab8-134">Das rechte Diagramm zeigt den derzeit verbrauchten Anteil des Abfragespeicherkontingents.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-134">The right chart shows the portion of the query store quota which is currently used up.</span></span> <span data-ttu-id="e0ab8-135">Beachten Sie, dass das Kontingent im linken Diagramm nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-135">Note that the quota is not shown in the left chart.</span></span> <span data-ttu-id="e0ab8-136">Das Kontingent kann die aktuelle Größe der Datenbank überschreiten.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-136">The quota may exceed the current size of the database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0ab8-137">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0ab8-137">Remarks</span></span>  
 <span data-ttu-id="e0ab8-138">Der Abfragespeicher bietet über DBAs Einblick in die Auswahl und die Leistung des Abfrageplans.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-138">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="e0ab8-139">Er vereinfacht das Beheben von Leistungsproblemen, indem er das schnelle Auffinden von Leistungsabweichungen durch Änderungen an Abfrageplänen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-139">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="e0ab8-140">Das Feature erfasst automatisch einen Verlauf der Abfrage-, Plan- und Laufzeitstatistiken und bewahrt diese zur Überprüfung auf.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-140">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="e0ab8-141">Es unterteilt die Daten nach Zeitfenstern und ermöglicht es Ihnen so, Verwendungsmuster für Datenbanken zu erkennen und zu verstehen, wann Abfrageplanänderungen auf dem Server aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-141">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="e0ab8-142">Der Abfragespeicher kann mithilfe dieser Eigenschaftenseite der Abfragespeicherdatenbank oder mithilfe der [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) -Option konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-142">The query store can be configured by using this query store database property page, or by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span> <span data-ttu-id="e0ab8-143">Der Abfragespeicher stellt Informationen mithilfe eines [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] -Dialogfelds dar.</span><span class="sxs-lookup"><span data-stu-id="e0ab8-143">The query store presents information by using a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dialog box.</span></span> <span data-ttu-id="e0ab8-144">Weitere Informationen zum Abfragespeicher finden Sie unter [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="e0ab8-144">For more information about query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ab8-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0ab8-145">See Also</span></span>  
 <span data-ttu-id="e0ab8-146">[Gespeicherte Prozeduren für den Abfragespeicher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0ab8-146">[Query Store Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="e0ab8-147">Katalogsichten des Abfragespeichers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0ab8-147">Query Store Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/query-store-catalog-views-transact-sql)  
  
  
