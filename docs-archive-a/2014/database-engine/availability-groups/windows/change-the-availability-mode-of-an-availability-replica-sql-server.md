---
title: Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], availability modes
ms.assetid: c4da8f25-fb1b-45a4-8bf2-195df6df634c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1636f3ea86e083e47276423b120dbc8d3744d387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725009"
---
# <a name="change-the-availability-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="8dbe8-102">Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8dbe8-102">Change the Availability Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="8dbe8-103">In diesem Thema wird beschrieben, wie der Verfügbarkeitsmodus eines Verfügbarkeitsreplikats in einer AlwaysOn-Verfügbarkeitsgruppe in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-103">This topic describes how to change the availability mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="8dbe8-104">Der Verfügbarkeitsmodus ist eine Replikateigenschaft, die steuert, ob das Replikat einen asynchronen oder synchronen Commit ausführt.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-104">The availability mode is a replica property that controls the whether the replica commits asynchronously or synchronously.</span></span> <span data-ttu-id="8dbe8-105">Der*asynchrone Commitmodus* maximiert die Leistung auf Kosten der Hochverfügbarkeit und unterstützt nur erzwungene manuelle Failovervorgänge (mit möglichem Datenverlust), in der Regel *erzwungenes Failover*genannt.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-105">*Asynchronous-commit mode* maximizes performance at the expense of high availability and supports only forced manual failover (with possible data loss), typically called *forced failover*.</span></span> <span data-ttu-id="8dbe8-106">Der*synchrone Commitmodus* bevorzugt Hochverfügbarkeit gegenüber Leistung und unterstützt, sobald das sekundäre Replikat synchronisiert ist, manuelle Failovervorgänge und optional automatische Failovervorgänge.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-106">*Synchronous-commit mode* emphasizes high availability over performance and, once the secondary replica is synchronized, supports manual failover and, optionally, automatic failover.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8dbe8-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8dbe8-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8dbe8-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8dbe8-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="8dbe8-109">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8dbe8-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8dbe8-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8dbe8-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8dbe8-111">Permissions</span></span>  
 <span data-ttu-id="8dbe8-112">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-112">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8dbe8-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8dbe8-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8dbe8-114">**So ändern Sie den Verfügbarkeitsmodus einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="8dbe8-114">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="8dbe8-115">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-115">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8dbe8-116">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="8dbe8-116">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="8dbe8-117">Klicken Sie auf die Verfügbarkeitsgruppe, deren Replikat geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-117">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="8dbe8-118">Klicken Sie mit der rechten Maustaste auf das Replikat, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-118">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8dbe8-119">Verwenden Sie im Dialogfeld **Eigenschaften des Verfügbarkeitsreplikats** die Dropdownliste **Verfügbarkeitsmodus** , um den Verfügbarkeitsmodus für dieses Replikat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-119">In the **Availability Replica Properties** dialog box, use the **Availability mode** drop list to change the availability mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8dbe8-120">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8dbe8-120">Using Transact-SQL</span></span>  
 <span data-ttu-id="8dbe8-121">**So ändern Sie den Verfügbarkeitsmodus einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="8dbe8-121">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="8dbe8-122">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-122">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="8dbe8-123">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8dbe8-123">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="8dbe8-124">ALTER AVAILABILITY GROUP *Gruppenname* MODIFY REPLICA ON '*Servername*'</span><span class="sxs-lookup"><span data-stu-id="8dbe8-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="8dbe8-125">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="8dbe8-125">WITH ( {</span></span>  
  
     <span data-ttu-id="8dbe8-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="8dbe8-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="8dbe8-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="8dbe8-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="8dbe8-128">} )</span><span class="sxs-lookup"><span data-stu-id="8dbe8-128">} )</span></span>  
  
     <span data-ttu-id="8dbe8-129">Dabei ist *group_name* der Name der Verfügbarkeits Gruppe und *server_name* der Name der Serverinstanz, auf der das zu ändernde Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-129">where *group_name* is the name of the availability group and *server_name* is the name of the server instance that hosts the replica to be modified.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dbe8-130">FAILOVER_MODE = AUTOMATIC wird nur unterstützt, wenn Sie auch AVAILABILITY_MODE = SYNCHRONOUS_COMMIT angeben.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-130">FAILOVER_MODE = AUTOMATIC is supported only if you also specify AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span></span>  
  
     <span data-ttu-id="8dbe8-131">Im folgenden, für das primäre Replikat der `AccountsAG` -Verfügbarkeitsgruppe eingegebenen Beispiel werden der Verfügbarkeitsmodus und der Failovermodus für das von der `INSTANCE09` -Serverinstanz gehostete Replikat in den Modus für synchrone Commits bzw. automatisches Failover geändert.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-131">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the availability and failover modes to synchronous commit and automatic failover, respectively, for the replica hosted by the `INSTANCE09` server instance.</span></span>  
  
    ```  
  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="8dbe8-132">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dbe8-132">Using PowerShell</span></span>

### <a name="to-change-the-availability-mode-of-an-availability-group"></a><span data-ttu-id="8dbe8-133">So ändern Sie den Verfügbarkeitsmodus einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="8dbe8-133">To change the availability mode of an availability group</span></span>
  
1.  <span data-ttu-id="8dbe8-134">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-134">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="8dbe8-135">Verwenden Sie das `Set-SqlAvailabilityReplica`-Cmdlet mit dem `AvailabilityMode`-Parameter und optional dem `FailoverMode`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-135">Use the `Set-SqlAvailabilityReplica` cmdlet with the `AvailabilityMode` parameter and, optionally, the `FailoverMode` parameter.</span></span>  
  
     <span data-ttu-id="8dbe8-136">Beispielsweise wird durch diesen Befehl das Replikat `MyReplica` in der Verfügbarkeitsgruppe `MyAg` so geändert, dass der Verfügbarkeitsmodus für synchrone Commits verwendet und automatische Failover unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-136">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `   
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dbe8-137">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="8dbe8-137">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="8dbe8-138">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8dbe8-138">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="8dbe8-139">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="8dbe8-139">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8dbe8-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8dbe8-140">See Also</span></span>  
 <span data-ttu-id="8dbe8-141">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8dbe8-141">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="8dbe8-142">[Verfügbarkeits Modi (AlwaysOn-Verfügbarkeitsgruppen)](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="8dbe8-142">[Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="8dbe8-143">Failover-und Failovermodi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="8dbe8-143">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md)  
