---
title: MSSQLSERVER_32043 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32043 (Database Engine error)
ms.assetid: a0c48ae3-4c8c-419c-afb5-579fcefac01d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2febc7173c8144451c7a9b0576f2293d5594c6df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608725"
---
# <a name="mssqlserver_32043"></a><span data-ttu-id="169b9-102">MSSQLSERVER_32043</span><span class="sxs-lookup"><span data-stu-id="169b9-102">MSSQLSERVER_32043</span></span>
    
## <a name="details"></a><span data-ttu-id="169b9-103">Details</span><span class="sxs-lookup"><span data-stu-id="169b9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="169b9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="169b9-104">Product Name</span></span>|<span data-ttu-id="169b9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="169b9-105">SQL Server</span></span>|  
|<span data-ttu-id="169b9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="169b9-106">Event ID</span></span>|<span data-ttu-id="169b9-107">32043</span><span class="sxs-lookup"><span data-stu-id="169b9-107">32043</span></span>|  
|<span data-ttu-id="169b9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="169b9-108">Event Source</span></span>|<span data-ttu-id="169b9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="169b9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="169b9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="169b9-110">Component</span></span>|<span data-ttu-id="169b9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="169b9-111">SQLEngine</span></span>|  
|<span data-ttu-id="169b9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="169b9-112">Symbolic Name</span></span>|<span data-ttu-id="169b9-113">SQLErrorNum32043</span><span class="sxs-lookup"><span data-stu-id="169b9-113">SQLErrorNum32043</span></span>|  
|<span data-ttu-id="169b9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="169b9-114">Message Text</span></span>|<span data-ttu-id="169b9-115">Die Warnung für 'nicht wiederhergestelltes Protokoll' wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="169b9-115">The alert for 'unrestored log' has been raised.</span></span> <span data-ttu-id="169b9-116">Der aktuelle Wert von '%d' überschreitet den Threshold '%d'.</span><span class="sxs-lookup"><span data-stu-id="169b9-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="169b9-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="169b9-117">Explanation</span></span>  
 <span data-ttu-id="169b9-118">Dieses Ereignis der Datenbankspiegelung wird für die Spiegelserverinstanz ausgelöst, um anzugeben, dass der Umfang des nicht wiederhergestellten Protokolls einen vom Benutzer angegebenen Schwellenwert erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="169b9-118">This database mirroring event is issued on the mirror server instance to indicate that the amount of unrestored log reached a user-specified threshold value.</span></span> <span data-ttu-id="169b9-119">Normalerweise tritt dieses Ereignis auf, weil sich die Leistung des Systems geändert hat.</span><span class="sxs-lookup"><span data-stu-id="169b9-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="169b9-120">Entweder hat sich die Bandbreite zwischen den beiden Systemen reduziert, oder die Last hat sich erhöht.</span><span class="sxs-lookup"><span data-stu-id="169b9-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="169b9-121">Ein nicht wiederhergestelltes Protokoll ist ein Protokoll, das von der Spiegelserverinstanz empfangen und auf einen Datenträger geschrieben wurde, das jedoch noch für die Spiegeldatenbank wiederhergestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="169b9-121">An unrestored log is a log that has been received by the mirror server instance and written to disk but is waiting to be restored to the mirror database.</span></span> <span data-ttu-id="169b9-122">Der Umfang des nicht wiederhergestellten Protokolls in Kilobyte (KB) ist eine Leistungsmetrik, mit der Sie die aktuelle Failoverzeit abschätzen können.</span><span class="sxs-lookup"><span data-stu-id="169b9-122">The amount of unrestored log in kilobytes (KB) is a performance metric that can help you evaluate the current failover time.</span></span> <span data-ttu-id="169b9-123">Die zum Übernehmen des nicht wiederhergestellten Protokolls erforderliche Zeit stellt den Hauptfaktor der Failoverzeit dar – zusammen mit einer kurzen zusätzlichen Zeit, die erforderlich ist, um die Datenbank wiederherzustellen und sie online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="169b9-123">The time that is required to apply the unrestored log is the main factor in failover time, along with a short additional time that is required to recover the database and bring it online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="169b9-124">Bei einem automatischen Failover ist die Zeit, die das System benötigt, um den Fehler zu erkennen, unabhängig von der Failoverzeit.</span><span class="sxs-lookup"><span data-stu-id="169b9-124">For an automatic failover, the time for the system to notice the failure is independent of the failover time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="169b9-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="169b9-125">User Action</span></span>  
 <span data-ttu-id="169b9-126">Prüfen Sie die Auslastung für die Instanzen des Prinzipalservers und des Spiegelservers sowie die entsprechenden Netzwerkverbindungen, um die Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="169b9-126">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169b9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="169b9-127">See Also</span></span>  
 <span data-ttu-id="169b9-128">[Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="169b9-128">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="169b9-129">Verwenden von Warnungsschwellenwerten und Warnmeldungen für Spiegelungsleistungsmetriken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="169b9-129">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
