---
title: Erstellen einer Verfügbarkeitsgruppe (SQL Server PowerShell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: bc69a7df-20fa-41e1-9301-11317c5270d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3af9bf896b954e6849c0d491f9ed267655369ccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727138"
---
# <a name="create-an-availability-group-sql-server-powershell"></a><span data-ttu-id="f1123-102">Erstellen einer Verfügbarkeitsgruppe (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f1123-102">Create an Availability Group (SQL Server PowerShell)</span></span>
  <span data-ttu-id="f1123-103">In diesem Thema wird beschrieben, wie PowerShell-Cmdlets zum Erstellen und Konfigurieren einer AlwaysOn-Verfügbarkeitsgruppe mithilfe von PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1123-103">This topic describes how to use PowerShell cmdlets to create and configure an AlwaysOn availability group by using PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f1123-104">Eine *Verfügbarkeitsgruppe* definiert einen Satz von Benutzerdatenbanken, für die als eine einzelne Einheit ein Failover ausgeführt wird, sowie einen Satz von Failoverpartnern, die als *Verfügbarkeitsreplikate*bezeichnet werden und das Failover unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f1123-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, which support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1123-105">Eine Einführung zu Verfügbarkeitsgruppen finden Sie unter [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f1123-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f1123-106">Als Alternative zur Verwendung von PowerShell-Cmdlets können Sie den Assistenten zum Erstellen einer Verfügbarkeitsgruppe oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1123-106">As an alternative to using PowerShell cmdlets, you can use the Create Availability Group wizard or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f1123-107">Weitere Informationen finden Sie unter [Verwenden des Dialogfelds „Neue Verfügbarkeitsgruppe“ &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) oder [Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1123-107">For more information, see [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) or [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1123-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f1123-108">Before You Begin</span></span>  
 <span data-ttu-id="f1123-109">Es wird dringend empfohlen, dass Sie diesen Abschnitt lesen, bevor Sie versuchen, Ihre erste Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1123-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="f1123-110">Voraussetzungen, Einschränkungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f1123-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="f1123-111">Überprüfen Sie vor dem Erstellen einer Verfügbarkeitsgruppe, ob sich die Hostinstanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] jeweils auf verschiedenen WSFC-Knoten (Windows Server-Failoverclustering) eines einzelnen WSFC-Failoverclusters befinden.</span><span class="sxs-lookup"><span data-stu-id="f1123-111">Before creating an availability group, verify that the host instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] each resides on a different Windows Server Failover Clustering (WSFC) node of a single WSFC failover cluster.</span></span> <span data-ttu-id="f1123-112">Stellen Sie auch sicher, dass die Serverinstanzen die anderen Serverinstanzvoraussetzungen erfüllen, dass alle anderen [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]-Anforderungen erfüllt sind und dass Sie die Empfehlungen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f1123-112">Also, verify that your server instances met the other server-instance prerequisites and that all of the other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] requirements are meet and that you are aware of the recommendations.</span></span> <span data-ttu-id="f1123-113">Wenn Sie weitere Informationen wünschen, sollten Sie unbedingt [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="f1123-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1123-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f1123-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1123-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f1123-115">Permissions</span></span>  
 <span data-ttu-id="f1123-116">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** und die CREATE AVAILABILITY GROUP-Serverberechtigung, ALTER ANY AVAILABILITY GROUP-Berechtigung oder CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="f1123-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-powershell-cmdlets"></a><a name="SummaryPSStatements"></a><span data-ttu-id="f1123-117">Zusammenfassung von Tasks und entsprechenden PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f1123-117">Summary of Tasks and Corresponding PowerShell Cmdlets</span></span>  
 <span data-ttu-id="f1123-118">In der folgenden Tabelle sind die grundlegenden Tasks für die Konfiguration einer Verfügbarkeitsgruppe aufgeführt, und es sind die Tasks angegeben, die von PowerShell-Cmdlets unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f1123-118">The following table lists the basic tasks involved in configuring an availability group and indicates those that are supported by PowerShell cmdlets.</span></span> <span data-ttu-id="f1123-119">Die [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Tasks müssen in der Reihenfolge ausgeführt werden, in der sie in der Tabelle dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="f1123-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="f1123-120">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="f1123-120">Task</span></span>|<span data-ttu-id="f1123-121">PowerShell-Cmdlets (falls verfügbar) oder Transact-SQL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f1123-121">PowerShell Cmdlets (if Available) or Transact-SQL Statement</span></span>|<span data-ttu-id="f1123-122">Wo der Task auszuführen ist**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="f1123-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|--------------------------------------------------------------------|-------------------------------------------|  
|<span data-ttu-id="f1123-123">Erstellen eines Datenbankspiegelungs-Endpunkts (einmal pro [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz)</span><span class="sxs-lookup"><span data-stu-id="f1123-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|`New-SqlHadrEndPoint`|<span data-ttu-id="f1123-124">Führen Sie diesen Task auf jeder Serverinstanz aus, auf der der Datenbankspiegelungs-Endpunkt fehlt.</span><span class="sxs-lookup"><span data-stu-id="f1123-124">Execute on each server instance that lacks database mirroring endpoint.</span></span><br /><br /> <span data-ttu-id="f1123-125">Hinweis: Verwenden Sie `Set-SqlHadrEndpoint`, um einen vorhandenen Datenbankspiegelungs-Endpunkt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f1123-125">Note: To alter an existing database mirroring endpoint, use `Set-SqlHadrEndpoint`.</span></span>|  
|<span data-ttu-id="f1123-126">Erstellen der Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f1123-126">Create availability group</span></span>|<span data-ttu-id="f1123-127">Verwenden Sie zuerst das `New-SqlAvailabilityReplica`-Cmdlet mit dem `-AsTemplate`-Parameter, um ein Verfügbarkeitsreplikatobjekt im Arbeitsspeicher für jedes der beiden Verfügbarkeitsreplikate zu erstellen, die Sie in die Verfügbarkeitsgruppe einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1123-127">First, use the `New-SqlAvailabilityReplica` cmdlet with the `-AsTemplate` parameter to create an in-memory availability-replica object for each of the two availability replicas that you plan to include in the availability group.</span></span><br /><br /> <span data-ttu-id="f1123-128">Erstellen Sie dann die Verfügbarkeitsgruppe mithilfe des `New-SqlAvailabilityGroup`-Cmdlets, und verweisen Sie auf die Verfügbarkeitsreplikatobjekte.</span><span class="sxs-lookup"><span data-stu-id="f1123-128">Then, create the availability group by using the `New-SqlAvailabilityGroup` cmdlet and referencing your availability-replica objects.</span></span>|<span data-ttu-id="f1123-129">Führen Sie diesen Task auf der Serverinstanz aus, auf der das anfängliche primäre Replikat gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1123-129">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="f1123-130">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f1123-130">Join secondary replica to availability group</span></span>|`Join-SqlAvailabilityGroup`|<span data-ttu-id="f1123-131">Führen Sie diesen Task auf jeder Serverinstanz aus, auf der ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-131">Execute on each server instance that is hosts a secondary replica.</span></span>|  
|<span data-ttu-id="f1123-132">Vorbereiten der sekundären Datenbank</span><span class="sxs-lookup"><span data-stu-id="f1123-132">Prepare the secondary database</span></span>|<span data-ttu-id="f1123-133">`Backup-SqlDatabase` und `Restore-SqlDatabase`</span><span class="sxs-lookup"><span data-stu-id="f1123-133">`Backup-SqlDatabase` and `Restore-SqlDatabase`</span></span>|<span data-ttu-id="f1123-134">Erstellen Sie Sicherungen auf der Serverinstanz, auf der das primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="f1123-135">Stellen Sie mit dem Wiederherstellungsparameter `NoRecovery` Sicherungen auf jeder Serverinstanz wieder her, auf der ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-135">Restore backups on each server instance that hosts a secondary replica, using the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="f1123-136">Wenn sich die Dateipfade zwischen den Computern unterscheiden, die das primäre Replikat und das sekundäre Zielreplikat hosten, verwenden Sie ebenfalls den Wiederherstellungsparameter `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="f1123-136">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>|  
|<span data-ttu-id="f1123-137">Starten der Datensynchronisierung durch Hinzufügen der einzelnen sekundären Datenbanken zur Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f1123-137">Start data synchronization by joining each secondary database to availability group</span></span>|`Add-SqlAvailabilityDatabase`|<span data-ttu-id="f1123-138">Führen Sie diesen Task auf jeder Serverinstanz aus, auf der ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="f1123-139">**<sup>\*</sup>** Um eine bestimmte Aufgabe auszuführen, ändern `cd` Sie das Verzeichnis () in die angegebene Serverinstanz bzw. die angegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="f1123-139">**<sup>\*</sup>**  To perform a given task, change directory (`cd`) to the indicated server instance or instances.</span></span>  
  
###  <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><a name="PsProviderLinks"></a><span data-ttu-id="f1123-140">So richten Sie den SQL Server PowerShell-Anbieter ein und verwenden ihn</span><span class="sxs-lookup"><span data-stu-id="f1123-140">To Set Up and Use the SQL Server PowerShell Provider</span></span>  
  
-   [<span data-ttu-id="f1123-141">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f1123-141">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="f1123-142">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1123-142">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="using-powershell-to-create-and-configure-an-availability-group"></a><a name="PowerShellProcedure"></a><span data-ttu-id="f1123-143">Verwenden von PowerShell zum Erstellen und Konfigurieren einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="f1123-143">Using PowerShell to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1123-144">Um die Syntax und ein Beispiel für ein bestimmtes Cmdlet anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f1123-144">To view the syntax and an example of a given cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f1123-145">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f1123-145">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
1.  <span data-ttu-id="f1123-146">Wechseln Sie in das Verzeichnis (`cd`) der Serverinstanz, die das primäre Replikat hosten soll.</span><span class="sxs-lookup"><span data-stu-id="f1123-146">Change directory (`cd`) to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="f1123-147">Erstellen Sie für das primäre Replikat ein Verfügbarkeitsreplikatobjekt im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f1123-147">Create an in-memory availability-replica object for the primary replica.</span></span>  
  
3.  <span data-ttu-id="f1123-148">Erstellen Sie für jedes der sekundären Replikate ein Verfügbarkeitsreplikatobjekt im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f1123-148">Create an in-memory availability-replica object for each of the secondary replicas.</span></span>  
  
4.  <span data-ttu-id="f1123-149">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f1123-149">Create the availability group.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1123-150">Die maximale Länge eines Verfügbarkeitsgruppennamens beträgt 128 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f1123-150">The maximum length for an availability group name is 128 characters.</span></span>  
  
5.  <span data-ttu-id="f1123-151">Verknüpfen Sie das neue sekundäre Replikat mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f1123-151">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="f1123-152">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-152">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
6.  <span data-ttu-id="f1123-153">Erstellen Sie für jede Datenbank in der Verfügbarkeitsgruppe eine sekundäre Datenbank, indem Sie letzte Sicherungen der primären Datenbank mit RESTORE WITH NORECOVERY wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f1123-153">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span>  
  
7.  <span data-ttu-id="f1123-154">Verknüpfen Sie alle neuen sekundären Datenbanken mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f1123-154">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="f1123-155">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-155">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="f1123-156">Verwenden Sie optional den `dir`-Befehl von Windows, um den Inhalt der neuen Verfügbarkeitsgruppe zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f1123-156">Optionally, use the Windows `dir` command to verify the contents of the new availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1123-157">Wenn die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienstkonten der Serverinstanzen unter unterschiedlichen Domänenbenutzerkonten ausgeführt werden, erstellen Sie auf jeder Serverinstanz eine Anmeldung für die andere Serverinstanz, und gewähren Sie dieser Anmeldung eine CONNECT-Berechtigung zum Zugreifen auf den lokalen Datenbankspiegelungs-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="f1123-157">If the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service accounts of the server instances run under different domain user accounts, on each server instance, create a login for the other server instance and grant this login CONNECT permission to the local database mirroring endpoint.</span></span>  
  
##  <a name="example-using-powershell-to-create-an-availability-group"></a><a name="ExampleConfigureGroup"></a><span data-ttu-id="f1123-158">Beispiel: Verwenden von PowerShell zum Erstellen einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="f1123-158">Example: Using PowerShell to Create an Availability Group</span></span>  
 <span data-ttu-id="f1123-159">Im folgenden PowerShell-Beispiel wird eine einfache Verfügbarkeitsgruppe mit dem Namen `MyAG` erstellt und konfiguriert, die über zwei Verfügbarkeitsreplikate und eine Verfügbarkeitsdatenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="f1123-159">The following PowerShell example creates and configures a simple availability group named `MyAG` with two availability replicas and one availability database.</span></span> <span data-ttu-id="f1123-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1123-160">The example:</span></span>  
  
1.  <span data-ttu-id="f1123-161">Sichert `MyDatabase` und das dazugehörige Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="f1123-161">Backs up `MyDatabase` and its transaction log.</span></span>  
  
2.  <span data-ttu-id="f1123-162">Stellt `MyDatabase` und das dazugehörige Transaktionsprotokoll mithilfe der Option `-NoRecovery` wieder her.</span><span class="sxs-lookup"><span data-stu-id="f1123-162">Restores `MyDatabase` and its transaction log, using the `-NoRecovery` option.</span></span>  
  
3.  <span data-ttu-id="f1123-163">Erstellt eine speicherinterne Darstellung des primären Replikats, die von der lokalen Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (mit dem Namen `PrimaryComputer\Instance`) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-163">Creates an in-memory representation of the primary replica, which will be hosted by the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `PrimaryComputer\Instance`).</span></span>  
  
4.  <span data-ttu-id="f1123-164">Erstellt eine speicherinterne Darstellung des sekundären Replikats, die von einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (mit dem Namen `SecondaryComputer\Instance`) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f1123-164">Creates an in-memory representation of the secondary replica, which will be hosted by an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `SecondaryComputer\Instance`).</span></span>  
  
5.  <span data-ttu-id="f1123-165">Erstellt eine Verfügbarkeitsgruppe mit dem Namen `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="f1123-165">Creates an availability group named `MyAG`.</span></span>  
  
6.  <span data-ttu-id="f1123-166">Verknüpft das sekundäre Replikat mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f1123-166">Joins the secondary replica to the availability group.</span></span>  
  
7.  <span data-ttu-id="f1123-167">Verknüpft die sekundäre Datenbank mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f1123-167">Joins the secondary database to the availability group.</span></span>  
  
```powershell
# Backup my database and its log on the primary  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "PrimaryComputer\Instance"  
  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "PrimaryComputer\Instance" `  
    -BackupAction Log   
  
# Restore the database and log on the secondary (using NO RECOVERY)  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -NoRecovery  
  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -RestoreAction Log `  
    -NoRecovery  
  
# Create an in-memory representation of the primary replica.  
$primaryReplica = New-SqlAvailabilityReplica `  
    -Name "PrimaryComputer\Instance" `  
    -EndpointURL "TCP://PrimaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create an in-memory representation of the secondary replica.  
$secondaryReplica = New-SqlAvailabilityReplica `  
    -Name "SecondaryComputer\Instance" `  
    -EndpointURL "TCP://SecondaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create the availability group  
New-SqlAvailabilityGroup `  
    -Name "MyAG" `  
    -Path "SQLSERVER:\SQL\PrimaryComputer\Instance" `  
    -AvailabilityReplica @($primaryReplica,$secondaryReplica) `  
    -Database "MyDatabase"  
  
# Join the secondary replica to the availability group.  
Join-SqlAvailabilityGroup -Path "SQLSERVER:\SQL\SecondaryComputer\Instance" -Name "MyAG"  
  
# Join the secondary database to the availability group.  
Add-SqlAvailabilityDatabase -Path "SQLSERVER:\SQL\SecondaryComputer\Instance\AvailabilityGroups\MyAG" -Database "MyDatabase"  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f1123-168">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f1123-168">Related Tasks</span></span>  
 <span data-ttu-id="f1123-169">**So konfigurieren Sie eine Serverinstanz für AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="f1123-169">**To configure a server instance for AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="f1123-170">Aktivieren und Deaktivieren von Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-170">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="f1123-171">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-171">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
 <span data-ttu-id="f1123-172">**So konfigurieren Sie Verfügbarkeitsgruppen- und Replikateigenschaften**</span><span class="sxs-lookup"><span data-stu-id="f1123-172">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="f1123-173">Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-173">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f1123-174">Ändern des Failovermodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-174">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f1123-175">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-175">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f1123-176">Konfigurieren der flexiblen Failoverrichtlinie zum Steuern der Bedingungen für ein automatisches Failover (AlwaysOn-Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="f1123-176">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="f1123-177">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-177">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="f1123-178">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-178">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="f1123-179">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-179">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f1123-180">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-180">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f1123-181">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-181">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="f1123-182">**So schließen Sie die Konfiguration von Verfügbarkeitsgruppen ab**</span><span class="sxs-lookup"><span data-stu-id="f1123-182">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="f1123-183">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-183">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f1123-184">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-184">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f1123-185">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-185">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f1123-186">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-186">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="f1123-187">**Alternative Möglichkeiten zum Erstellen einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="f1123-187">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="f1123-188">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-188">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f1123-189">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-189">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f1123-190">Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-190">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
 <span data-ttu-id="f1123-191">**Problembehandlung für die AlwaysOn-Verfügbarkeitsgruppenkonfiguration**</span><span class="sxs-lookup"><span data-stu-id="f1123-191">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="f1123-192">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfiguration (SQL Server) gelöscht</span><span class="sxs-lookup"><span data-stu-id="f1123-192">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="f1123-193">Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-193">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f1123-194">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f1123-194">Related Content</span></span>  
  
-   <span data-ttu-id="f1123-195">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="f1123-195">**Blogs:**</span></span>  
  
     [<span data-ttu-id="f1123-196">AlwaysON - HADRON-Lernreihe: Nutzung des Arbeitsthreadpools für HADRON-fähige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="f1123-196">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="f1123-197">Konfigurieren von AlwaysOn mit SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1123-197">Configuring AlwaysOn with SQL Server PowerShell</span></span>](https://blogs.msdn.com/b/sqlalwayson/archive/2012/02/03/configuring-alwayson-with-sql-server-powershell.aspx)  
  
     [<span data-ttu-id="f1123-198">SQL Server AlwaysOn-Teamblogs: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="f1123-198">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="f1123-199">CSS SQL Server-Technikblogs</span><span class="sxs-lookup"><span data-stu-id="f1123-199">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="f1123-200">**Videos:**</span><span class="sxs-lookup"><span data-stu-id="f1123-200">**Videos:**</span></span>  
  
     [<span data-ttu-id="f1123-201">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 1: Einführung in die nächste Generation von Lösungen mit hoher Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f1123-201">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="f1123-202">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 2: Erstellen einer unternehmenswichtigen Lösung für hohe Verfügbarkeit mit AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f1123-202">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="f1123-203">**Whitepaper:**</span><span class="sxs-lookup"><span data-stu-id="f1123-203">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="f1123-204">Microsoft SQL Server AlwaysOn-Lösungshandbuch zu hoher Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="f1123-204">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="f1123-205">Microsoft-Whitepapers für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="f1123-205">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="f1123-206">Whitepapers des SQL Server-Kundenberatungsteams</span><span class="sxs-lookup"><span data-stu-id="f1123-206">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="f1123-207">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1123-207">See Also</span></span>  
 [<span data-ttu-id="f1123-208">Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1123-208">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)   
