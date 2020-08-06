---
title: Konfiguration von SQL Native Client 11,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client configuration [SQL Server], SQL Server Native Client
ms.assetid: e73143e9-5e7b-4d0a-8827-ab900efdcb35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 183dd2d161b1bf0b13140a607167b81dab086fdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609617"
---
# <a name="sql-native-client-110-configuration"></a><span data-ttu-id="e07d7-102">SQL Native Client 11.0-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e07d7-102">SQL Native Client 11.0 Configuration</span></span>
  <span data-ttu-id="e07d7-103">Dieser Abschnitt enthält die F1-Hilfethemen für die Dialogfelder zur **SQL Server Native Client-Konfiguration** in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e07d7-103">This section contains the F1 Help topics for the **SQL Server Native Client Configuration** dialogs in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e07d7-104">Bei Native Client handelt es sich um die Netzwerkbibliothek, die von Clientcomputern zum Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet wird (ab [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="e07d7-104">Native Client is the network library that client computers use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], starting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e07d7-105">Die in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Konfiguration konfigurierten Einstellungen werden auf dem Computer verwendet, auf dem das Clientprogramm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e07d7-105">The settings configured in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Configuration, are used on the computer running the client program.</span></span> <span data-ttu-id="e07d7-106">Bei der Konfiguration auf dem Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]betreffen diese Einstellungen nur diejenigen Clientprogramme, die auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e07d7-106">When configured on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they affect only those client programs running on the server.</span></span>  
  
 <span data-ttu-id="e07d7-107">Diese Einstellungen wirken sich nicht auf Clients aus, die eine Verbindung mit vorherigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]herstellen, außer diese verwenden Clienttools ab [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], z. B. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e07d7-107">These settings do not affect clients connecting to previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], unless they are using the client tools starting with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e07d7-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e07d7-108">In this Section</span></span>  
  
-   [<span data-ttu-id="e07d7-109">SQL Server Native Client-Konfigurationseigenschaften &#40;Registerkarte „Flags“&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-109">SQL Server Native Client Configuration Properties &#40;Flags Tab&#41;</span></span>](../../../2014/tools/configuration-manager/sql-server-native-client-configuration-properties-flags-tab.md)  
  
-   [<span data-ttu-id="e07d7-110">Clientprotokolle &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-110">Client Protocols &#40;SQL Server Configuration Manager&#41;</span></span>](../../relational-databases/sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="e07d7-111">Eigenschaften der Clientprotokolle &#40;Registerkarte „Reihenfolge“&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-111">Client Protocols Properties &#40;Order Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-properties-order-tab.md)  
  
    -   [<span data-ttu-id="e07d7-112">Clientprotokolle - Shared Memory-Eigenschaften &#40;Registerkarte „Protokoll“&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-112">Client Protocols - Shared Memory Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-shared-memory-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="e07d7-113">Client Protokolle-TCP und IP-Eigenschaften &#40;Registerkarte "Protokoll"&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-113">Client Protocols - TCP and IP Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-tcp-and-ip-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="e07d7-114">Clientprotokolle - Named Pipes-Eigenschaften &#40;Registerkarte „Protokoll“&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-114">Client Protocols - Named Pipes Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-named-pipes-properties-protocol-tab.md)  
  
-   [<span data-ttu-id="e07d7-115">Aliase &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-115">Aliases &#40;SQL Server Configuration Manager&#41;</span></span>](../../../2014/tools/configuration-manager/aliases-sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="e07d7-116">Neuer Alias &#40;Registerkarte „Alias“&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-116">New Alias &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)  
  
    -   [<span data-ttu-id="e07d7-117">&#60;Alias&#62;-Eigenschaften &#40;Registerkarte „Alias“&#41;</span><span class="sxs-lookup"><span data-stu-id="e07d7-117">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
    -   [<span data-ttu-id="e07d7-118">Erstellen einer gültigen Verbindungszeichenfolge mithilfe des Shared Memory-Protokolls</span><span class="sxs-lookup"><span data-stu-id="e07d7-118">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
    -   [<span data-ttu-id="e07d7-119">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP</span><span class="sxs-lookup"><span data-stu-id="e07d7-119">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
    -   [<span data-ttu-id="e07d7-120">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes</span><span class="sxs-lookup"><span data-stu-id="e07d7-120">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
