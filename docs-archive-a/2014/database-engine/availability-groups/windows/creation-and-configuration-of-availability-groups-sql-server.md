---
title: Erstellen und Konfigurieren von Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], creating
ms.assetid: 7f89fab8-6ee2-4273-9de0-e594bfb9407f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc33da393527c19985f5e7b214ba4bc02dc2f3af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727125"
---
# <a name="creation-and-configuration-of-availability-groups-sql-server"></a><span data-ttu-id="f3d3f-102">Erstellung und Konfiguration von Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f3d3f-102">Creation and Configuration of Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="f3d3f-103">Die Themen in diesem Abschnitt erklären, wie eine [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Implementierung auf Instanzen von [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] bereitgestellt wird, die sich auf unterschiedlichen WSFC-Knoten (Windows Server-Failoverclustering) innerhalb eines einzelnen WSFC-Failoverclusters befinden.</span><span class="sxs-lookup"><span data-stu-id="f3d3f-103">The topics in this section explain how to deploy a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] implementation on instances of [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] that reside on different Windows Server Failover Clustering (WSFC) nodes within a single WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="f3d3f-104">Es wird dringend empfohlen, dass Sie sich vor dem Erstellen der ersten Verfügbarkeitsgruppe mit den Informationen in den folgenden Themen vertraut machen:</span><span class="sxs-lookup"><span data-stu-id="f3d3f-104">Before you create your first availability group, we strongly recommend that you familiarize yourself with the information in the following topics:</span></span>  
  
 [<span data-ttu-id="f3d3f-105">Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-105">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
 <span data-ttu-id="f3d3f-106">In diesem Thema werden die erforderlichen Voraussetzungen, Einschränkungen und Empfehlungen für Computer, WSFC-Knoten, Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], Verfügbarkeitsgruppen, Replikate und Datenbanken beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f3d3f-106">This topic describes the prerequisites, restrictions, and recommendations for computers; WSFC nodes; instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; availability groups, replicas, and databases.</span></span> <span data-ttu-id="f3d3f-107">Das Thema enthält auch Informationen zu Sicherheitsaspekten.</span><span class="sxs-lookup"><span data-stu-id="f3d3f-107">This topic also contains information about security considerations.</span></span>  
  
 [<span data-ttu-id="f3d3f-108">Die ersten Schritte mit AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-108">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="f3d3f-109">Enthält Informationen zu den Schritten zum Konfigurieren einer Serverinstanz, Erstellen einer Verfügbarkeitsgruppe, Konfigurieren der Verfügbarkeitsgruppe für Clientverbindungen, Verwalten von Verfügbarkeitsgruppen und Überwachen von Verfügbarkeitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="f3d3f-109">Contains information about the steps for configuring a server instance, creating an availability group, configuring the availability group for client connections, managing availability groups, and monitoring availability groups.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f3d3f-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f3d3f-110">Related Tasks</span></span>  
 <span data-ttu-id="f3d3f-111">**So konfigurieren Sie eine Serverinstanz für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-111">**To configure a server instance for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span></span>  
  
-   [<span data-ttu-id="f3d3f-112">Aktivieren und Deaktivieren von Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-112">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-113">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-113">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="f3d3f-114">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-114">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="f3d3f-115">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-115">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
 <span data-ttu-id="f3d3f-116">**Erste Schritte bei der Konfiguration von AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-116">**To get started with configuring AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="f3d3f-117">Die ersten Schritte mit AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-117">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="f3d3f-118">**So erstellen und konfigurieren Sie eine neue Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-118">**To create and configure a new availability group**</span></span>  
  
-   [<span data-ttu-id="f3d3f-119">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-119">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f3d3f-120">Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-120">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="f3d3f-121">Erstellen einer Verfügbarkeitsgruppe &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-121">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="f3d3f-122">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-122">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f3d3f-123">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-123">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="f3d3f-124">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-124">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-125">Konfigurieren der flexiblen Failoverrichtlinie zum Steuern der Bedingungen für ein automatisches Failover (AlwaysOn-Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="f3d3f-125">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="f3d3f-126">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-127">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-127">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-128">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-128">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-129">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-129">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-130">Starten Sie die Daten Verschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-130">Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;</span></span>](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-131">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-131">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-132">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-132">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-133">Verwaltung von Anmeldungen und Aufträgen für die Datenbanken einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-133">Management of Logins and Jobs for the Databases of an Availability Group &#40;SQL Server&#41;</span></span>](../../logins-and-jobs-for-availability-group-databases.md)  
  
 <span data-ttu-id="f3d3f-134">**So beheben Sie Probleme**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-134">**To troubleshoot**</span></span>  
  
-   [<span data-ttu-id="f3d3f-135">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfiguration (SQL Server) gelöscht</span><span class="sxs-lookup"><span data-stu-id="f3d3f-135">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="f3d3f-136">Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="f3d3f-136">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f3d3f-137">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f3d3f-137">Related Content</span></span>  
  
-   <span data-ttu-id="f3d3f-138">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-138">**Blogs:**</span></span>  
  
     [<span data-ttu-id="f3d3f-139">AlwaysON - HADRON-Lernreihe: Nutzung des Arbeitsthreadpools für HADRON-fähige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="f3d3f-139">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="f3d3f-140">SQL Server AlwaysOn-Teamblogs: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="f3d3f-140">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="f3d3f-141">CSS SQL Server-Technikblogs</span><span class="sxs-lookup"><span data-stu-id="f3d3f-141">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="f3d3f-142">**Videos:**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-142">**Videos:**</span></span>  
  
     [<span data-ttu-id="f3d3f-143">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 1: Einführung in die nächste Generation von Lösungen mit hoher Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f3d3f-143">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="f3d3f-144">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 2: Erstellen einer unternehmenswichtigen Lösung für hohe Verfügbarkeit mit AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f3d3f-144">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="f3d3f-145">**Whitepaper:**</span><span class="sxs-lookup"><span data-stu-id="f3d3f-145">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="f3d3f-146">Microsoft SQL Server AlwaysOn-Lösungshandbuch zu hoher Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="f3d3f-146">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="f3d3f-147">Microsoft-Whitepapers für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="f3d3f-147">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="f3d3f-148">Whitepapers des SQL Server-Kundenberatungsteams</span><span class="sxs-lookup"><span data-stu-id="f3d3f-148">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="f3d3f-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3d3f-149">See Also</span></span>  
 <span data-ttu-id="f3d3f-150">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3d3f-150">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="f3d3f-151">[Verwaltung einer Verfügbarkeits Gruppe &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3d3f-151">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="f3d3f-152">[AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="f3d3f-152">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="f3d3f-153">[Überwachen von Verfügbarkeitsgruppen (SQL Server)](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3d3f-153">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f3d3f-154">AlwaysOn-Verfügbarkeitsgruppen: Interoperabilität (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f3d3f-154">AlwaysOn Availability Groups: Interoperability (SQL Server)</span></span>](always-on-availability-groups-interoperability-sql-server.md)  
  
