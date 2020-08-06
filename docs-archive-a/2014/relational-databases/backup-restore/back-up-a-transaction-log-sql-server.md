---
title: Sichern eines Transaktionsprotokolls (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction log backups [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- backing up transaction logs [SQL Server], SQL Server Management Studio
ms.assetid: 3426b5eb-6327-4c7f-88aa-37030be69fbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b57ca40b08718cda5095249991e0d424e6593a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617143"
---
# <a name="back-up-a-transaction-log-sql-server"></a><span data-ttu-id="1e8a8-102">Sichern eines Transaktionsprotokolls (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1e8a8-102">Back Up a Transaction Log (SQL Server)</span></span>
  <span data-ttu-id="1e8a8-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder PowerShell ein Transaktionsprotokoll sichern.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-103">This topic describes how to back up a transaction log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="1e8a8-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1e8a8-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1e8a8-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1e8a8-107">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1e8a8-108">Security</span><span class="sxs-lookup"><span data-stu-id="1e8a8-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1e8a8-109">**Sichern eines Transaktionsprotokolls mit:**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-109">**To back up a transaction log, using:**</span></span>  
  
     [<span data-ttu-id="1e8a8-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e8a8-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1e8a8-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e8a8-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1e8a8-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8a8-112">PowerShell</span></span>](#PowerShellProcedure)  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e8a8-113"> Alternativ können Sie den[Wartungsplanungs-Assistenten](../maintenance-plans/use-the-maintenance-plan-wizard.md)zum Erstellen von Sicherungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-113">Alternatively, you can use the[Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md)to create backups.</span></span>  
  
-   [<span data-ttu-id="1e8a8-114">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1e8a8-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1e8a8-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1e8a8-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1e8a8-117">Die BACKUP-Anweisung ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1e8a8-118">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-118">Recommendations</span></span>  
  
-   <span data-ttu-id="1e8a8-119">Wenn eine Datenbank das vollständige oder das massenprotokollierte Wiederherstellungsmodell verwendet, muss das Transaktionsprotokoll so oft gesichert werden, dass die Daten geschützt sind und das Transaktionsprotokoll nicht aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-119">If a database uses either the full or bulk-logged recovery model, you must back up the transaction log regularly enough to protect your data and to keep the transaction log from filling.</span></span> <span data-ttu-id="1e8a8-120">Dadurch wird das Protokoll gekürzt, und die Wiederherstellung der Datenbank zu einem bestimmten Zeitpunkt wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-120">This truncates the log and supports restoring the database to a specific point in time.</span></span>  
  
-   <span data-ttu-id="1e8a8-121">Standardmäßig wird bei jedem erfolgreichen Sicherungsvorgang dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll und dem Systemereignisprotokoll ein Eintrag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-121">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="1e8a8-122">Wenn Sie das Protokoll regelmäßig sichern, kann die Anzahl dieser Erfolgsmeldungen schnell ansteigen, d. h., es entstehen sehr große Fehlerprotokolle, die das Suchen nach anderen Meldungen erschweren können.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-122">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="1e8a8-123">In solchen Fällen können Sie diese Protokolleinträge mithilfe des Ablaufverfolgungsflags 3226 unterdrücken, wenn keines der Skripts von diesen Einträgen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-123">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="1e8a8-124">Weitere Informationen finden Sie unter [Ablaufverfolgungsflags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-124">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1e8a8-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1e8a8-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1e8a8-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-126">Permissions</span></span>  
 <span data-ttu-id="1e8a8-127">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-127">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="1e8a8-128">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-128">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1e8a8-129">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-129">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="1e8a8-130">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-130">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="1e8a8-131">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-131">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1e8a8-132">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e8a8-132">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="1e8a8-133">So sichern Sie ein Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="1e8a8-133">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="1e8a8-134">Stellen Sie eine Verbindung mit der entsprechenden Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und klicken Sie danach im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-134">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1e8a8-135">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-135">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="1e8a8-136">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-136">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="1e8a8-137">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-137">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="1e8a8-138">Überprüfen Sie den Datenbanknamen im Listenfeld **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="1e8a8-138">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="1e8a8-139">Sie können optional eine andere Datenbank aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-139">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="1e8a8-140">Überprüfen Sie, ob als Wiederherstellungsmodell entweder **FULL** oder **BULK_LOGGED**ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-140">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="1e8a8-141">Wählen Sie im Listenfeld **Sicherungstyp** den Eintrag **Transaktionsprotokoll**aus.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-141">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="1e8a8-142">Sie können optional auch **Kopiesicherung** auswählen, um eine Kopiesicherung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-142">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="1e8a8-143">Eine *Kopiesicherung* ist eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherung, die unabhängig von der Sequenz von herkömmlichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherungen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-143">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="1e8a8-144">Weitere Informationen finden Sie unter [Kopiesicherungen &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-144">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e8a8-145">Wenn die Option **Differenziell** aktiviert ist, können Sie keine Kopiesicherung erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-145">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="1e8a8-146">Akzeptieren Sie entweder den im Textfeld **Name** vorgeschlagenen Standardnamen für den Sicherungssatz, oder geben Sie einen anderen Namen für den Sicherungssatz ein.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-146">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="1e8a8-147">Geben Sie optional in das Textfeld **Beschreibung** eine Beschreibung des Sicherungssatzes ein.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-147">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
10. <span data-ttu-id="1e8a8-148">Geben Sie an, wann der Sicherungssatz ablaufen soll:</span><span class="sxs-lookup"><span data-stu-id="1e8a8-148">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="1e8a8-149">Wenn der Sicherungssatz nach einer bestimmten Anzahl von Tagen ablaufen soll, klicken Sie auf **Nach** (die Standardoption), und geben Sie an, nach wie vielen Tagen der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-149">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="1e8a8-150">Dieser Wert kann zwischen 0 und 99999 Tagen liegen. Ein Wert von 0 Tagen bedeutet, dass der Sicherungssatz nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-150">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="1e8a8-151">Der Standardwert wird im Dialogfeld **Servereigenschaften** (Seite **Datenbankeinstellungen** ) über die Option**Standardbeibehaltung für Sicherungsmedien (in Tagen)** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-151">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="1e8a8-152">Klicken Sie zum Zugreifen auf dieses Dialogfeld im Objekt-Explorer mit der rechten Maustaste auf den Servernamen, und wählen Sie „Eigenschaften“ aus. Wählen Sie anschließend die Seite **Datenbankeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-152">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="1e8a8-153">Zum Speichern des Sicherungssatzes an einem bestimmten Datum klicken Sie auf **Am**. Geben Sie das Datum ein, an dem der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-153">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="1e8a8-154">Wählen Sie den Sicherungszieltyp aus, indem Sie auf **Datenträger**, **URL** oder **Band**klicken.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-154">Choose the type of backup destination by clicking **Disk**, **URL** or **Tape**.</span></span> <span data-ttu-id="1e8a8-155">Klicken Sie auf **Hinzufügen**, um die Pfade von bis zu 64 Datenträgern oder Bandlaufwerken, die einen einzelnen Mediensatz enthalten, auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-155">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="1e8a8-156">Die ausgewählten Pfade werden im Listenfeld **Sichern auf** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-156">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="1e8a8-157">Um einen Sicherungsziel zu entfernen, wählen Sie ihn aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-157">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="1e8a8-158">Zum Anzeigen des Inhalts eines Sicherungsziels wählen Sie es aus, und klicken Sie auf **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-158">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="1e8a8-159">Zum Anzeigen oder Auswählen der erweiterten Optionen klicken Sie auf **Optionen** im Bereich **Seite auswählen** .</span><span class="sxs-lookup"><span data-stu-id="1e8a8-159">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="1e8a8-160">Wählen Sie eine Option von **Medium überschreiben** aus, indem Sie auf eine der folgenden Optionen klicken:</span><span class="sxs-lookup"><span data-stu-id="1e8a8-160">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="1e8a8-161">**Auf vorhandenen Mediensatz sichern**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-161">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="1e8a8-162">Klicken Sie bei dieser Option entweder auf **An vorhandenen Sicherungssatz anfügen** oder auf **Alle vorhandenen Sicherungssätze überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-162">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="1e8a8-163">Weitere Informationen finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md):</span><span class="sxs-lookup"><span data-stu-id="1e8a8-163">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="1e8a8-164">Sie können bei Bedarf das Kontrollkästchen **Mediensatznamen und Ablaufzeit des Sicherungssatzes überprüfen** aktivieren, damit beim Sicherungsvorgang das Datum und die Uhrzeit überprüft werden, an dem bzw. zu der der Mediensatz und der Sicherungssatz ablaufen.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-164">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="1e8a8-165">Geben Sie optional einen Namen im Textfeld **Mediensatzname** ein.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-165">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="1e8a8-166">Wenn kein Name angegeben wurde, wird ein Mediensatz mit leerem Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-166">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="1e8a8-167">Wenn Sie einen Mediensatznamen angeben, wird überprüft, ob der tatsächliche Name des Mediums (Band oder Datenträger) mit dem eingegebenen Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-167">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="1e8a8-168">Wenn Sie den Mediennamen leer lassen und das Kontrollkästchen aktivieren, um ihn anhand des Mediums zu überprüfen, ist die Prüfung erfolgreich, wenn der Medienname auf dem Medium ebenfalls leer ist.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-168">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="1e8a8-169">**Auf neuen Mediensatz sichern und alle vorhandenen Sicherungssätze löschen**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-169">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="1e8a8-170">Geben Sie bei dieser Option einen Namen in das Textfeld **Name für neuen Mediensatz** und optional eine Beschreibung des Mediensatzes in das Textfeld **Beschreibung für neuen Mediensatz** ein.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-170">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span> <span data-ttu-id="1e8a8-171">Weitere Informationen finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md):</span><span class="sxs-lookup"><span data-stu-id="1e8a8-171">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
14. <span data-ttu-id="1e8a8-172">Im Bereich **Zuverlässigkeit** können Sie folgende Optionen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="1e8a8-172">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="1e8a8-173">**Sicherung nach dem Abschluss überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-173">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="1e8a8-174">**Vor dem Schreiben auf die Medien Prüfsumme bilden**, und optional **Bei Prüfsummenfehler fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-174">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="1e8a8-175">Weitere Informationen finden Sie unter [Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-175">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="1e8a8-176">Gehen Sie unter **Transaktionsprotokoll** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1e8a8-176">In the **Transaction log** section:</span></span>  
  
    -   <span data-ttu-id="1e8a8-177">Bei normalen Protokollsicherungen behalten Sie die Standardauswahl bei, also **Transaktionsprotokoll durch Entfernen inaktiver Einträge abschneiden**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-177">For routine log backups, keep the default selection, **Truncate the transaction log by removing inactive entries**.</span></span>  
  
    -   <span data-ttu-id="1e8a8-178">Soll das Protokollfragment gesichert werden (also das aktive Protokoll), aktivieren Sie die Option **Protokollfragment sichern und Datenbank im Wiederherstellungsstatus belassen**.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-178">To back up the tail of the log (that is, the active log), check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
         <span data-ttu-id="1e8a8-179">Eine Protokollfragmentsicherung wird angefertigt, wenn das Protokollfragment nicht gesichert werden konnte, um so einen Datenverlust zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-179">A tail-log backup is taken after a failure to back up the tail of the log in order to prevent work loss.</span></span> <span data-ttu-id="1e8a8-180">Sichern Sie das aktive Protokoll (Protokollfragmentsicherung) jeweils nach einem Fehler, vor dem Wiederherstellen der Datenbank oder beim Failover auf eine sekundäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-180">Back up the active log (a tail-log backup) both after a failure, before beginning to restore the database, or when failing over to a secondary database.</span></span> <span data-ttu-id="1e8a8-181">Wenn Sie diese Option auswählen, entspricht dies der Option NORECOVERY in der BACKUP LOG-Anweisung von Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-181">Selecting this option is equivalent to specifying the NORECOVERY option in the BACKUP LOG statement of Transact-SQL.</span></span> <span data-ttu-id="1e8a8-182">Weitere Informationen zu Sicherungen des Protokollfragments finden Sie unter [Protokollfragmentsicherungen &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-182">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
16. <span data-ttu-id="1e8a8-183">Wenn Sie auf ein Bandlaufwerk sichern (gemäß der Konfiguration im Abschnitt **Ziel** der Seite **Allgemein** ), ist die Option **Band nach dem Sichern entladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-183">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="1e8a8-184">Wenn Sie auf diese Option klicken, wird die Option **Band vor dem Entladen zurückspulen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-184">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
17. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="1e8a8-185">und höheren Versionen wird die [Sicherungskomprimierung](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-185">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="1e8a8-186">Ob eine Sicherung standardmäßig komprimiert wird, ist abhängig vom Wert der Serverkonfigurationsoption **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="1e8a8-186">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="1e8a8-187">Sie können jedoch unabhängig von der aktuellen Standardeinstellung auf Serverebene eine Sicherung komprimieren, indem Sie die Option **Sicherung komprimieren**aktivieren, oder die Komprimierung verhindern, indem Sie die Option **Sicherung nicht komprimieren**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-187">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="1e8a8-188">**So zeigen Sie die aktuelle Standardeinstellung für die Sicherungskomprimierung (Option "backup compression default") an**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-188">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="1e8a8-189">Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="1e8a8-189">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
 <span data-ttu-id="1e8a8-190">**Verschlüsselung**</span><span class="sxs-lookup"><span data-stu-id="1e8a8-190">**Encryption**</span></span>  
  
 <span data-ttu-id="1e8a8-191">Um die Sicherungsdatei zu verschlüsseln, aktivieren Sie das Kontrollkästchen **Sicherung verschlüsseln** .</span><span class="sxs-lookup"><span data-stu-id="1e8a8-191">To encrypt the backup file check the **Encrypt backup** check box.</span></span> <span data-ttu-id="1e8a8-192">Wählen Sie einen Verschlüsselungsalgorithmus aus, der zum Verschlüsseln der Sicherungsdatei verwendet werden soll, und geben Sie ein Zertifikat oder einen asymmetrischen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-192">Select an encryption algorithm to use for encrypting the backup file and provide a Certificate or Asymmetric key.</span></span> <span data-ttu-id="1e8a8-193">Folgende Algorithmen stehen für die Verschlüsselung zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="1e8a8-193">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="1e8a8-194">AES 128</span><span class="sxs-lookup"><span data-stu-id="1e8a8-194">AES 128</span></span>  
  
-   <span data-ttu-id="1e8a8-195">AES 192</span><span class="sxs-lookup"><span data-stu-id="1e8a8-195">AES 192</span></span>  
  
-   <span data-ttu-id="1e8a8-196">AES 256</span><span class="sxs-lookup"><span data-stu-id="1e8a8-196">AES 256</span></span>  
  
-   <span data-ttu-id="1e8a8-197">Triple DES</span><span class="sxs-lookup"><span data-stu-id="1e8a8-197">Triple DES</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1e8a8-198">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e8a8-198">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="1e8a8-199">So sichern Sie ein Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="1e8a8-199">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="1e8a8-200">Führen Sie die BACKUP LOG-Anweisung aus, um das Transaktionsprotokoll zu sichern, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="1e8a8-200">Execute the BACKUP LOG statement to back up the transaction log, specifying the following:</span></span>  
  
    -   <span data-ttu-id="1e8a8-201">Den Namen der Datenbank, zu der das zu sichernde Transaktionsprotokoll gehört.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-201">The name of the database to which the transaction log that you want to back up belongs.</span></span>  
  
    -   <span data-ttu-id="1e8a8-202">Das Sicherungsmedium, auf das die Transaktionsprotokollsicherung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-202">The backup device where the transaction log backup is written.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1e8a8-203">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1e8a8-203">Example (Transact-SQL)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e8a8-204">In diesem Beispiel wird die [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] -Datenbank verwendet, in der das einfache Wiederherstellungsmodell eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-204">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, which uses the simple recovery model.</span></span> <span data-ttu-id="1e8a8-205">Um Protokollsicherungen zu ermöglichen, wurde für die Datenbank vor dem Erstellen einer vollständigen Datenbanksicherung die Verwendung des vollständigen Wiederherstellungsmodells festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-205">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="1e8a8-206">Weitere Informationen finden Sie unter [Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-206">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="1e8a8-207">In diesem Beispiel wird eine Transaktionsprotokollsicherung für die [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] -Datenbank auf dem zuvor erstellten, benannten Sicherungsmedium `MyAdvWorks_FullRM_log1`erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-207">This example creates a transaction log backup for the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to the previously created named backup device, `MyAdvWorks_FullRM_log1`.</span></span>  
  
```sql  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1;  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1e8a8-208">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8a8-208">Using PowerShell</span></span>  
  
<span data-ttu-id="1e8a8-209">Verwenden Sie das `Backup-SqlDatabase`-Cmdlet, und geben Sie `Log` als Wert für den `-BackupAction`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-209">Use the `Backup-SqlDatabase` cmdlet and specify `Log` for the value of the `-BackupAction` parameter.</span></span>  
  
<span data-ttu-id="1e8a8-210">Im folgenden Beispiel wird eine Protokollsicherung der `MyDB` -Datenbank am standardmäßigen Sicherungsspeicherort der Serverinstanz `Computer\Instance`erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e8a8-210">The following example creates a log backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Log  
    ```  
  
<span data-ttu-id="1e8a8-211">Informationen zum Einrichten und Verwenden des SQL Server PowerShell Anbieters finden Sie unter [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1e8a8-211">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span></span>
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1e8a8-212">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1e8a8-212">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1e8a8-213">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8a8-213">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="1e8a8-214">Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8a8-214">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="1e8a8-215">Problembehandlung bei vollen Transaktionsprotokollen &#40;SQL Server-Fehler 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8a8-215">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e8a8-216">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e8a8-216">See Also</span></span>  
 <span data-ttu-id="1e8a8-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e8a8-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1e8a8-218">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e8a8-218">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1e8a8-219">[Wartungspläne](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="1e8a8-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="1e8a8-220">Vollständige Dateisicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e8a8-220">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
