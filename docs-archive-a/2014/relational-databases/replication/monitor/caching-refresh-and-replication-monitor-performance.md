---
title: Zwischenspeichern, Aktualisieren und Leistung des Replikationsmonitors | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b04a91e971e65d19c66cc36f142d8c4764b1b05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615938"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a><span data-ttu-id="0115f-102">Zwischenspeichern, Aktualisieren und Leistung des Replikationsmonitors</span><span class="sxs-lookup"><span data-stu-id="0115f-102">Caching, Refresh, and Replication Monitor Performance</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="0115f-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Der Replikations Monitor dient der effizienten Überwachung einer großen Anzahl von Computern in einem Produktionssystem.</span><span class="sxs-lookup"><span data-stu-id="0115f-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor is designed to efficiently monitor a large number of computers in a production system.</span></span> <span data-ttu-id="0115f-104">Die Abfragen, mit denen der Replikationsmonitor Berechnungen ausführt und Daten erfasst, werden zwischengespeichert und regelmäßig aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0115f-104">The queries that Replication Monitor uses to perform calculations and gather data are cached and refreshed on a periodic basis.</span></span> <span data-ttu-id="0115f-105">Das Zwischenspeichern verringert die Zahl der Abfragen und Berechnungen, die erforderlich sind, wenn Sie verschiedene Seiten im Replikationsmonitor anzeigen, und ermöglicht es, den Umfang der Überwachungen für mehrere Benutzer optimal anzupassen.</span><span class="sxs-lookup"><span data-stu-id="0115f-105">Caching reduces the number of queries and calculations required as you view different pages in Replication Monitor and allows monitoring to scale well for multiple users.</span></span>  
  
 <span data-ttu-id="0115f-106">Die Aktualisierung des Cache wird durch einen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agentauftrag ausgeführt: **Aktualisierung für die Replikationsüberwachung**.</span><span class="sxs-lookup"><span data-stu-id="0115f-106">Cache refresh is handled by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job, the **Replication monitoring refresher for distribution**.</span></span> <span data-ttu-id="0115f-107">Der Auftrag wird fortlaufend ausgeführt. Der Zeitplan für die Aktualisierung des Cache hängt von einer bestimmten Wartedauer nach der vorhergehenden Aktualisierung ab:</span><span class="sxs-lookup"><span data-stu-id="0115f-107">The job runs continuously, but the cache refresh schedule is based on waiting a certain amount time after the previous refresh:</span></span>  
  
-   <span data-ttu-id="0115f-108">Wenn seit dem letzten Erstellen des Cache Änderungen des Agent-Verlaufs stattgefunden haben, beträgt die Wartezeit mindestens 4 Sekunden oder die Zeitspanne, die das Erstellen des vorherigen Cache gedauert hat.</span><span class="sxs-lookup"><span data-stu-id="0115f-108">If there were agent history changes since the cache was last created, the wait time is the minimum of: 4 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
-   <span data-ttu-id="0115f-109">Wenn seit dem letzten Erstellen des Cache keine Änderungen des Agent-Verlaufs stattgefunden haben (es könnten andere Änderungen eingetreten sein), beträgt die Wartezeit maximal 30 Sekunden oder die Zeitspanne, die das Erstellen des vorherigen Cache gedauert hat.</span><span class="sxs-lookup"><span data-stu-id="0115f-109">If there were no agent history changes since the cache was last created (there could have been other changes), the wait time is the maximum of: 30 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a><span data-ttu-id="0115f-110">Aktualisieren der Benutzeroberfläche des Replikationsmonitors</span><span class="sxs-lookup"><span data-stu-id="0115f-110">Refreshing the Replication Monitor User Interface</span></span>  
 <span data-ttu-id="0115f-111">Die Benutzeroberfläche des Replikationsmonitors kann folgendermaßen aktualisiert werden:</span><span class="sxs-lookup"><span data-stu-id="0115f-111">The Replication Monitor user interface can be refreshed in the following ways:</span></span>  
  
-   <span data-ttu-id="0115f-112">Das Fenster des Replikationsmonitors (einschließlich aller Registerkarten) wird standardmäßig alle fünf Sekunden automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0115f-112">The main Replication Monitor window (including all tabs), automatically refreshes by default every five seconds.</span></span> <span data-ttu-id="0115f-113">Das automatische Aktualisieren erzwingt keine Aktualisierung des Cache. Die Benutzeroberfläche zeigt die aktuellste Version der Daten aus dem Cache an.</span><span class="sxs-lookup"><span data-stu-id="0115f-113">Automatic refreshes do not force a refresh of the cache; the user interface displays the most recent version of the data from the cache.</span></span> <span data-ttu-id="0115f-114">Sie können die Aktualisierungsrate für alle Fenster anpassen, die mit einem Verleger zusammenhängen, indem Sie die Einstellungen für den Verleger bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0115f-114">You can customize the refresh rate used for all windows associated with a Publisher by editing the Publisher settings.</span></span> <span data-ttu-id="0115f-115">Sie können die automatischen Aktualisierungen für einen Verleger auch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0115f-115">You can also disable automatic refreshes for a Publisher.</span></span>  
  
-   <span data-ttu-id="0115f-116">Die im Replikationsmonitor gestarteten Detailfenster werden nicht standardmäßig automatisch aktualisiert, ausgenommen Fenster, die mit einem gerade synchronisierten Merge-Abonnement zusammenhängen.</span><span class="sxs-lookup"><span data-stu-id="0115f-116">The detail windows that are launched from Replication Monitor are not automatically refreshed by default, with the exception of windows related to merge subscriptions that are synchronizing.</span></span> <span data-ttu-id="0115f-117">Wenn Sie das automatische Aktualisieren von Detailfenstern angeben, werden die Fenster nach demselben Zeitplan aktualisiert wie das Hauptfenster des Replikationsmonitors.</span><span class="sxs-lookup"><span data-stu-id="0115f-117">If you specify that detail windows should automatically refresh, they refresh on the same schedule as the main Replication Monitor window.</span></span>  
  
-   <span data-ttu-id="0115f-118">Sie können alle Fenster manuell aktualisieren. Drücken Sie dazu F5, oder klicken Sie mit der rechten Maustaste auf einen Knoten in der Struktur des Replikationsmonitors, und klicken Sie dann auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="0115f-118">All windows can be manually refreshed by pressing F5 or by right-clicking a node in the Replication Monitor tree and clicking **Refresh**.</span></span> <span data-ttu-id="0115f-119">Das manuelle Aktualisieren erzwingt eine Aktualisierung des Cache.</span><span class="sxs-lookup"><span data-stu-id="0115f-119">Manual refreshes force a refresh of the cache.</span></span>  
  
 <span data-ttu-id="0115f-120">Weitere Informationen finden Sie unter [Aktualisieren von Daten im Replikationsmonitor](refresh-data-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="0115f-120">For more information, see [Refresh Data in Replication Monitor](refresh-data-in-replication-monitor.md).</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="0115f-121">Überlegungen zur Leistung</span><span class="sxs-lookup"><span data-stu-id="0115f-121">Performance Considerations</span></span>  
 <span data-ttu-id="0115f-122">Der Replikationsmonitor ist zwar für ein effizientes Ausführen ausgelegt, jedoch sollten Sie Folgendes beachten:</span><span class="sxs-lookup"><span data-stu-id="0115f-122">Although Replication Monitor is designed to run efficiently, be aware of the following:</span></span>  
  
-   <span data-ttu-id="0115f-123">Legen Sie bei einer großen Zahl von Veröffentlichungen oder Abonnements einen Zeitplan fest, nach dem die Benutzeroberfläche weniger häufig automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0115f-123">If you have a large number of publications or subscriptions, consider setting a less frequent automatic refresh schedule for the user interface.</span></span>  
  
-   <span data-ttu-id="0115f-124">Vermeiden Sie das gleichzeitige Ausführen mehrerer Instanzen des Replikationsmonitors.</span><span class="sxs-lookup"><span data-stu-id="0115f-124">Avoid concurrently running multiple instances of Replication Monitor.</span></span>  
  
-   <span data-ttu-id="0115f-125">Vermeiden Sie es, eine große Zahl von Verteilern zu registrieren und festzulegen, dass der Replikationsmonitor zu allen automatisch eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="0115f-125">Avoid registering a large number of Distributors and setting Replication Monitor to automatically connect to all of them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0115f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0115f-126">See Also</span></span>  
 <span data-ttu-id="0115f-127">[Ausführen von Aufträgen zur Replikationswartung &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="0115f-127">[Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="0115f-128">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="0115f-128">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
