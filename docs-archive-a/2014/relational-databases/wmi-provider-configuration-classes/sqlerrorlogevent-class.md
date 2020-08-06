---
title: Sqlerrorlogevent-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 358b6906e422be2984f2ebdbde636ad0b8376993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616960"
---
# <a name="sqlerrorlogevent-class"></a><span data-ttu-id="323fb-102">SqlErrorLogEvent-Klasse</span><span class="sxs-lookup"><span data-stu-id="323fb-102">SqlErrorLogEvent Class</span></span>
  <span data-ttu-id="323fb-103">Stellt Eigenschaften zum Anzeigen von Ereignissen in einer angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Protokolldatei bereit.</span><span class="sxs-lookup"><span data-stu-id="323fb-103">Provides properties for viewing events in a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="323fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="323fb-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="323fb-105">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="323fb-105">Properties</span></span>  
 <span data-ttu-id="323fb-106">Die sqlerrorlogevent-Klasse definiert die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="323fb-106">The SQLErrorLogEvent class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="323fb-107">FileName</span><span class="sxs-lookup"><span data-stu-id="323fb-107">FileName</span></span>|<span data-ttu-id="323fb-108">Datentyp: `string`</span><span class="sxs-lookup"><span data-stu-id="323fb-108">Data type: `string`</span></span><br /><br /> <span data-ttu-id="323fb-109">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="323fb-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="323fb-110">Der Name der Fehlerprotokolldatei.</span><span class="sxs-lookup"><span data-stu-id="323fb-110">The name of the error log file.</span></span>|  
|<span data-ttu-id="323fb-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="323fb-111">InstanceName</span></span>|<span data-ttu-id="323fb-112">Datentyp: `string`</span><span class="sxs-lookup"><span data-stu-id="323fb-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="323fb-113">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="323fb-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="323fb-114">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="323fb-114">Qualifiers: Key</span></span><br /><br /> <span data-ttu-id="323fb-115">Der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die die Protokolldatei enthält.</span><span class="sxs-lookup"><span data-stu-id="323fb-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="323fb-116">LogDate</span><span class="sxs-lookup"><span data-stu-id="323fb-116">LogDate</span></span>|<span data-ttu-id="323fb-117">Datentyp: `datetime`</span><span class="sxs-lookup"><span data-stu-id="323fb-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="323fb-118">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="323fb-118">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="323fb-119">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="323fb-119">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="323fb-120">Datum und Uhrzeit, zu denen das Ereignis in der Protokolldatei aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="323fb-120">The date and time that the event was recorded in the log file.</span></span>|  
|<span data-ttu-id="323fb-121">Meldung</span><span class="sxs-lookup"><span data-stu-id="323fb-121">Message</span></span>|<span data-ttu-id="323fb-122">Datentyp: `string`</span><span class="sxs-lookup"><span data-stu-id="323fb-122">Data type: `string`</span></span><br /><br /> <span data-ttu-id="323fb-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="323fb-123">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="323fb-124">Die Ereignismeldung.</span><span class="sxs-lookup"><span data-stu-id="323fb-124">The event message.</span></span>|  
|<span data-ttu-id="323fb-125">ProcessInfo</span><span class="sxs-lookup"><span data-stu-id="323fb-125">ProcessInfo</span></span>|<span data-ttu-id="323fb-126">Datentyp: `string`</span><span class="sxs-lookup"><span data-stu-id="323fb-126">Data type: `string`</span></span><br /><br /> <span data-ttu-id="323fb-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="323fb-127">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="323fb-128">Informationen zur SPID (Source Server Process ID, Quellserverprozess-ID) für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="323fb-128">Information about the source server process ID (SPID) for the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="323fb-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="323fb-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="323fb-130">MOF</span><span class="sxs-lookup"><span data-stu-id="323fb-130">MOF</span></span>|<span data-ttu-id="323fb-131">Sqlmgmproviderxpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="323fb-131">Sqlmgmproviderxpsp2up.mof</span></span>|  
|<span data-ttu-id="323fb-132">DLL</span><span class="sxs-lookup"><span data-stu-id="323fb-132">DLL</span></span>|<span data-ttu-id="323fb-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="323fb-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="323fb-134">Namespace</span><span class="sxs-lookup"><span data-stu-id="323fb-134">Namespace</span></span>|<span data-ttu-id="323fb-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="323fb-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="323fb-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="323fb-136">Example</span></span>  
 <span data-ttu-id="323fb-137">Im folgenden Beispiel wird gezeigt, wie Werte für alle protokollierten Ereignisse in einer angegebenen Protokolldatei abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="323fb-137">The following example shows how to retrieve values for all logged events in a specified log file.</span></span> <span data-ttu-id="323fb-138">Um das Beispiel auszuführen, ersetzen Sie \<*Instance_Name*> durch den Namen der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , z. b. "instance1", und ersetzen Sie "File_Name" durch den Namen der Fehlerprotokoll Datei (z. b. ' ErrorLog. 1 ').</span><span class="sxs-lookup"><span data-stu-id="323fb-138">To run the example, replace \<*Instance_Name*> with the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as 'Instance1', and replace 'File_Name' with the name of the error log file, such as 'ERRORLOG.1'.</span></span>  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a><span data-ttu-id="323fb-139">Kommentare</span><span class="sxs-lookup"><span data-stu-id="323fb-139">Comments</span></span>  
 <span data-ttu-id="323fb-140">Wenn *instanceName* oder *filename* nicht in der WQL-Anweisung angegeben wird, gibt die Abfrage Informationen für die Standard Instanz und die aktuelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Protokolldatei zurück.</span><span class="sxs-lookup"><span data-stu-id="323fb-140">When *InstanceName* or *FileName* are not provided in the WQL statement, the query will return information for the default instance and the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span> <span data-ttu-id="323fb-141">Die folgende WQL-Anweisung gibt z. B. alle Protokollereignisse aus der aktuellen Protokolldatei (ERRORLOG) für die Standardinstanz (MSSQLSERVER) zurück.</span><span class="sxs-lookup"><span data-stu-id="323fb-141">For example, the following WQL statement will return all log events from the current log file (ERRORLOG) on the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a><span data-ttu-id="323fb-142">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="323fb-142">Security</span></span>  
 <span data-ttu-id="323fb-143">Zum Herstellen einer Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Protokolldatei über WMI müssen Sie sowohl auf dem lokalen Computer als auch auf dem Remote Computer über die folgenden Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="323fb-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="323fb-144">Lesen Sie den Zugriff auf den WMI-Namespace **root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="323fb-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="323fb-145">Standardmäßig verfügt jeder Benutzer durch die Berechtigung Konto aktivieren über Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="323fb-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
-   <span data-ttu-id="323fb-146">Leseberechtigung für den Ordner mit den Fehlerprotokollen.</span><span class="sxs-lookup"><span data-stu-id="323fb-146">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="323fb-147">Standardmäßig befinden sich die Fehlerprotokolle unter dem folgenden Pfad (wobei \<*Drive> \* das Laufwerk darstellt, auf dem Sie installiert haben, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und \<*InstanceName*> ist der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="323fb-147">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="323fb-148">\*\* \<Drive> : \Programme\Microsoft SQL server\mssql12\*\* **. \<InstanceName> \MSSQL\LOG**</span><span class="sxs-lookup"><span data-stu-id="323fb-148">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="323fb-149">Wenn Sie eine Verbindung über eine Firewall herstellen, stellen Sie sicher, dass in der Firewall für WMI auf Remotezielcomputern eine Ausnahme festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="323fb-149">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="323fb-150">Weitere Informationen finden Sie unter [Herstellen einer Remote Verbindung mit WMI ab Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="323fb-150">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323fb-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="323fb-151">See Also</span></span>  
 <span data-ttu-id="323fb-152">[Sqlerrorlogfile-Klasse](sqlerrorlogfile-class.md) </span><span class="sxs-lookup"><span data-stu-id="323fb-152">[SqlErrorLogFile Class](sqlerrorlogfile-class.md) </span></span>  
 [<span data-ttu-id="323fb-153">Anzeigen von Offlineprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="323fb-153">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
