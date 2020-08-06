---
title: SQL Server, Cursor-Manager nach Typ-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Cursor Manager by Type object
- SQLServer:Cursor Manager by Type
ms.assetid: d67fbd8a-7554-4a16-96f1-d9ee857a95e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7bee15aa2917f7b8890e6c1d3f26cc0e210208a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609847"
---
# <a name="sql-server-cursor-manager-by-type-object"></a><span data-ttu-id="83b92-102">SQL Server, Cursor-Manager nach Typ-Objekt</span><span class="sxs-lookup"><span data-stu-id="83b92-102">SQL Server, Cursor Manager by Type Object</span></span>
  <span data-ttu-id="83b92-103">Das **SQLServer:Cursor-Manager nach Typ** -Objekt stellt Leistungsindikatoren zum Überwachen von Cursorn bereit, die nach dem Typ gruppiert sind.</span><span class="sxs-lookup"><span data-stu-id="83b92-103">The **SQLServer:Cursor Manager by Type** object provides counters to monitor cursors, grouped by type.</span></span>  
  
 <span data-ttu-id="83b92-104">Diese Tabelle beschreibt die Leistungsindikatoren des **SQLServer:Cursor-Manager nach Typ** -Objekts von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="83b92-104">This table describes the SQL Server **Cursor Manager by Type** counters.</span></span>  
  
|<span data-ttu-id="83b92-105">Leistungsindikatoren des SQLServer:Cursor-Manager nach Typ-Objekts</span><span class="sxs-lookup"><span data-stu-id="83b92-105">Cursor Manager by Type counters</span></span>|<span data-ttu-id="83b92-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="83b92-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="83b92-107">**Aktive Cursor**</span><span class="sxs-lookup"><span data-stu-id="83b92-107">**Active cursors**</span></span>|<span data-ttu-id="83b92-108">Anzahl der aktiven Cursor.</span><span class="sxs-lookup"><span data-stu-id="83b92-108">Number of active cursors.</span></span>|  
|<span data-ttu-id="83b92-109">**Cachetrefferquote**</span><span class="sxs-lookup"><span data-stu-id="83b92-109">**Cache Hit Ratio**</span></span>|<span data-ttu-id="83b92-110">Das Verhältnis zwischen Cachetreffern und -suchvorgängen.</span><span class="sxs-lookup"><span data-stu-id="83b92-110">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="83b92-111">**Anzahl der zwischengespeicherten Cursor**</span><span class="sxs-lookup"><span data-stu-id="83b92-111">**Cached Cursor Counts**</span></span>|<span data-ttu-id="83b92-112">Anzahl der Cursor eines bestimmten Typs im Cache.</span><span class="sxs-lookup"><span data-stu-id="83b92-112">Number of cursors of a given type in the cache.</span></span>|  
|<span data-ttu-id="83b92-113">**Verwendungszähler für zwischengespeicherte Cursor/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="83b92-113">**Cursor Cache Use Count/sec**</span></span>|<span data-ttu-id="83b92-114">Häufigkeit, mit der jeder Typ eines zwischengespeicherten Cursors verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="83b92-114">Times each type of cached cursor has been used.</span></span>|  
|<span data-ttu-id="83b92-115">**Cursorspeicherauslastung**</span><span class="sxs-lookup"><span data-stu-id="83b92-115">**Cursor memory usage**</span></span>|<span data-ttu-id="83b92-116">Größe des Speicherplatzes, der durch Cursor belegt wird (KB).</span><span class="sxs-lookup"><span data-stu-id="83b92-116">Amount of memory consumed by cursors in kilobytes (KB).</span></span>|  
|<span data-ttu-id="83b92-117">**Cursoranforderungen/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="83b92-117">**Cursor Requests/sec**</span></span>|<span data-ttu-id="83b92-118">Anzahl der SQL-Cursoranforderungen, die vom Server empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="83b92-118">Number of SQL cursor requests received by server.</span></span>|  
|<span data-ttu-id="83b92-119">**Cursor-Arbeitstabellenverwendung**</span><span class="sxs-lookup"><span data-stu-id="83b92-119">**Cursor worktable usage**</span></span>|<span data-ttu-id="83b92-120">Anzahl der Arbeitstabellen, die von Cursorn verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83b92-120">Number of worktables used by cursors.</span></span>|  
|<span data-ttu-id="83b92-121">**Anzahl der aktiven Cursorpläne.**</span><span class="sxs-lookup"><span data-stu-id="83b92-121">**Number of active cursor plans**</span></span>|<span data-ttu-id="83b92-122">Anzahl der Cursorpläne.</span><span class="sxs-lookup"><span data-stu-id="83b92-122">Number of cursor plans.</span></span>|  
  
 <span data-ttu-id="83b92-123">Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="83b92-123">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="83b92-124">Cursor-Manager-Instanz</span><span class="sxs-lookup"><span data-stu-id="83b92-124">Cursor Manager instance</span></span>|<span data-ttu-id="83b92-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="83b92-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="83b92-126">**_Total**</span><span class="sxs-lookup"><span data-stu-id="83b92-126">**_Total**</span></span>|<span data-ttu-id="83b92-127">Informationen für alle Cursor.</span><span class="sxs-lookup"><span data-stu-id="83b92-127">Information for all cursors.</span></span>|  
|<span data-ttu-id="83b92-128">**API Cursor**</span><span class="sxs-lookup"><span data-stu-id="83b92-128">**API Cursor**</span></span>|<span data-ttu-id="83b92-129">Nur die API-Cursor-Informationen.</span><span class="sxs-lookup"><span data-stu-id="83b92-129">Only the API cursor information.</span></span>|  
|<span data-ttu-id="83b92-130">**TSQL Global Cursor**</span><span class="sxs-lookup"><span data-stu-id="83b92-130">**TSQL Global Cursor**</span></span>|<span data-ttu-id="83b92-131">Nur die globalen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Cursorinformationen.</span><span class="sxs-lookup"><span data-stu-id="83b92-131">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] global cursor information.</span></span>|  
|<span data-ttu-id="83b92-132">**TSQL Local Cursor**</span><span class="sxs-lookup"><span data-stu-id="83b92-132">**TSQL Local Cursor**</span></span>|<span data-ttu-id="83b92-133">Nur die lokalen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Cursorinformationen.</span><span class="sxs-lookup"><span data-stu-id="83b92-133">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] local cursor information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83b92-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83b92-134">See Also</span></span>  
 [<span data-ttu-id="83b92-135">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="83b92-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
