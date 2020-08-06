---
title: Implementieren von Endpunkten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- endpoints [SMO]
ms.assetid: f8674dbb-9bc0-488f-9def-e9e0ce1ddf86
author: stevestein
ms.author: sstein
ms.openlocfilehash: 293a661c6e1ad6f6139e30e0824e99686af98f90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723642"
---
# <a name="implementing-endpoints"></a><span data-ttu-id="94f41-102">Implementieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="94f41-102">Implementing Endpoints</span></span>
  <span data-ttu-id="94f41-103">Ein Endpunkt ist ein Dienst, der Anforderungen systemeigen überwachen kann.</span><span class="sxs-lookup"><span data-stu-id="94f41-103">An endpoint is a service that can listen natively for requests.</span></span> <span data-ttu-id="94f41-104">SMO unterstützt verschiedene Typen von Endpunkten mit dem <xref:Microsoft.SqlServer.Management.Smo.Endpoint>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="94f41-104">SMO supports various types of endpoints by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object.</span></span> <span data-ttu-id="94f41-105">Sie können einen Endpunkt erstellen, der einen bestimmten Typ von Nutzlast handhabt, der ein bestimmtes Protokoll nutzt, indem Sie eine Instanz eines <xref:Microsoft.SqlServer.Management.Smo.Endpoint>-Objekts erstellen und dessen Eigenschaften einrichten.</span><span class="sxs-lookup"><span data-stu-id="94f41-105">You can create an endpoint service that handles a specific type of payload, which uses a specific protocol, by creating an instance of an <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object and setting its properties.</span></span>  
  
 <span data-ttu-id="94f41-106">Die <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Endpoint>-Objekts kann verwendet werden, um die folgenden Nutzlasttypen festzulegen:</span><span class="sxs-lookup"><span data-stu-id="94f41-106">The <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object can be used to specify on of the following payload types:</span></span>  
  
-   <span data-ttu-id="94f41-107">Datenbankspiegelung</span><span class="sxs-lookup"><span data-stu-id="94f41-107">Database mirroring</span></span>  
  
-   <span data-ttu-id="94f41-108">SOAP (SOAP-Endpunkte werden in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] und früheren [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Versionen unterstützt)</span><span class="sxs-lookup"><span data-stu-id="94f41-108">SOAP (support for SOAP endpoints is present in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] and earlier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] versions)</span></span>  
  
-   <span data-ttu-id="94f41-109">Service Broker</span><span class="sxs-lookup"><span data-stu-id="94f41-109">Service Broker</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]  
  
 <span data-ttu-id="94f41-110">Darüber hinaus kann die <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>-Eigenschaft verwendet werden, um die beiden folgenden unterstützten Protokolle anzugeben:</span><span class="sxs-lookup"><span data-stu-id="94f41-110">Also, the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property can be used to specify the following two supported protocols:</span></span>  
  
-   <span data-ttu-id="94f41-111">HTTP-Protokoll</span><span class="sxs-lookup"><span data-stu-id="94f41-111">HTTP protocol</span></span>  
  
-   <span data-ttu-id="94f41-112">TCP-Protokoll</span><span class="sxs-lookup"><span data-stu-id="94f41-112">TCP protocol</span></span>  
  
 <span data-ttu-id="94f41-113">Nach Festlegung des Nutzlasttyps kann die tatsächliche Nutzlast über die <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A>-Objekteigenschaft eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="94f41-113">Having specified the type of payload, the actual payload can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> object property.</span></span> <span data-ttu-id="94f41-114">Die <xref:Microsoft.SqlServer.Management.Smo.Payload>-Objekteigenschaft stellt einen Verweis auf ein Nutzlastobjekt eines bestimmten Typs bereit, dessen Eigenschaften geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="94f41-114">The <xref:Microsoft.SqlServer.Management.Smo.Payload> object property provides a reference to a payload object of the specified type, for which the properties can be modified.</span></span>  
  
 <span data-ttu-id="94f41-115">Für das <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload>-Objekt müssen Sie die Spiegelungsrolle angeben und ob Verschlüsselung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="94f41-115">For the <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> object, you must specify the mirroring role and whether encryption is enabled.</span></span> <span data-ttu-id="94f41-116">Das <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload>-Objekt erfordert Informationen über die Nachrichtenweiterleitung, die maximale Anzahl der zugelassenen Verbindungen und den Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="94f41-116">The <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> object requires information about message forwarding, maximum number of connections allowed and the authentication mode.</span></span> <span data-ttu-id="94f41-117">Das <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A>-Objekt erfordert, dass diverse Eigenschaften eingerichtet werden müssen; hierunter auch die <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A>-Objekteigenschaft, die die SOAP-Nutzlastmethoden angibt, die Clients zur Verfügung stehen (gespeicherte Prozeduren und benutzerdefinierte Funktionen).</span><span class="sxs-lookup"><span data-stu-id="94f41-117">The <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> object requires various properties to be set including the <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> object property that specifies the SOAP payload methods available to clients (stored procedures and user-defined functions).</span></span>  
  
 <span data-ttu-id="94f41-118">Ähnlich kann das tatsächliche Protokoll über die <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A>-Objekteigenschaft eingerichtet werden, die auf ein Protokollobjekt verweist, das den von der <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>-Eigenschaft festgelegten Typ besitzt.</span><span class="sxs-lookup"><span data-stu-id="94f41-118">Similarly, the actual protocol can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> object property that references a protocol object of the type specified by <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property.</span></span> <span data-ttu-id="94f41-119">Das <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol>-Objekt erfordert eine Liste der eingeschränkten IP-Adressen und Informationen über Port, Website und Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="94f41-119">The <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> object requires a list of restricted IP addresses, and port, website, and authentication information.</span></span> <span data-ttu-id="94f41-120">Das <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol>-Objekt erfordert ebenfalls eine Liste der eingeschränkten IP-Adressen und Informationen über den Port.</span><span class="sxs-lookup"><span data-stu-id="94f41-120">The <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> object also requires a list of restricted IP addresses and port information.</span></span>  
  
 <span data-ttu-id="94f41-121">Wenn der Endpunkt erstellt wurde und vollständig definiert ist, kann Datenbankbenutzern, Gruppen, Rollen und Anmeldungen der Zugriff gewährt, aufgehoben oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="94f41-121">When the endpoint has been created and fully defined, access can be granted to, revoked from, and denied to database users, groups, roles, and logons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94f41-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94f41-122">Example</span></span>  
 <span data-ttu-id="94f41-123">Für das folgende Codebeispiel müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-123">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="94f41-124">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="94f41-124">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-basic"></a><span data-ttu-id="94f41-125">Erstellen eines Datenbankspiegelungs-Endpunkt-Diensts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94f41-125">Creating a Database Mirroring Endpoint Service in Visual Basic</span></span>  
 <span data-ttu-id="94f41-126">Im Codebeispiel wird veranschaulicht, wie ein Datenbankspiegelungs-Endpunkt in SMO erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94f41-126">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="94f41-127">Dies ist notwendig, bevor Sie einen Datenbankspiegel erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-127">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="94f41-128">Verwenden Sie <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> und andere Eigenschaften auf dem <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt, um einen Datenbankspiegel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-128">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEndpoints1](SMO How to#SMO_VBEndpoints1)]  -->  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-c"></a><span data-ttu-id="94f41-129">Erstellen eines Datenbankspiegelungs-Endpunkt-Diensts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="94f41-129">Creating a Database Mirroring Endpoint Service in Visual C#</span></span>  
 <span data-ttu-id="94f41-130">Im Codebeispiel wird veranschaulicht, wie ein Datenbankspiegelungs-Endpunkt in SMO erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94f41-130">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="94f41-131">Dies ist notwendig, bevor Sie einen Datenbankspiegel erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-131">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="94f41-132">Verwenden Sie <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> und andere Eigenschaften auf dem <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt, um einen Datenbankspiegel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-132">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```csharp
{  
            //Set up a database mirroring endpoint on the server before   
        //setting up a database mirror.   
        //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Define an Endpoint object variable for database mirroring.   
            Endpoint ep = default(Endpoint);  
            ep = new Endpoint(srv, "Mirroring_Endpoint");  
            ep.ProtocolType = ProtocolType.Tcp;  
            ep.EndpointType = EndpointType.DatabaseMirroring;  
            //Specify the protocol ports.   
            ep.Protocol.Http.SslPort = 5024;  
            ep.Protocol.Tcp.ListenerPort = 6666;  
            //Specify the role of the payload.   
            ep.Payload.DatabaseMirroring.ServerMirroringRole = ServerMirroringRole.All;  
            //Create the endpoint on the instance of SQL Server.   
            ep.Create();  
            //Start the endpoint.   
            ep.Start();  
            Console.WriteLine(ep.EndpointState);  
        }  
```  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-powershell"></a><span data-ttu-id="94f41-133">+Erstellen eines Datenbankspiegelungs-Endpunkt-Diensts in PowerShell</span><span class="sxs-lookup"><span data-stu-id="94f41-133">Creating a Database Mirroring Endpoint Service in PowerShell</span></span>  
 <span data-ttu-id="94f41-134">Im Codebeispiel wird veranschaulicht, wie ein Datenbankspiegelungs-Endpunkt in SMO erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94f41-134">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="94f41-135">Dies ist notwendig, bevor Sie einen Datenbankspiegel erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-135">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="94f41-136">Verwenden Sie <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> und andere Eigenschaften auf dem <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt, um einen Datenbankspiegel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="94f41-136">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get a new endpoint to congure and add  
$ep = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Endpoint -argumentlist $srv,"Mirroring_Endpoint"  
  
#Set some properties  
$ep.ProtocolType = [Microsoft.SqlServer.Management.SMO.ProtocolType]::Tcp  
$ep.EndpointType = [Microsoft.SqlServer.Management.SMO.EndpointType]::DatabaseMirroring  
$ep.Protocol.Http.SslPort = 5024  
$ep.Protocol.Tcp.ListenerPort = 6666 #inline comment  
$ep.Payload.DatabaseMirroring.ServerMirroringRole = [Microsoft.SqlServer.Management.SMO.ServerMirroringRole]::All  
  
# Create the endpoint on the instance  
$ep.Create()  
  
# Start the endpoint  
$ep.Start()  
  
# Report its state  
$ep.EndpointState;  
```  
  
## <a name="see-also"></a><span data-ttu-id="94f41-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94f41-137">See Also</span></span>  
 [<span data-ttu-id="94f41-138">Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94f41-138">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
