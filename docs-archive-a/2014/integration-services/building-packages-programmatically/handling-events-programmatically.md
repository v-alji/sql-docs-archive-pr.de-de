---
title: Programmgesteuerte Behandlung von Ereignissen | Microsoft-Dokumentation
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
- Integration Services packages, events
- SQL Server Integration Services packages, events
- SSIS events, programmatically handling
- packages [Integration Services], events
- DtsEventHandler object
- SSIS packages, events
- SSIS events
- events [Integration Services], programmatically
- tasks [Integration Services], events
- IDTSEvents interface
ms.assetid: 0f00bd66-efd5-4f12-9e1c-36195f739332
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70d2d8909df65f775fc3a3034931bb599597068
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616142"
---
# <a name="handling-events-programmatically"></a><span data-ttu-id="29ba1-102">Programmgesteuerte Behandlung von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="29ba1-102">Handling Events Programmatically</span></span>
  <span data-ttu-id="29ba1-103">Die [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Laufzeit stellt eine Auflistung von Ereignissen bereit, die vor, während und nach der Überprüfung und Ausführung eines Pakets auftreten.</span><span class="sxs-lookup"><span data-stu-id="29ba1-103">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] runtime provides a collection of events that occur before, during, and after the validation and execution of a package.</span></span> <span data-ttu-id="29ba1-104">Diese Ereignisse können auf zwei Weisen aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="29ba1-104">These events can be captured in two ways.</span></span> <span data-ttu-id="29ba1-105">Die erste Methode besteht in der Implementierung der <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>-Schnittstelle in einer Klasse und der Bereitstellung der Klasse als Parameter für `Execute`- und `Validate`-Methoden des Pakets.</span><span class="sxs-lookup"><span data-stu-id="29ba1-105">The first method is by implementing the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface in a class, and supplying the class as a parameter to the `Execute` and `Validate` methods of the package.</span></span> <span data-ttu-id="29ba1-106">Die zweite Methode besteht in der Erstellung von <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekten, die andere [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Objekte enthalten können, wie z. B. Tasks und Loops, die ausgeführt werden, wenn ein Ereignis in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> auftritt.</span><span class="sxs-lookup"><span data-stu-id="29ba1-106">The second method is by creating <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects, which can contain other [!INCLUDE[ssIS](../../includes/ssis-md.md)] objects, such as tasks and loops, that are executed when an event in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> occurs.</span></span> <span data-ttu-id="29ba1-107">In diesem Abschnitt werden diese beiden Methoden beschrieben und zur Veranschaulichung ihrer Verwendung Codebeispiele bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="29ba1-107">This section describes these two methods and provides code examples to demonstrate their use.</span></span>  
  
## <a name="receiving-idtsevents-callbacks"></a><span data-ttu-id="29ba1-108">Empfangen von IDTSEvents-Rückrufen</span><span class="sxs-lookup"><span data-stu-id="29ba1-108">Receiving IDTSEvents Callbacks</span></span>  
 <span data-ttu-id="29ba1-109">Entwickler, die Pakete programmgesteuert erstellen und ausführen, können während des Prüfungs-und Ausführungsprozesses über die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>-Schnittstelle Ereignisbenachrichtigungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="29ba1-109">Developers who build and execute packages programmatically can receive event notifications during the validation and execution process using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface.</span></span> <span data-ttu-id="29ba1-110">Dazu wird eine Klasse erstellt, die die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>-Schnittstelle implementiert, wobei diese Klasse als Parameter für die `Validate`- und `Execute`-Methoden eines Pakets bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="29ba1-110">This is done by creating a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface and providing this class as a parameter to the `Validate` and `Execute` methods of a package.</span></span> <span data-ttu-id="29ba1-111">Die Methoden der Klasse werden dann von der Runtime-Engine aufgerufen, wenn die Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="29ba1-111">The methods of the class are then called by the run-time engine when the events occur.</span></span>  
  
 <span data-ttu-id="29ba1-112">Die <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>-Klasse ist eine Klasse, die bereits die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>-Schnittstelle implementiert; eine weitere Alternative für die direkte Implementierung von <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> besteht daher in der Ableitung von <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> und dem Überschreiben der bestimmten Ereignisse, auf die Sie reagieren wollen.</span><span class="sxs-lookup"><span data-stu-id="29ba1-112">The <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class is a class that already implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface; therefore, another alternative to implementing <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> directly is to derive from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> and override the specific events that you want to respond to.</span></span> <span data-ttu-id="29ba1-113">Dann stellen Sie Ihre Klasse als Parameter für die `Validate`- und `Execute`-Methoden von <xref:Microsoft.SqlServer.Dts.Runtime.Package> bereit, um Ereignisrückrufe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29ba1-113">You then provide your class as a parameter to the `Validate` and `Execute` methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Package> to receive event callbacks.</span></span>  
  
 <span data-ttu-id="29ba1-114">Im folgenden Codebeispiel wird eine Klasse veranschaulicht, die von <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> abgeleitet wird und die die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A>-Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="29ba1-114">The following code sample demonstrates a class that derives from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, and overrides the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A> method.</span></span> <span data-ttu-id="29ba1-115">Die-Klasse wird dann als Parameter für die `Validate` -Methode und die- `Execute` Methode des Pakets bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="29ba1-115">The class is then provided as aparameter to the `Validate` and `Execute` methods of the package.</span></span>  
  
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
      MyEventsClass eventsClass = new MyEventsClass();  
  
      p.Validate(null, null, eventsClass, null);  
      p.Execute(null, null, eventsClass, null, null);  
  
      Console.Read();  
    }  
  }  
  class MyEventsClass : DefaultEvents  
  {  
    public override void OnPreExecute(Executable exec, ref bool fireAgain)  
    {  
      // TODO: Add custom code to handle the event.  
      Console.WriteLine("The PreExecute event of the " +  
        exec.ToString() + " has been raised.");  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim eventsClass As MyEventsClass = New MyEventsClass()  
  
    p.Validate(Nothing, Nothing, eventsClass, Nothing)  
    p.Execute(Nothing, Nothing, eventsClass, Nothing, Nothing)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
Class MyEventsClass  
  Inherits DefaultEvents  
  
  Public Overrides Sub OnPreExecute(ByVal exec As Executable, ByRef fireAgain As Boolean)  
  
    ' TODO: Add custom code to handle the event.  
    Console.WriteLine("The PreExecute event of the " & _  
      exec.ToString() & " has been raised.")  
  
  End Sub  
  
End Class  
```  
  
## <a name="creating-dtseventhandler-objects"></a><span data-ttu-id="29ba1-116">Erstellen von DtsEventHandler-Objekten</span><span class="sxs-lookup"><span data-stu-id="29ba1-116">Creating DtsEventHandler Objects</span></span>  
 <span data-ttu-id="29ba1-117">Die Runtime-Engine stellt durch das <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekt eine Ereignisbehandlung und ein Benachrichtigungssystem bereit, die sich durch Robustheit und hohe Flexibilität auszeichnen.</span><span class="sxs-lookup"><span data-stu-id="29ba1-117">The run-time engine provides a robust, highly flexible event handling and notification system through the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="29ba1-118">Mit diesen Objekten können Sie innerhalb des Ereignishandlers ganze Workflows entwerfen, die nur dann ausgeführt werden, wenn das Ereignis, zu dem der Ereignishandler gehört, eintritt.</span><span class="sxs-lookup"><span data-stu-id="29ba1-118">These objects let you design whole workflows within the event handler, which execute only when the event that the event handler belongs to occurs.</span></span> <span data-ttu-id="29ba1-119">Das <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekt ist ein Container, der ausgeführt wird, wenn das entsprechende Ereignis auf seinem übergeordneten Objekt ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="29ba1-119">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object is a container that is executed when the corresponding event on its parent object fires.</span></span> <span data-ttu-id="29ba1-120">Mit dieser Architektur können Sie isolierte Workflows erstellen, die als Antwort auf Ereignisse, die in einem Container auftreten, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29ba1-120">This architecture lets you create isolated workflows that are executed in response to events that occur on a container.</span></span> <span data-ttu-id="29ba1-121">Da <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekte synchron sind, wird die Ausführung erst dann fortgesetzt, wenn die an das Ereignis angefügten Ereignishandler zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="29ba1-121">Because <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are synchronous, execution does not resume until the event handlers that are attached to the event have returned.</span></span>  
  
 <span data-ttu-id="29ba1-122">Am folgenden Code wird das Erstellen eines <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="29ba1-122">The following code demonstrates how to create a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="29ba1-123">Der Code fügt <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> zur <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A>-Auflistung des Pakets hinzu und erzeugt dann ein <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>-Objekt für das <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> Ereignis der Task.</span><span class="sxs-lookup"><span data-stu-id="29ba1-123">The code adds a <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> collection of the package, and then creates a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object for the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event of the task.</span></span> <span data-ttu-id="29ba1-124"><xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> wird zum Ereignishandler hinzugefügt, der ausgeführt wird, wenn das <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A>-Ereignis beim ersten <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> eintritt.</span><span class="sxs-lookup"><span data-stu-id="29ba1-124">A <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> is added to the event handler, which is executed when the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event occurs for the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span></span> <span data-ttu-id="29ba1-125">In diesem Beispiel wird davon ausgegangen, dass Sie eine Datei haben, die C:\Windows\Temp\DemoFile.txt für Tests genannt wird.</span><span class="sxs-lookup"><span data-stu-id="29ba1-125">This example assumes that you have a file that is named C:\Windows\Temp\DemoFile.txt for testing.</span></span> <span data-ttu-id="29ba1-126">Wenn Sie das Beispiel zum ersten Mal ausführen, kann die Datei erfolgreich kopiert werden, und der Ereignishandler wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="29ba1-126">The first time that you run the sample, if copies the file successfully and the event handler is not called.</span></span> <span data-ttu-id="29ba1-127">Wenn Sie das Beispiel zum zweiten Mal ausführen, kann der erste <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> die Datei nicht kopieren (denn der Wert von <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> ist`false`), und der Ereignishandler wird aufgerufen. Der zweite <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> löscht die Quelldatei und das Paket meldet das Auftreten des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="29ba1-127">The second time you run the sample, the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> fails to copy the file (because the value of <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> is `false`), the event handler is called, the second <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> deletes the source file, and the package reports failure because of the error that occurred.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29ba1-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29ba1-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string f = "DemoFile.txt";  
      Executable e;  
      TaskHost th;  
      FileSystemTask fst;  
  
      Package p = new Package();  
  
      p.Variables.Add("sourceFile", true, String.Empty,  
        @"C:\Windows\Temp\" + f);  
      p.Variables.Add("destinationFile", true, String.Empty,  
        Path.Combine(Directory.GetCurrentDirectory(), f));  
  
      // Create a first File System task and add it to the package.  
      // This task tries to copy a file from one folder to another.  
      e = p.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask1";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.CopyFile;  
      fst.OverwriteDestinationFile = false;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
      fst.Destination = "destinationFile";  
      fst.IsDestinationPathVariable = true;  
  
      // Add an event handler for the FileSystemTask's OnError event.  
      DtsEventHandler ehOnError = (DtsEventHandler)th.EventHandlers.Add("OnError");  
  
      // Create a second File System task and add it to the event handler.  
      // This task deletes the source file if the event handler is called.  
      e = ehOnError.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask2";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.DeleteFile;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
  
      DTSExecResult vr = p.Validate(null, null, null, null);  
      Console.WriteLine("ValidationResult = " + vr.ToString());  
      if (vr == DTSExecResult.Success)  
      {  
        DTSExecResult er = p.Execute(null, null, null, null, null);  
        Console.WriteLine("ExecutionResult = " + er.ToString());  
        if (er == DTSExecResult.Failure)  
          if (!File.Exists(@"C:\Windows\Temp\" + f))  
            Console.WriteLine("Source file has been deleted by the event handler.");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim f As String = "DemoFile.txt"  
    Dim e As Executable  
    Dim th As TaskHost  
    Dim fst As FileSystemTask  
  
    Dim p As Package = New Package()  
  
    p.Variables.Add("sourceFile", True, String.Empty, _  
      "C:\Windows\Temp\" & f)  
    p.Variables.Add("destinationFile", True, String.Empty, _  
      Path.Combine(Directory.GetCurrentDirectory(), f))  
  
    ' Create a first File System task and add it to the package.  
    ' This task tries to copy a file from one folder to another.  
    e = p.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.CopyFile  
    fst.OverwriteDestinationFile = False  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
    fst.Destination = "destinationFile"  
    fst.IsDestinationPathVariable = True  
  
    ' Add an event handler for the FileSystemTask's OnError event.  
    Dim ehOnError As DtsEventHandler = CType(th.EventHandlers.Add("OnError"), DtsEventHandler)  
  
    ' Create a second File System task and add it to the event handler.  
    ' This task deletes the source file if the event handler is called.  
    e = ehOnError.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.DeleteFile  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
  
    Dim vr As DTSExecResult = p.Validate(Nothing, Nothing, Nothing, Nothing)  
    Console.WriteLine("ValidationResult = " + vr.ToString())  
    If vr = DTSExecResult.Success Then  
      Dim er As DTSExecResult = p.Execute(Nothing, Nothing, Nothing, Nothing, Nothing)  
      Console.WriteLine("ExecutionResult = " + er.ToString())  
      If er = DTSExecResult.Failure Then  
        If Not File.Exists("C:\Windows\Temp\" + f) Then  
          Console.WriteLine("Source file has been deleted by the event handler.")  
        End If  
      End If  
    End If  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="29ba1-129">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="29ba1-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="29ba1-130">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="29ba1-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="29ba1-131">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="29ba1-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="29ba1-132">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29ba1-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ba1-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29ba1-133">See Also</span></span>  
 <span data-ttu-id="29ba1-134">[Integration Services-Ereignishandler &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="29ba1-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="29ba1-135">Hinzufügen eines Ereignishandlers zu einem Paket</span><span class="sxs-lookup"><span data-stu-id="29ba1-135">Add an Event Handler to a Package</span></span>](../add-an-event-handler-to-a-package.md)  
  
  
