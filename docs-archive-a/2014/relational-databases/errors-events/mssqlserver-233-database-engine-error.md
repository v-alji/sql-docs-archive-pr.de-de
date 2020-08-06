---
title: MSSQLSERVER_233 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "233"
helpviewer_keywords:
- 233 (Database Engine error)
ms.assetid: 201665dc-7ac8-4c19-90d3-33354c5caa72
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c51fac7c0af16c520d7cf5538e512912e62cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698253"
---
# <a name="mssqlserver_233"></a><span data-ttu-id="7215f-102">MSSQLSERVER_233</span><span class="sxs-lookup"><span data-stu-id="7215f-102">MSSQLSERVER_233</span></span>
    
## <a name="details"></a><span data-ttu-id="7215f-103">Details</span><span class="sxs-lookup"><span data-stu-id="7215f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7215f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7215f-104">Product Name</span></span>|<span data-ttu-id="7215f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7215f-105">SQL Server</span></span>|  
|<span data-ttu-id="7215f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7215f-106">Event ID</span></span>|<span data-ttu-id="7215f-107">233</span><span class="sxs-lookup"><span data-stu-id="7215f-107">233</span></span>|  
|<span data-ttu-id="7215f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7215f-108">Event Source</span></span>|<span data-ttu-id="7215f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7215f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7215f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7215f-110">Component</span></span>|<span data-ttu-id="7215f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7215f-111">SQLEngine</span></span>|  
|<span data-ttu-id="7215f-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7215f-112">Symbolic Name</span></span>||  
|<span data-ttu-id="7215f-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7215f-113">Message Text</span></span>|<span data-ttu-id="7215f-114">Eine Verbindung mit dem Server wurde erfolgreich hergestellt, aber dann trat während des Anmeldevorgangs ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7215f-114">A connection was successfully established with the server, but then an error occurred during the login process.</span></span> <span data-ttu-id="7215f-115">(Anbieter: Shared Memory-Anbieter, Fehler: 0 - No process is on the other end of the pipe.) (0 – Kein Prozess ist am anderen Ende der Pipe.) (Microsoft SQL Server, Fehler: 233)</span><span class="sxs-lookup"><span data-stu-id="7215f-115">(provider: Shared Memory Provider, error: 0 - No process is on the other end of the pipe.) (Microsoft SQL Server, Error: 233)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7215f-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7215f-116">Explanation</span></span>  
 <span data-ttu-id="7215f-117">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Client kann keine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="7215f-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="7215f-118">Dieser Fehler ist möglicherweise darauf zurückzuführen, dass der Server nicht für die Annahme von Remoteverbindungen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="7215f-118">This error could occur because the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7215f-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7215f-119">User Action</span></span>  
 <span data-ttu-id="7215f-120">Verwenden Sie das Tool [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager, um zuzulassen, dass in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remoteverbindungen angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="7215f-120">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7215f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7215f-121">See Also</span></span>  
 <span data-ttu-id="7215f-122">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="7215f-122">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="7215f-123">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7215f-123">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="7215f-124">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="7215f-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="7215f-125">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="7215f-125">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
