---
title: Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei (AlwaysOn-Verfügbarkeitsgruppen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary databases [SQL Server], Availability Groups
- Availability Groups [SQL Server], troubleshooting
ms.assetid: 31ceaebf-864b-4dd0-9112-0d047b0316ad
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2551080c214f18473caa71a3e17797c34fcc943a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724950"
---
# <a name="troubleshoot-a-failed-add-file-operation-alwayson-availability-groups"></a><span data-ttu-id="6dbe8-102">Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei (AlwaysOn-Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="6dbe8-102">Troubleshoot a Failed Add-File Operation (AlwaysOn Availability Groups)</span></span>
  <span data-ttu-id="6dbe8-103">In einigen Bereitstellungen von AlwaysOn-Verfügbarkeitsgruppen unterscheiden sich Dateipfade zwischen dem System, das das primäre Replikat hostet, und Systemen, die ein sekundäres Replikat hosten.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-103">In some AlwaysOn availability group deployments, file paths differ between the system that hosts the primary replica and systems that host a secondary replica.</span></span> <span data-ttu-id="6dbe8-104">Wenn der Dateipfad eines Vorgangs zum Hinzufügen einer Datei auf einem sekundären Replikat nicht vorhanden ist, dann ist dieser Vorgang auf der primären Datenbank erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-104">If the file path of an add-file operation does not exist on a secondary replica, the add-file operation will succeed on the primary database.</span></span> <span data-ttu-id="6dbe8-105">Der Vorgang zum Hinzufügen einer Datei bewirkt jedoch, dass die sekundäre Datenbank angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-105">But the add-file operation will cause the secondary database to be suspended.</span></span> <span data-ttu-id="6dbe8-106">Dies bewirkt dann, dass das sekundäre Replikat den Status NOT SYNCHRONIZING erhält.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-106">This, in turn, causes the secondary replica to enter the NOT SYNCHRONIZING state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6dbe8-107">Außerdem sollte der Dateipfad (einschließlich des Laufwerkbuchstabens) einer sekundären Datenbank nach Möglichkeit mit dem Pfad der entsprechenden primären Datenbank übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-107">We recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span>  
  
## <a name="problem-resolution"></a><span data-ttu-id="6dbe8-108">Problemlösung</span><span class="sxs-lookup"><span data-stu-id="6dbe8-108">Problem Resolution</span></span>  
 <span data-ttu-id="6dbe8-109">Um dieses Problem zu beheben, muss der Datenbankbesitzer die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6dbe8-109">To resolve this problem the database owner must complete the following steps:</span></span>  
  
1.  <span data-ttu-id="6dbe8-110">Entfernen Sie die sekundäre Datenbank aus der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-110">Remove the secondary database from the availability group.</span></span> <span data-ttu-id="6dbe8-111">Weitere Informationen finden Sie unter [Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6dbe8-111">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="6dbe8-112">Stellen Sie in der vorhandenen sekundären Datenbank eine vollständige Sicherung der Dateigruppe wieder her, die die zur sekundären Datenbank hinzugefügte Datei enthält. Verwenden Sie hierzu WITH NORECOVERY und WITH MOVE (geben Sie den Dateipfad auf der Serverinstanz an, die das sekundäre Replikat hostet).</span><span class="sxs-lookup"><span data-stu-id="6dbe8-112">On the existing secondary database, restore a full backup of the filegroup that contains the added file to the secondary database, using WITH NORECOVERY and WITH MOVE (specifying the file path on the server instance that hosts the secondary replica).</span></span> <span data-ttu-id="6dbe8-113">Weitere Informationen finden Sie unter [Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6dbe8-113">For more information, see [Restore a Database to a New Location &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="6dbe8-114">Sichern Sie das Transaktionsprotokoll, das den Vorgang zum Hinzufügen der Datei auf der primären Datenbank enthält, und stellen Sie die Protokollsicherung auf der sekundären Datenbank manuell mit WITH NORECOVERY und WITH MOVE wieder her.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-114">Back up the transaction log that contains the add-file operation on the primary database, and manually restore the log backup on the secondary database using WITH NORECOVERY and WITH MOVE.</span></span>  
  
4.  <span data-ttu-id="6dbe8-115">Bereiten Sie die sekundäre Datenbank auf das erneute Hinzufügen zur Verfügbarkeitsgruppe vor, indem Sie mit WITH NO RECOVERY alle sonstigen ausstehenden Protokollsicherungen von der primären Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-115">Prepare the secondary database for re-joining the availability group, by restoring, WITH NO RECOVERY, any other outstanding log backups from the primary database.</span></span>  
  
5.  <span data-ttu-id="6dbe8-116">Fügen Sie die sekundäre Datenbank wieder zur Verfügbarkeitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-116">Rejoin the secondary database to the availability group.</span></span> <span data-ttu-id="6dbe8-117">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6dbe8-117">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbe8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6dbe8-118">See Also</span></span>  
 <span data-ttu-id="6dbe8-119">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6dbe8-119">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6dbe8-120">[Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6dbe8-120">[Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="6dbe8-121">[Problembehandlung bei verwaisten Benutzern &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6dbe8-121">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 [<span data-ttu-id="6dbe8-122">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfigurations &#40;SQL Server&#41;gelöscht</span><span class="sxs-lookup"><span data-stu-id="6dbe8-122">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
  
