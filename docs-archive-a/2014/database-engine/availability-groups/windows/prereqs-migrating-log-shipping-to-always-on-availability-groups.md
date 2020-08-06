---
title: Voraussetzungen für das Migrieren vom Protokoll Versand zu AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 2738ce65-205e-4682-92d8-dc7e37c58b2b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 76b50d5af8eb520b3764ff56397c040f2d0d0141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718727"
---
# <a name="prerequisites-for-migrating-from-log-shipping-to-alwayson-availability-groups-sql-server"></a><span data-ttu-id="1960a-102">Voraussetzungen für das Migrieren vom Protokollversand zu AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1960a-102">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="1960a-103">In diesem Thema werden die erforderlichen Komponenten zum Konvertieren einer primären Datenbank für den Protokollversand zusammen mit einer oder mehreren sekundären Datenbanken in eine primäre AlwaysOn-Datenbank und sekundäre Datenbank(en) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1960a-103">This topic describes the prerequisites for converting a log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and secondary database(s).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1960a-104">Sie können jede primäre oder sekundäre (ggf. lesbare) Datenbank in einer Verfügbarkeitsgruppe als primäre Datenbank für den Protokollversand konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1960a-104">You can configure any primary or secondary database (possibly readable) in an availability group as a log shipping primary database.</span></span>  
  
 <span data-ttu-id="1960a-105">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="1960a-105">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="1960a-106">Erforderliche Komponenten für Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="1960a-106">Availability Group Prerequisites</span></span>](#AGPrereqsRealAddress)  
  
-   [<span data-ttu-id="1960a-107">Erforderliche Komponenten für den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="1960a-107">Log Shipping Prerequisites</span></span>](#LogShipPrereqs)  
  
-   [<span data-ttu-id="1960a-108">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1960a-108">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="1960a-109">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1960a-109">Related Content</span></span>](#RelatedContent)  
  
##  <a name="availability-group-prerequisites"></a><a name="AGPrereqsRealAddress"></a><span data-ttu-id="1960a-110">Verfügbarkeits Gruppen Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1960a-110">Availability Group Prerequisites</span></span>  
 <span data-ttu-id="1960a-111">Damit Sicherungsaufträge auf dem primären Replikat der Verfügbarkeitsgruppe ausgeführt werden können, verwenden Sie die folgenden Sicherungseinstellungen für AlwaysOn-Verfügbarkeitsgruppen:</span><span class="sxs-lookup"><span data-stu-id="1960a-111">To allow backup jobs to run on the primary replica of the availability group, use the following AlwaysOn Availability Groups backup settings:</span></span>  
  
|<span data-ttu-id="1960a-112">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1960a-112">Property</span></span>|<span data-ttu-id="1960a-113">Einstellung</span><span class="sxs-lookup"><span data-stu-id="1960a-113">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="1960a-114">Die Voreinstellung für die automatisierte Sicherung der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1960a-114">Automated backup preference of availability group</span></span>|<span data-ttu-id="1960a-115">Nur auf dem primären Replikat</span><span class="sxs-lookup"><span data-stu-id="1960a-115">Only on the primary replica</span></span>|  
|<span data-ttu-id="1960a-116">Sicherungspriorität des primären Replikats.</span><span class="sxs-lookup"><span data-stu-id="1960a-116">Backup priority of the primary replica.</span></span>|<span data-ttu-id="1960a-117">>0</span><span class="sxs-lookup"><span data-stu-id="1960a-117">>0</span></span>|  
  
 <span data-ttu-id="1960a-118">**Weitere Informationen finden Sie unter:**</span><span class="sxs-lookup"><span data-stu-id="1960a-118">**For more information:**</span></span>  
  
 [<span data-ttu-id="1960a-119">Anzeigen von Verfügbarkeitsgruppeneigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-119">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
 [<span data-ttu-id="1960a-120">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-120">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="log-shipping-prerequisites"></a><a name="LogShipPrereqs"></a><span data-ttu-id="1960a-121">Anforderungen an den Protokoll Versand</span><span class="sxs-lookup"><span data-stu-id="1960a-121">Log Shipping Prerequisites</span></span>  
  
-   <span data-ttu-id="1960a-122">Die primäre Datenbank für den Protokollversand muss sich auf der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] befinden, auf der das anfängliche/aktuelle primäre Replikat der Verfügbarkeitsgruppe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1960a-122">The log shipping primary database must reside on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the initial/current primary replica of the availability group.</span></span>  
  
-   <span data-ttu-id="1960a-123">Damit eine angegebene sekundäre Datenbank für den Protokollversand in eine sekundäre AlwaysOn-Datenbank konvertiert werden kann, muss Folgendes erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="1960a-123">For a given log shipping secondary database to be converted to an AlwaysOn secondary database, it must:</span></span>  
  
    -   <span data-ttu-id="1960a-124">Sie muss den gleichen Namen wie die primäre Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="1960a-124">Use the same name as the primary database.</span></span>  
  
    -   <span data-ttu-id="1960a-125">Sie muss auf einer Serverinstanz befinden, auf der ein sekundäres Replikat für die Verfügbarkeitsgruppe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1960a-125">Reside on a server instance that hosts a secondary replica for the availability group.</span></span>  
  
 <span data-ttu-id="1960a-126">Sobald der Sicherungsauftrag auf der primären Datenbank ausgeführt wurde, deaktivieren Sie den Sicherungsauftrag, und sobald der Wiederherstellungsauftrag auf einer angegebenen sekundären Datenbank ausgeführt wurde, deaktivieren Sie den Wiederherstellungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="1960a-126">Once the backup job has run on the primary database, disable the backup job, and once the restore job has run on a given secondary database, disable the restore job.</span></span>  
  
 <span data-ttu-id="1960a-127">Nachdem Sie alle sekundären Datenbanken für die Verfügbarkeitsgruppe erstellt haben, sofern Sie Sicherungen auf sekundären Replikaten ausführen möchten, müssen Sie die Voreinstellung zur automatisierten Sicherung der Verfügbarkeitsgruppe neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1960a-127">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you need to re-configure the automated backup preference of the availability group.</span></span>  
  
 <span data-ttu-id="1960a-128">**Weitere Informationen finden Sie unter:**</span><span class="sxs-lookup"><span data-stu-id="1960a-128">**For more information:**</span></span>  
  
 <span data-ttu-id="1960a-129">[Konvertieren einer Protokollversandkonfiguration in eine Verfügbarkeitsgruppe](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (ein SQL Server-Blog)</span><span class="sxs-lookup"><span data-stu-id="1960a-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (a SQL Server blog)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1960a-130">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1960a-130">Related Tasks</span></span>  
 <span data-ttu-id="1960a-131">**Protokollversand**</span><span class="sxs-lookup"><span data-stu-id="1960a-131">**Log shipping**</span></span>  
  
-   [<span data-ttu-id="1960a-132">Aktualisieren des Protokoll Versands auf SQL Server 2014 &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-132">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](../../log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="1960a-133">Entfernen des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-133">Remove Log Shipping &#40;SQL Server&#41;</span></span>](../../log-shipping/remove-log-shipping-sql-server.md)  
  
 <span data-ttu-id="1960a-134">**AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="1960a-134">**AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="1960a-135">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-135">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1960a-136">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-136">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1960a-137">Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-137">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="1960a-138">Erstellen einer Verfügbarkeitsgruppe &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-138">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="1960a-139">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-139">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1960a-140">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1960a-140">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="1960a-141">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1960a-141">Related Content</span></span>  
  
-   <span data-ttu-id="1960a-142">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="1960a-142">**Blogs:**</span></span>  
  
     [<span data-ttu-id="1960a-143">Konvertieren einer Protokollversandkonfiguration in eine Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="1960a-143">Converting a logshipping configuration to Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/converting-a-logshipping-configuration-to-availability-group)  
  
     [<span data-ttu-id="1960a-144">Hinzufügen einer primären Datenbank für den Protokollversand und mindestens einer sekundären Datenbank zu einer vorhandenen Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="1960a-144">Add a Log Shipping Primary Database and Secondary Database(s) to an Existing Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/add-a-log-shipping-primary-database-and-secondary-databases-to-an-existing-availability-group)  
  
     [<span data-ttu-id="1960a-145">SQL Server AlwaysOn-Teamblogs: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="1960a-145">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/)  
  
     [<span data-ttu-id="1960a-146">CSS SQL Server-Technikblogs</span><span class="sxs-lookup"><span data-stu-id="1960a-146">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="1960a-147">**Whitepaper:**</span><span class="sxs-lookup"><span data-stu-id="1960a-147">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="1960a-148">Migrationshandbuch: Migrieren zu AlwaysOn-Verfügbarkeitsgruppen von vorherigen Bereitstellungen, in denen Datenbankspiegelung und Protokollversand kombiniert sind</span><span class="sxs-lookup"><span data-stu-id="1960a-148">Migration Guide: Migrating to AlwaysOn Availability Groups from Prior Deployments Combining Database Mirroring and Log Shipping</span></span>](https://msdn.microsoft.com/library/jj635217)  
  
     [<span data-ttu-id="1960a-149">Microsoft-Whitepapers für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="1960a-149">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="1960a-150">Whitepapers des SQL Server-Kundenberatungsteams</span><span class="sxs-lookup"><span data-stu-id="1960a-150">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="1960a-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1960a-151">See Also</span></span>  
 <span data-ttu-id="1960a-152">[Informationen zum Protokollversand &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1960a-152">[About Log Shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="1960a-153">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1960a-153">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="1960a-154">Überwachen von Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1960a-154">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
