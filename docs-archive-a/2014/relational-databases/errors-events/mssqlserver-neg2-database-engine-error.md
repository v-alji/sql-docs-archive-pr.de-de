---
title: MSSQLSERVER_-2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d39b4a11387a60056bba3f87adffcb2653b60f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701222"
---
# <a name="mssqlserver_-2"></a><span data-ttu-id="d74fb-102">MSSQLSERVER_-2</span><span class="sxs-lookup"><span data-stu-id="d74fb-102">MSSQLSERVER_-2</span></span>
    
## <a name="details"></a><span data-ttu-id="d74fb-103">Details</span><span class="sxs-lookup"><span data-stu-id="d74fb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d74fb-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d74fb-104">Product Name</span></span>|<span data-ttu-id="d74fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d74fb-105">SQL Server</span></span>|  
|<span data-ttu-id="d74fb-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d74fb-106">Event ID</span></span>|<span data-ttu-id="d74fb-107">-2</span><span class="sxs-lookup"><span data-stu-id="d74fb-107">-2</span></span>|  
|<span data-ttu-id="d74fb-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d74fb-108">Event Source</span></span>|<span data-ttu-id="d74fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d74fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d74fb-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d74fb-110">Component</span></span>|<span data-ttu-id="d74fb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d74fb-111">SQLEngine</span></span>|  
|<span data-ttu-id="d74fb-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d74fb-112">Symbolic Name</span></span>||  
|<span data-ttu-id="d74fb-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d74fb-113">Message Text</span></span>|<span data-ttu-id="d74fb-114">Timeout ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="d74fb-114">Timeout expired.</span></span>  <span data-ttu-id="d74fb-115">Das Timeout ist vor dem Beenden des Vorgangs eingetreten, oder der Server reagiert nicht.</span><span class="sxs-lookup"><span data-stu-id="d74fb-115">The timeout period elapsed prior to completion of the operation or the server is not responding.</span></span> <span data-ttu-id="d74fb-116">(Microsoft SQL Server, Fehler: -2)</span><span class="sxs-lookup"><span data-stu-id="d74fb-116">(Microsoft SQL Server, Error: -2)</span></span>|   
  
## <a name="explanation"></a><span data-ttu-id="d74fb-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d74fb-117">Explanation</span></span>  
 <span data-ttu-id="d74fb-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Client kann keine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="d74fb-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="d74fb-119">Dieser Fehler ist möglicherweise darauf zurückzuführen, dass die Verbindung von der Firewall auf dem Server abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="d74fb-119">This error could occur because the firewall on the server has refused the connection.</span></span> 
  
## <a name="user-action"></a><span data-ttu-id="d74fb-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d74fb-120">User Action</span></span>  
 <span data-ttu-id="d74fb-121">Stellen Sie sicher, dass Sie die Firewall auf der Serverinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] so konfiguriert haben, dass sie Verbindungen annimmt.</span><span class="sxs-lookup"><span data-stu-id="d74fb-121">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74fb-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d74fb-122">See Also</span></span>  
 <span data-ttu-id="d74fb-123">[Konfigurieren der Windows-Firewall für den SQL Server Zugriff](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span><span class="sxs-lookup"><span data-stu-id="d74fb-123">[Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span></span>  
 <span data-ttu-id="d74fb-124">[Konfigurieren einer Windows-Firewall für den Datenbank-Engine Zugriff](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="d74fb-124">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="d74fb-125">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="d74fb-125">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="d74fb-126">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="d74fb-126">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="d74fb-127">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d74fb-127">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="d74fb-128">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="d74fb-128">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="d74fb-129">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="d74fb-129">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
