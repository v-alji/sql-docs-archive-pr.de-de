---
title: Programmgesteuertes Aktivieren der Protokollierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- Integration Services packages, logs
- SSIS logging
- log providers [Integration Services]
- logs [Integration Services], enabling
- LoggingMode property
- LogProvider object
- packages [Integration Services], logs
ms.assetid: 3222a1ed-83eb-421c-b299-a53b67bba740
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff7f81aca330960e4e94b0343080a37ded8c1273
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700154"
---
# <a name="enabling-logging-programmatically"></a><span data-ttu-id="56603-102">Programmgesteuertes Aktivieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="56603-102">Enabling Logging Programmatically</span></span>
  <span data-ttu-id="56603-103">Die Runtime-Engine stellt eine Auflistung von <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider>-Objekten bereit, mit deren Hilfe ereignisspezifische Informationen während der Paketüberprüfung und -ausführung aufgezeichnet werden können.</span><span class="sxs-lookup"><span data-stu-id="56603-103">The run-time engine provides a collection of <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects that enable event-specific information to be captured during package validation and execution.</span></span> <span data-ttu-id="56603-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider>-Objekte sind für <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer>-Objekte verfügbar; hierzu zählen auch die Objekte <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop> und <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="56603-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects are available to <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer> objects, including the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>, and <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> objects.</span></span> <span data-ttu-id="56603-105">Die Protokollierung wird für einzelne Container oder das gesamte Paket aktiviert.</span><span class="sxs-lookup"><span data-stu-id="56603-105">Logging is enabled on individual containers, or on the whole package.</span></span>

 <span data-ttu-id="56603-106">Es gibt mehrere Typen von Protokollanbietern, die für einen zu verwendenden Container verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="56603-106">There are several types of log providers that are available for a container to use.</span></span> <span data-ttu-id="56603-107">Dies bietet die Flexibilität, Protokollinformationen in vielen verschiedenen Formaten erstellen und speichern zu können.</span><span class="sxs-lookup"><span data-stu-id="56603-107">This provides the flexibility to create and store log information in many formats.</span></span> <span data-ttu-id="56603-108">Das Eintragen eines Containerobjekts zur Protokollierung umfasst zwei Schritte. Zuerst wird die Protokollierung aktiviert, und im zweiten Schritt wird ein Protokollanbieter ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="56603-108">Enlisting a container object in logging is a two-step process: first logging is enabled, and then a log provider is selected.</span></span> <span data-ttu-id="56603-109">Die Eigenschaften <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> des Containers werden zum Angeben der protokollierten Ereignisse und zum Auswählen des Protokollanbieters verwendet.</span><span class="sxs-lookup"><span data-stu-id="56603-109">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> properties of the container are used to specify the logged events and to select the log provider.</span></span>

## <a name="enabling-logging"></a><span data-ttu-id="56603-110">Aktivieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="56603-110">Enabling Logging</span></span>
 <span data-ttu-id="56603-111">Die <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>-Eigenschaft ist in jedem Container verfügbar, der eine Protokollierung ausführen kann, und legt fest, ob die Ereignisinformationen des Containers im Ereignisprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="56603-111">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property, found in each container that can perform logging, determines whether the container's event information is recorded to the event log.</span></span> <span data-ttu-id="56603-112">Der Eigenschaft wird ein Wert aus der <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode>-Struktur zugewiesen, sie wird standardmäßig vom übergeordneten Container geerbt.</span><span class="sxs-lookup"><span data-stu-id="56603-112">This property is assigned a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> structure, and is inherited from the container's parent by default.</span></span> <span data-ttu-id="56603-113">Wenn der Container ein Paket ist und deshalb keinen übergeordneten Container hat, verwendet die Eigenschaft die <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, die standardmäßig auf `Disabled` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="56603-113">If the container is a package, and therefore has no parent, the property uses the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, which defaults to `Disabled`.</span></span>

### <a name="selecting-a-log-provider"></a><span data-ttu-id="56603-114">Auswählen eines Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="56603-114">Selecting a Log Provider</span></span>
 <span data-ttu-id="56603-115">Nachdem die <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>-Eigenschaft auf `Enabled` festgelegt wurde, wird der <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders>-Auflistung des Containers ein Protokollanbieter hinzugefügt, um den Prozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="56603-115">After the <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property is set to `Enabled`, a log provider is added to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection of the container to complete the process.</span></span> <span data-ttu-id="56603-116">Die <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders>-Auflistung steht im <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions>-Objekt zur Verfügung und enthält die für den Container ausgewählten Protokollanbieter.</span><span class="sxs-lookup"><span data-stu-id="56603-116">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection is available on the <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> object, and contains the log providers selected for the container.</span></span> <span data-ttu-id="56603-117">Zum Erstellen eines Anbieters und Hinzufügen dieses Anbieters zu einer Auflistung wird die <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="56603-117">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> method is called to create a provider and add it to the collection.</span></span> <span data-ttu-id="56603-118">Die Methode gibt daraufhin den Protokollanbieter zurück, der der Auflistung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="56603-118">The method then returns the log provider that was added to the collection.</span></span> <span data-ttu-id="56603-119">Jeder Anbieter verfügt über eindeutige Konfigurationseinstellungen, und diese Eigenschaften werden mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56603-119">Each provider has configuration settings that are unique to that provider, and these properties are set using the <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> property.</span></span>

 <span data-ttu-id="56603-120">In der folgenden Tabelle werden die verfügbaren Protokollanbieter, ihre Beschreibung und ihre <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>-Informationen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="56603-120">The following table lists the available log providers, their description, and their <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> information.</span></span>

|<span data-ttu-id="56603-121">Anbieter</span><span class="sxs-lookup"><span data-stu-id="56603-121">Provider</span></span>|<span data-ttu-id="56603-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56603-122">Description</span></span>|<span data-ttu-id="56603-123">ConfigString-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="56603-123">ConfigString property</span></span>|
|--------------|-----------------|---------------------------|
|<span data-ttu-id="56603-124">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="56603-124">SQL Server Profiler</span></span>|<span data-ttu-id="56603-125">Generiert SQL-Ablaufverfolgungen, die aufgezeichnet und im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Profiler angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="56603-125">Generates SQL traces that may be captured and viewed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span></span> <span data-ttu-id="56603-126">Die standardmäßige Dateinamenerweiterung für diesen Anbieter ist TRC.</span><span class="sxs-lookup"><span data-stu-id="56603-126">The default file name extension for this provider is .trc.</span></span>|<span data-ttu-id="56603-127">Es ist keine Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56603-127">No configuration is required.</span></span>|
|<span data-ttu-id="56603-128">SQL Server</span><span class="sxs-lookup"><span data-stu-id="56603-128">SQL Server</span></span>|<span data-ttu-id="56603-129">Schreibt in allen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbanken Ereignisprotokolleinträge in die **sysssislog**-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="56603-129">Writes event log entries to the **sysssislog** table in any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="56603-130">-Anbieter erfordert eine angegebene Verbindung zur Datenbank sowie den Namen der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="56603-130">provider requires that the connection to the database be specified, and also the target database name.</span></span>|
|<span data-ttu-id="56603-131">Textdatei</span><span class="sxs-lookup"><span data-stu-id="56603-131">Text File</span></span>|<span data-ttu-id="56603-132">Schreibt Ereignisprotokolleinträge im durch Trennzeichen getrennten CSV-Format in ASCII-Textdateien.</span><span class="sxs-lookup"><span data-stu-id="56603-132">Writes event log entries to ASCII text files in a comma-separated value (CSV) format.</span></span> <span data-ttu-id="56603-133">Die standardmäßige Dateinamenerweiterung für diesen Anbieter ist LOG.</span><span class="sxs-lookup"><span data-stu-id="56603-133">The default file name extension for this provider is .log.</span></span>|<span data-ttu-id="56603-134">Der Name eines Dateiverbindungs-Managers.</span><span class="sxs-lookup"><span data-stu-id="56603-134">The name of a file connection manager.</span></span>|
|<span data-ttu-id="56603-135">Windows-Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="56603-135">Windows Event Log</span></span>|<span data-ttu-id="56603-136">Schreibt Protokolle in das Anwendungsprotokoll im standardmäßigen Windows-Ereignisprotokoll auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="56603-136">Logs to standard Windows Event Log on the local computer in the Application log.</span></span>|<span data-ttu-id="56603-137">Es ist keine Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56603-137">No configuration is required.</span></span>|
|<span data-ttu-id="56603-138">XML-Datei</span><span class="sxs-lookup"><span data-stu-id="56603-138">XML File</span></span>|<span data-ttu-id="56603-139">Schreibt Ereignisprotokolleinträge in Dateien im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="56603-139">Writes event log entries to XML formatted file.</span></span> <span data-ttu-id="56603-140">Die standardmäßige Dateinamenerweiterung für diesen Anbieter ist XML.</span><span class="sxs-lookup"><span data-stu-id="56603-140">The default file name extension for this provider is .xml</span></span>|<span data-ttu-id="56603-141">Der Name eines Dateiverbindungs-Managers.</span><span class="sxs-lookup"><span data-stu-id="56603-141">The name of a file connection manager.</span></span>|

 <span data-ttu-id="56603-142">Ob Ereignisse in das Ereignisprotokoll aufgenommen werden oder nicht, wird über die `EventFilterKind`-Eigenschaft und die `EventFilter`-Eigenschaft des Containers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56603-142">Events are included in or excluded from the event log by setting the `EventFilterKind` and the `EventFilter` properties of the container.</span></span> <span data-ttu-id="56603-143">Die `EventFilterKind`-Struktur enthält die beiden Werte `ExclusionFilter` und `InclusionFilter`, die angeben, ob die dem `EventFilter` hinzugefügten Ereignisse im Ereignisprotokoll enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="56603-143">The `EventFilterKind` structure contains two values, `ExclusionFilter` and `InclusionFilter`, that indicate whether the events that are added to the `EventFilter` are included in the event log.</span></span> <span data-ttu-id="56603-144">Der `EventFilter`-Eigenschaft wird daraufhin ein Zeichenfolgenarray mit den Namen der Ereignisse zugewiesen, nach denen gefiltert wurde.</span><span class="sxs-lookup"><span data-stu-id="56603-144">The `EventFilter` property is then assigned a string array that contains the names of the events that are the subject of the filtering.</span></span>

 <span data-ttu-id="56603-145">Mit dem folgenden Code wird die Protokollfunktion eines Pakets aktiviert, der Protokollanbieter für Textdateien zur <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders>-Auflistung hinzugefügt und eine Liste der Ereignisse angegeben, die in die Protokollausgabe aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="56603-145">The following code enables logging on a package, adds the log provider for Text files to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection, and specifies a list of events to include in the logging output.</span></span>

## <a name="sample"></a><span data-ttu-id="56603-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56603-146">Sample</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package p = new Package();

      ConnectionManager loggingConnection = p.Connections.Add("FILE");
      loggingConnection.ConnectionString = @"C:\SSISPackageLog.txt";

      LogProvider provider = p.LogProviders.Add("DTS.LogProviderTextFile.2");
      provider.ConfigString = loggingConnection.Name;
      p.LoggingOptions.SelectedLogProviders.Add(provider);
      p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion;
      p.LoggingOptions.EventFilter = new String[] { "OnPreExecute", 
         "OnPostExecute", "OnError", "OnWarning", "OnInformation" };
      p.LoggingMode = DTSLoggingMode.Enabled;

      // Add tasks and other objects to the package.

    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim p As Package = New Package()

    Dim loggingConnection As ConnectionManager = p.Connections.Add("FILE")
    loggingConnection.ConnectionString = "C:\SSISPackageLog.txt"

    Dim provider As LogProvider = p.LogProviders.Add("DTS.LogProviderTextFile.2")
    provider.ConfigString = loggingConnection.Name
    p.LoggingOptions.SelectedLogProviders.Add(provider)
    p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion
    p.LoggingOptions.EventFilter = New String() {"OnPreExecute", _
       "OnPostExecute", "OnError", "OnWarning", "OnInformation"}
    p.LoggingMode = DTSLoggingMode.Enabled

    ' Add tasks and other objects to the package.

  End Sub

End Module
```

<span data-ttu-id="56603-147">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="56603-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="56603-148">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="56603-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="56603-149">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="56603-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="56603-150">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="56603-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="56603-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56603-151">See Also</span></span>
 [<span data-ttu-id="56603-152">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="56603-152">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)


