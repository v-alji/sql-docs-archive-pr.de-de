---
title: MSSQLSERVER_10061 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c866bd8dce01f65036f1d508a94252a97613424
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719957"
---
# <a name="mssqlserver_10061"></a><span data-ttu-id="f9b98-102">MSSQLSERVER_10061</span><span class="sxs-lookup"><span data-stu-id="f9b98-102">MSSQLSERVER_10061</span></span>
    
## <a name="details"></a><span data-ttu-id="f9b98-103">Details</span><span class="sxs-lookup"><span data-stu-id="f9b98-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9b98-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f9b98-104">Product Name</span></span>|<span data-ttu-id="f9b98-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9b98-105">SQL Server</span></span>|  
|<span data-ttu-id="f9b98-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f9b98-106">Event ID</span></span>|<span data-ttu-id="f9b98-107">10061</span><span class="sxs-lookup"><span data-stu-id="f9b98-107">10061</span></span>|  
|<span data-ttu-id="f9b98-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f9b98-108">Event Source</span></span>|<span data-ttu-id="f9b98-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f9b98-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f9b98-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f9b98-110">Component</span></span>|<span data-ttu-id="f9b98-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f9b98-111">SQLEngine</span></span>|  
|<span data-ttu-id="f9b98-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f9b98-112">Symbolic Name</span></span>||  
|<span data-ttu-id="f9b98-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f9b98-113">Message Text</span></span>|<span data-ttu-id="f9b98-114">Fehler beim Herstellen einer Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="f9b98-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="f9b98-115">Beim Herstellen einer Verbindung mit SQL Server kann dieser Fehler durch den Umstand verursacht werden, dass die Standardeinstellungen von SQL Server keine Remoteverbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="f9b98-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="f9b98-116">(Anbieter: TCP-Anbieter, Fehler: 0 - No connection could be made because the target machine actively refused it. (Es konnte keine Verbindung hergestellt werden, da der Zielcomputer die Verbindung verweigert.)) (Microsoft SQL Server, Fehler: 10061)</span><span class="sxs-lookup"><span data-stu-id="f9b98-116">(provider: TCP Provider, error: 0 - No connection could be made because the target machine actively refused it.) (Microsoft SQL Server, Error: 10061)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f9b98-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f9b98-117">Explanation</span></span>  
 <span data-ttu-id="f9b98-118">Der Server hat nicht auf die Clientanforderung reagiert.</span><span class="sxs-lookup"><span data-stu-id="f9b98-118">The server did not respond to the client request.</span></span> <span data-ttu-id="f9b98-119">Dieser Fehler ist möglicherweise darauf zurückzuführen, dass der Server nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f9b98-119">This error could occur because the server is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9b98-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f9b98-120">User Action</span></span>  
 <span data-ttu-id="f9b98-121">Stellen Sie sicher, dass der Server gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f9b98-121">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b98-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9b98-122">See Also</span></span>  
 <span data-ttu-id="f9b98-123">[Verwalten der Datenbank-Engine-Dienste](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="f9b98-123">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="f9b98-124">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="f9b98-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="f9b98-125">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="f9b98-125">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="f9b98-126">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f9b98-126">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="f9b98-127">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="f9b98-127">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="f9b98-128">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="f9b98-128">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
