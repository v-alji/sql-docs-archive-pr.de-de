---
title: SQL Server, Ausführungsstatistik-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d1a50c97add4708a58b9edc45fd49982b97a51ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609837"
---
# <a name="sql-server-execstatistics-object"></a><span data-ttu-id="ac6d9-102">SQL Server, Ausführungsstatistik-Objekt</span><span class="sxs-lookup"><span data-stu-id="ac6d9-102">SQL Server, ExecStatistics Object</span></span>
  <span data-ttu-id="ac6d9-103">Das **SQLServer:ExecStatistics** -Objekt in Microsoft SQL Server stellt Leistungsindikatoren zum Überwachen verschiedener Vorgänge zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-103">The **SQLServer:ExecStatistics** object in Microsoft SQL Server provides counters to monitor various executions.</span></span>  
  
 <span data-ttu-id="ac6d9-104">In dieser Tabelle werden die **Exec Statistics** -Leistungsindikatoren von SQL Server beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-104">This table describes the SQL Server **Exec Statistics** counters.</span></span>  
  
|<span data-ttu-id="ac6d9-105">Exec Statistics-Leistungsindikatoren von SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac6d9-105">SQL Server Exec Statistics counters</span></span>|<span data-ttu-id="ac6d9-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac6d9-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="ac6d9-107">**Verteilte Abfrage**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-107">**Distributed Query**</span></span>|<span data-ttu-id="ac6d9-108">Für die Ausführung von verteilten Abfragen wichtige Statistiken.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-108">Statistics relevant to execution of distributed queries.</span></span>|  
|<span data-ttu-id="ac6d9-109">**DTC-Aufrufe**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-109">**DTC calls**</span></span>|<span data-ttu-id="ac6d9-110">Für die Ausführung von DTC-Aufrufen wichtige Statistiken.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-110">Statistics relevant to execution of DTC calls.</span></span>|  
|<span data-ttu-id="ac6d9-111">**Erweiterte Prozeduren**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-111">**Extended Procedures**</span></span>|<span data-ttu-id="ac6d9-112">Für die Ausführung von erweiterten Prozeduren wichtige Statistiken.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-112">Statistics relevant to execution of extended procedures.</span></span>|  
|<span data-ttu-id="ac6d9-113">**OLE DB-Aufrufe**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-113">**OLEDB calls**</span></span>|<span data-ttu-id="ac6d9-114">Für die Ausführung von OLE DB-Aufrufen wichtige Statistiken.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-114">Statistics relevant to execution of OLEDB calls.</span></span>|  
  
 <span data-ttu-id="ac6d9-115">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="ac6d9-115">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="ac6d9-116">Element</span><span class="sxs-lookup"><span data-stu-id="ac6d9-116">Item</span></span>|<span data-ttu-id="ac6d9-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac6d9-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ac6d9-118">**Durchschnittliche Ausführungszeit (ms)**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-118">**Average execution time (ms)**</span></span>|<span data-ttu-id="ac6d9-119">Durchschnittliche Ausführungszeit des ausgewählten Ausführungstyps.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-119">Average execution time of the selected type of execution.</span></span>|  
|<span data-ttu-id="ac6d9-120">**Kumulierte Ausführungszeit (ms) pro Sekunde**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-120">**Cumulative execution time (ms) per second**</span></span>|<span data-ttu-id="ac6d9-121">Aggregierte Ausführungszeit des ausgewählten Ausführungstyps pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-121">Aggregated execution time per second, of the selected type of execution.</span></span>|  
|<span data-ttu-id="ac6d9-122">**Aktuelle Ausführungen**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-122">**Execs in progress**</span></span>|<span data-ttu-id="ac6d9-123">Anzahl der aktuellen Ausführungen des ausgewählten Ausführungstyps.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-123">Number of execs in progress of the selected type of execution.</span></span>|  
|<span data-ttu-id="ac6d9-124">**Gestartete Ausführungen pro Sekunde**</span><span class="sxs-lookup"><span data-stu-id="ac6d9-124">**Exec started per second**</span></span>|<span data-ttu-id="ac6d9-125">Anzahl der pro Sekunde gestarteten Ausführungen des ausgewählten Ausführungstyps.</span><span class="sxs-lookup"><span data-stu-id="ac6d9-125">Number of exes started per second of the selected type of execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac6d9-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac6d9-126">See Also</span></span>  
 [<span data-ttu-id="ac6d9-127">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="ac6d9-127">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
