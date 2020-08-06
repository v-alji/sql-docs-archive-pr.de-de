---
title: MSSQLSERVER_53 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "53"
helpviewer_keywords:
- 53 (Database Engine error)
ms.assetid: 1234f5a2-b3d1-425a-b29f-480fa792305f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 85fda292fb956047f51b9c7cd1d229ac0afce6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618728"
---
# <a name="mssqlserver_53"></a><span data-ttu-id="6e840-102">MSSQLSERVER_53</span><span class="sxs-lookup"><span data-stu-id="6e840-102">MSSQLSERVER_53</span></span>
    
## <a name="details"></a><span data-ttu-id="6e840-103">Details</span><span class="sxs-lookup"><span data-stu-id="6e840-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e840-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6e840-104">Product Name</span></span>|<span data-ttu-id="6e840-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e840-105">SQL Server</span></span>|  
|<span data-ttu-id="6e840-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6e840-106">Event ID</span></span>|<span data-ttu-id="6e840-107">53</span><span class="sxs-lookup"><span data-stu-id="6e840-107">53</span></span>|  
|<span data-ttu-id="6e840-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6e840-108">Event Source</span></span>|<span data-ttu-id="6e840-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6e840-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6e840-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6e840-110">Component</span></span>|<span data-ttu-id="6e840-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6e840-111">SQLEngine</span></span>|  
|<span data-ttu-id="6e840-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6e840-112">Symbolic Name</span></span>||  
|<span data-ttu-id="6e840-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6e840-113">Message Text</span></span>|<span data-ttu-id="6e840-114">Fehler beim Herstellen einer Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="6e840-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="6e840-115">Beim Herstellen einer Verbindung mit SQL Server kann dieser Fehler durch den Umstand verursacht werden, dass die Standardeinstellungen von SQL Server keine Remoteverbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="6e840-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="6e840-116">(Anbieter: Named Pipes-Anbieter, Fehler: 40 - Es konnte keine Verbindung zu SQL Server hergestellt werden) (.Net SqlClient-Datenanbieter)</span><span class="sxs-lookup"><span data-stu-id="6e840-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6e840-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6e840-117">Explanation</span></span>  
 <span data-ttu-id="6e840-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Client kann keine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="6e840-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="6e840-119">Dieser Fehler ist möglicherweise darauf zurückzuführen, dass entweder der Name des Servers durch den Client nicht aufgelöst werden kann oder der Name des Servers falsch ist.</span><span class="sxs-lookup"><span data-stu-id="6e840-119">This error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6e840-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6e840-120">User Action</span></span>  
 <span data-ttu-id="6e840-121">Stellen Sie sicher, dass Sie den richtigen Servernamen auf dem Client eingegeben haben und dass Sie den Namen des Servers auf dem Client auflösen können.</span><span class="sxs-lookup"><span data-stu-id="6e840-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="6e840-122">Zum Überprüfen der TCP/IP-Namensauflösung können Sie den **ping**-Befehl im Windows-Betriebssystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e840-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e840-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e840-123">See Also</span></span>  
 <span data-ttu-id="6e840-124">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="6e840-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="6e840-125">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6e840-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="6e840-126">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="6e840-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="6e840-127">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="6e840-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
