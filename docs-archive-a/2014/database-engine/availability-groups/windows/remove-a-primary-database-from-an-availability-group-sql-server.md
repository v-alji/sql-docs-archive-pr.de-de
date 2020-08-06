---
title: Entfernen einer primären Datenbank aus einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeprimarydb.f1
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 6d4ca31e-ddf0-44bf-be5e-a5da060bf096
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6fafaf6464431d68f8cfdf9dc9d8fa844a42a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615605"
---
# <a name="remove-a-primary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="2ca99-102">Entfernen einer primären Datenbank aus einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2ca99-102">Remove a Primary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="2ca99-103">In diesem Thema wird erläutert, wie sowohl die primäre Datenbank als auch die entsprechenden sekundären Datenbanken aus einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca99-103">This topic describes how to remove both the primary database and the corresponding secondary database(s) from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="2ca99-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="2ca99-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2ca99-105">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2ca99-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="2ca99-106">Security</span><span class="sxs-lookup"><span data-stu-id="2ca99-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2ca99-107">**Entfernen einer Verfügbarkeitsdatenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="2ca99-107">**To remove an availability database, using:**</span></span>  
  
     [<span data-ttu-id="2ca99-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ca99-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2ca99-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ca99-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="2ca99-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ca99-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="2ca99-111">**Nachverfolgung:**  [Nach dem Entfernen einer Verfügbarkeitsdatenbank aus einer Verfügbarkeitsgruppe](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2ca99-111">**Follow Up:**  [After Removing an Availability Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2ca99-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2ca99-112">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="2ca99-113">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2ca99-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="2ca99-114">Dieser Task wird nur für primäre Replikate unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ca99-114">This task is supported only on primary replicas.</span></span> <span data-ttu-id="2ca99-115">Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="2ca99-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2ca99-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2ca99-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2ca99-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2ca99-117">Permissions</span></span>  
 <span data-ttu-id="2ca99-118">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="2ca99-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2ca99-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ca99-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2ca99-120">**So entfernen Sie eine Verfügbarkeitsdatenbank**</span><span class="sxs-lookup"><span data-stu-id="2ca99-120">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="2ca99-121">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Replikat der zu entfernenden Datenbanken hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="2ca99-121">In Object Explorer, connect to the server instance that hosts the primary replica of the database or databases to be removed, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2ca99-122">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="2ca99-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="2ca99-123">Wählen Sie die Verfügbarkeitsgruppe aus, und erweitern Sie den Knoten **Verfügbarkeitsdatenbanken** .</span><span class="sxs-lookup"><span data-stu-id="2ca99-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="2ca99-124">Dieser Schritt hängt davon ab, ob Sie mehrere Datenbankgruppen oder nur eine Datenbank entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="2ca99-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="2ca99-125">Verwenden Sie zum Entfernen mehrerer Datenbanken den Bereich **Details zum Objekt-Explorer** , um alle zu entfernenden Datenbanken anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2ca99-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="2ca99-126">Weitere Informationen finden Sie unter [Verwenden der Details zum Objekt-Explorer zum Überwachen von Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="2ca99-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="2ca99-127">Wählen Sie zum Entfernen einer einzelnen Datenbank diese im Bereich **Objekt-Explorer** oder **Details zum Objekt-Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="2ca99-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="2ca99-128">Klicken Sie mit der rechten Maustaste auf die ausgewählten Datenbanken, und wählen Sie im Kontextmenü den Befehl **Datenbank aus Verfügbarkeitsgruppe entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="2ca99-128">Right-click the selected database or databases, and select **Remove Database from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="2ca99-129">Klicken Sie zum Entfernen aller aufgelisteten Datenbanken im Dialogfeld **Datenbanken aus Verfügbarkeitsgruppe entfernen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca99-129">In the **Remove Databases from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="2ca99-130">Wenn Sie nicht alle Datenbanken entfernen wollen, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="2ca99-130">If you do not want to remove all them, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2ca99-131">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ca99-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="2ca99-132">**So entfernen Sie eine Verfügbarkeitsdatenbank**</span><span class="sxs-lookup"><span data-stu-id="2ca99-132">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="2ca99-133">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="2ca99-133">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="2ca99-134">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2ca99-134">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="2ca99-135">ALTER AVAILABILITY GROUP *Gruppenname* REMOVE DATABASE *Verfügbarkeitsdatenbankname*</span><span class="sxs-lookup"><span data-stu-id="2ca99-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span></span>  
  
     <span data-ttu-id="2ca99-136">Dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe und *Verfügbarkeitsdatenbankname* der Name der zu entfernenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2ca99-136">where *group_name* is the name of the availability group and *database_name* is the name of the database to be removed.</span></span>  
  
     <span data-ttu-id="2ca99-137">Im folgenden Beispiel wird eine Datenbank namens `Db6` aus der `MyAG` -Verfügbarkeitsgruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="2ca99-137">The following example removes a databases named `Db6` from the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE DATABASE Db6;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="2ca99-138">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ca99-138">Using PowerShell</span></span>  
 <span data-ttu-id="2ca99-139">**So entfernen Sie eine Verfügbarkeitsdatenbank**</span><span class="sxs-lookup"><span data-stu-id="2ca99-139">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="2ca99-140">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="2ca99-140">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="2ca99-141">Verwenden Sie das `Remove-SqlAvailabilityDatabase`-Cmdlet, und geben Sie dabei den Namen der Verfügbarkeitsdatenbank an, die aus der Verfügbarkeitsgruppe entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2ca99-141">Use the `Remove-SqlAvailabilityDatabase` cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="2ca99-142">Wenn Sie mit der Serverinstanz verbunden sind, die das primäre Replikat hostet, werden die primäre Datenbank und ihre entsprechenden sekundären Datenbanken aus der Verfügbarkeitsgruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="2ca99-142">When you are connected to the server instance that hosts the primary replica, the primary database and its corresponding secondary databases are all removed from the availability group.</span></span>  
  
     <span data-ttu-id="2ca99-143">Beispielsweise wird durch den folgenden Befehl das Verfügbarkeitsdatenbank `MyDb9` von der Verfügbarkeitsgruppe namens `MyAg`entfernt.</span><span class="sxs-lookup"><span data-stu-id="2ca99-143">For example, the following command removes the availability database `MyDb9` from the availability group named `MyAg`.</span></span> <span data-ttu-id="2ca99-144">Da der Befehl auf der Serverinstanz ausgeführt wird, von der das primäre Replikat gehostet wird, werden die primäre Datenbank und alle entsprechenden sekundären Datenbanken aus der Verfügbarkeitsgruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="2ca99-144">Because the command is executed on the server instance that hosts the primary replica, the primary database and all its corresponding secondary databases are removed from the availability group.</span></span> <span data-ttu-id="2ca99-145">Für diese Datenbank wird auf allen sekundären Replikaten keine Datensynchronisierung mehr ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ca99-145">Data synchronization will no longer occur for this database on any secondary replica.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\PrimaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb9  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ca99-146">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="2ca99-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="2ca99-147">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2ca99-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="2ca99-148">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="2ca99-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="2ca99-149">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2ca99-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-an-availability-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="2ca99-150">Nachverfolgung: nach dem Entfernen einer Verfügbarkeits Datenbank aus einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="2ca99-150">Follow Up: After Removing an Availability Database from an Availability Group</span></span>  
 <span data-ttu-id="2ca99-151">Durch das Entfernen einer Verfügbarkeitsdatenbank aus ihrer Verfügbarkeitsgruppe wird die Datensynchronisierung zwischen der früheren primären Datenbank und den entsprechenden sekundären Datenbanken beendet.</span><span class="sxs-lookup"><span data-stu-id="2ca99-151">Removing an availability database from its availability group ends data synchronization between the former primary database and the corresponding secondary databases.</span></span> <span data-ttu-id="2ca99-152">Die frühere primäre Datenbank bleibt online.</span><span class="sxs-lookup"><span data-stu-id="2ca99-152">The former primary database remains online.</span></span> <span data-ttu-id="2ca99-153">Alle entsprechenden sekundären Datenbanken wechseln in den Status RESTORING.</span><span class="sxs-lookup"><span data-stu-id="2ca99-153">Every corresponding secondary database is placed in the RESTORING state.</span></span>  
  
 <span data-ttu-id="2ca99-154">Zu diesem Zeitpunkt stehen alternative Methoden zum Umgang mit einer entfernten sekundären Datenbank zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="2ca99-154">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="2ca99-155">Wenn eine bestimmte sekundäre Datenbank nicht mehr benötigt wird, können Sie sie löschen.</span><span class="sxs-lookup"><span data-stu-id="2ca99-155">If you no longer need a given secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="2ca99-156">Weitere Informationen finden Sie unter [Löschen einer Datenbank](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="2ca99-156">For more information, see [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="2ca99-157">Wenn Sie auf eine entfernte sekundäre Datenbank zugreifen möchten, nachdem sie aus der Verfügbarkeitsgruppe entfernt wurde, können Sie die Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="2ca99-157">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="2ca99-158">Wenn Sie jedoch eine entfernte sekundäre Datenbank wiederherstellen, sind zwei voneinander abweichende, unabhängige Datenbanken mit demselben Namen online.</span><span class="sxs-lookup"><span data-stu-id="2ca99-158">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="2ca99-159">Sie müssen sicherstellen, dass Clients nur auf eine von beiden zugreifen können (in der Regel die aktuelle primäre Datenbank).</span><span class="sxs-lookup"><span data-stu-id="2ca99-159">You must make sure that clients can access only one of them, typically the most recent primary database.</span></span>  
  
     <span data-ttu-id="2ca99-160">Weitere Informationen finden Sie unter [Wiederherstellen einer Datenbank ohne Wiederherstellung von Daten &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2ca99-160">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca99-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ca99-161">See Also</span></span>  
 <span data-ttu-id="2ca99-162">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2ca99-162">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="2ca99-163">Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2ca99-163">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
