---
title: Konfigurieren der Replikation für Always On-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 4e001426-5ae0-4876-85ef-088d6e3fb61c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 916458d2d6b8fbba81940257ee85ffe014d1f12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697190"
---
# <a name="configure-replication-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="f060f-102">Konfigurieren der Replikation für Always On-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f060f-102">Configure Replication for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="f060f-103">Das Konfigurieren von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Replikation und AlwaysOn-Verfügbarkeitsgruppen umfasst sieben Schritte.</span><span class="sxs-lookup"><span data-stu-id="f060f-103">Configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication and AlwaysOn availability groups involves seven steps.</span></span> <span data-ttu-id="f060f-104">Jeder dieser Schritte wird in den folgenden Abschnitten detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f060f-104">Each step is described in more detail in the following sections.</span></span>  

##  <a name="1-configure-the-database-publications-and-subscriptions"></a><a name="step1"></a> <span data-ttu-id="f060f-105">1. Konfigurieren der Datenbankveröffentlichungen und Abonnements</span><span class="sxs-lookup"><span data-stu-id="f060f-105">1. Configure the Database Publications and Subscriptions</span></span>  

### <a name="configure-the-distributor"></a><span data-ttu-id="f060f-106">Konfigurieren des Verteilers</span><span class="sxs-lookup"><span data-stu-id="f060f-106">Configure the distributor</span></span>
  
 <span data-ttu-id="f060f-107">Der Verteiler sollte kein Host für eine der aktuellen (oder vorgesehenen) Replikate der Verfügbarkeitsgruppe sein, zu der die Veröffentlichungsdatenbank gehört (oder gehören wird).</span><span class="sxs-lookup"><span data-stu-id="f060f-107">The distributor should not be a host for any of the current (or intended) replicas of the availability group that the publishing database is (or will become) a member of.</span></span>  
  
1.  <span data-ttu-id="f060f-108">Konfigurieren Sie Verteilung beim Verteiler.</span><span class="sxs-lookup"><span data-stu-id="f060f-108">Configure distribution at the distributor.</span></span> <span data-ttu-id="f060f-109">Wenn gespeicherte Prozeduren zur Konfiguration verwendet werden, führen Sie `sp_adddistributor` aus.</span><span class="sxs-lookup"><span data-stu-id="f060f-109">If stored procedures are being used for configuration, run `sp_adddistributor`.</span></span> <span data-ttu-id="f060f-110">Verwenden Sie den- *@password* Parameter, um das Kennwort zu identifizieren, das verwendet wird, wenn ein Remote Verleger eine Verbindung mit dem Verteiler herstellt.</span><span class="sxs-lookup"><span data-stu-id="f060f-110">Use the *@password* parameter to identify the password that will be used when a remote publisher connects to the distributor.</span></span> <span data-ttu-id="f060f-111">Das Kennwort wird auch bei jedem Remoteverleger benötigt, wenn der Remoteverteiler eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="f060f-111">The password will also be needed at each remote publisher when the remote distributor is set up.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = '**Strong password for distributor**';  
    ```  
  
2.  <span data-ttu-id="f060f-112">Erstellen Sie die Verteilungsdatenbank beim Verteiler.</span><span class="sxs-lookup"><span data-stu-id="f060f-112">Create the distribution database at the distributor.</span></span> <span data-ttu-id="f060f-113">Wenn gespeicherte Prozeduren zur Konfiguration verwendet werden, führen Sie `sp_adddistributiondb` aus.</span><span class="sxs-lookup"><span data-stu-id="f060f-113">If stored procedures are being used for configuration, run `sp_adddistributiondb`.</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sys.sp_adddistributiondb  
        @database = 'distribution',  
        @security_mode = 1;  
    ```  
  
3.  <span data-ttu-id="f060f-114">Konfigurieren Sie den Remoteverleger.</span><span class="sxs-lookup"><span data-stu-id="f060f-114">Configure the remote publisher.</span></span> <span data-ttu-id="f060f-115">Wenn gespeicherte Prozeduren zur Konfiguration des Verteilers verwendet werden, führen Sie `sp_adddistpublisher` aus.</span><span class="sxs-lookup"><span data-stu-id="f060f-115">If stored procedures are being used to configure the distributor, run `sp_adddistpublisher`.</span></span> <span data-ttu-id="f060f-116">Der- *@security_mode* Parameter wird verwendet, um zu bestimmen, wie die gespeicherte Prozedur zur Verleger Überprüfung, die von den Replikations-Agents ausgeführt wird, eine Verbindung mit dem aktuellen primären</span><span class="sxs-lookup"><span data-stu-id="f060f-116">The *@security_mode* parameter is used to determine how the publisher validation stored procedure that is run from the replication agents, connects to the current primary.</span></span> <span data-ttu-id="f060f-117">Wenn der Parameter auf 1 festgelegt ist, wird die Windows-Authentifizierung verwendet, um eine Verbindung mit dem aktuellen primären Replikat herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f060f-117">If set to 1 Windows authentication is used to connect to the current primary.</span></span> <span data-ttu-id="f060f-118">Wenn der Wert auf 0 festgelegt ist, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] wird die Authentifizierung mit den angegebenen *@login* Werten für und verwendet *@password* .</span><span class="sxs-lookup"><span data-stu-id="f060f-118">If set to 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authentication is used with the specified *@login* and *@password* values.</span></span> <span data-ttu-id="f060f-119">Die Anmeldedaten und das Kennwort, die angegeben wurden, müssen bei jedem sekundären Replikat gültig sein, damit die gespeicherte Prozedur zur Überprüfung erfolgreich eine Verbindung mit diesem Replikat herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f060f-119">The login and password specified must be valid at each secondary replica for the validation stored procedure to successfully connect to that replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f060f-120">Wenn geänderte Replikations-Agents auf einem anderen Computer als dem Verteiler ausgeführt werden, dann ist bei Verwendung der Windows-Authentifizierung zum Herstellen einer Verbindung zum primären Replikat erforderlich, dass die Kerberos-Authentifizierung für die Kommunikation zwischen den Replikathostcomputern konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="f060f-120">If any modified replication agents run on a computer other than the distributor, use of Windows authentication for the connection to the primary will require Kerberos authentication to be configured for the communication between the replica host computers.</span></span> <span data-ttu-id="f060f-121">Bei Verwendung einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Anmeldung zum Herstellen einer Verbindung mit dem aktuellen primären Replikat ist keine Kerberos-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f060f-121">Use of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login for the connection to the current primary will not require Kerberos authentication.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistpublisher  
        @publisher = 'AGPrimaryReplicaHost',  
        @distribution_db = 'distribution',  
        @working_directory = '\\MyReplShare\WorkingDir',  
        @login = 'MyPubLogin',  
        @password = '**Strong password for publisher**';  
    ```  
  
 <span data-ttu-id="f060f-122">Weitere Informationen finden Sie unter [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f060f-122">For more information, see [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span></span>  
  
### <a name="configure-the-publisher-at-the-original-publisher"></a><span data-ttu-id="f060f-123">Konfigurieren des Verlegers beim ursprünglichen Verleger</span><span class="sxs-lookup"><span data-stu-id="f060f-123">Configure the publisher at the original publisher</span></span>
  
1.  <span data-ttu-id="f060f-124">Konfigurieren Sie die Remoteverteilung.</span><span class="sxs-lookup"><span data-stu-id="f060f-124">Configure remote distribution.</span></span> <span data-ttu-id="f060f-125">Wenn gespeicherte Prozeduren zur Konfiguration des Verlegers verwendet werden, führen Sie `sp_adddistributor` aus.</span><span class="sxs-lookup"><span data-stu-id="f060f-125">If stored procedures are being used to configure the publisher, run `sp_adddistributor`.</span></span> <span data-ttu-id="f060f-126">Geben Sie den gleichen Wert für an *@password* , der verwendet wurde, als `sp_adddistrbutor` auf dem Verteiler ausgeführt wurde, um die Verteilung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f060f-126">Specify the same value for *@password* as that used when `sp_adddistrbutor` was run at the distributor to set up distribution.</span></span>  
  
    ```sql
    exec sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = 'MyDistPass'  
    ```  
  
2.  <span data-ttu-id="f060f-127">Aktivieren Sie die Datenbank für die Replikation.</span><span class="sxs-lookup"><span data-stu-id="f060f-127">Enable the database for replication.</span></span> <span data-ttu-id="f060f-128">Wenn gespeicherte Prozeduren zur Konfiguration des Verlegers verwendet werden, führen Sie `sp_replicationdboption` aus.</span><span class="sxs-lookup"><span data-stu-id="f060f-128">If stored procedures are being used to configure the publisher, run `sp_replicationdboption`.</span></span> <span data-ttu-id="f060f-129">Wenn sowohl Transaktions- als auch Mergereplikation für die Datenbank konfiguriert werden sollen, müssen beide aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f060f-129">If both transactional and merge replication are to be configured for the database, each must be enabled.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'true';  
  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'merge publish',  
        @value = 'true';  
    ```  
  
3.  <span data-ttu-id="f060f-130">Erstellen Sie die Replikationsveröffentlichung, Artikel und Abonnements.</span><span class="sxs-lookup"><span data-stu-id="f060f-130">Create the replication publication, articles, and subscriptions.</span></span> <span data-ttu-id="f060f-131">Weitere Informationen zum Konfigurieren der Replikation finden Sie unter "Veröffentlichen von Daten und Datenbankobjekten".</span><span class="sxs-lookup"><span data-stu-id="f060f-131">For more information about how to configure replication, see Publishing Data and Database objects.</span></span>  
  
##  <a name="2-configure-the-alwayson-availability-group"></a><a name="step2"></a><span data-ttu-id="f060f-132">2. Konfigurieren der AlwaysOn-Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="f060f-132">2. Configure the AlwaysOn Availability Group</span></span>  
 <span data-ttu-id="f060f-133">Erstellen Sie beim vorgesehenen primären Replikat die Veröffentlichungsgruppe, und ordnen Sie ihr die veröffentlichte (oder zu veröffentlichende) Datenbank als Elementdatenbank zu.</span><span class="sxs-lookup"><span data-stu-id="f060f-133">At the intended primary, create the availability group with the published (or to be published) database as a member database.</span></span> <span data-ttu-id="f060f-134">Wenn Sie den Verfügbarkeitsgruppen-Assistenten verwenden, können Sie es entweder dem Assistenten erlauben, die sekundären Replikatdatenbanken zum ersten Mal zu synchronisieren, oder Sie können die Initialisierung mit Sicherung und Wiederherstellung manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f060f-134">If using the Availability Group Wizard, you can either allow the wizard to initially synchronize the secondary replica databases or you can perform the initialization manually by using backup and restore.</span></span>  
  
 <span data-ttu-id="f060f-135">Erstellen Sie einen DNS-Listener für die Verfügbarkeitsgruppe, die von den Replikations-Agents verwendet wird, um eine Verbindung mit dem aktuellen Primären herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f060f-135">Create a DNS listener for the availability group that will be used by the replication agents to connect to the current primary.</span></span> <span data-ttu-id="f060f-136">Der angegebene Listenername wird als Umleitungsziel für das aus ursprünglichem Verleger und veröffentlichter Datenbank bestehende Paar verwendet.</span><span class="sxs-lookup"><span data-stu-id="f060f-136">The listener name that is specified will be used as the target of redirection for the original publisher/published database pair.</span></span> <span data-ttu-id="f060f-137">Wenn Sie die Verfügbarkeitsgruppe beispielsweise mithilfe von DDL konfigurieren, kann das folgende Codebeispiel zur Angabe eines Verfügbarkeitsgruppenlisteners für eine vorhandene Verfügbarkeitsgruppe mit dem Namen `MyAG` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f060f-137">For example, if you are using DDL to configure the availability group, the following code example can be used to specify an availability group listener for an existing availability group named `MyAG`:</span></span>  
  
```sql
ALTER AVAILABILITY GROUP 'MyAG'   
    ADD LISTENER 'MyAGListenerName' (WITH IP (('10.120.19.155', '255.255.254.0')));  
```  
  
 <span data-ttu-id="f060f-138">Weitere Informationen finden Sie unter [Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f060f-138">For more information, see [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span></span>  
  
##  <a name="3-insure-that-all-of-the-secondary-replica-hosts-are-configured-for-replication"></a><a name="step3"></a><span data-ttu-id="f060f-139">3. Stellen Sie sicher, dass alle sekundären Replikat Hosts für die Replikation konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="f060f-139">3. Insure that all of the Secondary Replica Hosts are Configured for Replication</span></span>  
 <span data-ttu-id="f060f-140">Überprüfen Sie bei jedem sekundären Replikathost, ob [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] so konfiguriert wurde, dass die Replikation unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f060f-140">At each secondary replica host, verify that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been configured to support replication.</span></span> <span data-ttu-id="f060f-141">Die folgende Abfrage kann auf jedem sekundären Replikathost ausgeführt werden, um zu bestimmen, ob die Replikation installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="f060f-141">The following query can be run at each secondary replica host to determine whether replication is installed:</span></span>  
  
```sql
USE master;  
GO  
DECLARE @installed int;  
EXEC @installed = sys.sp_MS_replication_installed;  
SELECT @installed;  
```  
  
 <span data-ttu-id="f060f-142">Wenn *@installed* den Wert 0 hat, muss die Replikation der-Installation hinzugefügt werden [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f060f-142">If *@installed* is 0, replication must be added to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span>  
  
##  <a name="4-configure-the-secondary-replica-hosts-as-replication-publishers"></a><a name="step4"></a> <span data-ttu-id="f060f-143">4. Konfigurieren des sekundären Replikathosts als Replikationsverleger</span><span class="sxs-lookup"><span data-stu-id="f060f-143">4. Configure the Secondary Replica Hosts as Replication Publishers</span></span>  
 <span data-ttu-id="f060f-144">Ein sekundäres Replikat kann nicht als Replikationsverleger oder Neuverleger fungieren, aber die Replikation kann so konfiguriert werden, dass das sekundäre Replikat nach einem Failover die Rolle übernehmen kann.</span><span class="sxs-lookup"><span data-stu-id="f060f-144">A secondary replica cannot act as a replication publisher or republisher but replication must be configured so that the secondary can take over after a failover.</span></span> <span data-ttu-id="f060f-145">Konfigurieren Sie beim Verteiler die Verteilung für jeden sekundären Replikathost.</span><span class="sxs-lookup"><span data-stu-id="f060f-145">At the distributor, configure distribution for each secondary replica host.</span></span> <span data-ttu-id="f060f-146">Geben Sie die Verteilungsdatenbank und das Arbeitsverzeichnis an, die angegeben wurden, als der ursprüngliche Verleger dem Verteiler hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f060f-146">Specify the same distribution database and working directory as was specified when the original publisher was added to the distributor.</span></span> <span data-ttu-id="f060f-147">Wenn Sie gespeicherte Prozeduren zum Konfigurieren der Verteilung verwenden, führen Sie `sp_adddistpublisher` aus, um die Remoteverleger dem Verteiler zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f060f-147">If you are using stored procedures to configure distribution, use `sp_adddistpublisher` to associate the remote publishers with the distributor.</span></span> <span data-ttu-id="f060f-148">Wenn *@login* und *@password* für den ursprünglichen Verleger verwendet wurden, geben Sie die gleichen Werte an, wenn Sie die sekundären Replikat Hosts als Verleger hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f060f-148">If *@login* and *@password* were used for the original publisher, specify the same values for each when you add the secondary replica hosts as publishers.</span></span>  
  
```sql
EXEC sys.sp_adddistpublisher  
    @publisher = 'AGSecondaryReplicaHost',  
    @distribution_db = 'distribution',  
    @working_directory = '\\MyReplShare\WorkingDir',  
    @login = 'MyPubLogin',  
    @password = '**Strong password for publisher**';  
```  
  
 <span data-ttu-id="f060f-149">Konfigurieren Sie die Verteilung auf jedem sekundären Replikathost.</span><span class="sxs-lookup"><span data-stu-id="f060f-149">At each secondary replica host, configure distribution.</span></span> <span data-ttu-id="f060f-150">Identifizieren Sie den Verteiler des ursprünglichen Verlegers als Remoteverteiler.</span><span class="sxs-lookup"><span data-stu-id="f060f-150">Identify the distributor of the original publisher as the remote distributor.</span></span> <span data-ttu-id="f060f-151">Verwenden Sie das Kennwort, das verwendet wurde, als `sp_adddistributor` ursprünglich auf dem Verteiler ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f060f-151">Use the same password as that used when `sp_adddistributor` was run originally at the distributor.</span></span> <span data-ttu-id="f060f-152">Wenn gespeicherte Prozeduren zum Konfigurieren der Verteilung verwendet werden, wird der- *@password* Parameter von `sp_adddistributor` verwendet, um das Kennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f060f-152">If stored procedures are being used to configure distribution, the *@password* parameter of `sp_adddistributor` is used to specify the password.</span></span>  
  
```sql
EXEC sp_adddistributor   
    @distributor = 'MyDistributor',  
    @password = '**Strong password for distributor**';  
```  
  
 <span data-ttu-id="f060f-153">Stellen Sie bei jedem sekundären Replikathost sicher, dass die Pushabonnenten der Datenbankveröffentlichungen als Verbindungsserver angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f060f-153">At each secondary replica host, make sure that the push subscribers of the database publications appear as linked servers.</span></span> <span data-ttu-id="f060f-154">Wenn gespeicherte Prozeduren zum Konfigurieren der Remoteverleger verwendet werden, führen Sie `sp_addlinkedserver` aus, um den Verlegern die Abonnenten (sofern nicht bereits vorhanden) als Verbindungsserver hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f060f-154">If stored procedures are being used to configure the remote publishers, use `sp_addlinkedserver` to add the subscribers (if not already present) as linked servers to the publishers.</span></span>  
  
```sql
EXEC sys.sp_addlinkedserver   
    @server = 'MySubscriber';  
```  
  
##  <a name="5-redirect-the-original-publisher-to-the-ag-listener-name"></a><a name="step5"></a> <span data-ttu-id="f060f-155">5. Umleiten des ursprünglichen Verlegers zum Namen des Verfügbarkeitsgruppenlisteners</span><span class="sxs-lookup"><span data-stu-id="f060f-155">5. Redirect the Original Publisher to the AG Listener Name</span></span>  
 <span data-ttu-id="f060f-156">Führen Sie auf dem Verteiler in der Verteilungsdatenbank die gespeicherte Prozedur `sp_redirect_publisher` aus, um den ursprünglichen Verleger und die veröffentlichte Datenbank dem Namen des Verfügbarkeitsgruppenlisteners der Verfügbarkeitsgruppe zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f060f-156">At the distributor, in the distribution database, run the stored procedure `sp_redirect_publisher` to associate the original publisher and the published database with the availability group listener name of the availability group.</span></span>  
  
```sql
USE distribution;  
GO  
EXEC sys.sp_redirect_publisher   
@original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = 'MyAGListenerName';  
```  
  
##  <a name="6-run-the-replication-validation-stored-procedure-to-verify-the-configuration"></a><a name="step6"></a> <span data-ttu-id="f060f-157">6. Ausführen der gespeicherten Prozedur zur Replikationsüberprüfung, um die Konfiguration zu überprüfen</span><span class="sxs-lookup"><span data-stu-id="f060f-157">6. Run the Replication Validation Stored Procedure to Verify the Configuration</span></span>  
 <span data-ttu-id="f060f-158">Führen Sie auf dem Verteiler in der Verteilungsdatenbank die gespeicherte Prozedur `sp_validate_replica_hosts_as_publishers` aus, um zu überprüfen, ob alle Replikathosts bereits so konfiguriert worden sind, um als Verleger für die veröffentlichte Datenbank zu fungieren.</span><span class="sxs-lookup"><span data-stu-id="f060f-158">At the distributor, in the distribution database, run the stored procedure `sp_validate_replica_hosts_as_publishers` to verify that all replica hosts are now configured to serve as publishers for the published database.</span></span>  
  
```sql
USE distribution;  
GO  
DECLARE @redirected_publisher sysname;  
EXEC sys.sp_validate_replica_hosts_as_publishers  
    @original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = @redirected_publisher output;  
```  
  
 <span data-ttu-id="f060f-159">Die gespeicherte Prozedur `sp_validate_replica_hosts_as_publishers` sollte von einer Anmeldung mit ausreichender Autorisierung bei jedem Verfügbarkeitsgruppenreplikathost ausgeführt werden, um Informationen zur Verfügbarkeitsgruppe abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f060f-159">The stored procedure `sp_validate_replica_hosts_as_publishers` should be run from a login with sufficient authorization at each availability group replica host to query for information about the availability group.</span></span> <span data-ttu-id="f060f-160">Im Gegensatz zu `sp_validate_redirected_publisher` verwendet Sie die Anmelde Informationen des Aufrufers und verwendet nicht die in msdb. dbo. MSdistpublishers beibehaltene Anmeldung, um eine Verbindung mit den Verfügbarkeits Gruppen Replikaten herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f060f-160">Unlike `sp_validate_redirected_publisher`, it uses the credentials of the caller and does not use the login retained in msdb.dbo.MSdistpublishers to connect to the availability group replicas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f060f-161">Die Überprüfung sekundärer Replikathosts, die keinen Lesezugriff zulassen oder die Angabe der Leseabsicht erfordern, schlägt bei `sp_validate_replica_hosts_as_publishers` mit dem folgenden Fehler fehl.</span><span class="sxs-lookup"><span data-stu-id="f060f-161">`sp_validate_replica_hosts_as_publishers` will fail with the following error when validating secondary replica hosts that do not allow read access, or require read intent to be specified.</span></span>  
>   
>  <span data-ttu-id="f060f-162">Meldung 21899, Ebene 11, Status 1, Prozedur `sp_hadr_verify_subscribers_at_publisher`, Zeile 109</span><span class="sxs-lookup"><span data-stu-id="f060f-162">Msg 21899, Level 11, State 1, Procedure `sp_hadr_verify_subscribers_at_publisher`, Line 109</span></span>  
>   
>  <span data-ttu-id="f060f-163">Die Abfrage beim umgeleiteten Verleger „MyReplicaHostName“ zur Bestimmung, ob sysserver-Einträge für die Abonnenten des ursprünglichen Verlegers „MyOriginalPublisher“ vorliegen, ist mit Fehler 976 und folgender Meldung fehlgeschlagen: „Fehler 976, Stufe 14, Status 1, Meldung: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries. (Die Zieldatenbank „MyPublishedDB“ ist an einer Verfügbarkeitsgruppe beteiligt, und Abfragen können derzeit nicht darauf zugreifen.)</span><span class="sxs-lookup"><span data-stu-id="f060f-163">The query at the redirected publisher 'MyReplicaHostName' to determine whether there were sysserver entries for the subscribers of the original publisher 'MyOriginalPublisher' failed with error '976', error message 'Error 976, Level 14, State 1, Message: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries.</span></span> <span data-ttu-id="f060f-164">Entweder die Datenverschiebung wurde angehalten, oder für das Verfügbarkeitsreplikat wurde kein Schreibzugriff aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f060f-164">Either data movement is suspended or the availability replica is not enabled for read access.</span></span> <span data-ttu-id="f060f-165">Um schreibgeschützten Zugriff auf diese und andere Datenbanken in der Verfügbarkeitsgruppe zuzulassen, aktivieren Sie den Lesezugriff auf mindestens ein sekundäres Verfügbarkeitsreplikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f060f-165">To allow read-only access to this and other databases in the availability group, enable read access to one or more secondary availability replicas in the group.</span></span>  <span data-ttu-id="f060f-166">Weitere Informationen finden Sie im Thema zur `ALTER AVAILABILITY GROUP`-Anweisung in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="f060f-166">For more information, see the `ALTER AVAILABILITY GROUP` statement in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.'.</span></span>  
>   
>  <span data-ttu-id="f060f-167">Es sind ein oder mehrere Verlegerüberprüfungsfehler für Replikathost 'MyReplicaHostName' aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f060f-167">One or more publisher validation errors were encountered for replica host 'MyReplicaHostName'.</span></span>  
  
 <span data-ttu-id="f060f-168">Dieses Verhalten wird erwartet.</span><span class="sxs-lookup"><span data-stu-id="f060f-168">This is expected behavior.</span></span> <span data-ttu-id="f060f-169">Sie müssen das Vorhandensein der Abonnentenservereinträge bei diesen sekundären Replikathosts überprüfen, indem Sie die sysserver-Einträge im Host direkt abfragen.</span><span class="sxs-lookup"><span data-stu-id="f060f-169">You must verify the presence of the subscriber server entries at these secondary replica hosts by querying for the sysserver entries directly at the host.</span></span>  
  
##  <a name="7-add-the-original-publisher-to-replication-monitor"></a><a name="step7"></a> <span data-ttu-id="f060f-170">7. Hinzufügen des ursprünglichen Verlegers zum Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="f060f-170">7. Add the Original Publisher to Replication Monitor</span></span>  
 <span data-ttu-id="f060f-171">Fügen Sie dem Replikationsmonitor bei jedem Verfügbarkeitsgruppenreplikat den ursprünglichen Verleger hinzu.</span><span class="sxs-lookup"><span data-stu-id="f060f-171">At each availability group replica, add the original publisher to Replication Monitor.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f060f-172">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f060f-172">Related Tasks</span></span>  
 <span data-ttu-id="f060f-173">**Replikation**</span><span class="sxs-lookup"><span data-stu-id="f060f-173">**Replication**</span></span>  
  
-   [<span data-ttu-id="f060f-174">Warten einer AlwaysOn-Veröffentlichungs Datenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-174">Maintaining an AlwaysOn Publication Database &#40;SQL Server&#41;</span></span>](maintaining-an-always-on-publication-database-sql-server.md)  
  
-   [<span data-ttu-id="f060f-175">Replikation, Änderungsnachverfolgung, Change Data Capture und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-175">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="f060f-176">Häufig gestellte Fragen für Replikationsadministratoren</span><span class="sxs-lookup"><span data-stu-id="f060f-176">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
 <span data-ttu-id="f060f-177">**So erstellen und konfigurieren Sie eine Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="f060f-177">**To create and configure an availability group**</span></span>  
  
-   [<span data-ttu-id="f060f-178">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-178">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f060f-179">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-179">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f060f-180">Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="f060f-181">Erstellen einer Verfügbarkeitsgruppe &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="f060f-182">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-182">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="f060f-183">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-183">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="f060f-184">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-184">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f060f-185">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-185">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f060f-186">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-186">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f060f-187">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f060f-187">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="f060f-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f060f-188">See Also</span></span>  
 <span data-ttu-id="f060f-189">[Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="f060f-189">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="f060f-190">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f060f-190">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="f060f-191">[AlwaysOn-Verfügbarkeitsgruppen: Interoperabilität (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f060f-191">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="f060f-192">SQL Server-Replikation</span><span class="sxs-lookup"><span data-stu-id="f060f-192">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
