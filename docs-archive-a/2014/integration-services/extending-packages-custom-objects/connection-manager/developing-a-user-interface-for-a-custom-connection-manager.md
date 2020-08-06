---
title: Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], developing user interface
- custom user interface [Integration Services], custom connection manager
ms.assetid: 908bf2ac-fc84-4af8-a869-1cb43573d2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc0e9f2a76f3d97c925c44219683ca6cd655e43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617195"
---
# <a name="developing-a-user-interface-for-a-custom-connection-manager"></a><span data-ttu-id="b0342-102">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="b0342-102">Developing a User Interface for a Custom Connection Manager</span></span>
  <span data-ttu-id="b0342-103">Nachdem Sie die Implementierung der Eigenschaften und Methoden der Basisklasse überschrieben haben, um benutzerdefinierte Funktionen bereitzustellen, möchten Sie vielleicht eine benutzerdefinierte Oberfläche für den Verbindungs-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0342-103">After you have overridden the implementation of the properties and methods of the base class to provide your custom functionality, you may want to create a custom user interface for your connection manager.</span></span> <span data-ttu-id="b0342-104">Wenn Sie keine individuelle Benutzeroberfläche erstellen, können die Benutzer den Verbindungs-Manager nur über das Eigenschaftenfenster konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b0342-104">If you do not create a custom user interface, users can configure your connection manager only by using the Properties window.</span></span>  
  
 <span data-ttu-id="b0342-105">In einem individuellen Benutzeroberflächenprojekt oder einer entsprechenden Assembly gibt es im Allgemeinen zwei Klassen: eine Klasse, die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> implementiert, und das Windows Form, in dem diese angezeigt wird, um Informationen vom Benutzer zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="b0342-105">In a custom user interface project or assembly, you normally have two classes-a class that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>, and the Windows form that it displays to gather information from the user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b0342-106">Nach dem Signieren und Erstellen der benutzerdefinierten Oberfläche und der Installation im globalen Assemblycache (siehe [Codieren eines benutzerdefinierten Verbindungs-Managers](../building-deploying-and-debugging-custom-objects.md)) müssen Sie den vollqualifizierten Namen dieser Klasse in der <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0342-106">After signing and building your custom user interface and installing it in the global assembly cache as described in [Coding a Custom Connection Manager](../building-deploying-and-debugging-custom-objects.md), remember to provide the fully qualified name of this class in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0342-107">Die meisten Tasks, Quellen und Ziele, die in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] integriert wurden, können nur mit bestimmten Typen integrierter Verbindungs-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0342-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="b0342-108">Daher können diese Beispiele nicht mit den integrierten Tasks und Komponenten getestet werden.</span><span class="sxs-lookup"><span data-stu-id="b0342-108">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="coding-the-user-interface-class"></a><span data-ttu-id="b0342-109">Codieren der Benutzeroberflächenklasse</span><span class="sxs-lookup"><span data-stu-id="b0342-109">Coding the User Interface Class</span></span>  
 <span data-ttu-id="b0342-110">Die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>-Schnittstelle verfügt über vier Methoden: <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0342-110">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface has four methods: <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>.</span></span> <span data-ttu-id="b0342-111">In den folgenden Abschnitten werden diese vier Methoden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0342-111">The following sections describe these four methods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0342-112">Für die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>-Methode müssen Sie möglicherweise keinen Code schreiben, wenn beim Löschen einer Instanz des Verbindungs-Managers durch einen Benutzer kein Cleanup erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b0342-112">You may not need to write any code for the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A> method if no cleanup is required when the user deletes an instance of the connection manager.</span></span>  
  
### <a name="initializing-the-user-interface"></a><span data-ttu-id="b0342-113">Initialisieren der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="b0342-113">Initializing the User Interface</span></span>  
 <span data-ttu-id="b0342-114">In der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>-Methode stellt der Designer einen Verweis auf den Verbindungs-Manager, der konfiguriert wird, bereit, damit die Benutzeroberflächenklasse die Eigenschaften des Verbindungs-Managers ändern kann.</span><span class="sxs-lookup"><span data-stu-id="b0342-114">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> method, the designer provides a reference to the connection manager that is being configured so that the user interface class can modify the connection manager's properties.</span></span> <span data-ttu-id="b0342-115">Wie im folgenden Beispiel dargestellt, muss der Code den Verweis auf den Verbindungs-Manager zur späteren Verwendung zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="b0342-115">As shown in the following code, your code needs to cache the reference to the connection managerfor later use.</span></span>  
  
```vb  
Public Sub Initialize(ByVal connectionManager As Microsoft.SqlServer.Dts.Runtime.ConnectionManager, ByVal serviceProvider As System.IServiceProvider) Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize  
  
    _connectionManager = connectionManager  
    _serviceProvider = serviceProvider  
  
  End Sub  
```  
  
```csharp  
public void Initialize(Microsoft.SqlServer.Dts.Runtime.ConnectionManager connectionManager, System.IServiceProvider serviceProvider)  
{  
  
  _connectionManager = connectionManager;  
  _serviceProvider = serviceProvider;  
  
}  
```  
  
### <a name="creating-a-new-instance-of-the-user-interface"></a><span data-ttu-id="b0342-116">Erstellen einer neuen Instanz der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="b0342-116">Creating a New Instance of the User Interface</span></span>  
 <span data-ttu-id="b0342-117">Die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>-Methode, bei der es sich nicht um einen Konstruktor handelt, wird nach der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>-Methode aufgerufen, wenn der Benutzer eine neue Instanz des Verbindungs-Managers erstellt.</span><span class="sxs-lookup"><span data-stu-id="b0342-117">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> method, which is not a constructor, is called after the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> method when the user creates a new instance of the connection manager.</span></span> <span data-ttu-id="b0342-118">Sie sollten in der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>-Methode das Formular zum Bearbeiten anzeigen, außer der Benutzer hat einen vorhandenen Verbindungs-Manager kopiert und eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b0342-118">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> method, you usually want to display the form for editing, unless the user has copied and pasted an existing connection manager.</span></span> <span data-ttu-id="b0342-119">Im folgenden Codebeispiel wird eine Implementierung dieser Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b0342-119">The following code shows an implementation of this method.</span></span>  
  
```vb  
Public Function [New](ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, ByVal connectionUIArgs As Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs) As Boolean Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New  
  
  Dim clipboardService As IDtsClipboardService  
  
  clipboardService = _  
    DirectCast(_serviceProvider.GetService(GetType(IDtsClipboardService)), IDtsClipboardService)  
  If Not clipboardService Is Nothing Then  
    ' If the connection manager has been copied and pasted, take no action.  
    If clipboardService.IsPasteActive Then  
      Return True  
    End If  
  End If  
  
  Return EditSqlConnection(parentWindow)  
  
End Function  
```  
  
```csharp  
public bool New(System.Windows.Forms.IWin32Window parentWindow, Microsoft.SqlServer.Dts.Runtime.Connections connections, Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs connectionUIArgs)  
  {  
    IDtsClipboardService clipboardService;  
  
    clipboardService = (IDtsClipboardService)_serviceProvider.GetService(typeof(IDtsClipboardService));  
    if (clipboardService != null)  
    // If connection manager has been copied and pasted, take no action.  
    {  
      if (clipboardService.IsPasteActive)  
      {  
        return true;  
      }  
    }  
  
    return EditSqlConnection(parentWindow);  
  }  
```  
  
### <a name="editing-the-connection-manager"></a><span data-ttu-id="b0342-120">Bearbeiten des Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="b0342-120">Editing the Connection Manager</span></span>  
 <span data-ttu-id="b0342-121">Da das Formular zum Bearbeiten sowohl von der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>-Methode als auch von der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>-Methode aufgerufen wird, sollten Sie eine Hilfsfunktion zum Kapseln des Codes, der das Formular anzeigt, verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0342-121">Because the form for editing is called from both the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> methods, it is convenient to use a helper function to encapsulate the code that displays the form.</span></span> <span data-ttu-id="b0342-122">Im folgenden Codebeispiel wird eine Implementierung dieser Hilfsfunktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b0342-122">The following code shows an implementation of this helper function.</span></span>  
  
```vb  
Private Function EditSqlConnection(ByVal parentWindow As IWin32Window) As Boolean  
  
  Dim sqlCMUIForm As New SqlConnMgrUIFormVB  
  
  sqlCMUIForm.Initialize(_connectionManager, _serviceProvider)  
  If sqlCMUIForm.ShowDialog(parentWindow) = DialogResult.OK Then  
    Return True  
  Else  
    Return False  
  End If  
  
End Function  
```  
  
```csharp  
private bool EditSqlConnection(IWin32Window parentWindow)  
 {  
  
   SqlConnMgrUIFormCS sqlCMUIForm = new SqlConnMgrUIFormCS();  
  
   sqlCMUIForm.Initialize(_connectionManager, _serviceProvider);  
   if (sqlCMUIForm.ShowDialog(parentWindow) == DialogResult.OK)  
   {  
     return true;  
   }  
   else  
   {  
     return false;  
   }  
  
 }  
```  
  
 <span data-ttu-id="b0342-123">In der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>-Methode müssen Sie nur das Formular zum Bearbeiten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0342-123">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> method, you simply have to display the form for editing.</span></span> <span data-ttu-id="b0342-124">Im folgenden Codebeispiel wird eine Implementierung der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>-Methode veranschaulicht, die den Code für das Formular mit einer Hilfsfunktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="b0342-124">The following code shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> method that uses a helper function to encapsulate the code for the form.</span></span>  
  
```vb  
Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, ByVal connectionUIArg As Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs) As Boolean Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit  
  
  Return EditSqlConnection(parentWindow)  
  
End Function  
```  
  
```csharp  
public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Microsoft.SqlServer.Dts.Runtime.Connections connections, Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs connectionUIArg)  
{  
  
  return EditSqlConnection(parentWindow);  
  
}  
```  
  
## <a name="coding-the-user-interface-form"></a><span data-ttu-id="b0342-125">Codieren des Benutzeroberflächenformulars</span><span class="sxs-lookup"><span data-stu-id="b0342-125">Coding the User Interface Form</span></span>  
 <span data-ttu-id="b0342-126">Nachdem Sie die Benutzeroberflächenklasse erstellt haben, die die Methoden der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>-Schnittstelle implementiert, müssen Sie ein Windows Form erstellen, in dem der Benutzer die Eigenschaften des Verbindungs-Managers konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="b0342-126">After creating the user interface class that implements the methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface, you must create a Windows form where the user can configure the properties of your connection manager.</span></span>  
  
### <a name="initializing-the-user-interface-form"></a><span data-ttu-id="b0342-127">Initialisieren des Benutzeroberflächenformulars</span><span class="sxs-lookup"><span data-stu-id="b0342-127">Initializing the User Interface Form</span></span>  
 <span data-ttu-id="b0342-128">Wenn Sie das benutzerdefinierte Formular zum Bearbeiten anzeigen, können Sie einen Verweis an den Verbindungs-Manager übergeben, der bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b0342-128">When you display your custom form for editing, you can pass a reference to the connection manager that is being edited.</span></span> <span data-ttu-id="b0342-129">Dazu können Sie entweder einen benutzerdefinierten Konstruktor für die Formularklasse verwenden oder, wie hier gezeigt, eine eigene `Initialize`-Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0342-129">You can pass this reference either by using a custom constructor for the form class, or by creating your own `Initialize` method as shown here.</span></span>  
  
```vb  
Public Sub Initialize(ByVal connectionManager As ConnectionManager, ByVal serviceProvider As IServiceProvider)  
  
  _connectionManager = connectionManager  
  _serviceProvider = serviceProvider  
  ConfigureControlsFromConnectionManager()  
  EnableControls()  
  
End Sub  
```  
  
```csharp  
public void Initialize(ConnectionManager connectionManager, IServiceProvider serviceProvider)  
 {  
  
   _connectionManager = connectionManager;  
   _serviceProvider = serviceProvider;  
   ConfigureControlsFromConnectionManager();  
   EnableControls();  
  
 }  
```  
  
### <a name="setting-properties-on-the-user-interface-form"></a><span data-ttu-id="b0342-130">Festlegen von Eigenschaften im Benutzeroberflächenformular</span><span class="sxs-lookup"><span data-stu-id="b0342-130">Setting Properties on the User Interface Form</span></span>  
 <span data-ttu-id="b0342-131">Zum Schluss benötigt die Formularklasse eine Hilfsfunktion, die die Steuerelemente im Formular auffüllt, wenn es zum ersten Mal mit den vorhandenen oder den Standardwerten der Eigenschaften des Verbindungs-Managers geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b0342-131">Finally, your form class needs a helper function that populates the controls on the form when it is first loaded with the existing or the default values of the properties of the connection manager.</span></span> <span data-ttu-id="b0342-132">Außerdem benötigt die Formularklasse eine ähnliche Funktion, die die Werte der Eigenschaften auf die vom Benutzer eingegebenen Werte setzt, wenn dieser auf OK klickt und das Formular schließt.</span><span class="sxs-lookup"><span data-stu-id="b0342-132">Your form class also needs a similar function that sets the values of the properties to the values entered by the user when the user clicks OK and closes the form.</span></span>  
  
```vb  
Private Const CONNECTIONNAME_BASE As String = "SqlConnectionManager"  
  
Private Sub ConfigureControlsFromConnectionManager()  
  
  Dim tempName As String  
  Dim tempServerName As String  
  Dim tempDatabaseName As String  
  
  With _connectionManager  
  
    tempName = .Properties("Name").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempName) Then  
      _connectionName = tempName  
    Else  
      _connectionName = CONNECTIONNAME_BASE  
    End If  
  
    tempServerName = .Properties("ServerName").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempServerName) Then  
      _serverName = tempServerName  
      txtServerName.Text = _serverName  
    End If  
  
    tempDatabaseName = .Properties("DatabaseName").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempDatabaseName) Then  
      _databaseName = tempDatabaseName  
      txtDatabaseName.Text = _databaseName  
    End If  
  
  End With  
  
End Sub  
  
Private Sub ConfigureConnectionManagerFromControls()  
  
  With _connectionManager  
    .Properties("Name").SetValue(_connectionManager, _connectionName)  
    .Properties("ServerName").SetValue(_connectionManager, _serverName)  
    .Properties("DatabaseName").SetValue(_connectionManager, _databaseName)  
  End With  
  
End Sub  
```  
  
```csharp  
private const string CONNECTIONNAME_BASE = "SqlConnectionManager";  
  
private void ConfigureControlsFromConnectionManager()  
 {  
  
   string tempName;  
   string tempServerName;  
   string tempDatabaseName;  
  
   {  
     tempName = _connectionManager.Properties["Name"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempName))  
     {  
       _connectionName = tempName;  
     }  
     else  
     {  
       _connectionName = CONNECTIONNAME_BASE;  
     }  
  
     tempServerName = _connectionManager.Properties["ServerName"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempServerName))  
     {  
       _serverName = tempServerName;  
       txtServerName.Text = _serverName;  
     }  
  
     tempDatabaseName = _connectionManager.Properties["DatabaseName"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempDatabaseName))  
     {  
       _databaseName = tempDatabaseName;  
       txtDatabaseName.Text = _databaseName;  
     }  
  
   }  
  
 }  
  
 private void ConfigureConnectionManagerFromControls()  
 {  
  
   {  
     _connectionManager.Properties["Name"].SetValue(_connectionManager, _connectionName);  
     _connectionManager.Properties["ServerName"].SetValue(_connectionManager, _serverName);  
     _connectionManager.Properties["DatabaseName"].SetValue(_connectionManager, _databaseName);  
   }  
  
 }  
```  
  
<span data-ttu-id="b0342-133">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="b0342-133">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b0342-134">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="b0342-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b0342-135">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="b0342-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b0342-136">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b0342-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0342-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0342-137">See Also</span></span>  
 <span data-ttu-id="b0342-138">[Erstellen eines benutzerdefinierten Verbindungs-Managers](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b0342-138">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="b0342-139">Codieren eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="b0342-139">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
  
  
