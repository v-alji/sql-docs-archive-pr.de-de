---
title: Konfiguration einer Server Instanz für Always on Verfügbarkeits Gruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], about
ms.assetid: fad8db32-593e-49d5-989c-39eb8399c416
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3392e6189b687516e627d847acceedb165141117
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724994"
---
# <a name="configuration-of-a-server-instance-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="95728-102">Konfiguration einer Serverinstanz für Always On-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="95728-102">Configuration of a Server Instance for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="95728-103">Dieses Thema enthält Informationen zu den Anforderungen für die Konfiguration einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zur Unterstützung von AlwaysOn-Verfügbarkeitsgruppen [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95728-103">This topic contains information about the requirements for configuring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="95728-104">Wichtige Informationen zu erforderlichen [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]-Komponenten und Einschränkungen für WSFC-Knoten (Windows Server-Failoverclustering) und für Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="95728-104">For essential information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites and restrictions for Windows Server Failover Clustering (WSFC) nodes and for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
 
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="95728-105">Begriffe und Definitionen</span><span class="sxs-lookup"><span data-stu-id="95728-105">Terms and Definitions</span></span>  
  
 <span data-ttu-id="95728-106">Eine Lösung für hohe Verfügbarkeit und Notfallwiederherstellung, die als Ersatz für die Datenbankspiegelung auf Unternehmensebene verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="95728-106">A high-availability and disaster-recovery solution that provides an enterprise-level replacement for database mirroring.</span></span> <span data-ttu-id="95728-107">Eine *Verfügbarkeits Gruppe* unterstützt eine Failoverumgebung für einen diskreten Satz von Benutzer Datenbanken (als *Verfügbarkeits Datenbanken*bezeichnet), für die ein Failover durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="95728-107">An *availability group* supports a failover environment for a discrete set of user databases, known as *availability databases*, that fail over together.</span></span>  
  
 <span data-ttu-id="95728-108">Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="95728-108">availability replica</span></span>  
 <span data-ttu-id="95728-109">Eine Instanziierung einer Verfügbarkeitsgruppe, die von einer bestimmten Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gehostet wird und eine lokale Kopie jeder Verfügbarkeitsdatenbank beibehält, die zur Verfügbarkeitsgruppe gehört.</span><span class="sxs-lookup"><span data-stu-id="95728-109">An instantiation of an availability group that is hosted by a specific instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and that maintains a local copy of each availability database that belongs to the availability group.</span></span> <span data-ttu-id="95728-110">Zwei Typen von Verfügbarkeitsreplikaten sind vorhanden: ein einzelnes *primäres Replikat* und ein bis vier *sekundäre Replikate*.</span><span class="sxs-lookup"><span data-stu-id="95728-110">Two types of availability replicas exist: a single *primary replica* and one to four *secondary replicas*.</span></span> <span data-ttu-id="95728-111">Die Serverinstanzen, die die Verfügbarkeitsreplikate für eine angegebene Verfügbarkeitsgruppe hosten, müssen sich auf verschiedenen Konten eines einzelnen WSFC-Clusters (Windows Server-Failoverclustering) befinden.</span><span class="sxs-lookup"><span data-stu-id="95728-111">The server instances that host the availability replicas for a given availability group must reside on different nodes of a single Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 [<span data-ttu-id="95728-112">Daten Bank Spiegelungs Endpunkt</span><span class="sxs-lookup"><span data-stu-id="95728-112">database mirroring endpoint</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
 <span data-ttu-id="95728-113">Ein Endpunkt ist ein SQL Server-Objekt, mit dessen Hilfe SQL Server über das Netzwerk kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="95728-113">An endpoint is a SQL Server object that enables SQL Server to communicate over the network.</span></span> <span data-ttu-id="95728-114">Um an einer Datenbankspiegelung und/oder [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] teilnehmen zu können, ist für eine Serverinstanz ein spezieller, dedizierter Endpunkt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="95728-114">To participate in database mirroring and/or [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a server instance requires a special, dedicated endpoint.</span></span> <span data-ttu-id="95728-115">Alle Spiegelungs- und Verfügbarkeitsgruppenverbindungen auf einer Serverinstanz verwenden denselben Datenbankspiegelungs-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="95728-115">All mirroring and availability group connections on a server instance use the same database mirroring endpoint.</span></span> <span data-ttu-id="95728-116">Dieser Endpunkt ist ein auf einen bestimmten Zweck ausgerichteter Endpunkt, der ausschließlich dafür verwendet wird, diese Verbindungen von anderen Serverinstanzen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="95728-116">This endpoint is a special-purpose endpoint used exclusively to receive these connections from other server instances.</span></span>  
  
##  <a name="to-configure-a-server-instance-to-support-alwayson-availability-groups"></a><a name="ConfigSI"></a><span data-ttu-id="95728-117">So konfigurieren Sie eine Server Instanz zur Unterstützung von AlwaysOn-Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="95728-117">To Configure a Server Instance to Support AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="95728-118">Um [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]zu unterstützen, muss sich eine Serverinstanz in einem Knoten im WSFC-Failovercluster befinden, der die Verfügbarkeitsgruppe hostet. Sie muss [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -aktiviert sein und über einen Datenbankspiegelungs-Endpunkt verfügen.</span><span class="sxs-lookup"><span data-stu-id="95728-118">To support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], a server instance must reside on a node in the WSFC failover cluster that hosts the availability group, be [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] enabled, and possess a database mirroring endpoint.</span></span>  
  
1.  <span data-ttu-id="95728-119">Aktivieren Sie die Funktion AlwaysOn-Verfügbarkeitsgruppen auf jeder Serverinstanz, die an einer oder mehreren Verfügbarkeitsgruppen teilnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="95728-119">Enable the AlwaysOn Availability Groups feature on every server instance that is to participate in one or more availability groups.</span></span> <span data-ttu-id="95728-120">Eine bestimmte Serverinstanz kann nur ein einzelnes Verfügbarkeitsreplikat für eine bestimmte Verfügbarkeitsgruppe hosten.</span><span class="sxs-lookup"><span data-stu-id="95728-120">A given server instance can host only a single availability replica for a given availability group.</span></span>  
  
2.  <span data-ttu-id="95728-121">Stellen Sie sicher, dass die Serverinstanz einen Datenbankspiegelungs-Endpunkt besitzt.</span><span class="sxs-lookup"><span data-stu-id="95728-121">Ensure that the server instance possesses a database mirroring endpoint.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="95728-122">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="95728-122">Related Tasks</span></span>  
 <span data-ttu-id="95728-123">**So aktivieren Sie AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="95728-123">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="95728-124">Aktivieren und Deaktivieren von Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="95728-124">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="95728-125">**So bestimmen Sie, ob ein Datenbankspiegelungs-Endpunkt vorhanden ist**</span><span class="sxs-lookup"><span data-stu-id="95728-125">**To determine whether a database mirroring endpoint exists**</span></span>  
  
-   [<span data-ttu-id="95728-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95728-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="95728-127">**So erstellen Sie einen Datenbankspiegelungs-Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="95728-127">**To create a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="95728-128">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="95728-128">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="95728-129">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95728-129">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="95728-130">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95728-130">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="95728-131">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="95728-131">Related Content</span></span>  
  
-   <span data-ttu-id="95728-132">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="95728-132">**Blogs:**</span></span>  
  
     [<span data-ttu-id="95728-133">AlwaysON - HADRON-Lernreihe: Nutzung des Arbeitsthreadpools für HADRON-fähige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="95728-133">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="95728-134">SQL Server AlwaysOn-Teamblogs: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="95728-134">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="95728-135">CSS SQL Server-Technikblogs</span><span class="sxs-lookup"><span data-stu-id="95728-135">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="95728-136">**Videos:**</span><span class="sxs-lookup"><span data-stu-id="95728-136">**Videos:**</span></span>  
  
     [<span data-ttu-id="95728-137">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 1: Einführung in die nächste Generation von Lösungen mit hoher Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="95728-137">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="95728-138">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 2: Erstellen einer unternehmenswichtigen Lösung für hohe Verfügbarkeit mit AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="95728-138">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="95728-139">**Whitepaper:**</span><span class="sxs-lookup"><span data-stu-id="95728-139">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="95728-140">Microsoft SQL Server AlwaysOn-Lösungshandbuch zu hoher Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="95728-140">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="95728-141">Microsoft-Whitepapers für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="95728-141">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="95728-142">Whitepapers des SQL Server-Kundenberatungsteams</span><span class="sxs-lookup"><span data-stu-id="95728-142">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="95728-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95728-143">See Also</span></span>  
 <span data-ttu-id="95728-144">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95728-144">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="95728-145">[Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="95728-145">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="95728-146">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95728-146">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="95728-147">[AlwaysOn-Verfügbarkeitsgruppen: Interoperabilität (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95728-147">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="95728-148">[Failoverclustering und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95728-148">[Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="95728-149">[Windows Server-Failoverclustering &#40;WSFC&#41; mit SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95728-149">[Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="95728-150">AlwaysOn-Failoverclusterinstanzen</span><span class="sxs-lookup"><span data-stu-id="95728-150">AlwaysOn Failover Cluster Instances</span></span>](../../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md)  
  
