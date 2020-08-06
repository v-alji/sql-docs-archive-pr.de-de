---
title: Löschen von BLOB-Sicherungsdateien mit aktiver Lease | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 13a8f879-274f-4934-a722-b4677fc9a782
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02aea910589633a5c3ec79e283c757727b4d92cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617136"
---
# <a name="deleting-backup-blob-files-with-active-leases"></a><span data-ttu-id="69468-102">Löschen von BLOB-Sicherungsdateien mit aktiver Lease</span><span class="sxs-lookup"><span data-stu-id="69468-102">Deleting Backup Blob Files with Active Leases</span></span>
  <span data-ttu-id="69468-103">Beim Sichern oder Wiederherstellen von Azure Storage erhält SQL Server eine unbegrenzte Lease, um exklusiven Zugriff auf das BLOB zu sperren.</span><span class="sxs-lookup"><span data-stu-id="69468-103">When backing up to or restoring from Azure storage, SQL Server acquires an infinite lease in order to lock exclusive access to the blob.</span></span> <span data-ttu-id="69468-104">Nachdem die Sicherung oder Wiederherstellung erfolgreich abgeschlossen wurde, wird die Lease wieder freigegeben.</span><span class="sxs-lookup"><span data-stu-id="69468-104">When the backup or restore process is successfully completed, the lease is released.</span></span> <span data-ttu-id="69468-105">Wenn eine Sicherung oder Wiederherstellung fehlschlägt, wird im Rahmen des Sicherungsvorgangs versucht, ungültige BLOBs zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="69468-105">If a backup or restore fails, the backup process attempts to clean up any invalid blob.</span></span> <span data-ttu-id="69468-106">Kann die Sicherung jedoch aufgrund eines längeren bzw. dauerhaften Netzwerkverbindungsfehlers nicht ausgeführt werden, ist der Sicherungsvorgang u. U. nicht in der Lage, auf das BLOB zuzugreifen, sodass das BLOB verwaist ist.</span><span class="sxs-lookup"><span data-stu-id="69468-106">However, if the backup fails due to prolonged or sustained network connectivity failure, the backup  process may not be able gain access to the blob and the blob may remain orphaned.</span></span> <span data-ttu-id="69468-107">Dies bedeutet, dass das BLOB erst wieder beschreibbar ist bzw. gelöscht werden kann, nachdem die Lease freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="69468-107">This means that the blob cannot be written to or deleted until the lease is released.</span></span> <span data-ttu-id="69468-108">In diesem Thema wird beschrieben, wie die Lease freigegeben und das BLOB gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="69468-108">This topic describes how to release the lease and deleting the blob..</span></span>  
  
 <span data-ttu-id="69468-109">Weitere Informationen zu Leasetypen finden Sie in diesem [Artikel](https://go.microsoft.com/fwlink/?LinkId=275664).</span><span class="sxs-lookup"><span data-stu-id="69468-109">For more information on the types of leases, read this [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span></span>  
  
 <span data-ttu-id="69468-110">Ist der Sicherungsvorgang fehlerhaft, kann eine ungültige Sicherungsdatei generiert werden.</span><span class="sxs-lookup"><span data-stu-id="69468-110">If the backup operation fails, it can result in a backup file that is not valid.</span></span>  <span data-ttu-id="69468-111">Außerdem kann für die BLOB-Sicherungsdatei eine aktive Lease bestehen, die verhindert, dass sie gelöscht oder überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="69468-111">The backup blob file might also have an active lease, preventing it from being deleted or overwritten.</span></span>  <span data-ttu-id="69468-112">Um derartige BLOBs zu löschen oder zu überschreiben, sollte die Lease zuerst unterbrochen werden. Bei Sicherungsfehlern empfiehlt es sich, Leases zu bereinigen und BLOBs zu löschen.</span><span class="sxs-lookup"><span data-stu-id="69468-112">In order to delete or overwrite such blobs, the lease should first be broken.If there are backup failures, we recommend that you clean up leases and delete blobs.</span></span> <span data-ttu-id="69468-113">Sie können im Rahmen der Speicherverwaltung auch regelmäßige Cleanups ausführen.</span><span class="sxs-lookup"><span data-stu-id="69468-113">You can also choose cleanup periodically as part of storage management tasks.</span></span>  
  
 <span data-ttu-id="69468-114">Da bei einem Wiederherstellungsfehler nachfolgende Wiederherstellungen nicht blockiert werden, stellt eine aktive Lease u. U. kein Problem dar.</span><span class="sxs-lookup"><span data-stu-id="69468-114">If there is a restore failure, subsequent restores are not blocked, and therefore the active lease may not be an issue.</span></span> <span data-ttu-id="69468-115">Die Unterbrechung der Lease ist nur erforderlich, wenn das BLOB überschrieben oder gelöscht werden muss.</span><span class="sxs-lookup"><span data-stu-id="69468-115">Breaking the lease is only necessary when you have to overwrite or delete the blob.</span></span>  
  
## <a name="managing-orphaned-blobs"></a><span data-ttu-id="69468-116">Verwalten verwaister BLOBs</span><span class="sxs-lookup"><span data-stu-id="69468-116">Managing Orphaned Blobs</span></span>  
 <span data-ttu-id="69468-117">In den folgenden Schritten wird beschrieben, wie nach einem fehlerhaften Sicherungs- oder Wiederherstellungsvorgang ein Cleanup ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69468-117">The follow steps describe how to clean up after failed backup or restore activity.</span></span> <span data-ttu-id="69468-118">Sämtliche Schritte können mithilfe von PowerShell-Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69468-118">All the steps can be done using PowerShell scripts.</span></span> <span data-ttu-id="69468-119">Im folgenden Abschnitt finden Sie ein Codebeispiel:</span><span class="sxs-lookup"><span data-stu-id="69468-119">A code example is provided in the following section:</span></span>  
  
1.  <span data-ttu-id="69468-120">**Ermitteln von BLOBs, die über Leases verfügen:** Falls Sie über ein Skript oder einen Prozess zum Ausführen der Sicherungsvorgänge verfügen, können Sie den Fehler möglicherweise innerhalb des Skripts oder Prozesses ermitteln und die BLOBs entsprechend bereinigen.</span><span class="sxs-lookup"><span data-stu-id="69468-120">**Identifying blobs that have leases:** If you have a script or a process that runs the backup processes, you might be able to capture the failure within the script or process and use that to clean up the blobs.</span></span>   <span data-ttu-id="69468-121">Sie können die BLOBs mit aktiven Leases auch mithilfe der LeaseStats-Eigenschaft und LeastState-Eigenschaft identifizieren.</span><span class="sxs-lookup"><span data-stu-id="69468-121">You can also use the LeaseStats and LeastState properties to identify the blobs that have leases on them.</span></span> <span data-ttu-id="69468-122">Nachdem Sie die BLOBs identifiziert haben, sollten Sie die Liste überprüfen, sicherstellen, dass die Sicherungsdatei gültig ist, und erst dann das BLOB löschen.</span><span class="sxs-lookup"><span data-stu-id="69468-122">Once you have identified the blobs, we recommend that you review the list, verify the validity of the backup file before deleting the blob.</span></span>  
  
2.  <span data-ttu-id="69468-123">**Unterbrechen der Lease:** Durch eine autorisierte Anforderung kann die Lease ohne Angabe einer Lease-ID unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="69468-123">**Breaking the lease:** An authorized request can break the lease without supplying a lease ID.</span></span> <span data-ttu-id="69468-124">Weitere Informationen finden Sie [hier](https://go.microsoft.com/fwlink/?LinkID=275664) .</span><span class="sxs-lookup"><span data-stu-id="69468-124">See [here](https://go.microsoft.com/fwlink/?LinkID=275664) for more information.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="69468-125">SQL Server gibt eine Lease-ID aus, um während des Wiederherstellungsvorgangs einen exklusiven Zugriff zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="69468-125">SQL Server issues a lease ID to establish exclusive access during the restore operation.</span></span> <span data-ttu-id="69468-126">Die ID für die Wiederherstellungslease lautet BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span><span class="sxs-lookup"><span data-stu-id="69468-126">The restore lease ID is BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span></span>  
  
3.  <span data-ttu-id="69468-127">**Löschen des BLOBs:** Um ein BLOB zu löschen, das über eine aktive Lease verfügt, müssen Sie zunächst die Lease unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="69468-127">**Deleting the Blob:** To delete a blob that has an active lease, you must first break the lease.</span></span>  
  
###  <a name="powershell-script-example"></a><a name="Code_Example"></a><span data-ttu-id="69468-128">Beispiel für ein PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="69468-128">PowerShell Script Example</span></span>  
 <span data-ttu-id="69468-129">Wichtig Wenn Sie PowerShell 2,0 ausführen, haben Sie möglicherweise Probleme beim Laden der Microsoft WindowsAzure.Storage.dll-Assembly. \*\* \* \* \* \* \*\*</span><span class="sxs-lookup"><span data-stu-id="69468-129">**\*\* Important \*\*** If you are running PowerShell 2.0, you may have problems loading the Microsoft WindowsAzure.Storage.dll assembly.</span></span> <span data-ttu-id="69468-130">Es wird empfohlen, ein Upgrade auf PowerShell 3.0 auszuführen, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="69468-130">We recommend that you upgrade to Powershell 3.0 to solve the issue.</span></span> <span data-ttu-id="69468-131">Sie können auch die folgende Problemumgehung für PowerShell 2.0 verwenden:</span><span class="sxs-lookup"><span data-stu-id="69468-131">You may also use the following workaround for PowerShell 2.0:</span></span>  
  
-   <span data-ttu-id="69468-132">Lassen Sie die .NET 2.0- und .NET 4.0-Assemblys zur Laufzeit laden. Dazu erstellen Sie eine Datei powershell.exe.config bzw. ändern eine bereits vorhandene Datei mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="69468-132">Create or modify the powershell.exe.config file to load .NET 2.0 and .NET 4.0 assemblies at runtime with the following:</span></span>  
  
    ```xml
    <?xml version="1.0"?>
    <configuration>
        <startup useLegacyV2RuntimeActivationPolicy="true">
            <supportedRuntime version="v4.0.30319"/>
            <supportedRuntime version="v2.0.50727"/>
        </startup>
    </configuration>
    ```  
  
 <span data-ttu-id="69468-133">Das folgende Beispiel veranschaulicht, wie BLOBs mit aktiven Leases identifiziert und die Leases anschließend unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="69468-133">The following example illustrates identifying blobs that have active leases and then breaking them.</span></span> <span data-ttu-id="69468-134">Das Beispiel zeigt auch, wie Sie nach freigegebenen Lease-IDs filtern.</span><span class="sxs-lookup"><span data-stu-id="69468-134">The example also demonstrates how filter for release lease IDs.</span></span>  
  
 <span data-ttu-id="69468-135">Tipps zum Ausführen des Skripts</span><span class="sxs-lookup"><span data-stu-id="69468-135">Tips on running this script</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="69468-136">Wenn eine Sicherung im Azure-BLOB-Speicherdienst zur gleichen Zeit wie dieses Skript ausgeführt wird, kann die Sicherung fehlschlagen, da dieses Skript die Lease unterbricht, die von der Sicherung gleichzeitig abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="69468-136">If a backup to Azure Blob storage service is running at the same time as this script, the backup can fail since this script will break the lease that the backup is trying to acquire at the same time.</span></span> <span data-ttu-id="69468-137">Es empfiehlt sich, das Skript während eines Wartungsfensters oder in Phasen auszuführen, in denen keine Sicherungsaktivitäten zu erwarten sind.</span><span class="sxs-lookup"><span data-stu-id="69468-137">We recommend running this script during a maintenance windows or when no backups are expected to run.</span></span>  
  
1.  <span data-ttu-id="69468-138">Wenn Sie dieses Skript ausführen, werden Sie aufgefordert, Werte für das Speicherkonto, den Speicher Schlüssel, den Container und den Pfad und die namens Parameter der Azure Storage-Assembly anzugeben.</span><span class="sxs-lookup"><span data-stu-id="69468-138">When you run this script, you will be prompted to provide values for the storage account, storage key, container, and the Azure storage assembly path and name parameters.</span></span> <span data-ttu-id="69468-139">Der Pfad der Speicherassembly entspricht dem Installationsverzeichnis der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz.</span><span class="sxs-lookup"><span data-stu-id="69468-139">The path of the storage is assembly is the installation directory of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="69468-140">Der Dateiname der Speicherassembly lautet "Microsoft.WindowsAzure.Storage.dll".</span><span class="sxs-lookup"><span data-stu-id="69468-140">The file name for the storage assembly is Microsoft.WindowsAzure.Storage.dll.</span></span> <span data-ttu-id="69468-141">Im Folgenden ein Beispiel für die angeforderten und eingegebenen Werte:</span><span class="sxs-lookup"><span data-stu-id="69468-141">Following is an example of the prompts and values entered:</span></span>  
  
    ```  
    cmdlet  at command pipeline position 1  
    Supply values for the following parameters:  
    storageAccount: mycloudstorageaccount  
    storageKey: 0BopKY7eEha3gBnistYk+904nf  
    blobContainer: mycontainer   
    storageAssemblyPath: C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Microsoft.WindowsAzure.Storage.dll  
    ```  
  
2.  <span data-ttu-id="69468-142">Wenn keine BLOBs mit gesperrten Leases vorhanden sind, sollte eine mit der folgenden vergleichbare Meldung angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="69468-142">If there are no blobs that have locked leases you should see the following message:</span></span>  
  
     <span data-ttu-id="69468-143">**Es sind keine BLOBs mit gesperrter Lease vorhanden**</span><span class="sxs-lookup"><span data-stu-id="69468-143">**There are no blobs with locked lease status**</span></span>  
  
     <span data-ttu-id="69468-144">Wenn BLOBs mit gesperrten Leases vorhanden sind, sollten Meldungen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="69468-144">If there are blobs with locked leases, you should see the following messages:</span></span>  
  
     <span data-ttu-id="69468-145">**Leases werden unterbrochen**</span><span class="sxs-lookup"><span data-stu-id="69468-145">**Breaking Leases**</span></span>  
  
     <span data-ttu-id="69468-146">**Die Lease für \<URL of the Blob> ist eine Wiederherstellungs Lease: Diese Meldung wird nur angezeigt, wenn Sie über ein BLOB mit einer Wiederherstellungs Lease verfügen, die noch aktiv ist.**</span><span class="sxs-lookup"><span data-stu-id="69468-146">**The lease on \<URL of the Blob> is a restore lease: You will see this message only if you have a blob with a restore lease that is still active.**</span></span>  
  
     <span data-ttu-id="69468-147">**Bei der Lease für \<URL of the Blob> handelt es sich nicht um eine Abbruch Lease für die Wiederherstellung \<URL of the Bob> .**</span><span class="sxs-lookup"><span data-stu-id="69468-147">**The lease on \<URL of the Blob> is not a restore lease Breaking lease on \<URL of the Bob>.**</span></span>  
  
```powershell
param(  
       [Parameter(Mandatory=$true)]  
       [string]$storageAccount,  
       [Parameter(Mandatory=$true)]  
       [string]$storageKey,  
       [Parameter(Mandatory=$true)]  
       [string]$blobContainer,  
       [Parameter(Mandatory=$true)]  
       [string]$storageAssemblyPath  
)  
  
# Well known Restore Lease ID  
$restoreLeaseId = "BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2"  
  
# Load the storage assembly without locking the file for the duration of the PowerShell session  
$bytes = [System.IO.File]::ReadAllBytes($storageAssemblyPath)  
[System.Reflection.Assembly]::Load($bytes)  
  
$cred = New-Object 'Microsoft.WindowsAzure.Storage.Auth.StorageCredentials' $storageAccount, $storageKey  
$client = New-Object 'Microsoft.WindowsAzure.Storage.Blob.CloudBlobClient' "https://$storageAccount.blob.core.windows.net", $cred  
$container = $client.GetContainerReference($blobContainer)  
  
#list all the blobs  
$allBlobs = $container.ListBlobs()
  
$lockedBlobs = @()  
# filter blobs that are have Lease Status as "locked"  
foreach($blob in $allBlobs)  
{  
    $blobProperties = $blob.Properties
    if($blobProperties.LeaseStatus -eq "Locked")  
    {  
        $lockedBlobs += $blob  
    }  
}  
  
if ($lockedBlobs.Count -eq 0)  
{
    Write-Host " There are no blobs with locked lease status"  
}

if($lockedBlobs.Count -gt 0)  
{  
    Write-Host "Breaking leases"  
    foreach($blob in $lockedBlobs )
    {  
        try  
        {  
            $blob.AcquireLease($null, $restoreLeaseId, $null, $null, $null)  
            Write-Host "The lease on $($blob.Uri) is a restore lease"  
        }  
        catch [Microsoft.WindowsAzure.Storage.StorageException]  
        {  
            if($_.Exception.RequestInformation.HttpStatusCode -eq 409)  
            {  
                Write-Host "The lease on $($blob.Uri) is not a restore lease"  
            }  
        }  
  
        Write-Host "Breaking lease on $($blob.Uri)"  
        $blob.BreakLease($(New-TimeSpan), $null, $null, $null) | Out-Null  
    }  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="69468-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69468-148">See Also</span></span>  
 [<span data-ttu-id="69468-149">SQL Server-Sicherung über URLs – bewährte Methoden und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="69468-149">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
