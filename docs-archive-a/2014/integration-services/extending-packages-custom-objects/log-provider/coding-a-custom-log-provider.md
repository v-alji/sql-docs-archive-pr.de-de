---
title: Codieren eines benutzerdefinierten Protokollanbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom log providers [Integration Services], coding
ms.assetid: 979a29ca-956e-4fdd-ab47-f06e84cead7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d529420207ac065ae5ecb3c1d984de3021845b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701301"
---
# <a name="coding-a-custom-log-provider"></a><span data-ttu-id="c353f-102">Codieren eines benutzerdefinierten Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="c353f-102">Coding a Custom Log Provider</span></span>
  <span data-ttu-id="c353f-103">Nachdem Sie eine Klasse erstellt haben, die von der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>-Basisklasse erbt, und das <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>-Attribut auf die Klasse angewendet haben, müssen Sie die Implementierung der Eigenschaften und Methoden der Basisklasse überschreiben, um die benutzerdefinierte Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c353f-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="c353f-104">Funktionstüchtige Beispiele benutzerdefinierter Protokollanbieter finden Sie unter [Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Protokollanbieter](developing-a-user-interface-for-a-custom-log-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c353f-104">For working samples of custom log providers, see [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md).</span></span>  
  
## <a name="configuring-the-log-provider"></a><span data-ttu-id="c353f-105">Konfigurieren des Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="c353f-105">Configuring the Log Provider</span></span>  
  
### <a name="initializing-the-log-provider"></a><span data-ttu-id="c353f-106">Initialisieren des Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="c353f-106">Initializing the Log Provider</span></span>  
 <span data-ttu-id="c353f-107">Sie überschreiben die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A>-Methode, um Verweise auf die Connections-Auflistung und die Ereignisschnittstelle zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="c353f-107">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> method to cache references to the connections collection and the events interface.</span></span> <span data-ttu-id="c353f-108">Sie können diese zwischengespeicherten Verweise später in anderen Methoden des Protokollanbieters verwenden.</span><span class="sxs-lookup"><span data-stu-id="c353f-108">You can use these cached references later in other methods of the log provider.</span></span>  
  
### <a name="using-the-configstring-property"></a><span data-ttu-id="c353f-109">Verwenden der ConfigString-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c353f-109">Using the ConfigString Property</span></span>  
 <span data-ttu-id="c353f-110">Zur Entwurfszeit erhält ein Protokollanbieter Konfigurationsinformationen aus der Spalte **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c353f-110">At design time, a log provider receives configuration information from the **Configuration** column.</span></span> <span data-ttu-id="c353f-111">Diese Konfigurationsinformationen entsprechen der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>-Eigenschaft des Protokollanbieters.</span><span class="sxs-lookup"><span data-stu-id="c353f-111">This configuration information corresponds to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property of the log provider.</span></span> <span data-ttu-id="c353f-112">Standardmäßig enthält diese Spalte ein Textfeld, aus dem Sie alle Zeichenfolgeninformationen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="c353f-112">By default, this column contains a text box from which you can retrieve any string information.</span></span> <span data-ttu-id="c353f-113">Die meisten in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] integrierten Protokollanbieter verwenden diese Eigenschaft, um den Namen des Verbindungs-Managers zu speichern, den der Anbieter zur Verbindung mit einer externen Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c353f-113">Most of the log providers included with [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] use this property to store the name of the connection manager that the provider uses to connect to an external data source.</span></span> <span data-ttu-id="c353f-114">Falls Ihr Protokollanbieter die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>-Eigenschaft verwendet, wenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>-Methode an, um diese Eigenschaft zu überprüfen und sicherzustellen, dass sie richtig eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="c353f-114">If your log provider uses the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property, use the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to validate this property and make sure that the property is set correctly.</span></span>  
  
### <a name="validating-the-log-provider"></a><span data-ttu-id="c353f-115">Überprüfen des Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="c353f-115">Validating the Log Provider</span></span>  
 <span data-ttu-id="c353f-116">Sie überschreiben die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>-Methode, um sicherzustellen, dass der Anbieter ordnungsgemäß konfiguriert wurde und zum Ausführen bereit ist.</span><span class="sxs-lookup"><span data-stu-id="c353f-116">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to make sure that the provider has been configured correctly and is ready for execution.</span></span> <span data-ttu-id="c353f-117">In der Regel genügt eine minimale Überprüfung, um sich zu vergewissern, dass <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> richtig eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="c353f-117">Typically, a minimum level of validation is to make sure that the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> is set correctly.</span></span> <span data-ttu-id="c353f-118">Die Ausführung kann erst fortgesetzt werden, wenn der Protokollanbieter <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> von der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>-Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c353f-118">Execution cannot continue until the log provider returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="c353f-119">Im folgenden Beispiel wird eine Implementierung von <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> gezeigt, die sicherstellt, dass der Name eines Verbindungs-Managers angegeben ist, dass der Verbindungs-Manager im Paket enthalten ist und dass er einen Dateinamen in der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>-Eigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c353f-119">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> that makes sure that the name of a connection manager name is specified, that the connection manager exists in the package, and that the connection manager returns a file name in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override DTSExecResult Validate(IDTSInfoEvents infoEvents)  
{  
    if (this.ConfigString.Length == 0 || connections.Contains(ConfigString) == false)  
    {  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
        return DTSExecResult.Failure;  
    }  
    else  
    {  
        string fileName = connections[ConfigString].AcquireConnection(null) as string;  
  
        if (fileName == null || fileName.Length == 0)  
        {  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
            return DTSExecResult.Failure;  
        }  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As IDTSInfoEvents) As DTSExecResult  
    If Me.ConfigString.Length = 0 Or connections.Contains(ConfigString) = False Then  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
        Return DTSExecResult.Failure  
    Else   
        Dim fileName As String =  connections(ConfigString).AcquireConnectionCType(as string, Nothing)  
  
        If fileName = Nothing Or fileName.Length = 0 Then  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
            Return DTSExecResult.Failure  
        End If  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
### <a name="persisting-the-log-provider"></a><span data-ttu-id="c353f-120">Beibehalten des Protokollanbieters</span><span class="sxs-lookup"><span data-stu-id="c353f-120">Persisting the Log Provider</span></span>  
 <span data-ttu-id="c353f-121">In der Regel müssen Sie keine benutzerdefinierte Persistenz für einen Verbindungs-Manager implementieren.</span><span class="sxs-lookup"><span data-stu-id="c353f-121">Ordinarily you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="c353f-122">Die benutzerdefinierte Persistenz ist nur erforderlich, wenn die Eigenschaften eines Objekts komplexe Datentypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c353f-122">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="c353f-123">Weitere Informationen finden Sie unter [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) (Entwickeln von benutzerdefinierten Objekten für Integration Services).</span><span class="sxs-lookup"><span data-stu-id="c353f-123">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="logging-with-the-log-provider"></a><span data-ttu-id="c353f-124">Protokollieren mit dem Protokollanbieter</span><span class="sxs-lookup"><span data-stu-id="c353f-124">Logging with the Log Provider</span></span>  
 <span data-ttu-id="c353f-125">Es gibt drei Laufzeitmethoden, die von allen Protokollanbietern überschrieben werden müssen: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="c353f-125">There are three run-time methods that must be overridden by all log providers: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c353f-126">Während der Überprüfung und Ausführung eines einzelnen Pakets werden die Methoden <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> mehrmals aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c353f-126">During the validation and execution of a single package, the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods are called more than one time.</span></span> <span data-ttu-id="c353f-127">Stellen Sie sicher, dass mit Ihrem benutzerdefinierten Code keine früheren Protokolleinträge beim nächsten Öffnen und Schließen des Protokolls überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c353f-127">Make sure that your custom code does not cause earlier log entries to be overwritten by the next opening and closing of the log.</span></span> <span data-ttu-id="c353f-128">Falls Sie die Protokollierung von Überprüfungsereignissen in Ihrem Testpaket festgelegt haben, sollte als erstes protokolliertes Ereignis OnPreValidate angezeigt werden. Falls als erstes Ereignis PackageStart angezeigt wird, wurden die anfänglichen Überprüfungsereignisse überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c353f-128">If you have selected to log validation events in your test package, the first logged event that you should see is OnPreValidate; if instead the first logged event that you see is PackageStart, the initial validation events have been overwritten.</span></span>  
  
### <a name="opening-the-log"></a><span data-ttu-id="c353f-129">Öffnen des Protokolls</span><span class="sxs-lookup"><span data-stu-id="c353f-129">Opening the Log</span></span>  
 <span data-ttu-id="c353f-130">Die meisten Protokollanbieter stellen eine Verbindung mit einer externen Datenquelle, wie z. B. einer Datei oder einer Datenbank her, um die Ereignisinformationen zu speichern, die während der Paketausführung gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="c353f-130">Most log providers connect to an external data source, such as a file or database, to store the event information that is collected during package execution.</span></span> <span data-ttu-id="c353f-131">Wie bei jedem anderen Objekt erfolgt die Verbindung mit der externen Datenquelle zur Laufzeit normalerweise über die Verwendung von Verbindungs-Manager-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c353f-131">As with any other object in the runtime, connecting to the external data source is typically accomplished by using connection manager objects.</span></span>  
  
 <span data-ttu-id="c353f-132">Die Methode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> wird zu Beginn der Paketausführung aufgerufen. Überschreiben Sie diese Methode, um eine Verbindung mit der externen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c353f-132">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method is called at the start of package execution.Override this method to establish a connection to the external data source.</span></span>  
  
 <span data-ttu-id="c353f-133">Im folgenden Beispielcode wird ein Protokollanbieter gezeigt, der während <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> eine Textdatei zum Schreiben öffnet.</span><span class="sxs-lookup"><span data-stu-id="c353f-133">The following sample code shows a log provider that opens a text file for writing during <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span></span> <span data-ttu-id="c353f-134">Die Datei wird durch Aufrufen der Methode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> des Verbindungs-Managers geöffnet, der in der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>-Eigenschaft angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c353f-134">It opens the file by calling the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager that was specified in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override void OpenLog()  
{  
    if(!this.connections.Contains(this.ConfigString))  
        throw new Exception("The ConnectionManager " + this.ConfigString + " does not exist in the Connections collection.");  
  
    this.connectionManager = connections[ConfigString];  
    string filePath = this.connectionManager.AcquireConnection(null) as string;  
  
    if(filePath == null || filePath.Length == 0)  
        throw new Exception("The ConnectionManager " + this.ConfigString + " is not a valid FILE ConnectionManager");  
  
    //  Create a StreamWriter to append to.  
    sw = new StreamWriter(filePath,true);  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString());  
}  
```  
  
```vb  
Public Overrides  Sub OpenLog()  
    If Not Me.connections.Contains(Me.ConfigString) Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " does not exist in the Connections collection.")  
    End If  
  
    Me.connectionManager = connections(ConfigString)  
    Dim filePath As String =  Me.connectionManager.AcquireConnectionCType(as string, Nothing)  
  
    If filePath = Nothing Or filePath.Length = 0 Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " is not a valid FILE ConnectionManager")  
    End If  
  
    '  Create a StreamWriter to append to.  
    sw = New StreamWriter(filePath,True)  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString())  
End Sub  
```  
  
### <a name="writing-log-entries"></a><span data-ttu-id="c353f-135">Schreiben von Protokolleinträgen</span><span class="sxs-lookup"><span data-stu-id="c353f-135">Writing Log Entries</span></span>  
 <span data-ttu-id="c353f-136">Die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>-Methode wird immer dann aufgerufen, wenn ein Objekt im Paket ein Ereignis auslöst, indem es eine Fire\<event>-Methode für eine der Ereignisschnittstellen aufruft.</span><span class="sxs-lookup"><span data-stu-id="c353f-136">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method is called every time that an object in the package raises an event by calling a Fire\<event> method on one of the event interfaces.</span></span> <span data-ttu-id="c353f-137">Jedes Ereignis wird mit Informationen über seinen Kontext ausgelöst und enthält normalerweise eine erklärende Meldung.</span><span class="sxs-lookup"><span data-stu-id="c353f-137">Each event is raised with information about its context and usually an explanatory message.</span></span> <span data-ttu-id="c353f-138">Aber nicht jeder Aufruf der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>-Methode enthält Informationen für jeden Methodenparameter.</span><span class="sxs-lookup"><span data-stu-id="c353f-138">However, not every call to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method includes information for every method parameter.</span></span> <span data-ttu-id="c353f-139">Beispielsweise liefern einige Standardereignisse, deren Namen selbsterklärend sind, keinen Meldungstext, und Datencode und Datenbytes sind für optionale Zusatzinformationen gedacht.</span><span class="sxs-lookup"><span data-stu-id="c353f-139">For example, some standard events whose names are self-explanatory do not provide MessageText, and DataCode and DataBytes are intended for optional supplemental information.</span></span>  
  
 <span data-ttu-id="c353f-140">Im folgenden Codebeispiel wird die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>-Methode implementiert und die Ereignisse in den Datenstrom geschrieben, der im vorhergehenden Abschnitt geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="c353f-140">The following code example implements the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method, and writes the events to the stream that was opened in the previous section.</span></span>  
  
```csharp  
public override void Log(string logEntryName, string computerName, string operatorName, string sourceName, string sourceID, string executionID, string messageText, DateTime startTime, DateTime endTime, int dataCode, byte[] dataBytes)  
{  
    sw.Write(logEntryName + ",");  
    sw.Write(computerName + ",");  
    sw.Write(operatorName + ",");  
    sw.Write(sourceName + ",");  
    sw.Write(sourceID + ",");  
    sw.Write(messageText + ",");  
    sw.Write(dataBytes + ",");  
    sw.WriteLine("");  
}  
```  
  
```vb  
Public Overrides  Sub Log(ByVal logEnTryName As String, ByVal computerName As String, ByVal operatorName As String, ByVal sourceName As String, ByVal sourceID As String, ByVal executionID As String, ByVal messageText As String, ByVal startTime As DateTime, ByVal endTime As DateTime, ByVal dataCode As Integer, ByVal dataBytes() As Byte)  
    sw.Write(logEnTryName + ",")  
    sw.Write(computerName + ",")  
    sw.Write(operatorName + ",")  
    sw.Write(sourceName + ",")  
    sw.Write(sourceID + ",")  
    sw.Write(messageText + ",")  
    sw.Write(dataBytes + ",")  
    sw.WriteLine("")  
End Sub  
```  
  
### <a name="closing-the-log"></a><span data-ttu-id="c353f-141">Schließen des Protokolls</span><span class="sxs-lookup"><span data-stu-id="c353f-141">Closing the Log</span></span>  
 <span data-ttu-id="c353f-142">Die <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>-Methode wird am Ende der Paketausführung aufgerufen, nachdem die Ausführung aller Objekte im Paket abgeschlossen ist oder wenn das Paket aufgrund eines Fehlers gestoppt wird.</span><span class="sxs-lookup"><span data-stu-id="c353f-142">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method is called at the end of package execution, after all the objects in the package have completed execution, or, when the package stops because of errors.</span></span>  
  
 <span data-ttu-id="c353f-143">Im folgenden Codebeispiel wird die Implementierung der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>-Methode veranschaulicht, die den Dateidatenstrom schließt, der von der <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>-Methode geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="c353f-143">The following code example demonstrates an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method that closes the file stream that was opened during the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method.</span></span>  
  
```csharp  
public override void CloseLog()  
{  
    if (sw != null)  
    {  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString());  
        sw.Close();  
    }  
}  
```  
  
```vb  
Public Overrides  Sub CloseLog()  
    If Not sw Is Nothing Then  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString())  
        sw.Close()  
    End If  
End Sub  
```  
  
<span data-ttu-id="c353f-144">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="c353f-144">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c353f-145">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="c353f-145">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c353f-146">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="c353f-146">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c353f-147">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c353f-147">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c353f-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c353f-148">See Also</span></span>  
 <span data-ttu-id="c353f-149">[Erstellen eines benutzerdefinierten Protokollanbieters](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="c353f-149">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="c353f-150">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Protokollanbieter</span><span class="sxs-lookup"><span data-stu-id="c353f-150">Developing a User Interface for a Custom Log Provider</span></span>](developing-a-user-interface-for-a-custom-log-provider.md)  
  
  
