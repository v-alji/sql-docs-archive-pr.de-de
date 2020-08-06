---
title: Überwachen der CPU-Auslastung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], CPU usage
- tuning databases [SQL Server], CPU usage
- processors [SQL Server], monitoring usage
- database performance [SQL Server], CPU usage
- monitoring CPU usage [SQL Server]
- server performance [SQL Server], CPU usage
- database monitoring [SQL Server], CPU usage
- monitoring [SQL Server], CPU usage
- processors [SQL Server]
- CPU [SQL Server], monitoring
- monitoring server performance [SQL Server], CPU usage
ms.assetid: 2a02a3b6-07b2-4ad0-8a24-670414d19812
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f08d49348fd25593f27a87f2b0123f7ce43e35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723729"
---
# <a name="monitor-cpu-usage"></a><span data-ttu-id="f7d52-102">Überwachen der CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="f7d52-102">Monitor CPU Usage</span></span>
  <span data-ttu-id="f7d52-103">Überwachen Sie eine Instanz von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in regelmäßigen Abständen, um sicherzustellen, dass sich die CPU-Nutzungsraten im Normalbereich bewegen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-103">Monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to determine whether CPU usage rates are within normal ranges.</span></span> <span data-ttu-id="f7d52-104">Eine konstant hohe CPU-Nutzungsrate kann ein Anzeichen dafür sein, dass die CPU aktualisiert werden muss oder weitere Prozessoren hinzugefügt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-104">A continually high rate of CPU usage may indicate the need to upgrade the CPU or add multiple processors.</span></span> <span data-ttu-id="f7d52-105">Darüber hinaus kann eine hohe CPU-Nutzungsrate auf eine schlecht angepasste oder entwickelte Anwendung hinweisen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-105">Alternatively, a high CPU usage rate may indicate a poorly tuned or designed application.</span></span> <span data-ttu-id="f7d52-106">Eine Optimierung der Anwendung kann die CPU-Nutzung senken.</span><span class="sxs-lookup"><span data-stu-id="f7d52-106">Optimizing the application can lower CPU utilization.</span></span>  
  
 <span data-ttu-id="f7d52-107">Um die CPU-Nutzungsrate festzustellen, rufen Sie am besten im Systemmonitor den Leistungsindikator **Prozessor: Prozessorzeit (%)** auf.</span><span class="sxs-lookup"><span data-stu-id="f7d52-107">An efficient way to determine CPU usage is to use the **Processor:% Processor Time** counter in System Monitor.</span></span> <span data-ttu-id="f7d52-108">Dieser Leistungsindikator überwacht die Zeit, die die CPU zur Verarbeitung eines Threads benötigt, der sich nicht im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="f7d52-108">This counter monitors the amount of time the CPU spends executing a thread that is not idle.</span></span> <span data-ttu-id="f7d52-109">Ein konstanter Status von 80-90 % kann darauf hinweisen, dass ein CPU-Upgrade notwendig ist oder weitere Prozessoren hinzugefügt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-109">A consistent state of 80 percent to 90 percent may indicate the need to upgrade your CPU or add more processors.</span></span> <span data-ttu-id="f7d52-110">Bei Multiprozessorsystemen sollte für jeden Prozessor eine separate Instanz dieses Leistungsindikators überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="f7d52-110">For multiprocessor systems, monitor a separate instance of this counter for each processor.</span></span> <span data-ttu-id="f7d52-111">Dieser Wert stellt die Summe der Prozessorzeit für einen bestimmten Prozessor dar.</span><span class="sxs-lookup"><span data-stu-id="f7d52-111">This value represents the sum of processor time on a specific processor.</span></span> <span data-ttu-id="f7d52-112">Um den Durchschnitt für alle Prozessoren zu ermitteln, müssen Sie dagegen den Leistungsindikator **System: Gesamtprozessorzeit (%)** aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-112">To determine the average for all processors, use the **System: %Total Processor Time** counter instead.</span></span>  
  
 <span data-ttu-id="f7d52-113">Darüber hinaus können Sie die Prozessornutzung aber auch über die folgenden Leistungsindikatoren überwachen:</span><span class="sxs-lookup"><span data-stu-id="f7d52-113">Optionally, you can also monitor the following counters to monitor processor usage:</span></span>  
  
-   <span data-ttu-id="f7d52-114">**Prozessor: Privilegierte Zeit (%)**</span><span class="sxs-lookup"><span data-stu-id="f7d52-114">**Processor: % Privileged Time**</span></span>  
  
     <span data-ttu-id="f7d52-115">Gibt den prozentualen Zeitanteil an der Gesamtzeit an, die der Prozessor benötigt, um Microsoft Windows-Kernelbefehle, wie die Verarbeitung von E/A-Anforderungen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-115">Corresponds to the percentage of time the processor spends on execution of Microsoft Windows kernel commands, such as processing of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] I/O requests.</span></span> <span data-ttu-id="f7d52-116">Sollte dieser Leistungsindikator bei hohen Werten für die Leistungsindikatoren **Physischer Datenträger** gleich bleibend hoch sein, sollten Sie die Installation eines schnelleren oder effizienteren Datenträgersubsystems in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-116">If this counter is consistently high when the **Physical Disk** counters are high, consider installing a faster or more efficient disk subsystem.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7d52-117">Unterschiedliche Datenträgercontroller und -treiber benötigen unterschiedlich viel Zeit für die Kernelverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="f7d52-117">Different disk controllers and drivers use different amounts of kernel processing time.</span></span> <span data-ttu-id="f7d52-118">Effiziente Controller und Treiber beanspruchen weniger privilegierte Zeit und überlassen Benutzeranwendungen so mehr Verarbeitungszeit, wodurch der Durchsatz insgesamt steigt.</span><span class="sxs-lookup"><span data-stu-id="f7d52-118">Efficient controllers and drivers use less privileged time, leaving more processing time available for user applications, increasing overall throughput.</span></span>  
  
-   <span data-ttu-id="f7d52-119">**Prozessor: Benutzerzeit (%)**</span><span class="sxs-lookup"><span data-stu-id="f7d52-119">**Processor: %User Time**</span></span>  
  
     <span data-ttu-id="f7d52-120">Gibt den prozentualen Zeitanteil an der Gesamtzeit an, die der Prozessor benötigt, um Benutzerprozesse wie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-120">Corresponds to the percentage of time that the processor spends on executing user processes such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f7d52-121">**System: Prozessor-Warteschlangenlänge**</span><span class="sxs-lookup"><span data-stu-id="f7d52-121">**System: Processor Queue Length**</span></span>  
  
     <span data-ttu-id="f7d52-122">Gibt die Anzahl der Threads an, die auf Prozessorzeit warten.</span><span class="sxs-lookup"><span data-stu-id="f7d52-122">Corresponds to the number of threads waiting for processor time.</span></span> <span data-ttu-id="f7d52-123">Ein Prozessorengpass entsteht, wenn die Threads eines Prozesses mehr Prozessorzyklen benötigen, als zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-123">A processor bottleneck develops when threads of a process require more processor cycles than are available.</span></span> <span data-ttu-id="f7d52-124">Wenn viele Prozesse versuchen, Prozessorzeit zu beanspruchen, müssen Sie ggf. einen schnelleren Prozessor installieren.</span><span class="sxs-lookup"><span data-stu-id="f7d52-124">If more than a few processes attempt to utilize the processor's time, you might need to install a faster processor.</span></span> <span data-ttu-id="f7d52-125">Bei einem Multiprozessorsystem könnten Sie auch einen Prozessor hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-125">Or, if you have a multiprocessor system, you could add a processor.</span></span>  
  
 <span data-ttu-id="f7d52-126">Bei der Überprüfung der Prozessornutzung müssen Sie auch die Art der Vorgänge berücksichtigen, die durch die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7d52-126">When you examine processor usage, consider the type of work that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs.</span></span> <span data-ttu-id="f7d52-127">Wenn in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viele Berechnungen ausgeführt werden, wie etwa Abfragen, die Aggregate enthalten, oder arbeitsspeichergestützte Abfragen, bei denen keine Datenträger-E/A notwendig ist, können durchaus 100 % der Prozessorzeit beansprucht werden.</span><span class="sxs-lookup"><span data-stu-id="f7d52-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs many calculations, such as queries involving aggregates or memory-bound queries that require no disk I/O, 100 percent of the processor's time can be used.</span></span> <span data-ttu-id="f7d52-128">Wenn dies bewirkt, dass die Leistung anderer Anwendungen leidet, versuchen Sie, die Arbeitsauslastung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f7d52-128">If this causes the performance of other applications to suffer, try changing the workload.</span></span> <span data-ttu-id="f7d52-129">Reservieren Sie beispielsweise den Computer für das Ausführen der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7d52-129">For example, dedicate the computer to running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f7d52-130">Nutzungsraten um 100 %, wenn viele Clientanforderungen verarbeitet werden, können darauf hinweisen, dass Prozesse in Warteschlangen angeordnet werden, auf Prozessorzeit warten und einen Engpass verursachen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-130">Usage rates around 100 percent, where many client requests are being processed, may indicate that processes are queuing up, waiting for processor time, and causing a bottleneck.</span></span> <span data-ttu-id="f7d52-131">Lösen Sie das Problem, indem Sie das System durch leistungsstärkere Prozessoren ergänzen.</span><span class="sxs-lookup"><span data-stu-id="f7d52-131">Resolve the problem by adding faster processors.</span></span>  
  
  
