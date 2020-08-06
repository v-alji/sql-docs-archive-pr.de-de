---
title: Verwalten von DQS-Protokolldateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ca85772b8cc8aca41b75ad05d028bc444f280378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621682"
---
# <a name="manage-dqs-log-files"></a><span data-ttu-id="6b387-102">Verwalten von DQS-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="6b387-102">Manage DQS Log Files</span></span>
  [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] <span data-ttu-id="6b387-103">(DQS)-Protokolldateien unterstützen Sie bei der Diagnose und bei der Problembehandlung mit den Komponenten [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]und [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b387-103">(DQS) log files help you in diagnosing and troubleshooting issue with [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="6b387-104">Für [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]und die [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)]werden separate Protokolldateien generiert.</span><span class="sxs-lookup"><span data-stu-id="6b387-104">Separate log files are generated for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
 <span data-ttu-id="6b387-105">Sie können die Einstellung des Protokollschweregrads für [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Funktionen und -Module mithilfe von [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6b387-105">You can use [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] to configure the log severity setting for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] features and modules.</span></span> <span data-ttu-id="6b387-106">Darüber hinaus können Sie auch andere (erweiterte) Einstellungen für die DQS-Protokolldateien konfigurieren, indem Sie die Einstellungen für die DQS-Protokollkonfiguration in der DQS_MAIN-Datenbank und in einer XML-Datei auf dem [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Computer manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="6b387-106">Additionally, you can also configure some other (advanced) settings for the DQS log files by manually changing the DQS log configuration settings in the DQS_MAIN database and an XML file on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer.</span></span>  
  
##  <a name="data-quality-server-log-file"></a><a name="DQSServer"></a><span data-ttu-id="6b387-107">Data Quality Server-Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="6b387-107">Data Quality Server Log File</span></span>  
 <span data-ttu-id="6b387-108">Die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokolldatei, DQServerLog.DQS_MAIN.log, enthält Protokolle der Aktivitäten, die in [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6b387-108">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, DQServerLog.DQS_MAIN.log, includes logs of activities that are run on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="6b387-109">Wenn Sie die Standardinstanz von SQL Server installiert haben, ist die Protokolldatei DQServerLog.DQS_MAIN.log unter C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b387-109">If you installed the default instance of SQL Server, the DQServerLog.DQS_MAIN.log file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span></span> <span data-ttu-id="6b387-110">Die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokolldatei enthält die folgenden Informationen, die jeweils durch ein Pipezeichen (|) begrenzt sind:</span><span class="sxs-lookup"><span data-stu-id="6b387-110">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file contains the following pieces of information, each delimited by a pipe (|):</span></span>  
  
-   <span data-ttu-id="6b387-111">Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="6b387-111">Date and time</span></span>  
  
-   <span data-ttu-id="6b387-112">Threadname</span><span class="sxs-lookup"><span data-stu-id="6b387-112">Thread name</span></span>  
  
-   <span data-ttu-id="6b387-113">Thread-ID</span><span class="sxs-lookup"><span data-stu-id="6b387-113">Thread ID</span></span>  
  
-   <span data-ttu-id="6b387-114">Protokollschweregrad (FATAL, ERROR, WARN, INFO und DEBUG)</span><span class="sxs-lookup"><span data-stu-id="6b387-114">Log severity (FATAL, ERROR, WARN, INFO, and DEBUG)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b387-115">Der DEBUG-Protokollierungsschweregrad entspricht der Option Ausführlich.</span><span class="sxs-lookup"><span data-stu-id="6b387-115">The DEBUG logging severity is same as Verbose.</span></span>  
  
-   <span data-ttu-id="6b387-116">UID (interne DQS-Infrastruktur-ID)</span><span class="sxs-lookup"><span data-stu-id="6b387-116">UID (internal DQS infrastructure ID)</span></span>  
  
-   <span data-ttu-id="6b387-117">Namespace</span><span class="sxs-lookup"><span data-stu-id="6b387-117">Namespace</span></span>  
  
-   <span data-ttu-id="6b387-118">Klasse und Methode</span><span class="sxs-lookup"><span data-stu-id="6b387-118">Class and method</span></span>  
  
-   <span data-ttu-id="6b387-119">Meldung</span><span class="sxs-lookup"><span data-stu-id="6b387-119">Message</span></span>  
  
 <span data-ttu-id="6b387-120">Neben diesen Informationen werden in der Protokolldatei auch Informationen zur Anwendungsversion, zum Computernamen, Benutzernamen und Betriebssystem angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b387-120">Along with these, the log file also displays information about the application version, computer name, user name, and operating system.</span></span>  
  
 <span data-ttu-id="6b387-121">Ein Beispieleintrag in der [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokolldatei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6b387-121">A sample entry in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file looks like the following:</span></span>  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 <span data-ttu-id="6b387-122">Die Datei DQServerLog.DQS_MAIN.log [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] ist eine Rolldatei. Eine neue Protokolldatei wird erstellt, sobald die vorhandene Protokolldatei die maximale Rolldateigröße überschreitet, die in den Konfigurationseinstellungen des -Protokolls angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6b387-122">The DQServerLog.DQS_MAIN.log file is a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="6b387-123">Weitere Informationen finden Sie unter [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="6b387-123">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="data-quality-client-log-file"></a><a name="DQSClient"></a><span data-ttu-id="6b387-124">Data Quality-Client Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="6b387-124">Data Quality Client Log File</span></span>  
 <span data-ttu-id="6b387-125">Die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolldatei, DQClientLog.log, enthält die clientseitigen Protokolle.</span><span class="sxs-lookup"><span data-stu-id="6b387-125">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file, DQClientLog.log, includes the client side logs.</span></span> <span data-ttu-id="6b387-126">Die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolldatei ist unter %APPDATA%\SSDQS\Log verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b387-126">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="6b387-127">Die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolldatei enthält ähnliche Informationen wie die Serverprotokolldatei, jedoch auf Clientseite.</span><span class="sxs-lookup"><span data-stu-id="6b387-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file contains similar set of information as in the server log file, but for the client side.</span></span>  
  
 <span data-ttu-id="6b387-128">Wie die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokolldatei ist auch die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolldatei eine Rolldatei, und eine neue Protokolldatei wird erstellt, sobald die vorhandene Protokolldatei die maximale Rolldateigröße überschreitet, die in den Konfigurationseinstellungen des [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolls angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6b387-128">As with the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is also a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log configuration settings.</span></span> <span data-ttu-id="6b387-129">Weitere Informationen finden Sie unter [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="6b387-129">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="dqs-cleansing-component-log-file"></a><a name="DQSCleansing"></a><span data-ttu-id="6b387-130">Protokolldatei der DQS-Bereinigungs Komponente</span><span class="sxs-lookup"><span data-stu-id="6b387-130">DQS Cleansing Component Log File</span></span>  
 <span data-ttu-id="6b387-131">Die [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] -Protokolldatei, DQSSSISLog.log, enthält Protokolle der Aktivitäten, die mithilfe der [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6b387-131">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file, DQSSSISLog.log, includes logs of activities performed using the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="6b387-132">Die Protokolldatei der Komponente [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] ist unter %APPDATA%\SSDQS\Log verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b387-132">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] component log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="6b387-133">Die [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] -Protokolldatei enthält ähnliche Informationen wie die Serverprotokolldatei, jedoch für die [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b387-133">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file contains similar set of information as in the server log file, but for the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
##  <a name="related-tasks"></a><a name="RT"></a> <span data-ttu-id="6b387-134">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6b387-134">Related Tasks</span></span>  
  
|<span data-ttu-id="6b387-135">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6b387-135">Task Description</span></span>|<span data-ttu-id="6b387-136">Thema</span><span class="sxs-lookup"><span data-stu-id="6b387-136">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="6b387-137">Beschreibt, wie die Einstellungen des Protokollschweregrads für DQS-Protokolldateien mit [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6b387-137">Describes how to configure log severity settings for DQS log files using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="6b387-138">Konfigurieren von Schweregraden für DQS-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="6b387-138">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|<span data-ttu-id="6b387-139">Beschreibt, wie die erweiterten Einstellungen für DQS-Protokolldateien manuell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6b387-139">Describes how to manually configure advanced settings for DQS log files.</span></span>|[<span data-ttu-id="6b387-140">Konfigurieren der erweiterten Einstellungen für DQS-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="6b387-140">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a><span data-ttu-id="6b387-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b387-141">See Also</span></span>  
 [<span data-ttu-id="6b387-142">DQS-Administration</span><span class="sxs-lookup"><span data-stu-id="6b387-142">DQS Administration</span></span>](../../2014/data-quality-services/dqs-administration.md)  
  
  
