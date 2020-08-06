---
title: Verwenden des Dialogfelds „Neue Verfügbarkeitsgruppe“ (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 1b0a6421-fbd4-4bb4-87ca-657f4782c433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 811710051089dfeb402e59bf1b7f45d05c84d925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616183"
---
# <a name="use-the-new-availability-group-dialog-box-sql-server-management-studio"></a><span data-ttu-id="37708-102">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="37708-102">Use the New Availability Group Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="37708-103">Dieses Thema enthält Informationen zum Verwenden des Dialogfelds **Neue Verfügbarkeitsgruppe** von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , um auf Instanzen von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , die für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]aktiviert sind, eine AlwaysOn-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37708-103">This topic contains information about how to use the **New Availability Group** dialog box of [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to create an AlwaysOn availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that are enabled for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="37708-104">Eine *Verfügbarkeitsgruppe* definiert einen Satz von Benutzerdatenbanken, für die als eine einzelne Einheit ein Failover ausgeführt wird, sowie einen Satz von Failoverpartnern, die als *Verfügbarkeitsreplikate*bezeichnet werden, die Failover unterstützen.</span><span class="sxs-lookup"><span data-stu-id="37708-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37708-105">Eine Einführung zu Verfügbarkeitsgruppen finden Sie unter [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37708-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  

> [!NOTE]  
>  <span data-ttu-id="37708-106">Informationen zu alternativen Möglichkeiten zum Erstellen einer Verfügbarkeitsgruppe finden Sie in [Verwandte Aufgaben](#RelatedTasks)später in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="37708-106">For information about alternative ways to create an availability group, see [Related Tasks](#RelatedTasks), later in this topic.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37708-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="37708-107">Before You Begin</span></span>  
 <span data-ttu-id="37708-108">Es wird dringend empfohlen, dass Sie diesen Abschnitt lesen, bevor Sie versuchen, Ihre erste Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37708-108">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="37708-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="37708-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="37708-110">Überprüfen Sie vor dem Erstellen einer Verfügbarkeitsgruppe, ob sich die Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , die Verfügbarkeitsreplikate hosten, auf verschiedenen WSFC-Konten (Windows Server Failover Clustering) des gleichen WSFC-Failoverclusters befinden.</span><span class="sxs-lookup"><span data-stu-id="37708-110">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="37708-111">Stellen Sie außerdem sicher, dass alle Serverinstanzen für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] aktiviert sind und alle anderen [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Voraussetzungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="37708-111">Also, verify that each of the server instance is enabled for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="37708-112">Wenn Sie weitere Informationen wünschen, sollten Sie unbedingt [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="37708-112">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="37708-113">Vor dem Erstellen einer Verfügbarkeitsgruppe muss gewährleistet sein, dass jede Serverinstanz, die ein Verfügbarkeitsreplikat hostet, einen voll funktionsfähigen Datenbankspiegelungs-Endpunkt besitzt.</span><span class="sxs-lookup"><span data-stu-id="37708-113">Before you create an availability group, ensure that every server instance that will host an availability replica has a fully functioning database mirroring endpoint.</span></span> <span data-ttu-id="37708-114">Weitere Informationen finden Sie unter [Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37708-114">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
-   <span data-ttu-id="37708-115">Zur Verwendung des Dialogfelds **Neue Verfügbarkeitsgruppe** müssen Sie die Namen der Serverinstanzen kennen, die Verfügbarkeitsreplikate hosten.</span><span class="sxs-lookup"><span data-stu-id="37708-115">To use the **New Availability Group** dialog box, you need to know the names of the server instances that will host availability replicas.</span></span> <span data-ttu-id="37708-116">Zudem müssen Sie die Namen sämtlicher Datenbanken kennen, die Sie der neuen Verfügbarkeitsgruppe hinzufügen möchten, und gewährleisten, dass diese Datenbanken die Voraussetzungen und Einschränkungen der Verfügbarkeitsdatenbank erfüllen, die unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="37708-116">Also, you need know the names of any databases that you intend to add to your new availability group, and you need to ensure that these databases meet the availability database prerequisites and restrictions described in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span> <span data-ttu-id="37708-117">Wenn Sie ungültige Werte eingeben, funktioniert die neue Verfügbarkeitsgruppe nicht.</span><span class="sxs-lookup"><span data-stu-id="37708-117">If you enter invalid values, the new availability group will not work.</span></span>  
  
###  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="37708-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="37708-118">Limitations</span></span>  
 <span data-ttu-id="37708-119">Das Dialogfeld **Neue Verfügbarkeitsgruppe** führt folgende Aktionen nicht durch:</span><span class="sxs-lookup"><span data-stu-id="37708-119">The **New Availability Group** dialog box does not:</span></span>  
  
-   <span data-ttu-id="37708-120">Verfügbarkeitsgruppenlistener erstellen</span><span class="sxs-lookup"><span data-stu-id="37708-120">Create an availability group listener.</span></span>  
  
-   <span data-ttu-id="37708-121">Verknüpfen sekundärer Replikate mit der Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="37708-121">Join secondary replicas to the availability group.</span></span>  
  
-   <span data-ttu-id="37708-122">Ausführen einer anfänglichen Datensynchronisierung</span><span class="sxs-lookup"><span data-stu-id="37708-122">Perform initial data synchronization.</span></span>  
  
 <span data-ttu-id="37708-123">Informationen zu diesen Konfigurationsaufgaben finden Sie unter [Nachverfolgung: Nach dem Erstellen einer Verfügbarkeitsgruppe](#FollowUp) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="37708-123">For information about these configuration tasks, see [Follow Up: After Creating an Availability Group](#FollowUp), later in this topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37708-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="37708-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37708-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="37708-125">Permissions</span></span>  
 <span data-ttu-id="37708-126">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** und die CREATE AVAILABILITY GROUP-Serverberechtigung, ALTER ANY AVAILABILITY GROUP-Berechtigung oder CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="37708-126">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-the-new-availability-group-dialog-box-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37708-127">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="37708-127">Using the New Availability Group Dialog Box (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="37708-128">**So erstellen Sie eine Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="37708-128">**To create an availability group**</span></span>  
  
1.  <span data-ttu-id="37708-129">Stellen Sie im Objekt-Explorer eine Verbindung zur Serverinstanz her, die das primäre Replikat hostet, und klicken Sie auf den Servernamen.</span><span class="sxs-lookup"><span data-stu-id="37708-129">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name.</span></span>  
  
2.  <span data-ttu-id="37708-130">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** .</span><span class="sxs-lookup"><span data-stu-id="37708-130">Expand the **AlwaysOn High Availability** node.</span></span>  
  
3.  <span data-ttu-id="37708-131">Klicken Sie mit der rechten Maustaste auf den Knoten **Verfügbarkeitsgruppen** , und wählen Sie den Befehl **Neue Verfügbarkeitsgruppe** aus.</span><span class="sxs-lookup"><span data-stu-id="37708-131">Right-click the **Availability Groups** node, and select the **New Availability Group** command.</span></span>  
  
4.  <span data-ttu-id="37708-132">Dieser Befehl erschließt das Dialogfeld **Neue Verfügbarkeitsgruppe** .</span><span class="sxs-lookup"><span data-stu-id="37708-132">This command opens up the **New Availability Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="37708-133">Verwenden Sie auf der Seite **Allgemein** das Feld **Name der Verfügbarkeitsgruppe** zur Eingabe eines Namens für die neue Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="37708-133">On the **General** page, use the **Availability group name** field to enter a name for the new availability group.</span></span> <span data-ttu-id="37708-134">Dieser Name muss ein gültiger SQL Server-Bezeichner und in allen Verfügbarkeitsgruppen im WSFC-Cluster eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="37708-134">This name must be a valid SQL Server identifier that is unique across all availability groups in the WSFC cluster.</span></span> <span data-ttu-id="37708-135">Die maximale Länge eines Verfügbarkeitsgruppennamens beträgt 128 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="37708-135">The maximum length for an availability group name is 128 characters.</span></span>  
  
6.  <span data-ttu-id="37708-136">Klicken Sie im Raster **Verfügbarkeitsdatenbanken** auf **Hinzufügen** , und geben Sie den Namen einer lokalen Datenbank ein, die zu dieser Verfügbarkeitsgruppe gehören soll.</span><span class="sxs-lookup"><span data-stu-id="37708-136">In the **Availability Databases** grid, click **Add** and enter the name of a local database that you want to belong to this availability group.</span></span> <span data-ttu-id="37708-137">Wiederholen Sie dies für jede hinzuzufügende Datenbank.</span><span class="sxs-lookup"><span data-stu-id="37708-137">Repeat this for every database to be added.</span></span> <span data-ttu-id="37708-138">Wenn Sie auf **OK**klicken, überprüft das Dialogfeld, ob die angegebene Datenbank die Voraussetzungen dafür erfüllt, dass sie einer Verfügbarkeitsgruppe angehört.</span><span class="sxs-lookup"><span data-stu-id="37708-138">When you click **OK**, the dialog will verify whether your specified database meet the prerequisites for belonging to an availability group.</span></span> <span data-ttu-id="37708-139">Informationen zur diesen Voraussetzungen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="37708-139">For information about these prerequisites, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
7.  <span data-ttu-id="37708-140">Klicken Sie im Raster **Verfügbarkeitsdatenbanken** auf **Hinzufügen** , und geben Sie den Namen einer Serverinstanz ein, um ein sekundäres Replikat zu hosten.</span><span class="sxs-lookup"><span data-stu-id="37708-140">In the **Availability Databases** grid, click **Add** and enter the name of a server instance to host a secondary replica.</span></span> <span data-ttu-id="37708-141">Das Dialogfeld versucht nicht, eine Verbindung zu diesen Instanzen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="37708-141">The dialog will not attempt to connect to these instances.</span></span> <span data-ttu-id="37708-142">Wenn Sie einen falschen Servernamen angeben, wird zwar ein sekundäres Replikat hinzugefügt, Sie können aber keine Verbindung mit diesem Replikat herstellen.</span><span class="sxs-lookup"><span data-stu-id="37708-142">If you specify an incorrect server name, a secondary replica will be added but you will be unable to connect to that replica.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="37708-143">Wenn Sie ein Replikat hinzugefügt haben und keine Verbindung zur Hostserverinstanz herstellen können, können Sie das Replikat entfernen und ein neues hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37708-143">If you have added a replica and cannot connect to the host server instance, you can remove the replica and add a new one.</span></span> <span data-ttu-id="37708-144">Weitere Informationen finden Sie unter [Entfernen eines sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) und [Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37708-144">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="37708-145">Klicken Sie im Bereich **Seite auswählen** des Dialogfelds auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="37708-145">On the **Select a page** pane of the dialog box, click **Backup Preferences**.</span></span> <span data-ttu-id="37708-146">Geben Sie dann auf der Seite **Sicherungseinstellungen** auf Grundlage der Replikatrolle an, wo die Sicherungen erstellt werden sollen, weisen Sie den einzelnen Serverinstanzen, die ein Verfügbarkeitsreplikat für diese Verfügbarkeitsgruppe hosten, Sicherungsprioritäten zu.</span><span class="sxs-lookup"><span data-stu-id="37708-146">Then, on the **Backup Preferences** page, specify where backups should occur based on replica role and assign backup priorities to each server instances that will host an availability replica for this availability group.</span></span> <span data-ttu-id="37708-147">Weitere Informationen finden Sie unter [Eigenschaften von Verfügbarkeitsgruppen: Neue Verfügbarkeitsgruppe &#40;Seite „Sicherungseinstellungen“&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span><span class="sxs-lookup"><span data-stu-id="37708-147">For more information, see [Availability Group Properties: New Availability Group &#40;Backup Preferences Page&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span></span>  
  
9. <span data-ttu-id="37708-148">Klicken Sie auf **OK**, um die Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37708-148">To create the availability group, click **OK**.</span></span> <span data-ttu-id="37708-149">Dadurch überprüft das Dialogfeld, ob die angegebenen Datenbanken die erforderlichen Komponenten erfüllen.</span><span class="sxs-lookup"><span data-stu-id="37708-149">This causes the dialog to verify whether that specified databases meet the prerequisites.</span></span>  
  
     <span data-ttu-id="37708-150">Um das Dialogfeld zu beenden, ohne die Verfügbarkeitsgruppe zu erstellen, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="37708-150">To exit the dialog box without creating the availability group, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-using-the-new-availability-group-dialog-box-to-create-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="37708-151">Nächster Schritt: Nach dem Erstellen einer Verfügbarkeitsgruppe mithilfe des Dialogfelds „Neue Verfügbarkeitsgruppe“</span><span class="sxs-lookup"><span data-stu-id="37708-151">Follow Up: After Using the New Availability Group Dialog Box to Create an Availability Group</span></span>  
  
-   <span data-ttu-id="37708-152">Sie wiederum müssen eine Verbindung zu jeder Serverinstanz herstellen, die ein sekundäres Replikat für die Verfügbarkeitsgruppe hostet, und die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="37708-152">You will need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
    1.  <span data-ttu-id="37708-153">Verknüpfen Sie das sekundäre Replikat mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="37708-153">Join the secondary replica to the availability group.</span></span> <span data-ttu-id="37708-154">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="37708-154">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
    2.  <span data-ttu-id="37708-155">Stellen Sie aktuelle Sicherungen jeder primären Datenbank und ihres Transaktionsprotokolls (mithilfe von RESTORE WITH NORECOVERY) wieder her.</span><span class="sxs-lookup"><span data-stu-id="37708-155">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="37708-156">Weitere Informationen finden Sie unter [Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)erstellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="37708-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
    3.  <span data-ttu-id="37708-157">Verknüpfen Sie jede neu vorbereitete sekundäre Datenbank sofort mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="37708-157">Immediately join each newly prepared secondary database to the availability group.</span></span> <span data-ttu-id="37708-158">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37708-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="37708-159">Wir empfehlen das Erstellen eines Verfügbarkeitsgruppenlisteners für die neue Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="37708-159">We recommend that you create an availability group listener for the new availability group.</span></span> <span data-ttu-id="37708-160">Dazu müssen Sie mit der Serverinstanz verbunden sein, auf der das aktuelle primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="37708-160">This requires that you be connected to the server instance that hosts the current primary replica.</span></span> <span data-ttu-id="37708-161">Weitere Informationen finden Sie unter [Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37708-161">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="37708-162">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="37708-162">Related Tasks</span></span>  
 <span data-ttu-id="37708-163">**So konfigurieren Sie Verfügbarkeitsgruppen- und Replikateigenschaften**</span><span class="sxs-lookup"><span data-stu-id="37708-163">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="37708-164">Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-164">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="37708-165">Ändern des Failovermodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-165">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="37708-166">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-166">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="37708-167">Konfigurieren der flexiblen Failoverrichtlinie zum Steuern der Bedingungen für ein automatisches Failover (AlwaysOn-Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="37708-167">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="37708-168">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-168">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="37708-169">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-169">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="37708-170">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-170">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="37708-171">Konfigurieren des schreibgeschützten Routing für eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-171">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="37708-172">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-172">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="37708-173">**So schließen Sie die Konfiguration von Verfügbarkeitsgruppen ab**</span><span class="sxs-lookup"><span data-stu-id="37708-173">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="37708-174">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-174">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="37708-175">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-175">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="37708-176">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-176">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="37708-177">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-177">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="37708-178">**Alternative Möglichkeiten zum Erstellen einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="37708-178">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="37708-179">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-179">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="37708-180">Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="37708-181">Erstellen einer Verfügbarkeitsgruppe &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="37708-182">**So aktivieren Sie AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="37708-182">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="37708-183">Aktivieren und Deaktivieren von Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-183">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="37708-184">**So konfigurieren Sie einen Datenbankspiegelungs-Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="37708-184">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="37708-185">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-185">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="37708-186">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-186">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="37708-187">Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-187">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="37708-188">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-188">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="37708-189">**Problembehandlung für die AlwaysOn-Verfügbarkeitsgruppenkonfiguration**</span><span class="sxs-lookup"><span data-stu-id="37708-189">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="37708-190">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfiguration (SQL Server) gelöscht</span><span class="sxs-lookup"><span data-stu-id="37708-190">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="37708-191">Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-191">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="37708-192">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="37708-192">Related Content</span></span>  
  
-   [<span data-ttu-id="37708-193">Microsoft SQL Server AlwaysOn-Lösungshandbuch zu hoher Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="37708-193">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="37708-194">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37708-194">See Also</span></span>  
 <span data-ttu-id="37708-195">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="37708-195">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="37708-196">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="37708-196">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="37708-197">[Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="37708-197">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="37708-198">Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37708-198">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  