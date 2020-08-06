---
title: Ändern des Failovermodus eines Verfügbarkeitsreplikats (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover modes [SQL Server]
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover modes
- Availability Groups [SQL Server], configuring
ms.assetid: 619a826f-8e65-48eb-8c34-39497d238279
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d946440e2950192299c42652babb4082790dbd03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724998"
---
# <a name="change-the-failover-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="4a4f8-102">Ändern des Failovermodus eines Verfügbarkeitsreplikats (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4a4f8-102">Change the Failover Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="4a4f8-103">In diesem Thema wird beschrieben, wie der Failovermodus eines Verfügbarkeitsreplikats in einer AlwaysOn-Verfügbarkeitsgruppe in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-103">This topic describes how to change the failover mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="4a4f8-104">Der Failovermodus ist eine Replikateigenschaft, die den Failovermodus für Replikate bestimmt, die im Verfügbarkeitsmodus mit synchronem Commit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-104">The failover mode is a replica property that determines the failover mode for replicas that run under synchronous-commit availability mode.</span></span> <span data-ttu-id="4a4f8-105">Weitere Informationen finden Sie unter [Failover und Failovermodi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;](failover-and-failover-modes-always-on-availability-groups.md) und [Verfügbarkeitsmodi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="4a4f8-105">For more information, see [Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) and [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a4f8-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4a4f8-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="4a4f8-107">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a4f8-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="4a4f8-108">Dieser Task wird nur für primäre Replikate unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-108">This task is supported only on primary replicas.</span></span> <span data-ttu-id="4a4f8-109">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="4a4f8-110">SQL Server-Failoverclusterinstanzen (FCIs) unterstützen kein automatisches Failover durch Verfügbarkeitsgruppen. Daher können die Verfügbarkeitsreplikate, die von einer FCI gehostet werden, nur für manuelles Failover konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-110">SQL Server Failover Cluster Instances (FCIs) do not support automatic failover by availability groups, so any availability replica that is hosted by an FCI can only be configured for manual failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a4f8-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4a4f8-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a4f8-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4a4f8-112">Permissions</span></span>  
 <span data-ttu-id="4a4f8-113">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-113">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a4f8-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a4f8-114">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4a4f8-115">**So ändern Sie den Failovermodus eines Verfügbarkeitsreplikats**</span><span class="sxs-lookup"><span data-stu-id="4a4f8-115">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="4a4f8-116">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-116">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4a4f8-117">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="4a4f8-117">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4a4f8-118">Klicken Sie auf die Verfügbarkeitsgruppe, deren Replikat geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-118">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="4a4f8-119">Klicken Sie mit der rechten Maustaste auf das Replikat, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-119">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="4a4f8-120">Verwenden Sie im Dialogfeld **Eigenschaften des Verfügbarkeitsreplikats** die Dropdownliste **Failovermodus** , um den Failovermodus für dieses Replikat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-120">In the **Availability Replica Properties** dialog box, use the **Failover mode** drop list to change the failover mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a4f8-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a4f8-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="4a4f8-122">**So ändern Sie den Failovermodus eines Verfügbarkeitsreplikats**</span><span class="sxs-lookup"><span data-stu-id="4a4f8-122">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="4a4f8-123">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-123">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4a4f8-124">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4a4f8-124">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4a4f8-125">ALTER AVAILABILITY GROUP *Gruppenname* MODIFY REPLICA ON '*Servername*'</span><span class="sxs-lookup"><span data-stu-id="4a4f8-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="4a4f8-126">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="4a4f8-126">WITH ( {</span></span>  
  
     <span data-ttu-id="4a4f8-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="4a4f8-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="4a4f8-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="4a4f8-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="4a4f8-129">}  )</span><span class="sxs-lookup"><span data-stu-id="4a4f8-129">}  )</span></span>  
  
     <span data-ttu-id="4a4f8-130">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="4a4f8-130">where</span></span>  
  
    -   <span data-ttu-id="4a4f8-131">*Gruppenname* ist der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-131">*group_name* is the name of the availability group.</span></span>  
  
    -   <span data-ttu-id="4a4f8-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span><span class="sxs-lookup"><span data-stu-id="4a4f8-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span></span>  
  
         <span data-ttu-id="4a4f8-133">Gibt die Adresse der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] an, die das Verfügbarkeitsreplikat hostet, das geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-133">Specifies the address of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica to be altered.</span></span> <span data-ttu-id="4a4f8-134">Diese Adresse weist die folgenden Komponenten auf:</span><span class="sxs-lookup"><span data-stu-id="4a4f8-134">The components of this address are as follows:</span></span>  
  
         <span data-ttu-id="4a4f8-135">*system_name*</span><span class="sxs-lookup"><span data-stu-id="4a4f8-135">*system_name*</span></span>  
         <span data-ttu-id="4a4f8-136">Ist der NetBIOS-Name des Computersystems, auf dem sich eine eigenständige Serverinstanz befindet.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-136">Is the NetBIOS name of the computer system on which a stand-alone server instance resides.</span></span>  
  
         <span data-ttu-id="4a4f8-137">*FCI_network_name*</span><span class="sxs-lookup"><span data-stu-id="4a4f8-137">*FCI_network_name*</span></span>  
         <span data-ttu-id="4a4f8-138">Ist der Netzwerkname, der verwendet wird, um auf einen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Failovercluster zuzugreifen, in dem eine Zielserverinstanz ein [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Failoverpartner (eine FCI) ist.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-138">Is the network name that is used to access a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster in which a target server instance is a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover partner (an FCI).</span></span>  
  
         <span data-ttu-id="4a4f8-139">*instance_name*</span><span class="sxs-lookup"><span data-stu-id="4a4f8-139">*instance_name*</span></span>  
         <span data-ttu-id="4a4f8-140">Ist der Name der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , die das Zielverfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-140">Is the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the target availability replica.</span></span> <span data-ttu-id="4a4f8-141">Bei einer Standardserverinstanz ist *instance_name* optional.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-141">For a default server instance, *instance_name* is optional.</span></span>  
  
     <span data-ttu-id="4a4f8-142">Weitere Informationen zu diesen Parametern finden Sie unter [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4a4f8-142">For more information about these parameters, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="4a4f8-143">Im folgenden Beispiel, eingegeben im primären Replikat der *MyAG* -Verfügbarkeitsgruppe, wird der Failovermodus für das Verfügbarkeitsreplikat, das sich auf der Standardserverinstanz auf dem Computer *COMPUTER01*befindet, in automatisches Failover geändert.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-143">The following example, entered on the primary replica of the *MyAG* availability group, changes the failover mode to automatic failover on the availability replica that is located on the default server instance on a computer named *COMPUTER01*.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP MyAG MODIFY REPLICA ON 'COMPUTER01' WITH  
       (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4a4f8-144">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a4f8-144">Using PowerShell</span></span>  

### <a name="to-change-the-failover-mode-of-an-availability-replica"></a><span data-ttu-id="4a4f8-145">So ändern Sie den Failovermodus eines Verfügbarkeitsreplikats</span><span class="sxs-lookup"><span data-stu-id="4a4f8-145">To change the failover mode of an availability replica</span></span>
  
1.  <span data-ttu-id="4a4f8-146">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4a4f8-147">Verwenden Sie das `Set-SqlAvailabilityReplica`-Cmdlet mit dem `FailoverMode`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-147">Use the `Set-SqlAvailabilityReplica` cmdlet with the `FailoverMode` parameter.</span></span> <span data-ttu-id="4a4f8-148">Wenn Sie ein Replikat auf automatisches Failover festlegen, müssen Sie möglicherweise den `AvailabilityMode`-Parameter verwenden, um das Replikat in den Verfügbarkeitsmodus mit synchronem Commit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-148">When setting a replica to automatic failover, you might need to use the `AvailabilityMode` parameter to change the replica to synchronous-commit availability mode.</span></span>  
  
     <span data-ttu-id="4a4f8-149">Beispielsweise wird durch diesen Befehl das Replikat `MyReplica` in der Verfügbarkeitsgruppe `MyAg` so geändert, dass der Verfügbarkeitsmodus für synchrone Commits verwendet und automatische Failover unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-149">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\Replicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a4f8-150">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4a4f8-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4a4f8-151">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4a4f8-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="4a4f8-152">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4a4f8-152">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a4f8-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a4f8-153">See Also</span></span>  
 [<span data-ttu-id="4a4f8-154">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4a4f8-154">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="4a4f8-155">[Verfügbarkeits Modi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="4a4f8-155">[Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="4a4f8-156">Failover-und Failovermodi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="4a4f8-156">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md) 
