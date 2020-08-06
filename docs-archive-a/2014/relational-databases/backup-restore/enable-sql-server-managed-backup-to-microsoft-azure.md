---
title: Einrichten SQL Server Managed Backup in Azure | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/04/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 68ebb53e-d5ad-4622-af68-1e150b94516e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9e3b86fde91028106263310aad8a1952fc041a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621522"
---
# <a name="setting-up-sql-server-managed-backup-to-azure"></a><span data-ttu-id="69713-102">Einrichten der verwalteten SQL Server-Sicherung in Azure</span><span class="sxs-lookup"><span data-stu-id="69713-102">Setting up SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="69713-103">Dieses Thema umfasst zwei Lernprogramme:</span><span class="sxs-lookup"><span data-stu-id="69713-103">This topic includes two tutorials:</span></span>  
  
 <span data-ttu-id="69713-104">Einrichten von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] auf Datenbankebene, Aktivieren der E-Mail-Benachrichtigung und Überwachen der Sicherungsaktivität</span><span class="sxs-lookup"><span data-stu-id="69713-104">Set up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="69713-105">Einrichten von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] auf Instanzebene, Aktivieren der E-Mail-Benachrichtigung und Überwachen der Sicherungsaktivität</span><span class="sxs-lookup"><span data-stu-id="69713-105">Setting up  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the instance level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="69713-106">Ein Tutorial zum Einrichten [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] von für Verfügbarkeits Gruppen finden Sie unter [Einrichten SQL Server verwalteten Sicherung für die Microsoft Azure von Verfügbarkeits Gruppen](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="69713-106">For a tutorial on setting up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for Availability Groups, see [Setting up SQL Server Managed Backup to Microsoft Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
## <a name="setting-up-ss_smartbackup"></a><span data-ttu-id="69713-107">Einrichten von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69713-107">Setting Up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span></span>  
  
### <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><span data-ttu-id="69713-108">Aktivieren und Konfigurieren von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="69713-108">Enable and Configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="69713-109">In diesem Lernprogramm werden die notwendigen Schritte zum Aktivieren und Konfigurieren von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] für eine Datenbank (TestDB) beschrieben, gefolgt von den Schritten, mit denen die Überwachung des "[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]"-Integritätsstatus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="69713-109">This tutorial describes the steps necessary to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a database (TestDB), followed by steps to enable monitoring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="69713-110">**Berechtigungen:**</span><span class="sxs-lookup"><span data-stu-id="69713-110">**Permissions:**</span></span>  
  
-   <span data-ttu-id="69713-111">Erfordert die Mitgliedschaft in **db_backupoperator** Daten Bank Rolle mit **ALTER ANY CREDENTIAL** -Berechtigungen und `EXECUTE` Berechtigungen für **sp_delete_backuphistory**gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="69713-111">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="69713-112">Erfordert **Select** -Berechtigungen für die **smart_admin. fn_get_current_xevent_settings**-Funktion.</span><span class="sxs-lookup"><span data-stu-id="69713-112">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="69713-113">Erfordert `EXECUTE` Berechtigungen für die gespeicherte Prozedur **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="69713-113">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="69713-114">Außerdem sind `VIEW SERVER STATE`-Berechtigungen erforderlich, da andere Systemobjekte, die diese Berechtigung erfordern, intern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="69713-114">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  
  
-   <span data-ttu-id="69713-115">Erfordert `EXECUTE` Berechtigungen für die `smart_admin.sp_set_instance_backup` `smart_admin.sp_backup_master_switch` gespeicherten Prozeduren und.</span><span class="sxs-lookup"><span data-stu-id="69713-115">Requires `EXECUTE` permissions on the `smart_admin.sp_set_instance_backup` and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  


1.  <span data-ttu-id="69713-116">**Erstellen Sie ein Microsoft Azure Speicherkonto:** Die Sicherungen werden im Microsoft Azure Speicher Dienstanbieter gespeichert.</span><span class="sxs-lookup"><span data-stu-id="69713-116">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="69713-117">Sie müssen zunächst ein Microsoft Azure Speicherkonto erstellen, wenn Sie noch nicht über ein Konto verfügen.</span><span class="sxs-lookup"><span data-stu-id="69713-117">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="69713-118">In SQL Server 2014 werden seitenblobs verwendet, die sich von Block-und anfügeblobs unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="69713-118">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="69713-119">Daher müssen Sie ein allgemeines Konto erstellen und kein BLOB-Konto.</span><span class="sxs-lookup"><span data-stu-id="69713-119">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="69713-120">Weitere Informationen finden Sie unter [Informationen zu Azure-Speicherkonten](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="69713-120">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="69713-121">Notieren Sie den Speicherkontonamen und die Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="69713-121">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="69713-122">Aus dem Speicherkontonamen und den Zugriffsschlüsseln werden SQL-Anmeldeinformationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="69713-122">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="69713-123">Die SQL-Anmeldeinformationen werden zur Authentifizierung beim Speicherkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="69713-123">The SQL Credential is used to authenticate to the storage account.</span></span>  
 
2.  <span data-ttu-id="69713-124">**Erstellen Sie SQL** -Anmelde Informationen: Erstellen Sie SQL-Anmelde Informationen, indem Sie den Namen des Speicher Kontos als Identität und den Speicherzugriffs Schlüssel als Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="69713-124">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="69713-125">**Stellen Sie sicher SQL Server-Agent der Dienst gestartet wird und ausgeführt wird:**  Starten Sie SQL Server-Agent, wenn er derzeit nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69713-125">**Ensure SQL Server Agent service is Started and Running:**  Start SQL Server Agent if it is not currently running.</span></span>  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="69713-126">benötigt einen laufenden SQL Server-Agent auf der Instanz, um Sicherungsvorgänge durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="69713-126">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="69713-127">Sie können den Starttyp des SQL Server-Agents auf "Automatisch" festlegen, um zu gewährleisten, dass regelmäßige Sicherungsvorgänge durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="69713-127">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="69713-128">**Bestimmen des Aufbewahrungszeitraums:** Bestimmen Sie die Beibehaltungsdauer für die Sicherungsdateien.</span><span class="sxs-lookup"><span data-stu-id="69713-128">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="69713-129">Die Beibehaltungsdauer wird in Tagen angegeben und kann zwischen 1 und 30 Tagen liegen.</span><span class="sxs-lookup"><span data-stu-id="69713-129">The retention period is specified in days and can range from 1 to 30.</span></span>  
  
5.  <span data-ttu-id="69713-130">**Aktivieren und konfigurieren [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** starten Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der Instanz her, auf der die Datenbank installiert ist</span><span class="sxs-lookup"><span data-stu-id="69713-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance where the database is installed.</span></span> <span data-ttu-id="69713-131">Führen Sie im Abfragefenster folgende Anweisung aus, nachdem Sie die Werte für Datenbankname, SQL-Anmeldeinformationen, Beibehaltungsdauer und Verschlüsselungsoptionen Ihren Anforderungen entsprechend angepasst haben:</span><span class="sxs-lookup"><span data-stu-id="69713-131">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="69713-132">Weitere Informationen zum Erstellen eines Zertifikats für die Verschlüsselung finden Sie im Schritt **Erstellen eines Sicherungs Zertifikats** unter [Erstellen einer verschlüsselten Sicherung](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="69713-132">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="69713-133">ist damit für die angegebene Datenbank aktiviert.</span><span class="sxs-lookup"><span data-stu-id="69713-133">is now enabled on the database you specified.</span></span> <span data-ttu-id="69713-134">Es kann bis zu 15 Minuten dauern, bis die Sicherungsvorgänge für die Datenbank gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="69713-134">It may take up to 15 minutes for the backup operations on the database to start to run.</span></span>  
  
6.  <span data-ttu-id="69713-135">**Überprüfen der Standardkonfiguration für erweiterte Ereignisse:** Überprüfen Sie die Einstellungen für erweiterte Ereignisse, indem Sie die folgende Transact-SQL-Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="69713-135">**Review Extended Event Default Configuration:** Review the Extended Event settings by running the following transact-SQL statement.</span></span>  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="69713-136">Stellen Sie sicher, dass Ereignisse der Kanäle Admin, Operational und Analytical standardmäßig aktiviert sind und nicht deaktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="69713-136">You should see that Admin, Operational, and Analytical channel events are enabled by default and cannot be disabled.</span></span> <span data-ttu-id="69713-137">Dies sollte ausreichen, um alle Ereignisse zu überwachen, die ein manuelles Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="69713-137">This should be sufficient to monitor the events that require manual intervention.</span></span>  <span data-ttu-id="69713-138">Sie können die Debugereignisse ebenfalls aktivieren. Diese Kanäle enthalten jedoch auch Informations- und Debugereignisse, die [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] intern zur Erkennung und Behebung von Fehlern verwendet.</span><span class="sxs-lookup"><span data-stu-id="69713-138">You can enable debug events, but the debug channels include informational and debug events that [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] uses to detect issues and solve them.</span></span> <span data-ttu-id="69713-139">Weitere Informationen finden Sie unter [überwachen SQL Server verwalteten Sicherung in Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="69713-139">For more information, see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
7.  <span data-ttu-id="69713-140">**Aktivieren und Konfigurieren der Benachrichtigung für den Integritätsstatus:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] verfügt über eine gespeicherte Prozedur, die einen Agent-Auftrag erstellt, um E-Mail-Benachrichtigungen mit Fehlern oder Warnungen zu senden, die möglicherweise ein Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="69713-140">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span> <span data-ttu-id="69713-141">In den folgenden Schritten wird der Prozess zum Aktivieren und Konfigurieren der E-Mail-Benachrichtigungen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="69713-141">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="69713-142">Richten Sie Datenbank-E-Mail ein, falls diese Funktion auf der Instanz noch nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="69713-142">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="69713-143">Weitere Informationen finden Sie unter [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="69713-143">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="69713-144">Konfigurieren Sie SQL Server-Agent-Benachrichtigungen für die Verwendung von Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="69713-144">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="69713-145">Weitere Informationen finden Sie unter [Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="69713-145">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="69713-146">**Aktivieren der E-mail-Benachrichtigungen für den Empfang von Sicherungsfehlern und Warnungen:** Führen Sie im Abfragefenster die folgenden Transact-SQL-Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="69713-146">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email1;email2>'  
  
        ```  
  
         <span data-ttu-id="69713-147">Weitere Informationen und ein vollständiges Beispielskript finden [Sie unter Überwachen SQL Server verwaltete Sicherung in Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="69713-147">For more information, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
8.  <span data-ttu-id="69713-148">**Anzeigen von Sicherungsdateien im Microsoft Azure-Speicherkonto:** Stellen Sie in SQL Server Management Studio oder über das Azure-Verwaltungsportal eine Verbindung mit dem Speicherkonto her.</span><span class="sxs-lookup"><span data-stu-id="69713-148">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="69713-149">Es wird ein Container für die Instanz von SQL Server angezeigt, die die Datenbank hostet, die Sie für die Verwendung von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="69713-149">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="69713-150">Innerhalb der ersten 15 Minuten nach dem Aktivieren von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] für die Datenbank können außerdem eine Datenbank- und eine Protokollsicherung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69713-150">You may also see a database and a log backup within 15 minutes of enabling [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the database.</span></span>  
  
9. <span data-ttu-id="69713-151">**Überwachen des Integritätsstatus:**  Sie können die zuvor konfigurierten E-Mail-Benachrichtigungen verwenden oder die protokollierten Ereignisse manuell überwachen.</span><span class="sxs-lookup"><span data-stu-id="69713-151">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="69713-152">Die folgenden Beispiele zeigen einige Transact-SQL-Anweisungen, mit denen die Ereignisse angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="69713-152">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
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
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="69713-153">Die in diesem Abschnitt beschriebenen Schritte sind speziell für die erste Konfiguration von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] für die Datenbank vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="69713-153">The steps described in this section are specifically for configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the first time on the database.</span></span> <span data-ttu-id="69713-154">Sie können die vorhandenen Konfigurationen mithilfe derselben gespeicherten System Prozedur smart_admin ändern **. sp_set_db_backup** und die neuen Werte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="69713-154">You can modify the existing configurations using the same system stored procedure **smart_admin.sp_set_db_backup** and provide the new values.</span></span> <span data-ttu-id="69713-155">Weitere Informationen finden Sie unter [SQL Server Managed Backup to Microsoft Azure Beibehaltungs-und Speichereinstellungen](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span><span class="sxs-lookup"><span data-stu-id="69713-155">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span></span>  
  
### <a name="enable-ss_smartbackup-for-the-instance-with-default-settings"></a><span data-ttu-id="69713-156">Aktivieren von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] mit Standardeinstellungen für die Instanz</span><span class="sxs-lookup"><span data-stu-id="69713-156">Enable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the Instance with Default Settings</span></span>  
 <span data-ttu-id="69713-157">In diesem Tutorial werden die Schritte zum Aktivieren und konfigurieren [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] von für die Instanz "MyInstance" beschrieben \\ .</span><span class="sxs-lookup"><span data-stu-id="69713-157">This tutorial describes the steps to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the instance, 'MyInstance',\\.</span></span> <span data-ttu-id="69713-158">Es umfasst Schritte, um das Überwachen des [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]-Integritätsstatus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69713-158">It includes steps to enable monitoring the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="69713-159">**Berechtigungen:**</span><span class="sxs-lookup"><span data-stu-id="69713-159">**Permissions:**</span></span>  
  
-   <span data-ttu-id="69713-160">Erfordert die Mitgliedschaft in **db_backupoperator** Daten Bank Rolle mit **ALTER ANY CREDENTIAL** -Berechtigungen und `EXECUTE` Berechtigungen für **sp_delete_backuphistory**gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="69713-160">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="69713-161">Erfordert **Select** -Berechtigungen für die **smart_admin. fn_get_current_xevent_settings**-Funktion.</span><span class="sxs-lookup"><span data-stu-id="69713-161">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="69713-162">Erfordert `EXECUTE` Berechtigungen für die gespeicherte Prozedur **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="69713-162">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="69713-163">Außerdem sind `VIEW SERVER STATE`-Berechtigungen erforderlich, da andere Systemobjekte, die diese Berechtigung erfordern, intern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="69713-163">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  


1.  <span data-ttu-id="69713-164">**Erstellen Sie ein Microsoft Azure Speicherkonto:** Die Sicherungen werden im Microsoft Azure Speicher Dienstanbieter gespeichert.</span><span class="sxs-lookup"><span data-stu-id="69713-164">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="69713-165">Sie müssen zunächst ein Microsoft Azure Speicherkonto erstellen, wenn Sie noch nicht über ein Konto verfügen.</span><span class="sxs-lookup"><span data-stu-id="69713-165">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="69713-166">In SQL Server 2014 werden seitenblobs verwendet, die sich von Block-und anfügeblobs unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="69713-166">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="69713-167">Daher müssen Sie ein allgemeines Konto erstellen und kein BLOB-Konto.</span><span class="sxs-lookup"><span data-stu-id="69713-167">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="69713-168">Weitere Informationen finden Sie unter [Informationen zu Azure-Speicherkonten](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="69713-168">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="69713-169">Notieren Sie den Speicherkontonamen und die Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="69713-169">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="69713-170">Aus dem Speicherkontonamen und den Zugriffsschlüsseln werden SQL-Anmeldeinformationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="69713-170">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="69713-171">Die SQL-Anmeldeinformationen werden zur Authentifizierung beim Speicherkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="69713-171">The SQL Credential is used to authenticate to the storage account.</span></span>  
  
2.  <span data-ttu-id="69713-172">**Erstellen Sie SQL** -Anmelde Informationen: Erstellen Sie SQL-Anmelde Informationen, indem Sie den Namen des Speicher Kontos als Identität und den Speicherzugriffs Schlüssel als Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="69713-172">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="69713-173">**Sicherstellen, dass der SQL Server-Agent-Dienst ausgeführt wird:** Starten Sie den SQL Server-Agent, wenn er nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69713-173">**Ensure SQL Server Agent service is Started and Running:** Start SQL Server Agent if it is not currently running.</span></span> [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="69713-174">benötigt einen laufenden SQL Server-Agent auf der Instanz, um Sicherungsvorgänge durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="69713-174">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="69713-175">Sie können den Starttyp des SQL Server-Agents auf "Automatisch" festlegen, um zu gewährleisten, dass regelmäßige Sicherungsvorgänge durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="69713-175">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="69713-176">**Bestimmen des Aufbewahrungszeitraums:** Bestimmen Sie die Beibehaltungsdauer für die Sicherungsdateien.</span><span class="sxs-lookup"><span data-stu-id="69713-176">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="69713-177">Die Beibehaltungsdauer wird in Tagen angegeben und kann zwischen 1 und 30 Tagen liegen.</span><span class="sxs-lookup"><span data-stu-id="69713-177">The retention period is specified in days and can range from 1 to 30.</span></span> <span data-ttu-id="69713-178">Sobald [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] auf Instanzebene mit Standardwerten aktiviert wurde, erben die neuen Datenbanken, die anschließend erstellt werden, die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="69713-178">Once [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is enabled at the instance level with the defaults all new databases created thereafter will inherit the settings.</span></span> <span data-ttu-id="69713-179">Es werden nur Datenbanken unterstützt und automatisch konfiguriert, für die eine vollständige oder massenprotokollierte Wiederherstellung festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="69713-179">Only databases that are set to full or bulk-logged recovery models are supported and will be configured automatically.</span></span> <span data-ttu-id="69713-180">Sie können [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] jederzeit für eine bestimmte Datenbank deaktivieren, wenn [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] für diese Datenbank nicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69713-180">You may disable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a specific database at any time if you  do not want [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configured.</span></span> <span data-ttu-id="69713-181">Außerdem können Sie die Konfiguration für eine bestimmte Datenbank ändern, indem Sie [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] auf Datenbankebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="69713-181">You can also change the configuration for a specific database by configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
5.  <span data-ttu-id="69713-182">**Aktivieren und konfigurieren [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** starten Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der Instanz von SQL Server her.</span><span class="sxs-lookup"><span data-stu-id="69713-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance of SQL Server.</span></span> <span data-ttu-id="69713-183">Führen Sie im Abfragefenster folgende Anweisung aus, nachdem Sie die Werte für Datenbankname, SQL-Anmeldeinformationen, Beibehaltungsdauer und Verschlüsselungsoptionen Ihren Anforderungen entsprechend angepasst haben:</span><span class="sxs-lookup"><span data-stu-id="69713-183">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and the encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="69713-184">Weitere Informationen zum Erstellen eines Zertifikats für die Verschlüsselung finden Sie im Schritt **Erstellen eines Sicherungs Zertifikats** unter [Erstellen einer verschlüsselten Sicherung](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="69713-184">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    Go  
       EXEC smart_admin.sp_set_instance_backup  
                     @enable_backup=1  
                    ,@retention_days=30   
                    ,@credential_name='sqlbackuptoURL'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert';  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="69713-185">ist nun für diese Instanz aktiviert.</span><span class="sxs-lookup"><span data-stu-id="69713-185">is now enabled on the instance.</span></span>  
  
6.  <span data-ttu-id="69713-186">Überprüfen Sie die Konfigurationseinstellungen, indem Sie folgende Transact-SQL-Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="69713-186">Verify the configuration settings by running the following Transact-SQL statement:</span></span>  
  
    ```  
    Use msdb;  
    GO  
    SELECT * FROM smart_admin.fn_backup_instance_config ();  
  
    ```  
  
7.  <span data-ttu-id="69713-187">Erstellen Sie eine neue Datenbank für die Instanz.</span><span class="sxs-lookup"><span data-stu-id="69713-187">Create a new database on the instance.</span></span> <span data-ttu-id="69713-188">Führen Sie die folgende Transact-SQL-Anweisung aus, um die Konfigurationseinstellungen von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] für die Datenbank anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="69713-188">Run the following Transact-SQL statement to view the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configuration settings for the database:</span></span>  
  
    ```  
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('NewDB')  
    ```  
  
     <span data-ttu-id="69713-189">Es kann bis zu 15 Minuten dauern, bis die Einstellungen angezeigt und die Sicherungsvorgänge für die Datenbank gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="69713-189">It may take up to 15 minutes for the settings to show and backup operations on the database to start to run.</span></span>  
  
8.  <span data-ttu-id="69713-190">**Aktivieren und Konfigurieren der Benachrichtigung für den Integritätsstatus:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] verfügt über eine gespeicherte Prozedur, die einen Agent-Auftrag erstellt, um E-Mail-Benachrichtigungen mit Fehlern oder Warnungen zu senden, die möglicherweise ein Eingreifen erfordern.</span><span class="sxs-lookup"><span data-stu-id="69713-190">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span>  <span data-ttu-id="69713-191">Wenn Sie diese E-Mail-Benachrichtigungen erhalten möchten, müssen Sie das Ausführen der gespeicherten Prozedur aktivieren, durch die ein SQL Server-Agentauftrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="69713-191">To receive such notifications, you must enable run the stored procedure which creates a SQL Server Agent Job.</span></span> <span data-ttu-id="69713-192">In den folgenden Schritten wird der Prozess zum Aktivieren und Konfigurieren der E-Mail-Benachrichtigungen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="69713-192">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="69713-193">Richten Sie Datenbank-E-Mail ein, falls diese Funktion auf der Instanz noch nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="69713-193">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="69713-194">Weitere Informationen finden Sie unter [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="69713-194">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="69713-195">Konfigurieren Sie SQL Server-Agent-Benachrichtigungen für die Verwendung von Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="69713-195">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="69713-196">Weitere Informationen finden Sie unter [Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="69713-196">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="69713-197">**Aktivieren der E-mail-Benachrichtigungen für den Empfang von Sicherungsfehlern und Warnungen:** Führen Sie im Abfragefenster die folgenden Transact-SQL-Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="69713-197">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email address>'  
  
        ```  
  
         <span data-ttu-id="69713-198">Weitere Informationen zum Überwachen und ein vollständiges Beispielskript finden [Sie unter Überwachen SQL Server verwalteten Sicherung in Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="69713-198">For more information about how to monitor, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
9. <span data-ttu-id="69713-199">**Anzeigen von Sicherungsdateien im Microsoft Azure-Speicherkonto:** Stellen Sie in SQL Server Management Studio oder über das Azure-Verwaltungsportal eine Verbindung mit dem Speicherkonto her.</span><span class="sxs-lookup"><span data-stu-id="69713-199">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="69713-200">Es wird ein Container für die Instanz von SQL Server angezeigt, die die Datenbank hostet, die Sie für die Verwendung von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="69713-200">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="69713-201">Innerhalb der ersten 15 Minuten nach dem Erstellen einer neuen Datenbank sollten außerdem eine Datenbank- und eine Protokollsicherung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69713-201">You may also see a database and a log backup within 15 minutes of creating a new database.</span></span>  
  
10. <span data-ttu-id="69713-202">**Überwachen des Integritätsstatus:**  Sie können die zuvor konfigurierten E-Mail-Benachrichtigungen verwenden oder die protokollierten Ereignisse manuell überwachen.</span><span class="sxs-lookup"><span data-stu-id="69713-202">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="69713-203">Die folgenden Beispiele zeigen einige Transact-SQL-Anweisungen, mit denen die Ereignisse angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="69713-203">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
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
  
    ```  
    --  to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="69713-204">Die Standardeinstellungen von [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] können für eine bestimmte Datenbank überschrieben werden, indem die Einstellungen auf Datenbankebene konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="69713-204">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] default settings can be overridden for a specific database by configuring the settings specifically at the database level.</span></span> <span data-ttu-id="69713-205">Außerdem können Sie den "[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]"-Dienst zeitweise anhalten und wieder fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="69713-205">You can also pause and resume [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] service temporarily.</span></span> <span data-ttu-id="69713-206">Weitere Informationen finden Sie unter [SQL Server Managed Backup to Microsoft Azure Beibehaltungs-und Speichereinstellungen](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="69713-206">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span></span>  
  
  
