---
title: Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], recovery models
- recovery [SQL Server], recovery model
- backing up databases [SQL Server], recovery models
- recovery models [SQL Server], switching
- recovery models [SQL Server], viewing
- database restores [SQL Server], recovery models
- modifying database recovery models
ms.assetid: 94918d1d-7c10-4be7-bf9f-27e00b003a0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889080301109938f0514bd6b81265c100237ab60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718307"
---
# <a name="view-or-change-the-recovery-model-of-a-database-sql-server"></a><span data-ttu-id="1646c-102">Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1646c-102">View or Change the Recovery Model of a Database (SQL Server)</span></span>
  <span data-ttu-id="1646c-103">In diesem Thema wird die Vorgehensweise zum Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1646c-103">This topic describes how to view or change the recovery model of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1646c-104">Ein *Wiederherstellungsmodell* ist eine Datenbankeigenschaft, die steuert, wie Transaktionen protokolliert werden, ob das Transaktionsprotokoll gesichert werden muss (und kann) und welche Arten von Wiederherstellungsvorgängen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1646c-104">A *recovery model* is a database property that controls how transactions are logged, whether the transaction log requires (and allows) backing up, and what kinds of restore operations are available.</span></span> <span data-ttu-id="1646c-105">Es stehen drei Wiederherstellungsmodelle zur Verfügung: einfach, vollständig und massenprotokolliert.</span><span class="sxs-lookup"><span data-stu-id="1646c-105">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="1646c-106">Für eine Datenbank wird im Allgemeinen das vollständige oder das einfache Wiederherstellungsmodell verwendet.</span><span class="sxs-lookup"><span data-stu-id="1646c-106">Typically, a database uses the full recovery model or simple recovery model.</span></span> <span data-ttu-id="1646c-107">Eine Datenbank kann jederzeit auf ein anderes Wiederherstellungsmodell umgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1646c-107">A database can be switched to another recovery model at any time.</span></span> <span data-ttu-id="1646c-108">Die **model** -Datenbank legt das Standardwiederherstellungsmodell der neuen Datenbanken fest.</span><span class="sxs-lookup"><span data-stu-id="1646c-108">The **model** database sets the default recovery model of new databases.</span></span>  
  
 <span data-ttu-id="1646c-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1646c-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1646c-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1646c-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1646c-111">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="1646c-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1646c-112">Security</span><span class="sxs-lookup"><span data-stu-id="1646c-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1646c-113">**Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="1646c-113">**To view or change the recovery model of a database, using:**</span></span>  
  
     [<span data-ttu-id="1646c-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1646c-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1646c-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1646c-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1646c-116">**Empfehlungen zur Nachverfolgung:**  [Nach dem Ändern des Wiederherstellungsmodells](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1646c-116">**Follow Up Recommendations:**  [After You Change the Recovery Model](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="1646c-117">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1646c-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1646c-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1646c-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1646c-119">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="1646c-119">Recommendations</span></span>  
  
-   <span data-ttu-id="1646c-120">Bevor Sie vom vollständigen oder massenprotokollierten Wiederherstellungsmodell umschalten, sichern Sie das Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="1646c-120">Before switching from the full recovery or bulk-logged recovery model, back up the transaction log.</span></span>  
  
-   <span data-ttu-id="1646c-121">Beim massenprotokollierten Modell ist keine Zeitpunktwiederherstellung möglich.</span><span class="sxs-lookup"><span data-stu-id="1646c-121">Point-in-time recovery is not possible with bulk-logged model.</span></span> <span data-ttu-id="1646c-122">Wenn Sie Transaktionen unter dem massenprotokollierten Wiederherstellungsmodell ausführen, für die u. U. eine Wiederherstellung des Transaktionsprotokolls erforderlich ist, besteht für diese Transaktionen die Gefahr eines Datenverlusts.</span><span class="sxs-lookup"><span data-stu-id="1646c-122">Therefore, if you run transactions under the bulk-logged recovery model that might require a transaction log restore, these transactions could be exposed to data loss.</span></span> <span data-ttu-id="1646c-123">Um die Wiederherstellbarkeit von Daten im Notfall zu maximieren, empfiehlt es sich, nur unter folgenden Bedingungen zum massenprotokollierten Wiederherstellungsmodell zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="1646c-123">To maximize data recoverability in a disaster-recovery scenario, we recommend that you switch to the bulk-logged recovery model only under the following conditions:</span></span>  
  
    -   <span data-ttu-id="1646c-124">Benutzer sind in der Datenbank derzeit nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1646c-124">Users are currently not allowed in the database.</span></span>  
  
    -   <span data-ttu-id="1646c-125">Alle während der Massenverarbeitung vorgenommenen Änderungen sind wiederherstellbar, ohne dass dazu eine Protokollsicherung erstellt werden muss, z. B. durch erneute Ausführung der Massenprozesse.</span><span class="sxs-lookup"><span data-stu-id="1646c-125">All modifications made during bulk processing are recoverable without depending on taking a log backup; for example, by re-running the bulk processes.</span></span>  
  
     <span data-ttu-id="1646c-126">Wenn Sie beide Bedingungen erfüllen, besteht während der Wiederherstellung eines Transaktionsprotokolls, das unter dem massenprotokollierten Wiederherstellungsmodell gesichert wurde, keine Gefahr eines Datenverlusts.</span><span class="sxs-lookup"><span data-stu-id="1646c-126">If you satisfy these two conditions, you will not be exposed to any data loss while restoring a transaction log that was backed up under the bulk-logged recovery model..</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1646c-127">Wenn Sie während eines Massenvorgangs auf das vollständige Wiederherstellungsmodell umstellen, sollten Sie beachten, dass sich die Protokollierung des Massenvorgangs von der minimalen Protokollierung in die vollständige Protokollierung ändert und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="1646c-127">If you switch to the full recovery model during a bulk operation, the logging of the bulk operation changes from minimal logging to full logging, and vice versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1646c-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1646c-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1646c-129">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1646c-129">Permissions</span></span>  
 <span data-ttu-id="1646c-130">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1646c-130">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1646c-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1646c-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-recovery-model"></a><span data-ttu-id="1646c-132">So zeigen Sie das Wiederherstellungsmodell an oder ändern es</span><span class="sxs-lookup"><span data-stu-id="1646c-132">To view or change the recovery model</span></span>  
  
1.  <span data-ttu-id="1646c-133">Stellen Sie eine Verbindung mit der entsprechenden Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und klicken Sie danach im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1646c-133">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1646c-134">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="1646c-134">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="1646c-135">Klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie dann auf **Eigenschaften**. Das Dialogfeld **Datenbankeigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1646c-135">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="1646c-136">Klicken Sie auf der Seite **Seite auswählen** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1646c-136">In the **Select a page** pane, click **Options**.</span></span>  
  
5.  <span data-ttu-id="1646c-137">Das aktuelle Wiederherstellungsmodell wird im Listenfeld **Wiederherstellungsmodell** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1646c-137">The current recovery model is displayed in the **Recovery model** list box.</span></span>  
  
6.  <span data-ttu-id="1646c-138">Sie können auch zum Wechseln des Wiederherstellungsmodells eine andere Modellliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="1646c-138">Optionally, to change the recovery model select a different model list.</span></span> <span data-ttu-id="1646c-139">Die Auswahlmöglichkeiten sind **Vollständig**, **Massenprotokolliert**oder **Einfach**.</span><span class="sxs-lookup"><span data-stu-id="1646c-139">The choices are **Full**, **Bulk-logged**, or **Simple**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1646c-140">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1646c-140">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-recovery-model"></a><span data-ttu-id="1646c-141">So zeigen Sie das Wiederherstellungsmodell an</span><span class="sxs-lookup"><span data-stu-id="1646c-141">To view the recovery model</span></span>  
  
1.  <span data-ttu-id="1646c-142">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="1646c-142">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1646c-143">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1646c-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1646c-144">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1646c-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1646c-145">In diesem Beispiel wird gezeigt, wie die [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) -Katalogsicht abgefragt werden muss, um mehr über das Wiederherstellungsmodell der **model** -Datenbank zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="1646c-145">This example shows how to query the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to learn the recovery model of the **model** database.</span></span>  
  
```sql  
SELECT name, recovery_model_desc  
   FROM sys.databases  
      WHERE name = 'model' ;  
GO  
  
```  
  
#### <a name="to-change-the-recovery-model"></a><span data-ttu-id="1646c-146">So ändern Sie das Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="1646c-146">To change the recovery model</span></span>  
  
1.  <span data-ttu-id="1646c-147">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="1646c-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1646c-148">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1646c-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1646c-149">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1646c-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1646c-150">In diesem Beispiel wird gezeigt, wie Sie das Wiederherstellungsmodell in der `model` -Datenbank in `FULL` mithilfe der `SET RECOVERY` -Option der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) -Anweisung ändern können.</span><span class="sxs-lookup"><span data-stu-id="1646c-150">This example shows how to change the recovery model in the `model` database to `FULL` by using the `SET RECOVERY` option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement.</span></span>  
  
```sql  
USE master ;  
ALTER DATABASE model SET RECOVERY FULL ;  
```  
  
##  <a name="follow-up-recommendations-after-you-change-the-recovery-model"></a><a name="FollowUp"></a><span data-ttu-id="1646c-151">Empfehlungen zur Nachverfolgung: nach dem Ändern des Wiederherstellungs Modells</span><span class="sxs-lookup"><span data-stu-id="1646c-151">Follow Up Recommendations: After You Change the Recovery Model</span></span>  
  
-   <span data-ttu-id="1646c-152">**Nach dem Umschalten zwischen dem vollständigen und massenprotokollierten Wiederherstellungsmodell**</span><span class="sxs-lookup"><span data-stu-id="1646c-152">**After switching between the full and bulk-logged recovery models**</span></span>  
  
    -   <span data-ttu-id="1646c-153">Wechseln Sie nach der Ausführung der Massenvorgänge sofort wieder zum vollständigen Wiederherstellungsmodus.</span><span class="sxs-lookup"><span data-stu-id="1646c-153">After completing the bulk operations, immediately switch back to full recovery mode.</span></span>  
  
    -   <span data-ttu-id="1646c-154">Sichern Sie das Protokoll erneut, nachdem Sie vom massenprotokollierten Wiederherstellungsmodell zurück zum vollständigen Wiederherstellungsmodell gewechselt sind.</span><span class="sxs-lookup"><span data-stu-id="1646c-154">After switching from the bulk-logged recovery model back to the full recovery model, back up the log.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1646c-155">Ihre Sicherungsstrategie ändert sich nicht. Führen Sie weiterhin regelmäßige Datenbanksicherungen, Protokollsicherungen und differenzielle Sicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="1646c-155">Your backup strategy remains the same: continue performing periodic database, log, and differential backups.</span></span>  
  
-   <span data-ttu-id="1646c-156">**Nach dem Umschalten vom einfachen Wiederherstellungsmodell**</span><span class="sxs-lookup"><span data-stu-id="1646c-156">**After switching from the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="1646c-157">Erstellen Sie sofort nach der Umstellung auf das vollständige Wiederherstellungsmodell bzw. das massenprotokollierte Wiederherstellungsmodell eine vollständige oder eine differenzielle Datenbanksicherung, um die Protokollkette zu starten.</span><span class="sxs-lookup"><span data-stu-id="1646c-157">Immediately after switching to the full recovery model or bulk-logged recovery model, take a full or differential database backup to start the log chain.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1646c-158">Die Umstellung auf das vollständige oder das massenprotokollierte Wiederherstellungsmodell wird erst nach der ersten Datensicherung wirksam.</span><span class="sxs-lookup"><span data-stu-id="1646c-158">The switch to the full or bulk-logged recovery model takes effect only after the first data backup.</span></span>  
  
    -   <span data-ttu-id="1646c-159">Planen Sie regelmäßige Protokollsicherungen, und aktualisieren Sie dementsprechend Ihren Wiederherstellungsplan.</span><span class="sxs-lookup"><span data-stu-id="1646c-159">Schedule regular log backups, and update your restore plan accordingly.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1646c-160">Wenn Sie das Transaktionsprotokoll nicht oft genug sichern, kann das Protokoll so stark vergrößert werden, bis kein Speicherplatz mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1646c-160">If you do not back up the log frequently enough, the transaction log can expand until it runs out of disk space.</span></span>  
  
-   <span data-ttu-id="1646c-161">**Nach dem Umschalten zum einfachen Wiederherstellungsmodell**</span><span class="sxs-lookup"><span data-stu-id="1646c-161">**After switching to the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="1646c-162">Unterbrechen Sie alle geplanten Aufträge, um das Transaktionsprotokoll zu sichern.</span><span class="sxs-lookup"><span data-stu-id="1646c-162">Discontinue any scheduled jobs for backing up the transaction log.</span></span>  
  
    -   <span data-ttu-id="1646c-163">Stellen Sie sicher, dass regelmäßige Datenbanksicherungen stattfinden.</span><span class="sxs-lookup"><span data-stu-id="1646c-163">Ensure periodic database backups are scheduled.</span></span> <span data-ttu-id="1646c-164">Datenbanksicherungen müssen regelmäßig durchgeführt werden, damit Ihre Daten geschützt sind und der inaktive Teil des Transaktionsprotokolls abgeschnitten werden kann.</span><span class="sxs-lookup"><span data-stu-id="1646c-164">Backing up your database is essential both to protect your data and to truncate the inactive portion of the transaction log.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1646c-165">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1646c-165">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1646c-166">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1646c-166">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="1646c-167">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1646c-167">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="1646c-168">Erstellen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="1646c-168">Create a Job</span></span>](../../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="1646c-169">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="1646c-169">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="1646c-170">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1646c-170">Related Content</span></span>  
  
-   <span data-ttu-id="1646c-171">[Datenbankwartungspläne](../maintenance-plans/maintenance-plans.md) (in der [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] -Onlinedokumentation)</span><span class="sxs-lookup"><span data-stu-id="1646c-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) (in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1646c-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1646c-172">See Also</span></span>  
 <span data-ttu-id="1646c-173">[Wiederherstellungsmodelle &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1646c-173">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="1646c-174">[Das Transaktionsprotokoll &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1646c-174">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="1646c-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1646c-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="1646c-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1646c-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="1646c-177">Wiederherstellungsmodelle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1646c-177">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
