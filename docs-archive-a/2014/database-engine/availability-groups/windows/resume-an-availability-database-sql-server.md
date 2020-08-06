---
title: Fortsetzen einer Verfügbarkeitsdatenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.resumedatamove.f1
helpviewer_keywords:
- Availability Groups [SQL Server], resuming a database
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], databases
ms.assetid: 20e9147b-e985-4caa-910e-fc4b38dbf9a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a2279940c2502a310e9dac4448bd6029b6e13dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724217"
---
# <a name="resume-an-availability-database-sql-server"></a><span data-ttu-id="a0315-102">Fortsetzen einer Verfügbarkeitsdatenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a0315-102">Resume an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="a0315-103">Eine angehaltene Verfügbarkeitsdatenbank können Sie in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="a0315-103">You can resume a suspended availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a0315-104">Beim Fortsetzen einer angehaltenen Datenbank wechselt die Datenbank in den Status SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="a0315-104">Resuming a suspended database puts the database into the SYNCHRONIZING state.</span></span> <span data-ttu-id="a0315-105">Beim Fortsetzen der primären Datenbank werden auch ihre sekundären Datenbanken fortgesetzt, die beim Anhalten der primären Datenbank angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="a0315-105">Resuming the primary database also resumes any of its secondary databases that were suspended as the result of suspending the primary database.</span></span> <span data-ttu-id="a0315-106">Wenn eine sekundäre Datenbank lokal von der Serverinstanz, die das sekundäre Replikat hostet, angehalten wurde, muss diese sekundäre Datenbank lokal fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a0315-106">If any secondary database was suspended locally, from the server instance that hosts the secondary replica, that secondary database must be resumed locally.</span></span> <span data-ttu-id="a0315-107">Sobald sich eine bestimmte sekundäre Datenbank und die entsprechende primäre Datenbank im Status SYNCHRONIZING befinden, wird die Datensynchronisierung auf der sekundären Datenbank fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a0315-107">Once a given secondary database and the corresponding primary database are in the SYNCHRONIZING state, data synchronization resumes on the secondary database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0315-108">Das Anhalten und Fortsetzen einer sekundären AlwaysOn-Datenbank wirkt sich nicht direkt auf die Verfügbarkeit der primären Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="a0315-108">Suspending and resuming an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="a0315-109">Das Anhalten einer sekundären Datenbank kann jedoch sich auf Redundanz- und Failoverfunktionen für die primäre Datenbank auswirken, bis die angehaltene sekundäre Datenbank fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a0315-109">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database, until the suspended secondary database is resumed.</span></span> <span data-ttu-id="a0315-110">Dies steht im Gegensatz zur Datenbankspiegelung, bei der der Spiegelungsstatus sowohl in der Spiegeldatenbank als auch in der Prinzipaldatenbank angehalten wird, bis die Spiegelung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a0315-110">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database until mirroring is resumed.</span></span> <span data-ttu-id="a0315-111">Durch Anhalten einer primären AlwaysOn-Datenbank wird die Datenverschiebung auf allen entsprechenden sekundären Datenbanken angehalten, und Redundanz- und Failoverfunktionen für diese Datenbank werden deaktiviert, bis die primäre Datenbank fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a0315-111">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="a0315-112">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a0315-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0315-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a0315-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a0315-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a0315-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a0315-115">Security</span><span class="sxs-lookup"><span data-stu-id="a0315-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a0315-116">**So setzen Sie eine sekundäre Datenbank fort mit:**</span><span class="sxs-lookup"><span data-stu-id="a0315-116">**To resume a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="a0315-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0315-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a0315-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0315-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a0315-119">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0315-119">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="a0315-120">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="a0315-120">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0315-121">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a0315-121">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a0315-122">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a0315-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a0315-123">Ein RESUME-Befehl gibt einen Wert zurück, sobald es vom Replikat akzeptiert wurde, das die Zieldatenbank hostet. Das Fortsetzen der Datenbank ist jedoch dadurch asynchron.</span><span class="sxs-lookup"><span data-stu-id="a0315-123">A RESUME command returns as soon as it has been accepted by the replica that hosts the target database, but actually resuming the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a0315-124">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a0315-124">Prerequisites</span></span>  
  
-   <span data-ttu-id="a0315-125">Sie müssen mit der Serverinstanz verbunden sein, auf der die fortzusetzende Datenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="a0315-125">You must be connected to the server instance that hosts the database to be resumed.</span></span>  
  
-   <span data-ttu-id="a0315-126">Die Verfügbarkeitsgruppe muss online sein.</span><span class="sxs-lookup"><span data-stu-id="a0315-126">The availability group must be online.</span></span>  
  
-   <span data-ttu-id="a0315-127">Die primäre Datenbank muss online und verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="a0315-127">The primary database must be online and available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0315-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a0315-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0315-129">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a0315-129">Permissions</span></span>  
 <span data-ttu-id="a0315-130">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a0315-130">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="a0315-131">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="a0315-131">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0315-132">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0315-132">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a0315-133">**So setzen Sie eine sekundäre Datenbank fort**</span><span class="sxs-lookup"><span data-stu-id="a0315-133">**To resume a secondary database**</span></span>  
  
1.  <span data-ttu-id="a0315-134">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz mit dem Verfügbarkeitsreplikat her, auf der eine Datenbank fortgesetzt werden soll, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="a0315-134">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to resume a database, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a0315-135">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="a0315-135">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a0315-136">Erweitern Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="a0315-136">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="a0315-137">Erweitern Sie den Knoten **Verfügbarkeitsdatenbanken** , klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie auf **Datenverschiebung fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="a0315-137">Expand the **Availability Databases** node, right-click the database, and click **Resume Data Movement**.</span></span>  
  
5.  <span data-ttu-id="a0315-138">Klicken Sie im Dialogfeld **Datenverschiebung fortsetzen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0315-138">In the **Resume Data Movement** dialog box, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0315-139">Wiederholen Sie zum Fortsetzen weiterer Datenbanken in diesem Replikatspeicherort Schritt 4 und 5 für jede Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a0315-139">To resume additional databases on this replica location, repeat steps 4 and 5 for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a0315-140">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0315-140">Using Transact-SQL</span></span>  
 <span data-ttu-id="a0315-141">**So setzen Sie eine sekundäre Datenbank fort, die lokal angehalten wurde**</span><span class="sxs-lookup"><span data-stu-id="a0315-141">**To resume a secondary database that was suspended locally**</span></span>  
  
1.  <span data-ttu-id="a0315-142">Stellen Sie eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet, dessen Datenbank Sie fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="a0315-142">Connect to the server instance that hosts the secondary replica whose database you want to resume.</span></span>  
  
2.  <span data-ttu-id="a0315-143">Setzen Sie die sekundäre Datenbank mithilfe der folgenden [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)-Anweisung fort:</span><span class="sxs-lookup"><span data-stu-id="a0315-143">Resume the secondary database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="a0315-144">ALTER DATABASE *database_name* Set HADR resume</span><span class="sxs-lookup"><span data-stu-id="a0315-144">ALTER DATABASE *database_name* SET HADR RESUME</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a0315-145">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0315-145">Using PowerShell</span></span>  

### <a name="to-resume-a-secondary-database"></a><span data-ttu-id="a0315-146">So setzen Sie eine sekundäre Datenbank fort</span><span class="sxs-lookup"><span data-stu-id="a0315-146">To resume a secondary database</span></span>
  
1.  <span data-ttu-id="a0315-147">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das Replikat hostet, dessen Datenbank Sie fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="a0315-147">Change directory (`cd`) to the server instance that hosts the replica whose database you want to resume.</span></span> <span data-ttu-id="a0315-148">Weitere Informationen finden Sie weiter oben in diesem Thema unter [Voraussetzungen](#Prerequisites).</span><span class="sxs-lookup"><span data-stu-id="a0315-148">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a0315-149">Verwenden Sie das Cmdlet **Resume-SqlAvailabilityDatabase** , um die Verfügbarkeitsgruppe fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a0315-149">Use the **Resume-SqlAvailabilityDatabase** cmdlet to resume the availability group.</span></span>  
  
     <span data-ttu-id="a0315-150">Beispielsweise wird durch den folgenden Befehl die Datensynchronisierung für die Verfügbarkeitsdatenbank `MyDb3` in der Verfügbarkeitsgruppe `MyAg`fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a0315-150">For example, the following command resumes data synchronization for the availability database `MyDb3` in the availability group `MyAg`.</span></span>  
  
    ```powershell
    Resume-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0315-151">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a0315-151">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a0315-152">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a0315-152">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a0315-153">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="a0315-153">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a0315-154">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="a0315-154">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a0315-155">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="a0315-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a0315-156">Anhalten einer Verfügbarkeitsdatenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a0315-156">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0315-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0315-157">See Also</span></span>  
 [<span data-ttu-id="a0315-158">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a0315-158">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
