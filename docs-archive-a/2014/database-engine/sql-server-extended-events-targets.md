---
title: SQL Server Ziele für erweiterte Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- extended events [SQL Server], targets
ms.assetid: e281684c-40d1-4cf9-a0d4-7ea1ecffa384
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 010b7cc29543f266b77aaf180c50173ef9f70346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608812"
---
# <a name="sql-server-extended-events-targets"></a><span data-ttu-id="f1a85-102">SQL Server Extended Events Targets</span><span class="sxs-lookup"><span data-stu-id="f1a85-102">SQL Server Extended Events Targets</span></span>
  <span data-ttu-id="f1a85-103">Ziele für erweiterte Ereignisse von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sind Ereignisconsumer.</span><span class="sxs-lookup"><span data-stu-id="f1a85-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events targets are event consumers.</span></span> <span data-ttu-id="f1a85-104">Ziele können in eine Datei schreiben, Ereignisdaten in einem Arbeitsspeicherpuffer speichern oder Ereignisdaten aggregieren.</span><span class="sxs-lookup"><span data-stu-id="f1a85-104">Targets can write to a file, store event data in a memory buffer, or aggregate event data.</span></span> <span data-ttu-id="f1a85-105">Ziele können Daten synchron oder asynchron verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f1a85-105">Targets can process data synchronously or asynchronously.</span></span>  
  
 <span data-ttu-id="f1a85-106">Durch das Design von Extended Events wird sichergestellt, dass Ziele garantiert nur einmal pro Sitzung Ereignisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="f1a85-106">The Extended Events design ensures that targets are guaranteed to receive events once and only once per session.</span></span>  
  
 <span data-ttu-id="f1a85-107">Erweiterte Ereignisse stellen die folgenden Ziele zur Verwendung in einer Sitzung mit erweiterten Ereignissen bereit:</span><span class="sxs-lookup"><span data-stu-id="f1a85-107">Extended Events provide the following targets that you can use for an Extended Events session:</span></span>  
  
-   [<span data-ttu-id="f1a85-108">Ereigniszähler</span><span class="sxs-lookup"><span data-stu-id="f1a85-108">Event counter</span></span>](../../2014/database-engine/event-counter-target.md)  
  
     <span data-ttu-id="f1a85-109">Zählt alle angegebenen Ereignisse, die während einer Sitzung für erweiterte Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="f1a85-109">Counts all specified events that occur during an Extended Events session.</span></span> <span data-ttu-id="f1a85-110">Wird eingesetzt, um Informationen über Merkmale der Arbeitsauslastung ohne den Aufwand einer vollständigen Ereignisauflistung zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="f1a85-110">Use to obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="f1a85-111">Dies ist ein synchrones Ziel.</span><span class="sxs-lookup"><span data-stu-id="f1a85-111">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="f1a85-112">Ereignis Datei</span><span class="sxs-lookup"><span data-stu-id="f1a85-112">Event file</span></span>](../../2014/database-engine/event-file-target.md)  
  
     <span data-ttu-id="f1a85-113">Wird eingesetzt, um die Ereignissitzungsausgabe aus vollständigen Speicherpuffern auf die Festplatte zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f1a85-113">Use to write event session output from complete memory buffers to disk.</span></span> <span data-ttu-id="f1a85-114">Dies ist ein asynchrones Ziel.</span><span class="sxs-lookup"><span data-stu-id="f1a85-114">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="f1a85-115">Ereignispaarbildung</span><span class="sxs-lookup"><span data-stu-id="f1a85-115">Event pairing</span></span>](../../2014/database-engine/event-pairing-target.md)  
  
     <span data-ttu-id="f1a85-116">Viele Arten von Ereignissen treten paarweise auf, wie z. B. Anforderungen zur Einrichtung und Aufhebung einer Sperre.</span><span class="sxs-lookup"><span data-stu-id="f1a85-116">Many kinds of events occur in pairs, such as lock acquires and lock releases.</span></span> <span data-ttu-id="f1a85-117">Ereignispaarbildung wird eingesetzt, um zu bestimmen, wann ein spezifisches, kombiniertes Ereignis nicht als Paar auftritt.</span><span class="sxs-lookup"><span data-stu-id="f1a85-117">Use to determine when a specified paired event does not occur in a matched set.</span></span> <span data-ttu-id="f1a85-118">Dies ist ein asynchrones Ziel.</span><span class="sxs-lookup"><span data-stu-id="f1a85-118">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="f1a85-119">Ereignisablaufverfolgung für Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="f1a85-119">Event Tracing for Windows (ETW)</span></span>](../relational-databases/extended-events/event-tracing-for-windows-target.md)  
  
     <span data-ttu-id="f1a85-120">Wird eingesetzt, um [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Ereignisse mit Ereignisdaten von Anwendungen oder des Windows-Betriebssystems zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="f1a85-120">Use to correlate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events with Windows operating system or application event data.</span></span> <span data-ttu-id="f1a85-121">Dies ist ein synchrones Ziel.</span><span class="sxs-lookup"><span data-stu-id="f1a85-121">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="f1a85-122">Histogramm</span><span class="sxs-lookup"><span data-stu-id="f1a85-122">Histogram</span></span>](../../2014/database-engine/histogram-target.md)  
  
     <span data-ttu-id="f1a85-123">Dient dazu, die Häufigkeit eines bestimmten Ereignisses auf Grundlage einer bestimmten Ereignisspalte oder Aktion zu zählen.</span><span class="sxs-lookup"><span data-stu-id="f1a85-123">Use to count the number of times that a specified event occurs, based on a specified event column or action.</span></span> <span data-ttu-id="f1a85-124">Dies ist ein asynchrones Ziel.</span><span class="sxs-lookup"><span data-stu-id="f1a85-124">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="f1a85-125">Ring Puffer</span><span class="sxs-lookup"><span data-stu-id="f1a85-125">Ring buffer</span></span>](../../2014/database-engine/ring-buffer-target.md)  
  
     <span data-ttu-id="f1a85-126">Wird verwendet, um die Ereignisdaten auf Basis der FIFO-Reihenfolge (First-In-First-Out) oder auf Basis der ereignisbezogenen FIFO-Reihenfolge im Speicher zu behalten.</span><span class="sxs-lookup"><span data-stu-id="f1a85-126">Use to hold the event data in memory on a first-in first-out (FIFO) basis, or on a per-event FIFO basis.</span></span> <span data-ttu-id="f1a85-127">Dies ist ein asynchrones Ziel.</span><span class="sxs-lookup"><span data-stu-id="f1a85-127">This is an asynchronous target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a85-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1a85-128">See Also</span></span>  
 <span data-ttu-id="f1a85-129">[Erweiterte Ereignisse](../relational-databases/extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1a85-129">[Extended Events](../relational-databases/extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="f1a85-130">[SQL Server von Paketen für erweiterte Ereignisse](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="f1a85-130">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="f1a85-131">[SQL Server Sitzungen für erweiterte Ereignisse](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="f1a85-131">[SQL Server Extended Events Sessions](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span></span>  
 [<span data-ttu-id="f1a85-132">Engine für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1a85-132">SQL Server Extended Events Engine</span></span>](../relational-databases/extended-events/sql-server-extended-events-engine.md)  
  
  
