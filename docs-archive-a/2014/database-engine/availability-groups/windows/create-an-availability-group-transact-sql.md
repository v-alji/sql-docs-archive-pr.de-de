---
title: Erstellen einer Verfügbarkeitsgruppe (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 8b0a6301-8b79-4415-b608-b40876f30066
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57a494af168a8f5572bafe93f8fb47b22a954a19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727133"
---
# <a name="create-an-availability-group-transact-sql"></a><span data-ttu-id="3233f-102">Erstellen einer Verfügbarkeitsgruppe (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3233f-102">Create an Availability Group (Transact-SQL)</span></span>
  <span data-ttu-id="3233f-103">In diesem Thema wird beschrieben, wie [!INCLUDE[tsql](../../../includes/tsql-md.md)] zum Erstellen und Konfigurieren einer Verfügbarkeitsgruppe für Instanzen von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit aktivierter [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-103">This topic describes how to use [!INCLUDE[tsql](../../../includes/tsql-md.md)] to create and configure an availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] on which the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature is enabled.</span></span> <span data-ttu-id="3233f-104">Eine *Verfügbarkeitsgruppe* definiert einen Satz von Benutzerdatenbanken, für die als eine einzelne Einheit ein Failover ausgeführt wird, sowie einen Satz von Failoverpartnern, die als *Verfügbarkeitsreplikate*bezeichnet werden, die Failover unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3233f-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3233f-105">Eine Einführung zu Verfügbarkeitsgruppen finden Sie unter [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3233f-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="3233f-106">Als Alternative zur Verwendung von [!INCLUDE[tsql](../../../includes/tsql-md.md)]können Sie den Assistenten zum Erstellen einer Verfügbarkeitsgruppe oder [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="3233f-106">As an alternative to using [!INCLUDE[tsql](../../../includes/tsql-md.md)], you can use the Create Availability Group wizard or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell cmdlets.</span></span> <span data-ttu-id="3233f-107">Weitere Informationen finden Sie unter [Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md)[Verwenden des Dialogfelds „Neue Verfügbarkeitsgruppe“ &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)[Erstellen einer Verfügbarkeitsgruppe &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3233f-107">For more information, see [Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), or [Create an Availability Group &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3233f-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3233f-108">Before You Begin</span></span>  
 <span data-ttu-id="3233f-109">Es wird dringend empfohlen, dass Sie diesen Abschnitt lesen, bevor Sie versuchen, Ihre erste Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3233f-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a><span data-ttu-id="3233f-110">Voraussetzungen, Einschränkungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="3233f-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="3233f-111">Überprüfen Sie vor dem Erstellen einer Verfügbarkeitsgruppe, ob sich die Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , die Verfügbarkeitsreplikate hosten, auf verschiedenen WSFC-Konten (Windows Server Failover Clustering) des gleichen WSFC-Failoverclusters befinden.</span><span class="sxs-lookup"><span data-stu-id="3233f-111">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="3233f-112">Stellen Sie außerdem sicher, dass alle Serverinstanzen alle anderen [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Voraussetzungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3233f-112">Also, verify that each of the server instance meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="3233f-113">Wenn Sie weitere Informationen wünschen, sollten Sie unbedingt [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="3233f-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3233f-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3233f-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3233f-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3233f-115">Permissions</span></span>  
 <span data-ttu-id="3233f-116">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** und die CREATE AVAILABILITY GROUP-Serverberechtigung, ALTER ANY AVAILABILITY GROUP-Berechtigung oder CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="3233f-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-transact-sql-statements"></a><a name="SummaryTsqlStatements"></a> <span data-ttu-id="3233f-117">Zusammenfassung von Tasks und entsprechenden Transact-SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3233f-117">Summary of Tasks and Corresponding Transact-SQL Statements</span></span>  
 <span data-ttu-id="3233f-118">In der folgenden Tabelle sind die grundlegenden Tasks aufgeführt, die zum Erstellen und Konfigurieren einer Verfügbarkeitsgruppe erforderlich sind, und es ist angegeben, welche [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisungen für diese Tasks zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="3233f-118">The following table lists the basic tasks involved in creating and configuring an availability group and indicates which [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to use for these tasks.</span></span> <span data-ttu-id="3233f-119">Die [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Tasks müssen in der Reihenfolge ausgeführt werden, in der sie in der Tabelle dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="3233f-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="3233f-120">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="3233f-120">Task</span></span>|<span data-ttu-id="3233f-121">Transact-SQL-Anweisung(en)</span><span class="sxs-lookup"><span data-stu-id="3233f-121">Transact-SQL Statement(s)</span></span>|<span data-ttu-id="3233f-122">Wo der Task auszuführen ist**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="3233f-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|----------------------------------|-------------------------------------------|  
|<span data-ttu-id="3233f-123">Erstellen eines Datenbankspiegelungs-Endpunkts (einmal pro [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz)</span><span class="sxs-lookup"><span data-stu-id="3233f-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|<span data-ttu-id="3233f-124">[Endpunkt](/sql/t-sql/statements/create-endpoint-transact-sql) *EndpointName* erstellen... für DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="3233f-124">[CREATE ENDPOINT](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... FOR DATABASE_MIRRORING</span></span>|<span data-ttu-id="3233f-125">Führen Sie diesen Task auf jeder Serverinstanz aus, auf der der Datenbankspiegelungs-Endpunkt fehlt.</span><span class="sxs-lookup"><span data-stu-id="3233f-125">Execute on each server instance that lacks database mirroring endpoint.</span></span>|  
|<span data-ttu-id="3233f-126">Erstellen der Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="3233f-126">Create availability group</span></span>|[<span data-ttu-id="3233f-127">CREATE AVAILABILITY GROUP</span><span class="sxs-lookup"><span data-stu-id="3233f-127">CREATE AVAILABILITY GROUP</span></span>](/sql/t-sql/statements/create-availability-group-transact-sql)|<span data-ttu-id="3233f-128">Führen Sie diesen Task auf der Serverinstanz aus, auf der das anfängliche primäre Replikat gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3233f-128">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="3233f-129">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="3233f-129">Join secondary replica to availability group</span></span>|<span data-ttu-id="3233f-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *Gruppenname* JOIN</span><span class="sxs-lookup"><span data-stu-id="3233f-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span></span>|<span data-ttu-id="3233f-131">Führen Sie diesen Task auf jeder Serverinstanz aus, auf der ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-131">Execute on each server instance that hosts a secondary replica.</span></span>|  
|<span data-ttu-id="3233f-132">Vorbereiten der sekundären Datenbank</span><span class="sxs-lookup"><span data-stu-id="3233f-132">Prepare the secondary database</span></span>|<span data-ttu-id="3233f-133">[Sichern](/sql/t-sql/statements/backup-transact-sql) und [Wiederherstellen](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3233f-133">[BACKUP](/sql/t-sql/statements/backup-transact-sql) and [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>|<span data-ttu-id="3233f-134">Erstellen Sie Sicherungen auf der Serverinstanz, auf der das primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="3233f-135">Stellen Sie mit RESTORE WITH NORECOVERY Sicherungen auf jeder Serverinstanz wieder her, auf der ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-135">Restore backups on each server instance that hosts a secondary replica, using RESTORE WITH NORECOVERY.</span></span>|  
|<span data-ttu-id="3233f-136">Starten der Datensynchronisierung durch Hinzufügen der einzelnen sekundären Datenbanken zur Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="3233f-136">Start data synchronization by joining each secondary database to availability group</span></span>|<span data-ttu-id="3233f-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *Datenbankname* SET HADR AVAILABILITY GROUP = *Gruppenname*</span><span class="sxs-lookup"><span data-stu-id="3233f-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>|<span data-ttu-id="3233f-138">Führen Sie diesen Task auf jeder Serverinstanz aus, auf der ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="3233f-139">**<sup>\*</sup>** Stellen Sie eine Verbindung mit der angegebenen Serverinstanz her, um eine bestimmte Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3233f-139">**<sup>\*</sup>**  To perform a given task, connect to the indicated server instance or instances.</span></span>  
  
##  <a name="using-transact-sql-to-create-and-configure-an-availability-group"></a><a name="TsqlProcedure"></a><span data-ttu-id="3233f-140">Verwenden von Transact-SQL zum Erstellen und Konfigurieren einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="3233f-140">Using Transact-SQL to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3233f-141"> Eine Vorgehensweise für eine Beispielkonfiguration mit Codebeispielen für jede dieser [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisungen finden Sie in [Beispiel: Konfigurieren einer Verfügbarkeitsgruppe, die die Windows-Authentifizierung verwendet](#ExampleConfigAGWinAuth).</span><span class="sxs-lookup"><span data-stu-id="3233f-141">For a sample configuration procedure containing code examples of each these [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements, see [Example: Configuring an Availability Group that Uses Windows Authentication](#ExampleConfigAGWinAuth).</span></span>  
  
1.  <span data-ttu-id="3233f-142">Stellen Sie eine Verbindung mit der Serverinstanz her, auf der das primäre Replikat gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3233f-142">Connect to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="3233f-143">Erstellen Sie die Verfügbarkeits Gruppe mithilfe der [Create Availability Group](/sql/t-sql/statements/create-availability-group-transact-sql) - [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3233f-143">Create the availability group by using the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
3.  <span data-ttu-id="3233f-144">Verknüpfen Sie das neue sekundäre Replikat mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3233f-144">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="3233f-145">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-145">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="3233f-146">Erstellen Sie für jede Datenbank in der Verfügbarkeitsgruppe eine sekundäre Datenbank, indem Sie letzte Sicherungen der primären Datenbank mit RESTORE WITH NORECOVERY wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3233f-146">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="3233f-147">Weitere Informationen finden Sie unter [Beispiel: Einrichten einer Verfügbarkeitsgruppe mithilfe der Windows-Authentifizierung (Transact-SQL)](create-an-availability-group-transact-sql.md)ab dem Schritt, in dem die Datenbanksicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-147">For more information, see [Example: Setting Up an Availability Group Using Windows Authentication (Transact-SQL)](create-an-availability-group-transact-sql.md), starting with the step that restores the database backup.</span></span>  
  
5.  <span data-ttu-id="3233f-148">Verknüpfen Sie alle neuen sekundären Datenbanken mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3233f-148">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="3233f-149">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="3233f-149">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="example-configuring-an-availability-group-that-uses-windows-authentication"></a><a name="ExampleConfigAGWinAuth"></a> <span data-ttu-id="3233f-150">Beispiel: Konfigurieren einer Verfügbarkeitsgruppe, die die Windows-Authentifizierung verwendet</span><span class="sxs-lookup"><span data-stu-id="3233f-150">Example: Configuring an Availability Group that Uses Windows Authentication</span></span>  
 <span data-ttu-id="3233f-151">In diesem Beispiel wird eine Beispiel- [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Konfigurationsprozedur erstellt, die [!INCLUDE[tsql](../../../includes/tsql-md.md)] zum Einrichten von Datenbankspiegelungs-Endpunkten, die die Windows-Authentifizierung verwenden, sowie zum Erstellen und Konfigurieren einer Verfügbarkeitsgruppe und deren sekundärer Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="3233f-151">This example creates a sample [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration procedure that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to set up database mirroring endpoints that use Windows Authentication and to create and configure an availability group and its secondary databases.</span></span>  
  
 <span data-ttu-id="3233f-152">Dieses Beispiel enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="3233f-152">This example contains the following sections:</span></span>  
  
-   [<span data-ttu-id="3233f-153">Voraussetzungen für die Verwendung der Beispiel Konfigurations Prozedur</span><span class="sxs-lookup"><span data-stu-id="3233f-153">Prerequisites for Using the Sample Configuration Procedure</span></span>](#PrerequisitesForExample)  
  
-   [<span data-ttu-id="3233f-154">Beispielkonfigurationsprozedur</span><span class="sxs-lookup"><span data-stu-id="3233f-154">Sample Configuration Procedure</span></span>](#SampleProcedure)  
  
-   [<span data-ttu-id="3233f-155">Vollständiges Codebeispiel für Beispielkonfigurationsprozedur</span><span class="sxs-lookup"><span data-stu-id="3233f-155">Complete Code Example for Sample Configuration Procedure</span></span>](#CompleteCodeExample)  
  
###  <a name="prerequisites-for-using-the-sample-configuration-procedure"></a><a name="PrerequisitesForExample"></a> <span data-ttu-id="3233f-156">Erforderliche Komponenten für die Verwendung der Beispielkonfigurationsprozedur</span><span class="sxs-lookup"><span data-stu-id="3233f-156">Prerequisites for Using the Sample Configuration Procedure</span></span>  
 <span data-ttu-id="3233f-157">Diese Beispielprozedur weist die folgenden Anforderungen auf:</span><span class="sxs-lookup"><span data-stu-id="3233f-157">This sample procedure has the following requirements:</span></span>  
  
-   <span data-ttu-id="3233f-158">Die Serverinstanzen müssen [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3233f-158">The server instances must support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="3233f-159">Weitere Informationen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen&#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="3233f-159">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="3233f-160">Zwei Beispieldatenbanken, *MyDb1* und *MyDb2*, müssen auf der Serverinstanz vorhanden sein, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="3233f-160">Two sample databases, *MyDb1* and *MyDb2*, must exist on the server instance that will host the primary replica.</span></span> <span data-ttu-id="3233f-161">In den folgenden Codebeispielen werden diese beiden Datenbanken erstellt und konfiguriert, und es wird eine vollständige Sicherung jeder Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="3233f-161">The following code examples create and configure these two databases and create a full backup of each.</span></span> <span data-ttu-id="3233f-162">Führen Sie diese Codebeispiele auf der Serverinstanz aus, auf der Beispielverfügbarkeitsgruppe erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3233f-162">Execute these code examples on the server instance on which you intend to create the sample availability group.</span></span> <span data-ttu-id="3233f-163">Auf dieser Serverinstanz wird das ursprüngliche primäre Replikat der Beispielverfügbarkeitsgruppe gehostet.</span><span class="sxs-lookup"><span data-stu-id="3233f-163">This server instance will host the initial primary replica of the sample availability group.</span></span>  
  
    1.  <span data-ttu-id="3233f-164">Im folgenden [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Beispiel werden diese Datenbanken erstellt und so geändert, dass das vollständige Wiederherstellungsmodell verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="3233f-164">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] example creates these databases and alters them to use the full recovery model:</span></span>  
  
        ```sql
        -- Create sample databases:  
        CREATE DATABASE MyDb1;  
        GO  
        ALTER DATABASE MyDb1 SET RECOVERY FULL;  
        GO  
  
        CREATE DATABASE MyDb2;  
        GO  
        ALTER DATABASE MyDb2 SET RECOVERY FULL;  
        GO  
        ```  
  
    2.  <span data-ttu-id="3233f-165">Im folgenden Codebeispiel wird eine vollständige Datenbanksicherung von *MyDb1* und *MyDb2*erstellt.</span><span class="sxs-lookup"><span data-stu-id="3233f-165">The following code example creates a full database backup of *MyDb1* and *MyDb2*.</span></span> <span data-ttu-id="3233f-166">In diesem Codebeispiel wird eine fiktive Sicherungs Freigabe verwendet: \\ \\ *File Server* \\ *sqlbackups*.</span><span class="sxs-lookup"><span data-stu-id="3233f-166">This code example uses a fictional backup share, \\\\*FILESERVER*\\*SQLbackups*.</span></span>  
  
        ```sql
        -- Backup sample databases:  
        BACKUP DATABASE MyDb1   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
            WITH FORMAT  
        GO  
  
        BACKUP DATABASE MyDb2   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
            WITH FORMAT  
        GO
        ```  
  
###  <a name="sample-configuration-procedure"></a><a name="SampleProcedure"></a> <span data-ttu-id="3233f-167">Beispielkonfigurationsprozedur</span><span class="sxs-lookup"><span data-stu-id="3233f-167">Sample Configuration Procedure</span></span>  
 <span data-ttu-id="3233f-168">In dieser Beispielkonfiguration wird das Verfügbarkeitsreplikat auf zwei eigenständigen Serverinstanzen erstellt, deren Dienstkonten unter unterschiedlichen – aber vertrauenswürdigen – Domänen (`DOMAIN1` und `DOMAIN2`) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3233f-168">In this sample configuration, the availability replica will be created on two stand-alone server instances whose service accounts run under different, but trusted, domains (`DOMAIN1` and `DOMAIN2`).</span></span>  
  
 <span data-ttu-id="3233f-169">In der folgenden Tabelle finden Sie eine Zusammenfassung der in dieser Beispielkonfiguration verwendeten Werte.</span><span class="sxs-lookup"><span data-stu-id="3233f-169">The following table summarizes the values used in this sample configuration.</span></span>  
  
|<span data-ttu-id="3233f-170">Ursprüngliche Rolle</span><span class="sxs-lookup"><span data-stu-id="3233f-170">Initial role</span></span>|<span data-ttu-id="3233f-171">System</span><span class="sxs-lookup"><span data-stu-id="3233f-171">System</span></span>|<span data-ttu-id="3233f-172">Hosten der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz</span><span class="sxs-lookup"><span data-stu-id="3233f-172">Host [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instance</span></span>|  
|------------------|------------|---------------------------------------------|  
|<span data-ttu-id="3233f-173">Primär</span><span class="sxs-lookup"><span data-stu-id="3233f-173">Primary</span></span>|`COMPUTER01`|`AgHostInstance`|  
|<span data-ttu-id="3233f-174">Secondary</span><span class="sxs-lookup"><span data-stu-id="3233f-174">Secondary</span></span>|`COMPUTER02`|<span data-ttu-id="3233f-175">Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="3233f-175">Default instance.</span></span>|  
  
1.  <span data-ttu-id="3233f-176">Erstellen Sie einen Datenbankspiegelungs-Endpunkt namens *dbm_endpoint* auf der Serverinstanz, auf der Sie die Verfügbarkeitsgruppe erstellen möchten (dies ist eine Instanz namens `AgHostInstance` auf `COMPUTER01`).</span><span class="sxs-lookup"><span data-stu-id="3233f-176">Create a database mirroring endpoint named *dbm_endpoint* on the server instance on which you plan to create the availability group (this is an instance named `AgHostInstance` on `COMPUTER01`).</span></span> <span data-ttu-id="3233f-177">Dieser Endpunkt verwendet Port 7022.</span><span class="sxs-lookup"><span data-stu-id="3233f-177">This endpoint uses port 7022.</span></span> <span data-ttu-id="3233f-178">Beachten Sie, dass die Serverinstanz, auf der Sie die Verfügbarkeitsgruppe erstellen, das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="3233f-178">Note that the server instance on which you create the availability group will host the primary replica.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the primary replica:  
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
2.  <span data-ttu-id="3233f-179">Erstellen Sie einen Endpunkt *dbm_endpoint* auf der Serverinstanz, die das sekundäre Replikat hostet (dies ist die Standardserverinstanz auf `COMPUTER02`).</span><span class="sxs-lookup"><span data-stu-id="3233f-179">Create an endpoint *dbm_endpoint* on the server instance that will host the secondary replica (this is the default server instance on `COMPUTER02`).</span></span> <span data-ttu-id="3233f-180">Dieser Endpunkt verwendet Port 5022.</span><span class="sxs-lookup"><span data-stu-id="3233f-180">This endpoint uses port 5022.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the secondary replica:   
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=5022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
3.  > [!NOTE]  
    >  <span data-ttu-id="3233f-181">Wenn die Dienstkonten der Serverinstanzen, auf denen die Verfügbarkeitsreplikate gehostet werden sollen, unter dem gleichen Domänenkonto ausgeführt wurden, ist dieser Schritt nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3233f-181">If the service accounts of the server instances that are to host your availability replicas run under the same domain account this step is unnecessary.</span></span> <span data-ttu-id="3233f-182">Überspringen Sie den Schritt, und fahren Sie gleich mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="3233f-182">Skip it and go directly to the next step.</span></span>  
  
     <span data-ttu-id="3233f-183">Wenn die Dienstkonten der Serverinstanzen unter unterschiedlichen Domänenbenutzern ausgeführt werden, erstellen Sie auf jeder Serverinstanz eine Anmeldung für die andere Serverinstanz, und gewähren Sie dieser Anmeldung Berechtigungen zum Zugreifen auf den lokalen Datenbankspiegelungs-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="3233f-183">If the service accounts of the server instances run under different domain users, on each server instance, create a login for the other server instance and grant this login permission to access the local database mirroring endpoint.</span></span>  
  
     <span data-ttu-id="3233f-184">Im folgenden Codebeispiel sind die [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisungen zum Erstellen einer Anmeldung und zum Gewähren der Berechtigung für einen Endpunkt für die Anmeldung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3233f-184">The following code example shows the [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements for creating a login and granting it permission on an endpoint.</span></span> <span data-ttu-id="3233f-185">Das Domänenkonto der Remoteserverinstanz wird hier als *domain_name*\\*user_name*dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3233f-185">The domain account of the remote server instance is represented here as *domain_name*\\*user_name*.</span></span>  
  
    ```sql
    -- If necessary, create a login for the service account, domain_name\user_name  
    -- of the server instance that will host the other replica:  
    USE master;  
    GO  
    CREATE LOGIN [domain_name\user_name] FROM WINDOWS;  
    GO  
    -- And Grant this login connect permissions on the endpoint:  
    GRANT CONNECT ON ENDPOINT::dbm_endpoint   
       TO [domain_name\user_name];  
    GO  
    ```  
  
4.  <span data-ttu-id="3233f-186">Erstellen Sie auf der Serverinstanz, auf der sich die Benutzerdatenbanken befinden, die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3233f-186">On the server instance where the user databases reside, create the availability group.</span></span>  
  
     <span data-ttu-id="3233f-187">Im folgenden Codebeispiel wird eine Verfügbarkeitsgruppe mit dem Namen *MyAG* auf der Serverinstanz erstellt, auf der die Beispieldatenbanken *MyDb1* und *MyDb2*erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3233f-187">The following code example creates an availability group named *MyAG* on the server instance on which the sample databases, *MyDb1* and *MyDb2*, were created.</span></span> <span data-ttu-id="3233f-188">Die lokale Serverinstanz `AgHostInstance`auf *COMPUTER01* wird zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="3233f-188">The local server instance, `AgHostInstance`, on *COMPUTER01* is specified first.</span></span> <span data-ttu-id="3233f-189">Diese Instanz hostet das ursprüngliche primäre Verfügbarkeitsreplikat.</span><span class="sxs-lookup"><span data-stu-id="3233f-189">This instance will host the initial primary replica.</span></span> <span data-ttu-id="3233f-190">Eine Remoteserverinstanz, die Standardserverinstanz auf *COMPUTER02*, wird angegeben, um ein sekundäres Replikat zu hosten.</span><span class="sxs-lookup"><span data-stu-id="3233f-190">A remote server instance, the default server instance on *COMPUTER02*, is specified to host a secondary replica.</span></span> <span data-ttu-id="3233f-191">Beide Verfügbarkeitsreplikate werden konfiguriert, um den Modus mit asynchronem Commit mit manuellem Failover zu verwenden (für Replikate mit asynchronem Commit bedeutet manuelles Failover erzwungenes Failover mit möglichem Datenverlust).</span><span class="sxs-lookup"><span data-stu-id="3233f-191">Both availability replica are configured to use asynchronous-commit mode with manual failover (for asynchronous-commit replicas manual failover means  forced failover with possible data loss).</span></span>  
  
    ```sql
    -- Create the availability group, MyAG:   
    CREATE AVAILABILITY GROUP MyAG   
       FOR   
          DATABASE MyDB1, MyDB2   
       REPLICA ON   
          'COMPUTER01\AgHostInstance' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',   
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             ),  
          'COMPUTER02' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );   
    GO  
    ```  
  
     <span data-ttu-id="3233f-192">Weitere [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Codebeispiele zur Erstellung einer Verfügbarkeitsgruppe finden Sie unter [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3233f-192">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
5.  <span data-ttu-id="3233f-193">Verknüpfen Sie auf der Serverinstanz, die das sekundäre Replikat hostet, das sekundäre Replikat mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3233f-193">On the server instance that hosts the secondary replica, join the secondary replica to the availability group.</span></span>  
  
     <span data-ttu-id="3233f-194">Im folgenden Codebeispiel wird das sekundäre Replikat auf `COMPUTER02` mit der `MyAG` -Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3233f-194">The following code example joins the secondary replica on `COMPUTER02` to the `MyAG` availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join the secondary replica to the availability group:  
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    GO  
    ```  
  
6.  <span data-ttu-id="3233f-195">Auf der Serverinstanz, die das sekundäre Replikat hostet, erstellen Sie die sekundären Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="3233f-195">On the server instance that hosts the secondary replica, create the secondary databases.</span></span>  
  
     <span data-ttu-id="3233f-196">Im folgenden Codebeispiel werden die sekundären Datenbanken *MyDb1* und *MyDb2* erstellt, indem Datenbanksicherungen mit RESTORE WITH NORECOVERY wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3233f-196">The following code example creates the *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- Restore database backups using the WITH NORECOVERY option:  
    RESTORE DATABASE MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NORECOVERY  
    GO  
  
    RESTORE DATABASE MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH NORECOVERY  
    GO
    ```  
  
7.  <span data-ttu-id="3233f-197">Sichern Sie auf der Serverinstanz, die das primäre Replikat hostet, das Transaktionsprotokoll zu jeder der primären Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="3233f-197">On the server instance that hosts the primary replica, back up the transaction log on each of the primary databases.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3233f-198">Wenn Sie eine echte Verfügbarkeitsgruppe konfigurieren, wird empfohlen, dass Sie vor Verwendung dieser Protokollsicherung Protokollsicherungstasks für die primären Datenbanken anhalten, bis Sie die entsprechenden sekundären Datenbanken mit der Verfügbarkeitsgruppe verknüpft haben.</span><span class="sxs-lookup"><span data-stu-id="3233f-198">When you are configuring a real availability group, we recommend that, before taking this log backup, you suspend log backup tasks for your primary databases until you have joined the corresponding secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="3233f-199">Im folgenden Codebeispiel wird eine Transaktionsprotokollsicherung in MyDb1 und MyDb2 erstellt.</span><span class="sxs-lookup"><span data-stu-id="3233f-199">The following code example creates a transaction log backup on MyDb1 and on MyDb2.</span></span>  
  
    ```sql
    -- On the server instance that hosts the primary replica,   
    -- Backup the transaction log on each primary database:  
    BACKUP LOG MyDb1   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NOFORMAT  
    GO  
  
    BACKUP LOG MyDb2   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITHNOFORMAT  
    GO
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="3233f-200">In der Regel muss für jede primäre Datenbank eine Protokollsicherung erstellt und dann in der entsprechenden sekundären Datenbank (mithilfe von WITH NORECOVERY) wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3233f-200">Typically, a log backup must be taken on each primary database and then restored on the corresponding secondary database (using WITH NORECOVERY).</span></span> <span data-ttu-id="3233f-201">Diese Protokollsicherung ist jedoch möglicherweise nicht erforderlich, wenn die Datenbank erst kürzlich erstellt wurde und bisher keine Protokollsicherung vorgenommen wurde oder wenn das Wiederherstellungsmodell soeben von SIMPLE in FULL geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3233f-201">However, this log backup might be unnecessary if the database has just been created and no log backup has been taken yet or the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
8.  <span data-ttu-id="3233f-202">Wenden Sie auf der Serverinstanz, die das sekundäre Replikat hostet, Protokollsicherungen für die sekundären Datenbanken an.</span><span class="sxs-lookup"><span data-stu-id="3233f-202">On the server instance that hosts the secondary replica, apply log backups to the secondary databases.</span></span>  
  
     <span data-ttu-id="3233f-203">Im folgenden Codebeispiel werden Sicherungen auf die sekundären Datenbanken *MyDb1* und *MyDb2* angewendet, indem Datenbanksicherungen mit RESTORE WITH NORECOVERY wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3233f-203">The following code example applies backups to *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3233f-204">Wenn Sie eine echte sekundäre Datenbank vorbereiten, müssen Sie jede Protokollsicherung anwenden, die seit der Datenbanksicherung erstellt wurde, aus der Sie die sekundäre Datenbank erstellt haben. Sie müssen dabei immer mit der frühesten Sicherung beginnen und RESTORE WITH NORECOVERY verwenden.</span><span class="sxs-lookup"><span data-stu-id="3233f-204">When you are preparing a real secondary database, you need to apply every log backup taken since the database backup from which you created the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="3233f-205">Wenn Sie sowohl vollständige als auch differenzielle Datenbanksicherungen wiederherstellen, müssten Sie natürlich nur die nach der differenziellen Sicherung erstellten Protokollsicherungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="3233f-205">Of course, if you restore both full and differential database backups, you would only need to apply the log backups taken after the differential backup.</span></span>  
  
    ```sql
    -- Restore the transaction log on each secondary database,  
    -- using the WITH NORECOVERY option:  
    RESTORE LOG MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    RESTORE LOG MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
9. <span data-ttu-id="3233f-206">Verknüpfen Sie auf der Serverinstanz, die das sekundäre Replikat hostet, die neue sekundäre Datenbank mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3233f-206">On the server instance that hosts the secondary replica, join the new secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="3233f-207">Im folgenden Codebeispiel wird die sekundäre Datenbank *MyDb1* und dann die sekundäre Datenbank *MyDb2* mit der *MyAG* -Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3233f-207">The following code example, joins the *MyDb1* secondary database and then the *MyDb2* secondary databases to the *MyAG* availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join each secondary database to the availability group:  
    ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
    GO  
  
    ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
    GO
    ```  
  
###  <a name="complete-code-example-for-sample-configuration-procedure"></a><a name="CompleteCodeExample"></a> <span data-ttu-id="3233f-208">Vollständiges Codebeispiel für Beispielkonfigurationsprozedur</span><span class="sxs-lookup"><span data-stu-id="3233f-208">Complete Code Example for Sample Configuration Procedure</span></span>  
 <span data-ttu-id="3233f-209">Im folgenden Beispiel werden die Codebeispiele aus allen Schritten der Beispielkonfigurationsprozedur zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="3233f-209">The following example merges the code examples from all the steps of the sample configuration procedure.</span></span> <span data-ttu-id="3233f-210">In der folgenden Tabelle werden die in diesem Codebeispiel verwendeten Platzhalterwerte zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="3233f-210">The following table summarized the placeholder values used in this code example.</span></span> <span data-ttu-id="3233f-211">Weitere Informationen zu den Schritten in diesem Codebeispiel finden Sie unter [Erforderliche Komponenten für die Verwendung der Beispielkonfigurationsprozedur](#PrerequisitesForExample) und [Beispielkonfigurationsprozedur](#SampleProcedure)weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="3233f-211">For more information about the steps in this code example, see [Prerequisites for Using the Sample Configuration Procedure](#PrerequisitesForExample) and [Sample Configuration Procedure](#SampleProcedure), earlier in this topic.</span></span>  
  
|<span data-ttu-id="3233f-212">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="3233f-212">Placeholder</span></span>|<span data-ttu-id="3233f-213">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3233f-213">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3233f-214">\\\\*FILESERVER*\\*SQLbackups*</span><span class="sxs-lookup"><span data-stu-id="3233f-214">\\\\*FILESERVER*\\*SQLbackups*</span></span>|<span data-ttu-id="3233f-215">Fiktive Sicherungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="3233f-215">Fictional backup share.</span></span>|  
|<span data-ttu-id="3233f-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span><span class="sxs-lookup"><span data-stu-id="3233f-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span></span>|<span data-ttu-id="3233f-217">Sicherungsdatei für MyDb1.</span><span class="sxs-lookup"><span data-stu-id="3233f-217">Backup file for MyDb1.</span></span>|  
|<span data-ttu-id="3233f-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span><span class="sxs-lookup"><span data-stu-id="3233f-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span></span>|<span data-ttu-id="3233f-219">Sicherungsdatei für MyDb2.</span><span class="sxs-lookup"><span data-stu-id="3233f-219">Backup file for MyDb2.</span></span>|  
|<span data-ttu-id="3233f-220">*7022*</span><span class="sxs-lookup"><span data-stu-id="3233f-220">*7022*</span></span>|<span data-ttu-id="3233f-221">Jedem Datenbankspiegelungs-Endpunkt zugewiesene Portnummer.</span><span class="sxs-lookup"><span data-stu-id="3233f-221">Port number assigned to each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="3233f-222">*COMPUTER01\AgHostInstance*</span><span class="sxs-lookup"><span data-stu-id="3233f-222">*COMPUTER01\AgHostInstance*</span></span>|<span data-ttu-id="3233f-223">Serverinstanz, die das ursprüngliche primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="3233f-223">Server instance that hosts the initial primary replica.</span></span>|  
|<span data-ttu-id="3233f-224">*COMPUTER02*</span><span class="sxs-lookup"><span data-stu-id="3233f-224">*COMPUTER02*</span></span>|<span data-ttu-id="3233f-225">Serverinstanz, die das ursprüngliche sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="3233f-225">Server instance that hosts the initial secondary replica.</span></span> <span data-ttu-id="3233f-226">Dies ist die Standardserverinstanz auf `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="3233f-226">This is the default server instance on `COMPUTER02`.</span></span>|  
|<span data-ttu-id="3233f-227">*dbm_endpoint*</span><span class="sxs-lookup"><span data-stu-id="3233f-227">*dbm_endpoint*</span></span>|<span data-ttu-id="3233f-228">Für jeden Datenbankspiegelungs-Endpunkt angegebener Name.</span><span class="sxs-lookup"><span data-stu-id="3233f-228">Name specified for each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="3233f-229">*MyAG*</span><span class="sxs-lookup"><span data-stu-id="3233f-229">*MyAG*</span></span>|<span data-ttu-id="3233f-230">Der Name der Beispielsverfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3233f-230">Name of sample availability group.</span></span>|  
|<span data-ttu-id="3233f-231">*MyDb1*</span><span class="sxs-lookup"><span data-stu-id="3233f-231">*MyDb1*</span></span>|<span data-ttu-id="3233f-232">Der Name der ersten Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="3233f-232">Name of first sample database.</span></span>|  
|<span data-ttu-id="3233f-233">*MyDb2*</span><span class="sxs-lookup"><span data-stu-id="3233f-233">*MyDb2*</span></span>|<span data-ttu-id="3233f-234">Der Name der zweiten Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="3233f-234">Name of second sample database.</span></span>|  
|<span data-ttu-id="3233f-235">*DOMAIN1\user1*</span><span class="sxs-lookup"><span data-stu-id="3233f-235">*DOMAIN1\user1*</span></span>|<span data-ttu-id="3233f-236">Dienstkonto der Serverinstanz, auf der das ursprüngliche primäre Replikat gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3233f-236">Service account of the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="3233f-237">*DOMAIN2\user2*</span><span class="sxs-lookup"><span data-stu-id="3233f-237">*DOMAIN2\user2*</span></span>|<span data-ttu-id="3233f-238">Dienstkonto der Serverinstanz, auf der das ursprüngliche primäre sekundäre Replikat gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3233f-238">Service account of the server instance that is to host the initial secondary replica.</span></span>|  
|<span data-ttu-id="3233f-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span><span class="sxs-lookup"><span data-stu-id="3233f-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span></span>|<span data-ttu-id="3233f-240">Endpunkt-URL der AgHostInstance-Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf COMPUTER01.</span><span class="sxs-lookup"><span data-stu-id="3233f-240">Endpoint URL of the AgHostInstance instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER01.</span></span>|  
|<span data-ttu-id="3233f-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span><span class="sxs-lookup"><span data-stu-id="3233f-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span></span>|<span data-ttu-id="3233f-242">Endpunkt-URL der Standardinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf COMPUTER02.</span><span class="sxs-lookup"><span data-stu-id="3233f-242">Endpoint URL of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER02.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="3233f-243">Weitere [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Codebeispiele zur Erstellung einer Verfügbarkeitsgruppe finden Sie unter [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3233f-243">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
```sql
-- on the server instance that will host the primary replica,   
-- create sample databases:  
CREATE DATABASE MyDb1;  
GO  
ALTER DATABASE MyDb1 SET RECOVERY FULL;  
GO  
  
CREATE DATABASE MyDb2;  
GO  
ALTER DATABASE MyDb2 SET RECOVERY FULL;  
GO  
  
-- Backup sample databases:  
BACKUP DATABASE MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FORMAT  
GO  
  
BACKUP DATABASE MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FORMAT  
GO  
  
-- Create the endpoint on the server instance that will host the primary replica:  
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- Create the endpoint on the server instance that will host the secondary replica:   
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the primary replica,   
-- create a login for the service account   
-- of the server instance that will host the secondary replica, DOMAIN2\user2,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
CREATE LOGIN [DOMAIN2\user2] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN2\user2];  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the secondary replica,  
-- create a login for the service account   
-- of the server instance that will host the primary replica, DOMAIN1\user1,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
  
CREATE LOGIN [DOMAIN1\user1] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN1\user1];  
GO  
  
-- On the server instance that will host the primary replica,   
-- create the availability group, MyAG:  
CREATE AVAILABILITY GROUP MyAG   
   FOR   
      DATABASE MyDB1, MyDB2   
   REPLICA ON   
      'COMPUTER01\AgHostInstance' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         ),  
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         );   
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join the secondary replica to the availability group:  
ALTER AVAILABILITY GROUP MyAG JOIN;  
GO  
  
-- Restore database backups onto this server instance, using RESTORE WITH NORECOVERY:  
RESTORE DATABASE MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NORECOVERY  
GO  
  
RESTORE DATABASE MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH NORECOVERY  
GO  
  
-- Back up the transaction log on each primary database:  
BACKUP LOG MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NOFORMAT  
GO  
  
BACKUP LOG MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITHNOFORMAT  
GO  
  
-- Restore the transaction log on each secondary database,  
-- using the WITH NORECOVERY option:  
RESTORE LOG MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FILE=1, NORECOVERY  
GO  
RESTORE LOG MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FILE=1, NORECOVERY  
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join each secondary database to the availability group:  
ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
GO  
  
ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
GO
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3233f-244">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="3233f-244">Related Tasks</span></span>  
 <span data-ttu-id="3233f-245">**So konfigurieren Sie Verfügbarkeitsgruppen- und Replikateigenschaften**</span><span class="sxs-lookup"><span data-stu-id="3233f-245">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="3233f-246">Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-246">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="3233f-247">Ändern des Failovermodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-247">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="3233f-248">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-248">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="3233f-249">Konfigurieren der flexiblen Failoverrichtlinie zum Steuern der Bedingungen für ein automatisches Failover (AlwaysOn-Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="3233f-249">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="3233f-250">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-250">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="3233f-251">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-251">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="3233f-252">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-252">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="3233f-253">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-253">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3233f-254">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-254">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="3233f-255">**So schließen Sie die Konfiguration von Verfügbarkeitsgruppen ab**</span><span class="sxs-lookup"><span data-stu-id="3233f-255">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="3233f-256">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-256">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3233f-257">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-257">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3233f-258">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-258">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3233f-259">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-259">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="3233f-260">**Alternative Möglichkeiten zum Erstellen einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="3233f-260">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="3233f-261">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-261">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="3233f-262">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-262">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="3233f-263">Erstellen einer Verfügbarkeitsgruppe &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-263">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="3233f-264">**So aktivieren Sie AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="3233f-264">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="3233f-265">Aktivieren und Deaktivieren von Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-265">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="3233f-266">**So konfigurieren Sie einen Datenbankspiegelungs-Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="3233f-266">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="3233f-267">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-267">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="3233f-268">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-268">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="3233f-269">Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-269">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="3233f-270">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-270">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="3233f-271">**Problembehandlung für die AlwaysOn-Verfügbarkeitsgruppenkonfiguration**</span><span class="sxs-lookup"><span data-stu-id="3233f-271">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="3233f-272">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfiguration (SQL Server) gelöscht</span><span class="sxs-lookup"><span data-stu-id="3233f-272">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="3233f-273">Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-273">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="3233f-274">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="3233f-274">Related Content</span></span>  
  
-   <span data-ttu-id="3233f-275">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="3233f-275">**Blogs:**</span></span>  
  
     [<span data-ttu-id="3233f-276">AlwaysON - HADRON-Lernreihe: Nutzung des Arbeitsthreadpools für HADRON-fähige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="3233f-276">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="3233f-277">SQL Server AlwaysOn-Teamblogs: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="3233f-277">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="3233f-278">CSS SQL Server-Technikblogs</span><span class="sxs-lookup"><span data-stu-id="3233f-278">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="3233f-279">**Videos:**</span><span class="sxs-lookup"><span data-stu-id="3233f-279">**Videos:**</span></span>  
  
     [<span data-ttu-id="3233f-280">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 1: Einführung in die nächste Generation von Lösungen mit hoher Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="3233f-280">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="3233f-281">Microsoft SQL Server Codename "Denali" AlwaysOn-Reihe, Teil 2: Erstellen einer unternehmenswichtigen Lösung für hohe Verfügbarkeit mit AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="3233f-281">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="3233f-282">**Whitepaper:**</span><span class="sxs-lookup"><span data-stu-id="3233f-282">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="3233f-283">Microsoft SQL Server AlwaysOn-Lösungshandbuch zu hoher Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="3233f-283">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="3233f-284">Microsoft-Whitepapers für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="3233f-284">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="3233f-285">Whitepapers des SQL Server-Kundenberatungsteams</span><span class="sxs-lookup"><span data-stu-id="3233f-285">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="3233f-286">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3233f-286">See Also</span></span>  
 <span data-ttu-id="3233f-287">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3233f-287">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="3233f-288">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3233f-288">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="3233f-289">Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3233f-289">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)   
