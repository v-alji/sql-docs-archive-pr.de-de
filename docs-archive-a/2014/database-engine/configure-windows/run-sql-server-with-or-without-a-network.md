---
title: Ausführen von SQL Server mit oder ohne Netzwerk | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a80e7e4d42f322bc42d0c67c57e3a1f9bddb87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618267"
---
# <a name="run-sql-server-with-or-without-a-network"></a><span data-ttu-id="22323-102">Ausführen von SQL Server mit oder ohne Netzwerk</span><span class="sxs-lookup"><span data-stu-id="22323-102">Run SQL Server With or Without a Network</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="22323-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann mit und ohne Netzwerk ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22323-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can run on a network, or it can function without a network.</span></span>  
  
## <a name="running-sql-server-on-a-network"></a><span data-ttu-id="22323-104">Ausführen von SQL Server in einem Netzwerk</span><span class="sxs-lookup"><span data-stu-id="22323-104">Running SQL Server on a Network</span></span>  
 <span data-ttu-id="22323-105">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über ein Netzwerk kommunizieren soll, muss der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22323-105">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to communicate over a network, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service must be running.</span></span> <span data-ttu-id="22323-106">Standardmäßig wird der integrierte [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Dienst automatisch von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Windows gestartet.</span><span class="sxs-lookup"><span data-stu-id="22323-106">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows automatically starts the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="22323-107">Wenn Sie feststellen möchten, ob der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst gestartet wurde, geben Sie Folgendes an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="22323-107">To find out whether the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has been started, at the command prompt, type the following:</span></span>  
  
 <span data-ttu-id="22323-108">**net start**</span><span class="sxs-lookup"><span data-stu-id="22323-108">**net start**</span></span>  
  
 <span data-ttu-id="22323-109">Wenn die Dienste für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gestartet wurden, werden in der Ausgabe von **net start** folgende Dienste angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22323-109">If the services associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have been started, the following services will appear in the **net start** output:</span></span>  
  
-   <span data-ttu-id="22323-110">SQL Server Analysis Services (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="22323-110">Analysis Services (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="22323-111">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="22323-111">SQL Server (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="22323-112">SQL Server-Agent (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="22323-112">SQL Server Agent (MSSQLSERVER)</span></span>  
  
## <a name="running-sql-server-without-a-network"></a><span data-ttu-id="22323-113">Ausführen von SQL Server ohne Netzwerk</span><span class="sxs-lookup"><span data-stu-id="22323-113">Running SQL Server Without a Network</span></span>  
 <span data-ttu-id="22323-114">Wenn eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ohne Netzwerk ausgeführt wird, müssen Sie den integrierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst nicht starten.</span><span class="sxs-lookup"><span data-stu-id="22323-114">When running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without a network, you do not need to start the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="22323-115">Da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], der SQL Server-Konfigurations-Manager und die Befehle **net start** und **net stop** immer funktionsfähig sind, sogar ohne Netzwerk, sind daher die Verfahren für das Starten und Beenden einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit und ohne Netzwerk identisch.</span><span class="sxs-lookup"><span data-stu-id="22323-115">Because [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], SQL Server Configuration Manager, and the **net start** and **net stop** commands are functional even without a network, the procedures for starting and stopping an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are identical for a network or stand-alone operation.</span></span>  
  
 <span data-ttu-id="22323-116">Wenn Sie von einem lokalen Client (z.B. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sqlcmd **) eine Verbindung mit einer eigenständigen Instanz von**herstellen, wird das Netzwerk umgangen. Die Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erfolgt direkt mithilfe einer lokalen Pipe.</span><span class="sxs-lookup"><span data-stu-id="22323-116">When connecting to an instance of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a local client such as **sqlcmd**, you bypass the network and connect directly to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a local pipe.</span></span> <span data-ttu-id="22323-117">Der Unterschied zwischen einer lokalen Pipe und einer Netzwerkpipe besteht darin, dass bei letzterer ein Netzwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22323-117">The difference between a local pipe and a network pipe is whether you are using a network.</span></span> <span data-ttu-id="22323-118">Sowohl lokale Pipes als auch Netzwerkpipes stellen eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe der Standardpipe her (\\\\.\pipe\sql\query), sofern nichts anderes festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="22323-118">Both local and network pipes establish a connection with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the standard pipe (\\\\.\pipe\sql\query), unless otherwise directed.</span></span>  
  
 <span data-ttu-id="22323-119">Wenn Sie ohne Angabe eines Servernamens eine Verbindung mit einer lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen, verwenden Sie eine lokale Pipe.</span><span class="sxs-lookup"><span data-stu-id="22323-119">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without specifying a server name, you are using a local pipe.</span></span> <span data-ttu-id="22323-120">Wenn Sie jedoch bei der Verbindung mit einer lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explizit einen Servernamen angeben, verwenden Sie entweder eine Netzwerkpipe oder einen anderen Mechanismus für die prozessübergreifende Kommunikation (IPC, Interprocess Communication) in Netzwerken, wie z. B. IPX/SPX (unter der Annahme, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Verwendung mehrerer Netzwerke konfiguriert wurde).</span><span class="sxs-lookup"><span data-stu-id="22323-120">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and specify a server name explicitly, you are using either a network pipe or another network interprocess communication (IPC) mechanism, such as Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX) (assuming you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use multiple networks).</span></span> <span data-ttu-id="22323-121">Da ein eigenständiger Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Netzwerkpipes nicht unterstützt, dürfen Sie das nicht notwendige **/** _<Servername>_ -Argument nicht verwenden, wenn Sie von einem Client eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen.</span><span class="sxs-lookup"><span data-stu-id="22323-121">Because a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support network pipes, you must omit the unnecessary **/**_<Server_name>_ argument when connecting to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client.</span></span> <span data-ttu-id="22323-122">Um z.B. mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] osql **eine Verbindung mit einer eigenständigen Instanz von**herzustellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="22323-122">For example, to connect to a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from **osql**, type:</span></span>  
  
 <span data-ttu-id="22323-123">**osql /Usa /P** _\<saPassword>_</span><span class="sxs-lookup"><span data-stu-id="22323-123">**osql /Usa /P** _\<saPassword>_</span></span>  
  
  
