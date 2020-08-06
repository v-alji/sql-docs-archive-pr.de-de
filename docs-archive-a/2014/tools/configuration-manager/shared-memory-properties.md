---
title: Shared Memory-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
ms.assetid: dc1704da-eacd-4d26-b529-c996f958ca4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6275215afdb6de3aa134dbffe74aa22b9e7b6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621765"
---
# <a name="shared-memory-properties"></a><span data-ttu-id="e9c08-102">Shared Memory-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e9c08-102">Shared Memory Properties</span></span>
  <span data-ttu-id="e9c08-103">Verwenden Sie die Seite **Protokoll**des Dialogfeldes **Eigenschaften von Shared Memory** , um das Shared Memory-Protokoll zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9c08-103">Use the **Protocol**page on the **Shared Memory Properties** dialog box to enable or disable the shared memory protocol.</span></span> <span data-ttu-id="e9c08-104">Shared Memory ist das am einfachsten zu verwendende Protokoll. Es weist keine konfigurierbaren Einstellungen auf.</span><span class="sxs-lookup"><span data-stu-id="e9c08-104">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="e9c08-105">Da Clients, die das Shared Memory-Protokoll verwenden, nur eine Verbindung mit einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz herstellen können, die auf demselben Computer ausgeführt wird, ist dieses Protokoll bei den meisten Datenbankaktivitäten nicht hilfreich.</span><span class="sxs-lookup"><span data-stu-id="e9c08-105">Because clients using the shared memory protocol can only connect to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="e9c08-106">Verwenden Sie das Shared Memory-Protokoll zur Problembehandlung, wenn Sie vermuten, dass die anderen Protokolle nicht ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e9c08-106">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e9c08-107">muss neu gestartet werden, um das Protokoll zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9c08-107">must be restarted to enable or disable the protocol.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e9c08-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e9c08-108">Options</span></span>  
 <span data-ttu-id="e9c08-109">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="e9c08-109">**Enabled**</span></span>  
 <span data-ttu-id="e9c08-110">Mögliche Werte sind **Yes** und **No**.</span><span class="sxs-lookup"><span data-stu-id="e9c08-110">Possible values are **Yes** and **No**.</span></span> <span data-ttu-id="e9c08-111">Das Shared Memory-Protokoll ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e9c08-111">The shared memory protocol is enabled by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c08-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9c08-112">See Also</span></span>  
 <span data-ttu-id="e9c08-113">[Auswählen eines Netzwerkprotokolls](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="e9c08-113">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="e9c08-114">Erstellen einer gültigen Verbindungszeichenfolge mithilfe des Shared Memory-Protokolls</span><span class="sxs-lookup"><span data-stu-id="e9c08-114">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
  
