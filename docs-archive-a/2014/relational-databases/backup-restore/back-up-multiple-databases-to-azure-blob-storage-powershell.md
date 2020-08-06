---
title: Verwenden von PowerShell zum Sichern mehrerer Datenbanken in Azure BLOB Storage Dienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: f7008339-e69d-4e20-9265-d649da670460
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95da5d0009f88943029e62960e7429b292242bbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618738"
---
# <a name="use-powershell-to-backup-multiple-databases-to-azure-blob-storage-service"></a><span data-ttu-id="3a600-102">Verwenden von PowerShell zum Sichern mehrerer Datenbanken im Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="3a600-102">Use PowerShell to Backup Multiple Databases to Azure Blob Storage Service</span></span>
  <span data-ttu-id="3a600-103">Dieses Thema enthält Beispielskripts, die verwendet werden können, um Sicherungen im Azure Blob Storage-Dienst mit PowerShell-Cmdlets zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="3a600-103">This topic provides sample scripts that can be used to automate backups to Azure Blob storage service using PowerShell cmdlets.</span></span>  
  
## <a name="overview-of-powershell-cmdlets-for-backup-and-restore"></a><span data-ttu-id="3a600-104">Übersicht über PowerShell-Cmdlets für Sicherungen und Wiederherstellungen</span><span class="sxs-lookup"><span data-stu-id="3a600-104">Overview of PowerShell cmdlets for Backup and Restore</span></span>  
 <span data-ttu-id="3a600-105">`Backup-SqlDatabase` und `Restore-SqlDatabase` sind die beiden wichtigsten Cmdlets, die für Sicherungs- und Wiederherstellungsvorgänge verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3a600-105">The `Backup-SqlDatabase` and `Restore-SqlDatabase` are the two main cmdlets available to do backup and restore operations.</span></span> <span data-ttu-id="3a600-106">Darüber hinaus gibt es andere Cmdlets, die möglicherweise erforderlich sind, um Sicherungen im Azure Blob Storage-Dienst zu automatisieren, wie den Satz von **SqlCredential**-Cmdlets. Im Anschluss finden Sie eine Liste der PowerShell-Cmdlets, die in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] verfügbar sind und die in den Sicherungs- und Wiederherstellungsvorgängen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3a600-106">In addition, there are other cmdlets that may be required to automate backups to Azure Blob storage like the set of **SqlCredential** cmdlets  Following is a list of PowerShell cmdlets available in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that are used in backup and restore operations:</span></span>  
  
 <span data-ttu-id="3a600-107">Backup_SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="3a600-107">Backup-SqlDatabase</span></span>  
 <span data-ttu-id="3a600-108">Dieses Cmdlet wird verwendet, um eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a600-108">This cmdlet is used to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Backup.</span></span>  
  
 <span data-ttu-id="3a600-109">Restore-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="3a600-109">Restore-SqlDatabase</span></span>  
 <span data-ttu-id="3a600-110">Wird zum Wiederherstellen einer Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a600-110">Used to restore a database.</span></span>  
  
 <span data-ttu-id="3a600-111">New-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="3a600-111">New-SqlCredential</span></span>  
 <span data-ttu-id="3a600-112">Dieses Cmdlet wird verwendet, um SQL-Anmeldeinformationen zu erstellen, die für die SQL Server-Sicherung in Azure Storage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a600-112">This cmdlet is used to create a SQL Credential to use for SQL Server Backup to Azure Storage.</span></span> <span data-ttu-id="3a600-113">Weitere Informationen zu Anmelde Informationen und deren Verwendung in SQL Server Sicherung und Wiederherstellung finden Sie unter [SQL Server sichern und Wiederherstellen mit Azure BLOB Storage Dienst](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="3a600-113">For more information on credentials and their use in SQL Server Backup and Restore, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="3a600-114">Get-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="3a600-114">Get-SqlCredential</span></span>  
 <span data-ttu-id="3a600-115">Dieses Cmdlet wird verwendet, um das Objekt mit den Anmeldeinformationen und den entsprechenden Eigenschaften abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3a600-115">This cmdlet is used to retrieve the Credential object and its properties.</span></span>  
  
 <span data-ttu-id="3a600-116">Remove-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="3a600-116">Remove-SqlCredential</span></span>  
 <span data-ttu-id="3a600-117">Löscht ein Objekt mit SQL-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="3a600-117">Delete a SQL Credential object</span></span>  
  
 <span data-ttu-id="3a600-118">Set-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="3a600-118">Set-SqlCredential</span></span>  
 <span data-ttu-id="3a600-119">Dieses Cmdlet wird verwendet, um die Eigenschaften des Objekts mit SQL-Anmeldeinformationen festzulegen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a600-119">This cmdlet is used to change or set the properties of the SQL Credential Object.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="3a600-120">Die Cmdlets für Anmeldeinformationen werden in Szenarien für den Azure Blob Storage bei der Sicherung und Wiederherstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a600-120">The Credential cmdlets are used in Backup and Restore to Azure Blob storage scenarios.</span></span>  
  
### <a name="powershell-for-multi-database-multi-instance-backup-operations"></a><span data-ttu-id="3a600-121">PowerShell für mehrere Datenbanken, Sicherungsvorgänge mit mehreren Instanzen</span><span class="sxs-lookup"><span data-stu-id="3a600-121">PowerShell for Multi-Database, Multi-Instance Backup Operations</span></span>  
 <span data-ttu-id="3a600-122">Die folgenden Abschnitte enthalten die Skripts für verschiedene Vorgänge wie das Erstellen von SQL-Anmeldeinformationen in mehreren SQL Server-Instanzen, das Sichern aller Benutzerdatenbanken in einer Instanz von SQL Server usw.</span><span class="sxs-lookup"><span data-stu-id="3a600-122">The following sections include scripts for various operations like creating a SQL Credential on multiple instance of SQL Server, backing up all user databases in an instance of SQL Server, and such.</span></span> <span data-ttu-id="3a600-123">Sie können diese Skripts verwenden, um Sicherungsvorgänge gemäß den Anforderungen Ihrer Umgebung zu automatisieren oder zu planen.</span><span class="sxs-lookup"><span data-stu-id="3a600-123">You can use these scripts to automate or schedule backup operations according to the requirements of your environment.</span></span> <span data-ttu-id="3a600-124">Die Skripts, die hier bereitgestellt werden, sind Beispiele und können für Ihre Umgebung geändert oder erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="3a600-124">The scripts provided here are examples, and may be modified or extended for your environment.</span></span>  
  
 <span data-ttu-id="3a600-125">Folgende Überlegungen sind bei Beispielskripts zu bedenken:</span><span class="sxs-lookup"><span data-stu-id="3a600-125">The following are considerations for the sample scripts:</span></span>  
  
1.  <span data-ttu-id="3a600-126">**Navigieren durch SQL Server PowerShell-Pfade:** Windows PowerShell implementiert Cmdlets, um in der Pfadstruktur zu navigieren, die die Hierarchie der von einem PowerShell-Anbieter unterstützten Objekte darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a600-126">**Navigating SQL Server PowerShell paths:** Windows PowerShell implements cmdlets to navigate the path structure that represents the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="3a600-127">Wenn Sie zu einem Knoten im Pfad navigiert haben, können Sie andere Cmdlets verwenden, um grundlegende Vorgänge für das aktuelle Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3a600-127">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span>  
  
2.  <span data-ttu-id="3a600-128">`Get-ChildItem`-Cmdlet: Welche Informationen von `Get-ChildItem` zurückgegeben werden, hängt vom Speicherort in einem SQL Server PowerShell-Pfad ab.</span><span class="sxs-lookup"><span data-stu-id="3a600-128">`Get-ChildItem` cmdlet: The information returned by the `Get-ChildItem` depends on the location in a SQL Server PowerShell path.</span></span> <span data-ttu-id="3a600-129">Wenn der Speicherort auf der Computerebene liegt, gibt dieses Cmdlets alle SQL Server-Datenbank-Engine-Instanzen zurück, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3a600-129">For example, if the location is at the computer level, this cmdlet returns all the SQL Server database engine instances installed on the computer.</span></span> <span data-ttu-id="3a600-130">Wenn der Speicherort aber auf Objektebene, wie z. B. Datenbanken, liegt, dann gibt dieses Cmdlets eine Liste von Datenbankobjekten zurück.</span><span class="sxs-lookup"><span data-stu-id="3a600-130">As another example, if the location is at the object level such as databases, then this cmdlet returns a list of database objects.</span></span>  <span data-ttu-id="3a600-131">Standardmäßig gibt das `Get-ChildItem`-Cmdlet keine Systemobjekte zurück.</span><span class="sxs-lookup"><span data-stu-id="3a600-131">By default the `Get-ChildItem` cmdlet does not return system objects.</span></span>  <span data-ttu-id="3a600-132">Wenn Sie den -Force-Parameter verwenden, können Sie die Systemobjekte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a600-132">Using the -Force parameter you can see the system objects.</span></span>  
  
     <span data-ttu-id="3a600-133">Weitere Informationen finden Sie unter [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span><span class="sxs-lookup"><span data-stu-id="3a600-133">For more information, see [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span></span>  
  
3.  <span data-ttu-id="3a600-134">Die Codebeispiele können unabhängig voneinander ausprobiert werden, indem die Variablenwerte geändert werden. Die Erstellung des Azure-Speicherkontos und der SQL-Anmeldeinformationen sind aber Voraussetzungen, die für alle Sicherungs- und Wiederherstellungsvorgänge im Azure Blob Storage-Dienst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3a600-134">Although each code sample can be tried independently by changing the variable values, creating an Azure Storage Account and a SQL Credential are prerequisites and required for all backup and restore operations to Azure Blob storage service.</span></span>  
  
### <a name="create-a-sql-credential-on-all-the-instances-of-sql-server"></a><span data-ttu-id="3a600-135">Erstellen von SQL-Anmeldeinformationen für alle Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a600-135">Create a SQL Credential on All the Instances of SQL Server</span></span>  
 <span data-ttu-id="3a600-136">Es gibt zwei Beispielskripts, und beide erstellen Anmeldeinformationen mit der Bezeichnung „mybackupToURL“ für alle Instanzen von SQL Server auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="3a600-136">There are two sample scripts, and both create a SQL Credential "mybackupToURL" on all the instances of SQL Server on a computer.</span></span> <span data-ttu-id="3a600-137">Das erste Beispiel ist einfach; die Anmeldeinformationen werden erstellt und keine Ausnahmen aufgefangen.</span><span class="sxs-lookup"><span data-stu-id="3a600-137">The first example creates is simple and creates the credential and does not trap exceptions.</span></span>  <span data-ttu-id="3a600-138">Wenn beispielsweise bereits vorhandene Anmeldeinformationen mit dem gleichen Namen für eine der Instanzen des Computers vorliegen, schlägt das Skript fehl.</span><span class="sxs-lookup"><span data-stu-id="3a600-138">For example, if there was already an existing credential with the same name on one of the instances of the computer, the script would fail.</span></span> <span data-ttu-id="3a600-139">Im zweiten Beispiel werden Fehler aufgefangen, und das Skript kann fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3a600-139">The second example traps errors and allows the script to continue.</span></span>  
  
```powershell
import-module sqlps  
  
# create variables  
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#pipe the instances to new-sqlcredentail cmdlet to create SQL credential  
$instances | New-SqlCredential -Name $credentialName -Identity $storageAccount -Secret $secureString  
```  
  
```powershell
import-module sqlps  
  
# set the parameter values
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#loop through instances and create a SQL credential, output any errors  
ForEach ($instance In $instances)  
{  
    Try  
{  
     New-SqlCredential -Name $credentialName -path "SQLServer:\SQL\$($instance.name)" -Identity $storageAccount -Secret $secureString -ea Stop
}  
Catch [Exception]  
    {
            Write-Host "instance - $($instance.name): "$_.Exception.Message
    }
 }
```  
  
### <a name="remove-a-sql-credential-from-all-the-instances-of-sql-server"></a><span data-ttu-id="3a600-140">Entfernen von SQL-Anmeldeinformationen für alle Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a600-140">Remove A SQL Credential from All the Instances of SQL Server</span></span>  
 <span data-ttu-id="3a600-141">Dieses Skript kann verwendet werden, um bestimmte Anmeldeinformationen von allen SQL Server-Instanzen auf dem Computer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3a600-141">This script can be used to remove a specific credential from all the instances of SQL Server installed on the computer.</span></span> <span data-ttu-id="3a600-142">Wenn das Credential-Objekt in einer bestimmten Instanz nicht vorhanden ist, wird eine Fehlermeldung angezeigt, und das Skript wird fortgesetzt, bis alle Instanzen überprüft sind.</span><span class="sxs-lookup"><span data-stu-id="3a600-142">If the Credential object does not exist on a specific instance, an error message is displayed, and the script continues until all instances are checked.</span></span>  
  
```powershell
import-module sqlps  
  
cd SQLServer:\SQL\COMPUTERNAME  
$credentialName = "mybackuptoURL"  
  
$instances = Get-ChildItem  
  
ForEach ($instance In $instances)  
   {
    Try  
        {  
            $path = "SQLServer:\SQL\$($instance.name)\credentials\$credentialName"   
            Remove-SqlCredential -Path $path -ea stop   
         }  
         Catch [Exception]  
         {  
            Write-Host $_.Exception.Message
        }
    }  
```  
  
### <a name="full-database-backup-for-all-databases-including-system-databases"></a><span data-ttu-id="3a600-143">Vollständige Sicherung für alle Datenbanken (EINSCHLIESSLICH SYSTEMDATENBANKEN)</span><span class="sxs-lookup"><span data-stu-id="3a600-143">Full Database Backup for all Databases (INCLUDING SYSTEM DATABASES)</span></span>  
 <span data-ttu-id="3a600-144">Mit dem folgenden Skript erstellen Sie Sicherungen aller Datenbanken auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="3a600-144">The following script creates backups of all databases on the computer.</span></span> <span data-ttu-id="3a600-145">Dies gilt sowohl für Benutzerdatenbanken als auch für die **msdb** -Systemdatenbank.</span><span class="sxs-lookup"><span data-stu-id="3a600-145">This includes both user databases and **msdb** system database.</span></span> <span data-ttu-id="3a600-146">Das Skript filtert **tempdb** - und **model** -Systemdatenbanken heraus.</span><span class="sxs-lookup"><span data-stu-id="3a600-146">The script filters out **tempdb** and **model** system databases.</span></span>  
  
```powershell
import-module sqlps  
# set the parameter values  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the  databases -filter out tempdb and model databases  
  
 ForEach ($instance In $instances)  
 {  
   $path = "sqlserver:\sql\$($instance.name)\databases"  
   $alldatabases = Get-ChildItem -Force -path $path | Where-Object {$_.name -ne "tempdb" -and $_.name -ne "model"}   
   $alldatabases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On -script   
 }
```  
  
### <a name="full-database-backup-for-all-user-databases"></a><span data-ttu-id="3a600-147">Vollständige Sicherung ALLER Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="3a600-147">Full Database Backup for ALL User Databases</span></span>  
 <span data-ttu-id="3a600-148">Das folgende Skript kann verwendet werden, um alle Benutzerdatenbanken in allen Instanzen von SQL Server auf dem Computer zu sichern.</span><span class="sxs-lookup"><span data-stu-id="3a600-148">The following script can be used to back up all the user databases on all the instances of SQL Server on the computer.</span></span>  
  
```powershell
import-module sqlps
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the user databases  
 ForEach ($instance In $instances)  
 {  
    $databases = dir "sqlserver:\sql\$($instance.name)\databases"  
    $databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On
 }  
```  
  
### <a name="full-database-backup-for-master-and-msdb-system-databases-on-all-the-instances-of-sql-server"></a><span data-ttu-id="3a600-149">Vollständige Sicherung für MASTER und MSDB (SYSTEMDATENBANKEN) in allen Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a600-149">Full Database Backup for MASTER and MSDB (SYSTEM DATABASES) On All the Instances of SQL Server</span></span>  
 <span data-ttu-id="3a600-150">Das folgende Skript kann verwendet werden, um alle **master** - und **msdb** -Datenbanken in allen Instanzen von SQL Server auf dem Computer zu sichern.</span><span class="sxs-lookup"><span data-stu-id="3a600-150">The following script can be used to back up **master** and **msdb** databases on all the instances of SQL Server installed on the computer.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackupToUrl"  
$sysDbs = "master", "msdb"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
$instances = Get-ChildItem
ForEach ($instance In $instances)  
 {  
      ForEach ($s In $sysdbs)  
     {  
        Backup-SqlDatabase -Database $s -path "sqlserver:\sql\$($instance.name)" -BackupContainer  $backupUrlContainer -SqlCredential $credentialName -Compression On   
}
 } 
```  
  
### <a name="full-database-backup-for-all-user-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="3a600-151">Vollständige Sicherung für alle Benutzerdatenbanken in einer Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a600-151">Full Database Backup for All User Databases on an Instance of SQL Server</span></span>  
 <span data-ttu-id="3a600-152">Das folgenden Skript wird verwendet, um nur die Benutzerdatenbanken zu sichern, die in einer benannten Instanz von SQL Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3a600-152">The following script is used to back up only the user databases available on a named instance of SQL Server.</span></span> <span data-ttu-id="3a600-153">Das gleiche Skript kann für die Standardinstanz auf dem Computer verwendet werden, indem der $srvPath-Parameterwert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="3a600-153">The same script can be used for the default instance on the computer by changing the $srvPath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME"  # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
  
#retrieves the database objects for a specific instance  
$databases = dir $srvPath\databases  
  
#backup all the user databases  
$databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
```  
  
### <a name="full-database-backup-for-only-system-databases-master-and-msdb-on-an-instance-of-sql-server"></a><span data-ttu-id="3a600-154">Vollständige Sicherung nur für Systemdatenbanken (MASTER UND MSDB) in einer Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a600-154">Full Database Backup for Only System Databases (MASTER AND MSDB) On an Instance of SQL Server</span></span>  
 <span data-ttu-id="3a600-155">Das vollständige Skript kann zum Sichern der **master** - und der **msdb** -Datenbanken in einer benannten Instanz von SQL Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a600-155">The full script can be used to back up the **master** and the **msdb** databases on a named instance of SQL Server.</span></span> <span data-ttu-id="3a600-156">Das gleiche Skript kann für die Standardinstanz auf dem Computer verwendet werden, indem der $srvPath-Parameterwert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="3a600-156">The same script can be used for the default instance on the computer by changing the $srvpath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME" # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#navigate to instance level  
cd $srvPath  
  
$sysDbs = "master", "msdb"  
ForEach ($s In $sysDbs)
{  
Backup-SqlDatabase -Database $s -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="3a600-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a600-157">See Also</span></span>
 <span data-ttu-id="3a600-158">[SQL Server sichern und Wiederherstellen mit Azure BLOB Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server bewährte Methoden und Problem](sql-server-backup-to-url-best-practices-and-troubleshooting.md) Behandlung bei URLs</span><span class="sxs-lookup"><span data-stu-id="3a600-158">[SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
