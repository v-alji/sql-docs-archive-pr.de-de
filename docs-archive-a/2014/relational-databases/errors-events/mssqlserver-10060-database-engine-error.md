---
title: MSSQLSERVER_10060 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10060"
helpviewer_keywords:
- 10060 (Database Engine error)
ms.assetid: 28c21277-cad8-406c-a955-07933a56982a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d634cfb06381fb916ef2e421e0677e76edb9ae02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722865"
---
# <a name="mssqlserver_10060"></a><span data-ttu-id="47896-102">MSSQLSERVER_10060</span><span class="sxs-lookup"><span data-stu-id="47896-102">MSSQLSERVER_10060</span></span>
    
## <a name="details"></a><span data-ttu-id="47896-103">Details</span><span class="sxs-lookup"><span data-stu-id="47896-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47896-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="47896-104">Product Name</span></span>|<span data-ttu-id="47896-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="47896-105">SQL Server</span></span>|  
|<span data-ttu-id="47896-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="47896-106">Event ID</span></span>|<span data-ttu-id="47896-107">10060</span><span class="sxs-lookup"><span data-stu-id="47896-107">10060</span></span>|  
|<span data-ttu-id="47896-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="47896-108">Event Source</span></span>|<span data-ttu-id="47896-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="47896-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="47896-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="47896-110">Component</span></span>|<span data-ttu-id="47896-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="47896-111">SQLEngine</span></span>|  
|<span data-ttu-id="47896-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="47896-112">Symbolic Name</span></span>||  
|<span data-ttu-id="47896-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="47896-113">Message Text</span></span>|<span data-ttu-id="47896-114">Fehler beim Herstellen einer Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="47896-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="47896-115">Beim Herstellen einer Verbindung mit SQL Server kann dieser Fehler durch den Umstand verursacht werden, dass die Standardeinstellungen von SQL Server keine Remoteverbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="47896-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="47896-116">(Anbieter: TCP-Anbieter, Fehler: 0 - Fehler beim Herstellen der Verbindung, weil die Gegenstelle nach einer bestimmten Zeitspanne nicht ordnungsgemäß reagiert hat, oder die hergestellte Verbindung konnte nicht aufrechterhalten werden, weil der verbundene Host nicht reagiert.) (Microsoft SQL Server, Fehler: 10060)</span><span class="sxs-lookup"><span data-stu-id="47896-116">(provider: TCP Provider, error: 0 - A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.) (Microsoft SQL Server, Error: 10060)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47896-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="47896-117">Explanation</span></span>  
 <span data-ttu-id="47896-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Client kann keine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="47896-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="47896-119">Dieser Fehler kann auftreten, weil entweder die Verbindung von der Firewall auf dem Server abgelehnt wurde oder der Server nicht so konfiguriert ist, dass er Remoteverbindungen annimmt.</span><span class="sxs-lookup"><span data-stu-id="47896-119">This error could occur because either the firewall on the server has refused the connection or the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47896-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="47896-120">User Action</span></span>  
 <span data-ttu-id="47896-121">Führen Sie zum Beheben dieses Fehlers eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="47896-121">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="47896-122">Stellen Sie sicher, dass Sie die Firewall auf dem Computer konfiguriert haben, sodass diese [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz Verbindungen annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="47896-122">Make sure that you have configured the firewall on the computer to allow this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
-   <span data-ttu-id="47896-123">Verwenden Sie das Tool [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager, um zuzulassen, dass in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remoteverbindungen angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="47896-123">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47896-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47896-124">See Also</span></span>  
 <span data-ttu-id="47896-125">[Konfigurieren einer Windows-Firewall für den Datenbank-Engine Zugriff](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="47896-125">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="47896-126">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="47896-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="47896-127">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="47896-127">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="47896-128">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="47896-128">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="47896-129">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="47896-129">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="47896-130">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="47896-130">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
