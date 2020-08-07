---
title: Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- read-only routing
- Availability Groups [SQL Server], readable secondary replicas
- Availability Groups [SQL Server], read-only routing
- readable secondary replicas
- Availability Groups [SQL Server], client connectivity
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 7bd89ddd-0403-4930-a5eb-3c78718533d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d51d1db75caa29814a01fc1f49bfdd49b403c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619999"
---
# <a name="configure-read-only-routing-for-an-availability-group-sql-server"></a><span data-ttu-id="fb922-102">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fb922-102">Configure Read-Only Routing for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="fb922-103">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]können Sie eine AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[tsql](../../../includes/tsql-md.md)] oder mit PowerShell für schreibgeschütztes Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb922-103">To configure an AlwaysOn availability group to support read-only routing in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can use either [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell.</span></span> <span data-ttu-id="fb922-104">*Schreibgeschütztes Routing* bezeichnet die Fähigkeit von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , schreibgeschützte Verbindungsanforderungen an ein verfügbares [lesbares sekundäres AlwaysOn-Replikat](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) weiterzuleiten (das heißt, an ein Replikat, das unter der sekundären Rolle für schreibgeschützte Arbeitsauslastungen konfiguriert ist).</span><span class="sxs-lookup"><span data-stu-id="fb922-104">*Read-only routing* refers to the ability of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to route qualifying read-only connection requests to an available AlwaysOn [readable secondary replica](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) (that is, a replica that is configured to allow read-only workloads when running under the secondary role).</span></span> <span data-ttu-id="fb922-105">Um schreibgeschütztes Routing zu unterstützen, muss die Verfügbarkeitsgruppe einen [Verfügbarkeitsgruppenlistener](../../listeners-client-connectivity-application-failover.md)besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb922-105">To support read-only routing, the availability group must possess an [availability group listener](../../listeners-client-connectivity-application-failover.md).</span></span> <span data-ttu-id="fb922-106">Schreibgeschützte Clients müssen die eigenen Verbindungsanforderungen an diesen Listener weiterleiten, und in den Verbindungszeichenfolgen des Clients muss die Anwendungsabsicht als "schreibgeschützt" angeben sein.</span><span class="sxs-lookup"><span data-stu-id="fb922-106">Read-only clients must direct their connection requests to this listener, and the client's connection strings must specify the application intent as "read-only."</span></span> <span data-ttu-id="fb922-107">Es muss sich also um *Verbindungsanforderungen für beabsichtigte Lesevorgänge*handeln.</span><span class="sxs-lookup"><span data-stu-id="fb922-107">That is, they must be *read-intent connection requests*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb922-108">Informationen zum Konfigurieren eines lesbaren sekundären Replikats finden Sie unter [Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md)besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb922-108">For information about how to configure a readable secondary replica, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="fb922-109">Die Konfiguration von schreibgeschütztem Routing wird von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb922-109">Configuring read-only routing is not supported by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fb922-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="fb922-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fb922-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fb922-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="fb922-112">Die Verfügbarkeitsgruppe muss über einen Verfügbarkeitsgruppenlistener verfügen.</span><span class="sxs-lookup"><span data-stu-id="fb922-112">The availability group must possess an availability group listener.</span></span> <span data-ttu-id="fb922-113">Weitere Informationen finden Sie unter [Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-113">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   <span data-ttu-id="fb922-114">Mindestens ein Verfügbarkeits Replikat muss so konfiguriert werden, dass es schreibgeschützte in der sekundären Rolle akzeptiert (d. h., wenn es sich um [lesbare sekundäre Replikate](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)handelt (AlwaysOn% 20availability% 20groups \) . MD)).</span><span class="sxs-lookup"><span data-stu-id="fb922-114">One or more availability replicas must be configured to accept read-only in the secondary role (that is, to be [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn%20Availability%20Groups\).md)).</span></span> <span data-ttu-id="fb922-115">Weitere Informationen finden Sie unter [Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md)besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb922-115">For more information, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>  
  
-   <span data-ttu-id="fb922-116">Sie müssen mit der Serverinstanz verbunden sein, auf der das aktuelle primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fb922-116">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
###  <a name="what-replica-properties-do-you-need-to-configure-to-support-read-only-routing"></a><a name="RORReplicaProperties"></a><span data-ttu-id="fb922-117">Welche Replikat Eigenschaften müssen Sie konfigurieren, um Schreib geschütztes Routing zu unterstützen?</span><span class="sxs-lookup"><span data-stu-id="fb922-117">What Replica Properties Do you Need to Configure to Support Read-Only Routing?</span></span>  
  
-   <span data-ttu-id="fb922-118">Für jedes lesbare sekundäre Replikat, das schreibgeschütztes Routing unterstützen soll, müssen Sie eine *URL für schreibgeschütztes Routing*angeben.</span><span class="sxs-lookup"><span data-stu-id="fb922-118">For each readable secondary replica that is to support read-only routing, you need to specify a *read-only routing URL*.</span></span> <span data-ttu-id="fb922-119">Diese URL wird nur wirksam, wenn das lokale Replikat unter der sekundären Rolle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb922-119">This URL takes effect only when the local replica is running under the secondary role.</span></span> <span data-ttu-id="fb922-120">Die URL für schreibgeschütztes Routing muss nach Bedarf replikatweise angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fb922-120">The read-only routing URL must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="fb922-121">Jede URL für schreibgeschütztes Routing wird zum Weiterleiten von Verbindungsanforderungen für beabsichtigte Lesevorgänge an ein bestimmtes lesbares sekundäres Replikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb922-121">Each read-only routing URL is used for routing read-intent connection requests to a specific readable secondary replica.</span></span> <span data-ttu-id="fb922-122">In der Regel wird jedem lesbaren sekundären Replikat eine URL für schreibgeschütztes Routing zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fb922-122">Typically, every readable secondary replica is assigned a read-only routing URL.</span></span>  
  
     <span data-ttu-id="fb922-123">Informationen zum Berechnen der schreibgeschützten Routing-URL für ein Verfügbarkeitsreplikat finden Sie unter [Berechnen von read_only_routing_url für AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="fb922-123">For information about calculating the read-only routing URL for an availability replica, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
-   <span data-ttu-id="fb922-124">Für jedes Verfügbarkeitsreplikat, das als primäres Replikat schreibgeschütztes Routing unterstützen soll, müssen Sie eine *Liste für schreibgeschütztes Routing*angeben.</span><span class="sxs-lookup"><span data-stu-id="fb922-124">For each availability replica that you want to support read-only routing when it is the primary replica, you need to specify a *read-only routing list*.</span></span> <span data-ttu-id="fb922-125">Eine Liste für schreibgeschütztes Routing wird nur wirksam, wenn das lokale Replikat unter der primären Rolle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb922-125">A given read-only routing list takes effect only when the local replica is running under the primary role.</span></span> <span data-ttu-id="fb922-126">Diese Liste muss nach Bedarf replikatweise angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fb922-126">This list must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="fb922-127">Normalerweise enthält jede Liste für schreibgeschütztes Routing jede URL für schreibgeschütztes Routing, wobei die URL des lokalen Replikats am Ende der Liste steht.</span><span class="sxs-lookup"><span data-stu-id="fb922-127">Typically, each read-only routing list would contain every read-only routing URL, with the URL of the local replica at the end of the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb922-128">Verbindungsanforderungen für beabsichtigte Lesevorgänge werden an das erste verfügbare lesbare sekundäre Replikat auf der Liste für schreibgeschütztes Routing des aktuellen primären Replikats weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fb922-128">Read-intent connection requests are routed to the first available readable secondary on the read-only routing list of the current primary replica.</span></span> <span data-ttu-id="fb922-129">Es erfolgt kein Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="fb922-129">There is no load balancing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb922-130">Weitere Informationen zu Verfügbarkeitsgruppenlistenern und zum schreibgeschützten Routing finden Sie unter [Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md)besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb922-130">For information about availability group listeners and more information about read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fb922-131">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fb922-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fb922-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fb922-132">Permissions</span></span>  
  
|<span data-ttu-id="fb922-133">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="fb922-133">Task</span></span>|<span data-ttu-id="fb922-134">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fb922-134">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="fb922-135">So konfigurieren Sie Replikate beim Erstellen einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fb922-135">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="fb922-136">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** und die CREATE AVAILABILITY GROUP-Serverberechtigung, ALTER ANY AVAILABILITY GROUP-Berechtigung oder CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="fb922-136">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="fb922-137">So ändern Sie ein Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="fb922-137">To modify an availability replica</span></span>|<span data-ttu-id="fb922-138">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="fb922-138">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fb922-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb922-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="fb922-140">**So konfigurieren Sie schreibgeschütztes Routing**</span><span class="sxs-lookup"><span data-stu-id="fb922-140">**To Configure read-only routing**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb922-141">Ein Codebeispiel finden Sie weiter unten in diesem Abschnitt unter [Beispiel (Transact-SQL)](#TsqlExample).</span><span class="sxs-lookup"><span data-stu-id="fb922-141">For a code example, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="fb922-142">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="fb922-142">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="fb922-143">Wenn Sie ein Replikat für eine neue Verfügbarkeitsgruppe angeben, verwenden Sie die [-Anweisung](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb922-143">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="fb922-144">Wenn Sie ein Replikat für eine vorhandene Verfügbarkeits Gruppe hinzufügen oder ändern, verwenden Sie die [Alter Availability Group](/sql/t-sql/statements/alter-availability-group-transact-sql) - [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisung.</span><span class="sxs-lookup"><span data-stu-id="fb922-144">If you are adding or modifying a replica for an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="fb922-145">Geben Sie zum Konfigurieren des schreibgeschützten Routings für die sekundäre Rolle in der ADD REPLICA- bzw. MODIFY REPLICA WITH-Klausel die SECONDARY_ROLE-Option wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="fb922-145">To configure read-only routing for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="fb922-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **= '** TCP **:// *`system-address`* : *`port`* ')**</span><span class="sxs-lookup"><span data-stu-id="fb922-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **://*`system-address`*:*`port`*')**</span></span>  
  
         <span data-ttu-id="fb922-147">Die URL für das schreibgeschützte Routing verfügt über die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="fb922-147">The parameters of the read-only routing URL are as follows:</span></span>  
  
         <span data-ttu-id="fb922-148">*system-address*</span><span class="sxs-lookup"><span data-stu-id="fb922-148">*system-address*</span></span>  
         <span data-ttu-id="fb922-149">Ist eine Zeichenfolge, beispielsweise ein Systemname, ein vollqualifizierter Domänenname oder eine IP-Adresse, die das Zielcomputersystem eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fb922-149">Is a string, such as a system name, a fully qualified domain name, or an IP address, that unambiguously identifies the destination computer system.</span></span>  
  
         <span data-ttu-id="fb922-150">*port*</span><span class="sxs-lookup"><span data-stu-id="fb922-150">*port*</span></span>  
         <span data-ttu-id="fb922-151">Ist eine Portnummer, die von der Datenbank-Engine der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb922-151">Is a port number that is used by the Database Engine of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="fb922-152">Beispiel:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span><span class="sxs-lookup"><span data-stu-id="fb922-152">For example:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span></span>  
  
         <span data-ttu-id="fb922-153">In einer MODIFY REPLICA-Klausel ist ALLOW_CONNECTIONS optional, wenn das Replikat bereits so konfiguriert worden ist, dass es schreibgeschützte Verbindungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="fb922-153">In a MODIFY REPLICA clause the ALLOW_CONNECTIONS is optional if the replica is already configured to allow read-only connections.</span></span>  
  
         <span data-ttu-id="fb922-154">Weitere Informationen finden Sie unter [Berechnen von read_only_routing_url für AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="fb922-154">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="fb922-155">Geben Sie zum Konfigurieren des schreibgeschützten Routings für die primäre Rolle in der ADD REPLICA- bzw. MODIFY REPLICA WITH-Klausel die PRIMARY_ROLE-Option wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="fb922-155">To configure read-only routing for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="fb922-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **= (' *`server`* '** [ **,**... *n* ] **))**</span><span class="sxs-lookup"><span data-stu-id="fb922-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **=('*`server`*'** [ **,**...*n* ] **))**</span></span>  
  
         <span data-ttu-id="fb922-157">wobei *server* eine Serverinstanz identifiziert, die ein schreibgeschütztes sekundäres Replikat in der Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="fb922-157">where, *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span>  
  
         <span data-ttu-id="fb922-158">Beispiel:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span><span class="sxs-lookup"><span data-stu-id="fb922-158">For example:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="fb922-159">Sie müssen die URL für das schreibgeschützte Routing festlegen, bevor Sie die schreibgeschützte Routingliste festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb922-159">You must set the read-only routing URL before configuring the read-only routing list.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="fb922-160">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb922-160">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="fb922-161">Im folgenden Beispiel werden zwei Verfügbarkeitsreplikate einer vorhandenen Verfügbarkeitsgruppe `AG1` geändert, sodass schreibgeschütztes Routing unterstützt wird, wenn eines dieser Replikate die primäre Rolle besitzt.</span><span class="sxs-lookup"><span data-stu-id="fb922-161">The following example modifies two availability replicas of an existing availability group, `AG1` to support read-only routing if one of these replicas currently owns the primary role.</span></span> <span data-ttu-id="fb922-162">In diesem Beispiel werden die Instanznamen `COMPUTER01` und `COMPUTER02` zur Identifikation der Serverinstanzen angegeben, die das Verfügbarkeitsreplikat hosten.</span><span class="sxs-lookup"><span data-stu-id="fb922-162">To identify the server instances that host the availability replica, this example specifies the instance names-`COMPUTER01` and `COMPUTER02`.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER02.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER02','COMPUTER01')));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER01','COMPUTER02')));  
GO
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="fb922-163">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb922-163">Using PowerShell</span></span>  

### <a name="to-configure-read-only-routing"></a><span data-ttu-id="fb922-164">So konfigurieren Sie schreibgeschütztes Routing</span><span class="sxs-lookup"><span data-stu-id="fb922-164">To Configure read-only routing</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="fb922-165">Ein Codebeispiel finden Sie weiter unten in diesem Abschnitt unter [Beispiel (PowerShell)](#PSExample).</span><span class="sxs-lookup"><span data-stu-id="fb922-165">For a code example, see [Example (PowerShell)](#PSExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="fb922-166">Legen Sie den Standard (`cd`) auf die Serverinstanz fest, auf der das primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fb922-166">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="fb922-167">Wenn Sie einer Verfügbarkeitsgruppe ein Verfügbarkeitsreplikat hinzufügen, verwenden Sie das `New-SqlAvailabilityReplica`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fb922-167">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="fb922-168">Wenn Sie ein vorhandenes Verfügbarkeitsreplikat ändern, verwenden Sie das `Set-SqlAvailabilityReplica`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fb922-168">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="fb922-169">Die relevanten Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fb922-169">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="fb922-170">Um das schreibgeschützte Routing für die sekundäre Rolle zu konfigurieren, geben Sie den Parameter **readonlyroutingconnectionurl " *`url`* "** an.</span><span class="sxs-lookup"><span data-stu-id="fb922-170">To configure read-only routing for the secondary role, specify the **ReadonlyRoutingConnectionUrl"*`url`*"** parameter.</span></span>  
  
         <span data-ttu-id="fb922-171">wobei *url* für den vollqualifizierten Domänennamen (FQDN) und Port der Verbindung steht, die beim Routing zum Replikat für schreibgeschützte Verbindungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb922-171">where, *url* is the connectivity fully-qualified domain name (FQDN) and port to use when routing to the replica for read-only connections.</span></span> <span data-ttu-id="fb922-172">Beispiel: `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span><span class="sxs-lookup"><span data-stu-id="fb922-172">For example:  `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span></span>  
  
         <span data-ttu-id="fb922-173">Weitere Informationen finden Sie unter [Berechnen von read_only_routing_url für AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="fb922-173">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="fb922-174">Um den Verbindungs Zugriff für die primäre Rolle zu konfigurieren, geben Sie **"Read onlyroutinglist" *`server`* "** [ **,**... *n* ], wobei *Server* eine Serverinstanz identifiziert, die ein Schreib geschütztes sekundäres Replikat in der Verfügbarkeits Gruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="fb922-174">To configure connection access for the primary role, specify **ReadonlyRoutingList"*`server`*"** [ **,**...*n* ], where *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span> <span data-ttu-id="fb922-175">Beispiel: `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span><span class="sxs-lookup"><span data-stu-id="fb922-175">For example:  `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="fb922-176">Sie müssen die URL für das schreibgeschützte Routing für ein Replikat festlegen, bevor Sie dessen schreibgeschützte Routingliste festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb922-176">You must set the read-only routing URL of a replica before configuring its read-only routing list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb922-177">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="fb922-177">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="fb922-178">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-178">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="fb922-179">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) und [Hilfe SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-179">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) and [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>
  
###  <a name="example-powershell"></a><a name="PSExample"></a> <span data-ttu-id="fb922-180">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="fb922-180">Example (PowerShell)</span></span>  
 <span data-ttu-id="fb922-181">Im folgenden Beispiel werden das primäre Replikat und ein sekundäres Replikat in einer Verfügbarkeitsgruppe für das schreibgeschützte Routing konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fb922-181">The following example configures the primary replica and one secondary replica in an availability group for read-only routing.</span></span> <span data-ttu-id="fb922-182">Im Beispiel wird zuerst jedem Replikat eine URL für das schreibgeschützte Routing zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fb922-182">First, the example assigns a read-only routing URL to each replica.</span></span> <span data-ttu-id="fb922-183">Anschließend wird die Liste für schreibgeschütztes Routing auf dem primären Replikat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb922-183">Then it sets the read-only routing list on the primary replica.</span></span> <span data-ttu-id="fb922-184">Verbindungen, für die in der Verbindungszeichenfolge die ReadOnly-Eigenschaft festgelegt wurde, werden an das sekundäre Replikat umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fb922-184">Connections with the "ReadOnly" property set in the connection string will be redirected to the secondary replica.</span></span> <span data-ttu-id="fb922-185">Wenn vom sekundären Replikat nicht gelesen werden kann (durch die `ConnectionModeInSecondaryRole`-Einstellung vorgegeben), wird die Verbindung wiederum zurück an das primäre Replikat geleitet.</span><span class="sxs-lookup"><span data-stu-id="fb922-185">If this secondary replica is not readable (as determined by the `ConnectionModeInSecondaryRole` setting), the connection will be directed back to the primary replica.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  
$secondaryReplica = Get-Item "AvailabilityReplicas\SecondaryServer"  
  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://PrimaryServer.domain.com:1433" -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://SecondaryServer.domain.com:1433" -InputObject $secondaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingList "SecondaryServer","PrimaryServer" -InputObject $primaryReplica  
```  
  
##  <a name="follow-up-after-configuring-read-only-routing"></a><a name="FollowUp"></a><span data-ttu-id="fb922-186">Nachverfolgung: nach dem Konfigurieren des schreibgeschützten Routings</span><span class="sxs-lookup"><span data-stu-id="fb922-186">Follow Up: After Configuring Read-Only Routing</span></span>  
 <span data-ttu-id="fb922-187">Sobald das aktuelle primäre Replikat und die lesbaren sekundären Replikate konfiguriert worden sind, sodass sie schreibgeschütztes Routing in beiden Rollen unterstützen, können die lesbaren sekundären Replikate Anforderungen für Leseverbindungen von Clients empfangen, die über den Verfügbarkeitsgruppenlistener eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="fb922-187">Once the current primary replica and the readable secondary replicas are configured to support read-only routing in both roles, the readable secondary replicas can receive read read-intent connection requests from clients that connect via the availability group listener.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="fb922-188">Wenn Sie das [Hilfsprogramm bcp](../../../tools/bcp-utility.md) oder das [Hilfsprogramm sqlcmd](../../../tools/sqlcmd-utility.md)verwenden, können Sie den schreibgeschützten Zugriff auf alle sekundären Replikate angeben, die für den schreibgeschützten Zugriff aktiviert sind, indem Sie den- `-K ReadOnly` Schalter angeben.</span><span class="sxs-lookup"><span data-stu-id="fb922-188">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
###  <a name="requirements-and-recommendations-for-client-connection-strings"></a><a name="ConnStringReqsRecs"></a><span data-ttu-id="fb922-189">Anforderungen und Empfehlungen für Client Verbindungs Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fb922-189">Requirements and Recommendations for Client Connection-Strings</span></span>  
 <span data-ttu-id="fb922-190">Damit eine Clientanwendung schreibgeschütztes Routing verwendet, muss seine Verbindungszeichenfolge die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="fb922-190">For a client application to use read-only routing, its connection string must satisfy the following requirements:</span></span>  
  
-   <span data-ttu-id="fb922-191">Verwendung des TCP-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="fb922-191">Use the TCP protocol.</span></span>  
  
-   <span data-ttu-id="fb922-192">Festlegen des Attributs bzw. der Eigenschaft für die Anwendungsabsicht auf schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb922-192">Set the application intent attribute/property to readonly.</span></span>  
  
-   <span data-ttu-id="fb922-193">Verweis auf den Listener einer Verfügbarkeitsgruppe, der zur Unterstützung des schreibgeschützten Routing konfiguriert worden ist.</span><span class="sxs-lookup"><span data-stu-id="fb922-193">Reference the listener of an availability group that is configured to support read-only routing.</span></span>  
  
-   <span data-ttu-id="fb922-194">Verweis auf eine Datenbank in dieser Verfügbarkeitsgruppennamen.</span><span class="sxs-lookup"><span data-stu-id="fb922-194">Reference a database in that availability group.</span></span>  
  
 <span data-ttu-id="fb922-195">Außerdem empfiehlt es sich, dass Verbindungszeichenfolgen Multisubnetzfailover aktivieren, das in jedem Subnetz einen parallelen Clientthread für jedes Replikat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb922-195">In addition, we recommend that connection strings enable multi-subnet failover, which supports a parallel client thread for each replica on each subnet.</span></span> <span data-ttu-id="fb922-196">Dadurch wird die Zeitspanne minimiert, die nach einem Failover zum Wiederherstellen der Verbindung mit dem Client erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fb922-196">This minimizes client reconnection time after a failover.</span></span>  
  
 <span data-ttu-id="fb922-197">Die Syntax für eine Verbindungszeichenfolge hängt vom SQL Server-Anbieter ab, den eine Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb922-197">The syntax for a connection string depends on the SQL Server provider an application is using.</span></span> <span data-ttu-id="fb922-198">Die folgende Beispielverbindungszeichenfolge für den .NET Framework-Datenanbieter 4.0.2 für SQL Server veranschaulicht die Teile einer Verbindungszeichenfolge, die für schreibgeschütztes Routing erforderlich und empfohlen sind.</span><span class="sxs-lookup"><span data-stu-id="fb922-198">The following example connection string for the .NET Framework Data Provider 4.0.2 for SQL Server illustrates the parts of a connection string that are required and recommended to work for read-only routing.</span></span>  
  
```  
Server=tcp:MyAgListener,1433;Database=Db1;IntegratedSecurity=SSPI;ApplicationIntent=ReadOnly;MultiSubnetFailover=True  
```  
  
 <span data-ttu-id="fb922-199">Weitere Informationen zur schreibgeschützten Anwendungsabsicht und zum schreibgeschützten Routing finden Sie unter [Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md)besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb922-199">For more information about read-only application intent and read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
### <a name="if-read-only-routing-is-not-working-correctly"></a><span data-ttu-id="fb922-200">Wenn schreibgeschütztes Routing nicht ordnungsgemäß funktioniert</span><span class="sxs-lookup"><span data-stu-id="fb922-200">If Read-Only Routing is Not Working Correctly</span></span>  
 <span data-ttu-id="fb922-201">Informationen zum Durchführen einer Problembehandlung an einer schreibgeschützten Routingkonfiguration finden Sie unter [Schreibgeschütztes Routing funktioniert nicht ordnungsgemäß](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-201">For information about troubleshooting a read-only routing configuration, see [Read-Only Routing is Not Working Correctly](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fb922-202">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="fb922-202">Related Tasks</span></span>  

### <a name="to-view-read-only-routing-configurations"></a><span data-ttu-id="fb922-203">So zeigen Sie schreibgeschützte Routingkonfigurationen an</span><span class="sxs-lookup"><span data-stu-id="fb922-203">To view read-only routing configurations</span></span>
  
-   [<span data-ttu-id="fb922-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb922-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
  
-   <span data-ttu-id="fb922-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url**-Spalte)</span><span class="sxs-lookup"><span data-stu-id="fb922-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url** column)</span></span>  
  
### <a name="to-configure-client-connection-access"></a><span data-ttu-id="fb922-206">So konfigurieren Sie den Clientverbindungszugriff</span><span class="sxs-lookup"><span data-stu-id="fb922-206">To configure client connection access</span></span>
  
-   [<span data-ttu-id="fb922-207">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fb922-207">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="fb922-208">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fb922-208">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
### <a name="to-use-connection-strings-in-applications"></a><span data-ttu-id="fb922-209">So verwenden Sie Verbindungszeichenfolgen in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="fb922-209">To use connection strings in applications</span></span>
  
-   [<span data-ttu-id="fb922-210">SQL Server Native Client-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="fb922-210">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](../../../relational-databases/native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
  
-   [<span data-ttu-id="fb922-211">Verwenden von Schlüsselwörtern für Verbindungszeichenfolgen mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="fb922-211">Using Connection String Keywords with SQL Server Native Client</span></span>](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="fb922-212">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="fb922-212">Related Content</span></span>  
  
-   <span data-ttu-id="fb922-213">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="fb922-213">**Blogs:**</span></span>  
  
     [<span data-ttu-id="fb922-214">Berechnen von read_only_routing_url für AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="fb922-214">Calculating read_only_routing_url for AlwaysOn</span></span>](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson)  
  
     [<span data-ttu-id="fb922-215">SQL Server AlwaysOn-Teamblogs: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="fb922-215">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="fb922-216">CSS SQL Server-Technikblogs</span><span class="sxs-lookup"><span data-stu-id="fb922-216">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="fb922-217">**Whitepaper:**</span><span class="sxs-lookup"><span data-stu-id="fb922-217">**White papers:**</span></span>  
  
     [<span data-ttu-id="fb922-218">Microsoft-Whitepapers für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="fb922-218">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="fb922-219">Whitepapers des SQL Server-Kundenberatungsteams</span><span class="sxs-lookup"><span data-stu-id="fb922-219">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="fb922-220">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb922-220">See Also</span></span>  
 <span data-ttu-id="fb922-221">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fb922-221">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="fb922-222">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fb922-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="fb922-223">[Aktive sekundäre Replikate: lesbare sekundäre Replikate (AlwaysOn-Verfügbarkeitsgruppen)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="fb922-223">[Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 <span data-ttu-id="fb922-224">[Informationen zum Clientverbindungszugriff auf Verfügbarkeitsreplikate &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fb922-224">[About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span></span>  
 [<span data-ttu-id="fb922-225">Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fb922-225">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
