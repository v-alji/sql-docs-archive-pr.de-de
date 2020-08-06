---
title: Verwenden von in-Memory-OLTP in einer VM-Umgebung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 27ec7eb3-3a24-41db-aa65-2f206514c6f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83cf785fbcd2df9449d61e328e3bf8e374a6656d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700197"
---
# <a name="using-in-memory-oltp-in-a-vm-environment"></a><span data-ttu-id="13f57-102">Verwenden von In-Memory OLTP in einer VM-Umgebung</span><span class="sxs-lookup"><span data-stu-id="13f57-102">Using In-Memory OLTP in a VM Environment</span></span>
  <span data-ttu-id="13f57-103">Servervirtualisierung kann durch eine verbesserte Anwendungsbereitstellung, Wartung, Verfügbarkeit sowie Sicherungs- und Wiederherstellungsprozesse das IT-Kapital und die Betriebskosten Ihres Unternehmens senken und die IT-Effizienz steigern.</span><span class="sxs-lookup"><span data-stu-id="13f57-103">Server virtualization can help you lower IT capital and operational costs and attain greater IT efficiency with improved application provisioning, maintenance, availability, and backup/recovery processes.</span></span> <span data-ttu-id="13f57-104">Dank der neuesten technologischen Entwicklungen können komplexe Datenbankarbeitslasten mithilfe der Virtualisierung leichter konsolidiert werden.</span><span class="sxs-lookup"><span data-stu-id="13f57-104">With recent technological advances, complex database workloads can be more readily consolidated using virtualization.</span></span> <span data-ttu-id="13f57-105">Dieses Thema enthält bewährte Methoden zur Verwendung von [!INCLUDE[hek_1](../includes/hek-1-md.md)] in einer virtualisierten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="13f57-105">This topic covers best practices for using [!INCLUDE[hek_1](../includes/hek-1-md.md)] in a virtualized environment.</span></span>  
  
##  <a name="memory-pre-allocation"></a><a name="bkmk_memoryPreAllocation"></a><span data-ttu-id="13f57-106">Vorab Zuordnung von Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="13f57-106">Memory pre-allocation</span></span>  
 <span data-ttu-id="13f57-107">Für den Arbeitsspeicher in einer virtualisierten Umgebung sind bessere Leistung und erweiterte Unterstützung zentrale Faktoren.</span><span class="sxs-lookup"><span data-stu-id="13f57-107">For memory in a virtualized environment, better performance and enhanced support are essential considerations.</span></span> <span data-ttu-id="13f57-108">Sie müssen sowohl in der Lage sein, virtuellen Computern auf Basis der jeweiligen Anforderungen (Last zu Spitzenzeiten und außerhalb von Spitzenzeiten) schnell Arbeitsspeicher zuzuordnen als auch sicherzustellen, dass dieser Arbeitsspeicher nicht verschwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13f57-108">You must be able to both quickly allocate memory to virtual machines depending on their requirements (peak and off-peak loads) and ensure that the memory is not wasted.</span></span> <span data-ttu-id="13f57-109">Der dynamischer Arbeitsspeicher von Hyper-V erhöht die Flexibilität bei der Zuweisung und Verwaltung von Arbeitsspeicher zwischen virtuellen Computern, die auf einem Host ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="13f57-109">The Hyper-V Dynamic Memory feature increases agility in how the memory is allocated and managed between virtual machines running on a host.</span></span>  
  
 <span data-ttu-id="13f57-110">Einige bewährte Methoden für die Virtualisierung und Verwaltung von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] müssen geändert werden, wenn eine Datenbank mit speicheroptimierten Tabellen virtualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="13f57-110">Some best practices for virtualizing and managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] need to be modified when virtualizing a database with memory-optimized tables.</span></span> <span data-ttu-id="13f57-111">Ohne speicheroptimierte Tabellen lauten zwei bewährte Methoden wie folgt:</span><span class="sxs-lookup"><span data-stu-id="13f57-111">Without memory-optimized tables, two of the best practices are:</span></span>  
  
-   <span data-ttu-id="13f57-112">Bei Verwendung von MIN_SERVER_MEMORY sollte nur die tatsächlich erforderliche Speichermenge zugewiesen werden, sodass ausreichend Speicher für andere Prozesse verbleibt (und Auslagerungen vermieden werden).</span><span class="sxs-lookup"><span data-stu-id="13f57-112">If you use MIN_SERVER_MEMORY, it is better to assign only the amount of memory that is required so sufficient memory remains for other processes (thereby avoiding paging).</span></span>  
  
-   <span data-ttu-id="13f57-113">Legen Sie den Wert für die Vorabbelegung von Arbeitsspeicher nicht zu hoch fest.</span><span class="sxs-lookup"><span data-stu-id="13f57-113">Do not set the memory pre-allocation value too high.</span></span> <span data-ttu-id="13f57-114">Andernfalls erhalten andere Prozesse u. U. nicht ausreichend Speicher, wenn sie ihn brauchen. Dies kann zu Speicherauslagerungen führen.</span><span class="sxs-lookup"><span data-stu-id="13f57-114">Otherwise, other processes may not get sufficient memory at the time when they require it, and this can result in memory paging.</span></span>  
  
 <span data-ttu-id="13f57-115">Wenn Sie für eine Datenbank mit speicheroptimierten Tabellen die oben genannten Methoden verwenden, kann der Versuch, die Datenbank wiederherzustellen, dazu führen, dass die Datenbank im Status „Wiederherstellung steht aus“ hängen bleibt, obwohl genügend Arbeitsspeicher zum Wiederherstellen der Datenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="13f57-115">If you follow the above practices for a database with memory-optimized tables, an attempt to restore and recover a database could result in the database being in a "Recovery Pending" state, even if you have sufficient memory to recover the database.</span></span> <span data-ttu-id="13f57-116">Die Ursache hierfür ist, dass [!INCLUDE[hek_2](../includes/hek-2-md.md)] die Daten beim Starten aggressiver in den Speicher lädt, als die dynamische Speicherbelegung den Arbeitsspeicher der Datenbank zuweist.</span><span class="sxs-lookup"><span data-stu-id="13f57-116">The reason for this is that, when starting up, [!INCLUDE[hek_2](../includes/hek-2-md.md)] brings data into memory more aggressively than dynamic memory allocation allocates memory to the database.</span></span>  
  
 <span data-ttu-id="13f57-117">**Lösung**</span><span class="sxs-lookup"><span data-stu-id="13f57-117">**Resolution**</span></span>  
  
 <span data-ttu-id="13f57-118">Um dieses Risiko abzuschwächen, ordnen Sie der Datenbank vorab genügend Arbeitsspeicher zu, um die Datenbank wiederherzustellen oder neu zu starten. Verwenden Sie hierfür nicht den Minimalwert auf Basis des dynamischen Speichers, um den zusätzlichen Arbeitsspeicher bei Bedarf bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="13f57-118">To mitigate this, pre-allocate sufficient memory to the database to recover or restart the database, not a minimum value relying on dynamic memory to provide the additional memory when needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f57-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13f57-119">See Also</span></span>  
 [<span data-ttu-id="13f57-120">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="13f57-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
