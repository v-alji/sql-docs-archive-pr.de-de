---
title: Datenbankspiegelung und Datenbankmomentaufnahmen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- snapshots [SQL Server database snapshots], database mirroring
- database snapshots [SQL Server], database mirroring
ms.assetid: 0bf1be90-7ce4-484c-aaa7-f8a782f57c5f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9df0b74270280bf2315c6a35a80d4b009b75a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615573"
---
# <a name="database-mirroring-and-database-snapshots-sql-server"></a><span data-ttu-id="b6920-102">Datenbankspiegelung und Datenbankmomentaufnahmen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b6920-102">Database Mirroring and Database Snapshots (SQL Server)</span></span>
  <span data-ttu-id="b6920-103">Sie können die Vorteile einer Spiegeldatenbank, die aus Gründen der Verfügbarkeit verwaltet wird, auch für die ausgelagerte Berichterstellung ausnutzen.</span><span class="sxs-lookup"><span data-stu-id="b6920-103">You can take advantage of a mirror database that you are maintaining for availability purposes to offload reporting.</span></span> <span data-ttu-id="b6920-104">Wenn Sie für die Berichterstellung eine Spiegeldatenbank verwenden möchten, können Sie eine Datenbankmomentaufnahme für die Spiegeldatenbank erstellen und die Clientverbindungsanforderungen an die zuletzt erstellte Momentaufnahme weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b6920-104">To use a mirror database for reporting, you can create a database snapshot on the mirror database and direct client connection requests to the most recent snapshot.</span></span> <span data-ttu-id="b6920-105">Eine Datenbankmomentaufnahme ist eine statische, schreibgeschützte, hinsichtlich der Transaktionen konsistente Momentaufnahme des Zustands einer Quelldatenbank, in dem sich diese zum Zeitpunkt der Erstellung der Momentaufnahme befand.</span><span class="sxs-lookup"><span data-stu-id="b6920-105">A database snapshot is a static, read-only, transaction-consistent snapshot of its source database as it existed at the moment of the snapshot's creation.</span></span> <span data-ttu-id="b6920-106">Zum Erstellen einer Datenbankmomentaufnahme für die Spiegeldatenbank muss sich die Datenbank im synchronisierten Spiegelungsstatus befinden.</span><span class="sxs-lookup"><span data-stu-id="b6920-106">To create a database snapshot on a mirror database, the database must be in the synchronized mirroring state.</span></span>  
  
 <span data-ttu-id="b6920-107">Im Gegensatz zur eigentlichen Spiegeldatenbank ist eine Datenbankmomentaufnahme auch für Clients zugreifbar.</span><span class="sxs-lookup"><span data-stu-id="b6920-107">Unlike the mirror database itself, a database snapshot is accessible to clients.</span></span> <span data-ttu-id="b6920-108">Solange der Spiegelserver mit dem Prinzipalserver kommuniziert, können Sie Berichtsclients an eine Verbindung mit einer Momentaufnahme weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b6920-108">As long as the mirror server is communicating with the principal server, you can direct reporting clients to connect to a snapshot.</span></span> <span data-ttu-id="b6920-109">Da Datenbankmomentaufnahmen statisch sind, sind neue Daten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b6920-109">Note that because a database snapshot is static, new data is not available.</span></span> <span data-ttu-id="b6920-110">Sie müssen in regelmäßigen Abständen eine neue Datenbankmomentaufnahme erstellen und sicherstellen, dass Anwendungen eingehende Clientverbindungen an die neueste Momentaufnahme weiterleiten, um den Benutzern relativ neue Daten zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="b6920-110">To make relatively recent data available to your users, you must create a new database snapshot periodically and have applications direct incoming client connections to the newest snapshot.</span></span>  
  
 <span data-ttu-id="b6920-111">Eine neue Datenbankmomentaufnahme ist fast leer. Er nimmt jedoch im Laufe der Zeit an Größe zu, wenn immer mehr Datenbankseiten zum ersten Mal aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b6920-111">A new database snapshot is almost empty, but it grows over time as more and more database pages are updated for the first time.</span></span> <span data-ttu-id="b6920-112">Da jede Momentaufnahme für eine Datenbank auf diese Weise schrittweise größer wird, verbraucht jede einzelne Datenbankmomentaufnahme genauso viele Ressourcen wie eine normale Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b6920-112">Because every snapshot on a database grows incrementally in this way, each database snapshot consumes as much resources as a normal database.</span></span> <span data-ttu-id="b6920-113">Abhängig von der Konfiguration des Spiegelservers und des Prinzipalservers kann sich bei Vorhandensein einer übermäßig hohen Anzahl von Datenbankmomentaufnahmen auf einer Spiegeldatenbank die Leistung der Prinzipaldatenbank verringern.</span><span class="sxs-lookup"><span data-stu-id="b6920-113">Depending on the configurations of the mirror server and principal server, having an excessive number of database snapshots on a mirror database might decrease performance on the principal database.</span></span> <span data-ttu-id="b6920-114">Sie sollten daher nur einige wenige, relativ neue Momentaufnahmen auf den Spiegeldatenbanken behalten.</span><span class="sxs-lookup"><span data-stu-id="b6920-114">Therefore, we recommend that you keep only a few relatively recent snapshots on your mirror databases.</span></span> <span data-ttu-id="b6920-115">Nachdem Sie eine Ersatzmomentaufnahme erstellt haben, sollten Sie eingehende Abfragen an die neue Momentaufnahme weiterleiten und die frühere Momentaufnahme löschen, sobald alle aktuellen Abfragen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="b6920-115">Typically, after you create a replacement snapshot, you should redirect incoming queries to the new snapshot and drop the earlier snapshot after any current queries complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6920-116">Weitere Informationen zu Datenbankmomentaufnahmen finden Sie unter [Datenbank-Momentaufnahmen &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b6920-116">For more information about database snapshots, see [Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span></span>  
  
 <span data-ttu-id="b6920-117">Wenn ein Rollenwechsel stattfindet, werden die Datenbank und die zugehörigen Momentaufnahmen neu gestartet, wobei die Verbindung mit den Benutzern vorübergehend getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="b6920-117">If role switching occurs, the database and its snapshots are restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="b6920-118">Anschließend verbleiben die Datenbankmomentaufnahmen auf der Serverinstanz, auf der sie erstellt wurden und die zur neuen Prinzipaldatenbank geworden ist.</span><span class="sxs-lookup"><span data-stu-id="b6920-118">Afterwards, the database snapshots remain on the server instance where they were created, which has become the new principal database.</span></span> <span data-ttu-id="b6920-119">Die Momentaufnahmen können nach dem Failover weiter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6920-119">Users can continue to use the snapshots after the failover.</span></span> <span data-ttu-id="b6920-120">Dies bedeutet für den neuen Prinzipalserver jedoch eine zusätzliche Belastung.</span><span class="sxs-lookup"><span data-stu-id="b6920-120">However, this places an additional load on the new principal server.</span></span> <span data-ttu-id="b6920-121">Falls in Ihrer Umgebung die Leistung eine wichtige Überlegung ist, sollten Sie auf der neuen Spiegeldatenbank eine Momentaufnahme erstellen, sobald diese verfügbar ist, die Clients zu der neuen Momentaufnahme umleiten und alle Datenbankmomentaufnahmen aus der früheren Spiegeldatenbank löschen.</span><span class="sxs-lookup"><span data-stu-id="b6920-121">If performance is a concern in your environment, we recommend that you create a snapshot on the new mirror database when it becomes available, redirect clients to the new snapshot, and drop all of the database snapshots from the former mirror database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6920-122">Wenn Sie eine dedizierte, gut skalierte Berichterstellung bevorzugen, sollten Sie eine Replikation in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="b6920-122">For a dedicated reporting solution that scales out well, consider replication.</span></span> <span data-ttu-id="b6920-123">Weitere Informationen finden Sie unter [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b6920-123">For more information, see [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6920-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6920-124">Example</span></span>  
 <span data-ttu-id="b6920-125">In diesem Beispiel werden Momentaufnahmen für eine gespiegelte Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="b6920-125">This example creates snapshots on a mirrored database.</span></span>  
  
 <span data-ttu-id="b6920-126">Angenommen, die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Datenbank wird in einer Datenbank-Spiegelungssitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6920-126">Assume that the database of a database mirroring session is [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="b6920-127">In diesem Beispiel werden drei Datenbankmomentaufnahmen für die Spiegelkopie der `AdventureWorks` -Datenbank erstellt, die sich auf Laufwerk `F` befindet.</span><span class="sxs-lookup"><span data-stu-id="b6920-127">This example creates three database snapshots on the mirror copy of the `AdventureWorks` database, which resides on the `F` drive.</span></span> <span data-ttu-id="b6920-128">Die Momentaufnahmen werden mit `AdventureWorks_0600`, `AdventureWorks_1200`und `AdventureWorks_1800` bezeichnet, um den ungefähren Zeitpunkt ihrer Erstellung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b6920-128">The snapshots are named `AdventureWorks_0600`, `AdventureWorks_1200`, and `AdventureWorks_1800` to identify their approximate creation times.</span></span>  
  
1.  <span data-ttu-id="b6920-129">Erstellen Sie die erste Datenbankmomentaufnahm für den Spiegel von [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6920-129">Create the first database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_0600  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_0600.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
2.  <span data-ttu-id="b6920-130">Erstellen Sie die zweite Datenbankmomentaufnahme für den Spiegel von [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6920-130">Create the second database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="b6920-131">Benutzer, die noch immer `AdventureWorks_0600` verwenden, können diese auch weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6920-131">Users who are still using `AdventureWorks_0600` can continue to use it.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1200  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1200.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="b6920-132">Die neuen Clientverbindungen können nun programmgesteuert an die zuletzt erstellte Momentaufnahme weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b6920-132">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
3.  <span data-ttu-id="b6920-133">Erstellen Sie die dritte Momentaufnahme für den Spiegel von [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6920-133">Create the third snapshot on the mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="b6920-134">Benutzer, die immer noch `AdventureWorks_0600` oder `AdventureWorks_1200` verwenden, können diese auch weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6920-134">Users who are still using `AdventureWorks_0600` or `AdventureWorks_1200` can continue to use them.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1800  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1800.SNP')  
        AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="b6920-135">Die neuen Clientverbindungen können nun programmgesteuert an die zuletzt erstellte Momentaufnahme weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b6920-135">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b6920-136">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b6920-136">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b6920-137">Erstellen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b6920-137">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="b6920-138">Anzeigen einer Datenbank-Momentaufnahme &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b6920-138">View a Database Snapshot &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="b6920-139">Löschen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b6920-139">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  

  
## <a name="see-also"></a><span data-ttu-id="b6920-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6920-140">See Also</span></span>  
 <span data-ttu-id="b6920-141">[Datenbank-Momentaufnahmen &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b6920-141">[Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span></span>  
 [<span data-ttu-id="b6920-142">Verbinden von Clients mit einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b6920-142">Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;</span></span>](connect-clients-to-a-database-mirroring-session-sql-server.md)  
  
  
