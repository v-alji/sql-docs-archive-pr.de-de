---
title: Bidirektionale Transaktionsreplikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- bidirectional replication
- transactional replication, bidirectional replication
- bidirectional transactional replication
ms.assetid: 98772e95-67ed-4010-8108-5113dbe709ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57b18dde2e7134e0ba9eb6a9b2e8f5357d171a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618635"
---
# <a name="bidirectional-transactional-replication"></a><span data-ttu-id="28c65-102">Bidirektionale Transaktionsreplikation</span><span class="sxs-lookup"><span data-stu-id="28c65-102">Bidirectional Transactional Replication</span></span>
  <span data-ttu-id="28c65-103">Die bidirektionale Transaktionsreplikation stellt eine spezielle Transaktionsreplikationstopologie dar, über die zwei Server Änderungen austauschen können: Jeder Server veröffentlicht Daten und abonniert dann eine Veröffentlichung mit denselben Daten vom anderen Server.</span><span class="sxs-lookup"><span data-stu-id="28c65-103">Bidirectional transactional replication is a specific transactional replication topology that allows two servers to exchange changes with each other: each server publishes data and then subscribes to a publication with the same data from the other server.</span></span> <span data-ttu-id="28c65-104">Der- **@loopback_detection** Parameter von [sp_addsubscription &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) auf true festgelegt ist, um sicherzustellen, dass Änderungen nur an den Abonnenten gesendet werden und nicht dazu führen, dass die Änderung zurück an den Verleger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="28c65-104">The **@loopback_detection** parameter of [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) is set to TRUE to ensure that changes are only sent to the Subscriber and do not result in the change being sent back to the Publisher.</span></span>  
  
 <span data-ttu-id="28c65-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] und höheren Versionen wird diese Topologie auch von der Peer-zu-Peer-Transaktionsreplikation unterstützt, doch kann die bidirektionale Replikation zu einer höheren Leistung führen.</span><span class="sxs-lookup"><span data-stu-id="28c65-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, this topology is also supported by peer-to-peer transactional replication, but bidirectional replication can provide improved performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c65-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28c65-106">See Also</span></span>  
 [<span data-ttu-id="28c65-107">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="28c65-107">Peer-to-Peer Transactional Replication</span></span>](peer-to-peer-transactional-replication.md)  
  
  
