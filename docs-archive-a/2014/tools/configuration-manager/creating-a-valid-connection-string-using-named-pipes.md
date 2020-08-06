---
title: Erstellen einer gültigen Verbindungs Zeichenfolge mithilfe von Named Pipes | Microsoft-Dokumentation
description: Erfahren Sie, wie Sie eine gültige Verbindungs Zeichenfolge erstellen, wenn Sie mit dem Named Pipes-Protokoll eine Verbindung mit einer Instanz von SQL Server herstellen. Anzeigen von Beispielen gültiger Pipenamen.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], named pipes
- pipes [SQL Server]
- pipes [SQL Server], connecting to
- aliases [SQL Server], named pipes
- Named Pipes [SQL Server], connection strings
ms.assetid: 90930ff2-143b-4651-8ae3-297103600e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f3e1d01e9e5b7b1d1c0d1bb822bf233ceee636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617343"
---
# <a name="creating-a-valid-connection-string-using-named-pipes"></a><span data-ttu-id="6b98d-104">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes</span><span class="sxs-lookup"><span data-stu-id="6b98d-104">Creating a Valid Connection String Using Named Pipes</span></span>
  <span data-ttu-id="6b98d-105">Wenn die Standard Instanz von das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Named Pipes-Protokoll überwacht, wird Sie als Pipename verwendet, es sei denn, Sie wird vom Benutzer geändert `\\.\pipe\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="6b98d-105">Unless changed by the user, when the default instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on the named pipes protocol, it uses `\\.\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="6b98d-106">Der Punkt gibt an, dass der Computer der lokale Computer ist, `pipe` gibt an, dass die Verbindung eine Named Pipe ist, und `sql\query` ist der Name der Pipe.</span><span class="sxs-lookup"><span data-stu-id="6b98d-106">The period indicates that the computer is the local computer, `pipe` indicates that the connection is a named pipe, and `sql\query` is the name of the pipe.</span></span> <span data-ttu-id="6b98d-107">Zum Herstellen einer Verbindung mit der Standardpipe muss der Alias `\\<computer_name>\pipe\sql\query` als Pipename aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b98d-107">To connect to the default pipe, the alias must have `\\<computer_name>\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="6b98d-108">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zum Lauschen auf einer anderen Pipe konfiguriert worden ist, muss vom Pipenamen diese Pipe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b98d-108">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to listen on a different pipe, the pipe name must use that pipe.</span></span> <span data-ttu-id="6b98d-109">Wenn beispielsweise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] als Pipe `\\.\pipe\unit\app` verwendet, muss der Alias als Pipenamen `\\<computer_name>\pipe\unit\app` verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b98d-109">For instance, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using `\\.\pipe\unit\app` as the pipe, the alias must use `\\<computer_name>\pipe\unit\app` as the pipe name.</span></span>  
  
 <span data-ttu-id="6b98d-110">Gehen Sie wie folgt vor, um einen gültigen Pipenamen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6b98d-110">To create a valid pipe name, you must:</span></span>  
  
-   <span data-ttu-id="6b98d-111">Geben Sie einen **Aliasnamen**an.</span><span class="sxs-lookup"><span data-stu-id="6b98d-111">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="6b98d-112">Wählen Sie **Named Pipes** als **Protokoll**aus.</span><span class="sxs-lookup"><span data-stu-id="6b98d-112">Select **Named Pipes** as the **Protocol**.</span></span>  
  
-   <span data-ttu-id="6b98d-113">Geben Sie den **Pipenamen**ein.</span><span class="sxs-lookup"><span data-stu-id="6b98d-113">Enter the **Pipe Name**.</span></span> <span data-ttu-id="6b98d-114">Alternativ können Sie den **Pipenamen** leer lassen, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager den entsprechenden Pipenamen nach der Angabe des **Protokolls** und **Servers** vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="6b98d-114">Alternatively, you can leave **Pipe Name** blank and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager will complete the appropriate pipe name after you specify the **Protocol** and **Server**</span></span>  
  
-   <span data-ttu-id="6b98d-115">Geben Sie einen **Server**an.</span><span class="sxs-lookup"><span data-stu-id="6b98d-115">Specify a **Server**.</span></span> <span data-ttu-id="6b98d-116">Sie können für eine benannte Instanz einen Servernamen und Instanznamen angeben.</span><span class="sxs-lookup"><span data-stu-id="6b98d-116">For a named instance you can provide a server name and instance name.</span></span>  
  
 <span data-ttu-id="6b98d-117">Zum Zeitpunkt der Verbindungs Herstellung werden von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Komponente die Werte für den Server, das Protokoll und den Pipenamen aus der Registrierung für den angegebenen Aliasnamen gelesen und ein Pipename im Format `np:\\<computer_name>\pipe\<pipename>` oder erstellt `np:\\<IPAddress>\pipe\<pipename>` . Für eine benannte Instanz lautet der standardpipename `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="6b98d-117">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and pipe name values from the registry for the specified alias name, and creates a pipe name in the format `np:\\<computer_name>\pipe\<pipename>` or `np:\\<IPAddress>\pipe\<pipename>`.For a named instance, the default pipe name is `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b98d-118">Der Port 445 wird von der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Firewall standardmäßig geschlossen.</span><span class="sxs-lookup"><span data-stu-id="6b98d-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 445 by default.</span></span> <span data-ttu-id="6b98d-119">Da [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über den Port 445 kommuniziert, müssen Sie diesen Port erneut öffnen, falls [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zum Lauschen auf eingehende Clientverbindungen mithilfe von Named Pipes konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="6b98d-119">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 445, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using named pipes.</span></span> <span data-ttu-id="6b98d-120">Informationen zum Konfigurieren einer Firewall finden Sie unter "Vorgehensweise: Konfigurieren einer Firewall für SQL Server-Zugriff" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation, oder prüfen Sie Ihre Firewalldokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b98d-120">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="6b98d-121">Herstellen einer Verbindung mit dem lokalen Server</span><span class="sxs-lookup"><span data-stu-id="6b98d-121">Connecting to the Local Server</span></span>  
 <span data-ttu-id="6b98d-122">Beim Herstellen einer Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], das auf dem gleichen Computer wie der Client ausgeführt wird, können Sie `(local)` als Servernamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b98d-122">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)`as the server name.</span></span> <span data-ttu-id="6b98d-123">Aus Gründen der Mehrdeutigkeit wird das Verwenden von `(local)` nicht empfohlen, kann aber nützlich sein, wenn vom Client bekannt ist, dass er auf dem vorgesehenen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6b98d-123">Using `(local)` is not encouraged because it leads to ambiguity; however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="6b98d-124">Beim Erstellen einer Anwendung für mobile Benutzer mit getrennter Verbindung (beispielsweise für Verkaufspersonal, wobei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf Laptops ausgeführt und zum Speichern von Projektdaten verwendet wird) würde beispielsweise die Verbindung eines Clients zu (local) immer zu dem auf dem Laptop ausgeführten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt.</span><span class="sxs-lookup"><span data-stu-id="6b98d-124">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to (local) would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="6b98d-125">Anstelle von `localhost` kann das Wort `(local)` oder ein Punkt (.) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b98d-125">The word `localhost` or a period (.) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="6b98d-126">Überprüfen des Verbindungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="6b98d-126">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="6b98d-127">Von der folgenden Abfrage wird das Protokoll zurückgegeben, das für die aktuelle Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b98d-127">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="6b98d-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6b98d-128">Examples</span></span>  
 <span data-ttu-id="6b98d-129">Verbindung mit Servernamen zur Standardpipe:</span><span class="sxs-lookup"><span data-stu-id="6b98d-129">Connecting by server name to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="6b98d-130">Verbindung mit IP-Adresse zur Standardpipe:</span><span class="sxs-lookup"><span data-stu-id="6b98d-130">Connecting by IP Address to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <leave blank>  
Protocol           Named Pipes  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="6b98d-131">Verbindung mit Servernamen zu einer Nichtstandardpipe:</span><span class="sxs-lookup"><span data-stu-id="6b98d-131">Connecting by server name to a non-default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\unit\app  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="6b98d-132">Verbindung mit Servernamen zu einer benannten Instanz:</span><span class="sxs-lookup"><span data-stu-id="6b98d-132">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\MSSQL$<instancename>\SQL\query  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="6b98d-133">Verbindung zum lokalen Computer mithilfe von `localhost`:</span><span class="sxs-lookup"><span data-stu-id="6b98d-133">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             localhost  
  
```  
  
 <span data-ttu-id="6b98d-134">Verbindung zum lokalen Computer mithilfe eines Punkts:</span><span class="sxs-lookup"><span data-stu-id="6b98d-134">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <left blank>  
Protocol           Named Pipes  
Server             .  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6b98d-135">Informationen zum Angeben des Netzwerk Protokolls als **sqlcmd** -Parameter finden Sie unter "Vorgehensweise: Herstellen einer Verbindung mit dem Datenbank-Engine mithilfe sqlcmd.exe" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Online Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b98d-135">To specify the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b98d-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b98d-136">See Also</span></span>  
 <span data-ttu-id="6b98d-137">[Erstellen einer gültigen Verbindungs Zeichenfolge mithilfe des Shared Memory-Protokolls](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="6b98d-137">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="6b98d-138">[Erstellen einer gültigen Verbindungs Zeichenfolge mithilfe von TCP-IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="6b98d-138">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 [<span data-ttu-id="6b98d-139">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="6b98d-139">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
