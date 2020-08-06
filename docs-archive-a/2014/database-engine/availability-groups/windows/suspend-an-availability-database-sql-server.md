---
title: Anhalten einer Verfügbarkeitsdatenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.suspenddatamove.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], suspending a database
- Availability Groups [SQL Server], databases
ms.assetid: 86858982-6af1-4e80-9a93-87451f0d7ee9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49afe868a509f84160fc1ad154135e8e67f6900a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724969"
---
# <a name="suspend-an-availability-database-sql-server"></a><span data-ttu-id="29dac-102">Anhalten einer Verfügbarkeitsdatenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="29dac-102">Suspend an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="29dac-103">Eine Verfügbarkeitsdatenbank können Sie in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]anhalten.</span><span class="sxs-lookup"><span data-stu-id="29dac-103">You can suspend an availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="29dac-104">Beachten Sie, dass der Befehl zum Anhalten auf der Serverinstanz ausgegeben werden muss, die die anzuhaltende oder fortzusetzende Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="29dac-104">Note that a suspend command needs to be issued on the server instance that hosts the database to be suspended or resumed.</span></span>  
  
 <span data-ttu-id="29dac-105">Die Auswirkung eines Anhaltebefehls ist davon abhängig, ob Sie eine sekundäre Datenbank oder eine primäre Datenbank anhalten:</span><span class="sxs-lookup"><span data-stu-id="29dac-105">The effect of a suspend command depends on whether you suspend a secondary database or a primary database, as follows:</span></span>  
  
|<span data-ttu-id="29dac-106">Angehaltene Datenbank</span><span class="sxs-lookup"><span data-stu-id="29dac-106">Suspended Database</span></span>|<span data-ttu-id="29dac-107">Auswirkung des Anhaltebefehls</span><span class="sxs-lookup"><span data-stu-id="29dac-107">Effect of Suspend Command</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="29dac-108">Sekundäre Datenbank</span><span class="sxs-lookup"><span data-stu-id="29dac-108">Secondary database</span></span>|<span data-ttu-id="29dac-109">Nur die lokale sekundäre Datenbank wird angehalten, und ihr Synchronisierungsstatus wird NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="29dac-109">Only the local secondary database is suspended and its synchronization state becomes NOT SYNCHRONIZING.</span></span> <span data-ttu-id="29dac-110">Andere sekundäre Datenbanken sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="29dac-110">Other secondary databases are not affected.</span></span> <span data-ttu-id="29dac-111">Die angehaltene Datenbank empfängt keine Daten (Protokolldatensätze) mehr und wendet keine Daten mehr an und beginnt, hinter die primäre Datenbank zu fallen.</span><span class="sxs-lookup"><span data-stu-id="29dac-111">The suspended database stops receiving and applying data (log records) and begins to fall behind the primary database.</span></span> <span data-ttu-id="29dac-112">Vorhandene Verbindungen mit dem lesbaren sekundären Replikat können weiter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29dac-112">Existing connections on the readable secondary remain usable.</span></span> <span data-ttu-id="29dac-113">Neue Verbindungen mit der angehaltenen Datenbank auf dem lesbaren sekundären Replikat werden erst zugelassen, wenn Datenverschiebung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="29dac-113">New connections to the suspended database on the readable secondary are not allowed until data movement is resumed.</span></span><br /><br /> <span data-ttu-id="29dac-114">Die primäre Datenbank bleibt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="29dac-114">The primary database remains available.</span></span> <span data-ttu-id="29dac-115">Wenn Sie jede der entsprechenden sekundären Datenbanken anhalten, wird die primären Datenbank ungeschützt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="29dac-115">If you suspend each of the corresponding secondary databases, the primary database runs exposed.</span></span><br /><br /> <span data-ttu-id="29dac-116">**\*\* Wichtig \*\*** Während eine sekundäre Datenbank angehalten ist, sammelt die Sendewarteschlange der entsprechenden primären Datenbank nicht gesendete Transaktionsprotokoll-Datensätze.</span><span class="sxs-lookup"><span data-stu-id="29dac-116">**\*\* Important \*\*** While a secondary database is suspended, the send queue of the corresponding primary database will accumulate unsent transaction log records.</span></span> <span data-ttu-id="29dac-117">Verbindungen mit dem sekundären Replikat geben Daten zurück, die verfügbar waren, als die Datenverschiebung angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="29dac-117">Connections to the secondary replica return data that was available at the time the data movement was suspended.</span></span>|  
|<span data-ttu-id="29dac-118">Primäre Datenbank</span><span class="sxs-lookup"><span data-stu-id="29dac-118">Primary database</span></span>|<span data-ttu-id="29dac-119">Die primäre Datenbank beendet die Datenverschiebung zu jeder verbundenen sekundären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="29dac-119">The primary database stops data movement to every connected secondary database.</span></span> <span data-ttu-id="29dac-120">Die primäre Datenbank wird weiterhin in einem ungeschützten Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="29dac-120">The primary database continues running, in an exposed mode.</span></span> <span data-ttu-id="29dac-121">Die primäre Datenbank bleibt für Clients verfügbar, und vorhandene Verbindungen in einer lesbaren sekundären Datenbank bleiben verwendbar, und neue Verbindungen können hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29dac-121">The primary database remains available to clients, and existing connections on a readable secondary remain usable and new connections can be made.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="29dac-122">Das Anhalten einer sekundären AlwaysOn-Datenbank wirkt sich nicht direkt auf die Verfügbarkeit der primären Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="29dac-122">Suspending an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="29dac-123">Das Anhalten einer sekundären Datenbank kann jedoch sich auf Redundanz- und Failoverfunktionen für die primäre Datenbank auswirken.</span><span class="sxs-lookup"><span data-stu-id="29dac-123">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database.</span></span> <span data-ttu-id="29dac-124">Dies steht im Gegensatz zur Datenbankspiegelung, bei der der Spiegelungsstatus sowohl in der Spiegeldatenbank als auch in der Prinzipaldatenbank angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="29dac-124">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database.</span></span> <span data-ttu-id="29dac-125">Durch Anhalten einer primären AlwaysOn-Datenbank wird die Datenverschiebung auf allen entsprechenden sekundären Datenbanken angehalten, und Redundanz- und Failoverfunktionen für diese Datenbank werden deaktiviert, bis die primäre Datenbank fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="29dac-125">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="29dac-126">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="29dac-126">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29dac-127">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="29dac-127">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="29dac-128">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="29dac-128">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="29dac-129">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="29dac-129">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="29dac-130">Security</span><span class="sxs-lookup"><span data-stu-id="29dac-130">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29dac-131">**Anhalten einer Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="29dac-131">**To suspend a database, using:**</span></span>  
  
-   [<span data-ttu-id="29dac-132">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29dac-132">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="29dac-133">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29dac-133">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="29dac-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="29dac-134">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="29dac-135">**Nachverfolgung:** [Vermeiden eines vollen Transaktionsprotokolls](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="29dac-135">**Follow up:** [Avoiding a Full Transaction Log](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="29dac-136">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="29dac-136">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29dac-137">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="29dac-137">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="29dac-138">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="29dac-138">Limitations and Restrictions</span></span>  
 <span data-ttu-id="29dac-139">Ein SUSPEND-Befehl gibt einen Wert zurück, sobald es vom Replikat akzeptiert wurde, das die Zieldatenbank hostet. Das Anhalten der Datenbank ist jedoch dadurch asynchron.</span><span class="sxs-lookup"><span data-stu-id="29dac-139">A SUSPEND command returns as soon as it has been accepted by the replica that hosts the target database, but actually suspending the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="29dac-140">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="29dac-140">Prerequisites</span></span>  
 <span data-ttu-id="29dac-141">Sie müssen mit der Serverinstanz verbunden sein, die die Datenbank hostet, die angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="29dac-141">You must be connected to the server instance that hosts the database that you want to suspend.</span></span> <span data-ttu-id="29dac-142">Um eine primäre Datenbank und die entsprechenden sekundären Datenbanken anzuhalten, stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="29dac-142">To suspend a primary database and the corresponding secondary databases, connect to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="29dac-143">Um eine sekundäre Datenbank anzuhalten und die primäre Datenbank verfügbar zu lassen, stellen Sie eine Verbindung mit dem sekundären Replikat her.</span><span class="sxs-lookup"><span data-stu-id="29dac-143">To suspend a secondary database while leaving the primary database available, connect to the secondary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="29dac-144">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="29dac-144">Recommendations</span></span>  
 <span data-ttu-id="29dac-145">Bei Engpässen ist das Anhalten einer oder mehrerer sekundärer Datenbanken möglicherweise kurz nützlich, um die Leistung auf dem primären Replikat vorübergehend zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="29dac-145">During bottlenecks, suspending one or more secondary databases briefly might be useful to improve performance temporarily on the primary replica.</span></span> <span data-ttu-id="29dac-146">Solange eine sekundäre Datenbank angehalten bleibt, kann das Transaktionsprotokoll der entsprechenden primären Datenbank nicht abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="29dac-146">As long as a secondary database remains suspended, the transaction log of the corresponding primary database cannot be truncated.</span></span> <span data-ttu-id="29dac-147">Dies führt dazu, dass sich Protokolldatensätze auf der primären Datenbank ansammeln.</span><span class="sxs-lookup"><span data-stu-id="29dac-147">This causes log records to accumulate on the primary database.</span></span> <span data-ttu-id="29dac-148">Daher wird empfohlen, dass Sie eine angehaltene sekundäre Datenbank schnell fortsetzen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="29dac-148">Therefore, we recommend that you resume, or remove, a suspended secondary database quickly.</span></span> <span data-ttu-id="29dac-149">Weitere Informationen finden Sie in diesem Artikel unter [Nachverfolgung: Vermeiden eines vollen Transaktionsprotokolls](#FollowUp).</span><span class="sxs-lookup"><span data-stu-id="29dac-149">For more information, see [Follow up: Avoiding a Full Transaction Log](#FollowUp), later in this topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29dac-150">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="29dac-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29dac-151">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29dac-151">Permissions</span></span>  
 <span data-ttu-id="29dac-152">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="29dac-152">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="29dac-153">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="29dac-153">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29dac-154">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29dac-154">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="29dac-155">**So halten Sie eine Datenbank an**</span><span class="sxs-lookup"><span data-stu-id="29dac-155">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="29dac-156">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz mit dem Verfügbarkeitsreplikat her, auf der eine Datenbank angehalten werden soll, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="29dac-156">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to suspend a database, and expand the server tree.</span></span> <span data-ttu-id="29dac-157">Weitere Informationen finden Sie weiter oben in diesem Thema unter [Voraussetzungen](#Prerequisites).</span><span class="sxs-lookup"><span data-stu-id="29dac-157">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="29dac-158">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="29dac-158">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="29dac-159">Erweitern Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="29dac-159">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="29dac-160">Erweitern Sie den Knoten **Verfügbarkeitsdatenbanken** , klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie auf **Datenverschiebung anhalten**.</span><span class="sxs-lookup"><span data-stu-id="29dac-160">Expand the **Availability Databases** node, right-click the database, and click **Suspend Data Movement**.</span></span>  
  
5.  <span data-ttu-id="29dac-161">Klicken Sie im Dialogfeld **Datenverschiebung anhalten** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="29dac-161">In the **Suspend Data Movement** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="29dac-162">Im Objekt-Explorer wird angegeben, dass die Datenbank angehalten wird, indem das Datenbanksymbol einen Pausenindikator anzeigt.</span><span class="sxs-lookup"><span data-stu-id="29dac-162">Object Explorer indicates that the database is suspended by changing  the database icon to display a pause indicator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29dac-163">Wiederholen Sie zum Anhalten weiterer Datenbanken in diesem Replikatspeicherort Schritt 4 und 5 für jede Datenbank.</span><span class="sxs-lookup"><span data-stu-id="29dac-163">To suspend additional databases on this replica location, repeat steps 4 and 5  for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29dac-164">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29dac-164">Using Transact-SQL</span></span>  
 <span data-ttu-id="29dac-165">**So halten Sie eine Datenbank an**</span><span class="sxs-lookup"><span data-stu-id="29dac-165">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="29dac-166">Stellen Sie eine Verbindung mit der Serverinstanz her, die das Replikat hostet, dessen Datenbank Sie anhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="29dac-166">Connect to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="29dac-167">Weitere Informationen finden Sie weiter oben in diesem Thema unter [Voraussetzungen](#Prerequisites).</span><span class="sxs-lookup"><span data-stu-id="29dac-167">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="29dac-168">Halten Sie die Datenbank mithilfe der folgenden [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)-Anweisung an:</span><span class="sxs-lookup"><span data-stu-id="29dac-168">Suspend the database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="29dac-169">ALTER DATABASE *database_name* Set HADR Suspend</span><span class="sxs-lookup"><span data-stu-id="29dac-169">ALTER DATABASE *database_name* SET HADR SUSPEND</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="29dac-170">PowerShell</span><span class="sxs-lookup"><span data-stu-id="29dac-170">Using PowerShell</span></span>  
 <span data-ttu-id="29dac-171">**So halten Sie eine Datenbank an**</span><span class="sxs-lookup"><span data-stu-id="29dac-171">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="29dac-172">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das Replikat hostet, dessen Datenbank Sie anhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="29dac-172">Change directory (`cd`) to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="29dac-173">Weitere Informationen finden Sie weiter oben in diesem Thema unter [Voraussetzungen](#Prerequisites).</span><span class="sxs-lookup"><span data-stu-id="29dac-173">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="29dac-174">Verwenden Sie das `Suspend-SqlAvailabilityDatabase`-Cmdlet, um die Verfügbarkeitsgruppe anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="29dac-174">Use the `Suspend-SqlAvailabilityDatabase` cmdlet to suspend the availability group.</span></span>  
  
     <span data-ttu-id="29dac-175">Durch den folgenden Befehl wird beispielsweise die Datensynchronisierung für die Verfügbarkeitsdatenbank `MyDb3` in der Verfügbarkeitsgruppe `MyAg` auf der Serverinstanz `Computer\Instance`angehalten.</span><span class="sxs-lookup"><span data-stu-id="29dac-175">For example, the following command suspends data synchronization for the availability database `MyDb3` in the availability group `MyAg` on the server instance named `Computer\Instance`.</span></span>  
  
    ```powershell
    Suspend-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="29dac-176">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="29dac-176">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="29dac-177">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="29dac-177">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="29dac-178">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="29dac-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="29dac-179">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="29dac-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-avoiding-a-full-transaction-log"></a><a name="FollowUp"></a><span data-ttu-id="29dac-180">Nächster Schritt: Vermeiden eines vollen Transaktionsprotokolls</span><span class="sxs-lookup"><span data-stu-id="29dac-180">Follow Up: Avoiding a Full Transaction Log</span></span>  
 <span data-ttu-id="29dac-181">Wenn ein automatischer Prüfpunkt für eine Datenbank ausgeführt wird, wird normalerweise das zugehörige Transaktionsprotokoll nach der nächsten Protokollsicherung auf diesen Prüfpunkt gekürzt.</span><span class="sxs-lookup"><span data-stu-id="29dac-181">Normally, when an automatic checkpoint is performed on a database, its transaction log is truncated to that checkpoint after the next log backup.</span></span> <span data-ttu-id="29dac-182">Wenn jedoch eine sekundäre Datenbank angehalten wird, bleiben alle aktuellen Protokolldatensätze auf der primären Datenbank aktiv.</span><span class="sxs-lookup"><span data-stu-id="29dac-182">However, while a secondary database is suspended, all of the current log records remain active on the primary database.</span></span> <span data-ttu-id="29dac-183">Wenn das Transaktionsprotokoll voll ist (weil die maximale Größe erreicht wurde oder weil für die Serverinstanz der Speicherplatz nicht ausreicht), kann die Datenbank keine Updates mehr ausführen.</span><span class="sxs-lookup"><span data-stu-id="29dac-183">If the transaction log fills up (either because it reaches its maximum size or the server instance runs out of space), the database cannot perform any more updates.</span></span>  
  
 <span data-ttu-id="29dac-184">Führen Sie eine der folgenden Aktionen aus, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="29dac-184">To avoid this problem, you should do one of the following:</span></span>  
  
-   <span data-ttu-id="29dac-185">Fügen Sie mehr Protokollspeicherplatz für die primäre Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="29dac-185">Add more log space for the primary database.</span></span>  
  
-   <span data-ttu-id="29dac-186">Setzen Sie die sekundäre Datenbank fort, bevor das Protokoll voll ist.</span><span class="sxs-lookup"><span data-stu-id="29dac-186">Resume the secondary database before the log fills up.</span></span> <span data-ttu-id="29dac-187">Weitere Informationen finden Sie weiter unten in diesem Thema unter [Fortsetzen einer Verfügbarkeitsdatenbank &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md)anhalten.</span><span class="sxs-lookup"><span data-stu-id="29dac-187">For more information, see [Resume an Availability Database &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span></span>  
  
-   <span data-ttu-id="29dac-188">Entfernen Sie die sekundäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="29dac-188">Remove the secondary database.</span></span> <span data-ttu-id="29dac-189">Weitere Informationen finden Sie unter [Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="29dac-189">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="29dac-190">**So beheben Sie die Fehler eines vollständigen Transaktionsprotokolls**</span><span class="sxs-lookup"><span data-stu-id="29dac-190">**To troubleshoot a full transaction log**</span></span>  
  
-   [<span data-ttu-id="29dac-191">Problembehandlung bei vollen Transaktionsprotokollen &#40;SQL Server-Fehler 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="29dac-191">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../../../relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="29dac-192">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="29dac-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="29dac-193">Fortsetzen einer Verfügbarkeitsdatenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29dac-193">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="29dac-194">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29dac-194">See Also</span></span>  
 <span data-ttu-id="29dac-195">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29dac-195">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="29dac-196">Fortsetzen einer Verfügbarkeitsdatenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29dac-196">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
