---
title: Wiederherstellen von Dateien und Dateigruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2576f1326cb50fa197b1623aaa1326d70137823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699801"
---
# <a name="restore-files-and-filegroups-sql-server"></a><span data-ttu-id="8d616-102">Wiederherstellen von Dateien und Dateigruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8d616-102">Restore Files and Filegroups (SQL Server)</span></span>
  <span data-ttu-id="8d616-103">In diesem Thema wird beschrieben, wie Sie Daten und Dateigruppen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="8d616-103">This topic describes how to restore files and filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8d616-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8d616-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8d616-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8d616-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8d616-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8d616-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="8d616-107">Security</span><span class="sxs-lookup"><span data-stu-id="8d616-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8d616-108">**So stellen Sie Dateien und Dateigruppen wieder her mit**</span><span class="sxs-lookup"><span data-stu-id="8d616-108">**To restore files and filegroups, using:**</span></span>  
  
     [<span data-ttu-id="8d616-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d616-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8d616-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d616-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8d616-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8d616-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8d616-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8d616-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8d616-113">Nur der mit der Wiederherstellung der Dateien und Dateigruppen betraute Systemadministrator darf zurzeit mit der wiederherzustellenden Datenbank arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8d616-113">The system administrator restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="8d616-114">RESTORE ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="8d616-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="8d616-115">Die Datei muss im Rahmen des Modells der einfachen Wiederherstellung zu einer schreibgeschützten Dateigruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="8d616-115">Under the simple recovery model, the file must belong to a read-only filegroup.</span></span>  
  
-   <span data-ttu-id="8d616-116">Bevor Sie mit dem vollständigen oder dem massenprotokollierten Wiederherstellungsmodell Dateien wiederherstellen können, müssen Sie das Protokoll der aktiven Transaktion (das sog. Protokollfragment) sichern.</span><span class="sxs-lookup"><span data-stu-id="8d616-116">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="8d616-117">Weitere Informationen finden Sie unter [Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)bezeichnet) gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="8d616-117">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="8d616-118">Um eine verschlüsselte Datenbank wiederherstellen zu können, muss das Zertifikat oder der asymmetrische Schlüssel verfügbar sein, das oder der zum Verschlüsseln der Datenbank verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8d616-118">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="8d616-119">Ohne das Zertifikat oder den asymmetrischen Schlüssel kann die Datenbank nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8d616-119">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="8d616-120">Darum muss das Zertifikat, das zur Verschlüsselung des Verschlüsselungsschlüssels für die Datenbank verwendet wurde, so lange beibehalten werden, wie die Sicherung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="8d616-120">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="8d616-121">Weitere Informationen finden Sie unter [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="8d616-121">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8d616-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8d616-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8d616-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8d616-123">Permissions</span></span>  
 <span data-ttu-id="8d616-124">Ist die wiederherzustellende Datenbank nicht vorhanden, muss der Benutzer über CREATE DATABASE-Berechtigungen verfügen, um RESTORE ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="8d616-124">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="8d616-125">Ist die Datenbank vorhanden, werden RESTORE-Berechtigungen standardmäßig den Mitgliedern der festen Serverrollen **sysadmin** und **dbcreator** sowie dem Besitzer (**dbo**) der Datenbank erteilt (für die Option FROM DATABASE_SNAPSHOT ist die Datenbank immer vorhanden).</span><span class="sxs-lookup"><span data-stu-id="8d616-125">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="8d616-126">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8d616-126">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="8d616-127">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="8d616-127">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8d616-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d616-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="8d616-129">So stellen Sie Dateien und Dateigruppen wieder her</span><span class="sxs-lookup"><span data-stu-id="8d616-129">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="8d616-130">Stellen Sie eine Verbindung mit der entsprechenden Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und klicken Sie danach im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="8d616-130">After you connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8d616-131">Erweitern Sie **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="8d616-131">Expand **Databases**.</span></span> <span data-ttu-id="8d616-132">Wählen Sie je nach Datenbank entweder eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken**, und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="8d616-132">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="8d616-133">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="8d616-133">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="8d616-134">Klicken Sie auf **Dateien und Dateigruppen**. Daraufhin wird das Dialogfeld **Dateien und Dateigruppen wiederherstellen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8d616-134">Click **Files and Filegroups**, which opens the **Restore Files and Filegroups** dialog box.</span></span>  
  
5.  <span data-ttu-id="8d616-135">Geben Sie auf der **Allgemein** im Listenfeld **In Datenbank** die wiederherzustellenden Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="8d616-135">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="8d616-136">Sie können eine neue Datenbank eingeben oder eine vorhandene Datenbank aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="8d616-136">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="8d616-137">Die Liste umfasst alle Datenbanken auf dem Server, mit Ausnahme der Datenbanken **master** und **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="8d616-137">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
6.  <span data-ttu-id="8d616-138">Zum Festlegen von Quelle und Speicherort der wiederherzustellenden Sicherungssätze klicken Sie auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="8d616-138">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="8d616-139">**Aus Datenbank**</span><span class="sxs-lookup"><span data-stu-id="8d616-139">**From database**</span></span>  
  
         <span data-ttu-id="8d616-140">Geben Sie im Listenfeld einen Datenbanknamen ein.</span><span class="sxs-lookup"><span data-stu-id="8d616-140">Enter a database name in the list box.</span></span> <span data-ttu-id="8d616-141">Diese Liste enthält nur Datenbanken, die entsprechend dem Sicherungsverlauf von **msdb** gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="8d616-141">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="8d616-142">**Von Gerät**</span><span class="sxs-lookup"><span data-stu-id="8d616-142">**From device**</span></span>  
  
         <span data-ttu-id="8d616-143">Klicken Sie auf die Schaltfläche zum Durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="8d616-143">Click the browse button.</span></span> <span data-ttu-id="8d616-144">Wählen Sie im Dialogfeld für das **Angeben der Sicherungsgeräte** einen der im Listenfeld **Sicherungsmedientyp** aufgeführten Medientypen aus.</span><span class="sxs-lookup"><span data-stu-id="8d616-144">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="8d616-145">Klicken Sie zum Auswählen von einem oder mehreren Medien für das Listenfeld **Sicherungsmedien** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8d616-145">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="8d616-146">Klicken Sie nach dem Hinzufügen der gewünschten Medien zum Listenfeld **Sicherungsmedien** auf **OK** , um zur Seite **Allgemein** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="8d616-146">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
7.  <span data-ttu-id="8d616-147">Wählen Sie im Raster **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die wiederherzustellenden Sicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="8d616-147">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="8d616-148">Mit diesem Raster werden die Sicherungen angezeigt, die für den angegebenen Speicherort verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8d616-148">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="8d616-149">Standardmäßig wird ein Wiederherstellungsplan vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="8d616-149">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="8d616-150">Sie können die Auswahl im Raster ändern, um den vorgeschlagenen Wiederherstellungsplan zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8d616-150">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="8d616-151">Für Sicherungen, die von einer Sicherung abhängig sind, für die die Auswahl aufgehoben wurde, wird die Auswahl automatisch aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="8d616-151">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="8d616-152">Spaltenkopf</span><span class="sxs-lookup"><span data-stu-id="8d616-152">Column head</span></span>|<span data-ttu-id="8d616-153">Werte</span><span class="sxs-lookup"><span data-stu-id="8d616-153">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="8d616-154">**Wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="8d616-154">**Restore**</span></span>|<span data-ttu-id="8d616-155">Die aktivierten Kontrollkästchen zeigen die wiederherzustellenden Sicherungssätze an.</span><span class="sxs-lookup"><span data-stu-id="8d616-155">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="8d616-156">**Name**</span><span class="sxs-lookup"><span data-stu-id="8d616-156">**Name**</span></span>|<span data-ttu-id="8d616-157">Name des Sicherungssatzes.</span><span class="sxs-lookup"><span data-stu-id="8d616-157">The name of the backup set.</span></span>|  
    |<span data-ttu-id="8d616-158">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="8d616-158">**File Type**</span></span>|<span data-ttu-id="8d616-159">Gibt den Typ der Daten in der Sicherung an. **Daten**, **Protokoll**, oder **Filestreamdaten**.</span><span class="sxs-lookup"><span data-stu-id="8d616-159">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="8d616-160">Daten, die in Tabellen enthalten sind, befinden sich in **Daten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="8d616-160">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="8d616-161">Transaktionsprotokolldaten befinden sich in **Protokoll** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="8d616-161">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="8d616-162">Blobdaten (Binary Large Object), die im Dateisystem gespeichert werden, befinden sich in **Filestreamdaten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="8d616-162">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="8d616-163">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8d616-163">**Type**</span></span>|<span data-ttu-id="8d616-164">Der Typ des ausgeführten Sicherungsvorgangs: **Vollständig**, **Differenziell** oder **Transaktionsprotokoll**.</span><span class="sxs-lookup"><span data-stu-id="8d616-164">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="8d616-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="8d616-165">**Server**</span></span>|<span data-ttu-id="8d616-166">Name der Instanz des Datenbankmoduls, durch die der Sicherungsvorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="8d616-166">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="8d616-167">**Logischer Name der Datei**</span><span class="sxs-lookup"><span data-stu-id="8d616-167">**File Logical Name**</span></span>|<span data-ttu-id="8d616-168">Der logische Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="8d616-168">The logical name of the file.</span></span>|  
    |<span data-ttu-id="8d616-169">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="8d616-169">**Database**</span></span>|<span data-ttu-id="8d616-170">Name der an der Sicherungsoperation beteiligten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8d616-170">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="8d616-171">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="8d616-171">**Start Date**</span></span>|<span data-ttu-id="8d616-172">Datum und Uhrzeit des Sicherungsbeginns, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="8d616-172">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="8d616-173">**Beendigungsdatum**</span><span class="sxs-lookup"><span data-stu-id="8d616-173">**Finish Date**</span></span>|<span data-ttu-id="8d616-174">Datum und Uhrzeit des Endes des Sicherungsvorgangs, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="8d616-174">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="8d616-175">**Größe**</span><span class="sxs-lookup"><span data-stu-id="8d616-175">**Size**</span></span>|<span data-ttu-id="8d616-176">Größe des Sicherungssatzes in Byte.</span><span class="sxs-lookup"><span data-stu-id="8d616-176">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="8d616-177">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="8d616-177">**User Name**</span></span>|<span data-ttu-id="8d616-178">Name des Benutzers, der den Sicherungsvorgang ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="8d616-178">The name of the user who performed the backup operation.</span></span>|  
  
8.  <span data-ttu-id="8d616-179">Klicken Sie auf der Seite **Seite auswählen** auf **Optionen**, um die erweiterten Optionen anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8d616-179">To view or select the advanced options, click **Options** in the **Select a page pane**.</span></span>  
  
9. <span data-ttu-id="8d616-180">Im Bereich **Wiederherstellungsoptionen** können Sie Ihren Anforderungen entsprechend aus den folgenden Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="8d616-180">In the **Restore options** panel, you can choose any of the following options, if appropriate for your situation.</span></span>  
  
     <span data-ttu-id="8d616-181">**Als Dateigruppe wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="8d616-181">**Restore as filegroup**</span></span>  
     <span data-ttu-id="8d616-182">Zeigt an, dass eine komplette Dateigruppe wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8d616-182">Indicates that an entire filegroup is being restored.</span></span>  
  
     <span data-ttu-id="8d616-183">**Vorhandene Datenbank überschreiben**</span><span class="sxs-lookup"><span data-stu-id="8d616-183">**Overwrite the existing database**</span></span>  
     <span data-ttu-id="8d616-184">Legt fest, dass beim Wiederherstellungsvorgang alle vorhandenen Datenbanken und die dazugehörigen Dateien überschrieben werden, selbst wenn bereits eine Datenbank oder Datei mit demselben Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8d616-184">Specifies that the restore operation should overwrite any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
     <span data-ttu-id="8d616-185">Das Auswählen dieser Option entspricht der Verwendung der Option REPLACE in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8d616-185">Selecting this option is equivalent to using the REPLACE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="8d616-186">**Bestätigung vor Wiederherstellen jeder einzelnen Sicherung**</span><span class="sxs-lookup"><span data-stu-id="8d616-186">**Prompt before restoring each backup**</span></span>  
     <span data-ttu-id="8d616-187">Fordert bei jedem Sicherungssatz eine Bestätigung vom Benutzer, bevor mit der Wiederherstellung begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="8d616-187">Asks you for confirmation before restoring each backup set.</span></span>  
  
     <span data-ttu-id="8d616-188">Diese Option ist insbesondere dann hilfreich, wenn Sie Bänder für verschiedene Mediensätze wechseln müssen, beispielsweise wenn der Server nur ein Bandgerät besitzt.</span><span class="sxs-lookup"><span data-stu-id="8d616-188">This option is particularly useful where you must swap tapes for different media sets, such as when the server has one tape device.</span></span>  
  
     <span data-ttu-id="8d616-189">**Zugriff auf die wiederhergestellte Datenbank einschränken**</span><span class="sxs-lookup"><span data-stu-id="8d616-189">**Restrict access to the restored database**</span></span>  
     <span data-ttu-id="8d616-190">Macht die wiederhergestellte Datenbank nur Mitgliedern von **db_owner**, **dbcreator** oder **sysadmin**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d616-190">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
     <span data-ttu-id="8d616-191">Das Auswählen dieser Option entspricht der Verwendung der Option RESTRICTED_USER in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8d616-191">Selecting this option is synonymous to using the RESTRICTED_USER option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
10. <span data-ttu-id="8d616-192">Optional: Sie können die Datenbank an einem neuen Speicherort wiederherstellen, indem Sie im Raster **Datenbankdateien wiederherstellen als** für jede Datei ein neues Wiederherstellungsziel angeben.</span><span class="sxs-lookup"><span data-stu-id="8d616-192">Optionally, you can restore the database to a new location by specifying a new restore destination for each file in the **Restore database files as** grid.</span></span>  
  
    |<span data-ttu-id="8d616-193">Spaltenkopf</span><span class="sxs-lookup"><span data-stu-id="8d616-193">Column head</span></span>|<span data-ttu-id="8d616-194">Werte</span><span class="sxs-lookup"><span data-stu-id="8d616-194">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="8d616-195">**Originaldateiname**</span><span class="sxs-lookup"><span data-stu-id="8d616-195">**Original File Name**</span></span>|<span data-ttu-id="8d616-196">Der vollständige Pfad einer Quellsicherungsdatei.</span><span class="sxs-lookup"><span data-stu-id="8d616-196">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="8d616-197">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="8d616-197">**File Type**</span></span>|<span data-ttu-id="8d616-198">Gibt den Typ der Daten in der Sicherung an. **Daten**, **Protokoll**, oder **Filestreamdaten**.</span><span class="sxs-lookup"><span data-stu-id="8d616-198">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="8d616-199">Daten, die in Tabellen enthalten sind, befinden sich in **Daten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="8d616-199">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="8d616-200">Transaktionsprotokolldaten befinden sich in **Protokoll** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="8d616-200">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="8d616-201">Blobdaten (Binary Large Object), die im Dateisystem gespeichert werden, befinden sich in **Filestreamdaten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="8d616-201">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="8d616-202">**Wiederherstellen als**</span><span class="sxs-lookup"><span data-stu-id="8d616-202">**Restore As**</span></span>|<span data-ttu-id="8d616-203">Der vollständige Pfad der wiederherzustellenden Datenbankdatei.</span><span class="sxs-lookup"><span data-stu-id="8d616-203">The full path of the database file to be restored.</span></span> <span data-ttu-id="8d616-204">Um eine neue Wiederherstellungsdatei anzugeben, klicken Sie auf das Textfeld, und bearbeiten Sie den vorgeschlagenen Pfad und Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="8d616-204">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="8d616-205">Das Ändern des Pfads oder des Dateinamens in der Spalte **Wiederherstellen als** entspricht der Option MOVE in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8d616-205">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
11. <span data-ttu-id="8d616-206">Die Optionen im Bereich **Wiederherstellungsstatus** bestimmen den Status der Datenbank nach dem Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="8d616-206">The **Recovery state** panel determines the state of the database after the restore operation.</span></span>  
  
     <span data-ttu-id="8d616-207">**Datenbank betriebsbereit belassen, indem für Transaktionen ohne Commit ein Rollback ausgeführt wird. Zusätzliche Transaktionsprotokolle können nicht wiederhergestellt werden. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="8d616-207">**Leave the database ready for use by rolling back the uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
     <span data-ttu-id="8d616-208">Stellt die Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="8d616-208">Recovers the database.</span></span> <span data-ttu-id="8d616-209">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="8d616-209">This is the default behavior.</span></span> <span data-ttu-id="8d616-210">Wählen Sie diese Option nur aus, wenn Sie alle benötigten Sicherungen jetzt wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d616-210">Choose this option only if you are restoring all of the necessary backups now.</span></span> <span data-ttu-id="8d616-211">Diese Option entspricht der Angabe von WITH RECOVERY in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8d616-211">This option is equivalent to specifying WITH RECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="8d616-212">**Datenbank nicht betriebsbereit belassen und kein Rollback für Transaktionen ohne Commit ausführen. Zusätzliche Transaktionsprotokolle können wiederhergestellt werden. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="8d616-212">**Leave the database non-operational, and don't roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
     <span data-ttu-id="8d616-213">Belässt die Datenbank im Wiederherstellungsstatus.</span><span class="sxs-lookup"><span data-stu-id="8d616-213">Leaves the database in the restoring state.</span></span> <span data-ttu-id="8d616-214">Um die Datenbank wiederherzustellen, müssen Sie eine weitere Wiederherstellung mithilfe der vorangegangenen Option RESTORE WITH RECOVERY ausführen (siehe oben).</span><span class="sxs-lookup"><span data-stu-id="8d616-214">To recover the database, you will need to perform another restore using the preceding RESTORE WITH RECOVERY option (see above).</span></span> <span data-ttu-id="8d616-215">Diese Option entspricht der Angabe von WITH NORECOVERY in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8d616-215">This option is equivalent to specifying WITH NORECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="8d616-216">Wenn Sie diese Option auswählen, ist die Option **Replikationseinstellungen beibehalten** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d616-216">If you select this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
     <span data-ttu-id="8d616-217">**Datenbank im schreibgeschützten Modus belassen. Transaktionen ohne Commit werden rückgängig gemacht, die Rückgängigaktionen werden jedoch in einer Standbydatei gespeichert, sodass die Auswirkungen der Wiederherstellung umgekehrt werden können. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="8d616-217">**Leave the database in read-only mode. Roll back the uncommitted transactions, but save the rollback operation in a file so the recovery effects can be undone. (RESTORE WITH STANDBY)**</span></span>  
     <span data-ttu-id="8d616-218">Belässt die Datenbank in einem Standbystatus.</span><span class="sxs-lookup"><span data-stu-id="8d616-218">Leaves the database in a standby state.</span></span> <span data-ttu-id="8d616-219">Diese Option entspricht der Angabe von WITH STANDBY in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8d616-219">This option is equivalent to specifying WITH STANDBY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="8d616-220">Bei Auswahl dieser Option müssen Sie eine Standbydatei angeben.</span><span class="sxs-lookup"><span data-stu-id="8d616-220">Choosing this option requires that you specify a standby file.</span></span>  
  
     <span data-ttu-id="8d616-221">**Rollback-Rückgängigdatei**</span><span class="sxs-lookup"><span data-stu-id="8d616-221">**Rollback undo file**</span></span>  
     <span data-ttu-id="8d616-222">Geben Sie im Textfeld **Rollback-Rückgängigdatei** einen Namen für die Standbydatei an.</span><span class="sxs-lookup"><span data-stu-id="8d616-222">Specify a standby file name in the **Rollback undo file** text box.</span></span> <span data-ttu-id="8d616-223">Diese Option ist erforderlich, wenn Sie die Datenbank im schreibgeschützten Modus belassen (RESTORE WITH STANDBY).</span><span class="sxs-lookup"><span data-stu-id="8d616-223">This option is required if you leave the database in read-only mode (RESTORE WITH STANDBY).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8d616-224">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d616-224">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="8d616-225">So stellen Sie Dateien und Dateigruppen wieder her</span><span class="sxs-lookup"><span data-stu-id="8d616-225">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="8d616-226">Führen Sie die RESTORE DATABASE-Anweisung aus, um die Datei- und Dateigruppensicherung wiederherzustellen, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="8d616-226">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="8d616-227">Den Namen der wiederherzustellenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8d616-227">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="8d616-228">Das Sicherungsmedium, von dem die vollständige Datenbanksicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8d616-228">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="8d616-229">Die FILE-Klausel für jede wiederherzustellende Datei.</span><span class="sxs-lookup"><span data-stu-id="8d616-229">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="8d616-230">Die FILEGROUP-Klausel für jede wiederherzustellende Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="8d616-230">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="8d616-231">Die NORECOVERY-Klausel.</span><span class="sxs-lookup"><span data-stu-id="8d616-231">The NORECOVERY clause.</span></span> <span data-ttu-id="8d616-232">Wenn die Dateien nach dem Erstellen der Sicherung nicht geändert wurden, geben Sie die RECOVERY-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="8d616-232">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="8d616-233">Wenn die Dateien nach dem Erstellen der Sicherung geändert wurden, führen Sie die RESTORE LOG-Anweisung aus, um die Transaktionsprotokollsicherung anzuwenden, und geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="8d616-233">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="8d616-234">Den Namen der Datenbank, auf die das zu sichernde Transaktionsprotokoll angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d616-234">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="8d616-235">Das Sicherungsmedium, von dem die Transaktionsprotokollsicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8d616-235">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="8d616-236">Die NORECOVERY-Klausel, wenn nach der aktuellen Transaktionsprotokollsicherung eine weitere angewendet werden soll. Geben Sie andernfalls die RECOVERY-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="8d616-236">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="8d616-237">Die gegebenenfalls angewendeten Transaktionsprotokollsicherungen müssen den Zeitpunkt, zu dem die Dateien und Dateigruppen gesichert wurden, bis hin zum Protokollende abdecken (es sei denn, ALLE Datenbankdateien werden wiederhergestellt).</span><span class="sxs-lookup"><span data-stu-id="8d616-237">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up until the end of log (unless ALL database files are restored).</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="8d616-238">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8d616-238">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="8d616-239">In diesem Beispiel werden die Dateien und Dateigruppen der `MyDatabase` -Datenbank wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="8d616-239">This example restores the files and filegroups for the `MyDatabase` database.</span></span> <span data-ttu-id="8d616-240">Zur Wiederherstellung der Datenbank zur aktuellen Zeit werden zwei Transaktionsprotokolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="8d616-240">To restore the database to the current time, two transaction logs are applied.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d616-241">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d616-241">See Also</span></span>  
 <span data-ttu-id="8d616-242">[Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="8d616-242">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="8d616-243">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8d616-243">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="8d616-244">[Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8d616-244">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="8d616-245">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8d616-245">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="8d616-246">[Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8d616-246">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="8d616-247">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d616-247">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
