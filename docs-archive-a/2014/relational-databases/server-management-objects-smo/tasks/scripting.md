---
title: Erstellen von Skripts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: bf46798597de021976cefa943a17500e773f9274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700928"
---
# <a name="scripting"></a><span data-ttu-id="8c33d-102">Skripterstellung</span><span class="sxs-lookup"><span data-stu-id="8c33d-102">Scripting</span></span>
  <span data-ttu-id="8c33d-103">Die Skripterstellung in SMO wird durch das <xref:Microsoft.SqlServer.Management.Smo.Scripter>-Objekt und dessen untergeordnete Objekte oder durch die `Script`-Methode für einzelne Objekte gesteuert.</span><span class="sxs-lookup"><span data-stu-id="8c33d-103">Scripting in SMO is controlled by the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects, or the `Script` method on individual objects.</span></span> <span data-ttu-id="8c33d-104">Das- <xref:Microsoft.SqlServer.Management.Smo.Scripter> Objekt steuert die Zuordnung von Abhängigkeitsbeziehungen für-Objekte in einer Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c33d-104">The <xref:Microsoft.SqlServer.Management.Smo.Scripter> object controls the mapping out of dependency relationships for objects on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8c33d-105">Die erweiterte Skripterstellung mithilfe des <xref:Microsoft.SqlServer.Management.Smo.Scripter>-Objekts und dessen untergeordneten Objekten ist ein Prozess, der aus drei Phasen besteht:</span><span class="sxs-lookup"><span data-stu-id="8c33d-105">Advanced scripting by using the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects is a three phase process:</span></span>  
  
1.  <span data-ttu-id="8c33d-106">Ermittlung</span><span class="sxs-lookup"><span data-stu-id="8c33d-106">Discovery</span></span>  
  
2.  <span data-ttu-id="8c33d-107">Listengenerierung</span><span class="sxs-lookup"><span data-stu-id="8c33d-107">List generation</span></span>  
  
3.  <span data-ttu-id="8c33d-108">Skriptgenerierung</span><span class="sxs-lookup"><span data-stu-id="8c33d-108">Script generation</span></span>  
  
 <span data-ttu-id="8c33d-109">Die Ermittlungsphase verwendet das <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8c33d-109">The discovery phase uses the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object.</span></span> <span data-ttu-id="8c33d-110">Bei einer URN-Liste mit Objekten gibt die <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A>-Methode des <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>-Objekts ein <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>-Objekt für die Objekte in der URN-Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="8c33d-110">Given an URN list of objects, the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object returns a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object for the objects in the URN list.</span></span> <span data-ttu-id="8c33d-111">Der boolesche *fParents* -Parameter wird verwendet, um auszuwählen, ob die übergeordneten Elemente oder die untergeordneten Elemente des angegebenen Objekts erkannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c33d-111">The Boolean *fParents* parameter is used to select whether the parents or the children of the specified object are to be discovered.</span></span> <span data-ttu-id="8c33d-112">Die Abhängigkeitsstruktur kann in dieser Phase geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8c33d-112">The dependency tree can be modified at this stage.</span></span>  
  
 <span data-ttu-id="8c33d-113">In der Listengenerierungsphase wird die Struktur übergeben und die resultierende Liste wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c33d-113">In the list generation phase, the tree is passed in and the resulting list is returned.</span></span> <span data-ttu-id="8c33d-114">Diese Objektliste ist in Skriptreihenfolge und kann bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8c33d-114">This object list is in scripting order and can be manipulated.</span></span>  
  
 <span data-ttu-id="8c33d-115">Die Listengenerierungsphase verwendet die <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A>-Methode, um <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8c33d-115">The list generation phases use the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> method to return a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span></span> <span data-ttu-id="8c33d-116"><xref:Microsoft.SqlServer.Management.Smo.DependencyTree> kann in dieser Phase geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8c33d-116">The <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> can be modified at this stage.</span></span>  
  
 <span data-ttu-id="8c33d-117">In der dritten und abschließenden Phase wird ein Skript mit der angegebenen Liste und den Skriptoptionen generiert.</span><span class="sxs-lookup"><span data-stu-id="8c33d-117">In the third and final phase, a script is generated with the specified list and scripting options.</span></span> <span data-ttu-id="8c33d-118">Das Ergebnis wird als <xref:System.Collections.Specialized.StringCollection>-Systemobjekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c33d-118">The result is returned as a <xref:System.Collections.Specialized.StringCollection> system object.</span></span> <span data-ttu-id="8c33d-119">In dieser Phase werden dann die abhängigen Objektnamen aus der Elementauflistung des <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>-Objekts und von Eigenschaften, wie <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> und <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>, extrahiert.</span><span class="sxs-lookup"><span data-stu-id="8c33d-119">In this phase the dependent object names are then extracted from the Items collection of the <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object and properties such as <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> and <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c33d-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c33d-120">Example</span></span>  
 <span data-ttu-id="8c33d-121">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c33d-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="8c33d-122">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="8c33d-122">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="8c33d-123">Dieses Codebeispiel erfordert eine `Imports`-Anweisung für den System.Collections.Specialized-Namespace.</span><span class="sxs-lookup"><span data-stu-id="8c33d-123">This code example requires an `Imports` statement for the System.Collections.Specialized namespace.</span></span> <span data-ttu-id="8c33d-124">Fügen Sie dies mit den anderen Imports-Anweisungen ein, vor jeglichen Deklarationen in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8c33d-124">Insert this with the other Imports statements, before any declarations in the application.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a><span data-ttu-id="8c33d-125">Ausgeben von Abhängigkeiten für eine Datenbank in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c33d-125">Scripting Out the Dependencies for a Database in Visual Basic</span></span>  
 <span data-ttu-id="8c33d-126">In diesem Codebeispiel wird gezeigt, wie die Abhängigkeiten ermittelt werden und wie die Liste durchlaufen wird, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c33d-126">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a><span data-ttu-id="8c33d-127">Ausgeben von Abhängigkeiten für eine Datenbank in Visual C#</span><span class="sxs-lookup"><span data-stu-id="8c33d-127">Scripting Out the Dependencies for a Database in Visual C#</span></span>  
 <span data-ttu-id="8c33d-128">In diesem Codebeispiel wird gezeigt, wie die Abhängigkeiten ermittelt werden und wie die Liste durchlaufen wird, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c33d-128">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a><span data-ttu-id="8c33d-129">Ausgeben von Abhängigkeiten für eine Datenbank in PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c33d-129">Scripting Out the Dependencies for a Database in PowerShell</span></span>  
 <span data-ttu-id="8c33d-130">In diesem Codebeispiel wird gezeigt, wie die Abhängigkeiten ermittelt werden und wie die Liste durchlaufen wird, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c33d-130">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
