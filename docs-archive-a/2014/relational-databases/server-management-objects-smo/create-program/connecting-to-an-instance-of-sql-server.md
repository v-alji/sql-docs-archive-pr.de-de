---
title: Herstellen einer Verbindung mit einer Instanz von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, connections
- connections [SMO]
- instances of SQL Server, connections
- SMO [SQL Server], connections
ms.assetid: ad3cf354-b2e3-468b-b986-1232e375fd84
author: stevestein
ms.author: sstein
ms.openlocfilehash: efc21451f4a876c6edfe4a2389ca937d11bc5c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621997"
---
# <a name="connecting-to-an-instance-of-sql-server"></a><span data-ttu-id="32c37-102">Herstellen einer Verbindung zu einer Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="32c37-102">Connecting to an Instance of SQL Server</span></span>
  <span data-ttu-id="32c37-103">Der erste Programmier Schritt in einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO)-Anwendung besteht darin, eine Instanz des <xref:Microsoft.SqlServer.Management.Smo.Server> -Objekts zu erstellen und eine Verbindung mit einer Instanz von herzustellen [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32c37-103">The first programming step in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) application is to create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and to establish its connection to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="32c37-104">Es stehen drei Möglichkeiten zur Verfügung, um eine Instanz des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts zu erstellen und eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herzustellen.</span><span class="sxs-lookup"><span data-stu-id="32c37-104">You can create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and establish a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in three ways.</span></span> <span data-ttu-id="32c37-105">Die erste Methode verwendet eine <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objektvariable, um die Verbindungsinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="32c37-105">The first is using a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable to provide the connection information.</span></span> <span data-ttu-id="32c37-106">Die zweite Methode besteht darin, die Verbindungsinformationen durch die explizite Angabe der <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekteigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-106">The second is to provide the connection information by explicitly setting the <xref:Microsoft.SqlServer.Management.Smo.Server> object properties.</span></span> <span data-ttu-id="32c37-107">Bei der dritten Methode wird der Name der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz im <xref:Microsoft.SqlServer.Management.Smo.Server>-Objektkonstruktor angegeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-107">The third is to pass the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span>  
  
 <span data-ttu-id="32c37-108">**Verwenden eines ServerConnection-Objekts**</span><span class="sxs-lookup"><span data-stu-id="32c37-108">**Using a ServerConnection object**</span></span>  
  
 <span data-ttu-id="32c37-109">Das Verwenden der <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objektvariable bietet den Vorteil, dass die Verbindungsinformationen wiederverwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="32c37-109">The advantage of using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable is that the connection information can be reused.</span></span> <span data-ttu-id="32c37-110">Deklarieren Sie eine <xref:Microsoft.SqlServer.Management.Smo.Server>-Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="32c37-110">Declare a <xref:Microsoft.SqlServer.Management.Smo.Server> object variable.</span></span> <span data-ttu-id="32c37-111">Deklarieren Sie anschließend ein <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt, und geben Sie die Eigenschaften mit Verbindungsinformationen wie dem Namen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz und dem Authentifizierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="32c37-111">Then, declare a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object and set properties with connection information such as the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and the authentication mode.</span></span> <span data-ttu-id="32c37-112">Übergeben Sie dann die <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objektvariable als Parameter an den <xref:Microsoft.SqlServer.Management.Smo.Server>-Objektkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="32c37-112">Then, pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable as a parameter to the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span> <span data-ttu-id="32c37-113">Es wird nicht empfohlen, mehrere Verbindungen zwischen unterschiedlichen Serverobjekten gleichzeitig freizugeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-113">It is not recommended to share connections between different server objects at the same time.</span></span> <span data-ttu-id="32c37-114">Verwenden Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A>-Methode, um eine Kopie der vorhandenen Verbindungseinstellungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="32c37-114">Use the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to get a copy of the existing connection settings.</span></span>  
  
 <span data-ttu-id="32c37-115">**Explizites Festlegen von Serverobjekteigenschaften**</span><span class="sxs-lookup"><span data-stu-id="32c37-115">**Setting Server object properties explicitly**</span></span>  
  
 <span data-ttu-id="32c37-116">Alternativ können Sie die <xref:Microsoft.SqlServer.Management.Smo.Server>-Objektvariable deklarieren und den Standardkonstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="32c37-116">Alternatively, you can declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and call the default constructor.</span></span> <span data-ttu-id="32c37-117">Normalerweise versucht das <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt, mit sämtlichen Standardverbindungseinstellungen eine Verbindung zur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Standardinstanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="32c37-117">As is, the <xref:Microsoft.SqlServer.Management.Smo.Server> object tries to connect to the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with all the default connection settings.</span></span>  
  
 <span data-ttu-id="32c37-118">**Bereitstellen des Namens der SQL Server-Instanz im Serverobjektkonstruktor**</span><span class="sxs-lookup"><span data-stu-id="32c37-118">**Providing the SQL Server instance name in the Server object constructor**</span></span>  
  
 <span data-ttu-id="32c37-119">Deklarieren Sie die <xref:Microsoft.SqlServer.Management.Smo.Server>-Objektvariable und übergeben Sie den Namen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz als Zeichenfolgenparameter im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="32c37-119">Declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and pass the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance name as a string parameter in the constructor.</span></span> <span data-ttu-id="32c37-120">Das <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt stellt mit den Standardverbindungseinstellungen eine Verbindung zur Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="32c37-120">The <xref:Microsoft.SqlServer.Management.Smo.Server> object establishes a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the default connection settings.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="32c37-121">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="32c37-121">Connection Pooling</span></span>  
 <span data-ttu-id="32c37-122">Es ist in der Regel nicht erforderlich, die <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>-Methode des <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekts aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="32c37-122">It is typically not required to call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="32c37-123">SMO stellt bei Bedarf automatisch eine Verbindung her und gibt nach dem Abschluss der Vorgänge die Verbindung zum Verbindungspool frei.</span><span class="sxs-lookup"><span data-stu-id="32c37-123">SMO will automatically establish a connection when required, and release the connection to the connection pool after it has finished performing operations.</span></span> <span data-ttu-id="32c37-124">Wenn die <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>-Methode aufgerufen wird, wird die Verbindung zum Pool nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-124">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not released to the pool.</span></span> <span data-ttu-id="32c37-125">Um die Verbindung zum Pool freizugeben, ist ein expliziter Aufruf der <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A>-Methode erforderlich.</span><span class="sxs-lookup"><span data-stu-id="32c37-125">An explicit call to the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method is required to release the connection to the pool.</span></span> <span data-ttu-id="32c37-126">Darüber hinaus können Sie eine nicht in einem Pool enthaltene Verbindung anfordern, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekts festlegen.</span><span class="sxs-lookup"><span data-stu-id="32c37-126">Additionally, you can request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="multithreaded-applications"></a><span data-ttu-id="32c37-127">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="32c37-127">Multithreaded Applications</span></span>  
 <span data-ttu-id="32c37-128">Für Multithreadanwendungen sollte in jedem Thread ein separates <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="32c37-128">For multithreaded applications, a separate <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object should be used in each thread.</span></span>  
  
## <a name="connecting-to-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="32c37-129">Herstellen einer Verbindung zu einer Instanz von SQL Server für RMO</span><span class="sxs-lookup"><span data-stu-id="32c37-129">Connecting to an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="32c37-130">Replikationsverwaltungsobjekte (RMO) unterscheiden sich im Aufbau einer Verbindung zu einem Replikationsserver leicht von SMO.</span><span class="sxs-lookup"><span data-stu-id="32c37-130">Replication Management Objects (RMO) uses a slightly different method from SMO to connect to a replication server.</span></span>  
  
 <span data-ttu-id="32c37-131">Bei RMO-Programmierobjekten ist es erforderlich, dass eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mithilfe des durch den `Microsoft.SqlServer.Management.Common`-Namespace implementierten <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekts erfolgt.</span><span class="sxs-lookup"><span data-stu-id="32c37-131">RMO programming objects require that a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is made by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object implemented by the `Microsoft.SqlServer.Management.Common` namespace.</span></span> <span data-ttu-id="32c37-132">Diese Verbindung zum Server erfolgt unabhängig von einem RMO-Programmierobjekt.</span><span class="sxs-lookup"><span data-stu-id="32c37-132">This connection to the server is made independently of an RMO programming object.</span></span> <span data-ttu-id="32c37-133">Sie wird anschließend entweder während der Erstellung der Instanz oder durch die Zuweisung zur <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>-Eigenschaft des Objekts an das RMO-Objekts weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-133">It is then it is passed to the RMO object either during instance creation or by assignment to the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the object.</span></span> <span data-ttu-id="32c37-134">Dadurch können ein RMO-Programmierobjekt und die Instanzen des Verbindungsobjekts getrennt erstellt und verwaltet werden. Zudem kann ein einzelnes Verbindungsobjekt mit mehreren RMO-Programmierobjekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="32c37-134">In this manner, an RMO programming object and the connection object instances can be created and managed separately, and a single connection object can be reused with multiple RMO programming objects.</span></span> <span data-ttu-id="32c37-135">Für Verbindungen mit einem Replikationsserver gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="32c37-135">The following rules apply for connections to a replication server:</span></span>  
  
-   <span data-ttu-id="32c37-136">Alle Eigenschaften für die Verbindung werden für ein angegebenes <xref:Microsoft.SqlServer.Management.Common.ServerConnection> Objekt definiert.</span><span class="sxs-lookup"><span data-stu-id="32c37-136">All properties for the connection are defined for a specified <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="32c37-137">Jede Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] muss über ein eigenes <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt verfügen.</span><span class="sxs-lookup"><span data-stu-id="32c37-137">Each connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must have its own <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="32c37-138">Sämtliche Authentifizierungsinformationen, die zur Herstellung der Verbindung und zur erfolgreichen Anmeldung beim Server erforderlich sind, sind im <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt angegeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-138">All authentication information to make the connection and successfully log on to the server is supplied in the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="32c37-139">Standardmäßig werden Verbindungen mit der Microsoft Windows-Authentifizierung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="32c37-139">By default, connections are made by using Microsoft Windows Authentication.</span></span> <span data-ttu-id="32c37-140">Um die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Authentifizierung verwenden zu können, müssen <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> auf False und <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> sowie <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> auf eine gültige [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Kombination von Anmeldeinformationen und Kennwort gesetzt sein.</span><span class="sxs-lookup"><span data-stu-id="32c37-140">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> must be set to False and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> must be set to a valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logon and password.</span></span> <span data-ttu-id="32c37-141">Anmelde Informationen für die Sicherheit müssen immer sicher gespeichert und verarbeitet werden, und Sie werden zur Laufzeit nach Möglichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="32c37-141">Security credentials must always be stored and handled securely, and supplied at run time whenever possible.</span></span>  
  
-   <span data-ttu-id="32c37-142">Die <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>-Methode muss vor Übergabe der Verbindung an ein RMO-Programmierobjekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="32c37-142">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method must be called before passing the connection to any RMO programming object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="32c37-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="32c37-143">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="32c37-144">Herstellen einer Verbindung zur lokalen Instanz von SQL Server mithilfe der Windows-Authentifizierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32c37-144">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="32c37-145">Das Herstellen einer Verbindung zur lokalen Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erfordert nur wenig Code.</span><span class="sxs-lookup"><span data-stu-id="32c37-145">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="32c37-146">Für Authentifizierungsmethode und Server werden die Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="32c37-146">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="32c37-147">Sobald das erste Mal Daten abgerufen werden müssen, wird eine Verbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="32c37-147">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="32c37-148">Dieses Beispiel ist [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET-Code, der mithilfe der Windows-Authentifizierung eine Verbindung mit der lokalen Instanz von herstellt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32c37-148">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB1](SMO How to#SMO_VB1)]  -->  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="32c37-149">Herstellen einer Verbindung zur lokalen Instanz von SQL Server mithilfe der Windows-Authentifizierung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="32c37-149">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="32c37-150">Das Herstellen einer Verbindung zur lokalen Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erfordert nur wenig Code.</span><span class="sxs-lookup"><span data-stu-id="32c37-150">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="32c37-151">Für Authentifizierungsmethode und Server werden die Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="32c37-151">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="32c37-152">Sobald das erste Mal Daten abgerufen werden müssen, wird eine Verbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="32c37-152">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="32c37-153">Der im Beispiel dargestellte Visual C# .NET-Code stellt mithilfe der Windows-Authentifizierung eine Verbindung zu einer lokalen Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="32c37-153">This example is Visual C# .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//The connection is established when a property is requested.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="32c37-154">Herstellen einer Verbindung zur Remoteinstanz von SQL Server mithilfe der Windows-Authentifizierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32c37-154">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="32c37-155">Wenn Sie mithilfe der Windows-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herstellen, müssen Sie den Authentifizierungstyp nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-155">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="32c37-156">Die Windows-Authentifizierung ist als Standard vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-156">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="32c37-157">Dieses Beispiel ist ein [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET-Code, der mithilfe der Windows-Authentifizierung eine Verbindung mit der Remote Instanz von herstellt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32c37-157">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="32c37-158">Die Zeichen folgen *Variable "* ".</span><span class="sxs-lookup"><span data-stu-id="32c37-158">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB2](SMO How to#SMO_VB2)]  -->  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="32c37-159">Herstellen einer Verbindung zur Remoteinstanz von SQL Server mithilfe der Windows-Authentifizierung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="32c37-159">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="32c37-160">Wenn Sie mithilfe der Windows-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herstellen, müssen Sie den Authentifizierungstyp nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-160">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="32c37-161">Die Windows-Authentifizierung ist als Standard vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-161">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="32c37-162">Der im Beispiel dargestellte Visual C# .NET-Code stellt mithilfe der Windows-Authentifizierung eine Verbindung zu einer Remoteinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="32c37-162">This example is Visual C# .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="32c37-163">Die Zeichen folgen *Variable "* ".</span><span class="sxs-lookup"><span data-stu-id="32c37-163">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
```  
{   
//Connect to a remote instance of SQL Server.   
Server srv;   
//The strServer string variable contains the name of a remote instance of SQL Server.   
srv = new Server(strServer);   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-basic"></a><span data-ttu-id="32c37-164">Herstellen einer Verbindung zu einer Instanz von SQL Server mithilfe der SQL Server-Authentifizierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32c37-164">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual Basic</span></span>  
 <span data-ttu-id="32c37-165">Wenn Sie mithilfe der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herstellen, müssen Sie den Authentifizierungstyp angeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-165">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="32c37-166">In diesem Beispiel ist eine Alternativmethode angegeben, mit der Sie eine <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objektvariable deklarieren und die Verbindungsinformationen wiederverwenden können.</span><span class="sxs-lookup"><span data-stu-id="32c37-166">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="32c37-167">Das Beispiel ist ein [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET-Code, der veranschaulicht, wie eine Verbindung mit dem Remote-und dem *vpassword* -Anmelde-und-Kennwort hergestellt</span><span class="sxs-lookup"><span data-stu-id="32c37-167">The example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim sqlServerLogin As [String] = "user_id"  
      Dim password As [String] = "pwd"  
      Dim instanceName As [String] = "instance_name"  
      Dim remoteSvrName As [String] = "remote_server_name"  
  
      ' Connecting to an instance of SQL Server using SQL Server Authentication  
      Dim srv1 As New Server()   ' connects to default instance  
      srv1.ConnectionContext.LoginSecure = False   ' set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin  
      srv1.ConnectionContext.Password = password  
      Console.WriteLine(srv1.Information.Version)   ' connection is established  
  
      ' Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      Dim srvConn As New ServerConnection()  
      srvConn.ServerInstance = ".\" & instanceName   ' connects to named instance  
      srvConn.LoginSecure = False   ' set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin  
      srvConn.Password = password  
      Dim srv2 As New Server(srvConn)  
      Console.WriteLine(srv2.Information.Version)   ' connection is established  
  
      ' For remote connection, remote server name / ServerInstance needs to be specified  
      Dim srvConn2 As New ServerConnection(remoteSvrName)  
      srvConn2.LoginSecure = False  
      srvConn2.Login = sqlServerLogin  
      srvConn2.Password = password  
      Dim srv3 As New Server(srvConn2)  
      Console.WriteLine(srv3.Information.Version)   ' connection is established  
   End Sub  
End Class  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-c"></a><span data-ttu-id="32c37-168">Herstellen einer Verbindung zu einer Instanz von SQL Server mithilfe der SQL Server-Authentifizierung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="32c37-168">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual C#</span></span>  
 <span data-ttu-id="32c37-169">Wenn Sie mithilfe der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herstellen, müssen Sie den Authentifizierungstyp angeben.</span><span class="sxs-lookup"><span data-stu-id="32c37-169">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="32c37-170">In diesem Beispiel ist eine Alternativmethode angegeben, mit der Sie eine <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objektvariable deklarieren und die Verbindungsinformationen wiederverwenden können.</span><span class="sxs-lookup"><span data-stu-id="32c37-170">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="32c37-171">Das Beispiel ist Visual c# .NET-Code, der veranschaulicht, wie eine Verbindung mit dem Remote-und dem *vpassword* -Element, das Anmelde-und Kennwort enthält</span><span class="sxs-lookup"><span data-stu-id="32c37-171">The example is Visual C# .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {   
      String sqlServerLogin = "user_id";  
      String password = "pwd";  
      String instanceName = "instance_name";  
      String remoteSvrName = "remote_server_name";  
  
      // Connecting to an instance of SQL Server using SQL Server Authentication  
      Server srv1 = new Server();   // connects to default instance  
      srv1.ConnectionContext.LoginSecure = false;   // set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin;  
      srv1.ConnectionContext.Password = password;  
      Console.WriteLine(srv1.Information.Version);   // connection is established  
  
      // Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      ServerConnection srvConn = new ServerConnection();  
      srvConn.ServerInstance = @".\" + instanceName;   // connects to named instance  
      srvConn.LoginSecure = false;   // set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin;  
      srvConn.Password = password;  
      Server srv2 = new Server(srvConn);  
      Console.WriteLine(srv2.Information.Version);   // connection is established  
  
      // For remote connection, remote server name / ServerInstance needs to be specified  
      ServerConnection srvConn2 = new ServerConnection(remoteSvrName);  
      srvConn2.LoginSecure = false;  
      srvConn2.Login = sqlServerLogin;  
      srvConn2.Password = password;  
      Server srv3 = new Server(srvConn2);  
      Console.WriteLine(srv3.Information.Version);   // connection is established  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="32c37-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32c37-172">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
