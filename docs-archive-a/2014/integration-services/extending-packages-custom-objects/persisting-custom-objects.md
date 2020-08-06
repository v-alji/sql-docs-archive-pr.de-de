---
title: Beibehalten von benutzerdefinierten Objekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom objects [Integration Services], persisting
ms.assetid: 97c19716-6447-4c1c-b277-cc2e6c1e6a6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55baa48f1ab0cf4175592b095463c9f12293b83f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621594"
---
# <a name="persisting-custom-objects"></a><span data-ttu-id="5ecfe-102">Beibehalten von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="5ecfe-102">Persisting Custom Objects</span></span>
  <span data-ttu-id="5ecfe-103">Sie müssen keine benutzerdefinierte Persistenz für die von Ihnen erstellten benutzerdefinierten Objekte einfügen, solange ihre Eigenschaften nur einfache Datentypen wie `integer` und `string` verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-103">You do not need to implement custom persistence for the custom objects that you create as long as their properties use only simple data types such as `integer` and `string`.</span></span> <span data-ttu-id="5ecfe-104">Die Standardimplementierung der Persistenz speichert die Metadaten Ihres Objekts zusammen mit den Werten aller Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-104">The default implementation of persistence saves the metadata for your object along with the values of all its properties.</span></span>  
  
 <span data-ttu-id="5ecfe-105">Falls Ihr Objekt jedoch Eigenschaften hat, die komplexe Datentypen verwenden, oder wenn Sie benutzerdefinierte Verarbeitung beim Laden und Speichern von Eigenschaftswerten durchführen möchten, können Sie die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist>-Schnittstelle und ihre Methoden <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.LoadFromXML%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.SaveToXML%2A> implementieren.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-105">However, if your object has properties that use complex data types, or if you want to perform custom processing on property values as they are loaded and saved, you can implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist> interface and its <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.LoadFromXML%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.SaveToXML%2A> methods.</span></span> <span data-ttu-id="5ecfe-106">In diesen Methoden laden Sie aus der XML-Definition des Pakets (oder speichern darin) ein XML-Fragment, das die Eigenschaften des Objekts und ihre aktuellen Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-106">In these methods you load from (or save to) the XML definition of the package an XML fragment that contains the properties of your object and their current values.</span></span> <span data-ttu-id="5ecfe-107">Das Format dieses XML-Fragments wird nicht definiert; es muss nur wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-107">The format of this XML fragment is not defined; it must only be well-formed XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5ecfe-108">Beim Implementieren von benutzerdefinierter Persistenz müssen Sie alle Eigenschaften des Objekts dauerhaft machen, einschließlich der beiden übernommenen Eigenschaften und der hinzugefügten benutzerdefinierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-108">When you implement custom persistence, you must persist all the properties of the object, including both inherited properties and custom properties that you have added.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ecfe-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ecfe-109">Example</span></span>  
 <span data-ttu-id="5ecfe-110">Obwohl das SQL Server Custom Connection Manager-Beispiel keine benutzerdefinierte Persistenz für die drei Eigenschaften des Typs erfordert `string` , zeigt der folgende Code ein Beispiel für den benutzerdefinierten Code, der erforderlich wäre, um den Verbindungs-Manager und dessen Eigenschaften beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-110">Although the Sql Server Custom Connection Manager Sample does not require custom persistence for its three properties of type `string`, the following code shows an example of the custom code that would be required to persist the connection manager and its properties.</span></span> <span data-ttu-id="5ecfe-111">Die Klasse, die diesen Code enthält, muss die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-111">The class that contains this code must implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist> interface.</span></span>  
  
```vb  
Private Const PERSIST_ELEMENT As String = "SqlConnectionManager"  
Private Const PERSIST_SERVER As String = "Server"  
Private Const PERSIST_DATABASE As String = "Database"  
Private Const PERSIST_CONNECTIONSTRING As String = "ConnectionString"  
  
Public Sub LoadFromXML(ByVal node As System.Xml.XmlElement, _  
  ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) _  
  Implements Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.LoadFromXML  
  
  Dim propertyNode As XmlNode  
  
  ' Make sure that the correct node is being loaded.  
  If node.Name <> PERSIST_ELEMENT Then  
    Throw New Exception("Persisted element is not of type " & PERSIST_ELEMENT)  
  End If  
  
  ' Load the three properties of the object from XML into variables.  
  For Each propertyNode In node.ChildNodes  
    Select Case propertyNode.Name  
      Case PERSIST_SERVER  
        _serverName = propertyNode.InnerText  
      Case PERSIST_DATABASE  
        _databaseName = propertyNode.InnerText  
      Case PERSIST_CONNECTIONSTRING  
        _connectionString = propertyNode.InnerText  
    End Select  
  Next  
  
End Sub  
  
Public Sub SaveToXML(ByVal doc As System.Xml.XmlDocument, _  
  ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) _  
  Implements Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.SaveToXML  
  
  Dim elementRoot As XmlElement  
  Dim propertyNode As XmlNode  
  
  ' Create a new node to persist the object and its properties.  
  elementRoot = doc.CreateElement(String.Empty, PERSIST_ELEMENT, String.Empty)  
  
  ' Save the three properties of the object from variables into XML.  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_SERVER, String.Empty)  
  propertyNode.InnerText = _serverName  
  elementRoot.AppendChild(propertyNode)  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_DATABASE, String.Empty)  
  propertyNode.InnerText = _databaseName  
  elementRoot.AppendChild(propertyNode)  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_CONNECTIONSTRING, String.Empty)  
  propertyNode.InnerText = _connectionString  
  elementRoot.AppendChild(propertyNode)  
  
  doc.AppendChild(elementRoot)  
  
End Sub  
```  
  
```csharp  
private const string PERSIST_ELEMENT = "SqlConnectionManager";  
private const string PERSIST_SERVER = "Server";  
private const string PERSIST_DATABASE = "Database";  
private const string PERSIST_CONNECTIONSTRING = "ConnectionString";  
  
public void LoadFromXML(System.Xml.XmlElement node,  
  Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  // Make sure that the correct node is being loaded.  
  if (node.Name != PERSIST_ELEMENT)  
  {  
    throw new Exception("Persisted element is not of type " + PERSIST_ELEMENT);  
  }  
  
  // Save the three properties of the object from variables into XML.  
  foreach (XmlNode propertyNode in node.ChildNodes)  
  {  
    switch (propertyNode.Name)  
    {  
      case PERSIST_SERVER:  
        _serverName = propertyNode.InnerText;  
        break;  
      case PERSIST_DATABASE:  
        _databaseName = propertyNode.InnerText;  
        break;  
      case PERSIST_CONNECTIONSTRING:  
        _connectionString = propertyNode.InnerText;  
        break;  
    }  
  }  
  
}  
  
public void SaveToXML(System.Xml.XmlDocument doc,  
  Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  XmlElement elementRoot;  
  XmlNode propertyNode;  
  
  // Create a new node to persist the object and its properties.  
  elementRoot = doc.CreateElement(String.Empty, PERSIST_ELEMENT, String.Empty);  
  
  // Save the three properties of the object from variables into XML.  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_SERVER, String.Empty);  
  propertyNode.InnerText = _serverName;  
  elementRoot.AppendChild(propertyNode);  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_DATABASE, String.Empty);  
  propertyNode.InnerText = _databaseName;  
  elementRoot.AppendChild(propertyNode);  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_CONNECTIONSTRING, String.Empty);  
  propertyNode.InnerText = _connectionString;  
  elementRoot.AppendChild(propertyNode);  
  
  doc.AppendChild(elementRoot);  
  
}  
```  
  
<span data-ttu-id="5ecfe-112">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="5ecfe-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5ecfe-113">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="5ecfe-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5ecfe-114">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="5ecfe-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5ecfe-115">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5ecfe-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecfe-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ecfe-116">See Also</span></span>  
 <span data-ttu-id="5ecfe-117">[Entwickeln von benutzerdefinierten Objekten für Integration Services](developing-custom-objects-for-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="5ecfe-117">[Developing Custom Objects for Integration Services](developing-custom-objects-for-integration-services.md) </span></span>  
 [<span data-ttu-id="5ecfe-118">Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten</span><span class="sxs-lookup"><span data-stu-id="5ecfe-118">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
  
  
