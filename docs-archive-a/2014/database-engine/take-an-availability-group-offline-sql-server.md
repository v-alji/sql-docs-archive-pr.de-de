---
title: Ändern der Verfügbarkeits Gruppe offline
description: Schritte zum Offline schalten der Always on-Verfügbarkeits Gruppe
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], take offline
ms.assetid: 50f5aad8-0dff-45ef-8350-f9596d3db898
author: rothja
ms.author: jroth
ms.openlocfilehash: db2f56befe6905b9c3de6bd1ab6a2e5a4a00b1b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618877"
---
# <a name="take-an-availability-group-offline-sql-server"></a><span data-ttu-id="948c4-103">Offlineschalten einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="948c4-103">Take an Availability Group Offline (SQL Server)</span></span>
  <span data-ttu-id="948c4-104">In diesem Thema wird beschrieben, wie eine AlwaysOn-Verfügbarkeitsgruppe über [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] und höheren Versionen vom Status ONLINE zum Status OFFLINE gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="948c4-104">This topic describes how to take an AlwaysOn availability group from the ONLINE state to the OFFLINE state by using [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="948c4-105">Es gibt keinen Datenverlust an Datenbanken mit synchronem Commit, da bei nicht vorgenommener Synchronisierung irgendeines Replikats mit synchronem Commit der OFFLINE-Vorgang einen Fehler auslöst und die Verfügbarkeitsgruppe ONLINE bleibt.</span><span class="sxs-lookup"><span data-stu-id="948c4-105">There is no data loss for synchronous-commit databases because if any synchronous-commit replica is not synchronized, the OFFLINE operation raises an error and leaves the availability group ONLINE.</span></span> <span data-ttu-id="948c4-106">Da die Verfügbarkeitsgruppe online bleibt, werden unsynchronisierte Datenbanken mit synchronem Commit vor möglichem Datenverlust geschützt.</span><span class="sxs-lookup"><span data-stu-id="948c4-106">Keeping the availability group online protects unsynchronized synchronous-commit databases from possible data loss.</span></span> <span data-ttu-id="948c4-107">Nachdem eine Verfügbarkeitsgruppe offline geschaltet wurde, sind ihre Datenbanken für Clients nicht mehr verfügbar, und Sie können die Verfügbarkeitsgruppe nicht wieder online schalten.</span><span class="sxs-lookup"><span data-stu-id="948c4-107">After an availability group goes offline, its databases become unavailable to clients and you cannot bring the availability group back online.</span></span> <span data-ttu-id="948c4-108">Schalten Sie daher eine Verfügbarkeitsgruppe nur offline, um die Verfügbarkeitsgruppenressourcen von einem WSFC-Cluster zu einem anderen zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="948c4-108">Therefore, take an availability group offline only to migrate the availability group resources from one WSFC cluster to another.</span></span>  
  
 <span data-ttu-id="948c4-109">Wenn während einer clusterübergreifenden Migration von [!INCLUDE[ssHADR](../includes/sshadr-md.md)]Anwendungen direkt eine Verbindung mit dem primären Replikat einer Verfügbarkeitsgruppe herstellen, muss die Verfügbarkeitsgruppe offline geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="948c4-109">During a cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)], if any applications connect directly to the primary replica of an availability group, the availability group must be taken offline.</span></span> <span data-ttu-id="948c4-110">Die clusterübergreifende Migration von [!INCLUDE[ssHADR](../includes/sshadr-md.md)] unterstützt Betriebssystemupgrades mit minimaler Downtime von Verfügbarkeitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="948c4-110">Cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supports OS upgrade with minimal downtime of availability groups.</span></span> <span data-ttu-id="948c4-111">Typischerweise wird die Kreuzclustermigration von [!INCLUDE[ssHADR](../includes/sshadr-md.md)] verwendet, um Betriebssysteme auf [!INCLUDE[win8](../includes/win8-md.md)] oder [!INCLUDE[win8srv](../includes/win8srv-md.md)]zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="948c4-111">The typical scenario is to use cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] for OS upgrade to [!INCLUDE[win8](../includes/win8-md.md)] or [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span></span> <span data-ttu-id="948c4-112">Weitere Informationen finden Sie unter [Clusterübergreifende Migration von AlwaysOn-Verfügbarkeitsgruppen für Betriebssystemupgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="948c4-112">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="948c4-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="948c4-113">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="948c4-114">Verwenden Sie die OFFLINE-Option nur für eine Kreuzclustermigration von Verfügbarkeitsgruppenressourcen.</span><span class="sxs-lookup"><span data-stu-id="948c4-114">Use the OFFLINE option only for a cross-cluster migration of availability group resources.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="948c4-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="948c4-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="948c4-116">Auf der Serverinstanz, auf der Sie den OFFLINE-Befehl eingeben, muss [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] oder höher (Enterprise Edition oder höher) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="948c4-116">The server instance on which you enter the OFFLINE command must be running [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="948c4-117">Die Verfügbarkeitsgruppe muss aktuell online sein.</span><span class="sxs-lookup"><span data-stu-id="948c4-117">The availability group must currently be online.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="948c4-118">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="948c4-118">Recommendations</span></span>  
 <span data-ttu-id="948c4-119">Bevor Sie die Verfügbarkeitsgruppe offline schalten, löschen Sie den Verfügbarkeitsgruppenlistener oder die Listener.</span><span class="sxs-lookup"><span data-stu-id="948c4-119">Before you take the availability group offline, delete the availability group listener or listeners.</span></span> <span data-ttu-id="948c4-120">Weitere Informationen finden Sie unter [Entfernen eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="948c4-120">For more information, see [Remove an Availability Group Listener &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="948c4-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="948c4-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="948c4-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="948c4-122">Permissions</span></span>  
 <span data-ttu-id="948c4-123">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="948c4-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="948c4-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="948c4-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="948c4-125">**So schalten Sie eine Verfügbarkeitsgruppe offline**</span><span class="sxs-lookup"><span data-stu-id="948c4-125">**To take an availability group offline**</span></span>  
  
1.  <span data-ttu-id="948c4-126">Stellen Sie eine Verbindung zu einer Serverinstanz her, auf der ein Verfügbarkeitsreplikat für die Verfügbarkeitsgruppe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="948c4-126">Connect to a server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="948c4-127">Dieses Replikat kann das primäre Replikat oder ein sekundäres Replikat sein.</span><span class="sxs-lookup"><span data-stu-id="948c4-127">This replica can be the primary replica or a secondary replica.</span></span>  
  
2.  <span data-ttu-id="948c4-128">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="948c4-128">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="948c4-129">ALTER AVAILABILITY GROUP *Gruppenname* OFFLINE</span><span class="sxs-lookup"><span data-stu-id="948c4-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span></span>  
  
     <span data-ttu-id="948c4-130">Dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="948c4-130">where *group_name* is the name of the availability group.</span></span>  
  
### <a name="example"></a><span data-ttu-id="948c4-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="948c4-131">Example</span></span>  
 <span data-ttu-id="948c4-132">Im folgenden Beispiel wird die `AccountsAG` -Verfügbarkeitsgruppe offline geschaltet.</span><span class="sxs-lookup"><span data-stu-id="948c4-132">The following example takes the `AccountsAG` availability group offline.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AccountsAG OFFLINE;  
```  
  
##  <a name="follow-up-after-the-availability-group-goes-offline"></a><a name="FollowUp"></a><span data-ttu-id="948c4-133">Nächster Schritt: Nachdem die Verfügbarkeitsgruppe offline geschaltet wurde</span><span class="sxs-lookup"><span data-stu-id="948c4-133">Follow Up: After the Availability Group Goes Offline</span></span>  
  
-   <span data-ttu-id="948c4-134">**Protokollieren eines OFFLINE-Vorgangs:**  Die Identität des WSFC-Knotens, in dem der OFFLINE-Vorgang initiiert wurde, wird sowohl im WSFC-Clusterprotokoll als auch in SQL ERRORLOG gespeichert.</span><span class="sxs-lookup"><span data-stu-id="948c4-134">**Logging of OFFLINE operation:**  The identity of the WSFC node where the OFFLINE operation was initiated is stored in both the WSFC cluster log and the SQL ERRORLOG.</span></span>  
  
-   <span data-ttu-id="948c4-135">**Wenn Sie den Verfügbarkeitsgruppenlistener vor dem Offlineschalten der Gruppe nicht gelöscht haben:**  Wenn Sie die Verfügbarkeitsgruppe zu einem anderen WSFC-Cluster migrieren, löschen Sie den VNN und die VIP des Listeners.</span><span class="sxs-lookup"><span data-stu-id="948c4-135">**If you did not delete the availability group listener before taking the group offline:**  If you are migrating the availability group to another WSFC cluster, delete the VNN and VIP of the listener.</span></span> <span data-ttu-id="948c4-136">Sie können sie entweder mit der Konsole der Failoverclusterverwaltung, dem PowerShell-Cmdlet [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) oder [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx)löschen.</span><span class="sxs-lookup"><span data-stu-id="948c4-136">You can delete them by using either the Failover Cluster Management console, the [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell cmdlet, or [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span></span> <span data-ttu-id="948c4-137">Beachten Sie, dass cluster.exe auf Windows 8 veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="948c4-137">Note that cluster.exe is deprecated on Windows 8.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="948c4-138">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="948c4-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="948c4-139">Entfernen eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="948c4-139">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="948c4-140">Ändern des HADR-Clusterkontexts der Serverinstanz &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="948c4-140">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="948c4-141">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="948c4-141">Related Content</span></span>  
  
-   <span data-ttu-id="948c4-142">[Technische Artikel zu SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="948c4-142">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="948c4-143">SQL Server AlwaysOn-Teamblog: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="948c4-143">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
## <a name="see-also"></a><span data-ttu-id="948c4-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="948c4-144">See Also</span></span>  
 [<span data-ttu-id="948c4-145">AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="948c4-145">AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/always-on-availability-groups-sql-server.md)  
