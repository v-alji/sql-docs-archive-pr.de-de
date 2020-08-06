---
title: MSSQLSERVER_2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- 2 (Database Engine error)
ms.assetid: 567fb571-7cda-4ce8-a702-cdff2df5d419
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 87d19a24219fda79de2cad4c06af4f1936b37b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620926"
---
# <a name="mssqlserver_2"></a><span data-ttu-id="321c3-102">MSSQLSERVER_2</span><span class="sxs-lookup"><span data-stu-id="321c3-102">MSSQLSERVER_2</span></span>
    
## <a name="details"></a><span data-ttu-id="321c3-103">Details</span><span class="sxs-lookup"><span data-stu-id="321c3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="321c3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="321c3-104">Product Name</span></span>|<span data-ttu-id="321c3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="321c3-105">SQL Server</span></span>|  
|<span data-ttu-id="321c3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="321c3-106">Event ID</span></span>|<span data-ttu-id="321c3-107">2</span><span class="sxs-lookup"><span data-stu-id="321c3-107">2</span></span>|  
|<span data-ttu-id="321c3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="321c3-108">Event Source</span></span>|<span data-ttu-id="321c3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="321c3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="321c3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="321c3-110">Component</span></span>|<span data-ttu-id="321c3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="321c3-111">SQLEngine</span></span>|  
|<span data-ttu-id="321c3-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="321c3-112">Symbolic Name</span></span>||  
|<span data-ttu-id="321c3-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="321c3-113">Message Text</span></span>|<span data-ttu-id="321c3-114">Fehler beim Herstellen einer Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="321c3-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="321c3-115">Beim Herstellen einer Verbindung mit SQL Server kann dieser Fehler durch den Umstand verursacht werden, dass die Standardeinstellungen von SQL Server keine Remoteverbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="321c3-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="321c3-116">(Anbieter: Named Pipes-Anbieter, Fehler: 40 - Es konnte keine Verbindung zu SQL Server hergestellt werden) (.Net SqlClient-Datenanbieter)</span><span class="sxs-lookup"><span data-stu-id="321c3-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="321c3-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="321c3-117">Explanation</span></span>  
 <span data-ttu-id="321c3-118">Keine Antwort von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf die Clientanforderung, da der Server wahrscheinlich nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="321c3-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] did not respond to the client request because the server is probably not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="321c3-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="321c3-119">User Action</span></span>  
 <span data-ttu-id="321c3-120">Stellen Sie sicher, dass der Server gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="321c3-120">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321c3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="321c3-121">See Also</span></span>  
 <span data-ttu-id="321c3-122">[Verwalten der Datenbank-Engine-Dienste](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="321c3-122">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="321c3-123">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="321c3-123">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="321c3-124">[Netzwerkprotokolle und Netzwerk Bibliotheken](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="321c3-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="321c3-125">[Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="321c3-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="321c3-126">[Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="321c3-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="321c3-127">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="321c3-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
