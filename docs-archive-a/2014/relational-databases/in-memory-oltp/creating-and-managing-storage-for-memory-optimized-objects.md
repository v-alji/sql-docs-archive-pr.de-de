---
title: Erstellen und Verwalten von Speicher für speicheroptimierte Objekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 622aabe6-95c7-42cc-8768-ac2e679c5089
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 118e5e582a284023dd8e5cc71629d635e79fb989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616565"
---
# <a name="creating-and-managing-storage-for-memory-optimized-objects"></a><span data-ttu-id="dc8af-102">Erstellen und Verwalten von Speicher für speicheroptimierte Objekte</span><span class="sxs-lookup"><span data-stu-id="dc8af-102">Creating and Managing Storage for Memory-Optimized Objects</span></span>
  <span data-ttu-id="dc8af-103">Die [!INCLUDE[hek_2](../../includes/hek-2-md.md)]-Engine ist in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]integriert, was es Ihnen ermöglicht, sowohl speicheroptimierte als auch (traditionelle) datenträgerbasierte Tabellen in der gleichen Datenbank zu haben.</span><span class="sxs-lookup"><span data-stu-id="dc8af-103">The [!INCLUDE[hek_2](../../includes/hek-2-md.md)] engine is integrated into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which lets you have both memory-optimized tables and (traditional) disk-based tables in the same database.</span></span> <span data-ttu-id="dc8af-104">Jedoch unterscheidet sich die Speicherstruktur für speicheroptimierte Tabellen von der für datenträgerbasierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="dc8af-104">However, the storage structure for memory-optimized tables is different from disk-based tables.</span></span>  
  
 <span data-ttu-id="dc8af-105">Speicher für datenträgerbasierte Tabelle weisen die folgenden Schlüsselattribute auf:</span><span class="sxs-lookup"><span data-stu-id="dc8af-105">Storage for disk-based table has following key attributes:</span></span>  
  
-   <span data-ttu-id="dc8af-106">Einer Dateigruppe zugeordnet, und die Dateigruppe enthält eine oder mehrere Dateien.</span><span class="sxs-lookup"><span data-stu-id="dc8af-106">Mapped to a filegroup and the filegroup contains one or more files.</span></span>  
  
-   <span data-ttu-id="dc8af-107">Jede Datei wird in Blöcke mit 8 Seiten unterteilt, und jede Seite hat eine Größe von 8.000 Byte.</span><span class="sxs-lookup"><span data-stu-id="dc8af-107">Each file is divided into extents of 8 pages and each page is of size 8K bytes.</span></span>  
  
-   <span data-ttu-id="dc8af-108">Ein Block kann über mehrere Tabellen gemeinsam genutzt werden, aber es gibt eine 1:1-Zuordnung zwischen der zugeordneten Seite und der Tabelle oder dem Index.</span><span class="sxs-lookup"><span data-stu-id="dc8af-108">An extent can be shared across multiple tables, but a there is 1-to-1 mapping between an allocated page and the table or index.</span></span> <span data-ttu-id="dc8af-109">Das bedeutet, dass eine Tabelle keine Zeilen von zwei oder mehr Tabellen oder Indizes enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="dc8af-109">In other words, a page can't have rows from two or more tables or index.</span></span>  
  
-   <span data-ttu-id="dc8af-110">Die Daten werden je nach Bedarf in den Arbeitsspeicher (der Pufferpool) verschoben, und die geänderten oder neu erstellten Seiten werden asynchron auf den Datenträger geschrieben, wobei hauptsächlich zufällige Ein- und Ausgaben generiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc8af-110">The data is moved into memory (the buffer pool) as needed and the modified or newly created pages are asynchronously written to the disk generating mostly random IO.</span></span>  
  
 <span data-ttu-id="dc8af-111">Speicher für speicheroptimierte Tabellen weisen die folgenden Schlüsselattribute auf:</span><span class="sxs-lookup"><span data-stu-id="dc8af-111">Storage for memory-optimized tables has following key attributes:</span></span>  
  
-   <span data-ttu-id="dc8af-112">Alle Speicher optimierten Tabellen sind einer Speicher optimierten Datei Gruppe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="dc8af-112">All memory-optimized tables are mapped to a memory-optimized filegroup.</span></span> <span data-ttu-id="dc8af-113">Diese Datei Gruppe wird mithilfe der FILESTREAM-Datei Gruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc8af-113">This filegroup is built using the filestream filegroup.</span></span>  
  
-   <span data-ttu-id="dc8af-114">Es gibt keine Seiten und die Daten werden als Zeile dauerhaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc8af-114">There are no pages and the data is persisted as a row.</span></span>  
  
-   <span data-ttu-id="dc8af-115">Alle Änderungen an speicheroptimierten Tabellen werden durch Anfügevorgänge an aktive Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc8af-115">All changes to memory-optimized tables are stored by appending to active files.</span></span> <span data-ttu-id="dc8af-116">Sowohl das Lesen als auch das Schreiben an Dateien ist sequenziell.</span><span class="sxs-lookup"><span data-stu-id="dc8af-116">Both reading and writing to files is sequential.</span></span>  
  
-   <span data-ttu-id="dc8af-117">Eine Aktualisierung wird jedoch als Vorgang implementiert, der aus einer Löschung und einer Einfügung besteht.</span><span class="sxs-lookup"><span data-stu-id="dc8af-117">An update is implemented as a delete followed by an insert.</span></span> <span data-ttu-id="dc8af-118">Die gelöschten Zeilen werden nicht sofort aus dem Speicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="dc8af-118">The deleted rows are not immediately removed from the storage.</span></span> <span data-ttu-id="dc8af-119">Die gelöschten Zeilen werden durch einen im Hintergrund ausgeführten Prozess namens MERGE entfernt; dies geschieht basierend auf einer Richtlinie wie in [Dauerhaftigkeit für speicheroptimierte Tabellen](memory-optimized-tables.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc8af-119">The deleted rows are removed by a background process, called MERGE, based on a policy as described in [Durability for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="dc8af-120">Im Gegensatz zum Speicher für datenträgerbasierten Tabellen wird der Speicher für speicheroptimierte Tabellen nicht komprimiert.</span><span class="sxs-lookup"><span data-stu-id="dc8af-120">Unlike disk-based tables, storage for memory-optimized tables is not compressed.</span></span> <span data-ttu-id="dc8af-121">Beim Migrieren einer komprimierten (ZEILE oder SEITE), datenträgerbasierten Tabelle zu einer speicheroptimierten Tabelle müssen Sie die Größenänderungen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="dc8af-121">When migrating a compressed (ROW or PAGE) disk-based table to memory-optimized table, you will need to account for the change in size.</span></span>  
  
-   <span data-ttu-id="dc8af-122">Eine speicheroptimierte Tabelle kann sowohl dauerhaft als auch nicht dauerhaft sein.</span><span class="sxs-lookup"><span data-stu-id="dc8af-122">A memory-optimized table can be durable or can be non-durable.</span></span> <span data-ttu-id="dc8af-123">Sie müssen Speicher nur für dauerhafte Speicher optimierte Tabellen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc8af-123">You only need to configure storage for durable memory-optimize tables.</span></span>  
  
 <span data-ttu-id="dc8af-124">In diesem Abschnitt werden Prüfpunktdateipaare und weitere Aspekte der Speicherung von Daten in speicheroptimierten Tabellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc8af-124">This section describes checkpoint file pairs and other aspects of how data in memory-optimized tables is stored.</span></span>  
  
 <span data-ttu-id="dc8af-125">Themen in diesem Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="dc8af-125">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="dc8af-126">Konfigurieren von Speicher für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="dc8af-126">Configuring Storage for Memory-Optimized Tables</span></span>](configuring-storage-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="dc8af-127">Die speicheroptimierte Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="dc8af-127">The Memory Optimized Filegroup</span></span>](the-memory-optimized-filegroup.md)  
  
-   [<span data-ttu-id="dc8af-128">Dauerhaftigkeit für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="dc8af-128">Durability for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
-   [<span data-ttu-id="dc8af-129">Prüfpunktvorgang für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="dc8af-129">Checkpoint Operation for Memory-Optimized Tables</span></span>](checkpoint-operation-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="dc8af-130">Definieren von Dauerhaftigkeit für speicheroptimierte Objekte</span><span class="sxs-lookup"><span data-stu-id="dc8af-130">Defining Durability for Memory-Optimized Objects</span></span>](defining-durability-for-memory-optimized-objects.md)  
  
-   [<span data-ttu-id="dc8af-131">Vergleichen des datenträgerbasierten Tabellenspeichers mit dem speicheroptimierten Tabellenspeicher</span><span class="sxs-lookup"><span data-stu-id="dc8af-131">Comparing Disk-Based Table Storage to Memory-Optimized Table Storage</span></span>](comparing-disk-based-table-storage-to-memory-optimized-table-storage.md)  
  
-   [<span data-ttu-id="dc8af-132">Überwachung und Problembehandlung beim Zusammenführen von Daten-/Änderungsdateipaaren</span><span class="sxs-lookup"><span data-stu-id="dc8af-132">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>](../../database-engine/monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc8af-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc8af-133">See Also</span></span>  
 [<span data-ttu-id="dc8af-134">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="dc8af-134">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
