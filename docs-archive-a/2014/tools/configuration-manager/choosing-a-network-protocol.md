---
title: Auswählen eines Netzwerk Protokolls | Microsoft-Dokumentation
description: Vergleichen und Vergleichen von Netzwerkprotokollen, die zum Herstellen einer Verbindung mit SQL Server Datenbank-Engine verfügbar sind, z. b. Shared Memory, TCP/IP und Named Pipes.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
- Named Pipes [SQL Server]
- TCP [SQL Server]
- network protocols [SQL Server], choosing
- protocols [SQL Server], choosing
- NWLink IPX/SPX [SQL Server]
- client configuration [SQL Server], protocols
- VIA
- Multiprotocol Net-Library [SQL Server]
- IPX/SPX [SQL Server]
- Banyan VINES
- protocols [SQL Server], client configuration
ms.assetid: 6565fb7d-b076-4447-be90-e10d0dec359a
author: rothja
ms.author: jroth
ms.openlocfilehash: 13cbfbcbef54759a16729692e4f5a649f387d059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720677"
---
# <a name="choosing-a-network-protocol"></a><span data-ttu-id="12ee8-103">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="12ee8-103">Choosing a Network Protocol</span></span>
  <span data-ttu-id="12ee8-104">Um eine Verbindung mit [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] herzustellen, müssen Sie ein aktiviertes Netzwerkprotokoll haben.</span><span class="sxs-lookup"><span data-stu-id="12ee8-104">To connect to [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] you must have a network protocol enabled.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="12ee8-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]kann Anforderungen für mehrere Protokolle gleichzeitig bedienen.</span><span class="sxs-lookup"><span data-stu-id="12ee8-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can service requests on several protocols at the same time.</span></span> <span data-ttu-id="12ee8-106">Clients stellen eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über ein einzelnes Protokoll her.</span><span class="sxs-lookup"><span data-stu-id="12ee8-106">Clients connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a single protocol.</span></span> <span data-ttu-id="12ee8-107">Wenn dem Clientprogramm nicht bekannt ist, auf welches Protokoll von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gelauscht wird, konfigurieren Sie den Client so, dass er nacheinander das Verwenden mehrerer Protokolle versucht.</span><span class="sxs-lookup"><span data-stu-id="12ee8-107">If the client program does not know which protocol [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on, configure the client to sequentially try multiple protocols.</span></span> <span data-ttu-id="12ee8-108">Verwenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager, um Netzwerkprotokolle zu aktivieren, zu deaktivieren oder zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="12ee8-108">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable, disable, and configure network protocols.</span></span>  
  
## <a name="shared-memory"></a><span data-ttu-id="12ee8-109">Shared Memory</span><span class="sxs-lookup"><span data-stu-id="12ee8-109">Shared Memory</span></span>  
 <span data-ttu-id="12ee8-110">Shared Memory ist das am einfachsten zu verwendende Protokoll. Es weist keine konfigurierbaren Einstellungen auf.</span><span class="sxs-lookup"><span data-stu-id="12ee8-110">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="12ee8-111">Da Clients, die das Shared Memory-Protokoll verwenden, nur eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen können, die auf demselben Computer ausgeführt wird, ist dieses Protokoll bei den meisten Datenbankaktivitäten nicht hilfreich.</span><span class="sxs-lookup"><span data-stu-id="12ee8-111">Because clients using the shared memory protocol can only connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="12ee8-112">Verwenden Sie das Shared Memory-Protokoll zur Problembehandlung, wenn Sie vermuten, dass die anderen Protokolle nicht ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="12ee8-112">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12ee8-113">Clients mit MDAC 2.8 oder früher können das Shared Memory-Protokoll nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="12ee8-113">Clients that use MDAC 2.8 or earlier cannot use shared memory protocol.</span></span> <span data-ttu-id="12ee8-114">Beim Versuch, das Protokoll aufzurufen, wird automatisch auf das Named Pipes-Protokoll umgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="12ee8-114">If these clients try this, they are automatically switched to the named pipes protocol.</span></span>  
  
## <a name="tcpip"></a><span data-ttu-id="12ee8-115">TCP/IP</span><span class="sxs-lookup"><span data-stu-id="12ee8-115">TCP/IP</span></span>  
 <span data-ttu-id="12ee8-116">TCP/IP ist ein Protokoll, das im Internet häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="12ee8-116">TCP/IP is a common protocol widely used over the Internet.</span></span> <span data-ttu-id="12ee8-117">Es kommuniziert über untereinander verbundene Computernetzwerke mit unterschiedlichen Hardwarearchitekturen und verschiedenen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="12ee8-117">It communicates across interconnected networks of computers that have diverse hardware architectures and various operating systems.</span></span> <span data-ttu-id="12ee8-118">TCP/IP schließt Standards zum Weiterleiten von Netzwerkverkehr ein und bietet erweiterte Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="12ee8-118">TCP/IP includes standards for routing network traffic and offers advanced security features.</span></span> <span data-ttu-id="12ee8-119">Es ist das heute in der Geschäftswelt am häufigsten verwendete Protokoll.</span><span class="sxs-lookup"><span data-stu-id="12ee8-119">It is the most popular protocol that is used in business today.</span></span> <span data-ttu-id="12ee8-120">Das Konfigurieren des Computers für die Verwendung von TCP/IP kann ein komplexer Vorgang sein, allerdings sind die meisten Netzwerkcomputer bereits ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="12ee8-120">Configuring your computer to use TCP/IP can be complex, but most networked computers are already correctly configured.</span></span> <span data-ttu-id="12ee8-121">Weitere Informationen zum Konfigurieren der TCP/IP-Einstellungen, die nicht im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager verfügbar sind, finden Sie in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="12ee8-121">To configure the TCP/IP settings that are not exposed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="named-pipes"></a><span data-ttu-id="12ee8-122">Named Pipes</span><span class="sxs-lookup"><span data-stu-id="12ee8-122">Named Pipes</span></span>  
 <span data-ttu-id="12ee8-123">Named Pipes ist ein Protokoll, das für lokale Netzwerke entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="12ee8-123">Named Pipes is a protocol developed for local area networks.</span></span> <span data-ttu-id="12ee8-124">Ein Teil des Arbeitsspeichers wird von einem Vorgang zum Weiterleiten von Informationen an einen anderen Vorgang verwendet, sodass die Ausgabe des einen Vorgangs der Eingabe des anderen entspricht.</span><span class="sxs-lookup"><span data-stu-id="12ee8-124">A part of memory is used by one process to pass information to another process, so that the output of one is the input of the other.</span></span> <span data-ttu-id="12ee8-125">Der zweite Prozess kann ein lokaler (auf demselben Computer wie der erste) oder ein Remoteprozess (auf einem Computer im Netzwerk) sein.</span><span class="sxs-lookup"><span data-stu-id="12ee8-125">The second process can be local (on the same computer as the first) or remote (on a networked computer).</span></span>  
  
## <a name="named-pipes-vs-tcpip-sockets"></a><span data-ttu-id="12ee8-126">Named Pipes im Vergleich zu TCP/IP-Sockets</span><span class="sxs-lookup"><span data-stu-id="12ee8-126">Named Pipes vs. TCP/IP Sockets</span></span>  
 <span data-ttu-id="12ee8-127">In einer schnellen LAN-Umgebung (Local Area Network) sind TCP/IP-Sockets (Transmission Control Protocol/Internet Protocol) und Named Pipes-Clients hinsichtlich der Leistung vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="12ee8-127">In a fast local area network (LAN) environment, Transmission Control Protocol/Internet Protocol (TCP/IP) Sockets and Named Pipes clients are comparable with regard to performance.</span></span> <span data-ttu-id="12ee8-128">Der Leistungsunterschied zwischen TCP/IP-Sockets und Named Pipes-Clients wird jedoch in langsameren Netzwerken, wie z. B. WANs oder Einwählverbindungen, deutlich.</span><span class="sxs-lookup"><span data-stu-id="12ee8-128">However, the performance difference between the TCP/IP Sockets and Named Pipes clients becomes apparent with slower networks, such as across wide area networks (WANs) or dial-up networks.</span></span> <span data-ttu-id="12ee8-129">Ursache hierfür sind die Unterschiede in der prozessübergreifenden Kommunikation (Interprocess Communication, IPC) zwischen Peers.</span><span class="sxs-lookup"><span data-stu-id="12ee8-129">This is because of the different ways the interprocess communication (IPC) mechanisms communicate between peers.</span></span>  
  
 <span data-ttu-id="12ee8-130">Für Named Pipes ist die Netzwerkkommunikation normalerweise überwiegend interaktiv.</span><span class="sxs-lookup"><span data-stu-id="12ee8-130">For named pipes, network communications are typically more interactive.</span></span> <span data-ttu-id="12ee8-131">Ein Peer sendet keine Daten, bevor ein anderer Peer sie mithilfe eines Lesebefehls anfordert.</span><span class="sxs-lookup"><span data-stu-id="12ee8-131">A peer does not send data until another peer asks for it using a read command.</span></span> <span data-ttu-id="12ee8-132">Zu einem Netzwerklesevorgang gehört normalerweise vor Beginn des Lesens der Daten das kurze Einsehen zahlreicher Named Pipes-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="12ee8-132">A network read typically involves a series of peek named pipes messages before it starts to read the data.</span></span> <span data-ttu-id="12ee8-133">Dies kann in einem langsamen Netzwerk sehr teuer sein und übermäßigen Netzwerkverkehr verursachen, was sich wiederum auf andere Netzwerkclients auswirkt.</span><span class="sxs-lookup"><span data-stu-id="12ee8-133">These can be very costly in a slow network and cause excessive network traffic, which in turn affects other network clients.</span></span>  
  
 <span data-ttu-id="12ee8-134">Darüber hinaus sollte geklärt werden, ob die Kommunikation über lokale Pipes oder Netzwerkpipes stattfindet.</span><span class="sxs-lookup"><span data-stu-id="12ee8-134">It is also important to clarify if you are talking about local pipes or network pipes.</span></span> <span data-ttu-id="12ee8-135">Wenn die Serveranwendung lokal auf dem Computer mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt wird, bietet sich das Verwenden des lokalen Named Pipes-Protokolls an.</span><span class="sxs-lookup"><span data-stu-id="12ee8-135">If the server application is running locally on the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the local Named Pipes protocol is an option.</span></span> <span data-ttu-id="12ee8-136">Lokale Named Pipes-Protokolle werden im Kernelmodus ausgeführt und sind sehr schnell.</span><span class="sxs-lookup"><span data-stu-id="12ee8-136">Local named pipes runs in kernel mode and is very fast.</span></span>  
  
 <span data-ttu-id="12ee8-137">Für TCP/IP-Sockets sind Datenübertragungen geradliniger und mit weniger Verwaltungsaufwand verbunden.</span><span class="sxs-lookup"><span data-stu-id="12ee8-137">For TCP/IP Sockets, data transmissions are more streamlined and have less overhead.</span></span> <span data-ttu-id="12ee8-138">Datenübertragungen können auch von Mechanismen zur TCP/IP-Socketleistungserweiterung, wie beispielsweise Windowing, verzögerten Bestätigungen usw. profitieren.</span><span class="sxs-lookup"><span data-stu-id="12ee8-138">Data transmissions can also take advantage of TCP/IP Sockets performance enhancement mechanisms such as windowing, delayed acknowledgements, and so on.</span></span> <span data-ttu-id="12ee8-139">Dies kann in einem langsamen Netzwerk sehr hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="12ee8-139">This can be very helpful in a slow network.</span></span> <span data-ttu-id="12ee8-140">Abhängig vom Anwendungstyp können diese Leistungsunterschiede sehr deutlich sein.</span><span class="sxs-lookup"><span data-stu-id="12ee8-140">Depending on the type of applications, such performance differences can be significant.</span></span>  
  
 <span data-ttu-id="12ee8-141">TCP/IP-Sockets unterstützen zudem eine Backlogwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="12ee8-141">TCP/IP Sockets also support a backlog queue.</span></span> <span data-ttu-id="12ee8-142">Dadurch kann im Vergleich zu Named Pipes, die aufgrund von ausgelasteten Pipes zu Fehlern beim Verbindungsversuch mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]führen können, ein begrenzter Glättungseffekt erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="12ee8-142">This can provide a limited smoothing effect compared to named pipes that could lead to pipe-busy errors when you are trying to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="12ee8-143">Im Allgemeinen wird TCP/IP in einem langsamen LAN, WAN oder DFÜ-Netzwerk bevorzugt. Wenn die Netzwerkgeschwindigkeit keine Rolle spielt, stellen Named Pipes hingegen häufig die bessere Wahl dar, da sie mehr Funktionalität, größere Benutzerfreundlichkeit und mehr Konfigurationsoptionen bieten.</span><span class="sxs-lookup"><span data-stu-id="12ee8-143">Generally, TCP/IP is preferred in a slow LAN, WAN, or dial-up network, whereas named pipes can be a better choice when network speed is not the issue, as it offers more functionality, ease of use, and configuration options.</span></span>  
  
## <a name="enabling-the-protocol"></a><span data-ttu-id="12ee8-144">Aktivieren des Protokolls</span><span class="sxs-lookup"><span data-stu-id="12ee8-144">Enabling the Protocol</span></span>  
 <span data-ttu-id="12ee8-145">Das Protokoll muss sowohl auf dem Client als auch dem Server aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="12ee8-145">The protocol must be enabled on both the client and server to work.</span></span> <span data-ttu-id="12ee8-146">Der Server kann gleichzeitig auf alle aktivierten Protokolle auf Anforderungen lauschen.</span><span class="sxs-lookup"><span data-stu-id="12ee8-146">The server can listen for requests on all enabled protocols at the same time.</span></span> <span data-ttu-id="12ee8-147">Clientcomputer können ein Protokoll auswählen oder das Verwenden der Protokolle in der Reihenfolge versuchen, in der sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="12ee8-147">Client computers can pick one, or try the protocols in the order listed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="12ee8-148">Ein kurzes Lernprogramm zum Konfigurieren von Protokollen und zum Herstellen einer Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)]finden Sie unter [Tutorial: Erste Schritte mit der Datenbank-Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="12ee8-148">For a short tutorial about how to configure protocols and connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], see [Tutorial: Getting Started with the Database Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span></span>  
  
  