---
title: Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- adding secondary databases
- secondary databases [SQL Server], in log shipping
- secondary data files [SQL Server], adding
- log shipping [SQL Server], secondary databases
ms.assetid: b02eba13-f8e6-4684-b7e4-75ea038ea473
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 062df1b53ed74321ba0c75c9df763de79a4802bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618248"
---
# <a name="add-a-secondary-database-to-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="9de4d-102">Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9de4d-102">Add a Secondary Database to a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="9de4d-103">In diesem Thema wird erläutert, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]einer vorhandenen Protokollversandkonfiguration eine sekundäre Datenbank hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-103">This topic describes how to add a secondary database to an existing log shipping configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9de4d-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9de4d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9de4d-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9de4d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9de4d-106">Security</span><span class="sxs-lookup"><span data-stu-id="9de4d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9de4d-107">**So fügen Sie eine sekundäre Datenbank für den Protokollversand hinzu mit:**</span><span class="sxs-lookup"><span data-stu-id="9de4d-107">**To add a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="9de4d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9de4d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9de4d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9de4d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="9de4d-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9de4d-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9de4d-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9de4d-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9de4d-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9de4d-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9de4d-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9de4d-113">Permissions</span></span>  
 <span data-ttu-id="9de4d-114">Die gespeicherten Prozeduren für den Protokollversand erfordern die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9de4d-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9de4d-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9de4d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="9de4d-116">So fügen Sie eine sekundäre Datenbank für den Protokollversand hinzu</span><span class="sxs-lookup"><span data-stu-id="9de4d-116">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="9de4d-117">Klicken Sie mit der rechten Maustaste auf die Datenbank, die Sie als primäre Datenbank in der Protokollversandkonfiguration verwenden möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9de4d-117">Right-click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9de4d-118">Klicken Sie unter **Seite auswählen**auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="9de4d-118">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="9de4d-119">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9de4d-119">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="9de4d-120">Klicken Sie auf **Verbinden** , und stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, die Sie als sekundären Server verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9de4d-120">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
5.  <span data-ttu-id="9de4d-121">Wählen Sie im Feld **Sekundäre Datenbank** eine Datenbank aus der Liste aus, oder geben Sie den Namen der Datenbank ein, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9de4d-121">In the **Secondary database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
6.  <span data-ttu-id="9de4d-122">Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option aus, die Sie zum Initialisieren der sekundären Datenbank verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9de4d-122">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
7.  <span data-ttu-id="9de4d-123">Geben Sie auf der Registerkarte **Dateien kopieren**im Ordner **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-123">On the **Copy Files tab**, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="9de4d-124">Dieser Ordner befindet sich oft auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="9de4d-124">This folder is often located on the secondary server.</span></span>  
  
8.  <span data-ttu-id="9de4d-125">Beachten Sie den Zeitplan für das Kopieren im Feld **Zeitplan** unter **Kopierauftrag**.</span><span class="sxs-lookup"><span data-stu-id="9de4d-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="9de4d-126">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan** , und passen Sie den Zeitplan des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="9de4d-126">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="9de4d-127">Dieser Zeitplan sollte ungefähr mit dem Sicherungszeitplan übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-127">This schedule should approximate the backup schedule.</span></span>  
  
9. <span data-ttu-id="9de4d-128">Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen**die Option **Kein Wiederherstellungsmodus** oder **Standbymodus** aus.</span><span class="sxs-lookup"><span data-stu-id="9de4d-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
10. <span data-ttu-id="9de4d-129">Wenn Sie die Option **Standbymodus** auswählen, legen Sie fest, ob die Benutzer von der sekundären Datenbank getrennt werden sollen, während der Wiederherstellungsvorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9de4d-129">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
11. <span data-ttu-id="9de4d-130">Wenn Sie den Wiederherstellungsprozess auf dem sekundären Server verzögern möchten, wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens**eine Verzögerungszeit aus.</span><span class="sxs-lookup"><span data-stu-id="9de4d-130">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
12. <span data-ttu-id="9de4d-131">Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in**einen Warnschwellenwert aus.</span><span class="sxs-lookup"><span data-stu-id="9de4d-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
13. <span data-ttu-id="9de4d-132">Beachten Sie den Wiederherstellungszeitplan im Feld **Zeitplan** unter **Wiederherstellungsauftrag**.</span><span class="sxs-lookup"><span data-stu-id="9de4d-132">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="9de4d-133">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan** , und passen Sie den Zeitplan des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="9de4d-133">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="9de4d-134">Dieser Zeitplan sollte ungefähr mit dem Sicherungszeitplan übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-134">This schedule should approximate the backup schedule.</span></span>  
  
14. <span data-ttu-id="9de4d-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9de4d-135">Click **OK**.</span></span>  
  
15. <span data-ttu-id="9de4d-136">Klicken Sie im Dialogfeld mit den Datenbankeigenschaften auf **OK** , um den Konfigurationsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="9de4d-136">Click **OK** on the Database Properties dialog box to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9de4d-137">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9de4d-137">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="9de4d-138">So fügen Sie eine sekundäre Datenbank für den Protokollversand hinzu</span><span class="sxs-lookup"><span data-stu-id="9de4d-138">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="9de4d-139">Führen Sie auf dem sekundären Server [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) aus, um die Details des primären Servers und der Datenbank zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-139">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="9de4d-140">Diese gespeicherte Prozedur gibt die sekundäre ID sowie die IDs des Kopier- und des Wiederherstellungsauftrags zurück.</span><span class="sxs-lookup"><span data-stu-id="9de4d-140">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
2.  <span data-ttu-id="9de4d-141">Führen Sie auf dem sekundären Server [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) aus, um den Zeitplan für den Kopier- und den Wiederherstellungsauftrag festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-141">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="9de4d-142">Führen Sie auf dem sekundären Server [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) aus, um eine sekundäre Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-142">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
4.  <span data-ttu-id="9de4d-143">Führen Sie auf dem primären Server [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) aus, um die erforderlichen Informationen über die neue sekundäre Datenbank dem primären Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9de4d-143">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
5.  <span data-ttu-id="9de4d-144">Aktivieren Sie auf dem sekundären Server den Kopier- und den Wiederherstellungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="9de4d-144">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="9de4d-145">Weitere Informationen finden sie unter [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="9de4d-145">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9de4d-146">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9de4d-146">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9de4d-147">Aktualisieren des Protokoll Versands auf SQL Server 2014 &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-147">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="9de4d-148">Konfigurieren des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-148">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="9de4d-149">Entfernen einer sekundären Datenbank aus einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-149">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="9de4d-150">Entfernen des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-150">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="9de4d-151">Anzeigen des Protokollversandberichts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-151">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="9de4d-152">Überwachen des Protokollversands &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-152">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="9de4d-153">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9de4d-153">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9de4d-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9de4d-154">See Also</span></span>  
 <span data-ttu-id="9de4d-155">[Informationen zum Protokollversand &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9de4d-155">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="9de4d-156">Protokollversandtabellen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9de4d-156">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
