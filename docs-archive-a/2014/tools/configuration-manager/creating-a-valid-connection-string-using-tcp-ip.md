---
title: Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine]
- ports [SQL Server], connecting to
- TCP/IP [SQL Server], connection strings
- connection strings [Database Engine], TCP/IP
- aliases [SQL Server], TCP/IP
ms.assetid: ee5dbc2c-1fc6-42bd-bdf5-efa792557934
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f761fa86ec4ed09c13bf4807489754c10b979ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617341"
---
# <a name="creating-a-valid-connection-string-using-tcp-ip"></a><span data-ttu-id="04798-102">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP</span><span class="sxs-lookup"><span data-stu-id="04798-102">Creating a Valid Connection String Using TCP IP</span></span>
  <span data-ttu-id="04798-103">Führen Sie folgende Schritte aus, um eine gültige Verbindungszeichenfolge mithilfe von TCP/IP zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="04798-103">To create a valid connection string using TCP/IP, you must:</span></span>  
  
-   <span data-ttu-id="04798-104">Geben Sie einen **Aliasnamen**an.</span><span class="sxs-lookup"><span data-stu-id="04798-104">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="04798-105">Geben Sie im Feld **Server**entweder den Namen eines Servers an, mit dem Sie eine Verbindung mithilfe des Hilfsprogramms **PING** herstellen können, oder eine IP-Adresse an, mit der Sie eine Verbindung mithilfe des Hilfsprogramms **PING** herstellen können.</span><span class="sxs-lookup"><span data-stu-id="04798-105">For the **Server**, enter either a server name to which you can connect using the **PING** utility, or an IP address to which you can connect using the **PING** utility.</span></span> <span data-ttu-id="04798-106">Bei einer benannten Instanz hängen Sie den Namen der Instanz an.</span><span class="sxs-lookup"><span data-stu-id="04798-106">For a named instance append the instance name.</span></span>  
  
-   <span data-ttu-id="04798-107">Geben Sie **TCP/IP** für das **Protokoll**an.</span><span class="sxs-lookup"><span data-stu-id="04798-107">Specify **TCP/IP** for the **Protocol**.</span></span>  
  
-   <span data-ttu-id="04798-108">Optional können Sie auch eine Portnummer für das Feld **Portnummer**eingeben.</span><span class="sxs-lookup"><span data-stu-id="04798-108">Optionally, enter a port number for the **Port No**.</span></span> <span data-ttu-id="04798-109">Der Standard ist 1433. Dies ist die Portnummer der Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf einem Server.</span><span class="sxs-lookup"><span data-stu-id="04798-109">The default is 1433, which is the port number of the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a server.</span></span> <span data-ttu-id="04798-110">Geben Sie die Portnummer an oder starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst, um eine Verbindung zu einer benannten Instanz oder einer Standardinstanz herzustellen, die nicht an Port 1433 lauscht.</span><span class="sxs-lookup"><span data-stu-id="04798-110">To connect to a named instance or a default instance that is not listening on port 1433, you must provide the port number, or start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span> <span data-ttu-id="04798-111">Weitere Informationen zum Konfigurieren des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdiensts finden Sie unter [SQL Server-Browserdienst](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="04798-111">For information on configuring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service, see [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="04798-112">Während der Verbindung werden von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Komponente die Werte für den Server, das Protokoll und den Port aus der Registrierung für den angegebenen Aliasnamen gelesen und eine Verbindungszeichenfolge im Format `tcp:<servername>[\<instancename>],<port>` oder `tcp:<IPAddress>[\<instancename>],<port>`erstellt.</span><span class="sxs-lookup"><span data-stu-id="04798-112">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and port values from the registry for the specified alias name, and creates a connection string in the format `tcp:<servername>[\<instancename>],<port>` or `tcp:<IPAddress>[\<instancename>],<port>`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04798-113">Der Port 1433 wird von der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Firewall standardmäßig geschlossen.</span><span class="sxs-lookup"><span data-stu-id="04798-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 1433 by default.</span></span> <span data-ttu-id="04798-114">Da [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über den Port 1433 kommuniziert, müssen Sie diesen Port erneut öffnen, falls [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zum Überprüfen eingehender Clientverbindungen mithilfe von TCP/IP konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="04798-114">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 1433, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using TCP/IP.</span></span> <span data-ttu-id="04798-115">Informationen zum Konfigurieren einer Firewall finden Sie unter "Vorgehensweise: Konfigurieren einer Firewall für SQL Server-Zugriff" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation, oder prüfen Sie Ihre Firewalldokumentation.</span><span class="sxs-lookup"><span data-stu-id="04798-115">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="04798-116">und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client unterstützen das Internetprotokoll, Version 4 (IPv4), und das Internetprotokoll, Version 6 (IPv6), vollständig.</span><span class="sxs-lookup"><span data-stu-id="04798-116">and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fully support both Internet Protocol version 4 (IPv4) and Internet Protocol version 6 (IPv6).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="04798-117">-Konfigurations-Manager akzeptiert sowohl IPv4- als auch IPv6-Formate für IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="04798-117">Configuration Manager accepts both IPv4 and IPv6 formats for IP addresses.</span></span> <span data-ttu-id="04798-118">Informationen zu IPv6 finden Sie unter "Herstellen von Verbindungen über IPv6" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="04798-118">For information on IPv6, see "Connecting Using IPv6" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="04798-119">Herstellen einer Verbindung mit dem lokalen Server</span><span class="sxs-lookup"><span data-stu-id="04798-119">Connecting to the Local Server</span></span>  
 <span data-ttu-id="04798-120">Beim Herstellen einer Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , das auf dem gleichen Computer wie der Client ausgeführt wird, können Sie `(local)` als Servernamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="04798-120">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)` as the server name.</span></span> <span data-ttu-id="04798-121">Aus Gründen der Mehrdeutigkeit wird dies nicht empfohlen, kann aber nützlich sein, wenn vom Client bekannt ist, dass er auf dem vorgesehenen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="04798-121">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="04798-122">Beim Erstellen einer Anwendung für mobile Benutzer mit getrennter Verbindung (beispielsweise für Verkaufspersonal, wobei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf Laptops ausgeführt und zum Speichern von Projektdaten verwendet wird) würde beispielsweise die Verbindung eines Clients zu `(local)` immer zu der auf dem Laptop ausgeführten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt.</span><span class="sxs-lookup"><span data-stu-id="04798-122">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to `(local)` would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="04798-123">Anstelle von `localhost` kann das Wort**oder ein Punkt (** . `(local)`) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04798-123">The word `localhost` or a period (**.**) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="04798-124">Überprüfen des Verbindungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="04798-124">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="04798-125">Die folgende Abfrage gibt das Protokoll zurück, das für die aktuelle Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04798-125">The following query returns the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="04798-126">Beispiele</span><span class="sxs-lookup"><span data-stu-id="04798-126">Examples</span></span>  
 <span data-ttu-id="04798-127">Verbindung über Servername:</span><span class="sxs-lookup"><span data-stu-id="04798-127">Connecting by server name:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="04798-128">Verbindung mit Servernamen zu einer benannten Instanz:</span><span class="sxs-lookup"><span data-stu-id="04798-128">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>\<instancename>  
  
```  
  
 <span data-ttu-id="04798-129">Verbindung über Servername zu einem angegebenen Port:</span><span class="sxs-lookup"><span data-stu-id="04798-129">Connecting by server name to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="04798-130">Verbindung über IP-Adresse:</span><span class="sxs-lookup"><span data-stu-id="04798-130">Connecting by IP address:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="04798-131">Verbindung über IP-Adresse zu einer benannten Instanz:</span><span class="sxs-lookup"><span data-stu-id="04798-131">Connecting by IP address to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>\<instancename>  
  
```  
  
 <span data-ttu-id="04798-132">Verbindung über IP-Adresse zu einem angegebenen Port:</span><span class="sxs-lookup"><span data-stu-id="04798-132">Connecting by IP address to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port number>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="04798-133">Verbindung zum lokalen Computer mithilfe von `(local)`:</span><span class="sxs-lookup"><span data-stu-id="04798-133">Connecting to the local computer using `(local)`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             (local)  
  
```  
  
 <span data-ttu-id="04798-134">Verbindung zum lokalen Computer mithilfe von `localhost`:</span><span class="sxs-lookup"><span data-stu-id="04798-134">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost  
  
```  
  
 <span data-ttu-id="04798-135">Verbindung zu einer benannten Instanz auf dem lokalen Computer `localhost`:</span><span class="sxs-lookup"><span data-stu-id="04798-135">Connecting to a named instance on the local computer `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost\<instancename>  
  
```  
  
 <span data-ttu-id="04798-136">Verbindung zum lokalen Computer mithilfe eines Punkts:</span><span class="sxs-lookup"><span data-stu-id="04798-136">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .  
  
```  
  
 <span data-ttu-id="04798-137">Verbindung zu einer benannten Instanz auf dem lokalen Computer mithilfe eines Punkts:</span><span class="sxs-lookup"><span data-stu-id="04798-137">Connecting to a named instance on the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .\<instancename>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="04798-138">Weitere Informationen zum Angeben eines Netzwerkprotokolls als einen **sqlcmd**-Parameter finden Sie unter „Gewusst wie: Herstellen einer Verbindung mit der Datenbank-Engine mithilfe von sqlcmd“ in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="04798-138">For information on specifying the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04798-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04798-139">See Also</span></span>  
 <span data-ttu-id="04798-140">[Erstellen einer gültigen Verbindungszeichenfolge mithilfe des Shared Memory-Protokolls](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="04798-140">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="04798-141">[Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="04798-141">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="04798-142">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="04798-142">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
