---
title: Entfernen eines sekundären Replikats aus einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removesecondaryar.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 35ddc8b6-3e7c-4417-9a0a-d4987a09ddf7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e3f2b35ec9cf27f2f7b23714a41665f2709837a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615600"
---
# <a name="remove-a-secondary-replica-from-an-availability-group-sql-server"></a><span data-ttu-id="38b48-102">Entfernen einer sekundären Replikats aus einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="38b48-102">Remove a Secondary Replica from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="38b48-103">In diesem Thema wird beschrieben, wie ein sekundäres Replikat aus einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="38b48-103">This topic describes how to remove a secondary replica from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="38b48-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="38b48-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="38b48-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="38b48-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="38b48-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="38b48-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="38b48-107">Security</span><span class="sxs-lookup"><span data-stu-id="38b48-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="38b48-108">**So entfernen Sie ein sekundäres Replikat mit**</span><span class="sxs-lookup"><span data-stu-id="38b48-108">**To remove a secondary replica, using:**</span></span>  
  
     [<span data-ttu-id="38b48-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38b48-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="38b48-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38b48-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="38b48-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="38b48-111">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="38b48-112">**Nachverfolgung:**  [Nach dem Entfernen eines sekundären Replikats](#PostBestPractices)</span><span class="sxs-lookup"><span data-stu-id="38b48-112">**Follow Up:**  [After Removing a Secondary Replica](#PostBestPractices)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="38b48-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="38b48-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="38b48-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="38b48-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="38b48-115">Dieser Task wird nur für das primäre Replikat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38b48-115">This task is supported only on the primary replica.</span></span>  
  
-   <span data-ttu-id="38b48-116">Nur ein sekundäres Replikat kann aus einer Verfügbarkeitsgruppe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="38b48-116">Only a secondary replica can be removed from an availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="38b48-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="38b48-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="38b48-118">Sie benötigen eine Verbindung zur Serverinstanz, die das primäre Replikat der Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="38b48-118">You must be connected to the server instance that hosts the primary replica of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="38b48-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="38b48-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="38b48-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="38b48-120">Permissions</span></span>  
 <span data-ttu-id="38b48-121">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="38b48-121">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="38b48-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38b48-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="38b48-123">**So entfernen Sie ein sekundäres Replikat**</span><span class="sxs-lookup"><span data-stu-id="38b48-123">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="38b48-124">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="38b48-124">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="38b48-125">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="38b48-125">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="38b48-126">Wählen Sie die Verfügbarkeitsgruppe aus, und erweitern Sie den Knoten **Verfügbarkeitsreplikate** .</span><span class="sxs-lookup"><span data-stu-id="38b48-126">Select the availability group, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="38b48-127">Dieser Schritt hängt davon ab, ob Sie mehrere Replikate oder nur ein Replikat entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="38b48-127">This step depends on whether you want to remove multiple replicas or only one replica, as follows:</span></span>  
  
    -   <span data-ttu-id="38b48-128">Verwenden Sie zum Entfernen mehrerer Replikate den Bereich **Details zum Objekt-Explorer** , um alle zu entfernenden Replikate anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="38b48-128">To remove multiple replicas, use the **Object Explorer Details** pane to view and select all the replicas that you want to remove.</span></span> <span data-ttu-id="38b48-129">Weitere Informationen finden Sie unter [Verwenden der Details zum Objekt-Explorer zum Überwachen von Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="38b48-129">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="38b48-130">Wählen Sie zum Entfernen eines einzelnen Replikats dieses im Bereich **Objekt-Explorer** oder **Details zum Objekt-Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="38b48-130">To remove a single replica, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="38b48-131">Klicken Sie mit der rechten Maustaste auf die ausgewählten sekundären Replikate, und wählen Sie im Befehlsmenü **Aus Verfügbarkeitsgruppe entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="38b48-131">Right-click the selected secondary replica or replicas, and select **Remove from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="38b48-132">Klicken Sie zum Entfernen aller aufgeführten sekundären Replikate im Dialogfeld **Sekundäre Replikate aus Verfügbarkeitsgruppe entfernen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="38b48-132">In the **Remove Secondary Replicas from Availability Group** dialog box, to remove all the listed secondary replicas, click **OK**.</span></span> <span data-ttu-id="38b48-133">Wenn Sie nicht alle aufgelisteten Replikate entfernen wollen, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="38b48-133">If you do not want to remove all the listed replicas, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="38b48-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38b48-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="38b48-135">**So entfernen Sie ein sekundäres Replikat**</span><span class="sxs-lookup"><span data-stu-id="38b48-135">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="38b48-136">Stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="38b48-136">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="38b48-137">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="38b48-137">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="38b48-138">ALTER AVAILABILITY GROUP *Gruppenname* REMOVE REPLICA ON '*Instanzname*' [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="38b48-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span></span>  
  
     <span data-ttu-id="38b48-139">Dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe und *Instanzname* die Serverinstanz, auf der sich das sekundäre Replikat befindet.</span><span class="sxs-lookup"><span data-stu-id="38b48-139">where *group_name* is the name of the availability group and *instance_name* is the server instance where the secondary replica is located.</span></span>  
  
     <span data-ttu-id="38b48-140">Im folgenden Codebeispiel wird ein sekundäres Replikat aus der *MyAG* -Verfügbarkeitsgruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="38b48-140">The following example removes a secondary replica from the *MyAG* availability group.</span></span> <span data-ttu-id="38b48-141">Das sekundäre Zielreplikat befindet sich auf der Serverinstanz *HADR_INSTANCE* auf dem Computer *COMPUTER02*.</span><span class="sxs-lookup"><span data-stu-id="38b48-141">The target secondary replica is located on a server instance named *HADR_INSTANCE* on a computer named *COMPUTER02*.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE REPLICA ON 'COMPUTER02\HADR_INSTANCE';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="38b48-142">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="38b48-142">Using PowerShell</span></span>  
 <span data-ttu-id="38b48-143">**So entfernen Sie ein sekundäres Replikat**</span><span class="sxs-lookup"><span data-stu-id="38b48-143">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="38b48-144">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="38b48-144">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="38b48-145">Verwenden Sie das Cmdlet **Remove-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="38b48-145">Use the **Remove-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="38b48-146">Beispielsweise wird durch den folgenden Befehl das Verfügbarkeitsreplikat auf dem `MyReplica` -Server von der Verfügbarkeitsgruppe namens `MyAg`entfernt.</span><span class="sxs-lookup"><span data-stu-id="38b48-146">For example, the following command removes the availability replica on the server `MyReplica` from the availability group named `MyAg`.</span></span>  <span data-ttu-id="38b48-147">Dieser Befehl muss auf der Serverinstanz ausgeführt werden, von der das primäre Replikat der Verfügbarkeitsgruppe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="38b48-147">This command must be run on the server instance that hosts the primary replica of the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityReplica -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="38b48-148">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="38b48-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="38b48-149">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="38b48-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="38b48-150">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="38b48-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="38b48-151">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="38b48-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-replica"></a><a name="PostBestPractices"></a> <span data-ttu-id="38b48-152">Nachverfolgung: Nach dem Entfernen eines sekundären Replikats</span><span class="sxs-lookup"><span data-stu-id="38b48-152">Follow Up: After Removing a Secondary Replica</span></span>  
 <span data-ttu-id="38b48-153">Wenn Sie ein Replikat angeben, das derzeit nicht verfügbar ist, wird beim Onlineschalten des Replikats festgestellt, dass es entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="38b48-153">If you specify a replica that is currently unavailable, when the replica comes online, it will discover that it has been removed.</span></span>  
  
 <span data-ttu-id="38b48-154">Wird ein Replikat entfernt, empfängt es keine Daten mehr.</span><span class="sxs-lookup"><span data-stu-id="38b48-154">Removing a replica causes it to stop receiving data.</span></span> <span data-ttu-id="38b48-155">Nachdem für ein sekundäres Replikat bestätigt wurde, dass es aus dem globalen Speicher entfernt wurde, entfernt das Replikat die Verfügbarkeitsgruppeneinstellungen aus seinen Datenbanken, die auf der lokalen Serverinstanz im Status RECOVERING verbleiben.</span><span class="sxs-lookup"><span data-stu-id="38b48-155">After a secondary replica confirms that it has been removed from the global store, the replica removes the availability group settings from its databases, which remain on the local server instance in the RECOVERING state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b48-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38b48-156">See Also</span></span>  
 <span data-ttu-id="38b48-157">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38b48-157">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="38b48-158">[Hinzufügen eines sekundären Replikats zu einer Verfügbarkeits Gruppe &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38b48-158">[Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span></span>  
 [<span data-ttu-id="38b48-159">Entfernen einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="38b48-159">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
