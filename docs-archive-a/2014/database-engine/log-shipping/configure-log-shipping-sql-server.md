---
title: Konfigurieren des Protokollversands (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], enabling
- log shipping [SQL Server], configuring
ms.assetid: c42aa04a-4945-4417-b4c7-50589d727e9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269b0ae2980435e507128cc87606f7eb702c2b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697106"
---
# <a name="configure-log-shipping-sql-server"></a><span data-ttu-id="b400a-102">Konfigurieren des Protokollversands (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b400a-102">Configure Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="b400a-103">In diesem Thema wird beschrieben, wie der Protokollversand in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="b400a-103">This topic describes how to configure log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b400a-104">Von [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] und höheren Versionen wird die Sicherungskomprimierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b400a-104">[!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] and later versions support backup compression.</span></span> <span data-ttu-id="b400a-105">Wenn Sie eine Protokollversandkonfiguration erstellen, können Sie das Verhalten der Sicherungskomprimierung von Protokollsicherungen steuern.</span><span class="sxs-lookup"><span data-stu-id="b400a-105">When creating a log shipping configuration, you can control the backup compression behavior of log backups.</span></span> <span data-ttu-id="b400a-106">Weitere Informationen finden Sie unter [Sicherungskomprimierung &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b400a-106">For more information, see [Backup Compression &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="b400a-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b400a-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b400a-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b400a-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b400a-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b400a-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b400a-110">Security</span><span class="sxs-lookup"><span data-stu-id="b400a-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b400a-111">**So konfigurieren Sie den Protokollversand mit:**</span><span class="sxs-lookup"><span data-stu-id="b400a-111">**To configure log shipping, using:**</span></span>  
  
     [<span data-ttu-id="b400a-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b400a-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b400a-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b400a-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="b400a-114">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b400a-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b400a-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b400a-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b400a-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b400a-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="b400a-117">Die primäre Datenbank muss das vollständige oder massenprotokollierte Wiederherstellungsmodell verwenden. Durch Umstellen der Datenbank auf die einfache Wiederherstellung ist der Protokollversand nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="b400a-117">The primary database must use the full or bulk-logged recovery model; switching the database to simple recovery will cause log shipping to stop functioning.</span></span>  
  
-   <span data-ttu-id="b400a-118">Vor der Konfiguration des Protokollversands müssen Sie eine Freigabe erstellen, um die Transaktionsprotokollsicherungen dem sekundären Server zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="b400a-118">Before you configure log shipping, you must create a share to make the transaction log backups available to the secondary server.</span></span> <span data-ttu-id="b400a-119">Es handelt sich dabei um eine Freigabe des Verzeichnisses, in dem die Transaktionsprotokollsicherungen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="b400a-119">This is a share of the directory where the transaction log backups will be generated.</span></span> <span data-ttu-id="b400a-120">Wenn Sie z.B. die Transaktionsprotokolle im Verzeichnis C:\data\tlogs\\sichern, können Sie die Freigabe \\\\*primaryserver*\tlogs dieses Verzeichnisses erstellen.</span><span class="sxs-lookup"><span data-stu-id="b400a-120">For example, if you back up your transaction logs to the directory c:\data\tlogs\\, you could create the \\\\*primaryserver*\tlogs share of that directory.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b400a-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b400a-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b400a-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b400a-122">Permissions</span></span>  
 <span data-ttu-id="b400a-123">Die gespeicherten Prozeduren für den Protokollversand erfordern die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b400a-123">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b400a-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b400a-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="b400a-125">So konfigurieren Sie den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="b400a-125">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="b400a-126">Klicken Sie mit der rechten Maustaste auf die Datenbank, die Sie als primäre Datenbank in der Protokollversandkonfiguration verwenden möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b400a-126">Right click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b400a-127">Klicken Sie unter **Seite auswählen**auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="b400a-127">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="b400a-128">Aktivieren Sie das Kontrollkästchen vor **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="b400a-128">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
4.  <span data-ttu-id="b400a-129">Klicken Sie unter **Transaktionsprotokollsicherungen**auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b400a-129">Under **Transaction log backups**, click **Backup Settings**.</span></span>  
  
5.  <span data-ttu-id="b400a-130">Geben Sie in das Feld **Geben Sie den Netzwerkpfad zum Sicherungsordner an** den Netzwerkpfad für die Freigabe ein, die Sie für den Ordner der Transaktionsprotokollsicherung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b400a-130">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>  
  
6.  <span data-ttu-id="b400a-131">Falls sich der Sicherungsordner auf dem primären Server befindet, geben Sie in das Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** den lokalen Pfad zum Sicherungsordner ein.</span><span class="sxs-lookup"><span data-stu-id="b400a-131">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="b400a-132">(Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="b400a-132">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b400a-133">Falls das Konto für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.</span><span class="sxs-lookup"><span data-stu-id="b400a-133">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>  
  
7.  <span data-ttu-id="b400a-134">Konfigurieren Sie die Parameter **Dateien löschen, die älter sind als** und **Warnen, wenn keine Sicherung erfolgt in** .</span><span class="sxs-lookup"><span data-stu-id="b400a-134">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>  
  
8.  <span data-ttu-id="b400a-135">Beachten Sie den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag**.</span><span class="sxs-lookup"><span data-stu-id="b400a-135">Note the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b400a-136">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan** , und passen Sie den Zeitplan des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="b400a-136">If you want to customize the schedule for your installation, then click **Schedule** and adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span>  
  
9. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="b400a-137">wird die [Sicherungskomprimierung](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b400a-137">supports [backup compression](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span> <span data-ttu-id="b400a-138">Wenn Sie eine Protokollversandkonfiguration erstellen, können Sie das Verhalten der Sicherungskomprimierung von Protokollsicherungen steuern, indem Sie eine der folgenden Optionen auswählen: **Standardservereinstellung verwenden**, **Sicherung komprimieren** oder **Sicherung nicht komprimieren**.</span><span class="sxs-lookup"><span data-stu-id="b400a-138">When creating a log shipping configuration, you can control the backup compression behavior of log backups by choosing one of the following options: **Use the default server setting**, **Compress backup**, or **Do not compress backup**.</span></span> <span data-ttu-id="b400a-139">Weitere Informationen finden Sie unter [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b400a-139">For more information, see [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span></span>  
  
10. <span data-ttu-id="b400a-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b400a-140">Click **OK**.</span></span>  
  
11. <span data-ttu-id="b400a-141">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b400a-141">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
12. <span data-ttu-id="b400a-142">Klicken Sie auf **Verbinden** , und stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, die Sie als sekundären Server verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b400a-142">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
13. <span data-ttu-id="b400a-143">Wählen Sie im Feld **Sekundäre Datenbank** eine Datenbank aus der Liste aus, oder geben Sie den Namen der Datenbank ein, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b400a-143">In the **Secondary Database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
14. <span data-ttu-id="b400a-144">Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option aus, die Sie zum Initialisieren der sekundären Datenbank verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b400a-144">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b400a-145">Wenn Sie veranlassen, dass [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] die sekundäre Datenbank von einer Datenbanksicherung initialisiert, werden die Daten- und Protokolldateien der sekundären Datenbank am gleichen Speicherort abgelegt wie die Daten- und Protokolldateien der **master** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b400a-145">If you choose to have [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialize the secondary database from a database backup, the data and log files of the secondary database are placed in the same location as the data and log files of the **master** database.</span></span> <span data-ttu-id="b400a-146">Dieser Speicherort unterscheidet sich wahrscheinlich vom Speicherort der Daten- und Protokolldateien der primären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b400a-146">This location is likely to be different than the location of the data and log files of the primary database.</span></span>  
  
15. <span data-ttu-id="b400a-147">Geben Sie auf der Registerkarte **Dateien kopieren** im Ordner **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b400a-147">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="b400a-148">Dieser Ordner befindet sich oft auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="b400a-148">This folder is often located on the secondary server.</span></span>  
  
16. <span data-ttu-id="b400a-149">Beachten Sie den Zeitplan für das Kopieren im Feld **Zeitplan** unter **Kopierauftrag**.</span><span class="sxs-lookup"><span data-stu-id="b400a-149">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b400a-150">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan** , und passen Sie den Zeitplan des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="b400a-150">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="b400a-151">Dieser Zeitplan sollte ungefähr mit dem Sicherungszeitplan übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b400a-151">This schedule should approximate the backup schedule.</span></span>  
  
17. <span data-ttu-id="b400a-152">Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen**die Option **Kein Wiederherstellungsmodus** oder **Standbymodus** aus.</span><span class="sxs-lookup"><span data-stu-id="b400a-152">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
18. <span data-ttu-id="b400a-153">Wenn Sie die Option **Standbymodus** auswählen, legen Sie fest, ob die Benutzer von der sekundären Datenbank getrennt werden sollen, während der Wiederherstellungsvorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b400a-153">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
19. <span data-ttu-id="b400a-154">Wenn Sie den Wiederherstellungsprozess auf dem sekundären Server verzögern möchten, wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens**eine Verzögerungszeit aus.</span><span class="sxs-lookup"><span data-stu-id="b400a-154">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
20. <span data-ttu-id="b400a-155">Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in**einen Warnschwellenwert aus.</span><span class="sxs-lookup"><span data-stu-id="b400a-155">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
21. <span data-ttu-id="b400a-156">Beachten Sie den Wiederherstellungszeitplan im Feld **Zeitplan** unter **Wiederherstellungsauftrag**.</span><span class="sxs-lookup"><span data-stu-id="b400a-156">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b400a-157">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan** , und passen Sie den Zeitplan des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="b400a-157">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="b400a-158">Dieser Zeitplan sollte ungefähr mit dem Sicherungszeitplan übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b400a-158">This schedule should approximate the backup schedule.</span></span>  
  
22. <span data-ttu-id="b400a-159">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b400a-159">Click **OK**.</span></span>  
  
23. <span data-ttu-id="b400a-160">Aktivieren Sie unter **Überwachungsserverinstanz**das Kontrollkästchen **Überwachungsserverinstanz verwenden** , und klicken Sie dann auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b400a-160">Under **Monitor server instance**, select the **Use a monitor server instance** check box, and then click **Settings**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b400a-161">Wenn Sie diese Protokollversandkonfiguration überwachen möchten, müssen Sie nun den Überwachungsserver hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b400a-161">To monitor this log shipping configuration, you must add the monitor server now.</span></span> <span data-ttu-id="b400a-162">Zum späteren Hinzufügen des Überwachungsservers müssten Sie diese Protokollversandkonfiguration entfernen und sie dann durch eine neue Konfiguration ersetzen, die einen Überwachungsserver umfasst.</span><span class="sxs-lookup"><span data-stu-id="b400a-162">To add the monitor server later, you would need to remove this log shipping configuration and then replace it with a new configuration that includes a monitor server.</span></span>  
  
24. <span data-ttu-id="b400a-163">Klicken Sie auf **Verbinden** , und stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, die Sie als Überwachungsserver verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b400a-163">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your monitor server.</span></span>  
  
25. <span data-ttu-id="b400a-164">Wählen Sie unter **Überwachungsverbindungen**die Verbindungsmethode aus, die von den Sicherungs-, Kopier- und Wiederherstellungsaufträgen zum Herstellen einer Verbindung mit dem Überwachungsserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b400a-164">Under **Monitor connections**, choose the connection method to be used by the backup, copy, and restore jobs to connect to the monitor server.</span></span>  
  
26. <span data-ttu-id="b400a-165">Wählen Sie unter **Verlaufsbeibehaltung**aus, wie lang ein Datensatz des Protokollversandverlaufs beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="b400a-165">Under **History retention**, choose the length of time you want to retain a record of your log shipping history.</span></span>  
  
27. <span data-ttu-id="b400a-166">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b400a-166">Click **OK**.</span></span>  
  
28. <span data-ttu-id="b400a-167">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK** , um den Konfigurationsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="b400a-167">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b400a-168">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b400a-168">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="b400a-169">So konfigurieren Sie den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="b400a-169">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="b400a-170">Initialisieren Sie die sekundäre Datenbank, indem Sie eine vollständige Sicherung der primären Datenbank auf dem sekundären Server wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b400a-170">Initialize the secondary database by restoring a full backup of the primary database on the secondary server.</span></span>  
  
2.  <span data-ttu-id="b400a-171">Führen Sie auf dem primären Server [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) aus, um eine primäre Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b400a-171">On the primary server, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) to add a primary database.</span></span> <span data-ttu-id="b400a-172">Von der gespeicherten Prozedur wird die Sicherungsauftrags-ID und die primäre ID zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b400a-172">The stored procedure returns the backup job ID and primary ID.</span></span>  
  
3.  <span data-ttu-id="b400a-173">Führen Sie auf dem primären Server [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) aus, um einen Zeitplan für den Sicherungsauftrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b400a-173">On the primary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to add a schedule for the backup job.</span></span>  
  
4.  <span data-ttu-id="b400a-174">Führen Sie auf dem Überwachungsserver [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) aus, um den Warnungsauftrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b400a-174">On the monitor server, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) to add the alert job.</span></span>  
  
5.  <span data-ttu-id="b400a-175">Aktivieren Sie auf dem primären Server den Sicherungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="b400a-175">On the primary server, enable the backup job.</span></span>  
  
6.  <span data-ttu-id="b400a-176">Führen Sie auf dem sekundären Server [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) aus, um die Details des primären Servers und der Datenbank zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="b400a-176">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="b400a-177">Diese gespeicherte Prozedur gibt die sekundäre ID sowie die IDs des Kopier- und des Wiederherstellungsauftrags zurück.</span><span class="sxs-lookup"><span data-stu-id="b400a-177">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
7.  <span data-ttu-id="b400a-178">Führen Sie auf dem sekundären Server [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) aus, um den Zeitplan für den Kopier- und den Wiederherstellungsauftrag festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b400a-178">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
8.  <span data-ttu-id="b400a-179">Führen Sie auf dem sekundären Server [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) aus, um eine sekundäre Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b400a-179">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
9. <span data-ttu-id="b400a-180">Führen Sie auf dem primären Server [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) aus, um die erforderlichen Informationen über die neue sekundäre Datenbank dem primären Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b400a-180">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
10. <span data-ttu-id="b400a-181">Aktivieren Sie auf dem sekundären Server den Kopier- und den Wiederherstellungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="b400a-181">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="b400a-182">Weitere Informationen finden sie unter [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="b400a-182">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b400a-183">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b400a-183">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b400a-184">Aktualisieren des Protokoll Versands auf SQL Server 2014 &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-184">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="b400a-185">Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-185">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="b400a-186">Entfernen einer sekundären Datenbank aus einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-186">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="b400a-187">Entfernen des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-187">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="b400a-188">Anzeigen des Protokollversandberichts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-188">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b400a-189">Überwachen des Protokollversands &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-189">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="b400a-190">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b400a-190">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b400a-191">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b400a-191">See Also</span></span>  
 <span data-ttu-id="b400a-192">[Informationen zum Protokollversand &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b400a-192">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="b400a-193">Protokollversandtabellen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b400a-193">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
