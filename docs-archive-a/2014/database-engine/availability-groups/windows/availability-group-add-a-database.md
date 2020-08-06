---
title: Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0907cf711cac65ad77a8948841d92705fdc1eac9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608881"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a><span data-ttu-id="7eb1c-102">Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7eb1c-102">Add a Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="7eb1c-103">In diesem Thema wird beschrieben, wie einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]eine Datenbank hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-103">This topic describes how to add a database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="7eb1c-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7eb1c-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7eb1c-105">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7eb1c-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="7eb1c-106">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7eb1c-106">Permissions</span></span>](#Permissions)  
  
-   <span data-ttu-id="7eb1c-107">**Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe mit:**</span><span class="sxs-lookup"><span data-stu-id="7eb1c-107">**To add a database to an availability group, using:**</span></span>  
  
     [<span data-ttu-id="7eb1c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7eb1c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7eb1c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7eb1c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="7eb1c-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eb1c-110">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7eb1c-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7eb1c-111">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="7eb1c-112">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7eb1c-112">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="7eb1c-113">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-113">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="7eb1c-114">Die Datenbank muss sich auf der Serverinstanz befinden, die das primäre Replikat hostet, und die Voraussetzungen und Einschränkungen für Verfügbarkeitsdatenbanken erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-114">The database must reside on the server instance that hosts the primary replica and comply with the prerequisites and restrictions for availability databases.</span></span> <span data-ttu-id="7eb1c-115">Weitere Informationen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen&#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-115">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7eb1c-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7eb1c-116">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7eb1c-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7eb1c-117">Permissions</span></span>  
 <span data-ttu-id="7eb1c-118">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7eb1c-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7eb1c-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7eb1c-120">**So fügen sie einer Verfügbarkeitsgruppe eine Datenbank hinzu**</span><span class="sxs-lookup"><span data-stu-id="7eb1c-120">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="7eb1c-121">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-121">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7eb1c-122">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="7eb1c-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="7eb1c-123">Klicken Sie mit der rechten Maustaste auf die Verfügbarkeitsgruppe, und wählen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="7eb1c-123">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="7eb1c-124">Wählen Sie zum Starten des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen den Befehl **Datenbank hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-124">To launch the Add Database to Availability Group Wizard, select the **Add Database** command.</span></span> <span data-ttu-id="7eb1c-125">Weitere Informationen finden Sie unter [Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-125">For more information, see [Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span></span>  
  
    -   <span data-ttu-id="7eb1c-126">Wählen Sie den Befehl **Eigenschaften** aus, um mindestens eine Datenbank durch Angabe im Dialogfeld für die \*\* Eigenschaften der Verfügbarkeitsgruppe \*\* hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-126">To add one or more databases by specifying them in the **Availability Group Properties** dialog box, select the **Properties** command.</span></span> <span data-ttu-id="7eb1c-127">Folgende Schritte sind zum Hinzufügen einer Datenbank erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7eb1c-127">The steps for adding a database are as follows:</span></span>  
  
        1.  <span data-ttu-id="7eb1c-128">Klicken Sie im Bereich **Verfügbarkeitsdatenbanken** auf die Schaltfläche **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="7eb1c-128">In the **Availability Databases** pane, click the **Add** button.</span></span> <span data-ttu-id="7eb1c-129">Dadurch wird ein leeres Datenbankfeld erstellt und ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-129">This creates and selects a blank database field.</span></span>  
  
        2.  <span data-ttu-id="7eb1c-130">Geben Sie den Namen einer Datenbank ein, die die Voraussetzungen der Verfügbarkeitsdatenbanken erfüllt.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-130">Enter the name of a database that meets the availability-databases prerequisites.</span></span>  
  
         <span data-ttu-id="7eb1c-131">Wiederholen Sie zum Hinzufügen einer weiteren Datenbank die vorhergehenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-131">To add another database, repeat the preceding steps.</span></span> <span data-ttu-id="7eb1c-132">Wenn Sie alle Datenbanken angegeben haben, klicken Sie auf **OK** , um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-132">When you are done specifying databases, click **OK** to complete the operation.</span></span>  
  
         <span data-ttu-id="7eb1c-133">Nachdem Sie das Kontrollkästchen **Eigenschaften der Verfügbarkeitsgruppe** aktiviert haben, um einer Verfügbarkeitsgruppe eine Datenbank hinzuzufügen, müssen Sie die zugehörige zweite Datenbank auf jeder Serverinstanz konfigurieren, auf der das sekundäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-133">After you use the **Availability Group Properties** dialog box to add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="7eb1c-134">Weitere Informationen finden Sie unter [Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-134">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7eb1c-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7eb1c-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="7eb1c-136">**So fügen sie einer Verfügbarkeitsgruppe eine Datenbank hinzu**</span><span class="sxs-lookup"><span data-stu-id="7eb1c-136">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="7eb1c-137">Stellen Sie eine Verbindung mit der Serverinstanz her, die die Serverinstanz mit dem primären Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-137">Connect to the server instance that hosts the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="7eb1c-138">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7eb1c-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="7eb1c-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="7eb1c-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span></span>  
  
     <span data-ttu-id="7eb1c-140">Dabei ist *group_name* der Name der Verfügbarkeitsgruppe und *database_name* der Name einer zur Gruppe hinzuzufügenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-140">where *group_name* is the name of the availability group and *database_name* is the name of a database to be added to the group.</span></span>  
  
     <span data-ttu-id="7eb1c-141">Im folgenden Beispiel wird die Datenbank *MyDb3* zur Verfügbarkeitsgruppe *MyAG* hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-141">The following example adds the *MyDb3* database to the *MyAG* availability group.</span></span>  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  <span data-ttu-id="7eb1c-142">Nachdem Sie einer Verfügbarkeitsgruppe eine Datenbank hinzugefügt haben, müssen Sie die zugehörige zweite Datenbank auf jeder Serverinstanz konfigurieren, auf der das sekundäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-142">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="7eb1c-143">Weitere Informationen finden Sie unter [Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-143">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="7eb1c-144">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eb1c-144">Using PowerShell</span></span>  
 <span data-ttu-id="7eb1c-145">**So fügen sie einer Verfügbarkeitsgruppe eine Datenbank hinzu**</span><span class="sxs-lookup"><span data-stu-id="7eb1c-145">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="7eb1c-146">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="7eb1c-147">Verwenden Sie das `Add-SqlAvailabilityDatabase`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-147">Use the `Add-SqlAvailabilityDatabase` cmdlet.</span></span>  
  
     <span data-ttu-id="7eb1c-148">Beispielsweise wird mit dem folgenden Befehl die sekundäre Datenbank `MyDd` der `MyAG` -Verfügbarkeitsgruppe hinzugefügt, deren primäres Replikat von `PrimaryServer\InstanceName`gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-148">For example, the following command adds the secondary database `MyDd` to the `MyAG` availability group, whose primary replica is hosted by `PrimaryServer\InstanceName`.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase `   
     -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
     -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7eb1c-149">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="7eb1c-150">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
3.  <span data-ttu-id="7eb1c-151">Nachdem Sie einer Verfügbarkeitsgruppe eine Datenbank hinzugefügt haben, müssen Sie die zugehörige zweite Datenbank auf jeder Serverinstanz konfigurieren, auf der das sekundäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-151">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="7eb1c-152">Weitere Informationen finden Sie unter [Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-152">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="7eb1c-153">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1c-153">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>

 <span data-ttu-id="7eb1c-154">Im folgenden Beispiel wird der vollständige Vorbereitungsprozess veranschaulicht: Eine sekundäre Datenbank wird von einer Datenbank auf der Serverinstanz, von der das primäre Replikat einer Verfügbarkeitsgruppe gehostet wird, vorbereitet. Anschließend wird die Datenbank einer Verfügbarkeitsgruppe (als primäre Datenbank) hinzugefügt, und dann wird die sekundäre Datenbank mit der Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-154">The following example shows the full process for preparing a secondary database from a database on the server instance that hosts the primary replica of an availability group, adding the database to an availability group (as a primary database), and then joining the secondary database to the availability group.</span></span> <span data-ttu-id="7eb1c-155">Zunächst werden die Datenbank und das zugehörige Transaktionsprotokoll gesichert.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-155">First, the example backs up the database and its transaction log.</span></span> <span data-ttu-id="7eb1c-156">Anschließend werden die Datenbank- und Protokollsicherungen in den Serverinstanzen wiederhergestellt, von denen ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-156">Then the example restores the database and log backups to the server instances that host a secondary replica.</span></span>  
  
 <span data-ttu-id="7eb1c-157">`Add-SqlAvailabilityDatabase` wird im Beispiel zweimal aufgerufen: zuerst für das primäre Replikat, um die Datenbank der Verfügbarkeitsgruppe hinzuzufügen, und anschließend für das sekundäre Replikat, um die sekundäre Datenbank auf diesem Replikat mit der Verfügbarkeitsgruppe zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-157">The example calls `Add-SqlAvailabilityDatabase` twice: first on the primary replica to add the database to the availability group, and then on the secondary replica to join the secondary database on that replica to the availability group.</span></span> <span data-ttu-id="7eb1c-158">Wenn Sie über mehr als ein sekundäres Replikat verfügen, muss die sekundäre Datenbank auf jedem einzelnen Replikat wiederhergestellt und verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="7eb1c-158">If you have more than one secondary replica, restore and join the secondary database on each of them.</span></span>  
  
```powershell
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"
```  
  
## <a name="see-also"></a><span data-ttu-id="7eb1c-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eb1c-159">See Also</span></span>  
 <span data-ttu-id="7eb1c-160">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7eb1c-160">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7eb1c-161">[Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7eb1c-161">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7eb1c-162">[Verwenden Sie das AlwaysOn-Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7eb1c-162">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="7eb1c-163">Überwachen von Verfügbarkeitsgruppen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7eb1c-163">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
