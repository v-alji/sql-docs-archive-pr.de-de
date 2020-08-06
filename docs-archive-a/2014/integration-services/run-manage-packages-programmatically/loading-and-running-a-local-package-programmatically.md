---
title: Programmgesteuertes Laden und Ausführen eines lokalen Pakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Integration Services packages, running
- events [Integration Services], capturing
- packages [Integration Services], running
- loading packages programmatically
- Visual Basic [Integration Services]
- running packages [Integration Services]
- programmatically load and run packages [SSIS]
ms.assetid: 2f9fc1a8-a001-4c54-8c64-63b443725422
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a29faf623c02fea4fd8722c235f595f0fe4492e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696914"
---
# <a name="loading-and-running-a-local-package-programmatically"></a><span data-ttu-id="1e929-102">Programmgesteuertes Laden und Ausführen eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="1e929-102">Loading and Running a Local Package Programmatically</span></span>
  <span data-ttu-id="1e929-103">Sie können [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete mit einer der unter [Ausführen von Paketen](../packages/run-integration-services-ssis-packages.md) beschriebenen Methoden bei Bedarf oder zu vorbestimmten Zeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e929-103">You can run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages as needed or at predetermined times by using the methods described in [Running Packages](../packages/run-integration-services-ssis-packages.md).</span></span> <span data-ttu-id="1e929-104">Mit nur wenigen Codezeilen können Sie ein Paket jedoch auch mit einer benutzerdefinierten Anwendung wie einer Windows Forms-Anwendung, einer Konsolenanwendung, einem Webformular oder Webdienst von ASP.NET oder einem Windows-Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e929-104">However, with only a few lines of code, you can also run a package from a custom application such as a Windows Forms application, a console application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
 <span data-ttu-id="1e929-105">In diesem Thema wird Folgendes erläutert:</span><span class="sxs-lookup"><span data-stu-id="1e929-105">This topic discusses:</span></span>  
  
-   <span data-ttu-id="1e929-106">Programmgesteuertes Laden eines Pakets</span><span class="sxs-lookup"><span data-stu-id="1e929-106">Loading a package programmatically</span></span>  
  
-   <span data-ttu-id="1e929-107">Programmgesteuertes Ausführen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="1e929-107">Running a package programmatically</span></span>  
  
 <span data-ttu-id="1e929-108">Alle in diesem Thema erläuterten Methoden zum Laden und Ausführen von Paketen erfordern einen Verweis auf die `Microsoft.SqlServer.ManagedDTS`-Assembly.</span><span class="sxs-lookup"><span data-stu-id="1e929-108">All of the methods used in this topic to load and run packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="1e929-109">Nachdem Sie den Verweis in einem neuen Projekt hinzugefügt haben, importieren Sie den <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace mit einer `using`-Anweisung oder einer `Imports`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e929-109">After adding the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="loading-a-package-programmatically"></a><span data-ttu-id="1e929-110">Programmgesteuertes Laden eines Pakets</span><span class="sxs-lookup"><span data-stu-id="1e929-110">Loading a Package Programmatically</span></span>  
 <span data-ttu-id="1e929-111">Rufen Sie unabhängig davon, ob ein Paket lokal oder remote gespeichert ist, zum programmgesteuerten Laden des Pakets auf dem lokalen Computer eine der folgenden Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="1e929-111">To load a package programmatically on the local computer, whether the package is stored locally or remotely, call one of the following methods:</span></span>  
  
|<span data-ttu-id="1e929-112">Speicherort</span><span class="sxs-lookup"><span data-stu-id="1e929-112">Storage Location</span></span>|<span data-ttu-id="1e929-113">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="1e929-113">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1e929-114">Datei</span><span class="sxs-lookup"><span data-stu-id="1e929-114">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>|  
|<span data-ttu-id="1e929-115">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="1e929-115">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e929-116">Die Methoden der <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse zum Arbeiten mit dem SSIS-Paketspeicher unterstützen nur ".", localhost oder den Namen des lokalen Servers.</span><span class="sxs-lookup"><span data-stu-id="1e929-116">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="1e929-117">Sie können "(local)" nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e929-117">You cannot use "(local)".</span></span>  
  
## <a name="running-a-package-programmatically"></a><span data-ttu-id="1e929-118">Programmgesteuertes Ausführen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="1e929-118">Running a Package Programmatically</span></span>  
 <span data-ttu-id="1e929-119">Das Entwickeln einer benutzerdefinierten Anwendung in verwaltetem Code zum Ausführen eines Pakets auf dem lokalen Computer erfordert den folgenden Ansatz.</span><span class="sxs-lookup"><span data-stu-id="1e929-119">Developing a custom application in managed code that runs a package on the local computer requires the following approach.</span></span> <span data-ttu-id="1e929-120">Die hier zusammengefassten Schritte werden in dem folgenden Beispiel einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1e929-120">The steps summarized here are demonstrated in the sample console application that follows.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically"></a><span data-ttu-id="1e929-121">So führen Sie ein Paket auf dem lokalen Computer programmgesteuert aus</span><span class="sxs-lookup"><span data-stu-id="1e929-121">To run a package on the local computer programmatically</span></span>  
  
1.  <span data-ttu-id="1e929-122">Starten Sie die Visual Studio-Entwicklungsumgebung, und erstellen Sie eine neue Anwendung in der gewünschten Entwicklungssprache.</span><span class="sxs-lookup"><span data-stu-id="1e929-122">Start the Visual Studio development environment, and create a new application in your preferred development language.</span></span> <span data-ttu-id="1e929-123">In diesem Beispiel wird eine Konsolenanwendung verwendet. Sie können ein Paket jedoch auch mit einer Windows Forms-Anwendung, einem Webformular oder Webdienst von ASP.NET oder einem Windows-Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e929-123">This example uses a console application; however you can also run a package from a Windows Forms application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
2.  <span data-ttu-id="1e929-124">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**, und fügen Sie einen Verweis auf **Microsoft.SqlServer.ManagedDTS.dll** hinzu.</span><span class="sxs-lookup"><span data-stu-id="1e929-124">On the **Project** menu, click **Add Reference** and add a reference to **Microsoft.SqlServer.ManagedDTS.dll**.</span></span> <span data-ttu-id="1e929-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e929-125">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="1e929-126">Verwenden Sie die Visual Basic- `Imports` Anweisung oder die c#- `using` Anweisung, um den **Microsoft. SqlServer. DTS. Runtime** -Namespace zu importieren.</span><span class="sxs-lookup"><span data-stu-id="1e929-126">Use the Visual Basic `Imports` statement or the C# `using` statement to import the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
4.  <span data-ttu-id="1e929-127">Fügen Sie den folgenden Code in der Hauptroutine hinzu.</span><span class="sxs-lookup"><span data-stu-id="1e929-127">Add the following code in the main routine.</span></span> <span data-ttu-id="1e929-128">Die abgeschlossene Konsolenanwendung sollte wie im folgenden Beispiel dargestellt aussehen.</span><span class="sxs-lookup"><span data-stu-id="1e929-128">The completed console application should look like the following example.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e929-129">Im Beispielcode wird das Laden des Pakets aus dem Dateisystem mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1e929-129">The sample code demonstrates loading the package from the file system by using the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A> method.</span></span> <span data-ttu-id="1e929-130">Sie können das Paket jedoch auch aus der MSDB-Datenbank durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>-Methode oder aus dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketspeicher durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>-Methode laden.</span><span class="sxs-lookup"><span data-stu-id="1e929-130">However you can also load the package from the MSDB database by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> method, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> method.</span></span>  
  
5.  <span data-ttu-id="1e929-131">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="1e929-131">Run the project.</span></span> <span data-ttu-id="1e929-132">Der Beispielcode führt das CalculatedColumns-Beispielpaket aus, das mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Beispielen installiert wird.</span><span class="sxs-lookup"><span data-stu-id="1e929-132">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="1e929-133">Das Ergebnis der Paketausführung wird im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e929-133">The result of package execution is displayed in the console window.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="1e929-134">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="1e929-134">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, Nothing)  
    pkgResults = pkg.Execute()  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, null);  
      pkgResults = pkg.Execute();  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
## <a name="capturing-events-from-a-running-package"></a><span data-ttu-id="1e929-135">Aufzeichnen von Ereignissen aus einem ausgeführten Paket</span><span class="sxs-lookup"><span data-stu-id="1e929-135">Capturing Events from a Running Package</span></span>  
 <span data-ttu-id="1e929-136">Wenn ein Paket wie im vorigen Beispiel dargestellt programmgesteuert ausgeführt wird, sollten auch Fehler und andere Ereignisse aufgezeichnet werden, die bei der Ausführung des Pakets auftreten.</span><span class="sxs-lookup"><span data-stu-id="1e929-136">When you run a package programmatically as shown in the preceding sample, you may also want to capture errors and other events that occur as the package executes.</span></span> <span data-ttu-id="1e929-137">Sie können dies erreichen, indem Sie eine Klasse hinzufügen, die von der <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>-Klasse erbt, und beim Laden des Pakets einen Verweis auf diese Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="1e929-137">You can accomplish this by adding a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class, and by passing a reference to that class when you load the package.</span></span> <span data-ttu-id="1e929-138">Auch wenn im folgenden Beispiel nur die <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A>-Ereignisse aufgezeichnet werden, gibt es noch viele weitere Ereignisse, die mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>-Klasse aufgezeichnet werden können.</span><span class="sxs-lookup"><span data-stu-id="1e929-138">Although the following example captures only the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A> event, there are many other events that the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class lets you capture.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically-and-capture-package-events"></a><span data-ttu-id="1e929-139">So führen Sie ein Paket auf dem lokalen Computer programmgesteuert aus und zeichnen Paketereignisse auf</span><span class="sxs-lookup"><span data-stu-id="1e929-139">To run a package on the local computer programmatically and capture package events</span></span>  
  
1.  <span data-ttu-id="1e929-140">Führen Sie die Schritte im vorangehenden Beispiel aus, um ein Projekt für dieses Beispiel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e929-140">Follow the steps in the preceding example to create a project for this example.</span></span>  
  
2.  <span data-ttu-id="1e929-141">Fügen Sie den folgenden Code in der Hauptroutine hinzu.</span><span class="sxs-lookup"><span data-stu-id="1e929-141">Add the following code in the main routine.</span></span> <span data-ttu-id="1e929-142">Die abgeschlossene Konsolenanwendung sollte wie im folgenden Beispiel dargestellt aussehen.</span><span class="sxs-lookup"><span data-stu-id="1e929-142">The completed console application should look like the following example.</span></span>  
  
3.  <span data-ttu-id="1e929-143">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="1e929-143">Run the project.</span></span> <span data-ttu-id="1e929-144">Der Beispielcode führt das CalculatedColumns-Beispielpaket aus, das mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Beispielen installiert wird.</span><span class="sxs-lookup"><span data-stu-id="1e929-144">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="1e929-145">Das Ergebnis der Paketausführung wird zusammen mit den aufgetretenen Fehlern im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e929-145">The result of package execution is displayed in the console window, along with any errors that occur.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="1e929-146">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="1e929-146">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    Dim eventListener As New EventListener()  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, eventListener)  
    pkgResults = pkg.Execute(Nothing, Nothing, eventListener, Nothing, Nothing)  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
  
Class EventListener  
  Inherits DefaultEvents  
  
  Public Overrides Function OnError(ByVal source As Microsoft.SqlServer.Dts.Runtime.DtsObject, _  
    ByVal errorCode As Integer, ByVal subComponent As String, ByVal description As String, _  
    ByVal helpFile As String, ByVal helpContext As Integer, _  
    ByVal idofInterfaceWithError As String) As Boolean  
  
    ' Add application-specific diagnostics here.  
    Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description)  
    Return False  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppWithEventsCS  
{  
  class MyEventListener : DefaultEvents  
  {  
    public override bool OnError(DtsObject source, int errorCode, string subComponent,   
      string description, string helpFile, int helpContext, string idofInterfaceWithError)  
    {  
      // Add application-specific diagnostics here.  
      Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description);  
      return false;  
    }  
  }  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      MyEventListener eventListener = new MyEventListener();  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, eventListener);  
      pkgResults = pkg.Execute(null, null, eventListener, null, null);  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
<span data-ttu-id="1e929-147">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="1e929-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1e929-148">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="1e929-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1e929-149">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="1e929-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1e929-150">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e929-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e929-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e929-151">See Also</span></span>  
 <span data-ttu-id="1e929-152">[Informationen zu den Unterschieden zwischen der lokalen und der Remote Ausführung](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="1e929-152">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="1e929-153">[Programm gesteuertes laden und Ausführen eines Remote Pakets](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="1e929-153">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="1e929-154">Laden der Ausgabe eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="1e929-154">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
