---
title: Erstellen eines benutzerdefinierten Verbindungs-Managers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857efebbe311e5510e15cae9e78a2b424559ded7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726094"
---
# <a name="creating-a-custom-connection-manager"></a><span data-ttu-id="c2f91-102">Erstellen eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="c2f91-102">Creating a Custom Connection Manager</span></span>
  <span data-ttu-id="c2f91-103">Die durchzuführenden Schritte zum Erstellen eines benutzerdefinierten Verbindungs-Managers ähneln denen jedes anderen benutzerdefinierten Objekts für [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c2f91-103">The steps that you must follow to create a custom connection manager are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c2f91-104">Erstellen Sie eine neue Klasse, die von der Basisklasse erbt.</span><span class="sxs-lookup"><span data-stu-id="c2f91-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="c2f91-105">Bei einem Verbindungs-Manager ist die Basisklasse <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="c2f91-105">For a connection manager, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span></span>  
  
-   <span data-ttu-id="c2f91-106">Weisen Sie das Attribut zu, das den Typ des Objekts für die Klasse identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c2f91-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="c2f91-107">Bei einem Verbindungs-Manager ist das Attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c2f91-107">For a connection manager, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
-   <span data-ttu-id="c2f91-108">Überschreiben Sie die Implementierung der Methoden und Eigenschaften der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="c2f91-108">Override the implementation of the methods and properties of the base class.</span></span> <span data-ttu-id="c2f91-109">Bei einem Verbindungs-Manager gehören dazu die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A>-Eigenschaft sowie die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>-Methode und die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c2f91-109">For a connection manager, these include the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods.</span></span>  
  
-   <span data-ttu-id="c2f91-110">Entwickeln Sie optional eine individuelle Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="c2f91-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="c2f91-111">Bei einem Verbindungs-Manager ist dazu eine Klasse erforderlich, die die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="c2f91-111">For a connection manager, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2f91-112">Die meisten Tasks, Quellen und Ziele, die in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] integriert wurden, können nur mit bestimmten Typen integrierter Verbindungs-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2f91-112">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="c2f91-113">Daher können diese Beispiele nicht mit den integrierten Tasks und Komponenten getestet werden.</span><span class="sxs-lookup"><span data-stu-id="c2f91-113">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="getting-started-with-a-custom-connection-manager"></a><span data-ttu-id="c2f91-114">Erste Schritte mit einem benutzerdefinierten Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="c2f91-114">Getting Started with a Custom Connection Manager</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="c2f91-115">Erstellen von Projekten und Klassen</span><span class="sxs-lookup"><span data-stu-id="c2f91-115">Creating Projects and Classes</span></span>  
 <span data-ttu-id="c2f91-116">Da alle verwalteten Verbindungs-Manager von der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>-Basisklasse abgeleitet sind, besteht der erste Schritt beim Erstellen eines benutzerdefinierten Verbindungs-Managers darin, in Ihrer bevorzugten verwalteten Programmiersprache ein Klassenbibliotheksprojekt anzulegen und eine Klasse zu generieren, die von der Basisklasse erbt.</span><span class="sxs-lookup"><span data-stu-id="c2f91-116">Because all managed connection managers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, the first step when you create a custom connection manager is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="c2f91-117">In dieser abgeleiteten Klasse überschreiben Sie die Methoden und Eigenschaften der Basisklasse, um die benutzerdefinierten Funktionen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c2f91-117">In this derived class, you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="c2f91-118">Erstellen Sie in der gleichen Lösung ein zweites Klassenbibliotheksprojekt für die individuelle Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="c2f91-118">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="c2f91-119">Für eine einfache Bereitstellung sollten Sie eine eigene Assembly für die Benutzeroberfläche verwenden, da Sie so den Verbindungs-Manager oder seine Benutzeroberfläche unabhängig aktualisieren und erneut bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="c2f91-119">A separate assembly for the user interface is recommended for ease of deployment because it lets you update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="c2f91-120">Konfigurieren Sie beide Projekte für das Signieren der Assemblys, die bei der Erstellung erzeugt werden, mit einer Schlüsseldatei mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="c2f91-120">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsconnection-attribute"></a><span data-ttu-id="c2f91-121">Zuweisen des 'DtsConnection'-Attributs</span><span class="sxs-lookup"><span data-stu-id="c2f91-121">Applying the DtsConnection Attribute</span></span>  
 <span data-ttu-id="c2f91-122">Weisen Sie das <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>-Attribut der Klasse zu, die Sie erstellt haben, um sie als Verbindungs-Manager zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c2f91-122">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class that you have created to identify it as a connection manager.</span></span> <span data-ttu-id="c2f91-123">Dieses Attribut stellt Entwurfszeitinformationen bereit, z. B. Name, Beschreibung und Verbindungstyp des Verbindungs-Managers.</span><span class="sxs-lookup"><span data-stu-id="c2f91-123">This attribute provides design-time information such as the name, description, and connection type of the connection manager.</span></span> <span data-ttu-id="c2f91-124">Die <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> `Description` Eigenschaften und entsprechen dem **Typ** und den `Description` Spalten, die im Dialogfeld **SSIS-Verbindungs-Manager hinzufügen** angezeigt werden. dieses Dialogfeld wird beim Konfigurieren von Verbindungen für ein Paket in angezeigt [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2f91-124">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> and `Description` properties correspond to the **Type** and `Description` columns displayed in the **Add SSIS Connection Manager** dialog box, which is displayed when configuring connections for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c2f91-125">Verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A>-Eigenschaft, um den Verbindungs-Manager mit der individuellen Benutzeroberfläche zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="c2f91-125">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property to link the connection manager to its custom user interface.</span></span> <span data-ttu-id="c2f91-126">Um das für diese Eigenschaft erforderliche öffentliche Schlüsseltoken zu erhalten, können Sie **sn.exe -t** verwenden. Damit zeigen Sie das öffentliche Schlüsseltoken aus der Schlüsselpaardatei (.snk) an, die Sie für das Signieren der Benutzeroberflächenassembly verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c2f91-126">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a><span data-ttu-id="c2f91-127">Erstellen, Bereitstellen und Debuggen eines benutzerdefinierten Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="c2f91-127">Building, Deploying, and Debugging a Custom Connection Manager</span></span>  
 <span data-ttu-id="c2f91-128">Die Schritte zum Erstellen, Bereitstellen und Debuggen eines benutzerdefinierten Verbindungs-Managers in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] ähneln denen für andere Typen benutzerdefinierter Objekte.</span><span class="sxs-lookup"><span data-stu-id="c2f91-128">The steps for building, deploying, and debugging a custom connection manager in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps for other types of custom objects.</span></span> <span data-ttu-id="c2f91-129">Weitere Informationen finden Sie unter [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) (Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten).</span><span class="sxs-lookup"><span data-stu-id="c2f91-129">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="c2f91-130">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="c2f91-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c2f91-131">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="c2f91-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c2f91-132">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="c2f91-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c2f91-133">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c2f91-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f91-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2f91-134">See Also</span></span>  
 <span data-ttu-id="c2f91-135">[Codieren eines benutzerdefinierten Verbindungs-Managers](coding-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c2f91-135">[Coding a Custom Connection Manager](coding-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="c2f91-136">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="c2f91-136">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
