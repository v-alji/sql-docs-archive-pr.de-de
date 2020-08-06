---
title: Programmgesteuertes Hinzufügen von Verbindungen | Microsoft-Dokumentation
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
- connection managers [Integration Services], packages
- Integration Services packages, connections
- connections [Integration Services], packages
- SSIS packages, connections
- packages [Integration Services], connections
- intrinsic properties [Integration Services]
- SQL Server Integration Services packages, connections
- ConnectionManager class
- SSIS connection managers
- adding package connections
ms.assetid: d90716d1-4c65-466c-b82c-4aabbee1e3e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5952221dbf2689d2328695baf965ce884dc07fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616652"
---
# <a name="adding-connections-programmatically"></a><span data-ttu-id="a99b5-102">Programmgesteuertes Hinzufügen von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="a99b5-102">Adding Connections Programmatically</span></span>
  <span data-ttu-id="a99b5-103">Die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Klasse stellt physische Verbindungen zu externen Datenquellen dar.</span><span class="sxs-lookup"><span data-stu-id="a99b5-103">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class represents physical connections to external data sources.</span></span> <span data-ttu-id="a99b5-104">Durch die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Klassen werden die Implementierungsdetails der Verbindung von der Laufzeit isoliert.</span><span class="sxs-lookup"><span data-stu-id="a99b5-104">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class isolates the implementation details of the connection from the runtime.</span></span> <span data-ttu-id="a99b5-105">Daher kann die Laufzeit mit den einzelnen Verbindungs-Managern auf eine konsistente, vorhersehbare Weise interagieren.</span><span class="sxs-lookup"><span data-stu-id="a99b5-105">This enables the runtime to interact with each connection manager in a consistent and predictable manner.</span></span> <span data-ttu-id="a99b5-106">Verbindungs-Manager enthalten eine Reihe von Basiseigenschaften, die alle Verbindungen gemeinsam haben, z. B. die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>-, die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>- <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> und die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a99b5-106">Connection managers contain a set of stock properties that all connections have in common, such as the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span></span> <span data-ttu-id="a99b5-107">Die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>-Eigenschaft und die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>-Eigenschaft sind jedoch in der Regel die einzigen Eigenschaften, die zur Konfiguration eines Verbindungs-Managers erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a99b5-107">However, the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> properties are ordinarily the only properties required to configure a connection manager.</span></span> <span data-ttu-id="a99b5-108">Im Gegensatz zu anderen Programmierungsmodellen, bei denen Verbindungsklassen Methoden wie die `Open`- oder die `Connect`-Methode verfügbar machen, um eine physische Verbindung mit der Datenquelle herzustellen, verwaltet die Runtime-Engine alle Verbindungen für das Paket während der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="a99b5-108">Unlike other programming paradigms, where connection classes expose methods such as `Open` or `Connect` to physically establish a connection to the data source, the run-time engine manages all the connections for the package while it runs.</span></span>  
  
 <span data-ttu-id="a99b5-109">Die <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Klasse ist eine Auflistung der Verbindungs-Manager, die dem Paket hinzugefügt wurden und zur Laufzeit für die Verwendung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-109">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> class is a collection of the connection managers that have been added to that package and are available for use at run time.</span></span> <span data-ttu-id="a99b5-110">Sie können der Auflistung mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A>-Methode der Auflistung mehrere Verbindungs-Manager hinzufügen und eine Zeichenfolge bereitstellen, die den Typ des Verbindungs-Managers angibt.</span><span class="sxs-lookup"><span data-stu-id="a99b5-110">You can add more connection managers to the collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method of the collection, and supplying a string that indicates the connection manager type.</span></span> <span data-ttu-id="a99b5-111">Die <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A>-Methode gibt die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Instanz zurück, die dem Paket hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="a99b5-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method returns the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> instance that was added to the package.</span></span>  
  
## <a name="intrinsic-properties"></a><span data-ttu-id="a99b5-112">Systeminterne Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a99b5-112">Intrinsic Properties</span></span>  
 <span data-ttu-id="a99b5-113">Die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Klasse macht eine Reihe von Eigenschaften verfügbar, die alle Verbindungen gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="a99b5-113">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class exposes a set of properties that are common to all connections.</span></span> <span data-ttu-id="a99b5-114">In einigen Fällen benötigen Sie jedoch Zugriff auf Eigenschaften, die für den speziellen Verbindungstyp eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="a99b5-114">However, sometimes you need access to properties that are unique to the specific connection type.</span></span> <span data-ttu-id="a99b5-115">Die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A>-Auflistung der <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Klasse bietet Zugriff auf diese Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a99b5-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class provides access to these properties.</span></span> <span data-ttu-id="a99b5-116">Die Eigenschaften können mithilfe des Indexers oder des Eigenschaftennamens und der **GetValue**-Methode aus der Auflistung abgerufen werden, und die Werte werden mithilfe der **setValue**-Methode festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a99b5-116">The properties can be retrieved from the collection using the indexer or the property name and the **GetValue** method, and the values are set using the **SetValue** method.</span></span> <span data-ttu-id="a99b5-117">Die Eigenschaften der zugrunde liegenden Verbindungsobjekteigenschaften können auch festgelegt werden, indem eine tatsächliche Instanz des Objekts abgerufen und die Eigenschaften direkt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a99b5-117">The properties of the underlying connection object properties can also be set by acquiring an actual instance of the object and setting its properties directly.</span></span> <span data-ttu-id="a99b5-118">Um die zugrunde liegende Verbindung abzurufen, verwenden Sie die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A>-Eigenschaft des Verbindungs-Managers.</span><span class="sxs-lookup"><span data-stu-id="a99b5-118">To get the underlying connection, use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> property of the connection manager.</span></span> <span data-ttu-id="a99b5-119">In der folgenden Codezeile ist eine C#-Zeile dargestellt, die von einem ADO.NET-Verbindungs-Manager mit der zugrunde liegenden Klasse, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a99b5-119">The following line of code shows a C# line that creates an ADO.NET connection manager that has the underlying class, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span></span>  
  
 `ConnectionManagerAdoNetClass cmado = cm.InnerObject as ConnectionManagerAdoNet;`  
  
 <span data-ttu-id="a99b5-120">Dadurch wird das Objekt des verwalteten Verbindungs-Managers in das zugrunde liegende Verbindungsobjekt umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="a99b5-120">This casts the managed connection manager object to its underlying connection object.</span></span> <span data-ttu-id="a99b5-121">Wenn Sie C++ verwenden, wird die `QueryInterface`-Methode des <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>-Objekts aufgerufen, und die Oberfläche des zugrunde liegenden Verbindungsobjekts wird angefordert.</span><span class="sxs-lookup"><span data-stu-id="a99b5-121">If you are using C++, the `QueryInterface` method of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object is called and the interface of the underlying connection object is requested.</span></span>  
  
 <span data-ttu-id="a99b5-122">In der folgenden Tabelle sind die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthaltenen Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="a99b5-122">The following table lists the connection managers included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="a99b5-123">sowie die Zeichenfolge aufgeführt, die in der `package.Connections.Add("xxx")`-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a99b5-123">and the string that is used in the `package.Connections.Add("xxx")` statement.</span></span> <span data-ttu-id="a99b5-124">Eine Liste aller Verbindungs-Manager finden Sie unter [Integration Services-Verbindungen &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="a99b5-124">For a list of all connection managers, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
|<span data-ttu-id="a99b5-125">String</span><span class="sxs-lookup"><span data-stu-id="a99b5-125">String</span></span>|<span data-ttu-id="a99b5-126">Ziel-Editor für Dimensionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="a99b5-126">Connection manager</span></span>|  
|------------|------------------------|  
|<span data-ttu-id="a99b5-127">„OLEDB“</span><span class="sxs-lookup"><span data-stu-id="a99b5-127">"OLEDB"</span></span>|<span data-ttu-id="a99b5-128">Verbindungs-Manager für OLE DB-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-128">Connection manager for OLE DB connections.</span></span>|  
|<span data-ttu-id="a99b5-129">„ODBC“</span><span class="sxs-lookup"><span data-stu-id="a99b5-129">"ODBC"</span></span>|<span data-ttu-id="a99b5-130">Verbindungs-Manager für ODBC-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-130">Connection manager for ODBC connections.</span></span>|  
|<span data-ttu-id="a99b5-131">„ADO“</span><span class="sxs-lookup"><span data-stu-id="a99b5-131">"ADO"</span></span>|<span data-ttu-id="a99b5-132">Verbindungs-Manager für ADO-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-132">Connection manager for ADO connections.</span></span>|  
|<span data-ttu-id="a99b5-133">„ADO.NET:SQL“</span><span class="sxs-lookup"><span data-stu-id="a99b5-133">"ADO.NET:SQL"</span></span>|<span data-ttu-id="a99b5-134">Verbindungs-Manager für ADO.NET-Verbindungen (SQL-Datenanbieter).</span><span class="sxs-lookup"><span data-stu-id="a99b5-134">Connection manager for ADO.NET (SQL data provider) connections.</span></span>|  
|<span data-ttu-id="a99b5-135">„ADO.NET:OLEDB“</span><span class="sxs-lookup"><span data-stu-id="a99b5-135">"ADO.NET:OLEDB"</span></span>|<span data-ttu-id="a99b5-136">Verbindungs-Manager für ADO.NET-Verbindungen (OLE DB-Datenanbieter).</span><span class="sxs-lookup"><span data-stu-id="a99b5-136">Connection manager for ADO.NET (OLE DB data provider) connections.</span></span>|  
|<span data-ttu-id="a99b5-137">„FLATFILE“</span><span class="sxs-lookup"><span data-stu-id="a99b5-137">"FLATFILE"</span></span>|<span data-ttu-id="a99b5-138">Verbindungs-Manager für Flatfileverbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-138">Connection manager for flat file connections.</span></span>|  
|<span data-ttu-id="a99b5-139">„FILE“</span><span class="sxs-lookup"><span data-stu-id="a99b5-139">"FILE"</span></span>|<span data-ttu-id="a99b5-140">Verbindungs-Manager für Dateiverbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-140">Connection manager for file connections.</span></span>|  
|<span data-ttu-id="a99b5-141">„MULTIFLATFILE“</span><span class="sxs-lookup"><span data-stu-id="a99b5-141">"MULTIFLATFILE"</span></span>|<span data-ttu-id="a99b5-142">Verbindungs-Manager für mehrere Flatfileverbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-142">Connection manager for multiple flat file connections.</span></span>|  
|<span data-ttu-id="a99b5-143">„MULTIFILE“</span><span class="sxs-lookup"><span data-stu-id="a99b5-143">"MULTIFILE"</span></span>|<span data-ttu-id="a99b5-144">Verbindungs-Manager für mehrere Dateiverbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-144">Connection manager for multiple file connections.</span></span>|  
|<span data-ttu-id="a99b5-145">„SQLMOBILE“</span><span class="sxs-lookup"><span data-stu-id="a99b5-145">"SQLMOBILE"</span></span>|<span data-ttu-id="a99b5-146">Verbindungs-Manager für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-146">Connection manager for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connections.</span></span>|  
|<span data-ttu-id="a99b5-147">„MSOLAP100“</span><span class="sxs-lookup"><span data-stu-id="a99b5-147">"MSOLAP100"</span></span>|<span data-ttu-id="a99b5-148">Verbindungs-Manager für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-148">Connection manager for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections.</span></span>|  
|<span data-ttu-id="a99b5-149">„FTP“</span><span class="sxs-lookup"><span data-stu-id="a99b5-149">"FTP"</span></span>|<span data-ttu-id="a99b5-150">Verbindungs-Manager für FTP-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-150">Connection manager for FTP connections.</span></span>|  
|<span data-ttu-id="a99b5-151">„HTTP“</span><span class="sxs-lookup"><span data-stu-id="a99b5-151">"HTTP"</span></span>|<span data-ttu-id="a99b5-152">Verbindungs-Manager für HTTP-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-152">Connection manager for HTTP connections.</span></span>|  
|<span data-ttu-id="a99b5-153">„MSMQ“</span><span class="sxs-lookup"><span data-stu-id="a99b5-153">"MSMQ"</span></span>|<span data-ttu-id="a99b5-154">Verbindungs-Manager für Message Queuing-Verbindungen (auch bekannt als MSMQ).</span><span class="sxs-lookup"><span data-stu-id="a99b5-154">Connection manager for Message Queuing (also known as MSMQ) connections.</span></span>|  
|<span data-ttu-id="a99b5-155">„SMTP“</span><span class="sxs-lookup"><span data-stu-id="a99b5-155">"SMTP"</span></span>|<span data-ttu-id="a99b5-156">Verbindungs-Manager für SMTP-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-156">Connection manager for SMTP connections.</span></span>|  
|<span data-ttu-id="a99b5-157">„WMI“</span><span class="sxs-lookup"><span data-stu-id="a99b5-157">"WMI"</span></span>|<span data-ttu-id="a99b5-158">Verbindungs-Manager für WMI (Microsoft Windows Management Instrumentation)-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a99b5-158">Connection manager for Microsoft Windows Management Instrumentation (WMI) connections.</span></span>|  
  
 <span data-ttu-id="a99b5-159">Im folgenden Codebeispiel wird das Hinzufügen einer OLE DB- und Dateiverbindung zur <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A>-Auflistung eines <xref:Microsoft.SqlServer.Dts.Runtime.Package> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a99b5-159">The following code example demonstrates adding an OLE DB and FILE connection to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> collection of a <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span></span> <span data-ttu-id="a99b5-160">In dem Beispiel werden dann die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>-Eigenschaft, die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>-Eigenschaft und die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a99b5-160">The example then sets the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> properties.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package, and retrieve its connections.  
      Package pkg = new Package();  
      Connections pkgConns = pkg.Connections;  
  
      // Add an OLE DB connection to the package, using the   
      // method defined in the AddConnection class.  
      CreateConnection myOLEDBConn = new CreateConnection();  
      myOLEDBConn.CreateOLEDBConnection(pkg);  
  
      // View the new connection in the package.  
      Console.WriteLine("Connection description: {0}",  
         pkg.Connections["SSIS Connection Manager for OLE DB"].Description);  
  
      // Add a second connection to the package.  
      CreateConnection myFileConn = new CreateConnection();  
      myFileConn.CreateFileConnection(pkg);  
  
      // View the second connection in the package.  
      Console.WriteLine("Connection description: {0}",  
        pkg.Connections["SSIS Connection Manager for Files"].Description);  
  
      Console.WriteLine();  
      Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count);  
  
      Console.Read();  
    }  
  }  
  // <summary>  
  // This class contains the definitions for multiple  
  // connection managers.  
  // </summary>  
  public class CreateConnection  
  {  
    // Private data.  
    private ConnectionManager ConMgr;  
  
    // Class definition for OLE DB Provider.  
    public void CreateOLEDBConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("OLEDB");  
      ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" +  
        "Data Source=(local);";  
      ConMgr.Name = "SSIS Connection Manager for OLE DB";  
      ConMgr.Description = "OLE DB connection to the AdventureWorks database.";  
    }  
    public void CreateFileConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("File");  
      ConMgr.ConnectionString = @"\\<yourserver>\<yourfolder>\books.xml";  
      ConMgr.Name = "SSIS Connection Manager for Files";  
      ConMgr.Description = "Flat File connection";  
    }  
  }  
  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package, and retrieve its connections.  
    Dim pkg As New Package()  
    Dim pkgConns As Connections = pkg.Connections  
  
    ' Add an OLE DB connection to the package, using the   
    ' method defined in the AddConnection class.  
    Dim myOLEDBConn As New CreateConnection()  
    myOLEDBConn.CreateOLEDBConnection(pkg)  
  
    ' View the new connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for OLE DB").Description)  
  
    ' Add a second connection to the package.  
    Dim myFileConn As New CreateConnection()  
    myFileConn.CreateFileConnection(pkg)  
  
    ' View the second connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for Files").Description)  
  
    Console.WriteLine()  
    Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
' This class contains the definitions for multiple  
' connection managers.  
  
Public Class CreateConnection  
  ' Private data.  
  Private ConMgr As ConnectionManager  
  
  ' Class definition for OLE DB provider.  
  Public Sub CreateOLEDBConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("OLEDB")  
    ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" & _  
      "Data Source=(local);"  
    ConMgr.Name = "SSIS Connection Manager for OLE DB"  
    ConMgr.Description = "OLE DB connection to the AdventureWorks database."  
  End Sub  
  
  Public Sub CreateFileConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("File")  
    ConMgr.ConnectionString = "\\<yourserver>\<yourfolder>\books.xml"  
    ConMgr.Name = "SSIS Connection Manager for Files"  
    ConMgr.Description = "Flat File connection"  
  End Sub  
  
End Class  
```  
  
 <span data-ttu-id="a99b5-161">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="a99b5-161">**Sample Output:**</span></span>  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Number of connections in package: 2`  
  
## <a name="external-resources"></a><span data-ttu-id="a99b5-162">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a99b5-162">External Resources</span></span>  
 <span data-ttu-id="a99b5-163">Technischer Artikel, [Verbindungszeichenfolgen](https://go.microsoft.com/fwlink/?LinkId=220743), unter carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="a99b5-163">Technical article, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), on carlprothman.net.</span></span>  
  
<span data-ttu-id="a99b5-164">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a99b5-164">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a99b5-165">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a99b5-165">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a99b5-166">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a99b5-166">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a99b5-167">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a99b5-167">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a99b5-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a99b5-168">See Also</span></span>  
 <span data-ttu-id="a99b5-169">[Integration Services &#40;SSIS-&#41; Verbindungen](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="a99b5-169">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="a99b5-170">Erstellen von Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="a99b5-170">Create Connection Managers</span></span>](../create-connection-managers.md)  
  
  
