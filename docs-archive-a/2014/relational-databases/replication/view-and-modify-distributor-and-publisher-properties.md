---
title: Anzeigen und Ändern der Verteiler- und Verlegereigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- Distributors [SQL Server replication], modifying
- modifying replication properties, Distributors
- Distributors [SQL Server replication], properties
ms.assetid: 5dae1d59-c377-4c6e-adc9-b68c5b328f79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 571f6f3a0d44f0fc87c67885249fca441776946d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615919"
---
# <a name="view-and-modify-distributor-and-publisher-properties"></a><span data-ttu-id="4a2a4-102">Anzeigen und Ändern der Verteiler- und Verlegereigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a2a4-102">View and Modify Distributor and Publisher Properties</span></span>
  <span data-ttu-id="4a2a4-103">In diesem Thema wird beschrieben, wie die Distributor-Eigenschaft und die Publisher-Eigenschaft in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-103">This topic describes how to view and modify Distributor and Publisher properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="4a2a4-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4a2a4-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4a2a4-106">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4a2a4-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4a2a4-107">Security</span><span class="sxs-lookup"><span data-stu-id="4a2a4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4a2a4-108">**So können Sie Verteiler- und Verlegereigenschaften anzeigen und ändern mit:**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-108">**To view and modify Distributor and Publisher properties, using:**</span></span>  
  
     [<span data-ttu-id="4a2a4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a2a4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4a2a4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a2a4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="4a2a4-111">Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="4a2a4-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a2a4-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4a2a4-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4a2a4-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4a2a4-113">Recommendations</span></span>  
  
-   <span data-ttu-id="4a2a4-114">Bei Verlegern, auf denen eine niedrigere Versionen als [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]ausgeführt wird, kann ein Benutzer der festen Serverrolle **sysadmin** auf der Seite **Abonnenten** Abonnenten registrieren.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-114">For Publishers running versions prior to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user in the **sysadmin** fixed server role can register Subscribers on the **Subscribers** page.</span></span> <span data-ttu-id="4a2a4-115">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]müssen Abonnenten für die Replikation nicht mehr explizit registriert werden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-115">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], it is no longer necessary to explicitly register Subscribers for replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a2a4-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4a2a4-116">Security</span></span>  
 <span data-ttu-id="4a2a4-117">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-117">When possible, prompt users to enter security credentials at runtime.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a2a4-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a2a4-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="4a2a4-119">So zeigen Sie die Verteilereigenschaften an oder ändern diese</span><span class="sxs-lookup"><span data-stu-id="4a2a4-119">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-120">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verteiler her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-120">Connect to the Distributor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4a2a4-121">Klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** , und klicken Sie dann auf **Verteilereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-121">Right-click the **Replication** folder, and then click **Distributor Properties**.</span></span>  
  
3.  <span data-ttu-id="4a2a4-122">Sie können die Eigenschaften im Dialogfeld **Verteilereigenschaften – \<Distributor>** anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-122">View and modify properties in the **Distributor Properties - \<Distributor>** dialog box.</span></span>  
  
    -   <span data-ttu-id="4a2a4-123">Um die Eigenschaften einer Verteilungsdatenbank anzuzeigen und zu ändern, klicken Sie auf die Schaltfläche Eigenschaften ( **...** ) für die Datenbank auf der Seite **Allgemein** des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-123">To view and modify properties for a distribution database, click the properties button (**...**) for the database on the **General** page of thedialog box.</span></span>  
  
    -   <span data-ttu-id="4a2a4-124">Um die mit dem Verteiler verbundenen Verlegereigenschaften anzuzeigen und zu ändern, klicken Sie auf der Seite**Verleger**des Dialogfelds auf die Schaltfläche Eigenschaften ( **...** ) des Verlegers.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-124">To view and modify Publisher properties associated with the Distributor, click the properties button (**...**) for the Publisher on the **Publishers** page of the dialog box.</span></span>  
  
    -   <span data-ttu-id="4a2a4-125">Klicken Sie auf der Seite **Allgemein** des Dialogfelds auf **Profilstandards** , um auf die Profile der Replikations-Agents zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-125">To access profiles for replication agents, click the **Profile Defaults** button on the **General** page of the dialog box.</span></span> <span data-ttu-id="4a2a4-126">Weitere Informationen finden Sie unter [Replication Agent Profiles](agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4a2a4-126">For more information, see [Replication Agent Profiles](agents/replication-agent-profiles.md).</span></span>  
  
    -   <span data-ttu-id="4a2a4-127">Um das Kennwort des zum Ausführen von administrativen gespeicherten Prozeduren auf dem Verleger und Aktualisieren von Informationen auf dem Verteiler verwendeten Kontos zu ändern, geben Sie auf der Seite **Verleger** des Dialogfelds in den Feldern **Kennwort** und **Kennwort bestätigen** ein neues Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-127">To change the password for the account used when administrative stored procedures execute at the Publisher and update information at the Distributor, enter a new password in the **Password** and **Confirm password** boxes on the **Publishers** page of the dialog box.</span></span> <span data-ttu-id="4a2a4-128">Weitere Informationen finden Sie unter [Schützen des Verteilers](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="4a2a4-128">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
4.  <span data-ttu-id="4a2a4-129">Ändern Sie die Eigenschaften nach Bedarf, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-129">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="4a2a4-130">So zeigen Sie die Verlegereigenschaften an oder ändern diese</span><span class="sxs-lookup"><span data-stu-id="4a2a4-130">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-131">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-131">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4a2a4-132">Klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** , und klicken Sie dann auf **Verlegereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-132">Right-click the **Replication** folder, and then click **Publisher Properties**.</span></span>  
  
3.  <span data-ttu-id="4a2a4-133">Anzeigen und Ändern der Eigenschaften im Dialogfeld **Verleger \< Publisher > Eigenschaften-** .</span><span class="sxs-lookup"><span data-stu-id="4a2a4-133">View and modify properties in the **Publisher Properties - \< Publisher >** dialog box.</span></span>  
  
    -   <span data-ttu-id="4a2a4-134">Ein Benutzer der festen Serverrolle **sysadmin** kann Datenbanken für die Replikation auf der Seite **Veröffentlichungsdatenbanken** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-134">A user in the **sysadmin** fixed server role can enable databases for replication on the **Publication Databases** page.</span></span> <span data-ttu-id="4a2a4-135">Durch das Aktivieren wird eine Datenbank nicht veröffentlicht, sondern Benutzer der festen Datenbankrolle **db_owner** für diese Datenbank können dann eine oder mehrere Veröffentlichungen in der Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-135">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications in the database.</span></span>  
  
4.  <span data-ttu-id="4a2a4-136">Ändern Sie die Eigenschaften nach Bedarf, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-136">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a2a4-137">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a2a4-137">Using Transact-SQL</span></span>  
 <span data-ttu-id="4a2a4-138">Die Verleger- und Verteilereigenschaften können mit gespeicherten Replikationsprozeduren programmgesteuert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-138">Publisher and Distributor properties can be viewed programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-view-distributor-and-distribution-database-properties"></a><span data-ttu-id="4a2a4-139">So zeigen Sie Verleger- und Verteilerdatenbankeigenschaften an</span><span class="sxs-lookup"><span data-stu-id="4a2a4-139">To view Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-140">Führen Sie [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) aus, um Informationen über Verteiler, Verteilungsdatenbank und Arbeitsverzeichnis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) to return information about the Distributor, distribution database, and working directory.</span></span>  
  
2.  <span data-ttu-id="4a2a4-141">Führen Sie [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) aus, um die Eigenschaften einer angegebenen Verteilungsdatenbank zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) to return properties of a specified distribution database.</span></span>  
  
#### <a name="to-change-distributor-and-distribution-database-properties"></a><span data-ttu-id="4a2a4-142">So ändern Sie Verleger- und Verteilerdatenbankeigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a2a4-142">To change Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-143">Führen Sie auf dem Verteiler [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) aus, um Verteilereigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-143">At the Distributor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) to modify Distributor properties.</span></span>  
  
2.  <span data-ttu-id="4a2a4-144">Führen Sie auf dem Verteiler [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) aus, um Eigenschaften der Verteilerdatenbank zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-144">At the Distributor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) to modify distribution database properties.</span></span>  
  
3.  <span data-ttu-id="4a2a4-145">Führen Sie auf dem Verteiler [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) aus, um das Verteilerkennwort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-145">At the Distributor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) to change the Distributor password.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4a2a4-146">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-146">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="4a2a4-147">Wenn Sie Anmeldeinformationen in einer Skriptdatei speichern müssen, sollten Sie die Datei schützen, um nicht autorisierten Zugriff zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-147">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
4.  <span data-ttu-id="4a2a4-148">Führen Sie auf dem Verteiler [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) aus, um mit dem Verteiler die Eigenschaften eines Verlegers zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-148">At the Distributor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) to change the properties of a Publisher using the Distributor.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4a2a4-149">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4a2a4-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="4a2a4-150">Das folgende Beispielskript [!INCLUDE[tsql](../../includes/tsql-md.md)] gibt Informationen über den Verteiler und die Verteilerdatenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-150">The following example [!INCLUDE[tsql](../../includes/tsql-md.md)] script returns information about the Distributor and distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_helpdistributor](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributor)]  
  
 [!code-sql[HowTo#sp_helpdistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributiondb)]  
  
 <span data-ttu-id="4a2a4-151">Im folgenden Beispiel werden die Beibehaltungsdauer für den Verteiler, das Kennwort für den Verbindungsaufbau zum Verteiler und das Intervall geändert, in dem der Verteiler den Status verschiedener Replikations-Agents überprüft (auch Taktintervall genannt).</span><span class="sxs-lookup"><span data-stu-id="4a2a4-151">This example changes retention periods for the Distributor, the password used when connecting to the Distributor, and the interval at which the Distributor checks the status of various replication agents (also known as the heartbeat interval).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4a2a4-152">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-152">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="4a2a4-153">Wenn Sie Anmeldeinformationen in einer Skriptdatei speichern müssen, sollten Sie die Datei schützen, um nicht autorisierten Zugriff zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-153">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_changedistributor_property](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_property)]  
  
 [!code-sql[HowTo#sp_changedistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributiondb)]  
  
 [!code-sql[HowTo#sp_changedistributor_password](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_password)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="4a2a4-154">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="4a2a4-154">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="4a2a4-155">So zeigen Sie die Verteilereigenschaften an oder ändern diese</span><span class="sxs-lookup"><span data-stu-id="4a2a4-155">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-156">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="4a2a4-157">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationServer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="4a2a4-158">Übergeben Sie das <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Objekt aus Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-158">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="4a2a4-159">(Optional) überprüfen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> -Eigenschaft, um sich davon zu überzeugen, dass der aktuell verbundene Server ein Verteiler ist.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-159">(Optional) Check the <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> property to verify that the currently connected server is a Distributor.</span></span>  
  
4.  <span data-ttu-id="4a2a4-160">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> -Methode auf, um die Eigenschaften vom Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties from the server.</span></span>  
  
5.  <span data-ttu-id="4a2a4-161">(Optional) Zum Ändern der Eigenschaften legen Sie einen neuen Wert für eine oder mehrere der Verteilereigenschaften fest, die im <xref:Microsoft.SqlServer.Replication.ReplicationServer> -Objekt festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-161">(Optional) To change properties, set a new value for one or more of the Distributor properties that can be set on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object.</span></span>  
  
6.  <span data-ttu-id="4a2a4-162">(Optional) Wenn die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Replication.ReplicationServer>-Objekts auf `true` festgelegt ist, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A>-Methode auf, um Änderungen auf dem Server einzutragen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-162">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-distribution-database-properties"></a><span data-ttu-id="4a2a4-163">So zeigen Sie Verteilerdatenbankeigenschaften an oder ändern Sie diese Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a2a4-163">To view and modify distribution database properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-164">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-164">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="4a2a4-165">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.DistributionDatabase>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-165">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> class.</span></span> <span data-ttu-id="4a2a4-166">Geben Sie die Namenseigenschaft an, und übergeben Sie das <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Objekt aus Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-166">Specify the name property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="4a2a4-167">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die Eigenschaften vom Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-167">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties from the server.</span></span> <span data-ttu-id="4a2a4-168">Wenn diese Methode `false` zurückgibt, ist die Datenbank mit dem angegebenen Namen nicht auf dem Server vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-168">If this method returns `false`, the database with the specified name does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="4a2a4-169">(Optional) Um Eigenschaften zu ändern, legen Sie einen neuen Wert für eine der definierbaren <xref:Microsoft.SqlServer.Replication.DistributionDatabase> -Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-169">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> properties that can be set.</span></span>  
  
5.  <span data-ttu-id="4a2a4-170">(Optional) Wenn die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Replication.DistributionDatabase>-Objekts auf `true` festgelegt ist, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A>-Methode auf, um Änderungen auf dem Server einzutragen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-170">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="4a2a4-171">So zeigen Sie die Verlegereigenschaften an oder ändern diese</span><span class="sxs-lookup"><span data-stu-id="4a2a4-171">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="4a2a4-172">Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-172">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="4a2a4-173">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.DistributionPublisher>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="4a2a4-174">Geben Sie die <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> -Eigenschaft an, und übergeben Sie das <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Objekt aus Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-174">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="4a2a4-175">(Optional) Um Eigenschaften zu ändern, legen Sie einen neuen Wert für eine der definierbaren <xref:Microsoft.SqlServer.Replication.DistributionPublisher> -Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-175">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> properties that can be set.</span></span>  
  
4.  <span data-ttu-id="4a2a4-176">(Optional) Wenn die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Replication.DistributionPublisher>-Objekts auf `true` festgelegt ist, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A>-Methode auf, um Änderungen auf dem Server einzutragen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-176">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-change-the-password-for-the-administrative-connection-from-the-publisher-to-the-distributor"></a><span data-ttu-id="4a2a4-177">So ändern Sie das Kennwort für die Verwaltungsverbindung zwischen dem Verleger und dem Verteiler</span><span class="sxs-lookup"><span data-stu-id="4a2a4-177">To change the password for the administrative connection from the Publisher to the Distributor</span></span>  
  
1.  <span data-ttu-id="4a2a4-178">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-178">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="4a2a4-179">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationServer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-179">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
3.  <span data-ttu-id="4a2a4-180">Legen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft auf die in Schritt 1 erstellte Verbindung fest.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-180">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="4a2a4-181">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-181">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
5.  <span data-ttu-id="4a2a4-182">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="4a2a4-183">Übergeben Sie den neuen Kennwortwert für den *password* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-183">Pass the new password value for the *password* parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4a2a4-184">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-184">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="4a2a4-185">Wenn Sie Anmeldeinformationen speichern müssen, verwenden Sie die [Kryptografiedienste](https://go.microsoft.com/fwlink/?LinkId=34733) von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-185">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
6.  <span data-ttu-id="4a2a4-186">(Optional) Führen Sie die folgenden Schritte aus, um das Kennwort bei jedem Remoteverleger zu ändern, der diesen Verteiler verwendet:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-186">(Optional) Perform the following steps to change the password at each remote Publisher that uses this Distributor:</span></span>  
  
    1.  <span data-ttu-id="4a2a4-187">Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
    2.  <span data-ttu-id="4a2a4-188">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationServer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
    3.  <span data-ttu-id="4a2a4-189">Legen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft auf die in Schritt 6a erstellte Verbindung fest.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-189">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 6a.</span></span>  
  
    4.  <span data-ttu-id="4a2a4-190">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
    5.  <span data-ttu-id="4a2a4-191">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-191">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="4a2a4-192">Übergeben Sie den neuen Kennwortwert aus Schritt 5 für den *password* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-192">Pass the new password value from Step 5 for the *password* parameter.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="4a2a4-193">Beispiel (RMO)</span><span class="sxs-lookup"><span data-stu-id="4a2a4-193">Example (RMO)</span></span>  
 <span data-ttu-id="4a2a4-194">In diesem Beispiel wird gezeigt, wie Verteilungs- und Verteilungsdatenbankeigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-194">This example shows how to change Distribution and distribution database properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4a2a4-195">Um die Speicherung von Anmeldeinformationen im Code vermeiden, wird das neue Verteilerkennwort zur Laufzeit angegeben.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-195">To avoid storing credentials in the code, the new Distributor password is supplied at runtime.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changedistpub)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changedistpub)]  
  
## <a name="see-also"></a><span data-ttu-id="4a2a4-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a2a4-196">See Also</span></span>  
 <span data-ttu-id="4a2a4-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="4a2a4-198">[Deaktivieren der Veröffentlichung und Verteilung](disable-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="4a2a4-199">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-199">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="4a2a4-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="4a2a4-201">[Informationsskript für Verleger und Verteiler](administration/distributor-and-publisher-information-script.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md) </span></span>  
 <span data-ttu-id="4a2a4-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="4a2a4-203">Anzeigen von Informationen und Ausführen von Aufgaben mithilfe des Replikations</span><span class="sxs-lookup"><span data-stu-id="4a2a4-203">View Information and Perform Tasks using Replication Monitor</span></span>](monitor/view-information-and-perform-tasks-replication-monitor.md)  
  
  
