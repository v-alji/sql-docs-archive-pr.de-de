---
title: Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joinreplica.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
ms.assetid: e5bd2489-097a-490e-8ea1-34fe48378ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c38c2d59a46b15fc9a1dca77ae6a67e8e59e1b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617267"
---
# <a name="join-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="60fab-102">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60fab-102">Join a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="60fab-103">In diesem Thema wird beschrieben, wie ein sekundäres Replikat in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]mit [!INCLUDE[tsql](../../../includes/tsql-md.md)], [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]oder PowerShell mit einer AlwaysOn-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="60fab-103">This topic describes how to join a secondary replica to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="60fab-104">Nachdem ein sekundäres Replikat einer AlwaysOn-Verfügbarkeitsgruppe hinzugefügt wurde, muss das sekundäre Replikat mit der Verfügbarkeitsgruppe verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="60fab-104">After a secondary replica is added to an AlwaysOn availability group, the secondary replica must be joined to the availability group.</span></span> <span data-ttu-id="60fab-105">Der Joinvorgang für das Replikat muss auf der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz ausgeführt werden, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="60fab-105">The join-replica operation must be performed on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting the secondary replica.</span></span>  
  
-   <span data-ttu-id="60fab-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="60fab-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60fab-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="60fab-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="60fab-108">Security</span><span class="sxs-lookup"><span data-stu-id="60fab-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60fab-109">**So bereiten Sie eine sekundäre Datenbank vor mit:**</span><span class="sxs-lookup"><span data-stu-id="60fab-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="60fab-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60fab-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="60fab-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60fab-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="60fab-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="60fab-112">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="60fab-113">**Nachverfolgung:** [Konfigurieren von sekundären Datenbanken](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="60fab-113">**Follow Up:** [Configure Secondary Databases](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60fab-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="60fab-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="60fab-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="60fab-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="60fab-116">Das primäre Replikat der Verfügbarkeitsgruppe muss derzeit online sein.</span><span class="sxs-lookup"><span data-stu-id="60fab-116">The primary replica of the availability group must currently be online.</span></span>  
  
-   <span data-ttu-id="60fab-117">Sie müssen mit der Serverinstanz verbunden sein, die ein sekundäres Replikat hostet, das noch nicht mit der Verfügbarkeitsgruppe verknüpft wurde.</span><span class="sxs-lookup"><span data-stu-id="60fab-117">You must be connected to the server instance that hosts a secondary replica that has not yet have been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="60fab-118">Die lokale Serverinstanz muss in der Lage sein, eine Verbindung mit dem Datenbankspiegelungs-Endpunkt der Serverinstanz herzustellen, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="60fab-118">The local server instance must be able to connect to the database mirroring endpoint of the server instance that is hosting the primary replica.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="60fab-119">Sobald eine Voraussetzung nicht erfüllt ist, tritt bei dem Joinvorgang ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="60fab-119">If any prerequisite is not met, the join operation fails.</span></span> <span data-ttu-id="60fab-120">Nach einem fehlerhaften Joinversuch müssen Sie möglicherweise eine Verbindung mit der Serverinstanz herstellen, die das primäre Replikat hostet, um das sekundäre Replikat zu entfernen und erneut hinzuzufügen, bevor Sie es mit der Verfügbarkeitsgruppe verknüpfen können.</span><span class="sxs-lookup"><span data-stu-id="60fab-120">After a failed join attempt, you might need to connect to the server instance that hosts the primary replica to remove and re-add the secondary replica before you can join it to the availability group.</span></span> <span data-ttu-id="60fab-121">Weitere Informationen finden Sie unter [Entfernen eines sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) und [Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60fab-121">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60fab-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="60fab-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60fab-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="60fab-123">Permissions</span></span>  
 <span data-ttu-id="60fab-124">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="60fab-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60fab-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60fab-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="60fab-126">**So verknüpfen Sie ein Verfügbarkeitsreplikat mit einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="60fab-126">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="60fab-127">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet, und klicken Sie auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="60fab-127">In Object Explorer, connect to the server instance that hosts the secondary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="60fab-128">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="60fab-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="60fab-129">Wählen Sie die Verfügbarkeitsgruppe des sekundären Replikats aus, zu dem eine Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="60fab-129">Select the availability group of the secondary replica to which you are connected.</span></span>  
  
4.  <span data-ttu-id="60fab-130">Klicken Sie mit der rechten Maustaste auf das sekundäre Replikat, und klicken Sie auf **Verfügbarkeitsgruppe beitreten**.</span><span class="sxs-lookup"><span data-stu-id="60fab-130">Right-click the secondary replica, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="60fab-131">Das Dialogfeld **Replikat mit Verfügbarkeitsgruppe verknüpfen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="60fab-131">This opens the **Join Replica to Availability Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="60fab-132">Klicken Sie auf **OK**, um das sekundäre Replikat mit der Verfügbarkeitsgruppe zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="60fab-132">To join the secondary replica to the availability group, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60fab-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60fab-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="60fab-134">**So verknüpfen Sie ein Verfügbarkeitsreplikat mit einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="60fab-134">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="60fab-135">Stellen Sie eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="60fab-135">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="60fab-136">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="60fab-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="60fab-137">ALTER AVAILABILITY GROUP *Gruppenname* JOIN</span><span class="sxs-lookup"><span data-stu-id="60fab-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span></span>  
  
     <span data-ttu-id="60fab-138">Dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="60fab-138">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="60fab-139">Im folgenden Codebeispiel wird das sekundäre Replikat mit der `MyAG`-Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="60fab-139">The following example, joins the secondary replica to the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="60fab-140">Unter [Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) können Sie die Verwendung dieser [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung im Kontext sehen.</span><span class="sxs-lookup"><span data-stu-id="60fab-140">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="60fab-141">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="60fab-141">Using PowerShell</span></span>  
 <span data-ttu-id="60fab-142">**So verknüpfen Sie ein Verfügbarkeitsreplikat mit einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="60fab-142">**To join an availability replica to an availability group**</span></span>  
  
 <span data-ttu-id="60fab-143">Im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Anbieter:</span><span class="sxs-lookup"><span data-stu-id="60fab-143">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="60fab-144">Ändern Sie das Verzeichnis (`cd`) in die Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="60fab-144">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="60fab-145">Verknüpfen Sie das sekundäre Replikat mit der Verfügbarkeitsgruppe, indem Sie das Cmdlet **Join-SqlAvailabilityGroup** mit dem Namen der Verfügbarkeitsgruppe ausführen.</span><span class="sxs-lookup"><span data-stu-id="60fab-145">Join the secondary replica to the availability group by executing the **Join-SqlAvailabilityGroup** cmdlet with the name of the availability group.</span></span>  
  
     <span data-ttu-id="60fab-146">Beispielsweise wird ein sekundäres Replikat, das von der Serverinstanz unter dem angegebenen Pfad gehostet wird, mithilfe des folgenden Befehls mit der Verfügbarkeitsgruppe `MyAg`verknüpft.</span><span class="sxs-lookup"><span data-stu-id="60fab-146">For example, the following command joins a secondary replica hosted by the server instance located at the specified path to the availability group named `MyAg`.</span></span>  <span data-ttu-id="60fab-147">Von dieser Serverinstanz muss ein sekundäres Replikat in dieser Verfügbarkeitsgruppe gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="60fab-147">This server instance must host a secondary replica in this availability group.</span></span>  
  
    ```powershell
    Join-SqlAvailabilityGroup -Path SQLSERVER:\SQL\SecondaryServer\InstanceName -Name 'MyAg'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="60fab-148">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="60fab-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="60fab-149">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="60fab-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="60fab-150">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="60fab-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="60fab-151">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="60fab-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-configure-secondary-databases"></a><a name="FollowUp"></a><span data-ttu-id="60fab-152">Nachverfolgung: Konfigurieren von sekundären Datenbanken</span><span class="sxs-lookup"><span data-stu-id="60fab-152">Follow Up: Configure Secondary Databases</span></span>  
 <span data-ttu-id="60fab-153">Für jede Datenbank in der Verfügbarkeitsgruppe benötigen Sie eine sekundäre Datenbank auf der Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="60fab-153">For every database in the availability group, you need a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="60fab-154">Sie können sekundäre Datenbanken entweder vor oder nach dem Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe konfigurieren. Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="60fab-154">You can configure secondary databases either before or after you join a secondary replica to an availability group, as follows:</span></span>  
  
1.  <span data-ttu-id="60fab-155">Stellen Sie mit RESTORE WITH NORECOVERY für jeden Wiederherstellungsvorgang die neuesten Datenbank- und Protokollsicherungen für jede primäre Datenbank auf der Serverinstanz wieder her, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="60fab-155">Restore recent database and log backups of each primary database onto the server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="60fab-156">Weitere Informationen finden Sie unter [Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)erstellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="60fab-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="60fab-157">Verknüpfen Sie jede sekundäre Datenbank mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="60fab-157">Join each secondary database to the availability group.</span></span> <span data-ttu-id="60fab-158">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60fab-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60fab-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60fab-159">See Also</span></span>  
 <span data-ttu-id="60fab-160">[Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60fab-160">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="60fab-161">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60fab-161">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="60fab-162">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfigurations &#40;SQL Server&#41;gelöscht</span><span class="sxs-lookup"><span data-stu-id="60fab-162">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
