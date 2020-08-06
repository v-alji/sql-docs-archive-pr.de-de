---
title: Programmgesteuertes Auflisten verfügbarer Pakete | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053f2e598b1cc18e68ee2182092188367ee7f10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696917"
---
# <a name="enumerating-available-packages-programmatically"></a><span data-ttu-id="96ce3-102">Enumerating Available Packages Programmatically</span><span class="sxs-lookup"><span data-stu-id="96ce3-102">Enumerating Available Packages Programmatically</span></span>
  <span data-ttu-id="96ce3-103">Wenn Sie programmgesteuert mit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen arbeiten, möchten Sie u. U. bestimmen, ob ein einzelnes Paket oder ein einzelner Ordner vorhanden ist, oder die gespeicherten Pakete auflisten, die zum Laden und Ausführen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="96ce3-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to enumerate the saved packages that are available to load and execute.</span></span> <span data-ttu-id="96ce3-104">Die <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse des <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace stellt eine Reihe von Methoden bereit, die diese Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="96ce3-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="96ce3-105">Bestimmen, ob ein Paket oder ein Ordner vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="96ce3-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="96ce3-106">Um programmgesteuert zu ermitteln, ob ein gespeichertes Paket vorhanden ist, rufen Sie eine der folgenden Methoden auf, bevor Sie versuchen, es zu laden und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="96ce3-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run it:</span></span>  
  
|<span data-ttu-id="96ce3-107">Speicherort</span><span class="sxs-lookup"><span data-stu-id="96ce3-107">Storage Location</span></span>|<span data-ttu-id="96ce3-108">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="96ce3-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="96ce3-109">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="96ce3-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="96ce3-110">Um programmgesteuert zu ermitteln, ob ein Ordner vorhanden ist, rufen Sie eine der folgenden Methoden auf, bevor Sie versuchen, die darin gespeicherten Pakete aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="96ce3-110">To determine programmatically whether a folder exists before attempting to list the packages stored in it, call one of the following methods:</span></span>  
  
|<span data-ttu-id="96ce3-111">Speicherort</span><span class="sxs-lookup"><span data-stu-id="96ce3-111">Storage Location</span></span>|<span data-ttu-id="96ce3-112">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="96ce3-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="96ce3-113">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="96ce3-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  
 [<span data-ttu-id="96ce3-114">Nach oben</span><span class="sxs-lookup"><span data-stu-id="96ce3-114">Back to top</span></span>](#top)  
  
##  <a name="enumerating-available-packages"></a><a name="listing"></a> <span data-ttu-id="96ce3-115">Auflisten verfügbarer Pakete</span><span class="sxs-lookup"><span data-stu-id="96ce3-115">Enumerating Available Packages</span></span>  
 <span data-ttu-id="96ce3-116">Rufen Sie eine der folgenden Methoden auf, um eine Liste von gespeicherten Paketen programmgesteuert abzurufen:</span><span class="sxs-lookup"><span data-stu-id="96ce3-116">To obtain a list of saved packages programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="96ce3-117">Speicherort</span><span class="sxs-lookup"><span data-stu-id="96ce3-117">Storage Location</span></span>|<span data-ttu-id="96ce3-118">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="96ce3-118">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="96ce3-119">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="96ce3-119">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|  
  
 <span data-ttu-id="96ce3-120">Die folgenden Beispiele sind Konsolenanwendungen, die die Verwendung dieser Methoden veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="96ce3-120">The following samples are console applications that demonstrate the use of these methods.</span></span>  
  
###  <a name="example-ssis-package-store"></a><a name="listing_store"></a> <span data-ttu-id="96ce3-121">Beispiel (SSIS-Paketspeicher)</span><span class="sxs-lookup"><span data-stu-id="96ce3-121">Example (SSIS Package Store)</span></span>  
 <span data-ttu-id="96ce3-122">Verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>-Methode, um im SSIS-Paketspeicher gespeicherte Pakete aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="96ce3-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> method to list packages stored in the SSIS Package Store.</span></span> <span data-ttu-id="96ce3-123">Die Standardspeicherorte, die vom SSIS-Paketspeicher verwaltet werden, sind "Dateisystem" und "MSDB".</span><span class="sxs-lookup"><span data-stu-id="96ce3-123">The default storage locations that are managed by the SSIS Package store are File System and MSDB.</span></span> <span data-ttu-id="96ce3-124">Sie können zusätzliche logische Ordner innerhalb dieser Speicherorte erstellen.</span><span class="sxs-lookup"><span data-stu-id="96ce3-124">You can create additional logical folders within these locations.</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlServer = "."  
  
    ssisApplication = New Application()  
  
    ' Get packages stored in MSDB.  
    sqlFolder = "MSDB"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in MSDB:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
      Console.WriteLine()  
    End If  
  
    ' Get packages stored in the File System.  
    sqlFolder = "File System"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in the File System:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
    End If  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSSIS_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlServer = ".";  
  
      ssisApplication = new Application();  
  
      // Get packages stored in MSDB.  
      sqlFolder = "MSDB";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in MSDB:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
        Console.WriteLine();  
      }  
  
      // Get packages stored in the File System.  
      sqlFolder = "File System";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in the File System:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
      }  
  
      Console.Read();  
  
    }  
  
  }  
  
}  
```  
  
 [<span data-ttu-id="96ce3-125">Nach oben</span><span class="sxs-lookup"><span data-stu-id="96ce3-125">Back to top</span></span>](#top)  
  
###  <a name="example-sql-server"></a><a name="listing_sql"></a> <span data-ttu-id="96ce3-126">Beispiel (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="96ce3-126">Example (SQL Server)</span></span>  
 <span data-ttu-id="96ce3-127">Verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>-Methode, um [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete aufzulisten, die in einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="96ce3-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> method to list [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are stored in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
    Dim sqlUser As String  
    Dim sqlPassword As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlFolder = String.Empty  
    sqlServer = "(local)"  
    sqlUser = String.Empty  
    sqlPassword = String.Empty  
  
    ssisApplication = New Application()  
  
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)  
  
    For Each sqlPackage In sqlPackages  
      Console.WriteLine(sqlPackage.Name)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSql_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
      string sqlUser;  
      string sqlPassword;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlFolder = String.Empty;  
      sqlServer = "(local)";  
      sqlUser = String.Empty;  
      sqlPassword = String.Empty;  
  
      ssisApplication = new Application();  
  
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);  
  
      foreach (PackageInfo sqlPackage in sqlPackages)  
      {  
        Console.WriteLine(sqlPackage.Name);  
      }  
  
      Console.Read();  
  
    }  
  }  
}  
```  
  
 [<span data-ttu-id="96ce3-128">Nach oben</span><span class="sxs-lookup"><span data-stu-id="96ce3-128">Back to top</span></span>](#top)  
  
<span data-ttu-id="96ce3-129">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="96ce3-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="96ce3-130">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="96ce3-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="96ce3-131">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="96ce3-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="96ce3-132">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96ce3-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ce3-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96ce3-133">See Also</span></span>  
 [<span data-ttu-id="96ce3-134">Paketverwaltung &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="96ce3-134">Package Management &#40;SSIS Service&#41;</span></span>](../service/package-management-ssis-service.md)  
  
  
