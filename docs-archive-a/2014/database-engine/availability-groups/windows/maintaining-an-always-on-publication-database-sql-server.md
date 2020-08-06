---
title: Verwalten einer AlwaysOn-Veröffentlichungs Datenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 55b345fe-2eb9-4b04-a900-63d858eec360
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8f36d29049140b6e5bbdfc1a4e716d41a766a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617264"
---
# <a name="maintaining-an-alwayson-publication-database-sql-server"></a><span data-ttu-id="36349-102">Warten einer AlwaysOn-Veröffentlichungsdatenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="36349-102">Maintaining an AlwaysOn Publication Database (SQL Server)</span></span>
  <span data-ttu-id="36349-103">In diesem Thema werden besondere Überlegungen zum Verwalten einer Veröffentlichungsdatenbank bei Verwendung von AlwaysOn-Verfügbarkeitsgruppen erläutert.</span><span class="sxs-lookup"><span data-stu-id="36349-103">This topic discusses special considerations for maintaining a publication database when you use AlwaysOn availability groups.</span></span>  
  
 
  
##  <a name="maintaining-a-published-database-in-an-availability-group"></a><a name="MaintainPublDb"></a><span data-ttu-id="36349-104">Verwalten einer veröffentlichten Datenbank in einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="36349-104">Maintaining a Published Database in an Availability Group</span></span>  
 <span data-ttu-id="36349-105">Die Wartung einer AlwaysOn-Veröffentlichungsdatenbank entspricht im Wesentlichen der Wartung einer standardmäßigen Veröffentlichungsdatenbank, wobei jedoch die folgenden Überlegungen zu berücksichtigen sind:</span><span class="sxs-lookup"><span data-stu-id="36349-105">Maintaining an AlwaysOn publication database is basically the same as maintaining a standard publication database, with the following considerations:</span></span>  
  
-   <span data-ttu-id="36349-106">Die Verwaltung muss beim primären Replikathost erfolgen.</span><span class="sxs-lookup"><span data-stu-id="36349-106">Administration must occur at the primary replica host.</span></span> <span data-ttu-id="36349-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]werden Veröffentlichungen unter dem Ordner **Lokale Veröffentlichungen** für den primären Replikathost und auch für lesbare sekundäre Replikate angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36349-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], publications appear under the **Local Publications** folder for the primary replica host and also for readable secondary replicas.</span></span> <span data-ttu-id="36349-108">Nach einem Failover müssen Sie unter Umständen [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] manuell aktualisieren, um die Änderung widerzuspiegeln, wenn das sekundäre Replikat, das zum primären Replikat höher gestuft wurde, nicht lesbar war.</span><span class="sxs-lookup"><span data-stu-id="36349-108">After failover, you might have to manually refresh [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] for the change to be reflected if the secondary that was promoted to primary was not readable.</span></span>  
  
-   <span data-ttu-id="36349-109">Der Replikationsmonitor zeigt immer Veröffentlichungsinformationen unter dem ursprünglichen Verleger an.</span><span class="sxs-lookup"><span data-stu-id="36349-109">Replication Monitor always displays publication information under the original publisher.</span></span> <span data-ttu-id="36349-110">Diese Informationen können jedoch von einem beliebigen Replikat aus im Replikationsmonitor angezeigt werden, indem der ursprüngliche Verleger als Server hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="36349-110">However, this information can be viewed in Replication Monitor from any replica by adding the original publisher as a server.</span></span>  
  
-   <span data-ttu-id="36349-111">Bei Verwendung von gespeicherten Prozeduren oder Replikationsverwaltungsobjekten (RMO, Replication Management Objects) zum Verwalten der Replikation im primären Replikat müssen Sie in Fällen, in denen Sie den Verlegernamen angeben, den Namen der Instanz angeben, auf der die Datenbank für die Replikation aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="36349-111">When using stored procedures or Replication Management Objects (RMO) to administer replication at the current primary, for cases in which you specify the Publisher name, you must specify the name of the instance on which the database was enabled for replication (the original publisher).</span></span> <span data-ttu-id="36349-112">Den entsprechenden Namen ermitteln Sie mithilfe der `PUBLISHINGSERVERNAME`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="36349-112">To determine the appropriate name, use the `PUBLISHINGSERVERNAME` function.</span></span> <span data-ttu-id="36349-113">Wenn eine Veröffentlichungsdatenbank einer Verfügbarkeitsgruppe beitritt, sind die in den sekundären Datenbankreplikaten gespeicherten Replikationsmetadaten mit denen im primären Replikat identisch.</span><span class="sxs-lookup"><span data-stu-id="36349-113">When a publishing database joins an availability group, the replication metadata stored in the secondary database replicas is identical to that at the primary.</span></span> <span data-ttu-id="36349-114">Demzufolge entspricht für Veröffentlichungsdatenbanken, die in der primären Replikatdatenbank zur Replikation aktiviert wurden, der in den Systemtabellen des sekundären Replikats gespeicherte Verlegerinstanzname dem Namen der primären Replikatdatenbank und nicht dem Namen der sekundären Replikatdatenbank.</span><span class="sxs-lookup"><span data-stu-id="36349-114">Consequently, for publication databases enabled for replication at the primary, the publisher instance name stored in system tables at the secondary is the name of the primary, not the secondary.</span></span> <span data-ttu-id="36349-115">Dies wirkt sich auf die Replikationskonfiguration und -wartung aus, wenn ein Failover der Veröffentlichungsdatenbank zur sekundären Replikatdatenbank erfolgt.</span><span class="sxs-lookup"><span data-stu-id="36349-115">This affects replication configuration and maintenance if the publication database fails over to a secondary.</span></span> <span data-ttu-id="36349-116">Wenn Sie z. b. die Replikation mit gespeicherten Prozeduren auf einem sekundären Replikat nach einem Failover konfigurieren und ein Pullabonnement für eine Veröffentlichungs Datenbank verwenden möchten, die auf einem anderen Replikat aktiviert wurde, müssen Sie den Namen des ursprünglichen Verlegers anstelle des aktuellen Verlegers als- *@publisher* Parameter von `sp_addpullsubscription` oder angeben `sp_addmergepulllsubscription` .</span><span class="sxs-lookup"><span data-stu-id="36349-116">For example, if you are configuring replication with stored procedures at a secondary after failover, and you want a pull subscription to a publication database that was enabled at a different replica, you must specify the name of the original publisher instead of the current publisher as the *@publisher* parameter of `sp_addpullsubscription` or `sp_addmergepulllsubscription`.</span></span> <span data-ttu-id="36349-117">Wenn Sie jedoch eine Veröffentlichungsdatenbank nach einem Failover aktivieren, entspricht der in den Systemtabellen gespeicherte Verlegerinstanzname dem Namen des aktuellen primären Hosts.</span><span class="sxs-lookup"><span data-stu-id="36349-117">However, if you enable a publication database after failover, the publisher instance name stored in the system tables is the name of the current primary host.</span></span> <span data-ttu-id="36349-118">In diesem Fall verwenden Sie den Hostnamen des aktuellen primären Replikats für den- *@publisher* Parameter.</span><span class="sxs-lookup"><span data-stu-id="36349-118">In this case, you would use the host name of the current primary replica for the *@publisher* parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36349-119">Bei einigen Prozeduren, z `sp_addpublication` . b., wird der- *@publisher* Parameter nur für Verleger unterstützt, die keine Instanzen von sind [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . in diesen Fällen ist er für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="36349-119">For some procedures, such as `sp_addpublication`, the *@publisher* parameter is supported only for publishers that are not instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; in these cases, it is not relevant for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span></span>  
  
-   <span data-ttu-id="36349-120">Synchronisieren Sie die Pullabonnements vom Abonnenten und die Pushabonnements vom aktiven Verleger aus, um ein Abonnement in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] nach einem Failover zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="36349-120">To synchronize a subscription in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] after a failover, synchronize pull subscriptions from the subscriber and synchronize push subscriptions from the active publisher.</span></span>  
  
##  <a name="removing-a-published-database-from-an-availability-group"></a><a name="RemovePublDb"></a> <span data-ttu-id="36349-121">Entfernen einer veröffentlichten Datenbank aus einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="36349-121">Removing a Published Database from an Availability Group</span></span>  
 <span data-ttu-id="36349-122">Berücksichtigen Sie die folgenden Probleme, wenn eine veröffentlichte Datenbank aus einer Verfügbarkeitsgruppe entfernt wird, oder wenn eine Verfügbarkeitsgruppe, die eine veröffentlichte Elementdatenbank aufweist, gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="36349-122">Consider the following issues if a published database is removed from an availability group, or if an availability group that has a published member database is dropped.</span></span>  
  
-   <span data-ttu-id="36349-123">Wenn die Veröffentlichungs Datenbank beim ursprünglichen Verleger aus einem primären Replikat der Verfügbarkeits Gruppe entfernt wird, müssen Sie ausführen, `sp_redirect_publisher` ohne einen Wert für den-Parameter anzugeben, um *@redirected_publisher* die Umleitung für das Verleger-/Datenbankpaar zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="36349-123">If the publication database at the original publisher is removed from an availability group primary replica, you must run `sp_redirect_publisher` without specifying a value for the *@redirected_publisher* parameter in order to remove the redirection for the publisher/database pair.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB';  
    ```  
  
     <span data-ttu-id="36349-124">Die Datenbank wird auf dem primären Replikat im Wiederherstellungsstatus belassen und muss wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="36349-124">The database will be left in the recovering state at the primary and must be restored.</span></span> <span data-ttu-id="36349-125">Sobald Sie dies tun, sollte die Replikation unverändert mit dem ursprünglichen Verleger funktionieren.</span><span class="sxs-lookup"><span data-stu-id="36349-125">Once you do this, replication should work unchanged against the original Publisher.</span></span>  
  
-   <span data-ttu-id="36349-126">Wenn für die Veröffentlichungsdatenbank ein Failover vom ursprünglichen Verleger zu einem Replikat ausgeführt und die Datenbank aus dem primären Replikat der Verfügbarkeitsgruppe entfernt wird, führen Sie die gespeicherte Prozedur `sp_redirect_publisher` aus, um den ursprünglichen Verleger zum neuen Verleger umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="36349-126">If the publication database fails over from the original publisher to a replica and the database is removed from the availability group primary replica, use the stored procedure `sp_redirect_publisher` to explicitly redirect the original publisher to the new publisher.</span></span> <span data-ttu-id="36349-127">Die Datenbank wird im Wiederherstellungsstatus belassen und muss wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="36349-127">The database will be left in the recovering state and must be restored.</span></span> <span data-ttu-id="36349-128">Sobald Sie dies tun, sollte die Replikation weiterhin so funktionieren wie zuvor in der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="36349-128">Once you do this, replication should continue to work as it did under the availability group.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB',  
        @redirected_publisher = 'MyNewPublisher';  
    ```  
  
     <span data-ttu-id="36349-129">Entfernen Sie den Remoteserver für den ursprünglichen Verleger selbst dann nicht aus dem Verteiler, wenn nicht mehr auf den Server zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="36349-129">Do not remove the remote server for the original publisher from the distributor, even if the server can no longer be accessed.</span></span> <span data-ttu-id="36349-130">Die Servermetadaten für den ursprünglichen Verleger werden beim Verteiler benötigt, um Abfragen von Veröffentlichungsmetadaten beantworten zu können</span><span class="sxs-lookup"><span data-stu-id="36349-130">The server metadata for the original publisher is needed at the distributor to satisfy publication metadata queries.</span></span>  
  
-   <span data-ttu-id="36349-131">Wenn eine vollständige Verfügbarkeitsgruppe entfernt wird, wirkt sich dies auf eine replizierte Mitgliedsdatenbank auf die gleiche Weise aus, wie das Entfernen einer veröffentlichten Datenbank aus einer Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="36349-131">If a complete availability group is removed, the behavior with regard to a member replicated database is the same as when a published database is removed from an availability group.</span></span> <span data-ttu-id="36349-132">Die Replikation kann vom letzten primären Replikat fortgesetzt werden, sobald die Datenbank wiederhergestellt und die Umleitung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="36349-132">Replication can be resumed from the last primary as soon as the database has been restored and the redirection has been modified.</span></span> <span data-ttu-id="36349-133">Wenn die Datenbank auf ihrem ursprünglichen Verleger wiederhergestellt wird, sollte die Umleitung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="36349-133">If the database is restored at its original publisher, redirection should be removed.</span></span> <span data-ttu-id="36349-134">Wenn die Datenbank bei einem anderen Host wiederhergestellt wird, sollte Umleitung explizit an den neuen Host umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="36349-134">If the database is restored at a different host, redirection should be explicitly directed to the new host.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36349-135">Wenn eine Verfügbarkeitsgruppe entfernt wird, die über veröffentlichte Mitgliedsdatenbanken verfügt, oder wenn eine veröffentlichte Datenbank aus einer Verfügbarkeitsgruppe entfernt wird, werden alle Kopien der veröffentlichten Datenbanken im Wiederherstellungsstatus belassen.</span><span class="sxs-lookup"><span data-stu-id="36349-135">When an availability group is removed that has published member databases, or a published database is removed from an availability group, all copies of the published databases will be left in the recovering state.</span></span> <span data-ttu-id="36349-136">Nach der Wiederherstellung wird jede Datenbank als veröffentlichte Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36349-136">If restored, each will appear as a published database.</span></span> <span data-ttu-id="36349-137">Nur eine Kopie sollte mit Veröffentlichungsmetadaten beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="36349-137">Only one copy should be retained with publication metadata.</span></span> <span data-ttu-id="36349-138">Um die Replikation für eine veröffentlichte Datenbankkopie zu deaktivieren, entfernen Sie zuerst alle Abonnements und Veröffentlichungen aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="36349-138">To disable replication for a published database copy, first remove all subscriptions and publications from the database.</span></span>  
  
     <span data-ttu-id="36349-139">Führen Sie `sp_dropsubscription` aus, um die Veröffentlichungsabonnements zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="36349-139">Run `sp_dropsubscription` to remove publication subscriptions.</span></span> <span data-ttu-id="36349-140">Stellen Sie sicher, dass der-Parameter auf 1 festgelegt ist *@ignore_distributributor* , um die Metadaten für die aktive Veröffentlichungs Datenbank auf dem Verteiler beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="36349-140">Make sure to set the parameter *@ignore_distributributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    USE MyDBName;  
    GO  
  
    EXEC sys.sp_dropsubscription   
        @subscriber = 'MySubscriber',  
        @publication = 'MyPublication',  
        @article = 'all',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="36349-141">Führen Sie `sp_droppublication` aus, um alle Veröffentlichungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="36349-141">Run `sp_droppublication` to remove all publications.</span></span> <span data-ttu-id="36349-142">Legen Sie den-Parameter *@ignore_distributor* auf 1 fest, um die Metadaten für die aktive Veröffentlichungs Datenbank auf dem Verteiler beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="36349-142">Again, set the parameter *@ignore_distributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    EXEC sys.sp_droppublication   
        @publication = 'MyPublication',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="36349-143">Führen Sie `sp_replicationdboption` aus, um die Replikation für die Datenbank zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="36349-143">Run `sp_replicationdboption` to disable replication for the database.</span></span>  
  
    ```  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'false';  
    ```  
  
     <span data-ttu-id="36349-144">An diesem Punkt kann die Kopie der veröffentlichten Datenbank beibehalten oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="36349-144">At this point, the copy of the published database can be retained or dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="36349-145">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="36349-145">Related Tasks</span></span>  
  
-   [<span data-ttu-id="36349-146">Konfigurieren der Replikation für AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="36349-146">Configure Replication for AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="36349-147">Replikation, Änderungsnachverfolgung, Change Data Capture und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36349-147">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="36349-148">Häufig gestellte Fragen für Replikationsadministratoren</span><span class="sxs-lookup"><span data-stu-id="36349-148">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
-   [<span data-ttu-id="36349-149">Replikations Abonnenten und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36349-149">Replication Subscribers and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="36349-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36349-150">See Also</span></span>  
 <span data-ttu-id="36349-151">[Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="36349-151">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="36349-152">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="36349-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="36349-153">[AlwaysOn-Verfügbarkeitsgruppen: Interoperabilität (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="36349-153">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="36349-154">SQL Server-Replikation</span><span class="sxs-lookup"><span data-stu-id="36349-154">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
  
  
