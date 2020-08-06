---
title: SQL Server, Wartestatistik-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfd2f1309cb118896ff7951b7f82feb38de60e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696749"
---
# <a name="sql-server-wait-statistics-object"></a><span data-ttu-id="a9610-102">SQL Server, Wartestatistik-Objekt</span><span class="sxs-lookup"><span data-stu-id="a9610-102">SQL Server, Wait Statistics Object</span></span>
  <span data-ttu-id="a9610-103">Das **SQLServer:Wartestatistik** -Leistungsobjekt enthält Leistungsindikatoren mit Informationen zum Wartestatus.</span><span class="sxs-lookup"><span data-stu-id="a9610-103">The **SQLServer:Wait Statistics** performance object contains performance counters that report information about wait status.</span></span>  
  
 <span data-ttu-id="a9610-104">In der folgenden Tabelle werden die im Wartestatistik-Objekt enthaltenen Leistungsindikatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a9610-104">The table below lists the counters that the Wait Statistics object contains.</span></span>  
  
|<span data-ttu-id="a9610-105">Leistungsindikatoren des SQLServer:Wartestatistik-Objekts</span><span class="sxs-lookup"><span data-stu-id="a9610-105">SQL Server Wait Statistics counters</span></span>|<span data-ttu-id="a9610-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a9610-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="a9610-107">**Sperrenwartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-107">**Lock waits**</span></span>|<span data-ttu-id="a9610-108">Statistik für Prozesse, die auf eine Sperre warten</span><span class="sxs-lookup"><span data-stu-id="a9610-108">Statistics for processes waiting on a lock.</span></span>|  
|<span data-ttu-id="a9610-109">**Protokollpuffer-Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-109">**Log buffer waits**</span></span>|<span data-ttu-id="a9610-110">Statistik für Prozesse, die auf die Verfügbarkeit des Protokollpuffers warten</span><span class="sxs-lookup"><span data-stu-id="a9610-110">Statistics for processes waiting for log buffer to be available.</span></span>|  
|<span data-ttu-id="a9610-111">**Wartevorgänge für Schreiben des Protokolls**</span><span class="sxs-lookup"><span data-stu-id="a9610-111">**Log write waits**</span></span>|<span data-ttu-id="a9610-112">Statistik für Prozesse, die darauf warten, dass der Protokollpuffer geschrieben wird</span><span class="sxs-lookup"><span data-stu-id="a9610-112">Statistics for processes waiting for log buffer to be written.</span></span>|  
|<span data-ttu-id="a9610-113">**Speicherzuweisungs-Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-113">**Memory grant queue waits**</span></span>|<span data-ttu-id="a9610-114">Statistik für Prozesse, die auf die Verfügbarkeit einer Speicherzuweisung warten</span><span class="sxs-lookup"><span data-stu-id="a9610-114">Statistics for processes waiting for memory grant to become available.</span></span>|  
|<span data-ttu-id="a9610-115">**Netzwerk-E/A-Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-115">**Network IO waits**</span></span>|<span data-ttu-id="a9610-116">Statistik für Wartevorgänge bezüglich Netzwerk-E/A</span><span class="sxs-lookup"><span data-stu-id="a9610-116">Statistics relevant to wait on network I/O.</span></span>|  
|<span data-ttu-id="a9610-117">**Nichtseiten-Latchwartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-117">**Non-Page latch waits**</span></span>|<span data-ttu-id="a9610-118">Statistik für Nichtseitenlatches</span><span class="sxs-lookup"><span data-stu-id="a9610-118">Statistics relevant to non-page latches.</span></span>|  
|<span data-ttu-id="a9610-119">**Seiten-E/A-Latchwartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-119">**Page IO latch waits**</span></span>|<span data-ttu-id="a9610-120">Statistik für Seiten-E/A-Latches</span><span class="sxs-lookup"><span data-stu-id="a9610-120">Statistics relevant to page I/O latches.</span></span>|  
|<span data-ttu-id="a9610-121">**Seitenlatch-Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-121">**Page latch waits**</span></span>|<span data-ttu-id="a9610-122">Statistik für Seitenlatches, ohne E/A-Latches</span><span class="sxs-lookup"><span data-stu-id="a9610-122">Statistics relevant to page latches, not including I/O latches.</span></span>|  
|<span data-ttu-id="a9610-123">**Thread-sichere Speicherobjekt-Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-123">**Thread-safe memory objects waits**</span></span>|<span data-ttu-id="a9610-124">Statistik für Prozesse, die auf Thread-sichere Speicherzuordnungen warten</span><span class="sxs-lookup"><span data-stu-id="a9610-124">Statistics for processes waiting on thread-safe memory allocators.</span></span>|  
|<span data-ttu-id="a9610-125">**Transaktionsbesitzer-Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-125">**Transaction ownership waits**</span></span>|<span data-ttu-id="a9610-126">Statistik für Prozesse, die den Zugriff auf Transaktionen synchronisieren</span><span class="sxs-lookup"><span data-stu-id="a9610-126">Statistics relevant to processes synchronizing access to transaction.</span></span>|  
|<span data-ttu-id="a9610-127">**Warten auf den Arbeitsthread**</span><span class="sxs-lookup"><span data-stu-id="a9610-127">**Wait for the worker**</span></span>|<span data-ttu-id="a9610-128">Statistik für Prozesse, die auf die Verfügbarkeit des Arbeitsthreads warten</span><span class="sxs-lookup"><span data-stu-id="a9610-128">Statistics relevant to processes waiting for worker to become available.</span></span>|  
|<span data-ttu-id="a9610-129">**Wartevorgänge für Arbeitsbereichssynchronisierung**</span><span class="sxs-lookup"><span data-stu-id="a9610-129">**Workspace synchronization waits**</span></span>|<span data-ttu-id="a9610-130">Statistik für Prozesse, die den Zugriff auf den Arbeitsbereich synchronisieren</span><span class="sxs-lookup"><span data-stu-id="a9610-130">Statistics relevant to processes synchronizing access to workspace.</span></span>|  
  
 <span data-ttu-id="a9610-131">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="a9610-131">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="a9610-132">Element</span><span class="sxs-lookup"><span data-stu-id="a9610-132">Item</span></span>|<span data-ttu-id="a9610-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a9610-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="a9610-134">**Durchschnittliche Wartezeit (ms)**</span><span class="sxs-lookup"><span data-stu-id="a9610-134">**Average wait time (ms)**</span></span>|<span data-ttu-id="a9610-135">Durchschnittliche Zeit für den ausgewählten Wartetyp</span><span class="sxs-lookup"><span data-stu-id="a9610-135">Average time for the selected type of wait.</span></span>|  
|<span data-ttu-id="a9610-136">**Kumulierte Wartezeit (ms) pro Sekunde**</span><span class="sxs-lookup"><span data-stu-id="a9610-136">**Cumulative wait time (ms) per second**</span></span>|<span data-ttu-id="a9610-137">Aggregierte Wartezeit für den ausgewählten Typ pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="a9610-137">Aggregated wait time per second, for the selected type of wait.</span></span>|  
|<span data-ttu-id="a9610-138">**Aktuell ausgeführte Wartevorgänge**</span><span class="sxs-lookup"><span data-stu-id="a9610-138">**Waits in progress**</span></span>|<span data-ttu-id="a9610-139">Anzahl der Prozesse, die zurzeit auf den folgenden Typ warten</span><span class="sxs-lookup"><span data-stu-id="a9610-139">Number of processes currently waiting on the following type.</span></span>|  
|<span data-ttu-id="a9610-140">**Gestartete Wartevorgänge pro Sekunde**</span><span class="sxs-lookup"><span data-stu-id="a9610-140">**Waits started per second**</span></span>|<span data-ttu-id="a9610-141">Anzahl der pro Sekunde gestarteten Wartevorgänge des ausgewählten Wartetyps</span><span class="sxs-lookup"><span data-stu-id="a9610-141">Number of waits started per second of the selected type of wait.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9610-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9610-142">See Also</span></span>  
 [<span data-ttu-id="a9610-143">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="a9610-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
