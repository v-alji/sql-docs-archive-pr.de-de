---
title: Codieren eines benutzerdefinierten Verbindungs-Managers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], coding
ms.assetid: b12b6778-1f01-4a7d-984d-73f2f7630aa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 793d70ba0a9ae6176ab35c82e16b9aba8c9ba2cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721621"
---
# <a name="coding-a-custom-connection-manager"></a><span data-ttu-id="65f61-102">Codieren eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="65f61-102">Coding a Custom Connection Manager</span></span>
  <span data-ttu-id="65f61-103">Nachdem Sie eine Klasse erstellt haben, die von der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>-Basisklasse erbt, und das <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>-Attribut auf die Klasse angewendet haben, müssen Sie die Implementierung der Eigenschaften und Methoden der Basisklasse überschreiben, um die benutzerdefinierte Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="65f61-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="65f61-104">Beispiele für benutzerdefinierte Verbindungs-Manager finden Sie unter [Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Verbindungs-Manager](developing-a-user-interface-for-a-custom-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="65f61-104">For samples of custom connection managers, see [Developing a User Interface for a Custom Connection Manager](developing-a-user-interface-for-a-custom-connection-manager.md).</span></span> <span data-ttu-id="65f61-105">Die in diesem Thema dargestellten Codebeispiele stammen aus dem SQL Server Custom Connection Manager-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="65f61-105">The code examples shown in this topic are drawn from the SQL Server Custom Connection Manager sample.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65f61-106">Die meisten Tasks, Quellen und Ziele, die in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] integriert wurden, können nur mit bestimmten Typen integrierter Verbindungs-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65f61-106">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="65f61-107">Daher können diese Beispiele nicht mit den integrierten Tasks und Komponenten getestet werden.</span><span class="sxs-lookup"><span data-stu-id="65f61-107">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="configuring-the-connection-manager"></a><span data-ttu-id="65f61-108">Konfigurieren des Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="65f61-108">Configuring the Connection Manager</span></span>  
  
### <a name="setting-the-connectionstring-property"></a><span data-ttu-id="65f61-109">Festlegen der ConnectionString-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="65f61-109">Setting the ConnectionString Property</span></span>  
 <span data-ttu-id="65f61-110">Die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A>-Eigenschaft ist eine wichtige Eigenschaft und die einzige für einen benutzerdefinierten Verbindungs-Manager eindeutige Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="65f61-110">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property is an important property and the only property unique to a custom connection manager.</span></span> <span data-ttu-id="65f61-111">Der Verbindungs-Manager verwendet den Wert dieser Eigenschaft, um eine Verbindung zur externen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="65f61-111">The connection manager uses the value of this property to connect to the external data source.</span></span> <span data-ttu-id="65f61-112">Wenn Sie mehrere andere Eigenschaften miteinander kombinieren, z. B. Servername und Datenbankname, um die Verbindungszeichenfolge zu erstellen, können Sie mit einer Hilfsfunktion die Zeichenfolge zusammenstellen, indem Sie bestimmte Werte in einer Verbindungszeichenfolgenvorlage durch den neuen vom Benutzer bereitgestellten Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="65f61-112">If you are combining several other properties, such as server name and database name, to create the connection string, you can use a helper function to assemble the string by replacing certain values in a connection string template with the new value supplied by the user.</span></span> <span data-ttu-id="65f61-113">Im folgenden Beispiel wird eine Implementierung der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A>-Eigenschaft dargestellt, die zum Zusammenstellen der Zeichenfolge eine Hilfsfunktion benötigt.</span><span class="sxs-lookup"><span data-stu-id="65f61-113">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property that relies on a helper function to assemble the string.</span></span>  
  
```vb  
' Default values.  
Private _serverName As String = "(local)"  
Private _databaseName As String = "AdventureWorks"  
Private _connectionString As String = String.Empty  
  
Private Const CONNECTIONSTRING_TEMPLATE As String = _  
  "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI"  
  
Public Property ServerName() As String  
  Get  
    Return _serverName  
  End Get  
  Set(ByVal value As String)  
    _serverName = value  
  End Set  
End Property  
  
Public Property DatabaseName() As String  
  Get  
    Return _databaseName  
  End Get  
  Set(ByVal value As String)  
    _databaseName = value  
  End Set  
End Property  
  
Public Overrides Property ConnectionString() As String  
  Get  
    UpdateConnectionString()  
    Return _connectionString  
  End Get  
  Set(ByVal value As String)  
    _connectionString = value  
  End Set  
End Property  
  
Private Sub UpdateConnectionString()  
  
  Dim temporaryString As String = CONNECTIONSTRING_TEMPLATE  
  
  If Not String.IsNullOrEmpty(_serverName) Then  
    temporaryString = temporaryString.Replace("<servername>", _serverName)  
  End If  
  If Not String.IsNullOrEmpty(_databaseName) Then  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName)  
  End If  
  
  _connectionString = temporaryString  
  
End Sub  
```  
  
```csharp  
// Default values.  
private string _serverName = "(local)";  
private string _databaseName = "AdventureWorks";  
private string _connectionString = String.Empty;  
  
private const string CONNECTIONSTRING_TEMPLATE = "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI";  
  
public string ServerName  
{  
  get  
  {  
    return _serverName;  
  }  
  set  
  {  
    _serverName = value;  
  }  
}  
  
public string DatabaseName  
{  
  get  
  {  
    return _databaseName;  
  }  
  set  
  {  
    _databaseName = value;  
  }  
}  
  
public override string ConnectionString  
{  
  get  
  {  
    UpdateConnectionString();  
    return _connectionString;  
  }  
  set  
  {  
    _connectionString = value;  
  }  
}  
  
private void UpdateConnectionString()  
{  
  
  string temporaryString = CONNECTIONSTRING_TEMPLATE;  
  
  if (!String.IsNullOrEmpty(_serverName))  
  {  
    temporaryString = temporaryString.Replace("<servername>", _serverName);  
  }  
  
  if (!String.IsNullOrEmpty(_databaseName))  
  {  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName);  
  }  
  
  _connectionString = temporaryString;  
  
}  
```  
  
### <a name="validating-the-connection-manager"></a><span data-ttu-id="65f61-114">Überprüfen des Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="65f61-114">Validating the Connection Manager</span></span>  
 <span data-ttu-id="65f61-115">Sie überschreiben die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>-Methode, um sicherzustellen, dass der Verbindungs-Manager ordnungsgemäß konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="65f61-115">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method to make sure that the connection manager has been configured correctly.</span></span> <span data-ttu-id="65f61-116">Sie sollten zumindest das Format der Verbindungszeichenfolge überprüfen und sicherstellen, dass die Werte für alle Argumente angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="65f61-116">At a minimum, you should validate the format of the connection string and make sure that values have been provided for all arguments.</span></span> <span data-ttu-id="65f61-117">Die Ausführung kann nicht fortgesetzt werden, bis der Verbindungs-Manager <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> von der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>-Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="65f61-117">Execution cannot continue until the connection manager returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="65f61-118">Im folgenden Codebeispiel wird eine Implementierung von <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> gezeigt, mit der sichergestellt wird, dass der Benutzer den Servernamen für die Verbindung angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="65f61-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> that makes sure that the user has specified a server name for the connection.</span></span>  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  If String.IsNullOrEmpty(_serverName) Then  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0)  
    Return DTSExecResult.Failure  
  Else  
    Return DTSExecResult.Success  
  End If  
  
End Function  
```  
  
```csharp  
public override Microsoft.SqlServer.Dts.Runtime.DTSExecResult Validate(Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  if (String.IsNullOrEmpty(_serverName))  
  {  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0);  
    return DTSExecResult.Failure;  
  }  
  else  
  {  
    return DTSExecResult.Success;  
  }  
  
}  
```  
  
### <a name="persisting-the-connection-manager"></a><span data-ttu-id="65f61-119">Beibehalten des Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="65f61-119">Persisting the Connection Manager</span></span>  
 <span data-ttu-id="65f61-120">In der Regel müssen Sie keine benutzerdefinierte Persistenz für einen Verbindungs-Manager implementieren.</span><span class="sxs-lookup"><span data-stu-id="65f61-120">Usually, you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="65f61-121">Die benutzerdefinierte Persistenz ist nur erforderlich, wenn die Eigenschaften eines Objekts komplexe Datentypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="65f61-121">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="65f61-122">Weitere Informationen finden Sie unter [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) (Entwickeln von benutzerdefinierten Objekten für Integration Services).</span><span class="sxs-lookup"><span data-stu-id="65f61-122">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="working-with-the-external-data-source"></a><span data-ttu-id="65f61-123">Arbeiten mit der externen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="65f61-123">Working with the External Data Source</span></span>  
 <span data-ttu-id="65f61-124">Die Methoden, die eine Verbindung zu einer externen Datenquelle unterstützen, sind die wichtigsten Methoden eines benutzerdefinierten Verbindungs-Managers.</span><span class="sxs-lookup"><span data-stu-id="65f61-124">The methods that support connecting to an external data source are the most important methods of a custom connection manager.</span></span> <span data-ttu-id="65f61-125">Die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>-Methode und die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>-Methode werden zu unterschiedlichen Zeitpunkten während des Entwurfs und der Ausführung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="65f61-125">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods are called at various times during both design time and run time.</span></span>  
  
### <a name="acquiring-the-connection"></a><span data-ttu-id="65f61-126">Abrufen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="65f61-126">Acquiring the Connection</span></span>  
 <span data-ttu-id="65f61-127">Sie müssen entscheiden, welcher Objekttyp für die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>-Methode geeignet ist, um vom benutzerdefinierten Verbindungs-Manager zurückgegeben zu werden.</span><span class="sxs-lookup"><span data-stu-id="65f61-127">You need to decide what type of object it is appropriate for the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method to return from your custom connection manager.</span></span> <span data-ttu-id="65f61-128">Ein Dateiverbindungs-Manager gibt beispielsweise nur eine Zeichenfolge zurück, die einen Pfad und einen Dateinamen enthält, ein ADO.NET-Verbindungs-Manager gibt hingegen ein verwaltetes Verbindungsobjekt, das bereits offen ist, zurück.</span><span class="sxs-lookup"><span data-stu-id="65f61-128">For example, a File connection manager returns only a string that contains a path and filename, whereas an ADO.NET connection manager returns a managed connection object that is already open.</span></span> <span data-ttu-id="65f61-129">Ein OLE DB-Verbindungs-Manager gibt ein systemeigenes OLE DB-Verbindungsobjekt zurück, das nicht vom verwalteten Code verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="65f61-129">An OLE DB connection manager returns a native OLE DB connection object that cannot be used from managed code.</span></span> <span data-ttu-id="65f61-130">Der benutzerdefinerte SQL Server-Verbindungs-Manager, dem die Codeabschnitte in diesem Themen entnommen wurden, gibt ein offenes `SqlConnection`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="65f61-130">The custom SQL Server connection manager, from which the code snippets in this topic are taken, returns an open `SqlConnection` object.</span></span>  
  
 <span data-ttu-id="65f61-131">Benutzer Ihres Verbindungs-Managers müssen vorab wissen, welche Objekttypen verwendet werden, sodass sie das zurückgegebene Objekt in den entsprechenden Typ umwandeln können und auf dessen Methoden und Eigenschaften zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="65f61-131">Users of your connection manager need to know in advance what type of object to expect, so that they can cast the returned object to the appropriate type and access its methods and properties.</span></span>  
  
```vb  
Public Overrides Function AcquireConnection(ByVal txn As Object) As Object  
  
  Dim sqlConnection As New SqlConnection  
  
  UpdateConnectionString()  
  
  With sqlConnection  
    .ConnectionString = _connectionString  
    .Open()  
  End With  
  
  Return sqlConnection  
  
End Function  
```  
  
```csharp  
public override object AcquireConnection(object txn)  
{  
  
  SqlConnection sqlConnection = new SqlConnection();  
  
  UpdateConnectionString();  
  
  {  
    sqlConnection.ConnectionString = _connectionString;  
    sqlConnection.Open();  
  }  
  
  return sqlConnection;  
  
}  
```  
  
### <a name="releasing-the-connection"></a><span data-ttu-id="65f61-132">Freigeben der Verbindung</span><span class="sxs-lookup"><span data-stu-id="65f61-132">Releasing the Connection</span></span>  
 <span data-ttu-id="65f61-133">Die auszuführende Aktion für die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>-Methode ist vom Objekttyp, der mit der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>-Methode zurückgegeben wird, abhängig.</span><span class="sxs-lookup"><span data-stu-id="65f61-133">The action that you take in the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> method depends on the type of object that you returned from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span> <span data-ttu-id="65f61-134">Wenn ein offenes Verbindungsobjekt vorliegt, sollten Sie es schließen, um von ihm verwendete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="65f61-134">If there is an open connection object, you should close it and to release any resources that it is using.</span></span> <span data-ttu-id="65f61-135">Wenn <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> nur einen Zeichenfolgenwert zurückgegeben hat, muss keine Aktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65f61-135">If <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> returned only a string value, no action needs to be taken.</span></span>  
  
```vb  
Public Overrides Sub ReleaseConnection(ByVal connection As Object)  
  
  Dim sqlConnection As SqlConnection  
  
  sqlConnection = DirectCast(connection, SqlConnection)  
  
  If sqlConnection.State <> ConnectionState.Closed Then  
    sqlConnection.Close()  
  End If  
  
End Sub  
```  
  
```csharp  
public override void ReleaseConnection(object connection)  
{  
  SqlConnection sqlConnection;  
  sqlConnection = (SqlConnection)connection;  
  if (sqlConnection.State != ConnectionState.Closed)  
    sqlConnection.Close();  
}  
```  
  
<span data-ttu-id="65f61-136">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="65f61-136">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="65f61-137">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="65f61-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="65f61-138">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="65f61-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="65f61-139">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="65f61-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f61-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65f61-140">See Also</span></span>  
 <span data-ttu-id="65f61-141">[Erstellen eines benutzerdefinierten Verbindungs-Managers](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="65f61-141">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="65f61-142">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="65f61-142">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
