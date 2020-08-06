---
title: Überwachen SQL Server verwalteten Sicherung in Azure | Microsoft-Dokumentation
description: In diesem Artikel werden Tools beschrieben, mit denen Sie die Gesamt Integrität von Sicherungen mithilfe SQL Server verwalteten Sicherung in Azure ermitteln und Fehler identifizieren können.
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: cfb9e431-7d4c-457c-b090-6f2528b2f315
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: baec99e63c70befde0cfce76e42dd6202ebc0bad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621669"
---
# <a name="monitor-sql-server-managed-backup-to-azure"></a><span data-ttu-id="eda75-103">Überwachen der verwalteten SQL Server-Sicherung in Azure</span><span class="sxs-lookup"><span data-stu-id="eda75-103">Monitor SQL Server Managed Backup to Azure</span></span>
  [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="eda75-104">verfügt über integrierte Measures, um Fehler und Probleme während der Sicherungsvorgänge zu identifizieren und wenn möglich mit Korrekturmaßnahmen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="eda75-104">has built-in measures to identify problems and errors during backup processes and remedy with corrective action when possible.</span></span>  <span data-ttu-id="eda75-105">In bestimmten Situationen ist jedoch ein Benutzereingriff erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eda75-105">However there are certain situations where user intervention is required.</span></span> <span data-ttu-id="eda75-106">In diesem Thema werden die Tools beschrieben, mit denen Sie den Gesamtintegritätsstatus von Sicherungen bestimmen und ggf. zu behebende Fehler ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="eda75-106">This topic describes the tools that you can use to determine the overall health status of backups, and identify any errors that need to be addressed.</span></span>  
  
## <a name="overview-of-ss_smartbackup-built-in-debugging"></a><span data-ttu-id="eda75-107">Übersicht über das in [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] integrierte Debuggen</span><span class="sxs-lookup"><span data-stu-id="eda75-107">Overview of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Built-in Debugging</span></span>  
 <span data-ttu-id="eda75-108">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] überprüft geplante Sicherungen in regelmäßigen Abständen und versucht, fehlerhafte Sicherungen erneut zu planen.</span><span class="sxs-lookup"><span data-stu-id="eda75-108">The [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] periodically reviews scheduled backups and attempts to reschedule any failed backups.</span></span> <span data-ttu-id="eda75-109">Das Speicherkonto wird regelmäßig abgefragt, um Unterbrechungen in Protokoll Ketten zu identifizieren, die sich auf die Wiederherstellbarkeit der Datenbank auswirken, und neue Sicherungen entsprechend</span><span class="sxs-lookup"><span data-stu-id="eda75-109">It polls the storage account periodically to identify breaks in log chains affecting recoverability of the database, and schedules new backups accordingly.</span></span> <span data-ttu-id="eda75-110">Außerdem werden die Richtlinien für die Azure-Drosselung berücksichtigt, und es gelten Mechanismen für die Verwaltung mehrerer Datenbanksicherungen.</span><span class="sxs-lookup"><span data-stu-id="eda75-110">It also takes into account Azure throttling policies, and has mechanisms in place to manage multiple database backups.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="eda75-111">verwendet erweiterte Ereignisse, um alle Aktivitäten nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="eda75-111">uses extended events to track all activity.</span></span> <span data-ttu-id="eda75-112">Die Kanäle für erweiterte Ereignisse, die vom [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]-Agent verwendet werden, umfassen Admin, Operational, Analytical und Debug.</span><span class="sxs-lookup"><span data-stu-id="eda75-112">The Extended Event channels used by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent include, Admin, Operational, Analytical, and Debug.</span></span> <span data-ttu-id="eda75-113">Ereignisse, die unter die Kategorie Admin fallen, stehen normalerweise im Zusammenhang mit Fehlern, erfordern einen Benutzereingriff und sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eda75-113">Events that fall under the Admin category usually are related to errors and require user intervention and are enabled by default.</span></span> <span data-ttu-id="eda75-114">Analytical-Ereignisse sind ebenfalls standardmäßig aktiviert, beziehen sich aber normalerweise nicht auf Fehler, die einen Benutzereingriff erfordern.</span><span class="sxs-lookup"><span data-stu-id="eda75-114">Analytical events are also turned on by default, but usually are not related to errors that require user intervention.</span></span> <span data-ttu-id="eda75-115">Operational-Ereignisse dienen typischerweise zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="eda75-115">Operation events are typically informational.</span></span> <span data-ttu-id="eda75-116">Zu den Betriebs Ereignissen zählen beispielsweise das Planen einer Sicherung, der erfolgreiche Abschluss der Sicherung usw. Das Debuggen ist die ausführlichste und wird intern von verwendet [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , um Probleme zu ermitteln und ggf. zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="eda75-116">For example, operational events include scheduling a backup, a successful completion of backup, etc. The Debug is the most verbose and is used internally by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] to determine issues and correct them if required.</span></span>  
  
### <a name="configure-monitoring-parameters-for-ss_smartbackup"></a><span data-ttu-id="eda75-117">Konfigurieren von Überwachungsparametern für [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eda75-117">Configure Monitoring Parameters for [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span></span>  
 <span data-ttu-id="eda75-118">Mit der gespeicherten System Prozedur **smart_admin. sp_set_parameter** können Sie die Überwachungs Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="eda75-118">The **smart_admin.sp_set_parameter** system stored procedure allows you to specify monitoring settings.</span></span> <span data-ttu-id="eda75-119">Die folgenden Abschnitte führen Sie durch den Vorgang zum Aktivieren erweiterter Ereignisse und zum Aktivieren von E-Mail-Benachrichtigungen bei Fehlern und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="eda75-119">The following sections walks through the process of enabling Extended Events,  and enabling email notification for errors and warnings.</span></span>  
  
 <span data-ttu-id="eda75-120">Die **smart_admin. fn_get_parameter** -Funktion kann verwendet werden, um die aktuelle Einstellung für einen bestimmten Parameter oder alle konfigurierten Parameter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eda75-120">The **smart_admin.fn_get_parameter** function can be used to get the current setting for a specific parameter or all configured parameters.</span></span> <span data-ttu-id="eda75-121">Wenn die Parameter nicht konfiguriert wurden, gibt die Funktion keine Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="eda75-121">If the parameters have never been configured, the function does not return any values.</span></span>  
  
1.  <span data-ttu-id="eda75-122">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="eda75-122">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eda75-123">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="eda75-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eda75-124">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="eda75-124">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="eda75-125">Dadurch wird die aktuelle Konfiguration für erweiterte Ereignisse und E-Mail-Benachrichtigungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eda75-125">This will return the current configuration for Extended Events, and e-mail notifications.</span></span>  
  
```sql
Use msdb  
Go  
SELECT * FROM smart_admin.fn_get_parameter (NULL)  
GO  
```  
  
 <span data-ttu-id="eda75-126">Weitere Informationen finden Sie unter [smart_admin. fn_get_parameter &#40;Transact-SQL-&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="eda75-126">For more information, see [smart_admin.fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span></span>  
  
### <a name="extended-events-for-monitoring"></a><span data-ttu-id="eda75-127">Erweiterte Ereignisse für die Überwachung</span><span class="sxs-lookup"><span data-stu-id="eda75-127">Extended Events for Monitoring</span></span>  
 <span data-ttu-id="eda75-128">Standardmäßig sind Admin-, Operational- und Analytical-Ereignisse aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eda75-128">By default, Admin, Operational and Analytical events are turned on.</span></span> <span data-ttu-id="eda75-129">Admin-Ereignisse sind am wichtigsten und hilfreich für die Ermittlung von Fehlern, die zur Behebung des Problems manuelle Eingriffe erfordern.</span><span class="sxs-lookup"><span data-stu-id="eda75-129">Admin events are most critical, useful when identifying errors that require manual intervention to solve the problem.</span></span> <span data-ttu-id="eda75-130">Sie können die Operational- und Debug-Ereignisse aktivieren, Sie sollten aber bedenken, dass diese Ereignisse ausführlich sind und möglicherweise gefiltert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="eda75-130">You may want to turn on the operational and debug events but consider that these events are verbose and may require some filtering.</span></span> <span data-ttu-id="eda75-131">Die folgenden Verfahren beschreiben, wie Sie über die erweiterten Ereignisse protokollierte Ereignisse überwachen können.</span><span class="sxs-lookup"><span data-stu-id="eda75-131">The following procedures describe how to monitor events logged through Extended Events.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eda75-132">Im Gegensatz zu erweiterten Ereignissen für SQL Engine unterstützt [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] die Konzepte von Sitzungen für erweiterte Ereignisse nicht.</span><span class="sxs-lookup"><span data-stu-id="eda75-132">Unlike Extended Events for SQL Engine, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] does not support Extended Event session concepts.</span></span> <span data-ttu-id="eda75-133">Gespeicherte Systemprozeduren und -funktionen sind die Tools für die Interaktion mit erweiterten Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="eda75-133">System stored procedures and functions are the tools used to interact with extended events.</span></span> <span data-ttu-id="eda75-134">Sie können das Protokoll für erweiterte Ereignisse im Protokollverzeichnis anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eda75-134">You can also view the extended event log from the log directory.</span></span>  
  
##### <a name="to-configure-and-view-extended-events"></a><span data-ttu-id="eda75-135">So konfigurieren Sie erweiterte Ereignisse und zeigen sie an</span><span class="sxs-lookup"><span data-stu-id="eda75-135">To Configure and View Extended Events</span></span>  
  
1.  <span data-ttu-id="eda75-136">Führen Sie die folgende Abfrage aus, um verfügbare Kanäle für erweiterte Ereignisse und ihren aktuellen Status anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="eda75-136">To view available Extended Event channels and their current status by running the following query:</span></span>  
  
    ```sql
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="eda75-137">In der Ausgabe dieser Abfrage wird der event_name angezeigt und ob es konfiguriert werden kann und derzeit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eda75-137">The output from this query will display the event_name, whether it is configurable or not, and whether it is currently enabled.</span></span>  <span data-ttu-id="eda75-138">Weitere Informationen finden Sie unter [smart_admin. fn_get_current_xevent_settings &#40;Transact-SQL-&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eda75-138">For more information, see [smart_admin.fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span></span>  
  
2.  <span data-ttu-id="eda75-139">Um Debug-Ereignisse zu aktivieren, führen Sie die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="eda75-139">To enable debug events, run the following query:</span></span>  
  
    ```sql
    --  to enable debug events  
    Use msdb;  
    GO 
    EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
    ```  
  
     <span data-ttu-id="eda75-140">Weitere Informationen zur gespeicherten Prozedur finden Sie unter [smart_admin. sp_set_parameter &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eda75-140">For more information about the stored procedure, see [smart_admin.sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span></span>  
  
3.  <span data-ttu-id="eda75-141">Führen Sie die folgende Abfrage aus, um die protokollierten Ereignisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="eda75-141">To view the logged events run the following query:</span></span>  
  
    ```sql
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;
    ```  
  
    ```sql
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'
    ```  
  
### <a name="aggregated-error-countshealth-status"></a><span data-ttu-id="eda75-142">Aggregierte Fehleranzahl/Integritätsstatus</span><span class="sxs-lookup"><span data-stu-id="eda75-142">Aggregated Error Counts/Health Status</span></span>  
 <span data-ttu-id="eda75-143">Die **smart_admin. fn_get_health_status** -Funktion gibt eine Tabelle der aggregierten Fehler Anzahl für jede Kategorie zurück, die zum Überwachen des Integritäts Status von verwendet werden kann [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eda75-143">The **smart_admin.fn_get_health_status** function returns a table of aggregated error counts for each category that can be used to monitor the health status of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="eda75-144">Die gleiche Funktion verwendet auch der vom System konfigurierte E-Mail-Benachrichtigungsmechanismus, der weiter unten in diesem Thema beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="eda75-144">This same function is also used by the system configured e-mail notification mechanism described later in this topic.</span></span>   
<span data-ttu-id="eda75-145">Anhand dieser aggregierten Anzahl kann die Systemintegrität überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="eda75-145">These aggregated counts can be used to monitor system health.</span></span> <span data-ttu-id="eda75-146">Wenn beispielsweise die Spalte number_ of_retention_loops 0 in 30 Minuten ist, benötigt die Beibehaltungsverwaltung viel Zeit oder funktioniert nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="eda75-146">For example, if the number_ of_retention_loops column is 0 in 30 minutes, it is possible that retention management is taking long time or even not working correctly.</span></span> <span data-ttu-id="eda75-147">Spalten mit Werten ungleich 0 können auf Probleme hindeuten. Sie sollten die Protokolle der erweiterten Ereignisse prüfen, um das Problem zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="eda75-147">Non-zero error columns may indicate problems and Extended Events logs should be checked to discover the problem.</span></span> <span data-ttu-id="eda75-148">Rufen Sie alternativ **smart_admin sp_get_backup_diagnostics** gespeicherten Prozedur auf, um die Details des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="eda75-148">Alternatively, call **smart_admin.sp_get_backup_diagnostics** stored procedure to find the details of the error.</span></span>  
  
### <a name="using-agent-notification-for-assessing-backup-status-and-health"></a><span data-ttu-id="eda75-149">Verwenden von Agent-Benachrichtigungen zum Bewerten von Sicherungsstatus und -integrität</span><span class="sxs-lookup"><span data-stu-id="eda75-149">Using Agent Notification for Assessing Backup Status and Health</span></span>  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="eda75-150">verfügt über einen Benachrichtigungsmechanismus, der auf Verwaltungsrichtlinien auf Grundlage von SQL Server-Richtlinien beruht.</span><span class="sxs-lookup"><span data-stu-id="eda75-150">includes a notification mechanism that is based on SQL Server policy based management policies.</span></span>  
  
 <span data-ttu-id="eda75-151">**Voraussetzungen:**</span><span class="sxs-lookup"><span data-stu-id="eda75-151">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="eda75-152">Datenbank-E-Mail ist erforderlich, um diese Funktionen verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="eda75-152">Database Mail is required to use this functionality.</span></span> <span data-ttu-id="eda75-153">Weitere Informationen zum Aktivieren von DB-e-Mail für die Instanz von SQL Server finden Sie unter [configure Datenbank-E-Mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="eda75-153">For more information, about how to enable DB Mail for the instance of SQL Server, see [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
-   <span data-ttu-id="eda75-154">Die Eigenschaften des SQL Server-Agent-Warnsystems sollten für die Verwendung der Datenbank-E-Mail festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="eda75-154">SQL Server Agent Alert System properties should be set to use Database Mail.</span></span>  
  
 <span data-ttu-id="eda75-155">**Benachrichtigungsarchitektur:**</span><span class="sxs-lookup"><span data-stu-id="eda75-155">**Notification Architecture:**</span></span>  
  
-   <span data-ttu-id="eda75-156">**Richtlinien basierte Verwaltung:** Zwei Richtlinien sind zum Überwachen der Sicherungs Integrität festgelegt: Integritätsrichtlinie für das **Smart admin-System**und die Richtlinie zur Integritäts **Richtlinie für Smart admin**</span><span class="sxs-lookup"><span data-stu-id="eda75-156">**Policy Based Management:** Two policies are set to monitor backup health: **Smart Admin System Health Policy**, and the **Smart Admin User Action Health Policy**.</span></span> <span data-ttu-id="eda75-157">Die Smart Admin-Richtlinie für die Systemintegrität wertet kritische Fehler wie fehlende oder ungültige SQL-Anmeldeinformationen oder Verbindungsfehler aus und meldet die Integrität des Systems.</span><span class="sxs-lookup"><span data-stu-id="eda75-157">The Smart Admin System Health Policy evaluates critical errors like lack of or invalid SQL Credentials, connectivity errors and reports the health of the system.</span></span> <span data-ttu-id="eda75-158">Bei diesen ist normalerweise ein manueller Eingriff erforderlich, um das zugrunde liegende Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="eda75-158">These typically require a manual action to correct the underlying issue.</span></span> <span data-ttu-id="eda75-159">Die Smart Admin-Richtlinie für die Integrität von Benutzeraktionen wertet Warnungen aus, z. B. beschädigte Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="eda75-159">The Smart Admin User Action Health Policy evaluates warnings such as corrupted backups, and such.</span></span>  <span data-ttu-id="eda75-160">Bei diesen ist möglicherweise keine Aktion erforderlich, sondern stellen lediglich eine Warnung zu einem Ereignis dar.</span><span class="sxs-lookup"><span data-stu-id="eda75-160">These may not require any action but just a warning of an event.</span></span> <span data-ttu-id="eda75-161">Es wird erwartet, dass solche Probleme automatisch vom [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]-Agent behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="eda75-161">It is expected that such issues will be automatically taken care of by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent.</span></span>  
  
-   <span data-ttu-id="eda75-162">**SQL Server-Agent** Job: die Benachrichtigung wird mithilfe eines SQL Server-Agent Auftrags ausgeführt, der drei Auftrags Schritte umfasst.</span><span class="sxs-lookup"><span data-stu-id="eda75-162">**SQL Server Agent** Job: The notification is performed using a SQL Server Agent job that has three job steps.</span></span> <span data-ttu-id="eda75-163">Im ersten Auftragsschritt wird ermittelt, ob [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine Datenbank oder eine Instanz konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="eda75-163">In the first job step it detects to see whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured for a database or instance.</span></span> <span data-ttu-id="eda75-164">Wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] aktiviert und konfiguriert vorgefunden wird, wird der zweite Schritt ausgeführt: Es wird ein PowerShell-Cmdlet ausgeführt, das den Integritätsstatus bewertet, indem die Verwaltungsrichtlinien auf Grundlage von SQL Server-Richtlinien ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="eda75-164">If it finds [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled and configured, it executes the second step: executes a PowerShell cmdlet that assess the health status by evaluating the SQL Server policy based management policies.</span></span> <span data-ttu-id="eda75-165">Wenn ein Fehler oder eine Warnung gefunden wird, schlägt der Vorgang fehl, und es wird der dritte Schritt ausgelöst: Eine E-Mail-Benachrichtigung mit dem Fehler-/Warnbericht wird gesendet.</span><span class="sxs-lookup"><span data-stu-id="eda75-165">If it finds either an error or warning, it fails which then triggers the third step: The third step sends out an e-mail notification with the error/warning report.</span></span>  <span data-ttu-id="eda75-166">Dieser SQL Server-Agent-Auftrag ist jedoch nicht standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eda75-166">However this SQL Server Agent job is not enabled by default.</span></span> <span data-ttu-id="eda75-167">Verwenden Sie die gespeicherte System Prozedur **smart_admin. sp_set_backup_parameter** , um den e-Mail-Benachrichtigungs Auftrag zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eda75-167">To enable the e-mail notification job, use the **smart_admin.sp_set_backup_parameter** system stored procedure.</span></span>  <span data-ttu-id="eda75-168">Das folgende Verfahren beschreibt diese Schritte ausführlicher:</span><span class="sxs-lookup"><span data-stu-id="eda75-168">The following procedure describes the steps in more detail:</span></span>  
  
##### <a name="enabling-email-notification"></a><span data-ttu-id="eda75-169">Aktivieren der E-Mail-Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="eda75-169">Enabling Email Notification</span></span>  
  
1.  <span data-ttu-id="eda75-170">Wenn Datenbank-E-Mail nicht bereits konfiguriert ist, befolgen Sie die Schritte unter [Konfigurieren von Datenbank-E-Mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="eda75-170">If Database Mail is not already configured, use the steps described in [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
2.  <span data-ttu-id="eda75-171">Datenbank als Mailsystem für SQL Server Warnungs System festlegen: Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, wählen Sie Warnungs **System**aus, aktivieren Sie das Kontrollkästchen **Mail Profil aktivieren** , wählen Sie **Datenbank-E-Mail** als e- **Mail-System**aus, und wählen Sie ein zuvor erstelltes</span><span class="sxs-lookup"><span data-stu-id="eda75-171">Set database as the Mail System for SQL Server Alert System: Right Click on **SQL Server Agent**, select **Alert System**, check the **Enable mail profile** box, Select **Database Mail** as the **Mail System**, and select a previously created Mail profile.</span></span>  
  
3.  <span data-ttu-id="eda75-172">Führen Sie die folgende Abfrage in einem Abfragefenster aus, und geben Sie die E-Mail-Adresse an, an die die Benachrichtigung gesendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="eda75-172">Run the following query in a query window and provide the e-mail address where you want the notification to be sent to:</span></span>  
  
    ```sql
    Use msdb  
    Go  
    EXEC smart_admin.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'
    ```  
  
     <span data-ttu-id="eda75-173">Dadurch wird ein SQL Server-Agent-Auftrag erstellt, der zum Abrufen des Integritätsstatus und zum Senden von Benachrichtigungen verwendet wird, wenn ein Fehler oder ein Problem mit Sicherungen auftritt.</span><span class="sxs-lookup"><span data-stu-id="eda75-173">This creates a SQL Server Agent job that is used to gather health status and send notifications when there is an error or an issue with backups.</span></span>  
  
 <span data-ttu-id="eda75-174">Im Folgenden ist ein Beispielskript aufgeführt, mit dem die Datenbank-E-Mail aktiviert und E-Mail-Benachrichtigungen über den SQL Server-Agent-Auftrag eingerichtet werden:</span><span class="sxs-lookup"><span data-stu-id="eda75-174">Following is a sample script  to enable DB Mail and set up the e-mail notification through SQL Server Agent Job</span></span>  
  
```sql
-- Prereq: Make sure that SQL Server service runs in a service account that has  
--  access to SMTP Server   
-- set SQL Server service account as domain account   
  
EXEC sp_configure 'show advanced', 1  
RECONFIGURE  
GO  
  
-- Enable DBMail  
EXEC sp_configure 'Database Mail XPs',1  
GO  
RECONFIGURE  
GO  
  
-- Configure DBMail  
DECLARE @emailid NVARCHAR(255)  
-- Note: change this email to your own email id  
SET @emailid = N'emailalias@mycompany.com'  
  
DECLARE @smtpserver NVARCHAR(255)  
SET @smtpserver = N'smtphost.domainname.com'  
  
DECLARE @mailprofile NVARCHAR(255)  
SET @mailprofile = N'my_profile'  
  
EXEC msdb.dbo.sysmail_add_account_sp @account_name=N'myaccount',  
                @email_address = @emailid,  
                @replyto_address = @emailid,  
                @mailserver_name = @smtpserver,  
                @use_default_credentials = 1  
  
EXEC msdb.dbo.sysmail_add_profile_sp @profile_name=@mailprofile  
EXEC msdb.dbo.sysmail_add_profileaccount_sp @profile_name=@mailprofile, @account_name=N'myaccount', @sequence_number=1  
  
-- Set SQL Agent to use DBMail profile  
EXEC msdb.dbo.sp_set_sqlagent_properties @databasemail_profile = @mailprofile  
  
-- Configure Notifications   
EXEC msdb.smart_admin.sp_set_parameter  
@parameter_name = 'SSMBackup2WANotificationEmailIds',  
@parameter_value = @emailid  
  
-- To test is you are receiving notifications  
-- delete few backup files from your storage container, Wait for 15 minutes & see if you get any email notification
```  
  
### <a name="using-powershell-to-setup-custom-health-monitoring"></a><span data-ttu-id="eda75-175">Einrichten einer benutzerdefinierten Integritätsüberwachung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="eda75-175">Using PowerShell to Setup Custom Health Monitoring</span></span>  
 <span data-ttu-id="eda75-176">Das **Test-sqlsmartadmin-** Cmdlet kann zum Erstellen einer benutzerdefinierten Integritäts Überwachung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eda75-176">The **Test-SqlSmartAdmin** cmdlet can be used to create custom health monitoring.</span></span> <span data-ttu-id="eda75-177">Beispielsweise kann die im vorhergehenden Abschnitt beschriebene Benachrichtigungsoption auf Instanzebene konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="eda75-177">For example, the notification option described in the previous section can be configured at the instance level.</span></span>  <span data-ttu-id="eda75-178">Wenn Sie mehrere SQL Server-Instanzen für die Verwendung von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] konfiguriert haben, können Sie mit dem PowerShell-Cmdlet Skripts erstellen, die den Status und die Integrität von Sicherungen für alle Instanzen erfassen.</span><span class="sxs-lookup"><span data-stu-id="eda75-178">If you have several instances of SQL Server configured to use [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], the PowerShell cmdlet can be used to create scripts in gather the status and health of backups for all the instances.</span></span>  
  
 <span data-ttu-id="eda75-179">Das **Test-sqlsmartadmin** -Cmdlet bewertet die Fehler und Warnungen, die von den SQL Server Richtlinien basierten Verwaltungsrichtlinien zurückgegeben werden, und meldet einen rollupstatus.</span><span class="sxs-lookup"><span data-stu-id="eda75-179">The **Test-SqlSmartAdmin** cmdlet assesses the errors and warnings returned by the SQL Server Policy Based Management policies and reports out a rolled up status.</span></span>  <span data-ttu-id="eda75-180">Dieses Cmdlet verwendet standardmäßig die Systemrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="eda75-180">By default this cmdlet uses the system policies.</span></span> <span data-ttu-id="eda75-181">Mit dem `-AllowUserPolicies`-Parameter können Sie beliebige benutzerdefinierte Richtlinien einschließen.</span><span class="sxs-lookup"><span data-stu-id="eda75-181">To include any custom policy use the `-AllowUserPolicies` parameter.</span></span>  
  
 <span data-ttu-id="eda75-182">Im Folgenden ist ein PowerShell-Beispielskript aufgeführt, das einen Bericht über Fehler und Warnungen auf Grundlage der Systemrichtlinien und ggf. von erstellten Benutzerrichtlinien zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="eda75-182">Following is a sample PowerShell script that returns a report of errors and warnings based on the system policies and any user policies created:</span></span>  
  
```powershell
$policyResults = Get-SqlSmartAdmin | Test-SqlSmartAdmin -AllowUserPolicies  
$policyResults.PolicyEvaluationDetails | Select Name, Category, Expression, Result, Exception | fl
```  
  
 <span data-ttu-id="eda75-183">Das folgende Skript gibt einen ausführlichen Bericht zu den Fehlern und Warnungen für die Standard Instanz ( `\SQL\COMPUTER\DEFAULT` ) zurück:</span><span class="sxs-lookup"><span data-stu-id="eda75-183">The following script returns a detailed report of the errors and warnings for the default instance (`\SQL\COMPUTER\DEFAULT`):</span></span>  
  
```powershell
(Get-SqlSmartAdmin ).EnumHealthStatus()  
```  
  
### <a name="objects-in-msdb-database"></a><span data-ttu-id="eda75-184">Objekte in einer MSDB-Datenbank</span><span class="sxs-lookup"><span data-stu-id="eda75-184">Objects in MSDB database</span></span>  
 <span data-ttu-id="eda75-185">Einige Objekte werden installiert, um die Funktionalität zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="eda75-185">There are objects that are installed to implement the functionality.</span></span> <span data-ttu-id="eda75-186">Diese Objekte sind für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="eda75-186">These objects are reserved for internal use.</span></span> <span data-ttu-id="eda75-187">Eine Systemtabelle kann jedoch bei der Überwachung des Sicherungsstatus von Nutzen sein: smart_backup_files.</span><span class="sxs-lookup"><span data-stu-id="eda75-187">However, there is one system table that can be useful in monitoring the backup status: smart_backup_files.</span></span> <span data-ttu-id="eda75-188">Die meisten der in dieser Tabelle gespeicherten Informationen, die sich auf die Überwachung wie den Sicherungstyp, den Datenbanknamen, die erste und die letzte LSN beziehen, werden mit der Systemfunktion [smart_admin. fn_available_backups &#40;Transact-SQL-&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql)verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="eda75-188">Most of the Information   stored in this table relevant to monitoring like the type of backup, database name, first and last lsn, backup expiry dates are exposed through the system function [smart_admin.fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span></span> <span data-ttu-id="eda75-189">Die Statusspalte in der smart_backup_files-Tabelle, die den Status der Sicherungsdatei angibt, ist bei Verwendung der Funktion jedoch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eda75-189">However the status column in the smart_backup_files table which indicates the status of the backup file is not available using the function.</span></span> <span data-ttu-id="eda75-190">Mithilfe der folgenden Beispielabfrage können verschiedene Informationen, u. a. auch der Status, aus der Systemtabelle abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="eda75-190">Following is a sample query you can use to retrieve the some information including the status from the system table:</span></span>  
  
```sql
USE msdb  
GO  
SELECT  
 database_name AS [Database Name] ,backup_path AS [Backup Destination and File]  
,[Backup Type] =  
CASE backup_type  
WHEN 1 THEN 'FULL'  
WHEN 2 THEN 'LOG'  
END  
,[Backup Status] =  
CASE [status]  
WHEN 'A' THEN 'Available'  
WHEN 'B' THEN 'Copy In Progress'  
WHEN 'C' THEN 'Corrupted'  
WHEN 'D' THEN 'Deleted'  
WHEN 'F' THEN 'Copy Failed'  
WHEN 'U' THEN 'Unknown'  
END  
,first_lsn AS [First LSN]  
,last_lsn AS [Last LSN]  
,backup_start_date AS [Backup Start Time]  
,backup_finish_date AS [Backup Completion Time]  
,expiration_date AS [Backup Expiry Date/Time]  
FROM  
smart_backup_files;
```  
  
 <span data-ttu-id="eda75-191">Im Folgenden werden die unterschiedlichen zurückgegebenen Statusangaben ausführlich erläutert:</span><span class="sxs-lookup"><span data-stu-id="eda75-191">Following is a detailed explanation of the different status returned:</span></span>  
  
-   <span data-ttu-id="eda75-192">**Verfügbar-A:** Dies ist eine normale Sicherungsdatei.</span><span class="sxs-lookup"><span data-stu-id="eda75-192">**Available - A:** This is a normal backup file.</span></span> <span data-ttu-id="eda75-193">Die Sicherung wurde abgeschlossen und außerdem überprüft, ob Sie im Azure-Speicher verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="eda75-193">The backup has been completed, and also verified that it is available in the Azure storage.</span></span>  
  
-   <span data-ttu-id="eda75-194">**Kopieren in Bearbeitung: B:** Dieser Status gilt speziell für Verfügbarkeits Gruppen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="eda75-194">**Copy in Progress -B:** This status is specifically for Availability Group databases.</span></span> <span data-ttu-id="eda75-195">Wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] eine Unterbrechung in der Sicherungsprotokollkette feststellt, wird zunächst versucht, die Sicherung zu ermitteln, die die Unterbrechung in der Sicherungskette verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="eda75-195">If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detects a break in the backup log chain, it will first attempt identify the  backup that might have caused the break in backup chain.</span></span> <span data-ttu-id="eda75-196">Beim Suchen der Sicherungsdatei wird versucht, die Datei in Azure Storage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="eda75-196">On finding the backup file it attempts to copy the file to Azure storage.</span></span> <span data-ttu-id="eda75-197">Dieser Status wird angezeigt, wenn der Kopiervorgang gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eda75-197">When the copying process is in progress it will display this status.</span></span>  
  
-   <span data-ttu-id="eda75-198">Fehler beim **kopieren: F:** Ähnlich wie bei der laufenden Kopie handelt es sich hierbei um bestimmte t-Verfügbarkeits Gruppen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="eda75-198">**Copy Failed - F:** Similar to Copy In Progress, this is specific t Availability Group databases.</span></span> <span data-ttu-id="eda75-199">Wenn der Kopiervorgang fehlschlägt, lautet der Status F.</span><span class="sxs-lookup"><span data-stu-id="eda75-199">If the copy process fails, the status is marked as F.</span></span>  
  
-   <span data-ttu-id="eda75-200">**Beschädigt-C:** Wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] die Sicherungsdatei im Speicher nicht überprüfen kann, indem Sie einen Restore HEADER_ONLY-Befehl selbst nach mehreren versuchen ausführt, wird diese Datei als beschädigt markiert.</span><span class="sxs-lookup"><span data-stu-id="eda75-200">**Corrupted - C:** If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is unable to verify the backup file in the storage by performing a RESTORE HEADER_ONLY command even after multiple attempts, it marks this file as corrupted.</span></span> <span data-ttu-id="eda75-201">Damit die beschädigte Datei keine Unterbrechung in der Sicherungskette verursacht, wird von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] eine Sicherung geplant.</span><span class="sxs-lookup"><span data-stu-id="eda75-201">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup to ensure that the corrupted file does not result in a break of the backup chain.</span></span>  
  
-   <span data-ttu-id="eda75-202">**Gelöscht-D:** Die entsprechende Datei wurde im Azure-Speicher nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="eda75-202">**Deleted - D:** The corresponding file cannot be found in the Azure storage.</span></span> <span data-ttu-id="eda75-203">Wenn die gelöschte Datei eine Unterbrechung in der Sicherungskette verursacht, wird von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] eine Sicherung geplant.</span><span class="sxs-lookup"><span data-stu-id="eda75-203">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup if the deleted file results in a break in the backup chain.</span></span>  
  
-   <span data-ttu-id="eda75-204">**Unbekannt-U:** Dieser Status [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] gibt an, dass noch nicht in der Lage war, das vorhanden sein von Dateien und deren Eigenschaften im Azure-Speicher zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eda75-204">**Unknown - U:** This status indicated that [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has not yet been able to verify file existence and its properties in the Azure storage.</span></span> <span data-ttu-id="eda75-205">Wenn der Prozess zum nächsten Mal ausgeführt wird, d. h. alle 15 Minuten, wird dieser Status aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="eda75-205">The next time the process runs, which is approximately every 15 minutes, this status will be updated.</span></span>  
