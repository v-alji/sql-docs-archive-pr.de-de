---
title: Service Broker mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da179219363422c4ec242d29be61f35dd1609823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618284"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="1bfc6-102">Service Broker mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bfc6-102">Service Broker with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="1bfc6-103">Dieses Thema enthält Informationen, wie Sie Service Broker in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] zur Verwendung mit [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-103">This topic contains information about configuring Service Broker to work with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="1bfc6-104">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-104">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="1bfc6-105">Anforderungen an einen Dienst in einer Verfügbarkeits Gruppe, um Remote Nachrichten zu empfangen</span><span class="sxs-lookup"><span data-stu-id="1bfc6-105">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>](#ReceiveRemoteMessages)  
  
-   [<span data-ttu-id="1bfc6-106">Anforderungen zum Senden von Nachrichten an einen Remote Dienst in einer Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="1bfc6-106">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>](#SendRemoteMessages)  
  
##  <a name="requirements-for-a-service-in-an-availability-group-to-receive-remote-messages"></a><a name="ReceiveRemoteMessages"></a> <span data-ttu-id="1bfc6-107">Anforderungen, damit ein Dienst in einer Verfügbarkeitsgruppe Remotenachrichten empfangen kann</span><span class="sxs-lookup"><span data-stu-id="1bfc6-107">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>  
  
1.  <span data-ttu-id="1bfc6-108">**Stellen Sie sicher, dass die Verfügbarkeitsgruppe über einen Listener verfügt.**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-108">**Ensure that the availability group possesses a listener.**</span></span>  
  
     <span data-ttu-id="1bfc6-109">Weitere Informationen finden Sie unter [Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bfc6-109">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="1bfc6-110">**Stellen Sie sicher, dass der Service Broker-Endpunkt vorhanden ist und ordnungsgemäß konfiguriert wird.**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-110">**Ensure that the Service Broker endpoint exists and is correctly configured.**</span></span>  
  
     <span data-ttu-id="1bfc6-111">Konfigurieren Sie für jede [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz, von der ein Verfügbarkeitsreplikat für die Verfügbarkeitsgruppe gehostet wird, den Service Broker-Endpunkt wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1bfc6-111">On every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group, configure the Service Broker endpoint, as follows:</span></span>  
  
    -   <span data-ttu-id="1bfc6-112">Legen Sie LISTENER_IP auf 'ALL' fest.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-112">Set LISTENER_IP to 'ALL'.</span></span> <span data-ttu-id="1bfc6-113">Durch diese Einstellung werden Verbindungen für eine beliebige gültige IP-Adresse aktiviert, die an den Verfügbarkeitsgruppenlistener gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-113">This setting enables connections on any valid IP address that is bound to the availability group listener.</span></span>  
  
    -   <span data-ttu-id="1bfc6-114">Legen Sie den Service Broker-PORT auf allen Hostserverinstanzen auf die gleiche Portnummer fest.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-114">Set the Service Broker PORT to the same port number on all the host server instances.</span></span>  
  
        > [!TIP]  
        >  <span data-ttu-id="1bfc6-115">Um die Portnummer des Service Broker-Endpunkts für eine bestimmte Serverinstanz anzuzeigen, fragen Sie die **port** -Spalte der [sys.tcp_endpoint](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) s-Katalogsicht ab, in der **type_desc** = 'SERVICE_BROKER' ist.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-115">To view the port number of the Service Broker endpoint on a given server instance, query the **port** column of the [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog view, where **type_desc** = 'SERVICE_BROKER'.</span></span>  
  
     <span data-ttu-id="1bfc6-116">Im folgenden Beispiel wird ein von Windows authentifizierter Service Broker-Endpunkt erstellt, der den Service Broker-Standardport (4022) verwendet und auf alle gültigen IP-Adressen lauscht.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-116">The following example creates a Windows authenticated Service Broker endpoint that uses the default Service Broker port (4022) and listens to all valid IP addresses.</span></span>  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     <span data-ttu-id="1bfc6-117">Weitere Informationen finden Sie unter [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bfc6-117">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
3.  <span data-ttu-id="1bfc6-118">**Erteilen Sie die CONNECT-Berechtigung für den Endpunkt.**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-118">**Grant CONNECT permission on the endpoint.**</span></span>  
  
     <span data-ttu-id="1bfc6-119">Erteilen Sie PUBLIC oder einem Anmeldenamen die CONNECT-Berechtigung für den Service Broker-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-119">Grant CONNECT permission on the Service Broker endpoint either to PUBLIC or to a login.</span></span>  
  
     <span data-ttu-id="1bfc6-120">Im folgenden Beispiel wird PUBLIC die Verbindungsberechtigung für einen Service Broker-Endpunkt mit dem Namen `broker_endpoint` erteilt.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-120">The following example grants the connection on a Service Broker endpoint named `broker_endpoint` to PUBLIC.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     <span data-ttu-id="1bfc6-121">Weitere Informationen finden Sie unter [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-121">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span>  
  
4.  <span data-ttu-id="1bfc6-122">**Stellen Sie sicher, dass in „msdb“ entweder eine AutoCreatedLocal-Route oder eine Route zum angegebenen Dienst enthalten ist.**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-122">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1bfc6-123">Standardmäßig enthält jede Benutzerdatenbank einschließlich **msdb**die Route **AutoCreatedLocal**.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-123">By default, each user database, including **msdb**, contains the route **AutoCreatedLocal**.</span></span> <span data-ttu-id="1bfc6-124">Diese Route stimmt mit beliebigen Dienstnamen und Brokerinstanzen überein und gibt an, dass die Nachricht innerhalb der aktuellen Instanz übermittelt werden muss.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-124">This route matches any service name and broker instance and specifies that the message should be delivered within the current instance.</span></span> <span data-ttu-id="1bfc6-125">**AutoCreatedLocal** hat eine niedrigere Priorität als Routen, in denen explizit ein bestimmter Dienst angegeben ist, der mit einer Remoteinstanz kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-125">**AutoCreatedLocal** has lower priority than routes that explicitly specify a specific service that communicates with a remote instance.</span></span>  
  
     <span data-ttu-id="1bfc6-126">Weitere Informationen zum Erstellen von Routen finden Sie unter [Service Broker-Routingbeispiele](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in der [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] -Version der Onlinedokumentation) und [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql)konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-126">For information about creating routes, see [Service Broker Routing Examples](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in the [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] version of Books Online) and [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
##  <a name="requirements-for-sending-messages-to-a-remote-service-in-an-availability-group"></a><a name="SendRemoteMessages"></a> <span data-ttu-id="1bfc6-127">Anforderungen zum Senden von Nachrichten an einen Remotedienst in einer Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="1bfc6-127">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>  
  
1.  <span data-ttu-id="1bfc6-128">**Erstellen Sie eine Route zum Zieldienst.**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-128">**Create a route to the target service.**</span></span>  
  
     <span data-ttu-id="1bfc6-129">Konfigurieren Sie die Route wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1bfc6-129">Configure the route as follows:</span></span>  
  
    -   <span data-ttu-id="1bfc6-130">Legen Sie ADDRESS auf die IP-Adresse des Listeners der Verfügbarkeitsgruppe fest, von der die Dienstdatenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-130">Set ADDRESS to the listener IP address of availability group that hosts the service database.</span></span>  
  
    -   <span data-ttu-id="1bfc6-131">Legen Sie PORT auf den Port fest, den Sie im Service Broker-Endpunkt jeder SQL Server-Remoteinstanz angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-131">Set PORT to the port that you specified in the Service Broker endpoint of each of the remote SQL Server instances.</span></span>  
  
     <span data-ttu-id="1bfc6-132">Im folgenden Beispiel wird eine Route mit dem Namen `RouteToTargetService` für den `ISBNLookupRequestService` -Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-132">The following example creates a route named `RouteToTargetService` for the `ISBNLookupRequestService` service.</span></span> <span data-ttu-id="1bfc6-133">Die Route hat den Verfügbarkeitsgruppenlistener `MyAgListener`zum Ziel, der den Port 4022 verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-133">The route targets the availability group listener, `MyAgListener`, which uses port 4022.</span></span>  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     <span data-ttu-id="1bfc6-134">Weitere Informationen finden Sie unter [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql)konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-134">For more information, see [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
2.  <span data-ttu-id="1bfc6-135">**Stellen Sie sicher, dass in „msdb“ entweder eine AutoCreatedLocal-Route oder eine Route zum angegebenen Dienst enthalten ist.**</span><span class="sxs-lookup"><span data-stu-id="1bfc6-135">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span> <span data-ttu-id="1bfc6-136">(Weitere Informationen finden Sie unter [Anforderungen, damit ein Dienst in einer Verfügbarkeitsgruppe Remotenachrichten empfangen kann](#ReceiveRemoteMessages)weiter oben in diesem Thema.)</span><span class="sxs-lookup"><span data-stu-id="1bfc6-136">(For more information, see [Requirements for a Service in an Availability Group to Receive Remote Messages](#ReceiveRemoteMessages), earlier in this topic.)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1bfc6-137">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1bfc6-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1bfc6-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1bfc6-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [<span data-ttu-id="1bfc6-139">CREATE ROUTE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1bfc6-139">CREATE ROUTE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [<span data-ttu-id="1bfc6-140">GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1bfc6-140">GRANT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-transact-sql)  
  
-   <span data-ttu-id="1bfc6-141">[Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners (SQL Server)](create-or-configure-an-availability-group-listener-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="1bfc6-141">[Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="1bfc6-142">Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1bfc6-142">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="1bfc6-143">Einrichten von Anmeldekonten für die Daten Bank Spiegelung oder AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1bfc6-143">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bfc6-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1bfc6-144">See Also</span></span>  
 <span data-ttu-id="1bfc6-145">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1bfc6-145">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="1bfc6-146">[Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="1bfc6-146">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="1bfc6-147">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="1bfc6-147">SQL Server Service Broker</span></span>](../../configure-windows/sql-server-service-broker.md)  
  
  
