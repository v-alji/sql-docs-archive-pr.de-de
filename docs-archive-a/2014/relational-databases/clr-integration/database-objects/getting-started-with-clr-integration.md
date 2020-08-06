---
title: Einstieg in die CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 43c97e411a4d74aa48b88f2edbbe420ae17f3534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607830"
---
# <a name="getting-started-with-clr-integration"></a><span data-ttu-id="5eef4-102">Erste Schritte mit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="5eef4-102">Getting Started with CLR Integration</span></span>
  <span data-ttu-id="5eef4-103">Dieses Thema bietet einen Überblick über die Namespaces und Bibliotheken, die zum Kompilieren von Datenbankobjekten mithilfe der- [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] Integration in die .NET Framework Common Language Runtime (CLR) erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5eef4-103">This topic provides an overview of the namespaces and libraries required to compile database objects using the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="5eef4-104">In diesem Thema wird außerdem erläutert, wie eine einfache gespeicherte CLR-Prozedur in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# geschrieben, kompiliert und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5eef4-104">The topic also shows you how to write, compile, and run a simple CLR stored procedure written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
## <a name="required-namespaces"></a><span data-ttu-id="5eef4-105">Erforderliche Namespaces</span><span class="sxs-lookup"><span data-stu-id="5eef4-105">Required Namespaces</span></span>  
 <span data-ttu-id="5eef4-106">Ab [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5eef4-106">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5eef4-107">Die CLR-Integrationsfunktionalität wird in einer Assembly mit dem Namen system.data.dll verfügbar gemacht, die Teil von .NET Framework ist.</span><span class="sxs-lookup"><span data-stu-id="5eef4-107">CLR integration functionality is exposed in an assembly called system.data.dll, which is part of the .NET Framework.</span></span> <span data-ttu-id="5eef4-108">Diese Assembly befindet sich im globalen Assemblycache (GAC) sowie im .NET Framework-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5eef4-108">This assembly can be found in the Global Assembly Cache (GAC) as well as in the .NET Framework directory.</span></span> <span data-ttu-id="5eef4-109">Ein Verweis auf diese Assembly wird in der Regel sowohl von Befehlszeilentools als auch von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio automatisch hinzugefügt und muss daher nicht manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5eef4-109">A reference to this assembly is typically added automatically by both command line tools and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, so there is no need to add it manually.</span></span>  
  
 <span data-ttu-id="5eef4-110">Die system.data.dll-Assembly enthält die folgenden Namespaces, die zum Kompilieren von CLR-Datenbankobjekten erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="5eef4-110">The system.data.dll assembly contains the following namespaces, which are required for compiling CLR database objects:</span></span>  
  
 `System.Data`  
  
 `System.Data.Sql`  
  
 `Microsoft.SqlServer.Server`  
  
 `System.Data.SqlTypes`  
  
## <a name="writing-a-simple-hello-world-stored-procedure"></a><span data-ttu-id="5eef4-111">Schreiben der einfachen gespeicherten Prozedur "Hello World"</span><span class="sxs-lookup"><span data-stu-id="5eef4-111">Writing A Simple "Hello World" Stored Procedure</span></span>  
 <span data-ttu-id="5eef4-112">Kopieren Sie den folgenden Visual C#- oder [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic-Code, fügen Sie ihn in einen Texteditor ein, und speichern Sie ihn in einer Datei mit dem Namen "helloworld.cs" oder "helloworld.vb".</span><span class="sxs-lookup"><span data-stu-id="5eef4-112">Copy and paste the following Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic code into a text editor, and save it in a file named "helloworld.cs" or "helloworld.vb".</span></span>  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    <Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="5eef4-113">Dieses einfache Programm enthält eine einzelne statische Methode in einer öffentlichen Klasse.</span><span class="sxs-lookup"><span data-stu-id="5eef4-113">This simple program contains a single static method on a public class.</span></span> <span data-ttu-id="5eef4-114">Diese Methode enthält die beiden neuen Klassen `SqlContext` und `SqlPipe` zum Erstellen von verwalteten Datenbankobjekten für die Ausgabe einer einfachen Textnachricht.</span><span class="sxs-lookup"><span data-stu-id="5eef4-114">This method uses two new classes, `SqlContext` and `SqlPipe`, for creating managed database objects to output a simple text message.</span></span> <span data-ttu-id="5eef4-115">Die-Methode weist auch die Zeichenfolge "Hello World!" zu.</span><span class="sxs-lookup"><span data-stu-id="5eef4-115">The method also assigns the string "Hello world!"</span></span> <span data-ttu-id="5eef4-116">als Wert eines out-Parameters.</span><span class="sxs-lookup"><span data-stu-id="5eef4-116">as the value of an out parameter.</span></span> <span data-ttu-id="5eef4-117">Diese Methode kann in einer gespeicherten Prozedur als gespeicherte Prozedur deklariert werden [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5eef4-117">This method can be declared as a stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span></span>  
  
 <span data-ttu-id="5eef4-118">Dieses Programm wird im Folgenden als Bibliothek kompiliert, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] geladen und als gespeicherte Prozedur ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5eef4-118">We will now compile this program as a library, load it into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and run it as a stored procedure.</span></span>  
  
## <a name="compiling-the-hello-world-stored-procedure"></a><span data-ttu-id="5eef4-119">Kompilieren der gespeicherten Prozedur "Hello World"</span><span class="sxs-lookup"><span data-stu-id="5eef4-119">Compiling the "Hello World" Stored Procedure</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)]<span data-ttu-id="5eef4-120">Standardmäßig .NET Framework Weitergabedateien.</span><span class="sxs-lookup"><span data-stu-id="5eef4-120">.NET Framework redistribution files by default.</span></span> <span data-ttu-id="5eef4-121">Zu diesen Dateien zählen die Dateien csc.exe und vbc.exe, die Befehlszeilencompiler für Visual C# sowie Visual Basic-Programme.</span><span class="sxs-lookup"><span data-stu-id="5eef4-121">These files include csc.exe and vbc.exe, the command-line compilers for Visual C# and Visual Basic programs.</span></span> <span data-ttu-id="5eef4-122">Zum Kompilieren des Beispiels müssen Sie die Pfadvariable so ändern, dass sie auf das Verzeichnis mit der Datei csc.exe oder mit der Datei vbc.exe zeigt.</span><span class="sxs-lookup"><span data-stu-id="5eef4-122">In order to compile our sample, you must modify your path variable to point to the directory containing csc.exe or vbc.exe.</span></span> <span data-ttu-id="5eef4-123">Der Standardinstallationspfad von .NET Framework lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5eef4-123">The following is the default installation path of the .NET Framework.</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\(version)  
```  
  
 <span data-ttu-id="5eef4-124">Diese Version enthält die Versionsnummer der installierten Redistributionsdatei von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5eef4-124">Version contains the version number of the installed .NET Framework redistributable.</span></span> <span data-ttu-id="5eef4-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5eef4-125">For example:</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\v2.0.31113  
```  
  
 <span data-ttu-id="5eef4-126">Nach dem Hinzufügen des .NET Framework-Verzeichnises zum Pfad können Sie die gespeicherte Prozedur in diesem Beispiel mit dem folgenden Befehl in eine Assembly kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5eef4-126">Once you have added the .NET Framework directory to your path, you can compile the sample stored procedure into an assembly with the following command.</span></span> <span data-ttu-id="5eef4-127">Mit der `/target`-Option können Sie sie in eine Assembly kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5eef4-127">The `/target` option allows you to compile it into an assembly.</span></span>  
  
 <span data-ttu-id="5eef4-128">Für Visual C#-Quelldateien gilt:</span><span class="sxs-lookup"><span data-stu-id="5eef4-128">For Visual C# source files:</span></span>  
  
```  
csc /target:library helloworld.cs   
```  
  
 <span data-ttu-id="5eef4-129">Für Visual Basic-Quelldateien gilt:</span><span class="sxs-lookup"><span data-stu-id="5eef4-129">For Visual Basic source files:</span></span>  
  
```  
vbc /target:library helloworld.vb  
```  
  
 <span data-ttu-id="5eef4-130">Mit diesen Befehlen wird der Visual C# - bzw. Visual Basic-Compiler unter Angabe der /target-Option aufgerufen, die festlegt, dass eine Bibliotheks-DLL erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5eef4-130">These commands launch the Visual C# or Visual Basic compiler using the /target option to specify building a library DLL.</span></span>  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a><span data-ttu-id="5eef4-131">Laden und Ausführen der gespeicherten Prozedur "Hello World" in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eef4-131">Loading and Running the "Hello World" Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="5eef4-132">Nachdem die Beispiel Prozedur erfolgreich kompiliert wurde, können Sie Sie in testen [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] und eine neue Abfrage erstellen, die eine Verbindung mit einer geeigneten Testdatenbank herstellt (z. b. die AdventureWorks-Beispieldatenbank).</span><span class="sxs-lookup"><span data-stu-id="5eef4-132">Once the sample procedure has successfully compiled, you can test it in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] and create a new query, connecting to a suitable test database (for example, the AdventureWorks sample database).</span></span>  
  
 <span data-ttu-id="5eef4-133">Die Funktion zum Ausführen von CLR-Code (Common Language Runtime) ist in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5eef4-133">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5eef4-134">Der CLR-Code kann mithilfe der gespeicherten System Prozedur **sp_configure** aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5eef4-134">The CLR code can be enabled by using the **sp_configure** system stored procedure.</span></span> <span data-ttu-id="5eef4-135">Weitere Informationen finden Sie unter [Enabling CLR Integration](../clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="5eef4-135">For more information, see [Enabling CLR Integration](../clr-integration-enabling.md).</span></span>  
  
 <span data-ttu-id="5eef4-136">Sie müssen die Assembly erstellen, um auf die gespeicherte Prozedur zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="5eef4-136">We will need to create the assembly so we can access the stored procedure.</span></span> <span data-ttu-id="5eef4-137">Für dieses Beispiel wird vorausgesetzt, dass Sie die helloworld.dll-Assembly im Verzeichnis C:\ erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5eef4-137">For this example, we will assume that you have created the helloworld.dll assembly in the C:\ directory.</span></span> <span data-ttu-id="5eef4-138">Fügen Sie die folgende [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung zur Abfrage hinzu:</span><span class="sxs-lookup"><span data-stu-id="5eef4-138">Add the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to your query.</span></span>  
  
```  
CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE  
```  
  
 <span data-ttu-id="5eef4-139">Nach dem Erstellen der Assembly können Sie mithilfe der CREATE PROCEDURE-Anweisung auf die HelloWorld-Methode zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5eef4-139">Once the assembly has been created, we can now access our HelloWorld method by using the create procedure statement.</span></span> <span data-ttu-id="5eef4-140">Die gespeicherte Prozedur wird "hello" genannt:</span><span class="sxs-lookup"><span data-stu-id="5eef4-140">We will call our stored procedure "hello":</span></span>  
  
```  
  
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
 <span data-ttu-id="5eef4-141">Nach dem Erstellen der Prozedur kann diese wie eine normale, in [!INCLUDE[tsql](../../../includes/tsql-md.md)] geschriebene gespeicherte Prozedur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5eef4-141">Once the procedure has been created, it can be run just like a normal stored procedure written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5eef4-142">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="5eef4-142">Execute the following command:</span></span>  
  
```  
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
 <span data-ttu-id="5eef4-143">Daraufhin sollte im Meldungsfenster von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] folgende Ausgabe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5eef4-143">This should result in the following output in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] messages window.</span></span>  
  
```  
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a><span data-ttu-id="5eef4-144">Entfernen des Beispiels der gespeicherten Prozedur "Hello World"</span><span class="sxs-lookup"><span data-stu-id="5eef4-144">Removing the "Hello World" Stored Procedure Sample</span></span>  
 <span data-ttu-id="5eef4-145">Wenn Sie die gespeicherte Beispielprozedur ausgeführt haben, können Sie die Prozedur und die Assembly aus der Testdatenbank entfernen.</span><span class="sxs-lookup"><span data-stu-id="5eef4-145">When you are finished running the sample stored procedure, you can remove the procedure and the assembly from your test database.</span></span>  
  
 <span data-ttu-id="5eef4-146">Entfernen Sie zuerst die Prozedur. Verwenden Sie hierzu den drop procedure-Befehl.</span><span class="sxs-lookup"><span data-stu-id="5eef4-146">First, remove the procedure using the drop procedure command.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
 <span data-ttu-id="5eef4-147">Nach dem Löschen der Prozedur können Sie die Assembly entfernen, die den Beispielcode enthält.</span><span class="sxs-lookup"><span data-stu-id="5eef4-147">Once the procedure has been dropped, you can remove the assembly containing your sample code.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eef4-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5eef4-148">See Also</span></span>  
 <span data-ttu-id="5eef4-149">[Gespeicherte CLR-Prozeduren](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="5eef4-149">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 <span data-ttu-id="5eef4-150">[SQL Server Prozess interne spezifische Erweiterungen für ADO.net](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span><span class="sxs-lookup"><span data-stu-id="5eef4-150">[SQL Server In-Process Specific Extensions to ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span></span>  
 <span data-ttu-id="5eef4-151">[Debugging von CLR-Datenbankobjekten](../debugging-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="5eef4-151">[Debugging CLR Database Objects](../debugging-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="5eef4-152">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="5eef4-152">CLR Integration Security</span></span>](../security/clr-integration-security.md)  
  
  
