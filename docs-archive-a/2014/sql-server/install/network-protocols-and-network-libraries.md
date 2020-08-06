---
title: Netzwerkprotokolle und Netzwerkbibliotheken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- protocols [SQL Server]
- configuration options [SQL Server], protocols
- network libraries [SQL Server]
- protocols [SQL Server], about network protocols
- pipes [SQL Server]
- network protocols [SQL Server]
- default SQL Server configurations
- library [SQL Server]
- network protocols [SQL Server], about network protocols
- configuration options [SQL Server], libraries
ms.assetid: 8cd437f6-9af1-44ce-9cb0-4d10c83da9ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be012ea2bc9499a99ca7763446c6f26cf219a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621824"
---
# <a name="network-protocols-and-network-libraries"></a><span data-ttu-id="925ea-102">Netzwerkprotokolle und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="925ea-102">Network Protocols and Network Libraries</span></span>
  <span data-ttu-id="925ea-103">Ein Server kann gleichzeitig auf mehreren Netzwerkprotokollen lauschen bzw. diese überwachen.</span><span class="sxs-lookup"><span data-stu-id="925ea-103">A server can listen on, or monitor, multiple network protocols at one time.</span></span> <span data-ttu-id="925ea-104">Jedes Protokoll muss jedoch konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="925ea-104">However, each protocol must be configured.</span></span> <span data-ttu-id="925ea-105">Wenn ein bestimmtes Protokoll nicht konfiguriert ist, kann der Server auf diesem Protokoll nicht lauschen.</span><span class="sxs-lookup"><span data-stu-id="925ea-105">If a particular protocol is not configured, the server cannot listen on that protocol.</span></span> <span data-ttu-id="925ea-106">Nach der Installation können diese Protokollkonfigurationen mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers geändert werden.</span><span class="sxs-lookup"><span data-stu-id="925ea-106">After installation, you can change the protocol configurations using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="default-sql-server-network-configuration"></a><span data-ttu-id="925ea-107">Standardnetzwerkkonfiguration von SQL Server</span><span class="sxs-lookup"><span data-stu-id="925ea-107">Default SQL Server Network Configuration</span></span>  
 <span data-ttu-id="925ea-108">Eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Standardinstanz wird konfiguriert für TCP/IP, Port 1433 und die Named Pipe „ \\\\.\pipe\sql\query“.</span><span class="sxs-lookup"><span data-stu-id="925ea-108">A default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for TCP/IP port 1433, and named pipe \\\\.\pipe\sql\query.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="925ea-109">werden für dynamische TCP-Ports konfiguriert, wobei eine Portnummer vom Betriebssystem zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="925ea-109">named instances are configured for TCP dynamic ports, with a port number assigned by the operating system.</span></span>  
  
 <span data-ttu-id="925ea-110">Wenn Sie keine dynamischen Portadressen verwenden können (beispielsweise wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindungen über einen Firewallserver weitergeleitet werden, der für die Verwendung bestimmter Portadressen konfiguriert ist).</span><span class="sxs-lookup"><span data-stu-id="925ea-110">If you cannot use dynamic port addresses (for example, when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections must pass through a firewall server configured to pass through specific port addresses).</span></span> <span data-ttu-id="925ea-111">Wählen Sie eine nicht zugewiesene Portnummer aus.</span><span class="sxs-lookup"><span data-stu-id="925ea-111">Select an unassigned port number.</span></span> <span data-ttu-id="925ea-112">Portnummernzuweisungen werden von der Internet Assigned Numbers Authority verwaltet und sind unter [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="925ea-112">Port number assignments are managed by the Internet Assigned Numbers Authority and are listed at [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span></span>  
  
 <span data-ttu-id="925ea-113">Zur Verbesserung der Sicherheit wird die Netzwerkkonnektivität bei der Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht vollständig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="925ea-113">To enhance security, network connectivity is not fully enabled when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span> <span data-ttu-id="925ea-114">Um Netzwerkprotokolle nach Abschluss des Setups zu aktivieren, zu deaktivieren und zu konfigurieren, verwenden Sie den Bereich für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Netzwerkkonfiguration des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers.</span><span class="sxs-lookup"><span data-stu-id="925ea-114">To enable, disable, and configure network protocols after Setup is complete, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Configuration area of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="server-message-block-protocol"></a><span data-ttu-id="925ea-115">SMB (Server Message-Block)-Protokoll</span><span class="sxs-lookup"><span data-stu-id="925ea-115">Server Message Block Protocol</span></span>  
 <span data-ttu-id="925ea-116">Bei Servern im Umkreisnetzwerk sollten alle nicht benötigten Protokolle deaktiviert sein, einschließlich des SMB (Server Message Block).</span><span class="sxs-lookup"><span data-stu-id="925ea-116">Servers in the perimeter network should have all unnecessary protocols disabled, including server message block (SMB).</span></span> <span data-ttu-id="925ea-117">Webserver und DNS-Server (Domain Name System) benötigen SMB nicht.</span><span class="sxs-lookup"><span data-stu-id="925ea-117">Web servers and Domain Name System (DNS) servers do not require SMB.</span></span> <span data-ttu-id="925ea-118">Dieses Protokoll sollte deaktiviert sein, um der Gefahr der Benutzerenumeration vorzubeugen.</span><span class="sxs-lookup"><span data-stu-id="925ea-118">This protocol should be disabled to counter the threat of user enumeration.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="925ea-119">Durch das Deaktivieren von Server Message Block wird der Zugriff auf die Remotedateifreigabe durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder durch den Windows-Clusterdienst blockiert.</span><span class="sxs-lookup"><span data-stu-id="925ea-119">Disabling Server Message Block will block the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Windows Cluster service from accessing the remote file share.</span></span> <span data-ttu-id="925ea-120">Deaktivieren Sie SMB nicht, wenn Sie einen der folgenden Schritte ausführen möchten:</span><span class="sxs-lookup"><span data-stu-id="925ea-120">Do not disable SMB if you do or plan to do one of the following:</span></span>  
> 
>  -   <span data-ttu-id="925ea-121">Verwenden des Mehrheitsquorummodus für Windows-Clusterknoten und Dateifreigaben</span><span class="sxs-lookup"><span data-stu-id="925ea-121">Use Windows Cluster Node and File Share Majority Quorum mode</span></span>  
> -   <span data-ttu-id="925ea-122">Angeben einer SMB-Dateifreigabe als Datenverzeichnis während der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installation</span><span class="sxs-lookup"><span data-stu-id="925ea-122">Specify an SMB file share as the data directory during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation</span></span>  
> -   <span data-ttu-id="925ea-123">Erstellen einer Datenbankdatei auf einer SMB-Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="925ea-123">Create a database file on an SMB file share</span></span>  
  
#### <a name="to-disable-smb"></a><span data-ttu-id="925ea-124">So deaktivieren Sie SMB</span><span class="sxs-lookup"><span data-stu-id="925ea-124">To disable SMB</span></span>  
  
1.  <span data-ttu-id="925ea-125">Zeigen Sie im Menü **Start** auf **Einstellungen**, und klicken Sie dann auf **Netzwerk- und DFÜ-Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="925ea-125">On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**.</span></span>  
  
     <span data-ttu-id="925ea-126">Klicken Sie mit der rechten Maustaste auf die Internetverbindung, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="925ea-126">Right-click the Internet-facing connection, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="925ea-127">Aktivieren Sie das Kontrollkästchen **Client für Microsoft-Netzwerke** , und klicken Sie dann auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="925ea-127">Select the **Client for Microsoft Networks** check box, and then click **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="925ea-128">Befolgen Sie die Schritte zur Deinstallation.</span><span class="sxs-lookup"><span data-stu-id="925ea-128">Follow the uninstall steps.</span></span>  
  
4.  <span data-ttu-id="925ea-129">Aktivieren Sie das Kontrollkästchen **Datei- und Druckerfreigabe für Microsoft-Netzwerke**, und klicken Sie dann auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="925ea-129">Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="925ea-130">Befolgen Sie die Schritte zur Deinstallation.</span><span class="sxs-lookup"><span data-stu-id="925ea-130">Follow the uninstall steps.</span></span>  
  
#### <a name="to-disable-smb-on-servers-accessible-from-the-internet"></a><span data-ttu-id="925ea-131">So deaktivieren Sie SMB auf Servern, auf die vom Internet aus zugegriffen werden kann</span><span class="sxs-lookup"><span data-stu-id="925ea-131">To disable SMB on servers accessible from the Internet</span></span>  
  
-   <span data-ttu-id="925ea-132">Deaktivieren Sie in den Eigenschaften von LAN-Verbindung im Dialogfeld **Eigenschaften von Internetprotokoll (TCP/IP)** die Kontrollkästchen **Datei- und Druckerfreigabe für Microsoft-Netzwerke** und **Client für Microsoft-Netzwerke**.</span><span class="sxs-lookup"><span data-stu-id="925ea-132">In the Local Area Connection properties, use the **Transmission Control Protocol/Internet Protocol (TCP/IP) properties** dialog box to remove **File and Printer Sharing for Microsoft Networks** and **Client for Microsoft Networks**.</span></span>  
  
## <a name="endpoints"></a><span data-ttu-id="925ea-133">Endpunkte</span><span class="sxs-lookup"><span data-stu-id="925ea-133">Endpoints</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="925ea-134">wird ein neues Konzept für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindungen eingeführt: Die Verbindung wird auf dem Server durch einen [!INCLUDE[tsql](../../includes/tsql-md.md)]*Endpunkt*.</span><span class="sxs-lookup"><span data-stu-id="925ea-134">introduces a new concept for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections; the connection is represented on the server end by a [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span></span> <span data-ttu-id="925ea-135">Für die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Endpunkte können Berechtigungen erteilt, aufgehoben oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="925ea-135">Permissions can be granted, revoked, and denied for [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints.</span></span> <span data-ttu-id="925ea-136">Standardmäßig sind alle Benutzer berechtigt, auf einen Endpunkt zuzugreifen, sofern die betreffende Berechtigung nicht durch ein Mitglied der sysadmin-Gruppe oder den Besitzer des Endpunkts verweigert oder aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="925ea-136">By default, all users have permissions to access an endpoint unless the permissions are denied or revoked by a member of the sysadmin group or by the endpoint owner.</span></span> <span data-ttu-id="925ea-137">Im Rahmen der GRANT-, REVOKE- und DENY ENDPOINT-Syntax wird eine Endpunkt-ID verwendet, die der Administrator aus der Katalogsicht des Endpunkts abrufen muss.</span><span class="sxs-lookup"><span data-stu-id="925ea-137">The GRANT, REVOKE, and DENY ENDPOINT syntax uses an endpoint ID that the administrator must get from the endpoint's catalog view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="925ea-138">-Setup erstellt [!INCLUDE[tsql](../../includes/tsql-md.md)] -Endpunkte für alle unterstützten Netzwerkprotokolle und für die dedizierte Administratorverbindung.</span><span class="sxs-lookup"><span data-stu-id="925ea-138">Setup creates [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints for all supported network protocols, as well as for the dedicated administrator connection.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="925ea-139">-Setup werden die folgenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Endpunkte erstellt:</span><span class="sxs-lookup"><span data-stu-id="925ea-139">endpoints created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup are as follows:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="925ea-140">Local Machine</span><span class="sxs-lookup"><span data-stu-id="925ea-140">local machine</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="925ea-141">Named Pipes</span><span class="sxs-lookup"><span data-stu-id="925ea-141">named pipes</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="925ea-142">Default TCP</span><span class="sxs-lookup"><span data-stu-id="925ea-142">default TCP</span></span>  
  
 <span data-ttu-id="925ea-143">Weitere Informationen über Endpunkte finden Sie unter [Konfigurieren der Datenbank-Engine zum Überwachen mehrerer TCP-Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) und [Endpunkte-Katalogsichten &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="925ea-143">For more information about endpoints, see [Configure the Database Engine to Listen on Multiple TCP Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) and [Endpoints Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span></span>  
  
 <span data-ttu-id="925ea-144">Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Netzwerkkonfigurationen finden Sie in den folgenden Themen in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation:</span><span class="sxs-lookup"><span data-stu-id="925ea-144">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network configurations, see the following topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="925ea-145">Server-Netzwerkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="925ea-145">Server Network Configuration</span></span>](../../database-engine/configure-windows/server-network-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="925ea-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="925ea-146">See Also</span></span>  
 <span data-ttu-id="925ea-147">[Oberflächenkonfiguration](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="925ea-147">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 <span data-ttu-id="925ea-148">[Überlegungen zur Sicherheit bei SQL Server-Installationen](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="925ea-148">[Security Considerations for a SQL Server Installation](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="925ea-149">Planen einer SQL Server-Installation</span><span class="sxs-lookup"><span data-stu-id="925ea-149">Planning a SQL Server Installation</span></span>](../../../2014/sql-server/install/planning-a-sql-server-installation.md)  
  
  
