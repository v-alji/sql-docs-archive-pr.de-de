---
title: 'SQL Server: Buffer Node | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14659e4c1191e2260bccdbcd612f510770913629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620815"
---
# <a name="sql-serverbuffer-node"></a><span data-ttu-id="bbe9b-102">SQLServer: Buffer Node</span><span class="sxs-lookup"><span data-stu-id="bbe9b-102">SQL Server:Buffer Node</span></span>
  <span data-ttu-id="bbe9b-103">Das **Buffer Node** -Objekt stellt Leistungsindikatoren bereit, die vom **Puffer-Manager** -Objekt bereitgestellte Leistungsindikatoren ergänzen.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-103">The **Buffer Node** object provides counters that complement counters provided by the **Buffer Manager** object.</span></span> <span data-ttu-id="bbe9b-104">Es ermöglicht Ihnen die Überwachung der Seitenverteilung im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Pufferpool für jeden NUMA-Knoten (Non-Uniform Memory Access).</span><span class="sxs-lookup"><span data-stu-id="bbe9b-104">It allows you to monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buffer pool page distribution for each non-uniform memory access (NUMA) node.</span></span> <span data-ttu-id="bbe9b-105">Es gibt eine Instanz des **Buffer Node** -Objekts für jeden verwendeten NUMA-Knoten.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-105">There is an instance of the **Buffer Node** object for each NUMA node in use.</span></span> <span data-ttu-id="bbe9b-106">In einer Nicht-NUMA-Architektur gibt es eine einzelne Instanz des **Buffer Node** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-106">On non-NUMA architecture, there will be a single instance of the **Buffer Node** object.</span></span>  
  
## <a name="buffer-node-performance-objects"></a><span data-ttu-id="bbe9b-107">Leistungsobjekte für "Buffer Node"</span><span class="sxs-lookup"><span data-stu-id="bbe9b-107">Buffer Node Performance Objects</span></span>  
 <span data-ttu-id="bbe9b-108">In dieser Tabelle werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Leistungsobjekte für **Buffer Node** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-108">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** performance objects.</span></span>  
  
|<span data-ttu-id="bbe9b-109">Buffer Node-Leistungsindikatoren von SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbe9b-109">SQL Server Buffer Node counters</span></span>|<span data-ttu-id="bbe9b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bbe9b-110">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="bbe9b-111">**Datenbankseiten**</span><span class="sxs-lookup"><span data-stu-id="bbe9b-111">**Database pages**</span></span>|<span data-ttu-id="bbe9b-112">Gibt die Anzahl der Seiten im Pufferpool auf diesem Knoten mit Datenbankinhalt an.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-112">Indicates the number of pages in the buffer pool on this node with database content.</span></span>|  
|<span data-ttu-id="bbe9b-113">**Lebenserwartung von Seiten**</span><span class="sxs-lookup"><span data-stu-id="bbe9b-113">**Page life expectancy**</span></span>|<span data-ttu-id="bbe9b-114">Gibt die Mindestanzahl von Sekunden an, für die eine Seite ohne Verweise im Pufferpool auf diesem Knoten verbleibt.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-114">Indicates the minimum number of seconds a page will stay in the buffer pool on this node without references.</span></span>|  
|<span data-ttu-id="bbe9b-115">**Suchvorgänge in Seiten für lokalen Knoten/Sek.**</span><span class="sxs-lookup"><span data-stu-id="bbe9b-115">**Local Node page lookups/sec**</span></span>|<span data-ttu-id="bbe9b-116">Gibt die Anzahl der Suchanforderungen von diesem Knoten an, die von diesem Knoten erfüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-116">Indicates the number of lookup requests from this node which were satisfied from this node.</span></span>|  
|<span data-ttu-id="bbe9b-117">**Suchvorgänge in Seiten für Remoteknoten/Sek.**</span><span class="sxs-lookup"><span data-stu-id="bbe9b-117">**Remote Note page lookups/sec**</span></span>|<span data-ttu-id="bbe9b-118">Gibt die Anzahl von Suchanforderungen von diesem Knoten an, die von anderen Knoten erfüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-118">Indicates the number of lookup requests from this node which were satisfied from other nodes.</span></span>|  
  
 <span data-ttu-id="bbe9b-119">Wenn SQL Server auf Nicht-NUMA-Hardware ausgeführt wird, sollten die Leistungsindikatoren der Objekte **Buffer Node** und **Puffer-Manager** übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-119">If SQL Server is running on non-NUMA hardware, the counters of **Buffer Node** and **Buffer Manager** objects should match.</span></span>  
  
 <span data-ttu-id="bbe9b-120">Auf NUMA-Hardware sollten die Summen der jeweiligen Leistungsindikatoren aller **Buffer Node** -Objekte ihren Gegenstücken von **Puffer-Manager**entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-120">On NUMA hardware, sums of respective counters of all **Buffer Nodes** should match their counterparts of **Buffer Manager**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbe9b-121">Die Werte und Summen der Leistungsindikatoren stimmen aufgrund der dynamischen Natur der Leistungsindikatoren und der Genauigkeit der Stichprobenahme möglicherweise nicht genau überein.</span><span class="sxs-lookup"><span data-stu-id="bbe9b-121">The counter values and sums may not match precisely due to the dynamic nature of the counters and the sampling accuracy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe9b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbe9b-122">See Also</span></span>  
 <span data-ttu-id="bbe9b-123">[SQL Server, Puffer-Manager-Objekt](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="bbe9b-123">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 <span data-ttu-id="bbe9b-124">[Serverkonfigurationsoptionen für den Serverarbeitsspeicher](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="bbe9b-124">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="bbe9b-125">[Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="bbe9b-125">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 [<span data-ttu-id="bbe9b-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bbe9b-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
