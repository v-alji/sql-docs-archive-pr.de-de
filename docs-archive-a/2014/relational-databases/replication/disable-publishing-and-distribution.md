---
title: Deaktivieren der Veröffentlichung und Verteilung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- disabling publishing
- publishing [SQL Server replication], disabling
- distribution disabling [SQL Server replication]
- removing replication
- replication [SQL Server], removing
- disabling replication
- disabling distribution
ms.assetid: 6d4a1474-4d13-4826-8be2-80050fafa8a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8843dac310d1e023fe7ce63eded02c9e1bed3731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609128"
---
# <a name="disable-publishing-and-distribution"></a><span data-ttu-id="84fa9-102">Deaktivieren der Veröffentlichung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="84fa9-102">Disable Publishing and Distribution</span></span>
  <span data-ttu-id="84fa9-103">In diesem Thema wird beschrieben, wie die Veröffentlichung und die Verteilung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-103">This topic describes how to disable publishing and distribution in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="84fa9-104">Sie können folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="84fa9-104">You can do the following:</span></span>  
  
-   <span data-ttu-id="84fa9-105">Löschen aller Verteilungsdatenbanken auf dem Verteiler.</span><span class="sxs-lookup"><span data-stu-id="84fa9-105">Delete all distribution databases on the Distributor.</span></span>  
  
-   <span data-ttu-id="84fa9-106">Deaktivieren aller Verleger, die den Verteiler verwenden, und Löschen aller Veröffentlichungen auf diesen Verlegern.</span><span class="sxs-lookup"><span data-stu-id="84fa9-106">Disable all Publishers that use the Distributor and delete all publications on those Publishers.</span></span>  
  
-   <span data-ttu-id="84fa9-107">Löschen aller Abonnements für die Veröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="84fa9-107">Delete all subscriptions to the publications.</span></span> <span data-ttu-id="84fa9-108">Daten in den Veröffentlichungs- und Abonnementdatenbanken werden nicht gelöscht. Allerdings geht die Synchronisierungsbeziehung zu allen Veröffentlichungsdatenbanken verloren.</span><span class="sxs-lookup"><span data-stu-id="84fa9-108">Data in the publication and subscription databases will not be deleted; however, it loses its synchronization relationship to any publication databases.</span></span> <span data-ttu-id="84fa9-109">Falls Sie die Daten auf dem Abonnenten löschen möchten, müssen Sie diese manuell löschen.</span><span class="sxs-lookup"><span data-stu-id="84fa9-109">If you want the data at the Subscriber to be deleted, you must delete it manually.</span></span>  
  
 <span data-ttu-id="84fa9-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="84fa9-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="84fa9-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="84fa9-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="84fa9-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="84fa9-112">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="84fa9-113">**So deaktivieren Sie die Veröffentlichung und Verteilung mit:**</span><span class="sxs-lookup"><span data-stu-id="84fa9-113">**To disable publishing and distribution, using:**</span></span>  
  
     [<span data-ttu-id="84fa9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84fa9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="84fa9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84fa9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="84fa9-116">Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="84fa9-116">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="84fa9-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="84fa9-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="84fa9-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="84fa9-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="84fa9-119">Zum Deaktivieren der Veröffentlichung und Verteilung müssen sämtliche Verteilungs- und Veröffentlichungsdatenbanken online sein.</span><span class="sxs-lookup"><span data-stu-id="84fa9-119">To disable publishing and distribution, all distribution and publication databases must be online.</span></span> <span data-ttu-id="84fa9-120">Wenn für Verteilungs- oder Veröffentlichungsdatenbanken *Datenbankmomentaufnahmen* vorhanden sind, müssen diese gelöscht werden, bevor die Veröffentlichung und Verteilung deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="84fa9-120">If any *database snapshots* exist for distribution or publication databases, they must be dropped before disabling publishing and distribution.</span></span> <span data-ttu-id="84fa9-121">Eine Datenbankenmomentaufnahme ist eine schreibgeschützte Offlinekopie einer Datenbank, die in keinem Bezug zu einer Replikationsmomentaufnahme steht.</span><span class="sxs-lookup"><span data-stu-id="84fa9-121">A database snapshot is a read-only offline copy of a database and is not related to a replication snapshot.</span></span> <span data-ttu-id="84fa9-122">Weitere Informationen finden Sie unter [Datenbankmomentaufnahmen &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="84fa9-122">For more information, see [Database Snapshots &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="84fa9-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84fa9-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="84fa9-124">Sie können die Veröffentlichung und die Verteilung mithilfe des Veröffentlichungs- und Verteilungsdeaktivierungs-Assistenten deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="84fa9-124">Disable publishing and distribution by using the Disable Publishing and Distribution Wizard.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="84fa9-125">So deaktivieren Sie die Veröffentlichung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="84fa9-125">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="84fa9-126">Stellen Sie in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Verbindung mit dem Verleger oder Verteiler her, den Sie deaktivieren möchten, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="84fa9-126">Connect to the Publisher or Distributor you want to disable in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="84fa9-127">Klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** , und klicken Sie dann auf **Veröffentlichung und Verteilung deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="84fa9-127">Right-click the **Replication** folder, and then click **Disable Publishing and Distribution**.</span></span>  
  
3.  <span data-ttu-id="84fa9-128">Führen Sie die Schritte des Veröffentlichungs- und Verteilungsdeaktivierungs-Assistenten vollständig aus.</span><span class="sxs-lookup"><span data-stu-id="84fa9-128">Complete the steps in the Disable Publishing and Distribution Wizard.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="84fa9-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84fa9-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="84fa9-130">Die Veröffentlichung und die Verteilung können mit gespeicherten Replikationsprozeduren programmgesteuert deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-130">Publishing and distributing can be disabled programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="84fa9-131">So deaktivieren Sie die Veröffentlichung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="84fa9-131">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="84fa9-132">Beenden Sie alle replikationsbezogenen Aufträge.</span><span class="sxs-lookup"><span data-stu-id="84fa9-132">Stop all replication-related jobs.</span></span> <span data-ttu-id="84fa9-133">Eine Auflistung der Auftragsnamen finden Sie im Abschnitt "Agentsicherheit mit SQL Server-Agent" unter [Sicherheitsmodell des Replikations-Agents](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="84fa9-133">For a list of job names, see the "Agent Security Under SQL Server Agent" section of [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
2.  <span data-ttu-id="84fa9-134">Führen Sie für jeden Abonnenten der Abonnementdatenbank [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) aus, um Replikationsobjekte aus der Datenbank zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="84fa9-134">At each Subscriber on the subscription database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span> <span data-ttu-id="84fa9-135">Diese gespeicherte Prozedur entfernt keine Replikationsaufträge vom Verteiler.</span><span class="sxs-lookup"><span data-stu-id="84fa9-135">This stored procedure will not remove replication jobs at the Distributor.</span></span>  
  
3.  <span data-ttu-id="84fa9-136">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) aus, um Replikationsobjekte aus der Datenbank zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="84fa9-136">At the Publisher on the publication database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span>  
  
4.  <span data-ttu-id="84fa9-137">Wenn der Verleger einen Remoteverteiler verwendet, führen Sie [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="84fa9-137">If the Publisher uses a remote Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span></span>  
  
5.  <span data-ttu-id="84fa9-138">Führen Sie auf dem Verteiler [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="84fa9-138">At the Distributor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span> <span data-ttu-id="84fa9-139">Diese gespeicherte Prozedur sollte für jeden auf dem Verteiler registrierten Verleger einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-139">This stored procedure should be run once for each Publisher registered at the Distributor.</span></span>  
  
6.  <span data-ttu-id="84fa9-140">Führen Sie auf dem Verteiler [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) aus, um die Verteilerdatenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="84fa9-140">At the Distributor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) to delete the distribution database.</span></span> <span data-ttu-id="84fa9-141">Diese gespeicherte Prozedur sollte für jede Verteilungsdatenbank auf dem Verteiler einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-141">This stored procedure should be run once for each distribution database at the Distributor.</span></span> <span data-ttu-id="84fa9-142">Dadurch werden außerdem alle der Verteilungsdatenbank zugeordnete Warteschlangenlese-Agentaufträge entfernt.</span><span class="sxs-lookup"><span data-stu-id="84fa9-142">This also removes any Queue Reader Agent jobs associated with the distribution database.</span></span>  
  
7.  <span data-ttu-id="84fa9-143">Führen Sie auf dem Verteiler [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) aus, um die Verteilerbezeichnung vom Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="84fa9-143">At the Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) to remove the Distributor designation from the server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84fa9-144">Wenn nicht alle Replikationsveröffentlichungs- und Verteilungsobjekte gelöscht wurden, bevor Sie [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) und [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql)ausführen, geben diese Prozeduren einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="84fa9-144">If all replication publishing and distribution objects are not dropped before you execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) and [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), these procedures will return an error.</span></span> <span data-ttu-id="84fa9-145">Um alle Replikations bezogenen Objekte zu löschen, wenn ein Verleger oder ein Verteiler gelöscht wird, muss der \*\* \@ no_checks\*\* -Parameter auf **1**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-145">To drop all replication-related objects when a Publisher or Distributor is dropped, the **\@no_checks** parameter must be set to **1**.</span></span> <span data-ttu-id="84fa9-146">Wenn ein Verleger oder Verteiler offline oder nicht erreichbar ist, kann der \*\* \@ ignore_distributor\*\* -Parameter auf **1** festgelegt werden, damit Sie gelöscht werden können. Allerdings müssen alle veröffentlichten Veröffentlichungs-und Verteilungs Objekte manuell entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-146">If a Publisher or Distributor is offline or unreachable, the **\@ignore_distributor** parameter can be set to **1** so that they can be dropped; however, any publishing and distributing objects left behind must be removed manually.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="84fa9-147">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="84fa9-147">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="84fa9-148">Dieses Beispielskript entfernt Replikationsobjekte aus der Abonnementdatenbank.</span><span class="sxs-lookup"><span data-stu-id="84fa9-148">This example script removes replication objects from the subscription database.</span></span>  
  
 [!code-sql[HowTo#sp_removedbreplication](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_removedbreplication)]  
  
 <span data-ttu-id="84fa9-149">Dieses Beispielskript deaktiviert die Veröffentlichung und die Verteilung auf einem Server, der ein Verleger und Verteiler ist, und löscht die Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="84fa9-149">This example script disables publishing and distribution on a server that is a Publisher and Distributor and drops the distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_DropDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_dropdistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="84fa9-150">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="84fa9-150">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="84fa9-151">So deaktivieren Sie die Veröffentlichung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="84fa9-151">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="84fa9-152">Entfernen Sie alle Abonnements von Veröffentlichungen, für die der Verteiler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84fa9-152">Remove all subscriptions to publications that use the Distributor.</span></span> <span data-ttu-id="84fa9-153">Weitere Informationen finden Sie unter [Delete a Pull Subscription](delete-a-pull-subscription.md) und [Delete a Push Subscription](delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="84fa9-153">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md) and [Delete a Push Subscription](delete-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="84fa9-154">Entfernen Sie alle Veröffentlichungen, für die der Verteiler verwendet wird, und deaktivieren Sie die Veröffentlichung für alle Datenbanken, wenn sich Verleger und Verteiler auf dem gleichen Server befinden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-154">Remove all publications that use the Distributor, and disable publishing for all databases if the Publisher and Distributor are on the same server.</span></span> <span data-ttu-id="84fa9-155">Weitere Informationen finden Sie unter [Delete a Publication](publish/delete-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="84fa9-155">For more information, see [Delete a Publication](publish/delete-a-publication.md).</span></span>  
  
3.  <span data-ttu-id="84fa9-156">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
4.  <span data-ttu-id="84fa9-157">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.DistributionPublisher>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="84fa9-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="84fa9-158">Geben Sie die <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> -Eigenschaft an, und übergeben Sie das <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Objekt aus Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="84fa9-158">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property, and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
5.  <span data-ttu-id="84fa9-159">(Optional) Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen und zu verifizieren, dass der Verleger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="84fa9-159">(Optional) Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object and verify that the Publisher exists.</span></span> <span data-ttu-id="84fa9-160">Wenn diese Methode `false` zurückgibt, war der in Schritt 4 festgelegte Verlegername falsch, oder der Verleger wird von diesem Verteiler nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="84fa9-160">If this method returns `false`, the Publisher name set in step 4 was incorrect or the Publisher is not used by this Distributor.</span></span>  
  
6.  <span data-ttu-id="84fa9-161">Rufen Sie die <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="84fa9-161">Call the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> method.</span></span> <span data-ttu-id="84fa9-162">Übergeben Sie den Wert `true` für *Force* , wenn sich der Verleger und der Verteiler auf unterschiedlichen Servern befinden, und wenn der Verleger auf dem Verteiler deinstalliert werden soll, ohne zuvor zu überprüfen, ob die Veröffentlichungen auf dem Verleger nicht mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="84fa9-162">Pass a value of `true` for *force* if the Publisher and Distributor are on different servers, and when the Publisher should be uninstalled at the Distributor without first verifying that publications no longer exist at the Publisher.</span></span>  
  
7.  <span data-ttu-id="84fa9-163">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationServer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="84fa9-163">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="84fa9-164">Übergeben Sie das <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Objekt aus Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="84fa9-164">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
8.  <span data-ttu-id="84fa9-165">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="84fa9-165">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> method.</span></span> <span data-ttu-id="84fa9-166">Übergeben `true` Sie den Wert für *Force* , um alle Replikations Objekte auf dem Verteiler zu entfernen, ohne zuvor zu überprüfen, ob alle lokalen Veröffentlichungs Datenbanken deaktiviert wurden und Verteilungs Datenbanken deinstalliert wurden.</span><span class="sxs-lookup"><span data-stu-id="84fa9-166">Pass a value of `true` for *force* to remove all replication objects at the Distributor without first verifying that all local publication databases have been disabled, and distribution databases have been uninstalled.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="84fa9-167">Beispiele (RMO)</span><span class="sxs-lookup"><span data-stu-id="84fa9-167">Examples (RMO)</span></span>  
 <span data-ttu-id="84fa9-168">In diesem Beispiel werden die Verlegerregistrierung auf dem Verteiler entfernt, die Verteilungsdatenbank gelöscht und der Verteiler deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="84fa9-168">This example removes the Publisher registration at the Distributor, drops the distribution database, and uninstalls the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpub)]  
  
 <span data-ttu-id="84fa9-169">In diesem Beispiel wird der Verteiler deinstalliert, ohne dass zuvor die lokalen Veröffentlichungsdatenbanken deaktiviert oder die Verteilungsdatenbank gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="84fa9-169">This example uninstalls the Distributor without first disabling local publication databases or dropping the distribution database.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPubForce](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpubforce)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPubForce](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpubforce)]  
  
## <a name="see-also"></a><span data-ttu-id="84fa9-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84fa9-170">See Also</span></span>  
 <span data-ttu-id="84fa9-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="84fa9-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 [<span data-ttu-id="84fa9-172">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="84fa9-172">Replication System Stored Procedures Concepts</span></span>](concepts/replication-system-stored-procedures-concepts.md)  
  
  
