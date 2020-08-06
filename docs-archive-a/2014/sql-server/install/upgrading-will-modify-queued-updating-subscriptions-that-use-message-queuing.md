---
title: Beim Upgrade werden Abonnements Message Queuing mit verzögertem Update über eine Warteschlange geändert. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication]
- MSMQ [SQL Server replication]
- queues [SQL Server replication]
- queued updating subscriptions [SQL Server replication]
ms.assetid: 97944de3-fbad-4db1-939a-dcd550bf5893
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d44cbad43d75634cbf8660110cc879522265c54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726449"
---
# <a name="upgrading-will-modify-queued-updating-subscriptions-that-use-message-queuing"></a><span data-ttu-id="f88e2-102">Das Upgrade ändert Abonnements mit verzögertem Update über eine Warteschlange, die Message Queuing verwenden</span><span class="sxs-lookup"><span data-stu-id="f88e2-102">Upgrading will modify queued updating subscriptions that use Message Queuing</span></span>
  <span data-ttu-id="f88e2-103">Der Upgrade Advisor hat erkannt, dass möglicherweise mindestens ein Abonnement mit verzögertem Update über eine Warteschlange vorhanden ist, das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (MSMQ) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f88e2-103">Upgrade Advisor detected that you might have one or more queued updating subscriptions that use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="f88e2-104">Die Replikation unterstützt kein Message Queuing mehr. Deshalb werden die Abonnements so geändert, dass sie eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Warteschlange verwenden.</span><span class="sxs-lookup"><span data-stu-id="f88e2-104">Replication no longer supports Message Queuing; therefore, the subscriptions will be modified to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span>  
  
 <span data-ttu-id="f88e2-105">Es ist nur der Wert **SQL** zulässig.</span><span class="sxs-lookup"><span data-stu-id="f88e2-105">Only a value of **sql** is allowed.</span></span> <span data-ttu-id="f88e2-106">Vorhandene Veröffentlichungen, für die Message Queuing verwendet wird, werden während des Upgrades geändert, um eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Warteschlange zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f88e2-106">Existing publications that use Message Queuing are modified during upgrade to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="f88e2-107">Wenn Sie Anwendungen verwenden, die auf dem verzögerten Update über Message Queuing basieren, müssen diese Anwendungen für eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Warteschlange umgeschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f88e2-107">If you have applications that depend on queued updating using Message Queuing, these applications will have to be rewritten to accommodate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="f88e2-108">Weitere Informationen über Abonnements mit verzögertem Update über eine Warteschlange finden unter "Aktualisierbare Abonnements für die Transaktionsreplikation" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="f88e2-108">For more information about queued updating subscriptions, see "Updatable Subscriptions for Transactional Replication" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="f88e2-109">Beim Upgrade werden die vorhandenen Message Queuing-Abonnementwarteschlangen entfernt, wenn der Message Queuing-Dienst ausgeführt wird, während [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f88e2-109">Upgrade will remove the existing Message Queuing subscription queues if the Message Queuing service is running while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being upgraded.</span></span>  
  
 <span data-ttu-id="f88e2-110">Wenn der Message Queuing-Dienst nicht ausgeführt wird, entfernen Sie alle Warteschlangen manuell, nachdem das Upgrade abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="f88e2-110">If the Message Queuing service is not running, remove the queues manually after upgrade is complete.</span></span> <span data-ttu-id="f88e2-111">Weitere Informationen darüber, wie Warteschlangen entfernt werden, finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f88e2-111">For more information about how to remove queues, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88e2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f88e2-112">See Also</span></span>  
 [<span data-ttu-id="f88e2-113">Probleme beim Replikationsupgrade</span><span class="sxs-lookup"><span data-stu-id="f88e2-113">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
