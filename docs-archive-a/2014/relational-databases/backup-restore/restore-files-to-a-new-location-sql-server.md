---
title: Wiederherstellen von Dateien an einem neuen Speicherort (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring databases [SQL Server], moving
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
ms.assetid: b4f4791d-646e-4632-9980-baae9cb1aade
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a8336e5d186fb72df4e0a17fdd9affccab4ee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699795"
---
# <a name="restore-files-to-a-new-location-sql-server"></a><span data-ttu-id="f73c0-102">Wiederherstellen von Dateien an einem neuen Speicherort (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f73c0-102">Restore Files to a New Location (SQL Server)</span></span>
  <span data-ttu-id="f73c0-103">In diesem Thema wird beschrieben, wie Sie Dateien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]auf einem neuen Speicherort wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="f73c0-103">This topic describes how to restore files to a new location in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f73c0-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f73c0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f73c0-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f73c0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f73c0-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f73c0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f73c0-107">Security</span><span class="sxs-lookup"><span data-stu-id="f73c0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f73c0-108">**So stellen Sie Dateien an einem neuen Speicherort wieder her mit**</span><span class="sxs-lookup"><span data-stu-id="f73c0-108">**To restore files to a new location, using:**</span></span>  
  
     [<span data-ttu-id="f73c0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f73c0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f73c0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f73c0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f73c0-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f73c0-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f73c0-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f73c0-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f73c0-113">Nur der Systemadministrator, der die Dateien wiederherstellt, darf zurzeit mit der wiederherzustellenden Datenbank arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f73c0-113">The system administrator restoring the files must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="f73c0-114">RESTORE ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="f73c0-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="f73c0-115">Bevor Sie mit dem vollständigen oder dem massenprotokollierten Wiederherstellungsmodell Dateien wiederherstellen können, müssen Sie das Protokoll der aktiven Transaktion (das sog. Protokollfragment) sichern.</span><span class="sxs-lookup"><span data-stu-id="f73c0-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="f73c0-116">Weitere Informationen finden Sie unter [Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)bezeichnet) gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="f73c0-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="f73c0-117">Um eine verschlüsselte Datenbank wiederherstellen zu können, muss das Zertifikat oder der asymmetrische Schlüssel verfügbar sein, das oder der zum Verschlüsseln der Datenbank verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f73c0-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="f73c0-118">Ohne das Zertifikat oder den asymmetrischen Schlüssel kann die Datenbank nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f73c0-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="f73c0-119">Darum muss das Zertifikat, das zur Verschlüsselung des Verschlüsselungsschlüssels für die Datenbank verwendet wurde, so lange beibehalten werden, wie die Sicherung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="f73c0-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="f73c0-120">Weitere Informationen finden Sie unter [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="f73c0-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f73c0-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f73c0-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f73c0-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f73c0-122">Permissions</span></span>  
 <span data-ttu-id="f73c0-123">Ist die wiederherzustellende Datenbank nicht vorhanden, muss der Benutzer über CREATE DATABASE-Berechtigungen verfügen, um RESTORE ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="f73c0-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="f73c0-124">Ist die Datenbank vorhanden, werden RESTORE-Berechtigungen standardmäßig den Mitgliedern der festen Serverrollen **sysadmin** und **dbcreator** sowie dem Besitzer (**dbo**) der Datenbank erteilt (für die Option FROM DATABASE_SNAPSHOT ist die Datenbank immer vorhanden).</span><span class="sxs-lookup"><span data-stu-id="f73c0-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="f73c0-125">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f73c0-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="f73c0-126">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f73c0-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f73c0-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="f73c0-128">So stellen Sie Dateien an einem neuen Speicherort wieder her</span><span class="sxs-lookup"><span data-stu-id="f73c0-128">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="f73c0-129">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, erweitern Sie diese Instanz und dann **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="f73c0-130">Klicken Sie mit der rechten Maustaste auf die gewünschte Datenbank, zeigen Sie auf **Tasks**, zeigen Sie auf **Wiederherstellen**, und klicken Sie anschließend auf **Dateien und Dateigruppen**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="f73c0-131">Geben Sie auf der **Allgemein** im Listenfeld **In Datenbank** die wiederherzustellenden Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="f73c0-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="f73c0-132">Sie können eine neue Datenbank eingeben oder eine vorhandene Datenbank aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="f73c0-133">Die Liste umfasst alle Datenbanken auf dem Server, mit Ausnahme der Datenbanken **master** und **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="f73c0-134">Zum Festlegen von Quelle und Speicherort der wiederherzustellenden Sicherungssätze klicken Sie auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="f73c0-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="f73c0-135">**Aus Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f73c0-135">**From database**</span></span>  
  
         <span data-ttu-id="f73c0-136">Geben Sie im Listenfeld einen Datenbanknamen ein.</span><span class="sxs-lookup"><span data-stu-id="f73c0-136">Enter a database name in the list box.</span></span> <span data-ttu-id="f73c0-137">Diese Liste enthält nur Datenbanken, die entsprechend dem Sicherungsverlauf von **msdb** gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="f73c0-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="f73c0-138">**Von Gerät**</span><span class="sxs-lookup"><span data-stu-id="f73c0-138">**From device**</span></span>  
  
         <span data-ttu-id="f73c0-139">Klicken Sie auf die Schaltfläche zum Durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-139">Click the browse button.</span></span> <span data-ttu-id="f73c0-140">Wählen Sie im Dialogfeld für das **Angeben der Sicherungsgeräte** einen der im Listenfeld **Sicherungsmedientyp** aufgeführten Medientypen aus.</span><span class="sxs-lookup"><span data-stu-id="f73c0-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="f73c0-141">Klicken Sie zum Auswählen von einem oder mehreren Medien für das Listenfeld **Sicherungsmedien** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="f73c0-142">Klicken Sie nach dem Hinzufügen der gewünschten Medien zum Listenfeld **Sicherungsmedien** auf **OK** , um zur Seite **Allgemein** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f73c0-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="f73c0-143">Wählen Sie im Raster **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die wiederherzustellenden Sicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="f73c0-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="f73c0-144">Mit diesem Raster werden die Sicherungen angezeigt, die für den angegebenen Speicherort verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f73c0-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="f73c0-145">Standardmäßig wird ein Wiederherstellungsplan vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="f73c0-146">Sie können die Auswahl im Raster ändern, um den vorgeschlagenen Wiederherstellungsplan zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f73c0-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="f73c0-147">Für Sicherungen, die von einer Sicherung abhängig sind, für die die Auswahl aufgehoben wurde, wird die Auswahl automatisch aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="f73c0-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="f73c0-148">Spaltenkopf</span><span class="sxs-lookup"><span data-stu-id="f73c0-148">Column head</span></span>|<span data-ttu-id="f73c0-149">Werte</span><span class="sxs-lookup"><span data-stu-id="f73c0-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="f73c0-150">**Wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="f73c0-150">**Restore**</span></span>|<span data-ttu-id="f73c0-151">Die aktivierten Kontrollkästchen zeigen die wiederherzustellenden Sicherungssätze an.</span><span class="sxs-lookup"><span data-stu-id="f73c0-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="f73c0-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="f73c0-152">**Name**</span></span>|<span data-ttu-id="f73c0-153">Name des Sicherungssatzes.</span><span class="sxs-lookup"><span data-stu-id="f73c0-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="f73c0-154">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="f73c0-154">**File Type**</span></span>|<span data-ttu-id="f73c0-155">Gibt den Typ der Daten in der Sicherung an. **Daten**, **Protokoll**, oder **Filestreamdaten**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="f73c0-156">Daten, die in Tabellen enthalten sind, befinden sich in **Daten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="f73c0-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="f73c0-157">Transaktionsprotokolldaten befinden sich in **Protokoll** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="f73c0-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="f73c0-158">Blobdaten (Binary Large Object), die im Dateisystem gespeichert werden, befinden sich in **Filestreamdaten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="f73c0-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="f73c0-159">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f73c0-159">**Type**</span></span>|<span data-ttu-id="f73c0-160">Der Typ des ausgeführten Sicherungsvorgangs: **Vollständig**, **Differenziell** oder **Transaktionsprotokoll**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="f73c0-161">**Server**</span><span class="sxs-lookup"><span data-stu-id="f73c0-161">**Server**</span></span>|<span data-ttu-id="f73c0-162">Name der Instanz des Datenbankmoduls, durch die der Sicherungsvorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f73c0-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="f73c0-163">**Logischer Name der Datei**</span><span class="sxs-lookup"><span data-stu-id="f73c0-163">**File Logical Name**</span></span>|<span data-ttu-id="f73c0-164">Der logische Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="f73c0-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="f73c0-165">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="f73c0-165">**Database**</span></span>|<span data-ttu-id="f73c0-166">Name der an der Sicherungsoperation beteiligten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f73c0-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="f73c0-167">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="f73c0-167">**Start Date**</span></span>|<span data-ttu-id="f73c0-168">Datum und Uhrzeit des Sicherungsbeginns, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="f73c0-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="f73c0-169">**Beendigungsdatum**</span><span class="sxs-lookup"><span data-stu-id="f73c0-169">**Finish Date**</span></span>|<span data-ttu-id="f73c0-170">Datum und Uhrzeit des Endes des Sicherungsvorgangs, entsprechend den Ländereinstellungen des Clients.</span><span class="sxs-lookup"><span data-stu-id="f73c0-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="f73c0-171">**Größe**</span><span class="sxs-lookup"><span data-stu-id="f73c0-171">**Size**</span></span>|<span data-ttu-id="f73c0-172">Größe des Sicherungssatzes in Byte.</span><span class="sxs-lookup"><span data-stu-id="f73c0-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="f73c0-173">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="f73c0-173">**User Name**</span></span>|<span data-ttu-id="f73c0-174">Name des Benutzers, der den Sicherungsvorgang ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="f73c0-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="f73c0-175">Klicken Sie im Bereich **Seite auswählen** auf die Seite **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="f73c0-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="f73c0-176">Geben Sie im Raster **Datenbankdateien wiederherstellen als** einen neuen Speicherort für die Datei oder die Dateien an, die Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="f73c0-176">In the **Restore database files as** grid, specify a new location for the file or files that you want to move.</span></span>  
  
    |<span data-ttu-id="f73c0-177">Spaltenkopf</span><span class="sxs-lookup"><span data-stu-id="f73c0-177">Column head</span></span>|<span data-ttu-id="f73c0-178">Werte</span><span class="sxs-lookup"><span data-stu-id="f73c0-178">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="f73c0-179">**Originaldateiname**</span><span class="sxs-lookup"><span data-stu-id="f73c0-179">**Original File Name**</span></span>|<span data-ttu-id="f73c0-180">Der vollständige Pfad einer Quellsicherungsdatei.</span><span class="sxs-lookup"><span data-stu-id="f73c0-180">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="f73c0-181">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="f73c0-181">**File Type**</span></span>|<span data-ttu-id="f73c0-182">Gibt den Typ der Daten in der Sicherung an. **Daten**, **Protokoll**, oder **Filestreamdaten**.</span><span class="sxs-lookup"><span data-stu-id="f73c0-182">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="f73c0-183">Daten, die in Tabellen enthalten sind, befinden sich in **Daten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="f73c0-183">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="f73c0-184">Transaktionsprotokolldaten befinden sich in **Protokoll** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="f73c0-184">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="f73c0-185">Blobdaten (Binary Large Object), die im Dateisystem gespeichert werden, befinden sich in **Filestreamdaten** -Dateien.</span><span class="sxs-lookup"><span data-stu-id="f73c0-185">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="f73c0-186">**Wiederherstellen als**</span><span class="sxs-lookup"><span data-stu-id="f73c0-186">**Restore As**</span></span>|<span data-ttu-id="f73c0-187">Der vollständige Pfad der wiederherzustellenden Datenbankdatei.</span><span class="sxs-lookup"><span data-stu-id="f73c0-187">The full path of the database file to be restored.</span></span> <span data-ttu-id="f73c0-188">Um eine neue Wiederherstellungsdatei anzugeben, klicken Sie auf das Textfeld, und bearbeiten Sie den vorgeschlagenen Pfad und Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-188">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="f73c0-189">Das Ändern des Pfads oder des Dateinamens in der Spalte **Wiederherstellen als** entspricht der Option MOVE in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f73c0-189">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f73c0-190">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f73c0-190">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="f73c0-191">So stellen Sie Dateien an einem neuen Speicherort wieder her</span><span class="sxs-lookup"><span data-stu-id="f73c0-191">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="f73c0-192">Führen Sie optional die RESTORE FILELISTONLY-Anweisung aus, um Anzahl und Namen der Dateien in der vollständigen Datenbanksicherung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-192">Optionally, execute the RESTORE FILELISTONLY statement to determine the number and names of the files in the full database backup.</span></span>  
  
2.  <span data-ttu-id="f73c0-193">Führen Sie die RESTORE DATABASE-Anweisung aus, um die vollständige Datenbanksicherung wiederherzustellen, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="f73c0-193">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="f73c0-194">Den Namen der wiederherzustellenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f73c0-194">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="f73c0-195">Das Sicherungsmedium, von dem die vollständige Datenbanksicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f73c0-195">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="f73c0-196">Die MOVE-Klausel für jede Datei, die an einem neuen Speicherort wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f73c0-196">The MOVE clause for each file to restore to a new location.</span></span>  
  
    -   <span data-ttu-id="f73c0-197">Die NORECOVERY-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f73c0-197">The NORECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="f73c0-198">Wenn die Dateien nach dem Erstellen der Sicherung geändert wurden, führen Sie die RESTORE LOG-Anweisung aus, um die Transaktionsprotokollsicherung anzuwenden, und geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="f73c0-198">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="f73c0-199">Den Namen der Datenbank, auf die das zu sichernde Transaktionsprotokoll angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f73c0-199">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="f73c0-200">Das Sicherungsmedium, von dem die Transaktionsprotokollsicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f73c0-200">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="f73c0-201">Die NORECOVERY-Klausel, wenn nach der aktuellen Transaktionsprotokollsicherung eine weitere angewendet werden soll. Geben Sie andernfalls die RECOVERY-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="f73c0-201">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="f73c0-202">Die gegebenenfalls angewendeten Transaktionsprotokollsicherungen müssen den Zeitpunkt einschließen, zu dem die Dateien und Dateigruppen gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="f73c0-202">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="f73c0-203">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f73c0-203">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="f73c0-204">In diesem Beispiel werden zwei der Dateien für die `MyNwind` -Datenbank, die sich ursprünglich auf Laufwerk C befanden, an neuen Speicherorten auf Laufwerk D wiederhergestellt. Zwei Transaktionsprotokolle werden ebenfalls angewendet, um die Datenbank bis zum aktuellen Zeitpunkt wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f73c0-204">This example restores two of the files for the `MyNwind` database that were originally located on Drive C to new locations on Drive D. Two transaction logs will also be applied to restore the database to the current time.</span></span> <span data-ttu-id="f73c0-205">Die `RESTORE FILELISTONLY` -Anweisung wird verwendet, um die Anzahl der logischen und physischen Namen der Dateien der Datenbank zu bestimmen, die wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f73c0-205">The `RESTORE FILELISTONLY` statement is used to determine the number and logical and physical names of the files in the database being restored.</span></span>  
  
```sql  
USE master;  
GO  
-- First determine the number and names of the files in the backup.  
RESTORE FILELISTONLY  
   FROM MyNwind_1;  
-- Restore the files for MyNwind.  
RESTORE DATABASE MyNwind  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   MOVE 'MyNwind_data_1' TO 'D:\MyData\MyNwind_data_1.mdf',   
   MOVE 'MyNwind_data_2' TO 'D:\MyData\MyNwind_data_2.ndf';  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f73c0-206">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f73c0-206">See Also</span></span>  
 <span data-ttu-id="f73c0-207">[Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="f73c0-207">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="f73c0-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f73c0-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="f73c0-209">[Kopieren von Datenbanken durch Sichern und Wiederherstellen](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="f73c0-209">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="f73c0-210">Wiederherstellen von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f73c0-210">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
  
