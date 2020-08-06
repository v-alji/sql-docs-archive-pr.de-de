---
title: Task 'Datenbank sichern' (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.backup.f1
- sql12.swb.maint.maintplanproperties.logbackup.f1
helpviewer_keywords:
- Back Up Database Task dialog box
ms.assetid: ed1ef012-fa14-4ba5-bafe-d1527ba065b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 952730f09deeede360dff5e2bd83f8cdc8a20a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616522"
---
# <a name="back-up-database-task-maintenance-plan"></a><span data-ttu-id="b58e5-102">Task 'Datenbank sichern' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="b58e5-102">Back Up Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="b58e5-103">Mithilfe des Dialogfelds **Task 'Datenbank sichern'** können Sie dem Wartungsplan einen Sicherungstask hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-103">Use the **Back Up Database Task** dialog to add a backup task to the maintenance plan.</span></span> <span data-ttu-id="b58e5-104">Eine Sicherung der Datenbank ist für den Fall wichtig, dass die Datenbank bei einem System- oder Hardwareausfall (oder einem Benutzerfehler) beschädigt wird. In diesem Fall muss eine Sicherungskopie wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b58e5-104">Backing up the database is important in case of system or hardware failure (or user errors) that cause the database to be damaged in some way, thus requiring a backed-up copy to be restored.</span></span> <span data-ttu-id="b58e5-105">Dieser Task ermöglicht vollständige und differenzielle Sicherungen sowie Sicherungen von Dateien, Dateigruppen und Transaktionsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-105">This task allows you to perform full, differential, files and filegroups, and transaction log backups.</span></span>  
  
 <span data-ttu-id="b58e5-106">**So erstellen Sie einen Datenbanksicherungstask**</span><span class="sxs-lookup"><span data-stu-id="b58e5-106">**To create a backup database task**</span></span>  
  
-   [<span data-ttu-id="b58e5-107">Erstellen eines Wartungsplans</span><span class="sxs-lookup"><span data-stu-id="b58e5-107">Create a Maintenance Plan</span></span>](create-a-maintenance-plan.md)  
  
## <a name="options"></a><span data-ttu-id="b58e5-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b58e5-108">Options</span></span>  
 <span data-ttu-id="b58e5-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="b58e5-109">**Connection**</span></span>  
 <span data-ttu-id="b58e5-110">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58e5-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="b58e5-111">**Neu**</span><span class="sxs-lookup"><span data-stu-id="b58e5-111">**New**</span></span>  
 <span data-ttu-id="b58e5-112">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58e5-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="b58e5-113">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b58e5-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="b58e5-114">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="b58e5-114">**Databases**</span></span>  
 <span data-ttu-id="b58e5-115">Gibt die Datenbanken an, die von dieser Aufgabe betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="b58e5-115">Specify the databases affected by this task.</span></span> <span data-ttu-id="b58e5-116">Wenn diese Option ausgewählt ist, enthält die Dropdownliste die folgenden Optionen: **Alle Datenbanken**, **Alle Systemdatenbanken**, **Alle Benutzerdatenbanken**, **Diese Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="b58e5-116">When selected, the drop down list provides the following options: **All databases**, **All system databases**, **All user databases**, **These specific databases**.</span></span>  
  
 <span data-ttu-id="b58e5-117">**Alle Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="b58e5-117">**All databases**</span></span>  
 <span data-ttu-id="b58e5-118">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-118">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="b58e5-119">**Alle Systemdatenbanken ('master', 'msdb', 'model')**</span><span class="sxs-lookup"><span data-stu-id="b58e5-119">**All system databases (master, msdb, model)**</span></span>  
 <span data-ttu-id="b58e5-120">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-120">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span> <span data-ttu-id="b58e5-121">Für benutzerdefinierte Datenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-121">No maintenance tasks are run against user-created databases.</span></span>  
  
 <span data-ttu-id="b58e5-122">**Alle Benutzerdatenbanken (außer 'master', 'model', 'msdb', 'tempdb')**</span><span class="sxs-lookup"><span data-stu-id="b58e5-122">**All user databases (excluding master, model, msdb, tempdb)**</span></span>  
 <span data-ttu-id="b58e5-123">Generiert einen Wartungsplan, der Wartungstasks für alle benutzerdefinierten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-123">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="b58e5-124">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-124">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
 <span data-ttu-id="b58e5-125">**Diese Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="b58e5-125">**These databases**</span></span>  
 <span data-ttu-id="b58e5-126">Generiert einen Wartungsplan, der Wartungstasks nur für die ausgewählten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-126">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="b58e5-127">Wenn diese Option ausgewählt wird, muss mindestens eine Datenbank in der Liste ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="b58e5-127">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="b58e5-128">**Sicherungstyp**</span><span class="sxs-lookup"><span data-stu-id="b58e5-128">**Backup type**</span></span>  
 <span data-ttu-id="b58e5-129">Zeigt den Typ der Sicherung an, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58e5-129">Shows the type of backup to be performed.</span></span>  
  
 <span data-ttu-id="b58e5-130">**Sicherungskomponente**</span><span class="sxs-lookup"><span data-stu-id="b58e5-130">**Backup component**</span></span>  
 <span data-ttu-id="b58e5-131">Wählen Sie **Datenbank** aus, um die gesamte Datenbank zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b58e5-131">Select **Database** to back up the entire database.</span></span> <span data-ttu-id="b58e5-132">Wählen Sie **Datei und Dateigruppen** aus, um nur einen Teil der Datenbank zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b58e5-132">Select **File and filegroups** to back up only a portion of the database.</span></span> <span data-ttu-id="b58e5-133">Bei Auswahl dieser Option müssen Sie die Datei bzw. Dateigruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="b58e5-133">If selected, provide the file or filegroup name.</span></span> <span data-ttu-id="b58e5-134">Wenn im Feld **Datenbanken** mehrere Datenbanken ausgewählt wurden, geben Sie für die **Sicherungskomponenten** nur **Datenbanken**an.</span><span class="sxs-lookup"><span data-stu-id="b58e5-134">When multiple databases are selected in the **Databases** box, only specify **Databases** for the **Backup components**.</span></span> <span data-ttu-id="b58e5-135">Erstellen Sie einen Task für jede Datenbank, um Datei- oder Dateigruppensicherungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-135">To perform file or filegroup backups, create a task for each database.</span></span>  
  
 <span data-ttu-id="b58e5-136">**Sicherungssatz läuft ab**</span><span class="sxs-lookup"><span data-stu-id="b58e5-136">**Backup set will expire**</span></span>  
 <span data-ttu-id="b58e5-137">Geben Sie an, wann der Sicherungssatz durch einen anderen Sicherungssatz überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b58e5-137">Specify when the backup set can be overwritten by another backup set.</span></span>  
  
 <span data-ttu-id="b58e5-138">**Sichern auf**</span><span class="sxs-lookup"><span data-stu-id="b58e5-138">**Back up to**</span></span>  
 <span data-ttu-id="b58e5-139">Sichert die Datenbank in einer Datei oder auf einem Band.</span><span class="sxs-lookup"><span data-stu-id="b58e5-139">Back up the database to a file or to tape.</span></span> <span data-ttu-id="b58e5-140">Es stehen nur Bandmedien zur Verfügung, die an den Computer mit der Datenbank angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="b58e5-140">Only tape devices attached to the computer containing the database are available.</span></span>  
  
 <span data-ttu-id="b58e5-141">**Datenbanken in einer oder in mehreren Dateien sichern**</span><span class="sxs-lookup"><span data-stu-id="b58e5-141">**Back up databases across one or more files**</span></span>  
 <span data-ttu-id="b58e5-142">Klicken Sie auf **Hinzufügen** , um das Dialogfeld **Sicherungsziel auswählen** zu öffnen, und geben Sie einen oder mehrere Datenträgerspeicherorte oder Bandgeräte an.</span><span class="sxs-lookup"><span data-stu-id="b58e5-142">Click **Add** to open the **Select Backup Destination** dialog box, and provide one or more a disk location, or tape device.</span></span>  
  
 <span data-ttu-id="b58e5-143">**Wenn Sicherungsdateien vorhanden sind**</span><span class="sxs-lookup"><span data-stu-id="b58e5-143">**If backup files exist**</span></span>  
 <span data-ttu-id="b58e5-144">Wählen Sie **Anfügen** , um diese Sicherung an das Ende der Datei anzufügen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-144">Select **Append** to add this backup to the end of the file.</span></span> <span data-ttu-id="b58e5-145">Wählen Sie **Überschreiben**aus, um alle alten Sicherungen in der Datei zu entfernen und sie mit der neuen Sicherung zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-145">Select **Overwrite**, to remove any old backup in the file and replace them with this new backup.</span></span>  
  
 <span data-ttu-id="b58e5-146">**Für jede Datenbank eine Sicherungsdatei erstellen**</span><span class="sxs-lookup"><span data-stu-id="b58e5-146">**Create a backup file for every database**</span></span>  
 <span data-ttu-id="b58e5-147">Erstellt eine Sicherungsdatei an dem im Feld für den Ordner angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b58e5-147">Create a backup file in the location specified in the folder box.</span></span> <span data-ttu-id="b58e5-148">Für jede ausgewählte Datenbank wird eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-148">One file will be created for each database selected.</span></span>  
  
 <span data-ttu-id="b58e5-149">**Unterverzeichnis für jede Datenbank erstellen**</span><span class="sxs-lookup"><span data-stu-id="b58e5-149">**Create a sub-directory for each database**</span></span>  
 <span data-ttu-id="b58e5-150">Wählen Sie diese Option aus, um alle Datenbanksicherungsdateien in einem Unterordner zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b58e5-150">Select to place each database in a subfolder.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b58e5-151">Obwohl Unterverzeichnisse von Wartungsplänen erstellt werden können, können Unterverzeichnisse in Wartungstasks nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b58e5-151">Although maintenance plans can create subdirectories, maintenance tasks cannot delete subdirectories.</span></span> <span data-ttu-id="b58e5-152">Diese Funktion reduziert die Möglichkeit eines bösartigen Angriffs, der den Task Wartungscleanup zum Löschen von Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="b58e5-152">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b58e5-153">Das Unterverzeichnis erbt Berechtigungen vom übergeordneten Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b58e5-153">The subdirectory inherits permissions from the parent directory.</span></span> <span data-ttu-id="b58e5-154">Schränken Sie die Berechtigungen ein, um einen nicht autorisierten Zugriff zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b58e5-154">Restrict permissions to avoid unauthorized access.</span></span>  
  
 <span data-ttu-id="b58e5-155">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="b58e5-155">**Folder**</span></span>  
 <span data-ttu-id="b58e5-156">Gibt den Ordner an, in dem die automatisch erstellten Datenbankdateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-156">Specify the folder to contain the automatically created database files.</span></span>  
  
 <span data-ttu-id="b58e5-157">**Sicherungsdateierweiterung**</span><span class="sxs-lookup"><span data-stu-id="b58e5-157">**Backup file extension**</span></span>  
 <span data-ttu-id="b58e5-158">Gibt die Dateierweiterung an, die für Sicherungsdateien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b58e5-158">Specify the extension to use for the backup files.</span></span> <span data-ttu-id="b58e5-159">Der Standardwert ist **.bak**.</span><span class="sxs-lookup"><span data-stu-id="b58e5-159">The default is **.bak**.</span></span>  
  
 <span data-ttu-id="b58e5-160">**Sicherungsintegrität überprüfen**</span><span class="sxs-lookup"><span data-stu-id="b58e5-160">**Verify backup integrity**</span></span>  
 <span data-ttu-id="b58e5-161">Überprüft, ob der Sicherungssatz vollständig ist und alle Volumes lesbar sind.</span><span class="sxs-lookup"><span data-stu-id="b58e5-161">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="b58e5-162">**Protokollfragment sichern und Datenbank im Wiederherstellungsstatus belassen**</span><span class="sxs-lookup"><span data-stu-id="b58e5-162">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="b58e5-163">Führen Sie eine Protokollsicherung als letzten Schritt vor dem Wiederherstellen einer Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="b58e5-163">Perform a log backup as the last step before restoring a database.</span></span> <span data-ttu-id="b58e5-164">Weitere Informationen finden Sie unter [Protokollfragmentsicherungen &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b58e5-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="b58e5-165">**Sicherungskomprimierung festlegen**</span><span class="sxs-lookup"><span data-stu-id="b58e5-165">**Set backup compression**</span></span>  
 <span data-ttu-id="b58e5-166">Wählen Sie in [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (oder höher) einen der folgenden Werte für die [Sicherungskomprimierung](../backup-restore/backup-compression-sql-server.md) aus:</span><span class="sxs-lookup"><span data-stu-id="b58e5-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (or a later version), select one the following [backup compression](../backup-restore/backup-compression-sql-server.md) values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b58e5-167">**Standardservereinstellungen verwenden**</span><span class="sxs-lookup"><span data-stu-id="b58e5-167">**Use the default server setting**</span></span>|<span data-ttu-id="b58e5-168">Klicken Sie hier, um die Standardeinstellung auf Serverebene zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b58e5-168">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="b58e5-169">Diese Standardeinstellung wird durch die Serverkonfigurationsoption **Komprimierungsstandard für Sicherung** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b58e5-169">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="b58e5-170">Informationen zum Anzeigen der aktuellen Einstellung dieser Option finden Sie unter [Anzeigen oder Konfigurieren der Serverkonfigurationsoption „Standardeinstellung für die Sicherungskomprimierung“](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b58e5-170">For information about how to view the current setting of this option,  see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="b58e5-171">**Sicherung komprimieren**</span><span class="sxs-lookup"><span data-stu-id="b58e5-171">**Compress backup**</span></span>|<span data-ttu-id="b58e5-172">Klicken Sie hier, um die Sicherung unabhängig von der Standardeinstellung auf Serverebene zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="b58e5-172">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="b58e5-173">**\*\* Wichtig \*\*** Standardmäßig steigt die CPU-Nutzung durch die Komprimierung erheblich, und die bei der Komprimierung zusätzlich verbrauchten CPU-Ressourcen können sich negativ auf gleichzeitige Vorgänge auswirken.</span><span class="sxs-lookup"><span data-stu-id="b58e5-173">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely affect concurrent operations.</span></span> <span data-ttu-id="b58e5-174">Daher ist es u. U. sinnvoll, in einer Sitzung, bei der die CPU-Nutzung durch die [Ressourcenkontrolle](../resource-governor/resource-governor.md) eingeschränkt ist, komprimierte Sicherungen mit niedriger Priorität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-174">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="b58e5-175">Weitere Informationen finden Sie unter [Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b58e5-175">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="b58e5-176">**Sicherung nicht komprimieren**</span><span class="sxs-lookup"><span data-stu-id="b58e5-176">**Do not compress backup**</span></span>|<span data-ttu-id="b58e5-177">Klicken Sie hier, um unabhängig von der Standardeinstellung auf Serverebene eine nicht komprimierte Sicherung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-177">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
 <span data-ttu-id="b58e5-178">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="b58e5-178">**View T-SQL**</span></span>  
 <span data-ttu-id="b58e5-179">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b58e5-179">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b58e5-180">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="b58e5-180">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="b58e5-181">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="b58e5-181">New Connection Dialog Box</span></span>  
 <span data-ttu-id="b58e5-182">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="b58e5-182">**Connection name**</span></span>  
 <span data-ttu-id="b58e5-183">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="b58e5-183">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="b58e5-184">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="b58e5-184">**Select or enter a server name**</span></span>  
 <span data-ttu-id="b58e5-185">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58e5-185">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="b58e5-186">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="b58e5-186">**Refresh**</span></span>  
 <span data-ttu-id="b58e5-187">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="b58e5-187">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="b58e5-188">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="b58e5-188">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="b58e5-189">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="b58e5-189">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="b58e5-190">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="b58e5-190">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="b58e5-191">Stellt mithilfe der Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="b58e5-191">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="b58e5-192">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="b58e5-192">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="b58e5-193">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="b58e5-193">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="b58e5-194">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b58e5-194">This option is not available.</span></span>  
  
 <span data-ttu-id="b58e5-195">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="b58e5-195">**User name**</span></span>  
 <span data-ttu-id="b58e5-196">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="b58e5-196">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="b58e5-197">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b58e5-197">This option is not available.</span></span>  
  
 <span data-ttu-id="b58e5-198">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="b58e5-198">**Password**</span></span>  
 <span data-ttu-id="b58e5-199">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="b58e5-199">Provide a password to use when authenticating.</span></span> <span data-ttu-id="b58e5-200">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b58e5-200">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58e5-201">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b58e5-201">See Also</span></span>  
 [<span data-ttu-id="b58e5-202">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b58e5-202">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  
  
