---
title: Herstellen einer Verbindung mit Datenquellen in einem benutzerdefinierten Task | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ConnectionManager objects
- connection managers [Integration Services], external data sources
- data sources [Integration Services], external
- custom tasks [Integration Services], external data sources
- external data sources [Integration Services]
- connections [Integration Services], external data sources
- SSIS custom tasks, external data sources
ms.assetid: 9f0b3a43-3eaa-4b3c-bb08-29b630c11306
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71c504f4b528a0c9809d00de74de4beb9c67c4f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619225"
---
# <a name="connecting-to-data-sources-in-a-custom-task"></a><span data-ttu-id="45a80-102">Herstellen einer Verbindung mit Datenquellen in einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="45a80-102">Connecting to Data Sources in a Custom Task</span></span>
  <span data-ttu-id="45a80-103">Tasks stellen eine Verbindung mit externen Datenquellen her, um Daten mit einem Verbindungs-Manager abzurufen oder zu speichern.</span><span class="sxs-lookup"><span data-stu-id="45a80-103">Tasks connect to external data sources to retrieve or save data by using a connection manager.</span></span> <span data-ttu-id="45a80-104">Zur Entwurfszeit stellt ein Verbindungs-Manager eine logische Verbindung dar und beschreibt Schlüsselinformationen wie den Servernamen und Authentifizierungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="45a80-104">At design time, a connection manager represents a logical connection, and describes key information such as the server name and any authentication properties.</span></span> <span data-ttu-id="45a80-105">Zur Laufzeit rufen Tasks die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>-Methode des Verbindung-Managers auf, um die physische Verbindung mit der Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="45a80-105">At run time, tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager to establish the physical connection to the data source.</span></span>  
  
 <span data-ttu-id="45a80-106">Da ein Paket zahlreiche Tasks enthalten kann, von denen möglicherweise jede eine Verbindung mit einer anderen Datenquelle herstellt, verfolgt das Paket alle Verbindungs-Manager in einer Auflistung, nämlich in der <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="45a80-106">Because a package can contain many tasks, each of which may have connections to different data sources, the package tracks all the connection managers in a collection, the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection.</span></span> <span data-ttu-id="45a80-107">Tasks suchen mithilfe der Auflistung in ihrem Paket nach dem Verbindungs-Manager, den sie bei der Überprüfung und Ausführung verwenden.</span><span class="sxs-lookup"><span data-stu-id="45a80-107">Tasks use the collection in their package to find the connection manager that they will use during validation and execution.</span></span> <span data-ttu-id="45a80-108">Die <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Auflistung ist der erste Parameter der Methoden <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="45a80-108">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection is the first parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="45a80-109">Sie können verhindern, dass der Task den falschen Verbindungs-Manager verwendet, indem Sie dem Benutzer die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekte aus der Auflistung mithilfe eines Dialogfelds oder einer Dropdownliste auf der grafischen Benutzeroberfläche anzeigen.</span><span class="sxs-lookup"><span data-stu-id="45a80-109">You can prevent the task from using the wrong connection manager by displaying the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects from the collection to the user, by using a dialog box or drop-down list in the graphical user interface.</span></span> <span data-ttu-id="45a80-110">So hat der Benutzer nur die Auswahl zwischen den im Paket enthaltenen <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekten des geeigneten Typs.</span><span class="sxs-lookup"><span data-stu-id="45a80-110">This gives the user a way to select from among only those <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects of the appropriate type that are contained in the package.</span></span>  
  
 <span data-ttu-id="45a80-111">Tasks rufen die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>-Methode auf, um die physische Verbindung mit der Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="45a80-111">Tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection to the data source.</span></span> <span data-ttu-id="45a80-112">Die Methode gibt das zugrunde liegende Verbindungsobjekt zurück, das dann vom Task verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="45a80-112">The method returns the underlying connection object that can then be used by the task.</span></span> <span data-ttu-id="45a80-113">Da der Verbindungs-Manager die Implementierungsdetails des zugrunde liegenden Verbindungsobjekts vom Task isoliert, muss der Task nur die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>-Methode aufrufen, um die Verbindung herzustellen, und muss sich um keine anderen Aspekte der Verbindung kümmern.</span><span class="sxs-lookup"><span data-stu-id="45a80-113">Because the connection manager isolates the implementation details of the underlying connection object from the task, the task only has to call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the connection, and does not have to be concerned with other aspects of the connection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45a80-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45a80-114">Example</span></span>  
 <span data-ttu-id="45a80-115">Im folgenden Codebeispiel wird die Überprüfung des <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Namens in den Methoden Validate und Execute dargestellt und gezeigt, wie mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>-Methode eine physische Verbindung in der Execute-Methode hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="45a80-115">The following sample code demonstrates validation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> name in the Validate and Execute methods, and shows how to use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection in the Execute method.</span></span>  
  
```csharp  
private string connectionManagerName = "";  
  
public string ConnectionManagerName  
{  
  get { return this.connectionManagerName; }  
  set { this.connectionManagerName = value; }  
}  
  
public override DTSExecResult Validate(  
  Connections connections, VariableDispenser variableDispenser,  
  IDTSComponentEvents componentEvents, IDTSLogging log)  
{  
  // If the connection manager exists, validation is successful;  
  // otherwise, fail validation.  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception e)  
  {  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
  
public override DTSExecResult Execute(Connections connections,   
  VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,   
  IDTSLogging log, object transaction)  
{  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    object connection = cm.AcquireConnection(transaction);  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception exception)  
  {  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
```  
  
```vb  
Private _connectionManagerName As String = ""  
  
Public Property ConnectionManagerName() As String  
  Get  
    Return Me._connectionManagerName  
  End Get  
  Set(ByVal Value As String)  
    Me._connectionManagerName = value  
  End Set  
End Property  
  
Public Overrides Function Validate( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  ' If the connection manager exists, validation is successful;  
  ' otherwise fail validation.  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Return DTSExecResult.Success  
  Catch e As System.Exception  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
  
Public Overrides Function Execute( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging, ByVal transaction As Object) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Dim connection As Object = cm.AcquireConnection(transaction)  
    Return DTSExecResult.Success  
  Catch exception As System.Exception  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
```  
  
<span data-ttu-id="45a80-116">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="45a80-116">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="45a80-117">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="45a80-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="45a80-118">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="45a80-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="45a80-119">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="45a80-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a80-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45a80-120">See Also</span></span>  
 <span data-ttu-id="45a80-121">[Integration Services &#40;SSIS-&#41; Verbindungen](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="45a80-121">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="45a80-122">Erstellen von Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="45a80-122">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
