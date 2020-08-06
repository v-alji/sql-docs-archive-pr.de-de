---
title: MSSQLSERVER_-1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "-1"
helpviewer_keywords:
- -1 (Database Engine error)
ms.assetid: bad25b91-eaed-46c0-a5b7-71117a32304c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 880212b1d2e9572bbb31535a5ba68b445c7e6f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719966"
---
# <a name="mssqlserver_-1"></a><span data-ttu-id="9e44c-102">MSSQLSERVER_-1</span><span class="sxs-lookup"><span data-stu-id="9e44c-102">MSSQLSERVER_-1</span></span>
    
## <a name="details"></a><span data-ttu-id="9e44c-103">Details</span><span class="sxs-lookup"><span data-stu-id="9e44c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e44c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="9e44c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="9e44c-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9e44c-105">Event ID</span></span>|<span data-ttu-id="9e44c-106">-1</span><span class="sxs-lookup"><span data-stu-id="9e44c-106">-1</span></span>|  
|<span data-ttu-id="9e44c-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="9e44c-107">Event Source</span></span>|<span data-ttu-id="9e44c-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9e44c-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9e44c-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="9e44c-109">Component</span></span>|<span data-ttu-id="9e44c-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9e44c-110">SQLEngine</span></span>|  
|<span data-ttu-id="9e44c-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="9e44c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="9e44c-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="9e44c-112">Message Text</span></span>|<span data-ttu-id="9e44c-113">Fehler beim Herstellen einer Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="9e44c-113">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="9e44c-114">Beim Herstellen der Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann dieser Fehler dadurch verursacht worden sein, dass die Standardeinstellungen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] keine Remoteverbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="9e44c-114">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this failure may be caused by the fact that under the default settings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow remote connections.</span></span> <span data-ttu-id="9e44c-115">(Anbieter: SQL-Netzwerkschnittstellen, Fehler: 28 - Server unterstützt das angeforderte Protokoll nicht) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Fehler: -1)</span><span class="sxs-lookup"><span data-stu-id="9e44c-115">(provider: SQL Network Interfaces, error: 28 - Server doesn't support requested protocol) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Error: -1)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e44c-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="9e44c-116">Explanation</span></span>  
 <span data-ttu-id="9e44c-117">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Client kann keine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="9e44c-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="9e44c-118">Dieser Fehler kann auf einen der folgenden Gründe zurückzuführen sein:</span><span class="sxs-lookup"><span data-stu-id="9e44c-118">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="9e44c-119">Ein angegebener [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanzenname ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9e44c-119">A specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name is not valid.</span></span>  
  
-   <span data-ttu-id="9e44c-120">Die TCP- oder Named Pipes-Protokolle sind nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9e44c-120">The TCP, or named pipes protocols are not enabled.</span></span>  
  
-   <span data-ttu-id="9e44c-121">Die Firewall auf dem Server hat die Verbindung abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="9e44c-121">The firewall on the server has refused the connection.</span></span>  
  
-   <span data-ttu-id="9e44c-122">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browserdienst (sqlbrowser) wurde nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="9e44c-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service (sqlbrowser) is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e44c-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="9e44c-123">User Action</span></span>  
 <span data-ttu-id="9e44c-124">Führen Sie zum Beheben dieses Fehlers eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9e44c-124">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="9e44c-125">Überprüfen Sie die Rechtschreibung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanznamens, der in der Verbindungszeichenfolge angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9e44c-125">Check the spelling of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name that is specified in the connection string.</span></span>  
  
-   <span data-ttu-id="9e44c-126">Verwenden Sie das Tool [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Configuration Manager, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu ermöglichen, Remoteverbindungen mithilfe von TCP oder Named Pipes zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="9e44c-126">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections over the TCP or named pipes protocols.</span></span>  
  
-   <span data-ttu-id="9e44c-127">Stellen Sie sicher, dass Sie die Firewall auf der Serverinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] so konfiguriert haben, dass Ports für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browserport (UDP 1434) geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="9e44c-127">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open ports for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser port (UDP 1434).</span></span>  
  
-   <span data-ttu-id="9e44c-128">Stellen Sie sicher, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browserdienst auf dem Server gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="9e44c-128">Make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is started on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e44c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e44c-129">See Also</span></span>  
 <span data-ttu-id="9e44c-130">[Konfigurieren einer Windows-Firewall für den Datenbank-Engine Zugriff](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="9e44c-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="9e44c-131">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="9e44c-131">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="9e44c-132">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="9e44c-132">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="9e44c-133">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9e44c-133">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="9e44c-134">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="9e44c-134">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="9e44c-135">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="9e44c-135">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
