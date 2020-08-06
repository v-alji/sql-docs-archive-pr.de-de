---
title: Programmgesteuertes Laden und Ausführen eines Remotepakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- remote packages [Integration Services]
ms.assetid: 9f6ef376-3408-46bf-b5fa-fc7b18c689c9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 06565140ae8ea3603461e2944e242aa91213de47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723998"
---
# <a name="loading-and-running-a-remote-package-programmatically"></a><span data-ttu-id="d9934-102">Programmgesteuertes Laden und Ausführen eines Remotepakets</span><span class="sxs-lookup"><span data-stu-id="d9934-102">Loading and Running a Remote Package Programmatically</span></span>
  <span data-ttu-id="d9934-103">Um Remotepakete auf einem lokalen Computer auszuführen, auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nicht installiert ist, starten Sie die Pakete, sodass sie auf dem Remotecomputer ausgeführt werden, auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d9934-103">To run remote packages from a local computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, start the packages so that they run on the remote computer on which [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span> <span data-ttu-id="d9934-104">Hierzu muss auf dem lokalen Computer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent, ein Webdienst oder eine Remotekomponente zum Starten der Pakete auf dem Remotecomputer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9934-104">You do this by having the local computer use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Web service, or a remote component to start the packages on the remote computer.</span></span> <span data-ttu-id="d9934-105">Wenn Sie versuchen, die Remotepakete direkt auf dem lokalen Computer zu starten, werden die Pakete geladen, und es wird versucht, die Pakete auf dem lokalen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d9934-105">If you try to start the remote packages directly from the local computer, the packages will load onto and try to run from the local computer.</span></span> <span data-ttu-id="d9934-106">Wenn [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nicht auf dem lokalen Computer installiert ist, werden die Pakete nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9934-106">If the local computer does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, the packages will not run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9934-107">Sie können Pakete außerhalb von [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] nur auf Clientcomputern ausführen, auf denen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installiert ist, wobei die Bedingungen Ihrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Lizenz möglicherweise die Installation von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] auf weiteren Computern nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="d9934-107">You cannot run packages outside [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing might not let you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="d9934-108">Bei [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] handelt es sich um eine Serverkomponente, die nicht an Clientcomputer weitergegeben werden darf.</span><span class="sxs-lookup"><span data-stu-id="d9934-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span>  
  
 <span data-ttu-id="d9934-109">Alternativ können Sie ein Remotepaket auch auf einem lokalen Computer ausführen, auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d9934-109">Alternately, you can run a remote package from a local computer that has [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed.</span></span> <span data-ttu-id="d9934-110">Weitere Informationen finden Sie unter [Programmgesteuertes Laden und Ausführen eines lokalen Pakets](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="d9934-110">For more information, see [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span></span>  
  
##  <a name="running-a-remote-package-on-the-remote-computer"></a><a name="top"></a> <span data-ttu-id="d9934-111">Ausführen eines Remotepakets auf dem Remotecomputer</span><span class="sxs-lookup"><span data-stu-id="d9934-111">Running a Remote Package on the Remote Computer</span></span>  
 <span data-ttu-id="d9934-112">Wie bereits erwähnt, gibt es mehrere Möglichkeiten, ein Remotepaket auf einem Remoteserver auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d9934-112">As mentioned above, there are multiple ways in which you can run a remote package on a remote server:</span></span>  
  
-   [<span data-ttu-id="d9934-113">Verwenden von SQL Server-Agent zum programmgesteuerten Ausführen des Remotepakets</span><span class="sxs-lookup"><span data-stu-id="d9934-113">Use SQL Server Agent to run the remote package programmatically</span></span>](#agent)  
  
-   [<span data-ttu-id="d9934-114">Verwenden eines Webdiensts oder einer Remotekomponente zum programmgesteuerten Auszuführen eines Remotepakets</span><span class="sxs-lookup"><span data-stu-id="d9934-114">Use a Web service or remote component to run the remote package programmatically</span></span>](#service)  
  
 <span data-ttu-id="d9934-115">Nahezu alle in diesem Thema erläuterten Methoden zum Laden und Speichern von Paketen erfordern einen Verweis auf die `Microsoft.SqlServer.ManagedDTS`-Assembly.</span><span class="sxs-lookup"><span data-stu-id="d9934-115">Almost all the methods that are used in this topic to load and save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="d9934-116">Die Ausnahme ist der ADO.net-Ansatz, der in diesem Thema veranschaulicht wird, um die gespeicherte Prozedur **sp_start_job** auszuführen, bei der nur ein Verweis auf erforderlich ist `System.Data` .</span><span class="sxs-lookup"><span data-stu-id="d9934-116">The exception is the ADO.NET approach demonstrated in this topic for executing the **sp_start_job** stored procedure, which requires only a reference to `System.Data`.</span></span> <span data-ttu-id="d9934-117">Nachdem Sie den Verweis in einem neuen Projekt zur `Microsoft.SqlServer.ManagedDTS`-Assembly hinzugefügt haben, importieren Sie den <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace mit der Anweisung `using` oder `Imports`.</span><span class="sxs-lookup"><span data-stu-id="d9934-117">After you add the reference to the `Microsoft.SqlServer.ManagedDTS` assembly in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
###  <a name="using-sql-server-agent-to-run-a-remote-package-programmatically-on-the-server"></a><a name="agent"></a> <span data-ttu-id="d9934-118">Verwenden von SQL Server-Agent zum programmgesteuerten Ausführen eines Remotepakets auf dem Server</span><span class="sxs-lookup"><span data-stu-id="d9934-118">Using SQL Server Agent to Run a Remote Package Programmatically on the Server</span></span>  
 <span data-ttu-id="d9934-119">Im folgenden Beispielcode wird die programmgesteuerte Verwendung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent zum Ausführen eines Remotepakets auf dem Server veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d9934-119">The following code sample demonstrates how to programmatically use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a remote package on the server.</span></span> <span data-ttu-id="d9934-120">Im Codebeispiel wird die gespeicherte Systemprozedur **sp_start_job** aufgerufen, die einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Auftrag startet.</span><span class="sxs-lookup"><span data-stu-id="d9934-120">The code sample calls the system stored procedure, **sp_start_job**, which launches a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="d9934-121">Der Auftrag, den die Prozedur startet, hat den Namen `RunSSISPackage` und befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="d9934-121">The job that the procedure launches is named `RunSSISPackage`, and this job is on the remote computer.</span></span> <span data-ttu-id="d9934-122">Der `RunSSISPackage`-Auftrag führt das Paket auf dem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="d9934-122">The `RunSSISPackage` job then runs the package on the remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9934-123">Der Rückgabewert der gespeicherten Prozedur **sp_start_job** gibt an, ob die gespeicherte Prozedur den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Auftrag starten konnte.</span><span class="sxs-lookup"><span data-stu-id="d9934-123">The return value of the **sp_start_job** stored procedure indicates whether the stored procedure was able to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job successfully.</span></span> <span data-ttu-id="d9934-124">Der Rückgabewert gibt nicht an, ob beim Ausführen des Pakets ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d9934-124">The return value does not indicate whether the package succeeded or failed.</span></span>  
  
 <span data-ttu-id="d9934-125">Weitere Informationen zur Problembehandlung bei der Ausführung von Paketen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Aufträgen finden Sie im Microsoft-Artikel [Beim Aufrufen aus einem SQL Server-Agent-Auftragsschritt wird ein SSIS-Paket nicht ausgeführt ](https://support.microsoft.com/kb/918760).</span><span class="sxs-lookup"><span data-stu-id="d9934-125">For information on troubleshooting packages that are run from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, see the Microsoft article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760).</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="d9934-126">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="d9934-126">Sample Code</span></span>  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
  
    Dim jobConnection As SqlConnection  
    Dim jobCommand As SqlCommand  
    Dim jobReturnValue As SqlParameter  
    Dim jobParameter As SqlParameter  
    Dim jobResult As Integer  
  
    jobConnection = New SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI")  
    jobCommand = New SqlCommand("sp_start_job", jobConnection)  
    jobCommand.CommandType = CommandType.StoredProcedure  
  
    jobReturnValue = New SqlParameter("@RETURN_VALUE", SqlDbType.Int)  
    jobReturnValue.Direction = ParameterDirection.ReturnValue  
    jobCommand.Parameters.Add(jobReturnValue)  
  
    jobParameter = New SqlParameter("@job_name", SqlDbType.VarChar)  
    jobParameter.Direction = ParameterDirection.Input  
    jobCommand.Parameters.Add(jobParameter)  
    jobParameter.Value = "RunSSISPackage"  
  
    jobConnection.Open()  
    jobCommand.ExecuteNonQuery()  
    jobResult = DirectCast(jobCommand.Parameters("@RETURN_VALUE").Value, Integer)  
    jobConnection.Close()  
  
    Select Case jobResult  
      Case 0  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.")  
      Case Else  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.")  
    End Select  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace LaunchSSISPackageAgent_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      SqlConnection jobConnection;  
      SqlCommand jobCommand;  
      SqlParameter jobReturnValue;  
      SqlParameter jobParameter;  
      int jobResult;  
  
      jobConnection = new SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI");  
      jobCommand = new SqlCommand("sp_start_job", jobConnection);  
      jobCommand.CommandType = CommandType.StoredProcedure;  
  
      jobReturnValue = new SqlParameter("@RETURN_VALUE", SqlDbType.Int);  
      jobReturnValue.Direction = ParameterDirection.ReturnValue;  
      jobCommand.Parameters.Add(jobReturnValue);  
  
      jobParameter = new SqlParameter("@job_name", SqlDbType.VarChar);  
      jobParameter.Direction = ParameterDirection.Input;  
      jobCommand.Parameters.Add(jobParameter);  
      jobParameter.Value = "RunSSISPackage";  
  
      jobConnection.Open();  
      jobCommand.ExecuteNonQuery();  
      jobResult = (Int32)jobCommand.Parameters["@RETURN_VALUE"].Value;  
      jobConnection.Close();  
  
      switch (jobResult)  
      {  
        case 0:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.");  
          break;  
        default:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.");  
          break;  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
 
  
###  <a name="using-a-web-service-or-remote-component-to-run-a-remote-package-programmatically"></a><a name="service"></a> <span data-ttu-id="d9934-127">Verwenden eines Webdiensts oder einer Remotekomponente zum programmgesteuerten Auszuführen eines Remotepakets</span><span class="sxs-lookup"><span data-stu-id="d9934-127">Using a Web Service or Remote Component to Run a Remote Package Programmatically</span></span>  
 <span data-ttu-id="d9934-128">Für die vorherige Lösung zum programmgesteuerten Ausführen von Paketen auf dem Server ist kein benutzerdefinierter Code auf dem Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9934-128">The previous solution for running packages programmatically on the server does not require any custom code on the server.</span></span> <span data-ttu-id="d9934-129">Möglicherweise bevorzugen Sie jedoch eine Lösung, bei der Pakete ohne SQL Server-Agent ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9934-129">However, you may prefer a solution that does not rely on SQL Server Agent to execute packages.</span></span> <span data-ttu-id="d9934-130">Im Folgenden wird ein Beispiel für einen Webdienst, der auf dem Server zum lokalen Starten von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketen erstellt werden kann, sowie für eine Testanwendung dargestellt, mit deren Hilfe der Webdienst von einem Clientcomputer aus aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9934-130">The following example demonstrates a Web service that can be created on the server to start [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages locally, and a test application that can be used to call the Web service from a client computer.</span></span> <span data-ttu-id="d9934-131">Wenn Sie anstelle eines Webdiensts lieber eine Remotekomponente erstellen, können Sie dieselbe Codelogik mit nur wenigen Änderungen für eine Remotekomponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9934-131">If you prefer to create a remote component instead of a Web service, you can use the same code logic with very few changes in a remote component.</span></span> <span data-ttu-id="d9934-132">Für eine Remotekomponente sind jedoch möglicherweise umfangreichere Konfigurationsschritte erforderlich als für einen Webdienst.</span><span class="sxs-lookup"><span data-stu-id="d9934-132">However a remote component may require more extensive configuration than a Web service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d9934-133">Mit den Standardeinstellungen für die Authentifizierung und Autorisierung verfügt ein Webdienst im Allgemeinen nicht über die erforderlichen Berechtigungen für den Zugriff auf SQL Server oder das Dateisystem, um Pakete zu laden und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d9934-133">With its default settings for authentication and authorization, a Web service generally does not have sufficient permissions to access SQL Server or the file system to load and execute packages.</span></span> <span data-ttu-id="d9934-134">Daher müssen Sie möglicherweise dem Webdienst die entsprechenden Berechtigungen zuweisen. Konfigurieren Sie hierzu die Einstellungen für die Authentifizierung und Autorisierung in der Datei **Web.config**, und weisen Sie die für Datenbank und Dateisystem erforderlichen Berechtigungen zu.</span><span class="sxs-lookup"><span data-stu-id="d9934-134">You may have to assign appropriate permissions to the Web service by configuring its authentication and authorization settings in the **web.config** file and assigning database and file system permissions as appropriate.</span></span> <span data-ttu-id="d9934-135">Eine ausführliche Beschreibung von Berechtigungen für Webdienste, Datenbanken und Dateisysteme ist nicht Gegenstand dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="d9934-135">A complete discussion of Web, database, and file system permissions is beyond the scope of this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d9934-136">Die Methoden der <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse zum Arbeiten mit dem SSIS-Paketspeicher unterstützen nur „.“, localhost oder den Namen des lokalen Servers.</span><span class="sxs-lookup"><span data-stu-id="d9934-136">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="d9934-137">Sie können "(local)" nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9934-137">You cannot use "(local)".</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="d9934-138">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="d9934-138">Sample Code</span></span>  
 <span data-ttu-id="d9934-139">In den folgenden Codebeispielen wird gezeigt, wie der Webdienst erstellt und getestet wird.</span><span class="sxs-lookup"><span data-stu-id="d9934-139">The following code samples show how to create and test the Web service.</span></span>  
  
#### <a name="creating-the-web-service"></a><span data-ttu-id="d9934-140">Erstellen des Webdiensts</span><span class="sxs-lookup"><span data-stu-id="d9934-140">Creating the Web Service</span></span>  
 <span data-ttu-id="d9934-141">Ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket kann direkt aus einer Datei, direkt aus SQL Server oder aus dem SSIS-Paketspeicher geladen werden, der die Paketspeicherung sowohl in SQL Server-Ordnern als auch in speziellen Dateisystemordnern verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d9934-141">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can be loaded directly from a file, directly from SQL Server, or from the SSIS Package Store, which manages package storage in both SQL Server and special file system folders.</span></span> <span data-ttu-id="d9934-142">Dieses Beispiel unterstützt alle verfügbaren Optionen mithilfe eines `Select Case`- oder eines `switch`-Konstrukts, damit die geeignete Syntax zum Starten des Pakets ausgewählt wird und die Eingabeargumente entsprechend verkettet werden können.</span><span class="sxs-lookup"><span data-stu-id="d9934-142">This sample supports all the available options by using a `Select Case` or `switch` construct to select the appropriate syntax for starting the package and to concatenate the input arguments appropriately.</span></span> <span data-ttu-id="d9934-143">Die <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>LaunchPackage<xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Webdienstmethode gibt das Ergebnis der Paketausführung als ganze Zahl zurück und nicht als [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Wert, sodass Clientcomputers keinen Verweis auf {3}-Assemblys benötigen.</span><span class="sxs-lookup"><span data-stu-id="d9934-143">The LaunchPackage Web service method returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span>  
  
###### <a name="to-create-a-web-service-to-run-packages-on-the-server-programmatically"></a><span data-ttu-id="d9934-144">So erstellen Sie einen Webdienst zum programmgesteuerten Ausführen von Paketen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="d9934-144">To create a Web service to run packages on the server programmatically</span></span>  
  
1.  <span data-ttu-id="d9934-145">Öffnen Sie Visual Studio, und erstellen Sie in der gewünchsten Programmiersprache ein Webdienstprojekt.</span><span class="sxs-lookup"><span data-stu-id="d9934-145">Open Visual Studio and create a Web service project in your preferred programming language.</span></span> <span data-ttu-id="d9934-146">Im Beispielcode wird der Name "LaunchSSISPackageService" für das Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9934-146">The sample code uses the name LaunchSSISPackageService for the project.</span></span>  
  
2.  <span data-ttu-id="d9934-147">Fügen Sie einen Verweis auf hinzu, `Microsoft.SqlServer.ManagedDTS` und fügen Sie `Imports` `using` der Codedatei für den **Microsoft. SqlServer. DTS. Runtime** -Namespace eine-oder-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d9934-147">Add a reference to `Microsoft.SqlServer.ManagedDTS` and add an `Imports` or `using` statement to the code file for the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
3.  <span data-ttu-id="d9934-148">Fügen Sie den Beispielcode für die LaunchPackage-Webdienstmethode in die Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="d9934-148">Paste the sample code for the LaunchPackage Web service method into the class.</span></span> <span data-ttu-id="d9934-149">(Im Beispiel ist der gesamte Inhalt des Codefensters dargestellt.)</span><span class="sxs-lookup"><span data-stu-id="d9934-149">(The sample shows the whole contents of the code window.)</span></span>  
  
4.  <span data-ttu-id="d9934-150">Erstellen und testen Sie den Webdienst. Stellen Sie hierzu eine Reihe gültiger Werte für die Eingabeargumente der LaunchPackage-Methode bereit, die auf ein vorhandenes Paket zeigen.</span><span class="sxs-lookup"><span data-stu-id="d9934-150">Build and test the Web service by providing a set of valid values for the input arguments of the LaunchPackage method that point to an existing package.</span></span> <span data-ttu-id="d9934-151">Beispiel: Wenn {1}package1.dtsx{2} auf dem Server im Verzeichnis {3}C:\My Packages{4} gespeichert ist, übergeben Sie "file" als Wert von {5}sourceType{6}, "C:\My Packages" als Wert von {7}sourceLocation{8} und "package1" (ohne Erweiterung) als Wert von {9}packageName{10}.</span><span class="sxs-lookup"><span data-stu-id="d9934-151">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of the sourceType, "C:\My Packages" as the value of sourceLocation, and "package1" (without the extension) as the value of packageName.</span></span>  
  
```vb  
Imports System.Web  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.IO  
  
<WebService(Namespace:="http://dtsue/")> _  
<WebServiceBinding(ConformsTo:=WsiProfiles.BasicProfile1_1)> _  
<Global.Microsoft.VisualBasic.CompilerServices.DesignerGenerated()> _  
Public Class LaunchSSISPackageService  
  Inherits System.Web.Services.WebService  
  
  ' LaunchPackage Method Parameters:  
  ' 1. sourceType: file, sql, dts  
  ' 2. sourceLocation: file system folder, (none), logical folder  
  ' 3. packageName: for file system, ".dtsx" extension is appended  
  
  <WebMethod()> _  
  Public Function LaunchPackage( _  
    ByVal sourceType As String, _  
    ByVal sourceLocation As String, _  
    ByVal packageName As String) As Integer 'DTSExecResult  
  
    Dim packagePath As String  
    Dim myPackage As Package  
    Dim integrationServices As New Application  
  
    ' Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName)  
  
    Select Case sourceType  
      Case "file"  
        ' Package is stored as a file.  
        ' Add extension if not present.  
        If String.IsNullOrEmpty(Path.GetExtension(packagePath)) Then  
          packagePath = String.Concat(packagePath, ".dtsx")  
        End If  
        If File.Exists(packagePath) Then  
          myPackage = integrationServices.LoadPackage(packagePath, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid file location: " & packagePath)  
        End If  
      Case "sql"  
        ' Package is stored in MSDB.  
        ' Combine logical path and package name.  
        If integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty) Then  
          myPackage = integrationServices.LoadFromSqlServer( _  
            packageName, "(local)", String.Empty, String.Empty, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case "dts"  
        ' Package is managed by SSIS Package Store.  
        ' Default logical paths are File System and MSDB.  
        If integrationServices.ExistsOnDtsServer(packagePath, ".") Then  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case Else  
        Throw New ApplicationException( _  
          "Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.")  
    End Select  
  
    Return myPackage.Execute()  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.IO;  
  
[WebService(Namespace = "http://dtsue/")]  
[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
public class LaunchSSISPackageServiceCS : System.Web.Services.WebService  
{  
  public LaunchSSISPackageServiceCS()  
  {  
    }  
  
  // LaunchPackage Method Parameters:  
  // 1. sourceType: file, sql, dts  
  // 2. sourceLocation: file system folder, (none), logical folder  
  // 3. packageName: for file system, ".dtsx" extension is appended  
  
  [WebMethod]  
  public int LaunchPackage(string sourceType, string sourceLocation, string packageName)  
  {   
  
    string packagePath;  
    Package myPackage;  
    Application integrationServices = new Application();  
  
    // Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName);  
  
    switch(sourceType)  
    {  
      case "file":  
        // Package is stored as a file.  
        // Add extension if not present.  
        if (String.IsNullOrEmpty(Path.GetExtension(packagePath)))  
        {  
          packagePath = String.Concat(packagePath, ".dtsx");  
        }  
        if (File.Exists(packagePath))  
        {  
          myPackage = integrationServices.LoadPackage(packagePath, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid file location: "+packagePath);  
        }  
        break;  
      case "sql":  
        // Package is stored in MSDB.  
        // Combine logical path and package name.  
        if (integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty))  
        {  
          myPackage = integrationServices.LoadFromSqlServer(packageName, "(local)", String.Empty, String.Empty, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      case "dts":  
        // Package is managed by SSIS Package Store.  
        // Default logical paths are File System and MSDB.  
        if (integrationServices.ExistsOnDtsServer(packagePath, "."))  
        {  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      default:  
        throw new ApplicationException("Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.");  
    }  
  
    return (Int32)myPackage.Execute();  
  
  }  
  
}  
```  
  
#### <a name="testing-the-web-service"></a><span data-ttu-id="d9934-152">Testen des Webdiensts</span><span class="sxs-lookup"><span data-stu-id="d9934-152">Testing the Web Service</span></span>  
 <span data-ttu-id="d9934-153">Im folgenden Beispiel für eine Konsolenanwendung wird der Webdienst zum Ausführen eines Pakets verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9934-153">The following sample console application uses the Web service to run a package.</span></span> <span data-ttu-id="d9934-154">Die LaunchPackage-Methode des Webdiensts gibt das Ergebnis der Paketausführung als ganze Zahl zurück und nicht als <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Wert, sodass Clientcomputers keinen Verweis auf [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Assemblys benötigen.</span><span class="sxs-lookup"><span data-stu-id="d9934-154">The LaunchPackage method of the Web service returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span> <span data-ttu-id="d9934-155">Mit dem Beispiel wird zum Melden der Ausführungsergebnisse eine private Enumeration erstellt, deren Werte die <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Werte spiegeln.</span><span class="sxs-lookup"><span data-stu-id="d9934-155">The sample creates a private enumeration whose values mirror the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> values to report the results of execution.</span></span>  
  
###### <a name="to-create-a-console-application-to-test-the-web-service"></a><span data-ttu-id="d9934-156">So erstellen Sie eine Konsolenanwendung zum Testen des Webdiensts</span><span class="sxs-lookup"><span data-stu-id="d9934-156">To create a console application to test the Web service</span></span>  
  
1.  <span data-ttu-id="d9934-157">Fügen Sie in Visual Studio mithilfe der gewünschten Programmiersprache eine neue Konsolenanwendung zu der Projektmappe hinzu, die das Webdienstprojekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d9934-157">In Visual Studio, add a new console application, using your preferred programming language, to the same solution that contains the Web service project.</span></span> <span data-ttu-id="d9934-158">Im Beispielcode wird der Name LaunchSSISPackageTest für das Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9934-158">The sample code uses the name LaunchSSISPackageTest for the project.</span></span>  
  
2.  <span data-ttu-id="d9934-159">Legen Sie die neue Konsolenanwendung als Startprojekt in der Projektmappe fest.</span><span class="sxs-lookup"><span data-stu-id="d9934-159">Set the new console application as the startup project in the solution.</span></span>  
  
3.  <span data-ttu-id="d9934-160">Fügen Sie einen Webverweis für das Webdienstprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="d9934-160">Add a Web reference for the Web service project.</span></span> <span data-ttu-id="d9934-161">Passen Sie ggf. die Variablendeklaration im Beispielscode für den Namen an, den Sie dem Webdienstproxyobjekt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d9934-161">If necessary, adjust the variable declaration in the sample code for the name that you assign to the Web service proxy object.</span></span>  
  
4.  <span data-ttu-id="d9934-162">Fügen Sie den Beispielcode für die Hauptroutine und die private Enumeration in den Code ein.</span><span class="sxs-lookup"><span data-stu-id="d9934-162">Paste the sample code for the Main routine and the private enumeration into the code.</span></span> <span data-ttu-id="d9934-163">(Im Beispiel ist der gesamte Inhalt des Codefensters dargestellt.)</span><span class="sxs-lookup"><span data-stu-id="d9934-163">(The sample shows the whole contents of the code window.)</span></span>  
  
5.  <span data-ttu-id="d9934-164">Bearbeiten Sie die Codezeile, die die LaunchPackage-Methode aufruft, um eine Reihe gültiger Werte für die Eingabeargumente bereitzustellen, die auf ein vorhandenes Paket zeigen.</span><span class="sxs-lookup"><span data-stu-id="d9934-164">Edit the line of code that calls the LaunchPackage method to provide a set of valid values for the input arguments that point to an existing package.</span></span> <span data-ttu-id="d9934-165">Beispiel: Wenn package1.dtsx auf dem Server im Verzeichnis C:\My Packages gespeichert ist, übergeben Sie "file" als Wert von `sourceType`, "C:\My Packages" als Wert von `sourceLocation` und "package1" (ohne Erweiterung) als Wert von `packageName`.</span><span class="sxs-lookup"><span data-stu-id="d9934-165">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of `sourceType`, "C:\My Packages" as the value of `sourceLocation`, and "package1" (without the extension) as the value of `packageName`.</span></span>  
  
```vb  
Module LaunchSSISPackageTest  
  
  Sub Main()  
  
    Dim launchPackageService As New LaunchSSISPackageService.LaunchSSISPackageService  
    Dim packageResult As Integer  
  
    Try  
      packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage")  
    Catch ex As Exception  
      ' The type of exception returned by a Web service is:  
      '  System.Web.Services.Protocols.SoapException  
      Console.WriteLine("The following exception occurred: " & ex.Message)  
    End Try  
  
    Console.WriteLine(CType(packageResult, PackageExecutionResult).ToString)  
    Console.ReadKey()  
  
  End Sub  
  
  Private Enum PackageExecutionResult  
    PackageSucceeded  
    PackageFailed  
    PackageCompleted  
    PackageWasCancelled  
  End Enum  
  
End Module  
```  
  
```csharp  
using System;  
  
namespace LaunchSSISPackageSvcTestCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS launchPackageService = new LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS();  
      int packageResult = 0;  
  
      try  
      {  
        packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage");  
      }  
      catch (Exception ex)  
      {  
        // The type of exception returned by a Web service is:  
        //  System.Web.Services.Protocols.SoapException  
        Console.WriteLine("The following exception occurred: " + ex.Message);  
      }  
  
      Console.WriteLine(((PackageExecutionResult)packageResult).ToString());  
      Console.ReadKey();  
  
    }  
  
    private enum PackageExecutionResult  
    {  
      PackageSucceeded,  
      PackageFailed,  
      PackageCompleted,  
      PackageWasCancelled  
    };  
  
  }  
}  
```  
  

  
## <a name="external-resources"></a><span data-ttu-id="d9934-166">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d9934-166">External Resources</span></span>  
  
-   <span data-ttu-id="d9934-167">Video [Vorgehensweise: Automatisieren der SSIS-Paketausführung mit dem SQL Server-Agent (SQL Server-Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx) auf technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d9934-167">Video, [How to: Automate SSIS Package Execution by Using the SQL Server Agent (SQL Server Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx), on technet.microsoft.com</span></span>  
  
<span data-ttu-id="d9934-168">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="d9934-168">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d9934-169">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="d9934-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d9934-170">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="d9934-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d9934-171">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d9934-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9934-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9934-172">See Also</span></span>  
 <span data-ttu-id="d9934-173">[Informationen zu den Unterschieden zwischen der lokalen und der Remote Ausführung](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="d9934-173">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="d9934-174">[Programm gesteuertes laden und Ausführen eines lokalen Pakets](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="d9934-174">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 [<span data-ttu-id="d9934-175">Laden der Ausgabe eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="d9934-175">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
