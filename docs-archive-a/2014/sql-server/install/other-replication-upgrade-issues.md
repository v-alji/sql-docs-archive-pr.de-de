---
title: Andere Replikations Upgradeprobleme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system tables [SQL Server], replication
- passwords [SQL Server replication]
- versions [SQL Server replication]
- connections [SQL Server replication]
- scripts [SQL Server replication]
- ActiveX controls [SQL Server replication]
ms.assetid: 8a5e74be-4992-4f17-b20c-c3dce8f49329
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e8ce3f35ead9d3322c636462f682ef391703cfe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621322"
---
# <a name="other-replication-upgrade-issues"></a><span data-ttu-id="ff221-102">Weitere Probleme beim Replikationsupgrade</span><span class="sxs-lookup"><span data-stu-id="ff221-102">Other Replication Upgrade Issues</span></span>
  <span data-ttu-id="ff221-103">In diesem Thema werden einige Upgradeprobleme erläutert, die nicht von Upgrade Advisor gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="ff221-103">This topic covers a number of upgrade issues that are not reported by Upgrade Advisor.</span></span>  
  
## <a name="versions-supported"></a><span data-ttu-id="ff221-104">Unterstützte Versionen</span><span class="sxs-lookup"><span data-stu-id="ff221-104">Versions Supported</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="ff221-105">unterstützt das Aktualisieren replizierter Datenbanken aus früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff221-105">supports upgrading replicated databases from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ff221-106">Während des Upgrades eines Knotens müssen die auf anderen Knoten ausgeführten Aktivitäten nicht beendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff221-106">You do not have to stop activity at other nodes while a node is being upgraded.</span></span> <span data-ttu-id="ff221-107">Stellen Sie sicher, dass die Regeln, die im Hinblick auf die in einer Topologie unterstützten Versionen gelten, eingehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ff221-107">Ensure that you adhere to the rules regarding which versions are supported in a topology.</span></span>  
  
 <span data-ttu-id="ff221-108">Bei einer Replikation mit unterschiedlichen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist der verfügbare Funktionsumfang häufig auf die Funktionen der frühesten verwendeten Version begrenzt.</span><span class="sxs-lookup"><span data-stu-id="ff221-108">When you replicate between or among different versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you are usually limited to the functionality of the earliest version that is being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff221-109">Da das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Speicherformat für Datenträger in 64-Bit- und in 32-Bit-Umgebungen übereinstimmt, können für eine Replikationstopologie Serverinstanzen, die in einer 32-Bit-Umgebung ausgeführt werden, mit Serverinstanzen, die in einer 64-Bit-Umgebung ausgeführt werden, kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="ff221-109">Because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on-disk storage format is the same in the 64-bit and 32-bit environments, a replication topology can combine server instances that run in a 32-bit environment and server instances that run in a 64-bit environment.</span></span>  
  
 <span data-ttu-id="ff221-110">Bei allen Replikationstypen darf auf dem Verteiler keine frühere Version ausgeführt werden als auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="ff221-110">For all types of replication, the Distributor version must be no earlier than the Publisher version.</span></span> <span data-ttu-id="ff221-111">(Häufig handelt es sich bei Verteiler und Verleger um dieselbe Instanz.)</span><span class="sxs-lookup"><span data-stu-id="ff221-111">(Frequently, the Distributor is the same instance as the Publisher.)</span></span>  
  
 <span data-ttu-id="ff221-112">Bei einer Transaktionsreplikation kann auf dem Abonnenten einer Transaktionsveröffentlichung eine Version verwendet werden, die sich um höchstens zwei Versionen von der Verlegerversion unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="ff221-112">For transactional replication, a Subscriber to a transactional publication can be any version within two versions of the Publisher version.</span></span>  
  
 <span data-ttu-id="ff221-113">Bei einer Mergereplikation ist auf dem Abonnenten einer Mergeveröffentlichung jede Version zulässig, die nicht höher als die des Verlegers ist.</span><span class="sxs-lookup"><span data-stu-id="ff221-113">For merge replication, a Subscriber to a merge publication can be any version no later than the Publisher version.</span></span>  
  
## <a name="merge-replication-batches-changes"></a><span data-ttu-id="ff221-114">Batchänderungen bei der Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="ff221-114">Merge Replication Batches Changes</span></span>  
 <span data-ttu-id="ff221-115">Vom Merge-Agent vorgenommene Änderungen werden zur Leistungsverbesserung in Batches gesammelt. Daher können in einer einzelnen Anweisung mehrere Zeilen eingefügt, aktualisiert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ff221-115">Changes that are made by the Merge Agent are batched to improve performance; therefore, more than one row can be inserted, updated, or deleted within a single statement.</span></span> <span data-ttu-id="ff221-116">Wenn veröffentlichte Tabellen in den Veröffentlichungs- und Abonnementdatenbanken Trigger enthalten, müssen diese mehrzeilige Einfüge-, Update- und Löschvorgänge verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="ff221-116">If any published tables in the publication or subscription databases have triggers, ensure that the triggers can handle multirow inserts, updates, and deletes.</span></span> <span data-ttu-id="ff221-117">Weitere Informationen finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation unter "Trigger bei mehrzeiligen Operationen".</span><span class="sxs-lookup"><span data-stu-id="ff221-117">For more information, see "Multirow Considerations for DML Triggers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="activex-control-changes"></a><span data-ttu-id="ff221-118">Änderungen von ActiveX-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ff221-118">ActiveX Control Changes</span></span>  
 <span data-ttu-id="ff221-119">Die folgenden Änderungen wurden für ActiveX-Replikationssteuerelemente vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="ff221-119">The following changes have been made for replication ActiveX controls:</span></span>  
  
-   <span data-ttu-id="ff221-120">Alle ActiveX-Steuerelemente sind als unsicher für die Skripterstellung und für die Initialisierung gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ff221-120">All ActiveX controls are marked as unsafe for scripting and initialization.</span></span>  
  
-   <span data-ttu-id="ff221-121">Das ActiveX-Steuerelement für Momentaufnahmen wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="ff221-121">The Snapshot ActiveX control has been dropped.</span></span> <span data-ttu-id="ff221-122">Sie können Momentaufnahmen mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder programmgesteuert mit gespeicherten Replikationsprozeduren erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ff221-122">You can create and manage snapshots by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or programmatically by using replication stored procedures.</span></span> <span data-ttu-id="ff221-123">Weitere Informationen finden Sie in der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Onlinedokumentation unter "Vorgehensweise: Erstellen und Anwenden der Anfangsmomentaufnahme ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)])" und unter "Vorgehensweise: Erstellen der Anfangsmomentaufnahme (Replikationsprogrammierung mit Transact-SQL)".</span><span class="sxs-lookup"><span data-stu-id="ff221-123">For more information, see the topics "How to: Create and Apply the Initial Snapshot ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" and "How to: Create the Initial Snapshot (Replication Transact-SQL Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="ff221-124">Das ActiveX-Verteilungssteuerelement und das ActiveX-Mergesteuerelement wurden als veraltete markiert.</span><span class="sxs-lookup"><span data-stu-id="ff221-124">The Distribution ActiveX control and Merge ActiveX control have been deprecated.</span></span> <span data-ttu-id="ff221-125">Ähnliche Funktionalität wird mit Replikationsverwaltungsobjekten (RMO) für verwaltete Codeanwendungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ff221-125">Similar functionality is provided for managed code applications using Replication Management Objects (RMO).</span></span> <span data-ttu-id="ff221-126">Weitere Informationen finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation unter "Synchronisieren von Abonnements (RMO-Programmierung)".</span><span class="sxs-lookup"><span data-stu-id="ff221-126">For more information, see "Synchronizing Subscriptions (RMO Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff221-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff221-127">See Also</span></span>  
 [<span data-ttu-id="ff221-128">Probleme beim Replikationsupgrade</span><span class="sxs-lookup"><span data-stu-id="ff221-128">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
