---
title: Sqlerrorlogfile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
ms.assetid: 2b83ae4a-c0d4-414c-b6e5-a41ec7c13159
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d73f97ebddd7a1d18c73a2cbce7fe79dafc17a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696578"
---
# <a name="sqlerrorlogfile-class"></a><span data-ttu-id="c8117-102">SqlErrorLogFile-Klasse</span><span class="sxs-lookup"><span data-stu-id="c8117-102">SqlErrorLogFile Class</span></span>
  <span data-ttu-id="c8117-103">Stellt Eigenschaften zum Anzeigen von Informationen über eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Protokolldatei bereit.</span><span class="sxs-lookup"><span data-stu-id="c8117-103">Provides properties for viewing information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8117-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8117-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogFile  
{  
   uint32ArchiveNumber;  
   stringInstanceName;  
   datetimeLastModified;  
   uint32LogFileSize;  
   stringName;  
  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="c8117-105">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c8117-105">Properties</span></span>  
 <span data-ttu-id="c8117-106">Die sqlerrorlogfile-Klasse definiert die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c8117-106">The SQLErrorLogFile class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8117-107">Archivenreiber</span><span class="sxs-lookup"><span data-stu-id="c8117-107">ArchiveNumber</span></span>|<span data-ttu-id="c8117-108">Datentyp: `uint32`</span><span class="sxs-lookup"><span data-stu-id="c8117-108">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="c8117-109">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c8117-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="c8117-110">Die Archivnummer für die Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="c8117-110">The archive number for the log file.</span></span>|  
|<span data-ttu-id="c8117-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="c8117-111">InstanceName</span></span>|<span data-ttu-id="c8117-112">Datentyp: `string`</span><span class="sxs-lookup"><span data-stu-id="c8117-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="c8117-113">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c8117-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="c8117-114">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c8117-114">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="c8117-115">Der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die die Protokolldatei enthält.</span><span class="sxs-lookup"><span data-stu-id="c8117-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="c8117-116">LastModified</span><span class="sxs-lookup"><span data-stu-id="c8117-116">LastModified</span></span>|<span data-ttu-id="c8117-117">Datentyp: `datetime`</span><span class="sxs-lookup"><span data-stu-id="c8117-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="c8117-118">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c8117-118">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="c8117-119">Das Datum, an dem die Protokolldatei zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c8117-119">The date that the log file was last modified.</span></span>|  
|<span data-ttu-id="c8117-120">Logfile size</span><span class="sxs-lookup"><span data-stu-id="c8117-120">LogFileSize</span></span>|<span data-ttu-id="c8117-121">Datentyp: `uint32`</span><span class="sxs-lookup"><span data-stu-id="c8117-121">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="c8117-122">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c8117-122">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="c8117-123">Die Größe der Protokolldatei in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c8117-123">The log file size, in bytes.</span></span>|  
|<span data-ttu-id="c8117-124">Name</span><span class="sxs-lookup"><span data-stu-id="c8117-124">Name</span></span>|<span data-ttu-id="c8117-125">Datentyp: `string`</span><span class="sxs-lookup"><span data-stu-id="c8117-125">Data type: `string`</span></span><br /><br /> <span data-ttu-id="c8117-126">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c8117-126">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="c8117-127">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c8117-127">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="c8117-128">Der Name der Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="c8117-128">The name of the log file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8117-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c8117-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8117-130">MOF</span><span class="sxs-lookup"><span data-stu-id="c8117-130">MOF</span></span>|<span data-ttu-id="c8117-131">Sqlmgmprovider xpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="c8117-131">Sqlmgmprovider xpsp2up.mof</span></span>|  
|<span data-ttu-id="c8117-132">DLL</span><span class="sxs-lookup"><span data-stu-id="c8117-132">DLL</span></span>|<span data-ttu-id="c8117-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="c8117-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="c8117-134">Namespace</span><span class="sxs-lookup"><span data-stu-id="c8117-134">Namespace</span></span>|<span data-ttu-id="c8117-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="c8117-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8117-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8117-136">Example</span></span>  
 <span data-ttu-id="c8117-137">Im folgenden Beispiel werden Informationen zu allen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Protokolldateien in einer angegebenen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c8117-137">The following example retrieves information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c8117-138">Um das Beispiel auszuführen, ersetzen Sie \<*Instance_Name*> durch den Namen der Instanz, z. b. "instance1".</span><span class="sxs-lookup"><span data-stu-id="c8117-138">To run the example, replace \<*Instance_Name*> with the name of the instance, for example, 'Instance1'.</span></span>  
  
```  
on error resume next  
set strComputer = "."  
set objWMIService = GetObject("winmgmts:\\.\root\Microsoft\SqlServer\ComputerManagement10")  
set LogFiles = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogFile WHERE InstanceName = '<Instance_Name>'")  
  
For Each logFile in LogFiles  
  
WScript.Echo "Instance Name:  " & logFile.InstanceName & vbNewLine _  
    & "Log File Name:  " & logFile.Name & vbNewLine _  
    & "Archive Number: " & logFile.ArchiveNumber & vbNewLine _  
    & "Log File Size:  " & logFile.LogFileSize & " bytes" & vbNewLine _  
    & "Last Modified:  " & logFile.LastModified & vbNewLine _  
  
Next   
```  
  
## <a name="comments"></a><span data-ttu-id="c8117-139">Kommentare</span><span class="sxs-lookup"><span data-stu-id="c8117-139">Comments</span></span>  
 <span data-ttu-id="c8117-140">Wenn *instanceName* nicht in der WQL-Anweisung angegeben wird, gibt die Abfrage Informationen für die Standard Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="c8117-140">When *InstanceName* is not provided in the WQL statement, the query will return information for the default instance.</span></span> <span data-ttu-id="c8117-141">Die folgende WQL-Anweisung gibt z. B. Informationen zu allen Protokolldateien der Standardinstanz (MSSQLSERVER) zurück.</span><span class="sxs-lookup"><span data-stu-id="c8117-141">For example, the following WQL statement will return information about all log files from the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogFile"  
```  
  
## <a name="security"></a><span data-ttu-id="c8117-142">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c8117-142">Security</span></span>  
 <span data-ttu-id="c8117-143">Zum Herstellen einer Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Protokolldatei über WMI müssen Sie sowohl auf dem lokalen Computer als auch auf dem Remote Computer über die folgenden Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="c8117-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="c8117-144">Lesen Sie den Zugriff auf den WMI-Namespace **root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="c8117-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="c8117-145">Standardmäßig verfügt jeder Benutzer durch die Berechtigung Konto aktivieren über Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="c8117-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8117-146">Weitere Informationen zum Überprüfen von WMI-Berechtigungen finden Sie im Abschnitt "Sicherheit" des Themas [Anzeigen von Offline Protokolldateien](../logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="c8117-146">For information about how to verify WMI permissions, see the Security section of the topic [View Offline Log Files](../logs/view-offline-log-files.md).</span></span>  
  
-   <span data-ttu-id="c8117-147">Leseberechtigung für den Ordner mit den Fehlerprotokollen.</span><span class="sxs-lookup"><span data-stu-id="c8117-147">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="c8117-148">Standardmäßig befinden sich die Fehlerprotokolle unter dem folgenden Pfad (wobei \<*Drive> \* das Laufwerk darstellt, auf dem Sie installiert haben, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und \<*InstanceName*> ist der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="c8117-148">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="c8117-149">\*\* \<Drive> : \Programme\Microsoft SQL server\mssql11\*\* **. \<InstanceName> \MSSQL\LOG**</span><span class="sxs-lookup"><span data-stu-id="c8117-149">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL11** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="c8117-150">Wenn Sie eine Verbindung über eine Firewall herstellen, stellen Sie sicher, dass in der Firewall für WMI auf Remotezielcomputern eine Ausnahme festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c8117-150">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="c8117-151">Weitere Informationen finden Sie unter [Herstellen einer Remote Verbindung mit WMI ab Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="c8117-151">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8117-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8117-152">See Also</span></span>  
 <span data-ttu-id="c8117-153">[Sqlerrorlogevent-Klasse](sqlerrorlogevent-class.md) </span><span class="sxs-lookup"><span data-stu-id="c8117-153">[SqlErrorLogEvent Class](sqlerrorlogevent-class.md) </span></span>  
 [<span data-ttu-id="c8117-154">Anzeigen von Offlineprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="c8117-154">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
