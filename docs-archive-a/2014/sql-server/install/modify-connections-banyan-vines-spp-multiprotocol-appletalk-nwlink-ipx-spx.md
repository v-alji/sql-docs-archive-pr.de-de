---
title: Ändern Sie die Verbindungen, die die Netzwerkprotokolle Banyan Vines sequenziert Packet Protocol (SPP), Multiprotocol, AppleTalk oder NWLink IPX SPX verwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], modifying connections
- SPP [SQL Server]
- NWLink IPX/SPX [SQL Server]
- connections [SQL Server]
- AppleTalk [SQL Server]
- Sequenced Packet Protocol [SQL Server]
- Multiprotocol Net-Library [SQL Server]
- Banyan VINES Sequenced Package Protocol [SQL Server]
- IPX/SPX [SQL Server]
- protocols [SQL Server], modifying connections
- RPC [SQL Server]
ms.assetid: 5c5ae453-cc5b-4898-95c7-ad34157b1f60
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 750b9c0b76ab6c3b43908ecb8454f31ac1a25b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724374"
---
# <a name="modify-connections-that-use-banyan-vines-sequenced-packet-protocol-spp-multiprotocol-appletalk-or-nwlink-ipx-spx-network-protocols"></a><span data-ttu-id="4f88a-102">Ändern von Verbindungen, die die Netzwerkprotokolle Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk oder NWLink IPX/SPX verwenden</span><span class="sxs-lookup"><span data-stu-id="4f88a-102">Modify connections that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX SPX network protocols</span></span>
  <span data-ttu-id="4f88a-103">Der Upgrade Advisor hat Client-Server-Verbindungsprotokolle erkannt, die in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4f88a-103">The Upgrade Advisor has detected client server connectivity protocols that are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4f88a-104">Clientanwendungen, die als Netzwerkprotokoll Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk oder NWLink IPX/SPX verwenden, müssen eine Verbindung über ein unterstütztes Protokoll herstellen.</span><span class="sxs-lookup"><span data-stu-id="4f88a-104">Client applications that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk, or NWLink IPX/SPX network protocols must connect using a supported protocol.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4f88a-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="4f88a-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4f88a-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4f88a-106">Description</span></span>  
 <span data-ttu-id="4f88a-107">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] werden die Netzwerkprotokolle Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk und NWLink IPX/SPX nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4f88a-107">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support the Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX/SPX network protocols.</span></span> <span data-ttu-id="4f88a-108">Clients, die zuvor Verbindungen mit diesen Protokollen hergestellt haben, müssen ein anderes Protokoll auswählen.</span><span class="sxs-lookup"><span data-stu-id="4f88a-108">Clients previously connecting with these protocols must select a different protocol.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4f88a-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="4f88a-109">Corrective Action</span></span>  
 <span data-ttu-id="4f88a-110">Ändern Sie die Clientanwendungen entsprechend, um ein unterstütztes Protokoll zu verwenden, wenn Sie eine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="4f88a-110">Change the client applications to use a supported protocol when connecting to the server.</span></span> <span data-ttu-id="4f88a-111">Wenn ein Alias eingerichtet ist, der eines der nicht unterstützten Protokolle verwendet, muss der Alias so geändert werden, dass er eines der unterstützten Protokolle verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f88a-111">If you have an alias setup that uses one of the unsupported protocols then the alias must be modified to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="4f88a-112">Wenn Ihre Anwendungs Verbindungs Zeichenfolge eines dieser Protokolle ausdrücklich verwendet oder lädt, indem Sie entweder Network = dbmsrpcn für RPC, Network = Dbmsadsn für AppleTalk oder Network = Dbmsvinn für Banyan Vines-Eigenschaft angeben, wenn Sie ein explizites Präfix wie z. b. "SPX:*/Instanznamen*" für SPX, "BV:*Server*" für Banyan-Reben, "ADSP:*Server*" für AppleTalk oder "RPC:*Server*" für MultiProtocol verwenden, müssen Sie die Anwendung so ändern, dass eines der unterstützten Protokolle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f88a-112">If your application connection string specifically uses or loads one of these protocols, by either specifying NETWORK=DBMSRPCN for RPC, NETWORK=DBMSADSN for Appletalk, or NETWORK=DBMSVINN for Banyan VINES property, or by using an explicit prefix such as "spx:*server\instance*" for SPX, "bv:*server*" for Banyan VINES, "adsp:*server*" for AppleTalk, or "rpc:*server*" for multiprotocol, then you must modify your application to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="4f88a-113">Weitere Informationen finden Sie unter "Auswählen eines Netzwerkprotokolls" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="4f88a-113">For more information, see "Choosing a Network Protocol" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f88a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f88a-114">See Also</span></span>  
 <span data-ttu-id="4f88a-115">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4f88a-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4f88a-116">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="4f88a-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
