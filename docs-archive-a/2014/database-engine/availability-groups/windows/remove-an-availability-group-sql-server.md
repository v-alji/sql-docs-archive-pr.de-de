---
title: Entfernen einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.deleteag.f1
helpviewer_keywords:
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], dropping
ms.assetid: 4b7f7f62-43a3-49db-a72e-22d4d7c2ddbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c17b7d5b362d8b4030d66ebf7ba0e425495410e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615598"
---
# <a name="remove-an-availability-group-sql-server"></a><span data-ttu-id="b8caa-102">Entfernen einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b8caa-102">Remove an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="b8caa-103">In diesem Thema wird beschrieben, wie eine AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b8caa-103">This topic describes how to delete (drop) an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b8caa-104">Wenn eine Serverinstanz, auf der eines der Verfügbarkeitsreplikate gehostet wird, offline ist, wenn Sie eine Verfügbarkeitsgruppe löschen, so wird das lokale Verfügbarkeitsreplikat von der Serverinstanz gelöscht, nachdem diese online geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="b8caa-104">If a server instance that hosts one of the availability replicas is offline when you delete an availability group, after coming online, the server instance will drop the local availability replica.</span></span> <span data-ttu-id="b8caa-105">Beim Löschen einer Verfügbarkeitsgruppe werden sämtliche zugeordneten Verfügbarkeitsgruppenlistener gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b8caa-105">Dropping an availability group deletes any associated availability group listener.</span></span>  
  
 <span data-ttu-id="b8caa-106">Beachten Sie, dass eine Verfügbarkeitsgruppe ggf. aus einem WSFC (Windows Server Failover Clustering)-Knoten gelöscht werden kann, der über die richtigen Sicherheitsanmeldeinformationen für die Verfügbarkeitsgruppe verfügt.</span><span class="sxs-lookup"><span data-stu-id="b8caa-106">Note that, if necessary, you can drop an availability group from any Windows Server Failover Clustering (WSFC) node that possesses the correct security credentials for the availability group.</span></span> <span data-ttu-id="b8caa-107">Auf diese Weise können Sie eine Verfügbarkeitsgruppe löschen, wenn keine ihrer Verfügbarkeitsreplikate mehr vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b8caa-107">This enables you to delete an availability group when none of its availability replicas remain.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8caa-108">Entfernen Sie die Verfügbarkeitsgruppe wenn möglich nur, während eine Verbindung mit der Serverinstanz besteht, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="b8caa-108">If possible, remove the availability group only while connected to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="b8caa-109">Wenn die Verfügbarkeitsgruppe aus dem primären Replikat gelöscht wird, sind Änderungen in den früheren primären Datenbanken (ohne Hochverfügbarkeitsschutz) zulässig.</span><span class="sxs-lookup"><span data-stu-id="b8caa-109">When the availability group is dropped from the primary replica, changes are allowed in the former primary databases (without high availability protection).</span></span> <span data-ttu-id="b8caa-110">Durch Löschen einer Verfügbarkeitsgruppe aus einem sekundären Replikat erhält das primäre Replikat den Status RESTORING und Änderungen an den Datenbanken sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b8caa-110">Deleting an availability group from a secondary replica leaves the primary replica in the RESTORING state, and changes are not allowed on the databases.</span></span>  
  
-   <span data-ttu-id="b8caa-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b8caa-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8caa-112">Einschränkungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b8caa-112">Limitations and Recommendations</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b8caa-113">Security</span><span class="sxs-lookup"><span data-stu-id="b8caa-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8caa-114">**So löschen Sie eine Verfügbarkeitsgruppe mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="b8caa-114">**To delete an availability group, using:**</span></span>  
  
     [<span data-ttu-id="b8caa-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8caa-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b8caa-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8caa-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b8caa-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8caa-117">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="b8caa-118">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="b8caa-118">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8caa-119">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b8caa-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-recommendations"></a><a name="Restrictions"></a><span data-ttu-id="b8caa-120">Einschränkungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b8caa-120">Limitations and Recommendations</span></span>  
  
-   <span data-ttu-id="b8caa-121">Wenn die Verfügbarkeitsgruppe online ist, bewirkt das Löschen aus einem sekundären Replikat den Übergang des primären Replikats in den Status RESTORING.</span><span class="sxs-lookup"><span data-stu-id="b8caa-121">When the availability group is online, deleting it from a secondary replica causes the primary replica to transition to the RESTORING state.</span></span> <span data-ttu-id="b8caa-122">Daher sollten Sie die Verfügbarkeitsgruppe möglichst nur aus der Serverinstanz entfernen, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="b8caa-122">Therefore, if possible, remove the availability group only from the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="b8caa-123">Wenn Sie eine Verfügbarkeitsgruppe von einem Computer löschen, der aus dem WSFC-Failovercluster entfernt wurde, wird die Verfügbarkeitsgruppe nur lokal gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b8caa-123">If you delete an availability group from a computer that has been removed or evicted from the WSFC failover cluster, the availability group is only deleted locally.</span></span>  
  
-   <span data-ttu-id="b8caa-124">Löschen Sie eine Verfügbarkeitsgruppe nicht, wenn der WSFC-Cluster (Windows Server Failover Clustering) kein Quorum hat.</span><span class="sxs-lookup"><span data-stu-id="b8caa-124">Avoid dropping an availability group when the Windows Server Failover Clustering (WSFC) cluster has no quorum.</span></span> <span data-ttu-id="b8caa-125">Wenn Sie eine Verfügbarkeitsgruppe löschen müssen, solange der Cluster über kein Quorum verfügt, wird die Metadaten-Verfügbarkeitsgruppe, die im Cluster gespeichert ist, nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8caa-125">If you must drop an availability group while the cluster lacks quorum, the metadata availability group that is stored in the cluster is not removed.</span></span> <span data-ttu-id="b8caa-126">Nachdem der Cluster das Quorum wiedererlangt hat, müssen Sie die Verfügbarkeitsgruppe erneut löschen, um diese aus dem WSFC-Cluster zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b8caa-126">After the cluster regains quorum, you will need to drop the availability group again to remove it from the WSFC cluster.</span></span>  
  
-   <span data-ttu-id="b8caa-127">Auf einem sekundären Replikat sollte DROP AVAILABILITY GROUP nur im Notfall verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8caa-127">On a secondary replica, DROP AVAILABILITY GROUP should only be used only for emergency purposes.</span></span> <span data-ttu-id="b8caa-128">Das liegt daran, dass durch Löschen einer Verfügbarkeitsgruppe die Verfügbarkeitsgruppe offline geschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b8caa-128">This is because dropping an availability group takes the availability group offline.</span></span> <span data-ttu-id="b8caa-129">Wenn Sie die Verfügbarkeitsgruppe aus einem sekundären Replikat löschen, kann das primäre Replikat nicht bestimmen, ob der OFFLINE-Status aufgrund des Quorumverlusts, eines erzwungenen Failovers oder eines DROP AVAILABILITY GROUP-Befehls aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b8caa-129">If you drop the availability group from a secondary replica, the primary replica cannot determine whether the OFFLINE state occurred because of quorum loss, a forced failover, or a DROP AVAILABILITY GROUP command.</span></span> <span data-ttu-id="b8caa-130">Das primäre Replikat geht in den Status RESTORING über, um eine mögliche Split Brain-Situation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b8caa-130">The primary replica transitions to the RESTORING state to prevent a possible split-brain situation.</span></span> <span data-ttu-id="b8caa-131">Weitere Informationen finden Sie unter [Funktionsweise: DROP AVAILABILITY GROUP-Verhaltensweisen](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (Blog von CSS SQL Server-Ingenieuren).</span><span class="sxs-lookup"><span data-stu-id="b8caa-131">For more information, see [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8caa-132">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b8caa-132">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8caa-133">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b8caa-133">Permissions</span></span>  
 <span data-ttu-id="b8caa-134">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="b8caa-134">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span> <span data-ttu-id="b8caa-135">Um eine Verfügbarkeitsgruppe zu löschen, die nicht von der lokalen Serverinstanz gehostet wird, benötigen Sie die CONTROL SERVER-Berechtigung oder die CONTROL-Berechtigung für diese Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="b8caa-135">To drop an availability group that is not hosted by the local server instance you need CONTROL SERVER permission or CONTROL permission on that Availability Group.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b8caa-136">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8caa-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b8caa-137">**So löschen Sie eine Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="b8caa-137">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="b8caa-138">Wenn möglich, stellen Sie in Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet, oder stellen Sie eine Verbindung zu einer anderen Serverinstanz her, die für AlwaysOn-Verfügbarkeitsgruppen in einem WSFC-Knoten aktiviert ist, der die richtigen Sicherheitsanmeldeinformationen für die Verfügbarkeitsgruppe besitzt.</span><span class="sxs-lookup"><span data-stu-id="b8caa-138">In Object Explorer, connect to the server instance that hosts primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span> <span data-ttu-id="b8caa-139">Erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="b8caa-139">Expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b8caa-140">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="b8caa-140">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="b8caa-141">Dieser Schritt hängt davon ab, ob Sie mehrere Verfügbarkeitsgruppen oder nur eine Verfügbarkeitsgruppe löschen möchten:</span><span class="sxs-lookup"><span data-stu-id="b8caa-141">This step depends on whether you want to delete multiple availability groups or only one availability group, as follows:</span></span>  
  
    -   <span data-ttu-id="b8caa-142">Zum Löschen mehrerer Verfügbarkeitsgruppen, deren primären Replikate sich auf der verbundenen Serverinstanz befinden, verwenden Sie den Bereich **Details zum Objekt-Explorer**, um alle Verfügbarkeitsgruppen, die Sie löschen möchten, anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b8caa-142">To delete multiple availability groups (whose primary replicas are on the connected server instance), use the **Object Explorer Details** pane to view and select all the availability groups that you want to delete.</span></span> <span data-ttu-id="b8caa-143">Weitere Informationen finden Sie unter [Verwenden der Details zum Objekt-Explorer zum Überwachen von Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b8caa-143">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="b8caa-144">Zum Löschen einer einzelnen Verfügbarkeitsgruppe wählen Sie sie entweder im Bereich **Objekt-Explorer** oder im Bereich **Details zum Objekt-Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="b8caa-144">To delete a single availability group, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
4.  <span data-ttu-id="b8caa-145">Klicken Sie mit der rechten Maustaste auf die ausgewählte Verfügbarkeitsgruppe oder die Gruppen, und wählen Sie den Befehl **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="b8caa-145">Right-click the selected availability group or groups, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="b8caa-146">Um im Dialogfeld **Verfügbarkeitsgruppe entfernen** alle aufgelisteten Verfügbarkeitsgruppen zu löschen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8caa-146">In the **Remove Availability Group** dialog box, to delete all the listed availability groups, click **OK**.</span></span> <span data-ttu-id="b8caa-147">Wenn Sie nicht alle aufgelisteten Verfügbarkeitsgruppen entfernen möchten, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="b8caa-147">If you do not want to remove all the listed availability groups, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b8caa-148">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8caa-148">Using Transact-SQL</span></span>  
 <span data-ttu-id="b8caa-149">**So löschen Sie eine Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="b8caa-149">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="b8caa-150">Wenn möglich, stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet, oder stellen Sie eine Verbindung zu einer anderen Serverinstanz her, die für AlwaysOn-Verfügbarkeitsgruppen in einem WSFC-Knoten aktiviert ist, der die richtigen Sicherheitsanmeldeinformationen für die Verfügbarkeitsgruppe besitzt.</span><span class="sxs-lookup"><span data-stu-id="b8caa-150">Connect to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="b8caa-151">Verwenden Sie die [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b8caa-151">Use the [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) statement, as follows</span></span>  
  
     <span data-ttu-id="b8caa-152">DROP AVAILABILITY GROUP *group_name*</span><span class="sxs-lookup"><span data-stu-id="b8caa-152">DROP AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="b8caa-153">Dabei ist *group_name* der Name der Verfügbarkeitsgruppe die gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8caa-153">where *group_name* is the name of the availability group to be dropped.</span></span>  
  
     <span data-ttu-id="b8caa-154">Im folgenden Beispiel wird die `MyAG` -Verfügbarkeitsgruppe gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b8caa-154">The following example deletes the `MyAG` availability group.</span></span>  
  
    ```sql
    DROP AVAILABILITY GROUP MyAG;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b8caa-155">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8caa-155">Using PowerShell</span></span>  
 <span data-ttu-id="b8caa-156">**So löschen Sie eine Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="b8caa-156">**To delete an availability group**</span></span>  
  
 <span data-ttu-id="b8caa-157">Im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Anbieter:</span><span class="sxs-lookup"><span data-stu-id="b8caa-157">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="b8caa-158">Wenn möglich, ändern sie das Verzeichnis (`cd`) zu der Serverinstanz, die das primäre Replikat hostet, oder stellen Sie eine Verbindung zu einer anderen Serverinstanz her, die für AlwaysOn-Verfügbarkeitsgruppen in einem WSFC-Knoten aktiviert ist, der die richtigen Sicherheitsanmeldeinformationen für die Verfügbarkeitsgruppe besitzt.</span><span class="sxs-lookup"><span data-stu-id="b8caa-158">Change directory (`cd`) to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="b8caa-159">Verwenden Sie das **Remove-SqlAvailabilityGroup** -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b8caa-159">Use the **Remove-SqlAvailabilityGroup** cmdlet.</span></span>  
  
     <span data-ttu-id="b8caa-160">Beispielsweise wird die Verfügbarkeitsgruppe namens `MyAg`mit dem folgenden Befehl entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8caa-160">For example, the following command removes the availability group named `MyAg`.</span></span> <span data-ttu-id="b8caa-161">Dieser Befehl kann auf jeder Serverinstanz ausgeführt werden, von der ein Verfügbarkeitsreplikat für die Verfügbarkeitsgruppe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b8caa-161">This command can be executed on any server instance that hosts an availability replica for the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8caa-162">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b8caa-162">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="b8caa-163">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b8caa-163">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="b8caa-164">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="b8caa-164">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="b8caa-165">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="b8caa-165">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="b8caa-166">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="b8caa-166">Related Content</span></span>  
  
-   <span data-ttu-id="b8caa-167">[Funktionsweise: DROP AVAILABILITY GROUP-Verhaltensweisen](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (Blog von CSS SQL Server-Ingenieuren)</span><span class="sxs-lookup"><span data-stu-id="b8caa-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8caa-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8caa-168">See Also</span></span>  
 <span data-ttu-id="b8caa-169">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8caa-169">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="b8caa-170">Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b8caa-170">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
