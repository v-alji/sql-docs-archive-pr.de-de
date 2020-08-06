---
title: Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c3de0afd73b46ae5594d26d1763f5bd78483efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615603"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="69637-102">Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="69637-102">Remove a Secondary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="69637-103">In diesem Thema wird beschrieben, wie eine sekundäre Datenbank aus einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="69637-103">This topic describes how to remove a secondary database from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="69637-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="69637-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="69637-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="69637-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="69637-106">Security</span><span class="sxs-lookup"><span data-stu-id="69637-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="69637-107">**So entfernen Sie eine sekundäre Datenbank mit**</span><span class="sxs-lookup"><span data-stu-id="69637-107">**To remove a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="69637-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69637-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="69637-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69637-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="69637-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="69637-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="69637-111">**Nachverfolgung:**  [Nach dem Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="69637-111">**Follow Up:**  [After Removing a Secondary Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="69637-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="69637-112">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>   
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="69637-113">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="69637-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="69637-114">Dieser Task wird nur für sekundäre Replikate unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69637-114">This task is supported only on secondary replicas.</span></span> <span data-ttu-id="69637-115">Sie müssen mit der Serverinstanz verbunden sein, auf der das sekundäre Replikat gehostet wird, aus dem die Datenbank entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="69637-115">You must be connected to the server instance that hosts the secondary replica from which the database is to be removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="69637-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="69637-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="69637-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="69637-117">Permissions</span></span>  
 <span data-ttu-id="69637-118">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="69637-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69637-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69637-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="69637-120">**So entfernen Sie eine sekundäre Datenbank aus einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="69637-120">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="69637-121">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, auf der das sekundäre Replikat gehostet wird, aus dem Sie mindestens eine sekundäre Datenbanken entfernen möchten, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="69637-121">In Object Explorer, connect to the server instance that hosts the secondary replica from which you want to remove one or more secondary databases, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="69637-122">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="69637-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="69637-123">Wählen Sie die Verfügbarkeitsgruppe aus, und erweitern Sie den Knoten **Verfügbarkeitsdatenbanken** .</span><span class="sxs-lookup"><span data-stu-id="69637-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="69637-124">Dieser Schritt hängt davon ab, ob Sie mehrere Datenbankgruppen oder nur eine Datenbank entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="69637-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="69637-125">Verwenden Sie zum Entfernen mehrerer Datenbanken den Bereich **Details zum Objekt-Explorer** , um alle zu entfernenden Datenbanken anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="69637-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="69637-126">Weitere Informationen finden Sie unter [Verwenden der Details zum Objekt-Explorer zum Überwachen von Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="69637-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="69637-127">Wählen Sie zum Entfernen einer einzelnen Datenbank diese im Bereich **Objekt-Explorer** oder **Details zum Objekt-Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="69637-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="69637-128">Klicken Sie mit der rechten Maustaste auf die ausgewählten Datenbanken, und wählen Sie im Befehlsmenü **Sekundäre Datenbank entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="69637-128">Right-click the selected database or databases, and select **Remove Secondary Database** in the command menu.</span></span>  
  
6.  <span data-ttu-id="69637-129">Klicken Sie zum Entfernen aller aufgelisteten Datenbanken im Dialogfeld **Datenbank aus Verfügbarkeitsgruppe entfernen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69637-129">In the **Remove Database from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="69637-130">Wenn Sie nicht alle aufgelisteten Datenbanken entfernen wollen, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="69637-130">If you do not want to remove all the listed databases, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="69637-131">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69637-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="69637-132">**So entfernen Sie eine sekundäre Datenbank aus einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="69637-132">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="69637-133">Stellen Sie eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="69637-133">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="69637-134">Verwenden Sie die [SET HADR-Klausel der ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="69637-134">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="69637-135">ALTER DATABASE *Name der Datenbank* SET HADR OFF</span><span class="sxs-lookup"><span data-stu-id="69637-135">ALTER DATABASE *database_name* SET HADR OFF</span></span>  
  
     <span data-ttu-id="69637-136">Dabei steht *Name der Datenbank* für den Namen einer sekundären Datenbank, die aus der Verfügbarkeitsgruppe entfernt werden soll, zu der sie gehört.</span><span class="sxs-lookup"><span data-stu-id="69637-136">where *database_name* is the name of a secondary database to be removed from the availability group to which it belongs.</span></span>  
  
     <span data-ttu-id="69637-137">Im folgenden Beispiel wird die sekundäre Datenbank *MyDb2* aus ihrer Verfügbarkeitsgruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="69637-137">The following example removes the local secondary database *MyDb2* from its availability group.</span></span>  
  
    ```sql
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="69637-138">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="69637-138">Using PowerShell</span></span>  
 <span data-ttu-id="69637-139">**So entfernen Sie eine sekundäre Datenbank aus einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="69637-139">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="69637-140">Ändern Sie das Verzeichnis (`cd`) in die Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="69637-140">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="69637-141">Verwenden Sie das **Remove-SqlAvailabilityDatabase** -Cmdlet, und geben Sie dabei den Namen der Verfügbarkeitsdatenbank an, die aus der Verfügbarkeitsgruppe entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="69637-141">Use the **Remove-SqlAvailabilityDatabase** cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="69637-142">Wenn Sie mit einer Serverinstanz verbunden sind, auf der ein sekundäres Replikat gehostet wird, wird nur die lokale sekundäre Datenbank aus der Verfügbarkeitsgruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="69637-142">When you are connected to a server instance that hosts a secondary replica, only the local secondary database is removed from the availability group.</span></span>  
  
     <span data-ttu-id="69637-143">Beispielsweise wird durch den folgenden Befehl die sekundäre Datenbank `MyDb8` aus dem sekundären Replikat entfernt, das von der Serverinstanz `SecondaryComputer\Instance`gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="69637-143">For example, the following command removes the secondary database `MyDb8` from the secondary replica hosted by the server instance named `SecondaryComputer\Instance`.</span></span> <span data-ttu-id="69637-144">Die Daten der entfernten sekundären Datenbanken werden nicht mehr synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="69637-144">Data synchronization to the removed secondary databases ceases.</span></span> <span data-ttu-id="69637-145">Dieser Befehl wirkt sich nicht auf die primäre Datenbank oder andere sekundäre Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="69637-145">This command does not affect the primary database or any other secondary databases.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="69637-146">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="69637-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="69637-147">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="69637-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="69637-148">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="69637-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="69637-149">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="69637-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="69637-150">Nachverfolgung: nach dem Entfernen einer sekundären Datenbank aus einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="69637-150">Follow Up: After Removing a Secondary Database from an Availability Group</span></span>  
 <span data-ttu-id="69637-151">Wenn eine sekundäre Datenbank entfernt wird, wird sie nicht mehr der Verfügbarkeitsgruppe hinzugefügt, und alle Informationen zur entfernten sekundären Datenbank werden von der Verfügbarkeitsgruppe verworfen.</span><span class="sxs-lookup"><span data-stu-id="69637-151">When a secondary database is removed, it is no longer joined to the availability group and all information about the removed secondary database is discarded by the availability group.</span></span> <span data-ttu-id="69637-152">Die entfernte sekundäre Datenbank wechselt in den Status RESTORING.</span><span class="sxs-lookup"><span data-stu-id="69637-152">The removed secondary database is placed in the RESTORING state.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="69637-153">Für eine kurze Zeit, nachdem Sie die sekundäre Datenbank entfernt haben, sind Sie möglicherweise in der Lage, die AlwaysOn-Datensynchronisierung für die Datenbank neu zu starten, indem Sie sie mit der Verfügbarkeitsgruppe verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="69637-153">For a short time after removing a secondary database, you might be able to restart AlwaysOn data synchronization on the database by re-joining it to the availability group.</span></span> <span data-ttu-id="69637-154">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69637-154">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="69637-155">Zu diesem Zeitpunkt stehen alternative Methoden zum Umgang mit einer entfernten sekundären Datenbank zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="69637-155">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="69637-156">Wenn Sie die sekundäre Datenbank nicht mehr benötigen, können Sie sie löschen.</span><span class="sxs-lookup"><span data-stu-id="69637-156">If you no longer need the secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="69637-157">Weitere Informationen finden Sie unter [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) oder [Löschen einer Datenbank](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="69637-157">For more information, see [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) or [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="69637-158">Wenn Sie auf eine entfernte sekundäre Datenbank zugreifen möchten, nachdem sie aus der Verfügbarkeitsgruppe entfernt wurde, können Sie die Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="69637-158">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="69637-159">Wenn Sie jedoch eine entfernte sekundäre Datenbank wiederherstellen, sind zwei voneinander abweichende, unabhängige Datenbanken mit demselben Namen online.</span><span class="sxs-lookup"><span data-stu-id="69637-159">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="69637-160">Sie müssen sicherstellen, dass Clients auf nur die aktuelle primäre Datenbank zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="69637-160">You must make sure that clients can access only the current primary database.</span></span>  
  
     <span data-ttu-id="69637-161">Weitere Informationen finden Sie unter [Wiederherstellen einer Datenbank ohne Wiederherstellung von Daten &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="69637-161">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69637-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69637-162">See Also</span></span>  
 <span data-ttu-id="69637-163">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="69637-163">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="69637-164">Entfernen einer primären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="69637-164">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
