---
title: Starten der Daten Verschiebung auf einer sekundären AlwaysOn-Datenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], databases
ms.assetid: 498eb3fb-6a43-434d-ad95-68a754232c45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ce4f80b456244cd6e024377383abe75e002057a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724970"
---
# <a name="start-data-movement-on-an-alwayson-secondary-database-sql-server"></a><span data-ttu-id="5fed9-102">Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5fed9-102">Start Data Movement on an AlwaysOn Secondary Database (SQL Server)</span></span>
  <span data-ttu-id="5fed9-103">Dieses Thema enthält Informationen zum Starten der Datensynchronisierung, nachdem Sie einer AlwaysOn-Verfügbarkeitsgruppe eine Datenbank hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="5fed9-103">This topic contains information about how to start data synchronization after you add a database to an AlwaysOn availability group.</span></span> <span data-ttu-id="5fed9-104">Für jedes neue primäre Replikat müssen sekundäre Datenbanken auf den Serverinstanzen vorbereitet werden, die die sekundären Replikate hosten.</span><span class="sxs-lookup"><span data-stu-id="5fed9-104">For each new primary replica, secondary databases must be prepared on the server instances that host the secondary replicas.</span></span> <span data-ttu-id="5fed9-105">Dann muss jede dieser sekundären Datenbanken manuell mit der Verfügbarkeitsgruppe verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="5fed9-105">Then each of these secondary databases must be manually joined to the availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5fed9-106">Wenn die Dateipfade auf jeder Serverinstanz, die ein Verfügbarkeitsreplikat für eine Verfügbarkeitsgruppe hostet, identisch sind, kann der [Assistent für neue Verfügbarkeitsgruppen](use-the-availability-group-wizard-sql-server-management-studio.md), der [Assistent zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)oder der [Assistent zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen](availability-group-add-database-to-group-wizard.md) unter Umständen die Datensynchronisierung automatisch starten.</span><span class="sxs-lookup"><span data-stu-id="5fed9-106">If the file paths are identical on every server instance that hosts an availability replica for an availability group, the [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md) might be able to automatically start data synchronization for you.</span></span>  
  
 <span data-ttu-id="5fed9-107">Um die Datensynchronisierung manuell zu starten, müssen Sie wiederum eine Verbindung mit jeder Serverinstanz herstellen, die ein sekundäres Replikat für die Verfügbarkeitsgruppe hostet, und die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="5fed9-107">To start data synchronization manually, you need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
1.  <span data-ttu-id="5fed9-108">Stellen Sie aktuelle Sicherungen jeder primären Datenbank und ihres Transaktionsprotokolls (mithilfe von RESTORE WITH NORECOVERY) wieder her.</span><span class="sxs-lookup"><span data-stu-id="5fed9-108">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="5fed9-109">Sie können einen der folgenden alternativen Ansätze verwenden:</span><span class="sxs-lookup"><span data-stu-id="5fed9-109">You can use either of the following alternative approaches:</span></span>  
  
    -   <span data-ttu-id="5fed9-110">Stellen Sie manuell mit RESTORE WITH NORECOVERY eine aktuelle Datenbanksicherung der primären Datenbank wieder her, und stellen Sie dann jede nachfolgende Protokollsicherung mit RESTORE WITH NORECOVERY wieder her.</span><span class="sxs-lookup"><span data-stu-id="5fed9-110">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="5fed9-111">Führen Sie diese Wiederherstellungssequenz auf jeder Serverinstanz aus, die ein sekundäres Replikat für die Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="5fed9-111">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  
  
         <span data-ttu-id="5fed9-112">**Weitere Informationen finden Sie unter:**</span><span class="sxs-lookup"><span data-stu-id="5fed9-112">**For more information:**</span></span>  
  
         [<span data-ttu-id="5fed9-113">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-113">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
    -   <span data-ttu-id="5fed9-114">Wenn Sie einer Verfügbarkeitsgruppe eine oder mehrere primäre Datenbanken für den Protokollversand hinzufügen, können Sie möglicherweise eine oder mehrere der entsprechenden sekundären Datenbanken für den Protokollversand zu AlwaysOn-Verfügbarkeitsgruppen migrieren.</span><span class="sxs-lookup"><span data-stu-id="5fed9-114">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to AlwaysOn Availability Groups.</span></span> <span data-ttu-id="5fed9-115">Das Migrieren einer sekundären Datenbank für den Protokollversand erfordert, dass sie den gleichen Datenbanknamen wie die primäre Datenbank verwendet und dass sie sich auf einer Serverinstanz befindet, die ein sekundäres Replikat für die Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="5fed9-115">Migrating a log shipping secondary database requires that it use the same database name as the primary database and that it reside on a server instance that is hosting a secondary replica for the availability group.</span></span> <span data-ttu-id="5fed9-116">Weiterhin muss die Verfügbarkeitsgruppe so konfiguriert sein, dass das primäre Replikat für Sicherungen bevorzugt wird und ein Kandidat zum Ausführen von Sicherungen ist (das heißt, eine Sicherungspriorität, die >0 hat).</span><span class="sxs-lookup"><span data-stu-id="5fed9-116">Furthermore, the availability group must be configured so that the primary replica is preferred for backups and is a candidate for performing backups (that is, that has a backup priority that is >0).</span></span> <span data-ttu-id="5fed9-117">Nachdem der Sicherungsauftrag auf der primären Datenbank ausgeführt wurde, müssen Sie den Sicherungsauftrag deaktivieren, und sobald der Wiederherstellungsauftrag auf einer angegebenen sekundären Datenbank ausgeführt wurde, müssen Sie den Wiederherstellungsauftrag deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5fed9-117">Once the backup job has run on the primary database, you will need to disable the backup job, and once the restore job has run on a given secondary database, you will need to disable the restore job.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5fed9-118">Nachdem Sie alle sekundären Datenbanken für die Verfügbarkeitsgruppe erstellt haben, sofern Sie Sicherungen auf sekundären Replikaten ausführen möchten, müssen Sie die Voreinstellung zur automatisierten Sicherung der Verfügbarkeitsgruppe neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5fed9-118">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
         <span data-ttu-id="5fed9-119">**Weitere Informationen finden Sie unter:**</span><span class="sxs-lookup"><span data-stu-id="5fed9-119">**For more information:**</span></span>  
  
         [<span data-ttu-id="5fed9-120">Voraussetzungen für das Migrieren vom Protokoll Versand zu AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-120">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
         [<span data-ttu-id="5fed9-121">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-121">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
2.  <span data-ttu-id="5fed9-122">Verknüpfen Sie jede neu vorbereitete sekundäre Datenbank sofort mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="5fed9-122">As soon as possible, join each newly prepared secondary database to the availability group.</span></span>  
  
     <span data-ttu-id="5fed9-123">**Weitere Informationen finden Sie unter:**</span><span class="sxs-lookup"><span data-stu-id="5fed9-123">**For more information:**</span></span>  
  
     [<span data-ttu-id="5fed9-124">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-124">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="5fed9-125">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="5fed9-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5fed9-126">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-126">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="5fed9-127">Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-127">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="5fed9-128">Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-128">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="5fed9-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5fed9-129">See Also</span></span>  
 [<span data-ttu-id="5fed9-130">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fed9-130">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
