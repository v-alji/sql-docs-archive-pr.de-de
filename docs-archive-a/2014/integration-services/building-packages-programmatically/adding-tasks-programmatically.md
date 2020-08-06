---
title: Programmgesteuertes Hinzufügen von Tasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], packages
- adding package tasks
ms.assetid: 5d4652d5-228c-4238-905c-346dd8503fdf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa61eb2fb87f45fe5b534b96280b8b4e2c21788d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616650"
---
# <a name="adding-tasks-programmatically"></a><span data-ttu-id="6aa57-102">Programmgesteuertes Hinzufügen von Tasks</span><span class="sxs-lookup"><span data-stu-id="6aa57-102">Adding Tasks Programmatically</span></span>
  <span data-ttu-id="6aa57-103">Folgenden Objekttypen in der Runtime-Engine können Tasks hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="6aa57-103">Tasks can be added to the following types of objects in the run-time engine:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Package>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Sequence>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>  
  
 <span data-ttu-id="6aa57-104">Diese Klassen werden als Container angesehen, und sie alle erben die <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6aa57-104">These classes are considered containers, and they all inherit the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A> property.</span></span> <span data-ttu-id="6aa57-105">Container können eine Auflistung von Tasks enthalten. Dies sind ausführbare Objekte, die von der Laufzeit bei der Ausführung des Containers verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6aa57-105">Containers can contain a collection of tasks, which are executable objects processed by the runtime during execution of the container.</span></span> <span data-ttu-id="6aa57-106">Die Ausführungsreihenfolge der Objekte in der Auflistung hängt von den <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> ab, die für die einzelnen Tasks im Container festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="6aa57-106">The order of execution of the objects in the collection is determined any <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> set on each task in the containers.</span></span> <span data-ttu-id="6aa57-107">Rangfolgeneinschränkungen ermöglichen eine verzweigte Ausführung, abhängig vom Erfolg, Fehlschlag oder der Beendigung einer <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6aa57-107">Precedence constraints enable execution branching based on the success, failure, or completion of an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in the collection.</span></span>  
  
 <span data-ttu-id="6aa57-108">Jeder Container verfügt über eine <xref:Microsoft.SqlServer.Dts.Runtime.Executables>-Auflistung, die die einzelnen <xref:Microsoft.SqlServer.Dts.Runtime.Executable>-Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="6aa57-108">Each container has an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection that contains the individual <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects.</span></span> <span data-ttu-id="6aa57-109">Jeder ausführbare Task erbt und implementiert die <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A>-Methode sowie die <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="6aa57-109">Each executable task inherits and implements the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> method and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> method.</span></span> <span data-ttu-id="6aa57-110">Diese zwei Methoden werden von der Runtime-Engine aufgerufen, um jede <xref:Microsoft.SqlServer.Dts.Runtime.Executable> zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6aa57-110">These two methods are called by the run-time engine to process each <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span></span>  
  
 <span data-ttu-id="6aa57-111">Um einem Paket einen Task hinzuzufügen, benötigen Sie einen Container mit einer Auflistung vorhandener <xref:Microsoft.SqlServer.Dts.Runtime.Executables>.</span><span class="sxs-lookup"><span data-stu-id="6aa57-111">To add a task to a package, you need a container with an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existing collection.</span></span> <span data-ttu-id="6aa57-112">Meist handelt es sich bei dem Task, den Sie der Auflistung hinzufügen, um ein Paket.</span><span class="sxs-lookup"><span data-stu-id="6aa57-112">Most of the time, the task that you will add to the collection is a package.</span></span> <span data-ttu-id="6aa57-113">Um der Auflistung des Containers die neue ausführbare Datei des Tasks hinzuzufügen, rufen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="6aa57-113">To add the new task executable into the collection for that container, you call the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method .</span></span> <span data-ttu-id="6aa57-114">Die Methode verfügt über einen Parameter, eine Zeichenfolge, die den CLSID-, PROGID- bzw. STOCK-Moniker oder den <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> des Tasks, den Sie hinzufügen, enthält.</span><span class="sxs-lookup"><span data-stu-id="6aa57-114">The method has a single parameter, a string, that contains the CLSID, PROGID, STOCK moniker, or <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> of the task you are adding.</span></span>  
  
## <a name="task-names"></a><span data-ttu-id="6aa57-115">Tasknamen</span><span class="sxs-lookup"><span data-stu-id="6aa57-115">Task Names</span></span>  
 <span data-ttu-id="6aa57-116">Sie können einen Task zwar über einen Namen oder eine ID definieren, aber der `STOCK`-Moniker ist der am häufigsten für die <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>-Methode verwendete Parameter.</span><span class="sxs-lookup"><span data-stu-id="6aa57-116">Although you can specify a task by name or by ID, the `STOCK` moniker is the parameter used most often in the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method.</span></span> <span data-ttu-id="6aa57-117">Verwenden Sie die folgende Syntax, um einen Task einer ausführbaren Datei hinzuzufügen, die durch den `STOCK`-Moniker identifiziert wird:</span><span class="sxs-lookup"><span data-stu-id="6aa57-117">To add a task to an executable identified by the `STOCK` moniker, use the following syntax:</span></span>  
  
```csharp  
Executable exec = package.Executables.Add("STOCK:BulkInsertTask");  
  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add("STOCK:BulkInsertTask")  
  
```  
  
 <span data-ttu-id="6aa57-118">Die folgende Liste zeigt die Namen für alle Tasks an, die nach dem `STOCK`-Moniker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6aa57-118">The following list shows the names for each task that are used after the `STOCK` moniker.</span></span>  
  
-   <span data-ttu-id="6aa57-119">ActiveXScriptTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-119">ActiveXScriptTask</span></span>  
  
-   <span data-ttu-id="6aa57-120">BulkInsertTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-120">BulkInsertTask</span></span>  
  
-   <span data-ttu-id="6aa57-121">ExecuteProcessTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-121">ExecuteProcessTask</span></span>  
  
-   <span data-ttu-id="6aa57-122">ExecutePackageTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-122">ExecutePackageTask</span></span>  
  
-   <span data-ttu-id="6aa57-123">Exec80PackageTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-123">Exec80PackageTask</span></span>  
  
-   <span data-ttu-id="6aa57-124">FileSystemTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-124">FileSystemTask</span></span>  
  
-   <span data-ttu-id="6aa57-125">FTPTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-125">FTPTask</span></span>  
  
-   <span data-ttu-id="6aa57-126">MSMQTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-126">MSMQTask</span></span>  
  
-   <span data-ttu-id="6aa57-127">PipelineTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-127">PipelineTask</span></span>  
  
-   <span data-ttu-id="6aa57-128">ScriptTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-128">ScriptTask</span></span>  
  
-   <span data-ttu-id="6aa57-129">SendMailTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-129">SendMailTask</span></span>  
  
-   <span data-ttu-id="6aa57-130">SQLTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-130">SQLTask</span></span>  
  
-   <span data-ttu-id="6aa57-131">TransferStoredProceduresTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-131">TransferStoredProceduresTask</span></span>  
  
-   <span data-ttu-id="6aa57-132">TransferLoginsTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-132">TransferLoginsTask</span></span>  
  
-   <span data-ttu-id="6aa57-133">TransferErrorMessagesTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-133">TransferErrorMessagesTask</span></span>  
  
-   <span data-ttu-id="6aa57-134">TransferJobsTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-134">TransferJobsTask</span></span>  
  
-   <span data-ttu-id="6aa57-135">TransferObjectsTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-135">TransferObjectsTask</span></span>  
  
-   <span data-ttu-id="6aa57-136">TransferDatabaseTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-136">TransferDatabaseTask</span></span>  
  
-   <span data-ttu-id="6aa57-137">WebServiceTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-137">WebServiceTask</span></span>  
  
-   <span data-ttu-id="6aa57-138">WmiDataReaderTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-138">WmiDataReaderTask</span></span>  
  
-   <span data-ttu-id="6aa57-139">WmiEventWatcherTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-139">WmiEventWatcherTask</span></span>  
  
-   <span data-ttu-id="6aa57-140">XMLTask</span><span class="sxs-lookup"><span data-stu-id="6aa57-140">XMLTask</span></span>  
  
 <span data-ttu-id="6aa57-141">Wenn Sie eine explizitere Syntax bevorzugen oder der Task, den Sie hinzufügen möchten, nicht über einen STOCK-Moniker verfügt, können Sie den Task unter Verwendung seines langen Namens der ausführbaren Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6aa57-141">If you prefer a more explicit syntax, or if the task that you want to add does not have a STOCK moniker, you can add the task to the executable using its long name.</span></span> <span data-ttu-id="6aa57-142">Bei dieser Syntax müssen Sie auch die Versionsnummer des Tasks angeben.</span><span class="sxs-lookup"><span data-stu-id="6aa57-142">This syntax requires that you also specify the version number of the task.</span></span>  
  
```csharp  
Executable exec = package.Executables.Add(  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " +  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " +  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91");  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add( _  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " & _  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " & _  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91")  
```  
  
 <span data-ttu-id="6aa57-143">Sie können den langen Namen des Tasks programmgesteuert mithilfe der **AssemblyQualifiedName**-Eigenschaft der Klasse erhalten, ohne die Taskversion angeben zu müssen. Dies wird im nächsten Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6aa57-143">You can obtain the long name for the task programmatically, without having to specify the task version, by using the **AssemblyQualifiedName** property of the class, as shown in the following example.</span></span> <span data-ttu-id="6aa57-144">Für dieses Beispiel ist ein Verweis auf die Microsoft.SqlServer.SQLTask-Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6aa57-144">This example requires a reference to the Microsoft.SqlServer.SQLTask assembly.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask;  
...  
      Executable exec = package.Executables.Add(  
        typeof(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName);  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask  
...  
    Dim exec As Executable = package.Executables.Add( _  
      GetType(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName)  
```  
  
 <span data-ttu-id="6aa57-145">Im folgenden Codebeispiel wird die Erstellung einer <xref:Microsoft.SqlServer.Dts.Runtime.Executables>-Auflistung aus einem neuen Paket veranschaulicht. Anschließend wird der Auflistung unter Verwendung der `STOCK`-Moniker ein Dateisystem- und ein Masseneinfügungstask hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6aa57-145">The following code example shows how to create an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection from a new package, and then add a File System task and a Bulk Insert task to the collection, by using their `STOCK` monikers.</span></span> <span data-ttu-id="6aa57-146">Für dieses Beispiel ist einVerweis auf die Microsoft.SqlServer.FileSystemTask- sowie die Microsoft.SqlServer.BulkInsertTask-Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6aa57-146">This example requires a reference to the Microsoft.SqlServer.FileSystemTask and Microsoft.SqlServer.BulkInsertTask assemblies.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thBulkInsertTask = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        Console.WriteLine("Type {0}", taskHost.InnerObject.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thBulkInsertTask As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      Console.WriteLine("Type {0}", taskHost.InnerObject.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="6aa57-147">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="6aa57-147">**Sample Output:**</span></span>  
  
 `Type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
## <a name="taskhost-container"></a><span data-ttu-id="6aa57-148">TaskHost-Container</span><span class="sxs-lookup"><span data-stu-id="6aa57-148">TaskHost Container</span></span>  
 <span data-ttu-id="6aa57-149">Bei der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Klasse handelt es sich um einen Container, der nicht auf der grafischen Benutzeroberfläche angezeigt wird, aber für die Programmierung sehr wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="6aa57-149">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class is a container that does not appear in the graphical user interface, but is very important in programming.</span></span> <span data-ttu-id="6aa57-150">Diese Klasse dient als Wrapper für alle Tasks.</span><span class="sxs-lookup"><span data-stu-id="6aa57-150">This class is a wrapper for every task.</span></span> <span data-ttu-id="6aa57-151">Tasks, die dem Paket mithilfe der<xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>-Methode als <xref:Microsoft.SqlServer.Dts.Runtime.Executable>-Objekte hinzugefügt werden, können in <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekte umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6aa57-151">Tasks that are added to the package by using the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object can be cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object.</span></span> <span data-ttu-id="6aa57-152">Wenn ein Task in ein <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt umgewandelt ist, können Sie auf den Task zusätzliche Eigenschaften und Methoden anwenden.</span><span class="sxs-lookup"><span data-stu-id="6aa57-152">When a task is cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, you can use additional properties and methods on the task.</span></span> <span data-ttu-id="6aa57-153">Darüber hinaus können Sie über die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> direkt auf den Task zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6aa57-153">Also, the task itself can be accessed through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="6aa57-154">Abhängig von Ihren Anforderungen können Sie den Task als <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt beibehalten, um die Eigenschaften des Tasks in der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>-Auflistung anwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="6aa57-154">Depending on your needs, you may decide to keep the task as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object so that you can use the properties of the task through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection.</span></span> <span data-ttu-id="6aa57-155">Der Vorteil, den die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> bieten, besteht darin, dass Sie allgemeineren Code schreiben können.</span><span class="sxs-lookup"><span data-stu-id="6aa57-155">The advantage of using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> is that you can write more generic code.</span></span> <span data-ttu-id="6aa57-156">Falls Sie für einen Task sehr spezifischen Code benötigen, sollten Sie den Task in das entsprechende Objekt umwandeln.</span><span class="sxs-lookup"><span data-stu-id="6aa57-156">If you need very specific code for a task, then you should cast the task to its appropriate object.</span></span>  
  
 <span data-ttu-id="6aa57-157">Das folgende Codebeispiel zeigt die Umwandlung eines <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, der einen <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> enthält, in ein <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="6aa57-157">The following code example shows how to cast a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, that contains a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> object.</span></span>  
  
```csharp  
BulkInsertTask myTask = thBulkInsertTask.InnerObject as BulkInsertTask;  
```  
  
```vb  
Dim myTask As BulkInsertTask = CType(thBulkInsertTask.InnerObject, BulkInsertTask)  
```  
  
 <span data-ttu-id="6aa57-158">Im folgenden Codebeispiel wird veranschaulicht, wie eine ausführbare Datei in einen <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> umgewandelt wird. Anschließend wird über die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A>-Eigenschaft der im Host enthaltene ausführbare Dateityp ermittelt.</span><span class="sxs-lookup"><span data-stu-id="6aa57-158">The following code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property to determine which type of executable is contained by the host.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask1 = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thFileSystemTask2 = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask)  
        {  
          // Do work with FileSystemTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        else if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask)  
        {  
          // Do work with BulkInsertTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        // Add additional statements to check InnerObject, if desired.  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask1 As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thFileSystemTask2 As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      If TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask Then  
        ' Do work with FileSystemTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      ElseIf TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask Then  
        ' Do work with BulkInsertTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      End If  
      ' Add additional statements to check InnerObject, if desired.  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="6aa57-159">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="6aa57-159">**Sample Output:**</span></span>  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
 <span data-ttu-id="6aa57-160">Die <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>-Anweisung gibt eine ausführbare Datei zurück, die aus dem neu geschaffenen <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Objekt in ein <xref:Microsoft.SqlServer.Dts.Runtime.Executable>-Objekt umgewandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="6aa57-160">The <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> statement returns an executable that is cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object from the newly created <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object.</span></span>  
  
 <span data-ttu-id="6aa57-161">Um Eigenschaften festzulegen oder Methoden auf dem neuen Objekt aufzurufen, haben Sie zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="6aa57-161">To set properties or to call methods on the new object, you have two options:</span></span>  
  
1.  <span data-ttu-id="6aa57-162">Verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>-Auflistung des <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="6aa57-162">Use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="6aa57-163">Verwenden Sie beispielsweise `th.Properties["propertyname"].GetValue(th))`, um eine Eigenschaft des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6aa57-163">For example, to obtain a property from the object, use `th.Properties["propertyname"].GetValue(th))`.</span></span> <span data-ttu-id="6aa57-164">Zum Festlegen einer Eigenschaft nutzen Sie `th.Properties["propertyname"].SetValue(th, <value>);`.</span><span class="sxs-lookup"><span data-stu-id="6aa57-164">To set a property, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span></span>  
  
2.  <span data-ttu-id="6aa57-165">Wandeln Sie das <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> des <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> in die Taskklasse um.</span><span class="sxs-lookup"><span data-stu-id="6aa57-165">Cast the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task class.</span></span> <span data-ttu-id="6aa57-166">Zum Umwandeln des Masseneinfügungstasks in einen <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, nachdem er dem Paket als <xref:Microsoft.SqlServer.Dts.Runtime.Executable> hinzugefügt und anschließend in einen <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> umgewandelt wurde, verwenden Sie beispielsweise `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span><span class="sxs-lookup"><span data-stu-id="6aa57-166">For example, to cast the Bulk Insert task to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> after it has been added to a package as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> and subsequently cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span></span>  
  
 <span data-ttu-id="6aa57-167">Die Verwendung der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>-Klasse im Code anstelle der Umwandlung in die taskspezifische Klasse bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="6aa57-167">Using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class in code, instead of casting to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="6aa57-168">Der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>-Anbieter benötigt keinen Verweis auf die Assembly im Code.</span><span class="sxs-lookup"><span data-stu-id="6aa57-168">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> provider does not require a reference to the assembly in the code.</span></span>  
  
-   <span data-ttu-id="6aa57-169">Sie können Code für generische Routinen schreiben, die für jeden Task anwendbar sind, da Sie bei der Kompilierung nicht über den Namen des Tasks verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="6aa57-169">You can code generic routines that work for any task, because you do not have to know the name of the task at compile time.</span></span> <span data-ttu-id="6aa57-170">Zu diesen generischen Routinen zählen Methoden, bei denen Sie den Tasknamen an die Methode übergeben und der Methodencode für alle Tasks geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="6aa57-170">Such generic routines include methods where you pass in the name of the task to the method, and the method code works for all tasks.</span></span> <span data-ttu-id="6aa57-171">Diese Methode ist gut für das Schreiben von Testcode geeignet.</span><span class="sxs-lookup"><span data-stu-id="6aa57-171">This is a good method for writing test code.</span></span>  
  
 <span data-ttu-id="6aa57-172">Die Umwandlung vom <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> in die taskspezifische Klasse bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="6aa57-172">Casting from the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="6aa57-173">Das Visual Studio-Projekt bietet Ihnen die Anweisungsvervollständigung (IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="6aa57-173">The Visual Studio project gives you statement completion (IntelliSense).</span></span>  
  
-   <span data-ttu-id="6aa57-174">Der Code wird möglicherweise schneller ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6aa57-174">The code may run faster.</span></span>  
  
-   <span data-ttu-id="6aa57-175">Taskspezifische Objekte ermöglichen eine frühe Bindung und die daraus resultierenden Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="6aa57-175">Task-specific objects enable early binding and the resulting optimizations.</span></span> <span data-ttu-id="6aa57-176">Weitere Informationen zur frühen und späten Bindung finden Sie im entsprechenden Thema der Visual Basic-Sprachkonzepte.</span><span class="sxs-lookup"><span data-stu-id="6aa57-176">For more information about early and late binding, see the topic "Early and Late Binding" in Visual Basic Language Concepts.</span></span>  
  
 <span data-ttu-id="6aa57-177">Im folgenden Codebeispiel wird das Konzept der Wiederverwendung von Taskcode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6aa57-177">The following code example expands on the concept of reusing task code.</span></span> <span data-ttu-id="6aa57-178">Anstatt Tasks in ihre jeweiligen Klassenentsprechungen umzuwandeln, wird in diesem Codebeispiel die Umwandlung der ausführbaren Datei in einen <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> und die anschließende Verwendung der <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> zum Schreiben von generischen Codes für alle Tasks gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6aa57-178">Instead of casting tasks to their specific class equivalents, the code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then uses the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> to write generic code against all the tasks.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
  
      string[] tasks = { "STOCK:SQLTask", "STOCK:ScriptTask",   
        "STOCK:ExecuteProcessTask", "STOCK:PipelineTask",   
        "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask" };  
  
      foreach (string s in tasks)  
      {  
        TaskHost taskhost = package.Executables.Add(s) as TaskHost;  
        DtsProperties props = taskhost.Properties;  
        Console.WriteLine("Enumerating properties on " + taskhost.Name);  
        Console.WriteLine(" TaskHost.InnerObject is " + taskhost.InnerObject.ToString());  
        Console.WriteLine();  
  
        foreach (DtsProperty prop in props)  
        {  
          Console.WriteLine("Properties for " + prop.Name);  
          Console.WriteLine("Name : " + prop.Name);  
          Console.WriteLine("Type : " + prop.Type.ToString());  
          Console.WriteLine("Readable : " + prop.Get.ToString());  
          Console.WriteLine("Writable : " + prop.Set.ToString());  
          Console.WriteLine();  
        }  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package = New Package()  
  
    Dim tasks() As String = New String() {"STOCK:SQLTask", "STOCK:ScriptTask", _  
              "STOCK:ExecuteProcessTask", "STOCK:PipelineTask", _  
              "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask"}  
  
    For Each s As String In tasks  
  
      Dim taskhost As TaskHost = CType(package.Executables.Add(s), TaskHost)  
      Dim props As DtsProperties = taskhost.Properties  
      Console.WriteLine("Enumerating properties on " & taskhost.Name)  
      Console.WriteLine(" TaskHost.InnerObject is " & taskhost.InnerObject.ToString())  
      Console.WriteLine()  
  
      For Each prop As DtsProperty In props  
        Console.WriteLine("Properties for " + prop.Name)  
        Console.WriteLine(" Name : " + prop.Name)  
        Console.WriteLine(" Type : " + prop.Type.ToString())  
        Console.WriteLine(" Readable : " + prop.Get.ToString())  
        Console.WriteLine(" Writable : " + prop.Set.ToString())  
        Console.WriteLine()  
      Next  
  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="6aa57-179">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6aa57-179">External Resources</span></span>  
 <span data-ttu-id="6aa57-180">Blogbeitrag, [EzAPI – Updated for SQL Server 2012 (EzAPI: für SQL Server 2012 aktualisiert)](https://go.microsoft.com/fwlink/?LinkId=243223), auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="6aa57-180">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="6aa57-181">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="6aa57-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6aa57-182">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="6aa57-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6aa57-183">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="6aa57-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6aa57-184">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6aa57-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa57-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6aa57-185">See Also</span></span>  
 [<span data-ttu-id="6aa57-186">Programmgesteuertes Verbinden von Tasks</span><span class="sxs-lookup"><span data-stu-id="6aa57-186">Connecting Tasks Programmatically</span></span>](../building-packages-programmatically/connecting-tasks-programmatically.md)  
  
  
