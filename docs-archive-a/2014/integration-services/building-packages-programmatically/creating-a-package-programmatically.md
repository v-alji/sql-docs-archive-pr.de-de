---
title: Programmgesteuertes Erstellen von Paketen | Microsoft-Dokumentation
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
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1159784fc95dd86d9d33c4354291cc7c52812982
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700149"
---
# <a name="creating-a-package-programmatically"></a><span data-ttu-id="09cff-102">Programmgesteuertes Erstellen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="09cff-102">Creating a Package Programmatically</span></span>
  <span data-ttu-id="09cff-103">Das <xref:Microsoft.SqlServer.Dts.Runtime.Package>-Objekt ist der Container oberster Ebene für alle anderen Objekte in einer [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="09cff-103">The <xref:Microsoft.SqlServer.Dts.Runtime.Package> object is the top-level container for all other objects in an [!INCLUDE[ssIS](../../includes/ssis-md.md)] project solution.</span></span> <span data-ttu-id="09cff-104">Als Container der obersten Ebene ist das Paket das erste Objekt, das erstellt wird. Nachfolgende Objekte werden diesem hinzugefügt und dann in dem Kontext des Pakets ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="09cff-104">As the top-level container, the package is the first object created, and subsequent objects are added to it, and then executed within the context of the package.</span></span> <span data-ttu-id="09cff-105">Das Paket selbst verschiebt oder transformiert keine Daten.</span><span class="sxs-lookup"><span data-stu-id="09cff-105">The package itself does not move or transform data.</span></span> <span data-ttu-id="09cff-106">Das Paket ist zur Ausführung der Arbeit auf die Tasks angewiesen, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="09cff-106">The package relies on the tasks it contains to perform the work.</span></span> <span data-ttu-id="09cff-107">Tasks führen den Großteil der von einem Paket ausgeführten Arbeit aus und definieren die Funktionalität eines Pakets.</span><span class="sxs-lookup"><span data-stu-id="09cff-107">Tasks perform most of the work performed by a package, and define the functionality of a package.</span></span> <span data-ttu-id="09cff-108">Ein Paket wird mit nur drei Codezeilen erstellt und ausgeführt. Um dem Paket zusätzliche Funktionalität zu verleihen, können jedoch verschiedene Tasks und <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekte hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="09cff-108">A package is created and executed with just three lines of code, but various tasks and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects are added to give additional functionality to your package.</span></span> <span data-ttu-id="09cff-109">In diesem Abschnitt wird erläutert, wie ein Paket programmgesteuert erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="09cff-109">This section discusses how to programmatically create a package.</span></span> <span data-ttu-id="09cff-110">Er enthält keine Informationen zum Erstellen der Tasks oder des <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="09cff-110">It does not provide information about how to create the tasks or the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span> <span data-ttu-id="09cff-111">Diese Themen werden in späteren Abschnitten behandelt.</span><span class="sxs-lookup"><span data-stu-id="09cff-111">These are covered in later sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09cff-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09cff-112">Example</span></span>  
 <span data-ttu-id="09cff-113">Zum Schreiben von Code mithilfe der Visual Studio-IDE ist ein Verweis auf Microsoft.SqlServer.ManagedDTS.DLL erforderlich, um eine `using`-Anweisung (`Imports` in Visual Basic .NET) für Microsoft.SqlServer.Dts.Runtime zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="09cff-113">To write code using the Visual Studio IDE, a reference to Microsoft.SqlServer.ManagedDTS.DLL is required in order to create a `using` statement (`Imports` in Visual Basic .NET) to the Microsoft.SqlServer.Dts.Runtime.</span></span> <span data-ttu-id="09cff-114">Im folgenden Codebeispiel wird das Erstellen eines leeren Pakets veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="09cff-114">The following code sample demonstrates creating an empty package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="09cff-115">Drücken Sie F5 in Visual Studio, um das Beispiel zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="09cff-115">To compile and run the sample, press F5 in Visual Studio.</span></span> <span data-ttu-id="09cff-116">Verwenden Sie zum Erstellen des Codes mithilfe des C#-Compilers, **csc.exe** , an der Eingabeaufforderung für die Kompilierung den folgenden Befehl sowie die folgenden Dateiverweise, und ersetzen Sie *\<filename>* durch den Namen der CS- oder VB-Datei. Legen Sie einen *\<outputfilename>* Ihrer Wahl fest.</span><span class="sxs-lookup"><span data-stu-id="09cff-116">To build the code using the C# compiler, **csc.exe**, at the command prompt to compile, use the following command and file references, replacing the *\<filename>* with the name of the .cs or .vb file, and giving it an *\<outputfilename>* of your choice.</span></span>  
  
 <span data-ttu-id="09cff-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="09cff-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="09cff-118">Verwenden Sie zum Erstellen des Codes mithilfe des Visual Basic .NET-Compilers, **vbc.exe**, an der Eingabeaufforderung für die Kompilierung den folgenden Befehl sowie die folgenden Dateiverweise.</span><span class="sxs-lookup"><span data-stu-id="09cff-118">To build the code using the Visual Basic .NET compiler, **vbc.exe**, at the command prompt to compile, use the following command and file references.</span></span>  
  
 <span data-ttu-id="09cff-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="09cff-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="09cff-120">Sie können auch ein Paket erstellen, indem Sie ein vorhandenes Paket, das auf der Festplatte gespeichert wurde, in das Dateisystem oder in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] laden.</span><span class="sxs-lookup"><span data-stu-id="09cff-120">You can also create a package by loading an existing package that was saved on disk, in the file system, or to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="09cff-121">Der Unterschied besteht darin, dass das <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Objekt zuerst erstellt wird und dann das Paketobjekt mit einer der überlasteten Methoden der Anwendung gefüllt wird: `LoadPackage` bei Flatfiles, `LoadFromSQLServer` bei Paketen, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeichert sind, oder <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> bei Paketen, die im Dateisystem gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="09cff-121">The difference is that the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object is first created, and then the package object is filled by one of the Application's overloaded methods: `LoadPackage` for flat files, `LoadFromSQLServer` for packages saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> for packages saved to the file system.</span></span> <span data-ttu-id="09cff-122">Im folgenden Beispiel wird ein vorhandenes Paket von der Festplatte geladen. Anschließend werden die verschiedenen Eigenschaften des Pakets betrachtet.</span><span class="sxs-lookup"><span data-stu-id="09cff-122">The following example loads an existing package from disk, and then views several properties on the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="09cff-123">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="09cff-123">**Sample Output:**</span></span>  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a><span data-ttu-id="09cff-124">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="09cff-124">External Resources</span></span>  
  
-   <span data-ttu-id="09cff-125">Blogeintrag, [API Sample – OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), (API-Beispiel – OleDB-Quelle und OleDB-Ziel) auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="09cff-125">Blog entry, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="09cff-126">Blogbeitrag, [EzAPI – Updated for SQL Server 2012 (EzAPI: für SQL Server 2012 aktualisiert)](https://go.microsoft.com/fwlink/?LinkId=243223), auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="09cff-126">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="09cff-127">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="09cff-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="09cff-128">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="09cff-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="09cff-129">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="09cff-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="09cff-130">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="09cff-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cff-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09cff-131">See Also</span></span>  
 [<span data-ttu-id="09cff-132">Programmgesteuertes Hinzufügen von Tasks</span><span class="sxs-lookup"><span data-stu-id="09cff-132">Adding Tasks Programmatically</span></span>](../building-packages-programmatically/adding-tasks-programmatically.md)  
  
  
