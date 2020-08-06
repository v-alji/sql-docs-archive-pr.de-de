---
title: Konfigurieren des Integration Services Dienstanbieter (SSIS-Dienst) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- configuration files [Integration Services]
- service [Integration Services], configuring
- default configuration files
ms.assetid: 36d78393-a54c-44b0-8709-7f003f44c27f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70c41377a2c302e1a021c6ade2a9d487579fa64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722982"
---
# <a name="configuring-the-integration-services-service-ssis-service"></a><span data-ttu-id="0eed5-102">Konfigurieren des Integration Services-Diensts (SSIS-Dienst)</span><span class="sxs-lookup"><span data-stu-id="0eed5-102">Configuring the Integration Services Service (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="0eed5-103">In diesem Thema wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst beschrieben, ein Windows-Dienst zur Verwaltung von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paketen.</span><span class="sxs-lookup"><span data-stu-id="0eed5-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] <span data-ttu-id="0eed5-104">unterstützt den Dienst für die Abwärtskompatibilität mit früheren Versionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eed5-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="0eed5-105">Ab [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]können Sie Objekte, z. B. Pakete, auf dem Integration Services-Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="0eed5-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="0eed5-106">Der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst erhält seine Einstellungen über eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0eed5-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service relies on a configuration file for its settings.</span></span> <span data-ttu-id="0eed5-107">Standardmäßig wird der Name für diese Konfigurationsdatei MsDtsSrvr.ini.xml, und die Datei befindet sich im Ordner%ProgramFiles%\Microsoft SQL server\120\dz\binn.</span><span class="sxs-lookup"><span data-stu-id="0eed5-107">By default, the name for this configuration file is MsDtsSrvr.ini.xml, and the file is located in the folder, %ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span></span>  
  
 <span data-ttu-id="0eed5-108">In der Regel müssen Sie keine Änderungen an dieser Konfigurationsdatei vornehmen. Ebenso wenig müssen Sie den Standardspeicherort der Datei ändern.</span><span class="sxs-lookup"><span data-stu-id="0eed5-108">Typically, you do not have to make any changes to this configuration file, nor do you have to change the file's default location.</span></span> <span data-ttu-id="0eed5-109">Sie müssen die Konfigurationsdatei jedoch ändern, wenn Ihre Pakete in einer benannten Instanz, einer Remoteinstanz von [!INCLUDE[ssDE](../includes/ssde-md.md)]oder in mehreren Instanzen von [!INCLUDE[ssDE](../includes/ssde-md.md)]gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0eed5-109">However, you will have to modify the configuration file if your packages are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)], or in multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="0eed5-110">Auch wenn Sie die Konfigurationsdatei an einen anderen Speicherort verschieben, müssen Sie den Registrierungsschlüssel ändern, der den Dateispeicherort angibt.</span><span class="sxs-lookup"><span data-stu-id="0eed5-110">Also, if you move the configuration file to a location other than the default location, you will have to modify the Registry key that specifies the file location.</span></span>  
  
## <a name="configuration-file-contents"></a><span data-ttu-id="0eed5-111">Inhalt der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0eed5-111">Configuration File Contents</span></span>  
 <span data-ttu-id="0eed5-112">Wenn Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]installieren, erstellt und installiert der Setupprozess die Konfigurationsdatei für den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="0eed5-112">When you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the setup process creates and installs the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="0eed5-113">Diese Konfigurationsdatei enthält die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0eed5-113">This configuration file contains the following settings:</span></span>  
  
-   <span data-ttu-id="0eed5-114">Paketen wird ein Befehl zum Beenden gesendet, wenn der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0eed5-114">Packages are sent a stop command when the service stops.</span></span>  
  
-   <span data-ttu-id="0eed5-115">Die Stammordner, die für [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] angezeigt werden sollen, sind die Ordner MSDB und File System.</span><span class="sxs-lookup"><span data-stu-id="0eed5-115">The root folders to display for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in Object Explorer of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are the MSDB and File System folders.</span></span>  
  
-   <span data-ttu-id="0eed5-116">Die Pakete im Dateisystem, die vom- [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Dienst verwaltet werden, befinden sich unter%ProgramFiles%\Microsoft SQL server\120\dz\packages.</span><span class="sxs-lookup"><span data-stu-id="0eed5-116">The packages in the file system that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages are located in %ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span></span>  
  
 <span data-ttu-id="0eed5-117">Diese Konfigurationsdatei gibt auch an, welche msdb-Datenbank die Pakete enthält, die der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0eed5-117">This configuration file also specifies which msdb database contains the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service will manage.</span></span> <span data-ttu-id="0eed5-118">Standardmäßig wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst für die Verwaltung von Paketen in der msdb-Datenbank der Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)] konfiguriert, die zur selben Zeit wie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]installiert wird.</span><span class="sxs-lookup"><span data-stu-id="0eed5-118">By default, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed at the same time as [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="0eed5-119">Wenn eine Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)] nicht zur selben Zeit installiert wird, wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst so konfiguriert, dass Pakete in der msdb-Datenbank der lokalen Standardinstanz von [!INCLUDE[ssDE](../includes/ssde-md.md)]verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0eed5-119">If an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] is not installed at the same time, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the local, default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
### <a name="default-configuration-file-example"></a><span data-ttu-id="0eed5-120">Beispiel für eine Standardkonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0eed5-120">Default Configuration File Example</span></span>  
 <span data-ttu-id="0eed5-121">Folgendes Beispiel zeigt eine Standardkonfigurationsdatei, die die folgenden Einstellungen angibt:</span><span class="sxs-lookup"><span data-stu-id="0eed5-121">The following example shows a default configuration file that specifies the following settings:</span></span>  
  
-   <span data-ttu-id="0eed5-122">Die Ausführung von Paketen wird beim Beenden des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Diensts beendet.</span><span class="sxs-lookup"><span data-stu-id="0eed5-122">Packages stop running when the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service stops.</span></span>  
  
-   <span data-ttu-id="0eed5-123">Die Stammordner für das Speichern von Paketen in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sind die Ordner MSDB und Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="0eed5-123">The root folders for package storage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are MSDB and File System.</span></span>  
  
-   <span data-ttu-id="0eed5-124">Der Dienst verwaltet Pakete, die in der msdb-Datenbank der lokalen Standardinstanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0eed5-124">The service manages packages that are stored in the msdb database of the local, default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0eed5-125">Der Dienst verwaltet Pakete, die im Dateisystem im Ordner Pakete gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0eed5-125">The service manages packages that are stored in the file system in the Packages folder.</span></span>  
  
 <span data-ttu-id="0eed5-126">**Beispiel einer Standardkonfigurationsdatei**</span><span class="sxs-lookup"><span data-stu-id="0eed5-126">**Example of a Default Configuration File**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>.</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file"></a><span data-ttu-id="0eed5-127">Änderung der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0eed5-127">Modification of the Configuration File</span></span>  
 <span data-ttu-id="0eed5-128">Sie können die Konfigurationsdatei ändern, um Pakete beim Beenden des Diensts weiterhin auszuführen, um zusätzliche Stammordner im Objekt-Explorer anzuzeigen oder um einen anderen Ordner oder zusätzliche Ordner im Dateisystem anzugeben, die von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0eed5-128">You can modify the configuration file to allow packages to continue running if the service stops, to display additional root folders in Object Explorer, or to specify a different folder or additional folders in the file system to be managed by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="0eed5-129">Sie können beispielsweise zusätzliche Stammordner des Typs `SqlServerFolder` erstellen, um Pakete in den msdb-Datenbanken zusätzlicher Instanzen von [!INCLUDE[ssDE](../includes/ssde-md.md)] zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0eed5-129">For example, you can create additional root folders of type, `SqlServerFolder`, to manage packages in the msdb databases of additional instances of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0eed5-130">Manche Zeichen sind für Ordnernamen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0eed5-130">Some characters are not valid in folder names.</span></span> <span data-ttu-id="0eed5-131">Die gültigen Zeichen für Ordnernamen werden durch die [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] -Klasse **System.IO.Path** und das Feld **GetInvalidFilenameChars** bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0eed5-131">Valid characters for folder names are determined by the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] class **System.IO.Path** and the **GetInvalidFilenameChars** field.</span></span> <span data-ttu-id="0eed5-132">Das Feld **GetInvalidFilenameChars** stellt ein plattformspezifisches Array mit Zeichen bereit, das nicht in Pfadzeichenfolgenargumenten angegeben werden kann, die an Mitglieder der **Path** -Klasse übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0eed5-132">The **GetInvalidFilenameChars** field provides a platform-specific array of characters that cannot be specified in path string arguments passed to members of the **Path** class.</span></span> <span data-ttu-id="0eed5-133">Die Menge der ungültigen Zeichen kann je nach Dateisystem variieren.</span><span class="sxs-lookup"><span data-stu-id="0eed5-133">The set of invalid characters can vary by file system.</span></span> <span data-ttu-id="0eed5-134">Normalerweise zählen zu den ungültigen Zeichen das Anführungszeichen ("), das Kleiner-als-Zeichen (<) und der senkrechte Strich (|).</span><span class="sxs-lookup"><span data-stu-id="0eed5-134">Typically, invalid characters are the quotation mark ("), less than (<) character, and pipe (|) character.</span></span>  
  
 <span data-ttu-id="0eed5-135">Um Pakete zu verwalten, die in einer benannten Instanz oder einer Remoteinstanz von [!INCLUDE[ssDE](../includes/ssde-md.md)]gespeichert sind, müssen Sie die Konfigurationsdatei jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="0eed5-135">However, you will have to modify the configuration file to manage packages that are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="0eed5-136">Wenn Sie die Konfigurationsdatei nicht aktualisieren, können Sie mit dem **Objekt-Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] keine Pakete anzeigen, die in der msdb-Datenbank auf der benannten Instanz oder der Remoteinstanz gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0eed5-136">If you do not update the configuration file, you cannot use **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view packages that are stored in the msdb database on the named instance or the remote instance.</span></span> <span data-ttu-id="0eed5-137">Wenn Sie versuchen, diese Pakete mit dem **Objekt-Explorer** anzuzeigen, erhalten Sie die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="0eed5-137">If you try to use **Object Explorer** to view these packages, you receive the following error message:</span></span>  
  
 `Failed to retrieve data for this request. (Microsoft.SqlServer.SmoEnum)`  
  
 `The SQL Server specified in Integration Services service configuration is not present or is not available. This might occur when there is no default instance of SQL Server on the computer. For more information, see the topic "Configuring the Integration Services Service" in SQL Server 2008 Books Online.`  
  
 `Login Timeout Expired`  
  
 `An error has occurred while establishing a connection to the server. When connecting to SQL Server 2008, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.`  
  
 `Named Pipes Provider: Could not open a connection to SQL Server [2]. (MsDtsSvr).`  
  
 <span data-ttu-id="0eed5-138">Um die Konfigurationsdatei für den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst zu ändern, verwenden Sie einen Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="0eed5-138">To modify the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, you use a text editor.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0eed5-139">Nachdem Sie die Dienstkonfigurationsdatei geändert haben, müssen Sie den Dienst neu starten, damit Sie die aktualisierte Dienstkonfiguration verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0eed5-139">After you modify the service configuration file, you must restart the service to use the updated service configuration.</span></span>  
  
### <a name="modified-configuration-file-example"></a><span data-ttu-id="0eed5-140">Beispiel für eine geänderte Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0eed5-140">Modified Configuration File Example</span></span>  
 <span data-ttu-id="0eed5-141">Im folgenden Beispiel wird eine geänderte Konfigurationsdatei für [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0eed5-141">The following example shows a modified configuration file for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="0eed5-142">Diese Datei dient für eine benannte Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mit dem Namen `InstanceName` auf dem Server `ServerName`.</span><span class="sxs-lookup"><span data-stu-id="0eed5-142">This file is for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] called `InstanceName` on a server named `ServerName`.</span></span>  
  
 <span data-ttu-id="0eed5-143">**Beispiel einer geänderten Konfigurationsdatei für eine benannte Instanz von SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0eed5-143">**Example of a Modified Configuration File for a Named Instance of SQL Server**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>ServerName\InstanceName</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file-location"></a><span data-ttu-id="0eed5-144">Änderung des Speicherorts der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0eed5-144">Modification of the Configuration File Location</span></span>  
<span data-ttu-id="0eed5-145">Der Registrierungsschlüssel **HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL server\120\ssis\serviceconfigfile** gibt den Speicherort und den Namen für die Konfigurationsdatei an, die vom- [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0eed5-145">The Registry key **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\ServiceConfigFile** specifies the location and name for the configuration file that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service uses.</span></span> <span data-ttu-id="0eed5-146">Der Standardwert des Registrierungsschlüssels lautet **c:\Programme\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span><span class="sxs-lookup"><span data-stu-id="0eed5-146">The default value of the Registry key is **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span></span> <span data-ttu-id="0eed5-147">Sie können den Wert des Registrierungsschlüssels aktualisieren, um einen anderen Namen und Speicherort für die Konfigurationsdatei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0eed5-147">You can update the value of the Registry key to use a different name and location for the configuration file.</span></span> <span data-ttu-id="0eed5-148">Beachten Sie, dass die Versionsnummer im Pfad (120 für SQL Server [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] ) je nach SQL Server Version variiert.</span><span class="sxs-lookup"><span data-stu-id="0eed5-148">Note that the version number in the path (120 for SQL Server  [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)]) will vary depending on the SQL Server version.</span></span> 
  
  
> [!CAUTION]  
>  <span data-ttu-id="0eed5-149">Unsachgemäßes Bearbeiten der Registrierung kann zu schwerwiegenden Problemen führen, die ein Neuinstallieren des Betriebssystems erforderlich machen können.</span><span class="sxs-lookup"><span data-stu-id="0eed5-149">Incorrectly editing the Registry can cause serious problems that may require you to reinstall your operating system.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="0eed5-150">garantiert nicht, dass Probleme, die durch unsachgemäßes Bearbeiten der Registrierung entstehen, behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="0eed5-150">cannot guarantee that problems resulting from editing the Registry incorrectly can be resolved.</span></span> <span data-ttu-id="0eed5-151">Sichern Sie vor dem Bearbeiten der Registrierung alle wichtigen Daten.</span><span class="sxs-lookup"><span data-stu-id="0eed5-151">Before editing the Registry, back up any valuable data.</span></span> <span data-ttu-id="0eed5-152">Weitere Informationen zum Sichern, Wiederherstellen und Bearbeiten der Registrierung finden Sie im [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base-Artikel [Windows-Registrierungsinformationen für Benutzer mit fortgeschrittenen Kenntnissen](https://support.microsoft.com/kb/256986).</span><span class="sxs-lookup"><span data-stu-id="0eed5-152">For information about how to back up, restore, and edit the Registry, see the [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base article, [Description of the Microsoft Windows registry](https://support.microsoft.com/kb/256986).</span></span>  
  
 <span data-ttu-id="0eed5-153">Die Konfigurationsdatei wird beim Starten des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Diensts geladen.</span><span class="sxs-lookup"><span data-stu-id="0eed5-153">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service loads the configuration file when the service is started.</span></span> <span data-ttu-id="0eed5-154">Bei Änderungen am Registrierungseintrag ist es erforderlich, den Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="0eed5-154">Any changes to the Registry entry require that the service be restarted.</span></span>  
  
  
