---
title: Datenbankfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 04518abb-8581-47c8-a601-ee9136c3c0eb
author: rothja
ms.author: jroth
ms.openlocfilehash: 56b9f9ba9cc6e11ea82b822ae10b31710c8617b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619161"
---
# <a name="database-features"></a><span data-ttu-id="48f0f-102">Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="48f0f-102">Database Features</span></span>
  <span data-ttu-id="48f0f-103">Dieser Abschnitt enthält die Datenbanken zugeordneten Funktionen und Tasks, Datenbankobjekte, Datentypen und die Mechanismen zum Arbeiten mit oder Verwalten von Daten.</span><span class="sxs-lookup"><span data-stu-id="48f0f-103">This section contains the features and tasks associated with databases, database objects, data types, and the mechanisms used to work with or manage data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48f0f-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="48f0f-104">In This Section</span></span>  
  
|||
|--|--|
|[<span data-ttu-id="48f0f-105">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="48f0f-105">Databases</span></span>](databases/databases.md)|[<span data-ttu-id="48f0f-106">Sichern und Wiederherstellen von SQL Server-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="48f0f-106">Back Up and Restore of SQL Server Databases</span></span>](backup-restore/back-up-and-restore-of-sql-server-databases.md)|  
|[<span data-ttu-id="48f0f-107">Tabellen</span><span class="sxs-lookup"><span data-stu-id="48f0f-107">Tables</span></span>](tables/tables.md)|[<span data-ttu-id="48f0f-108">Sequenznummern</span><span class="sxs-lookup"><span data-stu-id="48f0f-108">Sequence Numbers</span></span>](sequence-numbers/sequence-numbers.md)|[<span data-ttu-id="48f0f-109">Massenimport und -export von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-109">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](import-export/bulk-import-and-export-of-data-sql-server.md)|  
|[<span data-ttu-id="48f0f-110">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-110">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp/in-memory-oltp-in-memory-optimization.md)|[<span data-ttu-id="48f0f-111">DDL-Trigger</span><span class="sxs-lookup"><span data-stu-id="48f0f-111">DDL Triggers</span></span>](triggers/ddl-triggers.md)|[<span data-ttu-id="48f0f-112">Datenkomprimierung</span><span class="sxs-lookup"><span data-stu-id="48f0f-112">Data Compression</span></span>](data-compression/data-compression.md)|  
|[<span data-ttu-id="48f0f-113">Indizes</span><span class="sxs-lookup"><span data-stu-id="48f0f-113">Indexes</span></span>](indexes/indexes.md)|[<span data-ttu-id="48f0f-114">DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="48f0f-114">DML Triggers</span></span>](triggers/dml-triggers.md)|[<span data-ttu-id="48f0f-115">OLE-Automatisierungsobjekte in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="48f0f-115">OLE Automation Objects in Transact-SQL</span></span>](stored-procedures/ole-automation-objects-in-transact-sql.md)|  
|[<span data-ttu-id="48f0f-116">Partitionierte Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="48f0f-116">Partitioned Tables and Indexes</span></span>](partitions/partitioned-tables-and-indexes.md)|[<span data-ttu-id="48f0f-117">Synonyme &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-117">Synonyms &#40;Database Engine&#41;</span></span>](synonyms/synonyms-database-engine.md)|[<span data-ttu-id="48f0f-118">Ereignis Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="48f0f-118">Event Notifications</span></span>](service-broker/event-notifications.md)|  
|[<span data-ttu-id="48f0f-119">Ansichten</span><span class="sxs-lookup"><span data-stu-id="48f0f-119">Views</span></span>](views/views.md)|[<span data-ttu-id="48f0f-120">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-120">XML Data &#40;SQL Server&#41;</span></span>](xml/xml-data-sql-server.md)|[<span data-ttu-id="48f0f-121">Überwachen und Optimieren der Leistung</span><span class="sxs-lookup"><span data-stu-id="48f0f-121">Monitor and Tune for Performance</span></span>](performance/monitor-and-tune-for-performance.md)|  
|[<span data-ttu-id="48f0f-122">Gespeicherte Prozeduren &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-122">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures/stored-procedures-database-engine.md)|[<span data-ttu-id="48f0f-123">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial/spatial-data-sql-server.md)||  
|[<span data-ttu-id="48f0f-124">&#40;SQL Server suchen&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-124">Search &#40;SQL Server&#41;</span></span>](../database-engine/search-sql-server.md)|[<span data-ttu-id="48f0f-125">Binary Large Object &#40;Blob&#41; Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-125">Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;</span></span>](blob/binary-large-object-blob-data-sql-server.md)||  
|[<span data-ttu-id="48f0f-126">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="48f0f-126">User-Defined Functions</span></span>](user-defined-functions/user-defined-functions.md)|[<span data-ttu-id="48f0f-127">Datenebenenanwendungen</span><span class="sxs-lookup"><span data-stu-id="48f0f-127">Data-tier Applications</span></span>](data-tier-applications/data-tier-applications.md)||  
|[<span data-ttu-id="48f0f-128">Statistik</span><span class="sxs-lookup"><span data-stu-id="48f0f-128">Statistics</span></span>](statistics/statistics.md)|[<span data-ttu-id="48f0f-129">Das Transaktionsprotokoll &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-129">The Transaction Log &#40;SQL Server&#41;</span></span>](logs/the-transaction-log-sql-server.md)||  
|[<span data-ttu-id="48f0f-130">Planhinweislisten</span><span class="sxs-lookup"><span data-stu-id="48f0f-130">Plan Guides</span></span>](performance/plan-guides.md)|[<span data-ttu-id="48f0f-131">Datenbankprüfpunkte &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48f0f-131">Database Checkpoints &#40;SQL Server&#41;</span></span>](logs/database-checkpoints-sql-server.md)||  
  
  
