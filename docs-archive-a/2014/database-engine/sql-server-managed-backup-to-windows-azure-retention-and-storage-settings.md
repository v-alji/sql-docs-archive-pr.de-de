---
title: SQL Server verwaltete Sicherung in Azure-Beibehaltungs-und Speichereinstellungen | Microsoft-Dokumentation
description: In diesem Thema wird beschrieben, wie SQL Server verwaltete Sicherung konfiguriert wird, um für eine-Datenbank zu Microsoft Azure und die Standardeinstellungen für die-Instanz zu konfigurieren.
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: c4aa26ea-5465-40cc-8b83-f50603cb9db1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8ebdb81f8aa9edb9cd9326bcb1d286d5d3fe632c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721725"
---
# <a name="sql-server-managed-backup-to-azure---retention-and-storage-settings"></a><span data-ttu-id="9bbb1-103">Verwaltete SQL Server-Sicherung in Azure: Beibehaltungs- und Speichereinstellungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-103">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>
  <span data-ttu-id="9bbb1-104">In diesem Thema werden die grundlegenden Schritte zum Konfigurieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine Datenbank sowie zum Konfigurieren der Standardeinstellungen für die Instanz beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-104">This topic describes the basic steps to configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database and to configure default settings for the instance.</span></span> <span data-ttu-id="9bbb1-105">Außerdem werden in diesem Thema die zum Anhalten und Fortsetzen der [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Dienste für die Instanz erforderlichen Schritte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-105">The topic also describes the steps necessary to pause and resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for the instance.</span></span>  
  
 <span data-ttu-id="9bbb1-106">Eine umfassende Exemplarische Vorgehensweise zum Einrichten von finden Sie unter [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] [Einrichten von SQL Server Managed Backup in Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) und [Einrichten von SQL Server verwalteten Sicherung in Azure für Verfügbarkeits Gruppen](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-106">For a complete walkthrough of setting up [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] see [Setting up SQL Server Managed Backup to Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9bbb1-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9bbb1-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-108">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9bbb1-109">Aktivieren Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] nicht für Datenbanken, die derzeit Wartungspläne oder Protokollversand verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-109">Do not enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on databases that are currently using maintenance plans or log shipping.</span></span> <span data-ttu-id="9bbb1-110">Weitere Informationen zur Interoperabilität und Koexistenz mit anderen SQL Server Features finden Sie unter [SQL Server Managed Backup to Azure: Interoperabilität und Koexistenz](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span><span class="sxs-lookup"><span data-stu-id="9bbb1-110">For more information on interoperability and coexistence with other SQL Server features, see [SQL Server Managed Backup to Azure: Interoperability and Coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9bbb1-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="9bbb1-112">Der SQL Server-Agent muss ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-112">SQL Server Agent should be running.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="9bbb1-113">Wenn der SQL Server-Agent einige Zeit nicht ausgeführt und danach neu gestartet wird, können abhängig von der Zeitspanne zwischen der Beendigung und dem Start des SQL-Agents verstärkt Sicherungsaktivitäten auftreten und ein Rückstand von Protokollsicherungen entstehen, die auf die Ausführung warten.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-113">If SQL Server Agent is stopped for a period of time and then restarted, you may see an increased backup activity depending on the length of time elapsed between the stop and start of SQL Agent, and there might be a backlog of log backups waiting to run.</span></span> <span data-ttu-id="9bbb1-114">Es könnte ratsam sein, den SQL Server-Agent für den automatischen Start beim Systemstart zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-114">Consider configuring SQL Server Agent to start automatically on start up.</span></span>  
  
-   <span data-ttu-id="9bbb1-115">Ein Azure-Speicherkonto und SQL-Anmelde Informationen, in denen die Authentifizierungsinformationen für das Speicherkonto gespeichert werden, sollten vor dem Konfigurieren von erstellt werden [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-115">A Azure storage account and a SQL Credential that stores the authentication information to the storage account should both be created before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="9bbb1-116">Ausführliche Informationen finden Sie im Thema [SQL Server-URL-Sicherung](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) im Abschnitt **Introduction to Key Components and Concepts** und in [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-116">For more information see [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) section of the **SQL Server Backup to URL** topic, and [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbb1-117">erstellt die notwendigen Container zum Speichern der Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-117">creates the necessary containers to store the backups.</span></span> <span data-ttu-id="9bbb1-118">Der Container Name wird im Format "Computername-Instanzname" erstellt.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-118">The container name is created using 'machine name-instance name' format.</span></span> <span data-ttu-id="9bbb1-119">Bei AlwaysOn-Verfügbarkeitsgruppen wird der Container unter Verwendung der GUID der Verfügbarkeitsgruppe benannt.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-119">For AlwaysOn Availability Groups the container is named using the GUID of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9bbb1-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9bbb1-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9bbb1-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-121">Permissions</span></span>  
 <span data-ttu-id="9bbb1-122">Zum Ausführen der gespeicherten Prozeduren, die aktivieren [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , müssen Sie entweder ein `System Administrator` -oder-Mitglied in der **db_backupoperator** -Daten Bank Rolle mit **ALTER ANY CREDENTIAL** -Berechtigungen und- `EXECUTE` Berechtigungen für die **sp_delete_backuphistory**und `smart_admin.sp_backup_master_switch` gespeicherte Prozeduren sein.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-122">To run the stored procedures that enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], you must be a  either a `System Administrator` or  member  in the **db_backupoperator** database role with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on the **sp_delete_backuphistory**, and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  <span data-ttu-id="9bbb1-123">Gespeicherte Prozeduren und Funktionen zur Überprüfung der vorhandenen Einstellungen erfordern in der Regel `Execute`-Berechtigungen für die gespeicherte Prozedur bzw. `Select`-Berechtigungen für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-123">Stored procedures and functions used to review the existing settings typically require `Execute` permissions on the stored procedure and `Select` on the function respectively.</span></span>  
  

  
###  <a name="considerations-for-enabling-ss_smartbackup-for-databases-and-instances"></a><a name="Considerations"></a><span data-ttu-id="9bbb1-124">Überlegungen zum Aktivieren [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] von für Datenbanken und Instanzen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-124">Considerations for enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for Databases and Instances</span></span>  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbb1-125">kann separat für einzelne Datenbanken oder für die gesamte Instanz aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-125">can be enabled for individual databases separately or for the entire instance.</span></span> <span data-ttu-id="9bbb1-126">Die Auswahl hängt von den Anforderungen für die Wiederherstellbarkeit der Datenbanken auf der Instanz, den Anforderungen für die Verwaltung mehrerer Datenbanken und Instanzen und der strategischen Verwendung von Azure Storage ab.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-126">The choices depend on the recoverability requirements for the databases on the instance, requirements for managing multiple databases and instances, and using Azure storage strategically.</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-database-level"></a><span data-ttu-id="9bbb1-127">Aktivieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="9bbb1-127">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Database Level</span></span>  
 <span data-ttu-id="9bbb1-128">Wenn für eine Datenbank bestimmte Anforderungen an den Sicherungszeitraum und die Beibehaltungsdauer (Wiederherstellbarkeits-SLA) bestehen, die sich von denjenigen für andere Datenbanken in der Instanz unterscheiden, konfigurieren Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für diese Datenbank auf Datenbankebene.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-128">If a database has specific requirements for backup and retention period (recoverability SLA) that is different from other databases on the instance, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level for this database.</span></span> <span data-ttu-id="9bbb1-129">Datenbankebeneneinstellungen überschreiben Konfigurationseinstellungen der Instanzebenen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-129">Database level settings override instance level configuration settings.</span></span> <span data-ttu-id="9bbb1-130">Es können jedoch beide Optionen auf derselben Instanz zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-130">However both these options can be used together on the same instance.</span></span> <span data-ttu-id="9bbb1-131">Im Folgenden finden Sie eine Liste der Vorteile und Überlegungen beim Aktivieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] auf Datenbankebene.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-131">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
-   <span data-ttu-id="9bbb1-132">Präziser: Separate Konfigurationseinstellungen für jede Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-132">More granular: Separate configuration settings for each database.</span></span> <span data-ttu-id="9bbb1-133">Unterstützung verschiedener Beibehaltungsdauern für einzelne Datenbanken sind möglich.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-133">Can support different retention periods for individual databases.</span></span>  
  
-   <span data-ttu-id="9bbb1-134">Überschreibt Instanzebeneneinstellungen für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-134">Overrides instance level settings for the database.</span></span>  
  
-   <span data-ttu-id="9bbb1-135">Kann verwendet werden, um die Speicherkosten zu verringern, indem einzelne zu sichernde Datenbanken ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-135">Can be used to reduce storage costs by selecting individual databases to be backed up.</span></span>  
  
-   <span data-ttu-id="9bbb1-136">Erfordert die Verwaltung jeder Datenbank</span><span class="sxs-lookup"><span data-stu-id="9bbb1-136">Requires managing each database</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-instance-level-with-default-settings"></a><span data-ttu-id="9bbb1-137">Aktivieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] auf Instanzebene mit Standardeinstellungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-137">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level with Default Settings</span></span>  
 <span data-ttu-id="9bbb1-138">Verwenden Sie diese Einstellung, wenn die meisten Datenbanken in der Instanz die gleichen Anforderungen an die Sicherungs- und Beibehaltungsrichtlinie besitzen oder wenn neue Datenbankinstanzen bei der Erstellung automatisch gesichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-138">Use this setting if most of the databases in the instance have the same requirements for backup and retention policies, or if you want new database instances to automatically be backed up on creation.</span></span> <span data-ttu-id="9bbb1-139">Einige Datenbanken, die eine Ausnahme von der Richtlinie darstellen, können dennoch einzeln konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-139">A few databases that are exception to the policy can still be configured individually.</span></span> <span data-ttu-id="9bbb1-140">Im Folgenden sind Vorteile und Überlegungen aufgelistet, die sich auf die Aktivierung von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] auf Instanzebene beziehen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-140">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the instance level.</span></span>  
  
-   <span data-ttu-id="9bbb1-141">Automatisierung auf Instanzebene: Anschließend werden gemeinsame Einstellungen automatisch auf neue Datenbanken angewendet.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-141">Automation at the instance level: Common settings applied to automatically for new databases added thereafter.</span></span>  
  
-   <span data-ttu-id="9bbb1-142">Neue Datenbanken werden kurz nach ihrer Erstellung auf den Instanzen automatisch gesichert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-142">New databases will be automatically backed up soon after they are created on the instances</span></span>  
  
-   <span data-ttu-id="9bbb1-143">Eine Anwendung auf Datenbanken mit den gleichen Anforderungen an die Beibehaltungsdauer ist möglich.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-143">Can be applied to databases that have the same retention period requirements.</span></span>  
  
-   <span data-ttu-id="9bbb1-144">Sie können trotzdem einzelne Datenbanken konfigurieren, für die eine andere Beibehaltungsdauer erforderlich ist, selbst wenn die [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Sicherung auf Instanzebene mit Standardeinstellungen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-144">You can still configure individual databases that require a different retention period even with [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] backup enabled at in instance level with default settings.</span></span> <span data-ttu-id="9bbb1-145">Sie können [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für Datenbanken auch deaktivieren, wenn Sie nicht beabsichtigen, den Azure-Speicher für die Sicherungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-145">You can also disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for databases if you do not intend to use Azure storage for the backups.</span></span>  
  
##  <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><a name="DatabaseConfigure"></a><span data-ttu-id="9bbb1-146">Aktivieren und konfigurieren [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] von für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="9bbb1-146">Enable and Configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="9bbb1-147">Die gespeicherte Systemprozedur `smart_admin.sp_set_db_backup` wird verwendet, um [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine bestimmte Datenbank zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-147">The system stored procedure `smart_admin.sp_set_db_backup` is used to enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database.</span></span> <span data-ttu-id="9bbb1-148">Wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] zum ersten Mal in der Datenbank aktiviert wird, müssen zusätzlich zum Aktivieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]die folgenden Informationen angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-148">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time on the database, the following information must be specified in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span></span>  
  
-   <span data-ttu-id="9bbb1-149">Der Name der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-149">The name of the database.</span></span>  
  
-   <span data-ttu-id="9bbb1-150">Die Beibehaltungsdauer.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-150">The retention period.</span></span>  
  
-   <span data-ttu-id="9bbb1-151">SQL-Anmelde Informationen, die für die Authentifizierung beim Azure Storage-Konto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-151">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="9bbb1-152">Geben Sie an, dass die Verschlüsselung nicht mithilfe \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** , oder geben Sie einen unterstützten Verschlüsselungsalgorithmus an.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-152">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="9bbb1-153">Weitere Informationen zur Verschlüsselung finden Sie unter [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-153">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbb1-154">für die Konfiguration auf Datenbankebene wird nur über Transact-SQL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-154">for database level configuration is only supported through Transact-SQL.</span></span>  
  
 <span data-ttu-id="9bbb1-155">Nach der Aktivierung von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine Datenbank werden diese Informationen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-155">Once [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for a database this information is persisted.</span></span> <span data-ttu-id="9bbb1-156">Wenn Sie die Konfiguration ändern, sind nur der Datenbankname und die zu ändernde Einstellung erforderlich. [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] behält in diesem Fall die vorhandenen Werte für andere Parameter bei, sofern sie nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-156">If you are changing the configuration, only the database name and the setting you want to change is required, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values for other parameters when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9bbb1-157">Vor dem Konfigurieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine Datenbank kann es empfehlenswert sein, vorhandene Konfigurationen ggf. zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-157">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on a database it might be useful to existing configuration if any.</span></span> <span data-ttu-id="9bbb1-158">Der Schritt zum Prüfen der Konfigurationseinstellungen für eine Datenbank wird weiter unten in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-158">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
-   <span data-ttu-id="9bbb1-159">**Verwenden von Transact-SQL:**</span><span class="sxs-lookup"><span data-stu-id="9bbb1-159">**Using Transact-SQL:**</span></span>  
  
     <span data-ttu-id="9bbb1-160">Wenn Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] zum ersten Mal aktivieren, sind die erforderlichen Parameter: \* \@ database_name*, \* \@ credential_name* \* \@ encryption_algorithm*, \* \@ enable_backup* der \* \@ storage_url\* Parameter optional ist.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-160">If you are enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the first time, the required parameters are: *\@database_name*, *\@credential_name*, *\@encryption_algorithm*,  *\@enable_backup* The *\@storage_url* parameter is optional.</span></span> <span data-ttu-id="9bbb1-161">Wenn Sie keinen Wert für den @storage_url Parameter angeben, wird der Wert anhand der Speicherkonto Informationen aus den SQL-Anmelde Informationen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-161">If you do not provide a value for  the @storage_url parameter, the value is derived using the storage account information from the SQL Credential.</span></span> <span data-ttu-id="9bbb1-162">Wenn Sie die Speicher-URL bereitstellen, geben Sie nur die URL für den Stamm des Speicherkontos an; diese muss mit den Informationen in den SQL-Anmeldeinformationen übereinstimmen, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-162">If you provide the storage URL you should only provide the URL for the root of the storage account, and must match the information in the SQL Credential you specified.</span></span>  
  
    1.  <span data-ttu-id="9bbb1-163">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-163">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
    2.  <span data-ttu-id="9bbb1-164">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-164">From the Standard bar, click **New Query**.</span></span>  
  
    3.  <span data-ttu-id="9bbb1-165">Fügen Sie das folgende Beispiel in das Abfragefenster ein, und klicken Sie auf `Execute` .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-165">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="9bbb1-166">In diesem Beispiel wird [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für die Datenbank "TestDB" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-166">This example enables [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the database 'TestDB'.</span></span> <span data-ttu-id="9bbb1-167">Die Beibehaltungsdauer wird auf 30 Tage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-167">The retention period is set to 30 days.</span></span> <span data-ttu-id="9bbb1-168">Im Beispiel wird die Verschlüsselungsoption verwendet, bei der der Verschlüsselungsalgorithmus und die Verschlüsselungsinformationen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-168">This sample uses the encryption option by specifying the encryption algorithm and the encryptor information.</span></span>  
  
    ```sql
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@enable_backup=1  
                    ,@retention_days =30   
                    ,@credential_name ='MyCredential'  
                    ,@encryption_algorithm ='AES_256'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
    GO
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9bbb1-169">Die Beibehaltungsdauer kann auf einen beliebigen Wert zwischen 1 und 30 Tage festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-169">The retention period can be set to any value from 1 to 30 days.</span></span>  
    >   
    >  <span data-ttu-id="9bbb1-170">Weitere Informationen zum Erstellen eines Zertifikats für die Verschlüsselung finden Sie im Schritt Erstellen Sie ein Sicherungszertifikat in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-170">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
     <span data-ttu-id="9bbb1-171">Weitere Informationen zu dieser gespeicherten Prozedur finden Sie unter [smart_admin. set_db_backup &#40;Transact-SQL-&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="9bbb1-171">For more information on this stored procedure, see [smart_admin.set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span></span>  
  
     <span data-ttu-id="9bbb1-172">Überprüfen Sie die Konfigurationseinstellungen für eine Datenbank mit der folgenden Abfrage:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-172">To review the configuration settings for a database use the following query:</span></span>  
  
    ```sql
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('TestDB')  
    ```  
  
##  <a name="enable-and-configure-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceConfigure"></a><span data-ttu-id="9bbb1-173">Aktivieren und konfigurieren [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] der Standardeinstellungen für die Instanz</span><span class="sxs-lookup"><span data-stu-id="9bbb1-173">Enable and Configure Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="9bbb1-174">Sie können die Standard [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Einstellungen auf Instanzebene auf zweierlei Weise aktivieren und konfigurieren: mithilfe der gespeicherten System Prozedur `smart_admin.set_instance_backup` oder **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-174">You can enable and configure default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings at the instance level in two ways:  By using the system stored procedure `smart_admin.set_instance_backup` or **SQL Server Management Studio**.</span></span> <span data-ttu-id="9bbb1-175">Die beiden Methoden werden nachfolgend erläutert:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-175">The two methods are explained below:</span></span>  
  
 <span data-ttu-id="9bbb1-176">**smart_admin. set_instance_backup:**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-176">**smart_admin.set_instance_backup:**.</span></span> <span data-ttu-id="9bbb1-177">Wenn Sie den Wert **1** für \* \@ enable_backup\* Parameter angeben, können Sie die Sicherung aktivieren und die Standardkonfigurationen festlegen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-177">By specifying the value **1** for *\@enable_backup* parameter, you can enable backup and set the default configurations.</span></span> <span data-ttu-id="9bbb1-178">Nachdem diese auf Instanzebene angewendet wurden, werden diese Standardeinstellungen auf alle neuen Datenbanken angewendet, die dieser Instanz hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-178">Once applied at the instance level, these default settings are applied to any new database that is added to this instance.</span></span>  <span data-ttu-id="9bbb1-179">Wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] zum ersten Mal aktiviert wird, müssen zusätzlich zum Aktivieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für die Instanz die folgenden Informationen angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-179">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time, the following information must be provided in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on the instance:</span></span>  
  
-   <span data-ttu-id="9bbb1-180">Die Beibehaltungsdauer.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-180">The retention period.</span></span>  
  
-   <span data-ttu-id="9bbb1-181">SQL-Anmelde Informationen, die für die Authentifizierung beim Azure Storage-Konto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-181">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="9bbb1-182">Die Verschlüsselungsoption.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-182">The encryption option.</span></span> <span data-ttu-id="9bbb1-183">Geben Sie an, dass die Verschlüsselung nicht mithilfe \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** , oder geben Sie einen unterstützten Verschlüsselungsalgorithmus an.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-183">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="9bbb1-184">Weitere Informationen zur Verschlüsselung finden Sie unter [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-184">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="9bbb1-185">Nach der Aktivierung werden diese Einstellungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-185">Once enabled these settings are persisted.</span></span> <span data-ttu-id="9bbb1-186">Wenn Sie die Konfiguration ändern, sind nur der Datenbankname und der Einstellung, die Sie ändern möchten, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-186">If you are changing the configuration, only the database name and the setting you want to change is required.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbb1-187">behält die vorhandenen Werte bei, wenn nichts angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-187">retains the existing values when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9bbb1-188">Vor dem Konfigurieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine Instanz kann es empfehlenswert sein, vorhandene Konfigurationen ggf. zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-188">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on an instance, it might be useful to check for existing configuration, if any.</span></span> <span data-ttu-id="9bbb1-189">Der Schritt zum Prüfen der Konfigurationseinstellungen für eine Datenbank wird weiter unten in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-189">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
 <span data-ttu-id="9bbb1-190">**SQL Server Management Studio:** Um diese Aufgabe in SQL Server Management Studio auszuführen, erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** und klicken mit der rechten Maustaste auf **Managed Backup**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-190">**SQL Server Management Studio:** To do this task in SQL Server Management Studio, go the object explorer, expand the **Management** node, and right click on **Managed Backup**.</span></span> <span data-ttu-id="9bbb1-191">Wählen Sie **Konfigurieren**aus.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-191">Select **Configure**.</span></span> <span data-ttu-id="9bbb1-192">Das Dialogfeld **Managed Backup** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-192">This opens the **Managed Backup** dialog.</span></span> <span data-ttu-id="9bbb1-193">Verwenden Sie dieses Dialogfeld, um die Beibehaltungsdauer, SQL-Anmeldeinformationen, die Speicher-URL und Verschlüsselungseinstellungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-193">Use this dialog to specify the retention period, SQL Credential, Storage URL, and the encryption settings.</span></span> <span data-ttu-id="9bbb1-194">Spezifische Hilfe zu diesem Dialogfeld finden Sie unter [configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-194">For specific help with this dialog, see [Configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span></span>  
  
#### <a name="using-transact-sql"></a><span data-ttu-id="9bbb1-195">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9bbb1-195">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="9bbb1-196">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-196">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9bbb1-197">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-197">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9bbb1-198">Fügen Sie das folgende Beispiel in das Abfragefenster ein, und klicken Sie auf `Execute` .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-198">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
   EXEC smart_admin.sp_set_instance_backup  
                @retention_days=30   
                ,@credential_name='sqlbackuptoURL'  
                ,@encryption_algorithm ='AES_128'  
                ,@encryptor_type= 'Certificate'  
                ,@encryptor_name='MyBackupCert'  
                ,@enable_backup=1;  
GO  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9bbb1-199">Die Beibehaltungsdauer kann auf einen beliebigen Wert zwischen 1 und 30 Tage festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-199">The retention period can be set to any value from 1 to 30 days.</span></span>  
>   
>  <span data-ttu-id="9bbb1-200">Weitere Informationen zum Erstellen eines Zertifikats für die Verschlüsselung finden Sie im Schritt Erstellen Sie ein Sicherungszertifikat in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="9bbb1-200">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
 <span data-ttu-id="9bbb1-201">Zeigen Sie die Standardkonfigurationseinstellungen für die Instanz mit der folgenden Abfrage an:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-201">To view the default configuration settings for the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_instance_config ();
```  
  
#### <a name="using-powershell"></a><span data-ttu-id="9bbb1-202">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bbb1-202">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9bbb1-203">Starten Sie eine PowerShell-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-203">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="9bbb1-204">Führen Sie das folgende Skript aus, nachdem Sie es an Ihre Einstellungen angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-204">Run the following script after modifying it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    $encryptionOption = New-SqlBackupEncryptionOption -EncryptionAlgorithm Aes128 -EncryptorType ServerCertificate -EncryptorName "MyBackupCert"  
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -BackupEnabled $True -BackupRetentionPeriodInDays 10 -EncryptionOption $encryptionOption  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9bbb1-205">Wenn Sie nach dem Konfigurieren der Standardeinstellungen eine neue Datenbank erstellen, kann es bis zu 15 Minuten dauern, bis die Datenbank mit den Standardeinstellungen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-205">When you create a new database after configuring the default settings, it may take up to 15 minutes for the database to be configured with the default settings.</span></span> <span data-ttu-id="9bbb1-206">Dies gilt auch für Datenbanken, die von **Simple** auf das Wiederherstellungsmodell **Full** oder **Bulk-Logged** geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-206">This also applies to databases that are changed from **Simple** to **Full** or **Bulk-Logged** recovery model.</span></span>  
  
##  <a name="disable-ss_smartbackup-for-a-database"></a><a name="DatabaseDisable"></a> <span data-ttu-id="9bbb1-207">Deaktivieren von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="9bbb1-207">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database</span></span>  
 <span data-ttu-id="9bbb1-208">Sie können [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Einstellungen mithilfe der `sp_set_db_backup` gespeicherten System Prozedur deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-208">You can disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings by using the `sp_set_db_backup` system stored procedure.</span></span> <span data-ttu-id="9bbb1-209">Der \* \@ enableparameter\* wird zum Aktivieren und deaktivieren [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] von Konfigurationen für eine bestimmte Datenbank verwendet, wobei "1" aktiviert und "0" die Konfigurationseinstellungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-209">The *\@enableparameter* is used to enable and disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations for a specific database, where 1 enables and 0 disables the configuration settings.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-for-a-specific-database"></a><span data-ttu-id="9bbb1-210">So deaktivieren Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für eine bestimmte Datenbank</span><span class="sxs-lookup"><span data-stu-id="9bbb1-210">To Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database:</span></span>  
  
1.  <span data-ttu-id="9bbb1-211">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-211">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9bbb1-212">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-212">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9bbb1-213">Fügen Sie das folgende Beispiel in das Abfragefenster ein, und klicken Sie auf `Execute` .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-213">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin.sp_set_db_backup   
                @database_name='TestDB'   
                ,@enable_backup=0;  
GO
```  
  
##  <a name="disable-ss_smartbackup-for-all-the-databases-on-the-instance"></a><a name="DatabaseAllDisable"></a> <span data-ttu-id="9bbb1-214">Deaktivieren Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] für alle Datenbanken in der Instanz.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-214">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for all the databases on the Instance</span></span>  
 <span data-ttu-id="9bbb1-215">Mit dem folgenden Verfahren können Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Konfigurationseinstellungen für alle Datenbanken deaktivieren, für die [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] momentan für die Instanz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-215">The following procedure is for when you want to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuration settings from all the databases that currently have [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled on the instance.</span></span>  <span data-ttu-id="9bbb1-216">Die Konfigurationseinstellungen wie Speicher-URL, Beibehaltung und SQL-Anmeldeinformationen verbleiben in den Metadaten und können verwendet werden, wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] zu einem späteren Zeitpunkt für die Datenbank aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-216">The configuration settings like the storage URL, retention, and the SQL Credential will remain in the metadata and can be used  if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the database at a later time.</span></span> <span data-ttu-id="9bbb1-217">Wenn Sie die [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Dienste vorübergehend anhalten möchten, können Sie den in den folgenden Abschnitten weiter unten in diesem Thema erläuterten Hauptschalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-217">If you want to just pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services temporarily, you can use the master switch explained in the following sections later in this topic.</span></span>  
  
#### <a name="to-disable-ss_smartbackupfor-all-the-databases"></a><span data-ttu-id="9bbb1-218">So deaktivieren Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]für alle Datenbanken</span><span class="sxs-lookup"><span data-stu-id="9bbb1-218">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]for all the databases:</span></span>  
  
1.  <span data-ttu-id="9bbb1-219">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-219">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9bbb1-220">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-220">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9bbb1-221">Fügen Sie das folgende Beispiel in das Abfragefenster ein, und klicken Sie auf `Execute` .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-221">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="9bbb1-222">Im folgenden Beispiel wird ermittelt, ob [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] auf Instanzebene konfiguriert ist und für welche Datenbanken in der Instanz [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] aktiviert ist, und die gespeicherte Systemprozedur `sp_set_db_backup` wird ausgeführt, um [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-222">The following example identifies if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured at the instance level and all the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled databases on the instance, and executes the system stored procedure `sp_set_db_backup` to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span>  
  
```sql
-- Create a working table to store the database names  
Declare @DBNames TABLE  
  
       (  
             RowID int IDENTITY PRIMARY KEY  
             ,DBName varchar(500)  
  
       )  
-- Define the variables  
DECLARE @rowid int  
DECLARE @dbname varchar(500)  
DECLARE @SQL varchar(2000)  
-- Get the database names from the system function  
  
INSERT INTO @DBNames (DBName)  
  
SELECT db_name  
       FROM
  
       smart_admin.fn_backup_db_config (NULL)  
       WHERE is_smart_backup_enabled = 1  
  
       --Select DBName from @DBNames 
       select @rowid = min(RowID) FROM @DBNames  
  
       WHILE @rowID IS NOT NULL  
       Begin
             Set @dbname = (Select DBName From @DBNames Where RowID = @rowid)  
             Begin  
             Set @SQL = 'EXEC smart_admin.sp_set_db_backup    
                @database_name= '''+'' + @dbname+ ''+''',   
                @enable_backup=0'  
  
            EXECUTE (@SQL)  
  
             END  
             Select @rowid = min(RowID)  
             From @DBNames Where RowID > @rowid  
  
       END
```  
  
 <span data-ttu-id="9bbb1-223">Prüfen Sie die Konfigurationseinstellungen für alle Datenbanken auf der Instanz mit der folgenden Abfrage:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-223">To review the configuration settings for all the databases on the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_db_config (NULL);  
GO
```  
  
##  <a name="disable-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceDisable"></a> <span data-ttu-id="9bbb1-224">Deaktivieren der [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Standardeinstellungen für die Instanz</span><span class="sxs-lookup"><span data-stu-id="9bbb1-224">Disable Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="9bbb1-225">Standardeinstellungen auf Instanzebene gelten für alle neuen Datenbanken, die auf dieser Instanz erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-225">Default settings at the instance level apply to all new databases created on that instance.</span></span>  <span data-ttu-id="9bbb1-226">Wenn Sie die Standardeinstellungen nicht mehr benötigen, können Sie diese Konfiguration mit der gespeicherten Systemprozedur **smart_admin.sp_set_instance_backup** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-226">If you no longer need or require default settings, you can disable this configuration by using the **smart_admin.sp_set_instance_backup** System stored procedure.</span></span> <span data-ttu-id="9bbb1-227">Durch die Deaktivierung werden die anderen Konfigurationseinstellungen wie Speicher-URL, Beibehaltungseinstellung oder der Name der SQL-Anmeldeinformationen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-227">Disabling does not remove the other configuration settings like the storage URL, retention setting, or the SQL Credential name.</span></span> <span data-ttu-id="9bbb1-228">Diese Einstellungen werden verwendet, wenn [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] zu einem späteren Zeitpunkt für die Instanz aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-228">These settings will be used if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the instance at a later time.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-default-configuration-settings"></a><span data-ttu-id="9bbb1-229">So deaktivieren Sie die [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Standardkonfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9bbb1-229">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] default configuration settings:</span></span>  
  
1.  <span data-ttu-id="9bbb1-230">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-230">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9bbb1-231">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-231">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9bbb1-232">Fügen Sie das folgende Beispiel in das Abfragefenster ein, und klicken Sie auf `Execute` .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-232">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
    ```sql
    Use msdb;  
    Go  
    EXEC smart_admin.sp_set_instance_backup  
                    @enable_backup=0;  
    GO
    ```  
  
#### <a name="using-powershell"></a><span data-ttu-id="9bbb1-233">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bbb1-233">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9bbb1-234">Starten Sie eine PowerShell-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-234">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="9bbb1-235">Führen Sie folgendes Skript aus:</span><span class="sxs-lookup"><span data-stu-id="9bbb1-235">Run the following script:</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Set-SqlSmartAdmin -BackupEnabled $False  
    ```  
  
##  <a name="pause-ss_smartbackup-at-the-instance-level"></a><a name="InstancePause"></a> <span data-ttu-id="9bbb1-236">Anhalten von [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] auf Instanzebene</span><span class="sxs-lookup"><span data-stu-id="9bbb1-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level</span></span>  
 <span data-ttu-id="9bbb1-237">Zuweilen kann es vorkommen, dass Sie die [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Dienste für kurze Zeit vorübergehend anhalten müssen.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-237">There might be times when you need to temporarily pause the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for a short period time.</span></span>  <span data-ttu-id="9bbb1-238">Mit der gespeicherten `smart_admin.sp_backup_master_switch`-Systemprozedur können Sie den [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]-Dienst auf Instanzebene deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-238">The `smart_admin.sp_backup_master_switch` system stored procedure allows you to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] service at the instance level.</span></span>  <span data-ttu-id="9bbb1-239">Mit der gleichen gespeicherten Prozedur wird [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-239">The same stored procedure is used to resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="9bbb1-240">Mit dem @state-Parameter wird definiert, ob [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] aktiviert oder deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-240">The @state parameter is used to define whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] should be turned off or on.</span></span>  
  
#### <a name="to-pause-ss_smartbackup-services-using-transact-sql"></a><span data-ttu-id="9bbb1-241">So halten Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] -Dienste mit Transact-SQL an</span><span class="sxs-lookup"><span data-stu-id="9bbb1-241">To Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Services Using Transact-SQL:</span></span>  
  
1.  <span data-ttu-id="9bbb1-242">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-242">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9bbb1-243">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-243">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9bbb1-244">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf`Execute`</span><span class="sxs-lookup"><span data-stu-id="9bbb1-244">Copy and paste the following example into the query window and then click `Execute`</span></span>  
  
```sql
Use msdb;  
GO  
EXEC smart_admin.sp_backup_master_switch @new_state=0;  
Go  
  
```  
  
#### <a name="to-pause-ss_smartbackup-using-powershell"></a><span data-ttu-id="9bbb1-245">So halten Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] mit PowerShell an</span><span class="sxs-lookup"><span data-stu-id="9bbb1-245">To pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9bbb1-246">Starten Sie eine PowerShell-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-246">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="9bbb1-247">Führen Sie das folgende Skript aus, nachdem Sie es an Ihre Einstellungen angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-247">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $False  
    ```  
  
#### <a name="to-resume-ss_smartbackup-using-transact-sql"></a><span data-ttu-id="9bbb1-248">So setzen Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] mit Transact-SQL fort</span><span class="sxs-lookup"><span data-stu-id="9bbb1-248">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="9bbb1-249">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-249">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9bbb1-250">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-250">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9bbb1-251">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf `Execute` .</span><span class="sxs-lookup"><span data-stu-id="9bbb1-251">Copy and paste the following example into the query window and then click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin. sp_backup_master_switch @new_state=1;  
GO
```  
  
#### <a name="to-resume-ss_smartbackup-using-powershell"></a><span data-ttu-id="9bbb1-252">So setzen Sie [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] mit PowerShell fort</span><span class="sxs-lookup"><span data-stu-id="9bbb1-252">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9bbb1-253">Starten Sie eine PowerShell-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-253">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="9bbb1-254">Führen Sie das folgende Skript aus, nachdem Sie es an Ihre Einstellungen angepasst haben.</span><span class="sxs-lookup"><span data-stu-id="9bbb1-254">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $True  
    ```  
