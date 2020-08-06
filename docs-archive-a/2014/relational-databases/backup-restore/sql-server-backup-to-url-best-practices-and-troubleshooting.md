---
title: SQL Server-URL-Sicherung – bewährte Methoden und Problembehandlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619172"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a><span data-ttu-id="a7402-102">SQL Server-URL-Sicherung – bewährte Methoden und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a7402-102">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>
  <span data-ttu-id="a7402-103">In diesem Thema werden bewährte Methoden und Tipps zur Problembehandlung beschrieben, die sich auf SQL Server-Sicherungs- und Wiederherstellungsvorgänge im Azure Blob-Dienst beziehen.</span><span class="sxs-lookup"><span data-stu-id="a7402-103">This topic includes best practices and troubleshooting tips for SQL Server backup and restores to the Azure Blob service.</span></span>  
  
 <span data-ttu-id="a7402-104">Weitere Informationen zur Verwendung des Azure Blob Storage-Diensts für SQL Server-Sicherungs- oder -Wiederherstellungsvorgänge finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a7402-104">For more information about using Azure Blob storage service for SQL Server backup or restore operations, see:</span></span>  
  
-   [<span data-ttu-id="a7402-105">SQL Server-Sicherung und -Wiederherstellung mit dem Microsoft Azure Blob Storage Service</span><span class="sxs-lookup"><span data-stu-id="a7402-105">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [<span data-ttu-id="a7402-106">Tutorial: SQL Server-Sicherung und -Wiederherstellung mit dem Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="a7402-106">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a><span data-ttu-id="a7402-107">Verwalten von Sicherungen</span><span class="sxs-lookup"><span data-stu-id="a7402-107">Managing Backups</span></span>  
 <span data-ttu-id="a7402-108">Die folgende Liste enthält allgemeine Empfehlungen zur Verwaltung von Sicherungen:</span><span class="sxs-lookup"><span data-stu-id="a7402-108">The following list includes general recommendations to manage backups:</span></span>  
  
-   <span data-ttu-id="a7402-109">Für jede Sicherung sollte ein eindeutiger Dateiname verwendet werden, um zu verhindern, dass BLOBs versehentlich überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a7402-109">Unique file name for every backup is recommended to prevent accidentally overwriting the blobs.</span></span>  
  
-   <span data-ttu-id="a7402-110">Beim Erstellen eines Containers wird empfohlen, die Zugriffsebene auf **Privat**festzulegen, sodass der Lese- oder Schreibzugriff auf Blobs im Container nur Benutzern oder Konten mit den erforderlichen Authentifizierungsinformationen gestattet ist.</span><span class="sxs-lookup"><span data-stu-id="a7402-110">When creating a container, it is recommended that you set the access level to **private**, so only users or accounts that can provide the required authentication information can read or write the blobs in the container.</span></span>  
  
-   <span data-ttu-id="a7402-111">Verwenden Sie für SQL Server-Datenbanken in einer Instanz von SQL Server, die auf einem virtuellen Azure-Computer ausgeführt wird, ein Speicherkonto in derselben Region wie der virtuelle Computer, um Datenübertragungskosten zwischen Regionen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a7402-111">For SQL Server databases on an instance of SQL Server running in an Azure Virtual Machine, use a storage account in the same region as the virtual machine to avoid data transfer costs between regions.</span></span> <span data-ttu-id="a7402-112">Wenn Sie innerhalb einer Region bleiben, erzielen Sie darüber hinaus optimale Leistung bei Sicherungs- und Wiederherstellungsvorgängen.</span><span class="sxs-lookup"><span data-stu-id="a7402-112">Using the same region also ensures optimal performance for backup and restore operations.</span></span>  
  
-   <span data-ttu-id="a7402-113">Eine fehlerhafte Sicherungsaktivität kann dazu führen, dass eine Sicherungsdatei unbrauchbar wird.</span><span class="sxs-lookup"><span data-stu-id="a7402-113">Failed backup activity can result in an invalid backup file.</span></span> <span data-ttu-id="a7402-114">Es wird empfohlen, regelmäßig nach fehlerhaften Sicherungen zu suchen und die BLOB-Dateien zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a7402-114">We recommend periodic identification of failed backups and deleting the blob files.</span></span> <span data-ttu-id="a7402-115">Weitere Informationen hierzu finden Sie unter [Löschen von Sicherungsblobdateien aktiver Lease](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="a7402-115">For more information, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
-   <span data-ttu-id="a7402-116">Wenn Sie die Sicherung mit der `WITH COMPRESSION`-Option durchführen, können Sie die Speicherkosten und Speichertransaktionskosten minimieren.</span><span class="sxs-lookup"><span data-stu-id="a7402-116">Using the `WITH COMPRESSION` option during backup can minimize your storage costs and storage transaction costs.</span></span> <span data-ttu-id="a7402-117">Darüber hinaus verkürzt die Option die Dauer des Sicherungsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="a7402-117">It can also decrease the time taken to complete the backup process.</span></span>  
  
## <a name="handling-large-files"></a><span data-ttu-id="a7402-118">Behandlung großer Dateien</span><span class="sxs-lookup"><span data-stu-id="a7402-118">Handling Large Files</span></span>  
  
-   <span data-ttu-id="a7402-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherungsvorgänge verwenden mehrere Threads, um die Datenübertragung an die Azure Blob Storage-Dienste zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="a7402-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup operation uses multiple threads to optimize data transfer to Azure Blob storage services.</span></span>  <span data-ttu-id="a7402-120">Die Leistung hängt jedoch von verschiedenen Faktoren ab wie der Bandbreite des unabhängigen Softwareherstellers (ISV) und der Größe der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a7402-120">However the performance depends on various factors, such as ISV bandwidth and size of the database.</span></span> <span data-ttu-id="a7402-121">Wenn Sie beabsichtigen, große Datenbanken oder Dateigruppen von einer lokalen SQL Server-Datenbank zu sichern, sollten Sie zunächst den Durchsatz testen.</span><span class="sxs-lookup"><span data-stu-id="a7402-121">If you plan to back up large databases or filegroups from an on-premise SQL Server database, it is recommended that you do some throughput testing first.</span></span> <span data-ttu-id="a7402-122">[Die Azure Storage-SLA](https://go.microsoft.com/fwlink/?LinkId=271619) hat maximale Verarbeitungszeiten für BLOB, die Sie in Erwägung ziehen können.</span><span class="sxs-lookup"><span data-stu-id="a7402-122">[Azure storage SLA's](https://go.microsoft.com/fwlink/?LinkId=271619) have maximum processing times for blobs that you can take into consideration.</span></span>  
  
-   <span data-ttu-id="a7402-123">Die Verwendung der im Abschnitt **Verwalten von Sicherungen** empfohlenen `WITH COMPRESSION`-Option ist besonders beim Sichern umfangreicher Dateien von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="a7402-123">Using the `WITH COMPRESSION` option as recommended in the **Managing Backup** section, it is very important when backing up large files.</span></span>  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a><span data-ttu-id="a7402-124">Problembehandlung bei Sicherungs- oder Wiederherstellungsvorgängen über URLs</span><span class="sxs-lookup"><span data-stu-id="a7402-124">Troubleshooting Backup To or Restore from URL</span></span>  
 <span data-ttu-id="a7402-125">Im Folgenden finden Sie einige schnelle Lösungen zur Behandlung von Sicherungs- und Wiederherstellungsfehlern im Azure Blob Storage-Dienst.</span><span class="sxs-lookup"><span data-stu-id="a7402-125">Following are some quick ways to troubleshoot errors when backing up to or restoring from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="a7402-126">Um Fehler aufgrund von nicht unterstützten Optionen oder Einschränkungen zu vermeiden, überprüfen Sie die Liste der Einschränkungen und die Unterstützung für Sicherungs-und Wiederherstellungs Befehle im Artikel [SQL Server sichern und Wiederherstellen mit Azure BLOB Storage Dienst](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="a7402-126">To avoid errors due to unsupported options or limitations, review the list of limitations, and support for BACKUP and RESTORE commands information in the [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) article.</span></span>  
  
 <span data-ttu-id="a7402-127">**Authentifizierungsfehler:**</span><span class="sxs-lookup"><span data-stu-id="a7402-127">**Authentication Errors:**</span></span>  
  
-   <span data-ttu-id="a7402-128">WITH Credential ist eine neue Option, die zum Sichern oder Wiederherstellen aus dem Azure BLOB Storage-Dienst erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a7402-128">WITH CREDENTIAL is a new option and required to back up to or restore from the Azure Blob storage service.</span></span> <span data-ttu-id="a7402-129">In Zusammenhang mit Anmeldeinformationen können folgende Fehler auftreten:</span><span class="sxs-lookup"><span data-stu-id="a7402-129">Failures related to credential could be the following:</span></span>  
  
     <span data-ttu-id="a7402-130">Die im `BACKUP`-Befehl oder `RESTORE`-Befehl angegebenen Anmeldeinformationen sind nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a7402-130">The credential specified in the `BACKUP` or `RESTORE` command does not exist.</span></span> <span data-ttu-id="a7402-131">Um dieses Problem zu vermeiden, können Sie T-SQL-Anweisungen zum Erstellen von Anmeldeinformationen einschließen, falls in der BACKUP-Anweisung keine Anmeldeinformationen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a7402-131">To avoid this issue, you can include T-SQL statements to create the credential if one does not exist in the backup statement.</span></span> <span data-ttu-id="a7402-132">Beachten Sie das folgende Anwendungsbeispiel:</span><span class="sxs-lookup"><span data-stu-id="a7402-132">The following is an example you can use:</span></span>  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   <span data-ttu-id="a7402-133">Die Anmeldeinformationen sind zwar vorhanden, aber das Anmeldekonto zum Ausführen des Sicherungsbefehls verfügt über keine Berechtigung für den Zugriff auf die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="a7402-133">The credential exists but the login account that is used to run the backup command does not have permissions to access the credentials.</span></span> <span data-ttu-id="a7402-134">Verwenden Sie ein Anmeldekonto aus der **db_backupoperator** -Rolle mit Berechtigungen für **Beliebige Anmeldeinformationen ändern** .</span><span class="sxs-lookup"><span data-stu-id="a7402-134">Use a login account in the **db_backupoperator** role with **Alter any credential** permissions.</span></span>  
  
-   <span data-ttu-id="a7402-135">Überprüfen Sie den Namen des Speicherkontos und die Schlüsselwerte.</span><span class="sxs-lookup"><span data-stu-id="a7402-135">Verify the storage account name and key values.</span></span> <span data-ttu-id="a7402-136">Die in den Anmeldeinformationen gespeicherten Informationen müssen den Eigenschaftswerten Azure-Speicherkontos entsprechen, das Sie für Sicherungs- und Wiederherstellungsvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7402-136">The information stored in the credential must match the property values of the Azure storage account you are using in the backup and restore operations.</span></span>  
  
 <span data-ttu-id="a7402-137">**Sicherungsfehler:**</span><span class="sxs-lookup"><span data-stu-id="a7402-137">**Backup Errors/Failures:**</span></span>  
  
-   <span data-ttu-id="a7402-138">Parallele Sicherungen im selben Blob führen dazu, dass bei einer der Sicherungen die Meldung **Fehler beim Initialisieren** ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a7402-138">Parallel backups to the same blob cause one of the backups to fail with an **Initialization failed** error.</span></span>  
  
-   <span data-ttu-id="a7402-139">Verwenden Sie die folgenden Fehlerprotokolle, die Ihnen die Problembehandlung bei Sicherungsfehlern erleichtern:</span><span class="sxs-lookup"><span data-stu-id="a7402-139">Use the following error logs to help with troubleshooting backup errors:</span></span>  
  
    -   <span data-ttu-id="a7402-140">Legen Sie das Ablaufverfolgungsflag 3051 wie folgt fest, um die Protokollierung in einem bestimmten Fehlerprotokoll zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a7402-140">Set trace flag 3051 to turn on logging to a specific error log with the following format in:</span></span>  
  
         <span data-ttu-id="a7402-141">Backuptourl- \<instname> - \<dbname> -Action- \<PID> . log, wobei \<action> einer der folgenden ist:</span><span class="sxs-lookup"><span data-stu-id="a7402-141">BackupToUrl-\<instname>-\<dbname>-action-\<PID>.log Where \<action> is one of:</span></span>  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   <span data-ttu-id="a7402-142">Informationen finden Sie auch im Windows-Ereignisprotokoll unter Anwendungsprotokolle mit dem Namen "sqlbackuptourl".</span><span class="sxs-lookup"><span data-stu-id="a7402-142">You can also find information by reviewing the Windows Event Log - Under Application logs with the name 'SQLBackupToUrl'.</span></span>  
  
-   <span data-ttu-id="a7402-143">Bei der Wiederherstellung von einer komprimierten Sicherung kann eine Fehlermeldung mit etwa folgendem Wortlaut angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a7402-143">When restoring from a compressed backup, you might see the following error:</span></span>  
  
    -   <span data-ttu-id="a7402-144">**SqlException 3284 ist aufgetreten. Schweregrad: 16 Status: 5**</span><span class="sxs-lookup"><span data-stu-id="a7402-144">**SqlException 3284 occurred. Severity: 16 State: 5**</span></span>  
        <span data-ttu-id="a7402-145">**Die Nachrichten dateinmarkierung auf dem Gerät "" https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak ist nicht ausgerichtet. Wiederholen Sie die RESTORE-Anweisung mit derselben Blockgröße, die zum Erstellen des Sicherungs Aufruhrs verwendet wurde: "65536" sieht wie ein möglicher Wert aus.**</span><span class="sxs-lookup"><span data-stu-id="a7402-145">**Message Filemark on device 'https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak' is not aligned. Reissue the Restore statement with the same block size used to create the backupset: '65536' looks like a possible value.**</span></span>  
  
         <span data-ttu-id="a7402-146">Um diesen Fehler zu beheben, übergeben Sie die `BACKUP`-Anweisung erneut mit `BLOCKSIZE = 65536`.</span><span class="sxs-lookup"><span data-stu-id="a7402-146">To solve this error, reissue the `BACKUP` statement with `BLOCKSIZE = 65536` specified.</span></span>  
  
-   <span data-ttu-id="a7402-147">Fehler während der Sicherung aufgrund von Blobs mit aktiver Lease: Eine fehlerhafte Sicherungsaktivität kann zu Blobs mit aktiven Leases führen.</span><span class="sxs-lookup"><span data-stu-id="a7402-147">Error during backup due to blobs that have active lease on them: Failed backup activity can result in blobs with active leases.</span></span>  
  
     <span data-ttu-id="a7402-148">Wenn die BACKUP-Anweisung erneut ausgeführt wird, kann ein Sicherungsvorgang einen Fehler mit etwa folgendem Wortlaut verursachen:</span><span class="sxs-lookup"><span data-stu-id="a7402-148">If a backup statement is reattempted, backup operation might fail with an error similar to the following:</span></span>  
  
     <span data-ttu-id="a7402-149">**Bei einer URL-Sicherung wurde eine Ausnahme vom Remoteendpunkt empfangen. Ausnahmemeldung: Der Remoteserver hat einen Fehler zurückgegeben: (412) Derzeit weist das Blob eine Lease auf, obwohl in der Anforderung keine Lease-ID angegeben wurde**.</span><span class="sxs-lookup"><span data-stu-id="a7402-149">**Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (412) There is currently a lease on the blob and no lease ID was specified in the request**.</span></span>  
  
     <span data-ttu-id="a7402-150">Wenn versucht wird, eine RESTORE-Anweisung für eine BLOB-Sicherungsdatei mit aktiver Leasedauer auszuführen, wird eine Fehlermeldung mit etwa folgendem Wortlaut angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a7402-150">If a restore statement is attempted on a backup blob file that has an active lease, the restore operation fails with an error similar to the following:</span></span>  
  
     <span data-ttu-id="a7402-151">**Ausnahmemeldung: Der Remoteserver hat einen Fehler zurückgegeben: (409) Konflikt...**</span><span class="sxs-lookup"><span data-stu-id="a7402-151">**Exception Message: The remote server returned an error: (409) Conflict..**</span></span>  
  
     <span data-ttu-id="a7402-152">Wenn dieser Fehler auftritt, müssen die BLOB-Dateien gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a7402-152">When such error occurs, the blob files need to be deleted.</span></span> <span data-ttu-id="a7402-153">Weitere Informationen zu diesem Szenario und Lösungsvorschläge finden Sie unter [Löschen von Sicherungsblobdateien mit aktiver Lease](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="a7402-153">For more information on this scenario and how to correct this problem, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
## <a name="proxy-errors"></a><span data-ttu-id="a7402-154">Proxyfehler</span><span class="sxs-lookup"><span data-stu-id="a7402-154">Proxy Errors</span></span>  
 <span data-ttu-id="a7402-155">Wenn Sie über Proxyserver auf das Internet zugreifen, können folgende Probleme auftreten:</span><span class="sxs-lookup"><span data-stu-id="a7402-155">If you are using Proxy Servers to access the internet, you may see the following issues:</span></span>  
  
 <span data-ttu-id="a7402-156">**Durch Proxyserver gedrosselte Verbindungen:**</span><span class="sxs-lookup"><span data-stu-id="a7402-156">**Connection throttling by Proxy Servers:**</span></span>  
  
 <span data-ttu-id="a7402-157">Proxyserver können über Einstellungen verfügen, die die Anzahl der Verbindungen pro Minute begrenzen.</span><span class="sxs-lookup"><span data-stu-id="a7402-157">Proxy Servers can have settings that limit the number of connections per minute.</span></span> <span data-ttu-id="a7402-158">Der URL-Sicherungsprozess ist ein Multithreadprozess und kann diese Begrenzung folglich überschreiten.</span><span class="sxs-lookup"><span data-stu-id="a7402-158">The Backup to URL process is a multi-threaded process and hence can go over this limit.</span></span> <span data-ttu-id="a7402-159">In diesem Fall wird die Verbindung vom Proxyserver abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a7402-159">If this happens, the proxy server kills the connection.</span></span> <span data-ttu-id="a7402-160">Um das Problem zu beheben, ändern Sie die Proxyeinstellungen, damit der Proxy von SQL Server nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7402-160">To resolve this issue, change the proxy settings so SQL Server is not using the proxy.</span></span>   <span data-ttu-id="a7402-161">Im Folgenden einige Beispiele für Fehlertypen oder -meldungen, die im Fehlerprotokoll angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="a7402-161">Following are some examples of the types or error messages you may see in the error log:</span></span>  
  
-   <span data-ttu-id="a7402-162">Fehler beim Schreiben in " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ": bei der URL-Sicherung wurde eine Ausnahme vom Remote Endpunkt empfangen.</span><span class="sxs-lookup"><span data-stu-id="a7402-162">Write on "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak" failed: Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="a7402-163">Ausnahmemeldung: Von der Übertragungsverbindung können keine Daten gelesen werden: Die Verbindung wurde geschlossen.</span><span class="sxs-lookup"><span data-stu-id="a7402-163">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
-   <span data-ttu-id="a7402-164">Nicht behebbarer E/A-Fehler für die Datei http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: Error could not be gathered from Remote Endpoint. (Fehler konnte am Endpunkt nicht erfasst werden.)</span><span class="sxs-lookup"><span data-stu-id="a7402-164">A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Error could not be gathered from Remote Endpoint.</span></span>  
  
     <span data-ttu-id="a7402-165">Meldung 3013, Ebene 16, Status 1, Zeile 2</span><span class="sxs-lookup"><span data-stu-id="a7402-165">Msg 3013, Level 16, State 1, Line 2</span></span>  
  
     <span data-ttu-id="a7402-166">BACKUP DATABASE wird fehlerbedingt beendet.</span><span class="sxs-lookup"><span data-stu-id="a7402-166">BACKUP DATABASE is terminating abnormally.</span></span>  
  
-   <span data-ttu-id="a7402-167">Backupiorequest:: reportioerror: Schreibfehler auf dem Sicherungsmedium " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ".</span><span class="sxs-lookup"><span data-stu-id="a7402-167">BackupIoRequest::ReportIoError: write failure on backup device 'http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak'.</span></span> <span data-ttu-id="a7402-168">Betriebssystemfehler: Bei einer URL-Sicherung wurde eine Ausnahme vom Remoteendpunkt empfangen.</span><span class="sxs-lookup"><span data-stu-id="a7402-168">Operating system error Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="a7402-169">Ausnahmemeldung: Von der Übertragungsverbindung können keine Daten gelesen werden: Die Verbindung wurde geschlossen.</span><span class="sxs-lookup"><span data-stu-id="a7402-169">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
 <span data-ttu-id="a7402-170">Wenn Sie die ausführliche Protokollierung mit Ablaufverfolgungsflag 3051 aktivieren, können auch folgende Meldungen in den Protokollen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a7402-170">If you turn on the verbose logging using the trace flag 3051 you may also see the following message in the logs:</span></span>  
  
 <span data-ttu-id="a7402-171">HTTP-Statuscode 502, HTTP-Statusmeldung: Proxyfehler (Die Anzahl der HTTP-Anforderungen pro Minute hat das konfigurierte Limit überschritten.</span><span class="sxs-lookup"><span data-stu-id="a7402-171">HTTP status code 502, HTTP Status Message Proxy Error ( The number of HTTP requests per minute exceeded the configured limit.</span></span> <span data-ttu-id="a7402-172">Wenden Sie sich an Ihren ISA Server-Administrator.</span><span class="sxs-lookup"><span data-stu-id="a7402-172">Contact your ISA Server administrator.</span></span>  <span data-ttu-id="a7402-173">)</span><span class="sxs-lookup"><span data-stu-id="a7402-173">)</span></span>  
  
 <span data-ttu-id="a7402-174">**Standardproxyeinstellungen wurden nicht abgerufen:**</span><span class="sxs-lookup"><span data-stu-id="a7402-174">**Default Proxy Settings not picked up:**</span></span>  
  
 <span data-ttu-id="a7402-175">In manchen Fällen werden die Standardeinstellungen nicht abgerufen, wodurch Proxy Authentifizierungsfehler wie die unten gezeigte verursacht werden:*ein nicht BEHEB barer e/a-Fehler für die Datei " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: " bei der URL-Sicherung wurde eine Ausnahme vom Remote Endpunkt empfangen. Ausnahme Meldung: der Remote Server hat einen Fehler zurückgegeben: (407)* **Proxy Authentifizierung erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="a7402-175">Sometimes the default settings are not picked up causing proxy authentication errors such as the one shown below:*A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (407)* **Proxy Authentication Required**.</span></span>  
  
 <span data-ttu-id="a7402-176">Um dieses Problem zu beheben, erstellen Sie mithilfe folgender Schritte eine Konfigurationsdatei, durch die beim URL-Sicherungsprozess die Standardproxyeinstellungen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="a7402-176">To resolve this issue, create a configuration file that allows the Backup to URL process to use the default proxy settings using the following steps:</span></span>  
  
1.  <span data-ttu-id="a7402-177">Erstellen Sie eine Konfigurationsdatei mit dem Namen BackuptoURL.exe.config und folgender XML:</span><span class="sxs-lookup"><span data-stu-id="a7402-177">Create a configuration file named BackuptoURL.exe.config  with the following xml:</span></span>  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  <span data-ttu-id="a7402-178">Speichern Sie die Konfigurationsdatei im Ordner Binn der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="a7402-178">Place the configuration file in the Binn folder of the SQL Server Instance.</span></span> <span data-ttu-id="a7402-179">Wenn z. b. meine SQL Server auf dem Laufwerk C des Computers installiert ist, platzieren Sie die Konfigurationsdatei hier: *c:\Programme\Microsoft SQL server\mssql12. \<InstanceName> \MSSQL\Binn*.</span><span class="sxs-lookup"><span data-stu-id="a7402-179">For example, if my SQL Server is installed on the C drive of the machine, place the configuration file here: *C:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Binn*.</span></span>  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a><span data-ttu-id="a7402-180">Problembehandlung für die verwaltete SQL Server-Sicherung in Azure</span><span class="sxs-lookup"><span data-stu-id="a7402-180">Troubleshooting SQL Server Managed Backup to Azure</span></span>  
 <span data-ttu-id="a7402-181">Da SQL Server Managed Backup auf der URL-Sicherung aufbaut, gelten die in den vorherigen Abschnitten aufgeführten Tipps zur Fehlerbehebung für Datenbanken oder Instanzen, für die SQL Server Managed Backup verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7402-181">Since SQL Server Managed Backup is built on top of Backup to URL, the troubleshooting tips described in the earlier sections apply to databases or instances using SQL Server Managed Backup.</span></span>  <span data-ttu-id="a7402-182">Informationen zur Problembehandlung SQL Server verwalteten Sicherung in Azure finden Sie unter [Problembehandlung SQL Server verwaltete Sicherung in Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="a7402-182">Information about troubleshooting SQL Server Managed Backup to Azure is described in detail in [Troubleshooting SQL Server Managed  Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7402-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7402-183">See Also</span></span>  
 [<span data-ttu-id="a7402-184">Wiederherstellen aus in Azure gespeicherten Sicherungen</span><span class="sxs-lookup"><span data-stu-id="a7402-184">Restoring From Backups Stored in Azure</span></span>](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  
