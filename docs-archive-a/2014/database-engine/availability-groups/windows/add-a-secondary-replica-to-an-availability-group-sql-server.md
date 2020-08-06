---
title: Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 6669dcce-85f9-495f-aadf-7f62cff4a9da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 498103a781641c72e166c6b11663f5248ae5ccfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609462"
---
# <a name="add-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="64f6d-102">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="64f6d-102">Add a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="64f6d-103">In diesem Thema wird beschrieben, wie ein sekundäres Replikat einer vorhandenen AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="64f6d-103">This topic describes how to add a secondary replica to an existing AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="64f6d-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="64f6d-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="64f6d-105">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="64f6d-105">Prerequisites and Restrictions</span></span>](#PrerequisitesRestrictions)  
  
     [<span data-ttu-id="64f6d-106">Security</span><span class="sxs-lookup"><span data-stu-id="64f6d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="64f6d-107">**Hinzufügen eines Replikats mit:**</span><span class="sxs-lookup"><span data-stu-id="64f6d-107">**To add a replica, using:**</span></span>  
  
     [<span data-ttu-id="64f6d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64f6d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="64f6d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64f6d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="64f6d-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="64f6d-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="64f6d-111">**Nachverfolgung:**  [Nach dem Hinzufügen eines sekundären Replikats](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="64f6d-111">**Follow Up:**  [After Adding a Secondary Replica](#FollowUp)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="64f6d-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="64f6d-112">Before You Begin</span></span>  
 <span data-ttu-id="64f6d-113">Es wird dringend empfohlen, dass Sie diesen Abschnitt lesen, bevor Sie versuchen, Ihre erste Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="64f6d-113">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
##  <a name="prerequisites-and-restrictions"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="64f6d-114">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="64f6d-114">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="64f6d-115">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="64f6d-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
 <span data-ttu-id="64f6d-116">Weitere Informationen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen&#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="64f6d-116">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64f6d-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="64f6d-117">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64f6d-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="64f6d-118">Permissions</span></span>  
 <span data-ttu-id="64f6d-119">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="64f6d-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="64f6d-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64f6d-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="64f6d-121">**So fügen Sie ein Replikat hinzu**</span><span class="sxs-lookup"><span data-stu-id="64f6d-121">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="64f6d-122">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="64f6d-122">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="64f6d-123">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="64f6d-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="64f6d-124">Klicken Sie mit der rechten Maustaste auf die Verfügbarkeitsgruppe, und wählen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="64f6d-124">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="64f6d-125">Wählen Sie zum Starten des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen den Befehl **Replikat hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="64f6d-125">Select the **Add Replica** command to launch the Add Replica to Availability Group Wizard.</span></span> <span data-ttu-id="64f6d-126">Weitere Informationen finden Sie unter [Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="64f6d-126">For more information, see [Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
    -   <span data-ttu-id="64f6d-127">Wählen Sie alternativ den Befehl **Eigenschaften** aus, um das Dialogfeld **Eigenschaften der Verfügbarkeitsgruppe** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="64f6d-127">Alternatively, select the **Properties** command to open the **Availability Group Properties** dialog box.</span></span> <span data-ttu-id="64f6d-128">Für das Hinzufügen eines Replikats in diesem Dialogfeld sind folgende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="64f6d-128">The steps for adding a replica in this dialog box are as follows:</span></span>  
  
        1.  <span data-ttu-id="64f6d-129">Klicken Sie im Bereich **Verfügbarkeitsreplikate** des Dialogfelds auf die Schaltfläche **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="64f6d-129">In the **Availability Replicas** pane of the dialog box, click the **Add** button.</span></span> <span data-ttu-id="64f6d-130">Dadurch wird ein Replikateintrag erstellt und ausgewählt, in dem das leere Serverinstanzfeld ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="64f6d-130">This creates and selects a replica entry in which the blank Server Instance field is selected.</span></span>  
  
        2.  <span data-ttu-id="64f6d-131">Geben Sie den Namen einer Serverinstanz ein, die die Voraussetzungen zum Hosten eines Verfügbarkeitsreplikats erfüllt.</span><span class="sxs-lookup"><span data-stu-id="64f6d-131">Enter the name of a server instance that meets the prerequisites for hosting an availability replica.</span></span>  
  
         <span data-ttu-id="64f6d-132">Wiederholen Sie zum Hinzufügen eines weiteren Replikats die vorhergehenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="64f6d-132">To add an additional replicas, repeat the preceding steps.</span></span> <span data-ttu-id="64f6d-133">Wenn Sie alle Replikate angegeben haben, klicken Sie auf **OK** , um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="64f6d-133">When you are done specifying replicas, click **OK** to complete the operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="64f6d-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64f6d-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="64f6d-135">**So fügen Sie ein Replikat hinzu**</span><span class="sxs-lookup"><span data-stu-id="64f6d-135">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="64f6d-136">Stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="64f6d-136">Connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="64f6d-137">Fügen Sie der Verfügbarkeitsgruppe das neue sekundäre Replikat mit der ADD REPLICA ON-Klausel der ALTER AVAILABILITY GROUP-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="64f6d-137">Add the new secondary replica to the availability group by using the ADD REPLICA ON clause of the ALTER AVAILABILITY GROUP statement.</span></span> <span data-ttu-id="64f6d-138">In einer ADD REPLICA ON-Klausel sind die ENDPOINT_URL-, AVAILABILITY_MODE- und FAILOVER_MODE-Optionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64f6d-138">The ENDPOINT_URL, AVAILABILITY_MODE, and FAILOVER_MODE options are required in an ADD REPLICA ON clause.</span></span> <span data-ttu-id="64f6d-139">Die anderen Replikatoptionen (BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE und SESSION_TIMEOUT) sind optional.</span><span class="sxs-lookup"><span data-stu-id="64f6d-139">The other replica options- BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE, and SESSION_TIMEOUT-are optional.</span></span> <span data-ttu-id="64f6d-140">Weitere Informationen finden Sie unter [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql)hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="64f6d-140">For more information, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="64f6d-141">Beispielsweise wird durch die folgende [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung ein neues Replikat für eine Verfügbarkeitsgruppe namens `MyAG` auf der von `COMPUTER04`gehosteten Standardserverinstanz, deren Endpunkt-URL `TCP://COMPUTER04.Adventure-Works.com:5022'`lautet, erstellt.</span><span class="sxs-lookup"><span data-stu-id="64f6d-141">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement creates a new replica to an availability group named `MyAG` on the default server instance hosted by `COMPUTER04`, whose endpoint URL is `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span></span> <span data-ttu-id="64f6d-142">Das Replikat unterstützt ein manuelles Failover und den Verfügbarkeitsmodus für asynchrone Commits.</span><span class="sxs-lookup"><span data-stu-id="64f6d-142">This replica supports manual failover and asynchronous-commit availability mode.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG ADD REPLICA ON 'COMPUTER04'   
       WITH (  
             ENDPOINT_URL = 'TCP://COMPUTER04.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="64f6d-143">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="64f6d-143">Using PowerShell</span></span>  
 <span data-ttu-id="64f6d-144">**So fügen Sie ein Replikat hinzu**</span><span class="sxs-lookup"><span data-stu-id="64f6d-144">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="64f6d-145">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="64f6d-145">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="64f6d-146">Verwenden Sie das **New-SqlAvailabilityReplica** -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="64f6d-146">Use the **New-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="64f6d-147">Beispielsweise wird mit dem folgenden Befehl einer vorhandenen Verfügbarkeitsgruppe namens `MyAg`ein Verfügbarkeitsreplikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64f6d-147">For example, the following command adds an availability replica to an existing availability group named `MyAg`.</span></span> <span data-ttu-id="64f6d-148">Das Replikat unterstützt ein manuelles Failover und den Verfügbarkeitsmodus für asynchrone Commits.</span><span class="sxs-lookup"><span data-stu-id="64f6d-148">This replica supports manual failover and asynchronous-commit availability mode.</span></span> <span data-ttu-id="64f6d-149">In der sekundären Rolle unterstützt dieses Replikat Verbindungen mit Lesezugriff, sodass Sie die schreibgeschützte Verarbeitung auf dieses Replikat auslagern können.</span><span class="sxs-lookup"><span data-stu-id="64f6d-149">In the secondary role, this replica will support read access connections, allowing you to offload read-only processing to this replica.</span></span>  
  
    ```powershell
    $agPath = "SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
    $endpointURL = "TCP://PrimaryServerName.domain.com:5022"  
    $failoverMode = "Manual"  
    $availabilityMode = "AsynchronousCommit"  
    $secondaryReadMode = "AllowAllConnections"  
  
    New-SqlAvailabilityReplica -Name SecondaryServer\Instance `   
    -EndpointUrl $endpointURL `   
    -FailoverMode $failoverMode `   
    -AvailabilityMode $availabilityMode `   
    -ConnectionModeInSecondaryRole $secondaryReadMode `   
    -Path $agPath  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="64f6d-150">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="64f6d-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="64f6d-151">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="64f6d-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="64f6d-152">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="64f6d-152">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="64f6d-153">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="64f6d-153">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-adding-a-secondary-replica"></a><a name="FollowUp"></a><span data-ttu-id="64f6d-154">Nachverfolgung: nach Hinzufügen eines sekundären Replikats</span><span class="sxs-lookup"><span data-stu-id="64f6d-154">Follow Up: After Adding a Secondary Replica</span></span>  
 <span data-ttu-id="64f6d-155">Zum Hinzufügen eines Replikats für eine vorhandene Verfügbarkeitsgruppe müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="64f6d-155">To add a replica for an existing availability group, you must perform the following steps:</span></span>  
  
1.  <span data-ttu-id="64f6d-156">Stellen Sie eine Verbindung mit der Serverinstanz her, die das neue sekundäre Replikat hosten wird.</span><span class="sxs-lookup"><span data-stu-id="64f6d-156">Connect to the server instance that is going to host the new secondary replica.</span></span>  
  
2.  <span data-ttu-id="64f6d-157">Verknüpfen Sie das neue sekundäre Replikat mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="64f6d-157">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="64f6d-158">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="64f6d-158">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="64f6d-159">Erstellen Sie für jede Datenbank in der Verfügbarkeitsgruppe eine sekundäre Datenbank auf der Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="64f6d-159">For each database in the availability group, create a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="64f6d-160">Weitere Informationen finden Sie unter [Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)erstellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="64f6d-160">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="64f6d-161">Verknüpfen Sie alle neuen sekundären Datenbanken mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="64f6d-161">Join each of the new secondary databases to the availability group.</span></span> <span data-ttu-id="64f6d-162">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="64f6d-162">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="64f6d-163">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="64f6d-163">Related Tasks</span></span>  
 <span data-ttu-id="64f6d-164">**So verwalten Sie ein Verfügbarkeitsreplikat**</span><span class="sxs-lookup"><span data-stu-id="64f6d-164">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="64f6d-165">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-165">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="64f6d-166">Entfernen einer sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-166">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="64f6d-167">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-167">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="64f6d-168">Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-168">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="64f6d-169">Ändern des Failovermodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-169">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="64f6d-170">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-170">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="64f6d-171">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-171">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="64f6d-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64f6d-172">See Also</span></span>  
 <span data-ttu-id="64f6d-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="64f6d-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="64f6d-174">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="64f6d-174">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="64f6d-175">[Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="64f6d-175">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="64f6d-176">[Verwenden Sie das AlwaysOn-Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="64f6d-176">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="64f6d-177">Überwachen von Verfügbarkeitsgruppen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64f6d-177">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
