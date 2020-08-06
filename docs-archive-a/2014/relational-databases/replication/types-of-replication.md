---
title: Replikationstypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], types
ms.assetid: c1655e8d-d14c-455a-a7f9-9d2f43e88ab4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5576331004eca44bc32dbde8f430284f75e6eb70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717803"
---
# <a name="types-of-replication"></a><span data-ttu-id="78a45-102">Replikationstypen</span><span class="sxs-lookup"><span data-stu-id="78a45-102">Types of Replication</span></span>
  <span data-ttu-id="78a45-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stehen für die Verwendung in verteilten Anwendungen die folgenden Replikationstypen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="78a45-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of replication for use in distributed applications:</span></span>  
  
-   <span data-ttu-id="78a45-104">Transaktionsreplikation.</span><span class="sxs-lookup"><span data-stu-id="78a45-104">Transactional replication.</span></span> <span data-ttu-id="78a45-105">Weitere Informationen finden Sie unter [Transaktionsreplikation](transactional/transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="78a45-105">For more information, see [Transactional Replication](transactional/transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="78a45-106">Mergereplikation.</span><span class="sxs-lookup"><span data-stu-id="78a45-106">Merge replication.</span></span> <span data-ttu-id="78a45-107">Weitere Informationen finden Sie unter [Mergereplikation](merge/merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="78a45-107">For more information, see [Merge Replication](merge/merge-replication.md).</span></span>  
  
-   <span data-ttu-id="78a45-108">Momentaufnahmereplikation.</span><span class="sxs-lookup"><span data-stu-id="78a45-108">Snapshot replication.</span></span> <span data-ttu-id="78a45-109">Weitere Informationen finden Sie unter [Momentaufnahmereplikation](snapshot-replication.md).</span><span class="sxs-lookup"><span data-stu-id="78a45-109">For more information, see [Snapshot Replication](snapshot-replication.md).</span></span>  
  
 <span data-ttu-id="78a45-110">Für welchen Replikationstyp Sie sich bei Ihrer konkreten Anwendung entscheiden sollten, hängt von vielen Faktoren ab. So müssen z. B. die physische Replikationsumgebung, die Art und Menge der zu replizierenden Daten und die Frage berücksichtigt werden, ob die Daten auf dem Abonnenten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="78a45-110">The type of replication you choose for an application depends on many factors, including the physical replication environment, the type and quantity of data to be replicated, and whether the data is updated at the Subscriber.</span></span> <span data-ttu-id="78a45-111">Bei der physischen Umgebung sind die Anzahl und der Standort der Computer in Betracht zu ziehen, die in die Replikation mit einbezogen werden sollen. Außerdem muss berücksichtigt werden, ob es sich bei diesen Computern um Clients (Arbeitsstationen, Laptops bzw. Handhelds) oder Server handelt.</span><span class="sxs-lookup"><span data-stu-id="78a45-111">The physical environment includes the number and location of computers involved in replication and whether these computers are clients (workstations, laptops, or handheld devices) or servers.</span></span>  
  
 <span data-ttu-id="78a45-112">Unabhängig vom jeweiligen Typ beginnen alle Replikationen typischerweise mit einer Erstsynchronisierung der veröffentlichten Objekte auf dem Verleger und den Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="78a45-112">Each type of replication typically begins with an initial synchronization of the published objects between the Publisher and Subscribers.</span></span> <span data-ttu-id="78a45-113">Diese Erstsynchronisierung kann durch eine Replikation mit einer *Momentaufnahme*ausgeführt werden. Die Momentaufnahme ist eine Kopie aller in einer Veröffentlichung enthaltenen Objekte und Daten.</span><span class="sxs-lookup"><span data-stu-id="78a45-113">This initial synchronization can be performed by replication with a *snapshot*, which is a copy of all of the objects and data specified by a publication.</span></span> <span data-ttu-id="78a45-114">Diese Momentaufnahme wird an die Abonnenten weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="78a45-114">After the snapshot is created, it is delivered to the Subscribers.</span></span> <span data-ttu-id="78a45-115">Bei einigen Anwendungen ist lediglich eine Momentaufnahmereplikation erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a45-115">For some applications, snapshot replication is all that is required.</span></span> <span data-ttu-id="78a45-116">Bei anderen Anwendungstypen hingegen ist es wichtig, dass nachfolgende Datenänderungen inkrementell an den Abonnenten weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="78a45-116">For other types of applications, it is important that subsequent data changes flow to the Subscriber incrementally over time.</span></span> <span data-ttu-id="78a45-117">Es gibt auch Anwendungen, bei denen Änderungen vom Abonnenten zurück an den Verleger fließen müssen.</span><span class="sxs-lookup"><span data-stu-id="78a45-117">Some applications also require that changes flow from the Subscriber back to the Publisher.</span></span> <span data-ttu-id="78a45-118">Für solche Anwendungstypen bieten die Transaktionsreplikation und die Mergereplikation entsprechende Optionen.</span><span class="sxs-lookup"><span data-stu-id="78a45-118">Transactional replication and merge replication provide options for these types of applications.</span></span>  
  
 <span data-ttu-id="78a45-119">Datenänderungen werden bei der Momentaufnahmereplikation nicht nachverfolgt, sodass jedes Mal, wenn eine Momentaufnahme angewendet wird, die vorhandenen Daten komplett überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="78a45-119">Data changes are not tracked for snapshot replication; each time a snapshot is applied, it completely overwrites the existing data.</span></span> <span data-ttu-id="78a45-120">Bei der Transaktionsreplikation werden Änderungen im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Transaktionsprotokoll nachverfolgt. Bei der Mergereplikation erfolgt die Änderungsnachverfolgung mithilfe von Triggern und Metadatentabellen.</span><span class="sxs-lookup"><span data-stu-id="78a45-120">Transactional replication tracks changes through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, and merge replication tracks changes through triggers and metadata tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a45-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78a45-121">See Also</span></span>  
 [<span data-ttu-id="78a45-122">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="78a45-122">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
