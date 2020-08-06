---
title: Erstellen eines benutzerdefinierten Tasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom tasks [Integration Services], creating
ms.assetid: 42965c09-1782-4cdb-9ce1-216af4c23e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f752acad7a442a8e0aad2d24e94938c14195a35d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619220"
---
# <a name="creating-a-custom-task"></a><span data-ttu-id="a677e-102">Erstellen eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="a677e-102">Creating a Custom Task</span></span>
  <span data-ttu-id="a677e-103">Die Schritte zum Erstellen eines benutzerdefinierten Tasks ähneln denen jedes anderen benutzerdefinierten Objekts für [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a677e-103">The steps involved in creating a custom task are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="a677e-104">Erstellen Sie eine neue Klasse, die von der Basisklasse erbt.</span><span class="sxs-lookup"><span data-stu-id="a677e-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="a677e-105">Für Tasks ist [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) die Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a677e-105">For a task, the base class is [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span></span>  
  
-   <span data-ttu-id="a677e-106">Weisen Sie das Attribut zu, das den Typ des Objekts für die Klasse identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a677e-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="a677e-107">Für einen Task ist das Attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a677e-107">For a task, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span></span>  
  
-   <span data-ttu-id="a677e-108">Überschreiben Sie die Implementierung der Methoden und Eigenschaften der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a677e-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="a677e-109">Für einen Task sind dies die Methoden <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="a677e-109">For a task, these include the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
-   <span data-ttu-id="a677e-110">Entwickeln Sie optional eine individuelle Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a677e-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="a677e-111">Für einen Task ist dazu eine Klasse erforderlich, die die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a677e-111">For a task, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface.</span></span>  
  
## <a name="getting-started-with-a-custom-task"></a><span data-ttu-id="a677e-112">Erste Schritte mit einem benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="a677e-112">Getting Started with a Custom Task</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="a677e-113">Erstellen von Projekten und Klassen</span><span class="sxs-lookup"><span data-stu-id="a677e-113">Creating Projects and Classes</span></span>  
 <span data-ttu-id="a677e-114">Da alle verwalteten Tasks von der [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task)-Basisklasse abgeleitet werden, besteht der erste Schritt beim Erstellen eines benutzerdefinierten Tasks darin, in Ihrer bevorzugten verwalteten Programmiersprache ein Klassenbibliotheksprojekt anzulegen und eine Klasse zu generieren, die von der Basisklasse erbt.</span><span class="sxs-lookup"><span data-stu-id="a677e-114">Because all managed tasks derive from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, the first step when you create a custom task is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="a677e-115">In dieser abgeleiteten Klasse überschreiben Sie die Methoden und Eigenschaften der Basisklasse, um die benutzerdefinierten Funktionen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a677e-115">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="a677e-116">Erstellen Sie in der gleichen Lösung ein zweites Klassenbibliotheksprojekt für die individuelle Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a677e-116">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="a677e-117">Für eine einfache Bereitstellung sollten Sie eine eigene Assembly für die Benutzeroberfläche verwenden, da Sie so den Verbindungs-Manager oder seine Benutzeroberfläche unabhängig aktualisieren und erneut bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="a677e-117">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="a677e-118">Konfigurieren Sie beide Projekte für das Signieren der Assemblys, die bei der Erstellung erzeugt werden, mit einer Schlüsseldatei mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="a677e-118">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtstask-attribute"></a><span data-ttu-id="a677e-119">Zuweisen des 'DtsTask'-Attributs</span><span class="sxs-lookup"><span data-stu-id="a677e-119">Applying the DtsTask Attribute</span></span>  
 <span data-ttu-id="a677e-120">Weisen Sie das <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attribut der Klasse zu, die Sie erstellt haben, um sie als Task zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="a677e-120">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class that you have created to identify it as a task.</span></span> <span data-ttu-id="a677e-121">Dieses Attribut stellt Entwurfszeitinformationen, z. B. Name, Beschreibung und Tasktyp des Tasks, bereit.</span><span class="sxs-lookup"><span data-stu-id="a677e-121">This attribute provides design-time information such as the name, description, and task type of the task.</span></span>  
  
 <span data-ttu-id="a677e-122">Verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>-Eigenschaft, um den Task mit der individuellen Benutzeroberfläche zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="a677e-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property to link the task to its custom user interface.</span></span> <span data-ttu-id="a677e-123">Um das für diese Eigenschaft erforderliche öffentliche Schlüsseltoken zu erhalten, können Sie **sn.exe -t** verwenden. Damit zeigen Sie das öffentliche Schlüsseltoken aus der Schlüsselpaardatei (.snk) an, die Sie für das Signieren der Benutzeroberflächenassembly verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a677e-123">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
## <a name="building-deploying-and-debugging-a-custom-task"></a><span data-ttu-id="a677e-124">Erstellen, Bereitstellen und Debuggen eines benutzerdefinierten Tasks</span><span class="sxs-lookup"><span data-stu-id="a677e-124">Building, Deploying, and Debugging a Custom Task</span></span>  
 <span data-ttu-id="a677e-125">Die Schritte zum Erstellen, Bereitstellen und Debuggen eines benutzerdefinierten Tasks in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] ähneln denen für andere Typen benutzerdefinierter Objekte.</span><span class="sxs-lookup"><span data-stu-id="a677e-125">The steps for building, deploying, and debugging a custom task in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="a677e-126">Weitere Informationen finden Sie unter [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) (Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten).</span><span class="sxs-lookup"><span data-stu-id="a677e-126">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="a677e-127">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a677e-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a677e-128">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a677e-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a677e-129">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a677e-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a677e-130">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a677e-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a677e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a677e-131">See Also</span></span>  
 <span data-ttu-id="a677e-132">[Erstellen eines benutzerdefinierten Tasks](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="a677e-132">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="a677e-133">[Codieren eines benutzerdefinierten Tasks](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="a677e-133">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="a677e-134">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="a677e-134">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
