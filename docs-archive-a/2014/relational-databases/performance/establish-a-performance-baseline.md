---
title: Festlegen einer Leistungsbasislinie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], baselines
- monitoring performance [SQL Server], baselines
- tuning databases [SQL Server], baselines
- server performance [SQL Server], baselines
- performance [SQL Server], baselines
- baseline performance [SQL Server]
- measurements for baseline statistics [SQL Server]
- monitoring server performance [SQL Server], establishing baseline
- database monitoring [SQL Server], baselines
ms.assetid: dc5aa8d6-2507-448f-ad86-4196443915fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0cb85ae8ad370b816c6240b58aabd247c7593c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696741"
---
# <a name="establish-a-performance-baseline"></a><span data-ttu-id="34034-102">Festlegen einer Leistungsbasislinie</span><span class="sxs-lookup"><span data-stu-id="34034-102">Establish a Performance Baseline</span></span>
  <span data-ttu-id="34034-103">Wenn Sie ermitteln möchten, ob das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -System einwandfrei arbeitet, sollten Sie die Leistung in regelmäßigen Abständen messen, selbst wenn keine Probleme auftreten, um eine Basislinie für die Serverleistung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="34034-103">To determine whether your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system is performing optimally, take performance measurements at regular intervals over time, even when no problems occur, to establish a server performance baseline.</span></span> <span data-ttu-id="34034-104">Vergleichen Sie jede neue Messreihe mit den zuvor erfassten Messungen.</span><span class="sxs-lookup"><span data-stu-id="34034-104">Compare each new set of measurements with those taken earlier.</span></span>  
  
 <span data-ttu-id="34034-105">Die folgenden Bereiche wirken sich auf die Leistung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]aus:</span><span class="sxs-lookup"><span data-stu-id="34034-105">The following areas affect the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="34034-106">Systemressourcen (Hardware)</span><span class="sxs-lookup"><span data-stu-id="34034-106">System resources (hardware)</span></span>  
  
-   <span data-ttu-id="34034-107">Netzwerkarchitektur</span><span class="sxs-lookup"><span data-stu-id="34034-107">Network architecture</span></span>  
  
-   <span data-ttu-id="34034-108">Das Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="34034-108">The operating system</span></span>  
  
-   <span data-ttu-id="34034-109">Datenbankanwendungen</span><span class="sxs-lookup"><span data-stu-id="34034-109">Database applications</span></span>  
  
-   <span data-ttu-id="34034-110">Clientanwendungen</span><span class="sxs-lookup"><span data-stu-id="34034-110">Client applications</span></span>  
  
 <span data-ttu-id="34034-111">Es sollten mindestens die folgenden Basislinienmessungen vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="34034-111">At a minimum, use baseline measurements to determine:</span></span>  
  
-   <span data-ttu-id="34034-112">Leistung bei Spitzen- und Normalbetrieb.</span><span class="sxs-lookup"><span data-stu-id="34034-112">Peak and off-peak hours of operation.</span></span>  
  
-   <span data-ttu-id="34034-113">Antwortzeiten für Produktionsabfragen oder Batchbefehle.</span><span class="sxs-lookup"><span data-stu-id="34034-113">Production-query or batch-command response times.</span></span>  
  
-   <span data-ttu-id="34034-114">Zeiten für das Sichern und Wiederherstellen von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="34034-114">Database backup and restore completion times.</span></span>  
  
 <span data-ttu-id="34034-115">Nach dem Erstellen einer Basislinie für die Serverleistung sollten Sie die Basislinienstatistik mit der aktuellen Serverleistung vergleichen.</span><span class="sxs-lookup"><span data-stu-id="34034-115">After you establish a server performance baseline, compare the baseline statistics to current server performance.</span></span> <span data-ttu-id="34034-116">Zahlen, die deutlich über oder unter der Basislinie liegen, sollten näher untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="34034-116">Numbers far above or far below your baseline are candidates for further investigation.</span></span> <span data-ttu-id="34034-117">Sie können ein Hinweis auf Bereiche, die optimiert oder neu konfiguriert werden müssen, sein.</span><span class="sxs-lookup"><span data-stu-id="34034-117">They may indicate areas in need of tuning or reconfiguration.</span></span> <span data-ttu-id="34034-118">Wenn beispielsweise die Zeitdauer zum Ausführen einer Reihe von Abfragen steigt, sollten Sie die Abfragen untersuchen, um festzustellen, ob sie neu geschrieben werden können oder ob Spaltenstatistiken oder neue Indizes hinzugefügt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="34034-118">For example, if the amount of time to execute a set of queries increases, examine the queries to determine if they can be rewritten, or if column statistics or new indexes must be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34034-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34034-119">See Also</span></span>  
 [<span data-ttu-id="34034-120">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34034-120">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
