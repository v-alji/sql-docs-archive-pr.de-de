---
title: Allgemeine Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- IdleConnectionTimeout property
- InstanceVisible property
- TempDir property
- AdminTimeout property
- MinIdleSessionTimeout property
- MaxIdleSessionTimeout property
- IdleOrphanSessionTimeout property
- BackupDir property
- CommitTimeout property
- ExternalCommandTimeout property
- Enabled property
- ForceCommitTimeout property
- Port property
- CoordinatorShutdownMode property
- ServerTimeout property
- AllowedBrowsingFolders property
- CoordinatorCancelCount property
- DataDir property
- CoordinatorQueryMaxThreads property
- CoordinatorExecutionMode property
- ExternalConnectionTimeout property
- CollationName property
- EnableFast1033Locale property
- CoordinatorBuildMaxThreads property
- Language property
- StatisticsStoreSize property
- RepositoryConnectionString property
ms.assetid: 88a8117c-396a-469f-a62d-c6f262504021
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca746a1bb57e84cf0f6a8f47622b118c7180eb1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727178"
---
# <a name="general-properties"></a><span data-ttu-id="8bd91-102">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8bd91-102">General Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="8bd91-103">unterstützt die in den folgenden Tabellen aufgeführten Servereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8bd91-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="8bd91-104">In diesem Thema werden die Servereigenschaften in der Datei msmdsrv.ini dokumentiert, die nicht in einem bestimmten Abschnitt wie Sicherheit, Netzwerk oder ThreadPool behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-104">This topic documents those server properties in the msmdsrv.ini file that are not otherwise included in a specific section, such as Security, Network, or ThreadPool.</span></span> <span data-ttu-id="8bd91-105">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8bd91-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="8bd91-106">**Gilt für:** Mehrdimensionaler und tabellarischer Server Modus, sofern nichts anderes angegeben ist</span><span class="sxs-lookup"><span data-stu-id="8bd91-106">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="8bd91-107">Nicht spezifische Kategorie</span><span class="sxs-lookup"><span data-stu-id="8bd91-107">Non-Specific Category</span></span>  
 `AdminTimeout`  
 <span data-ttu-id="8bd91-108">Eine ganze 32-Bit-Zahl mit Vorzeichen, die den Administratortimeoutwert in Sekunden definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-108">A signed 32-bit integer property that defines the administrator timeout in seconds.</span></span> <span data-ttu-id="8bd91-109">Hierbei handelt es sich um eine erweiterte Eigenschaft, die nicht ohne die Unterstützung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8bd91-109">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="8bd91-110">Der Standardwert für diese Eigenschaft ist Null (0), d. h. es findet kein Timeout statt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-110">The default value for this property is zero (0), which indicates there is no timeout.</span></span>  
  
 `AllowedBrowsingFolders`  
 <span data-ttu-id="8bd91-111">Eine Zeichenfolgeneigenschaft, die in einer getrennten Liste die Ordner angibt, die durchsucht werden können, wenn Dateien in Analysis Services-Dialogfeldern gespeichert, geöffnet und gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-111">A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes.</span></span> <span data-ttu-id="8bd91-112">Das Analysis Services-Dienstkonto muss Lese- und Schreibberechtigungen für alle Ordner haben, die Sie der Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bd91-112">The Analysis Services service account must have read and write permissions to any folders that you add to the list.</span></span>  
  
 `BackupDir`  
 <span data-ttu-id="8bd91-113">Eine Zeichen folgen Eigenschaft, die den Namen des Verzeichnisses identifiziert, in dem Sicherungsdateien standardmäßig gespeichert werden, im Fall, dass kein Pfad als Teil des Backup-Befehls angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bd91-113">A string property that identifies the name of the directory where backup files are stored by default, in the event a path is not specified as part of the Backup command.</span></span>  
  
 `CollationName`  
 <span data-ttu-id="8bd91-114">Eine Zeichenfolge, die die Serversortierung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-114">A string property that identifies the server collation.</span></span> <span data-ttu-id="8bd91-115">Weitere Informationen finden Sie unter [Sprachen und Sortierungen &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8bd91-115">For more information, see [Languages and Collations &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span></span>  
  
 `CommitTimeout`  
 <span data-ttu-id="8bd91-116">Eine Ganzzahleigenschaft, die angibt, wie lange der Server wartet (in Millisekunden), um eine Schreibsperre für den Commit einer Transaktion abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8bd91-116">An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock for the purpose of committing a transaction.</span></span> <span data-ttu-id="8bd91-117">Eine Wartezeit ist oftmals erforderlich, da der Server darauf warten muss, dass andere Sperren freigegeben werden, bevor eine Schreibsperre verwendet werden kann, die einen Commit für die Transaktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-117">A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.</span></span>  
  
 <span data-ttu-id="8bd91-118">Der Standardwert für diese Eigenschaft ist 0 (null), d. h., der Server wartet unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-118">The default value for this property is zero (0), which indicates that the server will wait indefinitely.</span></span> <span data-ttu-id="8bd91-119">Weitere Informationen zu sperrenbezogenen Eigenschaften finden Sie im [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(SQL Server 2008 R2 Analysis Services-Vorgangshandbuch).</span><span class="sxs-lookup"><span data-stu-id="8bd91-119">For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorBuildMaxThreads`  
 <span data-ttu-id="8bd91-120">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von Threads zum Erstellen von Partitionsindizes definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-120">A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes.</span></span> <span data-ttu-id="8bd91-121">Durch Erhöhen dieses Werts kann die Partitionsindizierung auf Kosten der Speicherauslastung beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-121">Increase this value in order to speed-up partition indexing, at the cost of memory usage.</span></span> <span data-ttu-id="8bd91-122">Weitere Informationen zu dieser Eigenschaft finden Sie im [SQL Server 2008 R2 Analysis Services-Vorgangshandbuch](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="8bd91-122">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorCancelCount`  
 <span data-ttu-id="8bd91-123">Eine ganze 32-Bit-Zahl mit Vorzeichen, die definiert, wie häufig der Server überprüfen soll, ob ein Cancel-Ereignis aufgetreten ist (basierend auf der Anzahl interner Iterationen).</span><span class="sxs-lookup"><span data-stu-id="8bd91-123">A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count).</span></span> <span data-ttu-id="8bd91-124">Verringern Sie diese Zahl, um häufiger, jedoch zu Lasten der allgemeinen Leistung, eine Überprüfung auf Cancel-Ereignisse durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8bd91-124">Decrease this number in order to check for Cancel more frequently, at the expense of general performance.</span></span>  
  
 <span data-ttu-id="8bd91-125">`CoordinatorCancelCount` wird im tabellarischen Servermodus ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-125">`CoordinatorCancelCount` is ignored in tabular server mode.</span></span>  
  
 `CoordinatorExecutionMode`  
 <span data-ttu-id="8bd91-126">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von parallelen Servervorgängen definiert, einschließlich von Verarbeitungs- und Abfragevorgängen.</span><span class="sxs-lookup"><span data-stu-id="8bd91-126">A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations.</span></span> <span data-ttu-id="8bd91-127">Null (0) bedeutet, dass der Server basierend auf einem internen Algorithmus selbst entscheidet.</span><span class="sxs-lookup"><span data-stu-id="8bd91-127">Zero (0) indicates that the server will decide, based on an internal algorithm.</span></span> <span data-ttu-id="8bd91-128">Eine positive Zahl zeigt die maximale Anzahl von Vorgängen insgesamt an.</span><span class="sxs-lookup"><span data-stu-id="8bd91-128">A positive number indicates the maximum number of operations in total.</span></span> <span data-ttu-id="8bd91-129">Eine negative Zahl (mit umgekehrtem Vorzeichen) zeigt die maximale Anzahl von Vorgängen pro Prozessor an.</span><span class="sxs-lookup"><span data-stu-id="8bd91-129">A negative number, with the sign reversed, indicates the maximum number of operations per processor.</span></span>  
  
 <span data-ttu-id="8bd91-130">`CoordinatorExecutionMode` wird im tabellarischen Servermodus ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-130">`CoordinatorExecutionMode` is ignored in tabular server mode.</span></span>  
  
 <span data-ttu-id="8bd91-131">Der Standardwert für diese Eigenschaft ist -4. Dies bedeutet, der Server ist auf 4 parallele Vorgänge pro Prozessor eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-131">The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor.</span></span> <span data-ttu-id="8bd91-132">Weitere Informationen zu dieser Eigenschaft finden Sie im [SQL Server 2008 R2 Analysis Services-Vorgangshandbuch](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="8bd91-132">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorQueryMaxThreads`  
 <span data-ttu-id="8bd91-133">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von Threads pro Partitionssegment während der Abfrageauflösung definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-133">A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution.</span></span> <span data-ttu-id="8bd91-134">Je kleiner die Anzahl von gleichzeitigen Benutzern ist, umso höher kann dieser Wert sein, jedoch auf Kosten des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="8bd91-134">The fewer the number of concurrent users, the higher this value can be, at the cost of memory.</span></span> <span data-ttu-id="8bd91-135">Umgekehrt muss bei einer großen Anzahl von gleichzeitigen Benutzern der Wert möglicherweise reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-135">Conversely, it may need to be lowered if there are a large number of concurrent users.</span></span>  
  
 `CoordinatorShutdownMode`  
 <span data-ttu-id="8bd91-136">Eine boolesche Eigenschaft, die den Modus zum Herunterfahren des Koordinators definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-136">A Boolean property that defines coordinator shutdown mode.</span></span> <span data-ttu-id="8bd91-137">Hierbei handelt es sich um eine erweiterte Eigenschaft, die nicht ohne die Unterstützung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8bd91-137">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataDir`  
 <span data-ttu-id="8bd91-138">Eine Zeichenfolge, die den Namen des Verzeichnisses zum Speichern von Daten identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-138">A string property that identifies the name of the directory where data is stored.</span></span>  
  
 `DeploymentMode`  
 <span data-ttu-id="8bd91-139">Bestimmt den operativen Kontext einer Analysis Services-Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="8bd91-139">Determines the operational context of an Analysis Services server instance.</span></span> <span data-ttu-id="8bd91-140">Diese Eigenschaft wird in Dialogfeldern, Meldungen und Dokumentation als "Server Modus" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8bd91-140">This property is referred to as 'server mode' in dialog boxes, messages, and documentation.</span></span> <span data-ttu-id="8bd91-141">Diese Eigenschaft wird basierend auf dem Servermodus, den Sie beim Installieren von Analysis Services ausgewählt haben, von SQL Server-Setup konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-141">This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services.</span></span> <span data-ttu-id="8bd91-142">Diese Eigenschaft sollte nur intern berücksichtigt und immer der vom Setup angegebene Wert verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-142">This property should be considered internal only, always using the value specified by Setup.</span></span>  
  
 <span data-ttu-id="8bd91-143">Für diese Eigenschaften gibt es u. a. folgende gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="8bd91-143">Valid values for this property include the following:</span></span>  
  
|<span data-ttu-id="8bd91-144">Wert</span><span class="sxs-lookup"><span data-stu-id="8bd91-144">Value</span></span>|<span data-ttu-id="8bd91-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bd91-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd91-146">0</span><span class="sxs-lookup"><span data-stu-id="8bd91-146">0</span></span>|<span data-ttu-id="8bd91-147">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-147">This is the default value.</span></span> <span data-ttu-id="8bd91-148">Der mehrdimensionale Modus wird angegeben. Er dient zur Verwaltung von mehrdimensionalen Datenbanken, die MOLAP, HOLAP und ROLAP-Speicher sowie Data Mining-Modelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-148">It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.</span></span>|  
|<span data-ttu-id="8bd91-149">1</span><span class="sxs-lookup"><span data-stu-id="8bd91-149">1</span></span>|<span data-ttu-id="8bd91-150">Gibt Analysis Services-Instanzen an, die als Teil einer PowerPivot für SharePoint-Bereitstellung installiert waren.</span><span class="sxs-lookup"><span data-stu-id="8bd91-150">Specifies Analysis Services instances that were installed as part of a PowerPivot for SharePoint deployment.</span></span> <span data-ttu-id="8bd91-151">Ändern Sie die Bereitstellungsmoduseigenschaft der Analysis Services-Instanz nicht, die Teil einer PowerPivot für SharePoint-Installation ist.</span><span class="sxs-lookup"><span data-stu-id="8bd91-151">Do not change the deployment mode property of Analysis Services instance that is part of a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="8bd91-152">Wenn Sie den Modus ändern, werden PowerPivot-Daten nicht mehr auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-152">PowerPivot data will no longer run on the server if you change the mode.</span></span>|  
|<span data-ttu-id="8bd91-153">2</span><span class="sxs-lookup"><span data-stu-id="8bd91-153">2</span></span>|<span data-ttu-id="8bd91-154">Gibt den Tabellenmodus an, der zum Hosten von Tabellenmodelldatenbanken dient, die Speicher im Arbeitsspeicher oder DirectQuery-Speicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-154">Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.</span></span>|  
  
 <span data-ttu-id="8bd91-155">Die Modi schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="8bd91-155">Each mode is exclusive of the other.</span></span> <span data-ttu-id="8bd91-156">Ein Server, der für den Tabellenmodus konfiguriert ist, kann keine Analysis Services-Datenbanken ausführen, die Cubes und Dimensionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8bd91-156">A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions.</span></span> <span data-ttu-id="8bd91-157">Bei Unterstützung durch die zugrunde liegende Computerhardware können Sie mehrere Instanzen von Analysis Services auf demselben Computer installieren und jede Instanz für einen anderen Bereitstellungsmodus konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8bd91-157">If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode.</span></span> <span data-ttu-id="8bd91-158">Beachten Sie, dass Analysis Services eine ressourcenintensive Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="8bd91-158">Remember that Analysis Services is a resource intensive application.</span></span> <span data-ttu-id="8bd91-159">Die Bereitstellung mehrerer Instanzen auf demselben System wird nur für High-End-Server empfohlen.</span><span class="sxs-lookup"><span data-stu-id="8bd91-159">Deploying multiple instances on the same system is recommended only for high-end servers.</span></span>  
  
 `EnableFast1033Locale`  
 <span data-ttu-id="8bd91-160">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8bd91-160">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ExternalCommandTimeout`  
 <span data-ttu-id="8bd91-161">Eine Ganzzahleigenschaft, die den Timeoutwert (in Sekunden) für Befehle definiert, die an externe Server ausgegeben werden, einschließlich relationaler Datenquellen und externer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Server.</span><span class="sxs-lookup"><span data-stu-id="8bd91-161">An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="8bd91-162">Der Standardwert für diese Eigenschaft ist 3.600 (Sekunden).</span><span class="sxs-lookup"><span data-stu-id="8bd91-162">The default value for this property is 3600 (seconds).</span></span>  
  
 `ExternalConnectionTimeout`  
 <span data-ttu-id="8bd91-163">Eine Ganzzahleigenschaft, die den Timeoutwert (in Sekunden) für das Erstellen von Verbindungen mit externen Servern definiert, einschließlich relationaler Datenquellen und externer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Server.</span><span class="sxs-lookup"><span data-stu-id="8bd91-163">An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span> <span data-ttu-id="8bd91-164">Diese Eigenschaft wird ignoriert, wenn ein Verbindungstimeout für die Verbindungszeichenfolge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bd91-164">This property is ignored if a connection timeout is specified on the connection string.</span></span>  
  
 <span data-ttu-id="8bd91-165">Der Standardwert für diese Eigenschaft ist 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-165">The default value for this property is 60 (seconds).</span></span>  
  
 `ForceCommitTimeout`  
 <span data-ttu-id="8bd91-166">Eine Ganzzahleigenschaft, die angibt, wie lange (Dauer in Millisekunden) ein Schreib-Commit-Vorgang warten soll, bevor andere Befehle abgebrochen werden, die dem aktuellen Befehl vorausgingen, einschließlich momentan ausgeführter Abfragen.</span><span class="sxs-lookup"><span data-stu-id="8bd91-166">An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress.</span></span> <span data-ttu-id="8bd91-167">Dadurch kann die Commit-Transaktion fortgesetzt werden, da Vorgänge mit niedrigerer Priorität, z. B. Abfragen, abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-167">This allows the commit transaction to proceed by canceling lower priority operations, such as queries.</span></span>  
  
 <span data-ttu-id="8bd91-168">Der Standardwert für diese Eigenschaft ist 30 Sekunden (30.000 Millisekunden), d. h., dass für andere Befehle erst dann ein Timeout erzwungen wird, wenn die Commit-Transaktion 30 Sekunden lang gewartet hat.</span><span class="sxs-lookup"><span data-stu-id="8bd91-168">The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8bd91-169">Abfragen und Prozesse, die von diesem Ereignis abgebrochen wurden, geben die folgende Fehlermeldung aus: „`Server: The operation has been cancelled`“.</span><span class="sxs-lookup"><span data-stu-id="8bd91-169">Queries and processes cancelled by this event will report the following error message: "`Server: The operation has been cancelled`"</span></span>  
  
 <span data-ttu-id="8bd91-170">Weitere Informationen zu dieser Eigenschaft finden Sie im [SQL Server 2008 R2 Analysis Services-Vorgangshandbuch](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="8bd91-170">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8bd91-171">`ForceCommitTimeout` gilt für Cubeverarbeitungsbefehle und Rückschreibevorgänge.</span><span class="sxs-lookup"><span data-stu-id="8bd91-171">`ForceCommitTimeout` applies to cube processing commands and to writeback operations.</span></span>  
  
 `IdleConnectionTimeout`  
 <span data-ttu-id="8bd91-172">Eine Ganzzahleigenschaft, die ein Timeout für inaktive Verbindungen angibt (in Sekunden).</span><span class="sxs-lookup"><span data-stu-id="8bd91-172">An integer property that specifies a timeout, in seconds, for connections that are inactive.</span></span>  
  
 <span data-ttu-id="8bd91-173">Der Standardwert für diese Eigenschaft ist Null (0), d. h. bei Verbindungen im Leerlauf erfolgt kein Timeout.</span><span class="sxs-lookup"><span data-stu-id="8bd91-173">The default value for this property is zero (0), which indicates that idle connections will not be timed out.</span></span>  
  
 `IdleOrphanSessionTimeout`  
 <span data-ttu-id="8bd91-174">Eine Ganzzahleigenschaft, die definiert, wie lange verwaiste Sitzungen im Arbeitsspeicher des Servers beibehalten werden (Dauer in Sekunden).</span><span class="sxs-lookup"><span data-stu-id="8bd91-174">An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory.</span></span> <span data-ttu-id="8bd91-175">Eine verwaiste Sitzung ist eine Sitzung, die keine zugeordnete Verbindung besitzt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-175">An orphaned session is one that no longer has an associated connection.</span></span> <span data-ttu-id="8bd91-176">Der Standardwert ist 120 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-176">The default is 120 seconds.</span></span>  
  
 `InstanceVisible`  
 <span data-ttu-id="8bd91-177">Eine boolesche Eigenschaft, die angibt, ob die Serverinstanz sichtbar ist, um Instanzanforderungen des SQL Server-Browserdiensts zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8bd91-177">A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service.</span></span> <span data-ttu-id="8bd91-178">Der Standardwert ist True.</span><span class="sxs-lookup"><span data-stu-id="8bd91-178">The default is True.</span></span> <span data-ttu-id="8bd91-179">Wenn Sie False festlegen, ist die Instanz für den SQL Server-Browser nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8bd91-179">If you set it to false, the instance is not visible to SQL Server Browser.</span></span>  
  
 `Language`  
 <span data-ttu-id="8bd91-180">Eine Zeichenfolge, die die Sprache definiert, auch für Fehlermeldungen und Zahlenformatierung.</span><span class="sxs-lookup"><span data-stu-id="8bd91-180">A string property that defines the language, including error messages and number formatting.</span></span> <span data-ttu-id="8bd91-181">Diese Eigenschaft überschreibt die CollationName-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8bd91-181">This property overrides the CollationName property.</span></span>  
  
 <span data-ttu-id="8bd91-182">Der Standardwert für diese Eigenschaft ist leer. Dies bedeutet, dass die Sprache durch die CollationName-Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8bd91-182">The default value for this property is blank, which indicates that the CollationName property defines the language.</span></span>  
  
 `LogDir`  
 <span data-ttu-id="8bd91-183">Eine Zeichenfolge, die den Namen des Verzeichnisses identifiziert, das die Serverprotokolle enthält.</span><span class="sxs-lookup"><span data-stu-id="8bd91-183">A string property that identifies the name of the directory that contains server logs.</span></span> <span data-ttu-id="8bd91-184">Diese Eigenschaft gilt nur, wenn für die Protokollierung Dateien auf dem Datenträger anstelle von Datenbanktabellen (das Standardverhalten) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-184">This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).</span></span>  
  
 `MaxIdleSessionTimeout`  
 <span data-ttu-id="8bd91-185">Eine Ganzzahleigenschaft, die den maximalen Timeoutwert für Verbindungen im Leerlauf in Sekunden definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-185">An integer property that defines the maximum idle session timeout, in seconds.</span></span> <span data-ttu-id="8bd91-186">Der Standardwert ist 0 (null) und zeigt an, dass für Sitzungen nie ein Timeout auftritt. Allerdings werden Sitzungen im Leerlauf weiterhin entfernt, wenn der Server Ressourceneinschränkungen unterliegt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-186">The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.</span></span>  
  
 `MinIdleSessionTimeout`  
 <span data-ttu-id="8bd91-187">Eine Ganzzahleigenschaft, die den minimalen Timeoutwert für Verbindungen im Leerlauf in Sekunden definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd91-187">An integer property that defines the minimum time, in seconds, that idle sessions will timeout.</span></span> <span data-ttu-id="8bd91-188">Der Standardwert ist 2.700 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-188">The default is 2700 seconds.</span></span> <span data-ttu-id="8bd91-189">Nach Ablauf dieser Zeit kann der Server die Sitzung im Leerlauf beenden, sofern der belegte Arbeitsspeicher benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="8bd91-189">After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.</span></span>  
  
 `Port`  
 <span data-ttu-id="8bd91-190">Eine Ganzzahleigenschaft, die die Portnummer definiert, an der der Server auf Clientverbindungen lauscht.</span><span class="sxs-lookup"><span data-stu-id="8bd91-190">An integer property that defines the port number on which server will listen for client connections.</span></span> <span data-ttu-id="8bd91-191">Wird diese Eigenschaft nicht festgelegt, sucht der Server dynamisch nach dem ersten freien Port.</span><span class="sxs-lookup"><span data-stu-id="8bd91-191">If not set, server dynamically finds first unused port.</span></span>  
  
 <span data-ttu-id="8bd91-192">Der Standardwert für diese Eigenschaft ist Null (0), d. h. es wird standardmäßig Port 2383 verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bd91-192">The default value for this property is zero (0), which in turn defaults to port 2383.</span></span> <span data-ttu-id="8bd91-193">Weitere Informationen zur Portkonfiguration finden Sie unter [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="8bd91-193">For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
 `ServerTimeout`  
 <span data-ttu-id="8bd91-194">Eine Ganzzahl, die das Timeout für Abfragen definiert (in Sekunden).</span><span class="sxs-lookup"><span data-stu-id="8bd91-194">An integer that defines the timeout, in seconds, for queries.</span></span> <span data-ttu-id="8bd91-195">Der Standardwert beträgt 3600 Sekunden (oder 60 Minuten).</span><span class="sxs-lookup"><span data-stu-id="8bd91-195">The default is 3600 seconds (or 60 minutes).</span></span> <span data-ttu-id="8bd91-196">Null (0) gibt an, dass für Abfragen kein Timeout erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="8bd91-196">Zero (0) specifies that no queries will timeout.</span></span>  
  
 `TempDir`  
 <span data-ttu-id="8bd91-197">Eine Zeichenfolgeneigenschaft, die den Ort zum Speichern von temporären Dateien angibt, die während Verarbeitung, Wiederherstellung und anderer Vorgänge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bd91-197">A string property that specifies the location for storing temporary files used during processing, restoring, and other operations.</span></span> <span data-ttu-id="8bd91-198">Der Standardwert für diese Eigenschaft wird von Setup bestimmt.</span><span class="sxs-lookup"><span data-stu-id="8bd91-198">The default value for this property is determined by setup.</span></span> <span data-ttu-id="8bd91-199">Wenn nichts angegeben wird, wird standardmäßig das Verzeichnis Data verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bd91-199">If not specified, the default is the Data directory.</span></span>  
  
## <a name="requestprioritization-category"></a><span data-ttu-id="8bd91-200">RequestPrioritization-Kategorie</span><span class="sxs-lookup"><span data-stu-id="8bd91-200">RequestPrioritization Category</span></span>  
 `Enabled`  
 <span data-ttu-id="8bd91-201">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8bd91-201">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `StatisticsStoreSize`  
 <span data-ttu-id="8bd91-202">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8bd91-202">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd91-203">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8bd91-203">See Also</span></span>  
 <span data-ttu-id="8bd91-204">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="8bd91-204">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="8bd91-205">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="8bd91-205">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
